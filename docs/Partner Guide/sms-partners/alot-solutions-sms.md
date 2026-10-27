---
title: Alot Solutions
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

Alot Solutions is a Communications Platform as a Service (CPaaS) provider that enables businesses to engage customers across multiple channels. When integrated with CleverTap, Alot Solutions delivers transactional and promotional SMS messages directly from the CleverTap dashboard, with full DLR (Delivery Receipt) tracking for visibility into campaign performance and delivery status.

Here are a few ways businesses use Alot Solutions with CleverTap:

- **Transactional Alerts:** Deliver real-time OTPs, order confirmations, and payment updates.
- **Promotional Campaigns:** Announce offers, discounts, or product launches to targeted user segments.
- **Abandoned Cart Reminders:** Prompt users to complete their purchase with time-sensitive nudges.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and supported by Alot Solutions. For any questions or issues related to this integration, contact [Alot Solutions support](mailto:support@alotsolutions.com).
</Callout>

This document covers the following:

- [Prerequisites for Integration](#prerequisites-for-integration)
- [Integrate Alot Solutions with CleverTap](#integrate-alot-solutions-with-clevertap)
- [Set Up SMS Callbacks](#set-up-sms-callbacks)
- [Verify Successful Integration](#verify-successful-integration)

## Prerequisites for Integration

Before integrating Alot Solutions with CleverTap, ensure the following are in place:

- An active CleverTap account with SMS channels enabled.
- An Alot Solutions account with the following credentials, provided by your Alot Solutions point of contact:
  - Username and password
  - Sender ID
  - DLT credentials (required for accounts registered in India)
- DLT compliance for your Alot Solutions account, if you are registered in India.

## Integrate Alot Solutions with CleverTap

Integrating Alot Solutions with CleverTap requires three steps: finding your API credentials, configuring the CleverTap dashboard, and sending a test SMS to confirm delivery.

### Find Alot Solutions API Credentials

To complete the setup, gather the following details from your Alot Solutions account or Alot Solutions support:

| Credential      | Description                                | Where to Find                                             |
| --------------- | ------------------------------------------ | --------------------------------------------------------- |
| Endpoint URL    | The API endpoint for Alot Solutions        | Fixed value: `https://alots.io/api/v1/sms/clevertap`      |
| API Key         | Used in the `Authorization` request header | _Profile Settings_ in your Alot Solutions Customer Portal |
| Sender ID (SID) | The sender ID linked to your account       | Provided by your Alot Solutions point of contact          |

### Set Up CleverTap Dashboard

Configuring the CleverTap dashboard connects and authenticates your Alot Solutions SMS provider using the Generic SMS provider option.

1. Go to _Settings > Channels > SMS_ in the CleverTap dashboard.
2. Click **+ Add Provider**. The _Add SMS provider_ page opens.
3. Under _Provider_, select **Other (Generic)** and enter the following details:

| Field         | Description                                                                                                                                                     |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname      | Enter a unique name for this provider. For example: `Alot Solutions SMS`.                                                                                       |
| Callback URL  | Contact your Alot Solutions point of contact to obtain the callback URL and configure it on the Alot Solutions platform to receive SMS delivery status updates. |
| Request Type  | Select **POST** as the HTTP method.                                                                                                                             |
| HTTP Endpoint | Enter the Alot Solutions API endpoint: `https://alots.io/api/v1/sms/clevertap`                                                                                  |


<Image src="https://files.readme.io/2dedf8fa1197adf67c4f8eba4f7d6b1757b6b484b300fab651723cf9ab542b4a-Screenshot_2026-10-12_at_16.25.56.png" alt="The Provider Configuration section for Alot Solutions in the SMS Channel" align="center" caption="Provider Configuration in SMS Channel" border={true} />


4. Under the _Headers_ section, enter the following key-value pairs:

| Key             | Value              |
| --------------- | ------------------ |
| `Authorization` | `Bearer <API_KEY>` |
| `Content-Type`  | `application/json` |

Replace `<API_KEY>` with the API key from your Alot Solutions Customer Portal.


<Image src="https://files.readme.io/4e473631c862c264b07f1b4845c1cef7fd2f49c91afa89836c8afb2bbb26c822-Screenshot_2026-10-07_at_15.33.07.png" alt="The Headers section in the Provider Configuration page for SMS" align="center" caption="Headers section for SMS Channel" border={true} />


5. Under _Parameters_, select **JSON** as the request type. Use the following sample payload:

```json
{
  "route": "Transactional",
  "sender": "$$hid",
  "tid": "$$TemplateID",
  "msgs": [
    {
      "message": "$$Body",
      "mobile": "$$To",
      "msg_id": "$$MessageID"
    }
  ]
}
```

<Callout icon="📘" theme="info">
  #### Note

  CleverTap replaces `$$Body`, `$$To`, `$$TemplateID`, and `$$MessageID` dynamically at send time with the actual message content, recipient number, template ID, and a unique message identifier. `$$MessageID` is required for accurate DLR (Delivery Report) tracking: Alot Solutions must return the same ID in the delivery callback for CleverTap to match and record the delivery status.
</Callout>

6. Select the **Batch** option to send multiple SMS records in a single request. A single batch supports a maximum of 1,000 records.
7. Click **Save**. A prompt appears to send a test SMS.


<Image src="https://files.readme.io/ad8a33cb5998e37a7f1387db15c6a5d57dd8f1b1a351f4fb7fb7abe73d338ef0-Screenshot_2026-10-12_at_16.34.44.png" align="center" caption="Parameters tab in the Provider Configuration section" border={true} />


### Send a Test SMS

Sending a test SMS confirms that the Alot Solutions integration is working before you launch a live campaign.

1. Click the **Send Test SMS** link after saving your provider configuration.
2. Enter the following details:
   - **Country Code and Mobile Number:** Enter the country code and mobile number for the test recipient.
   - **Message:** Enter sample text, for example: `This is a test message powered by Alot Solutions`.
3. Click **Send Test**.


<Image src="https://files.readme.io/e03621eb64ce782f6d02a242ddff619bd14babb111f3eaf21ba2189994b15c6d-Screenshot_2026-10-07_at_15.48.51.png" alt="The Test SMS pop-up." align="center" caption="Test SMS Pop-Up" border={true} />


If the configuration is correct, the test message is delivered, and Alot Solutions returns a DLR update. If an error occurs, for example, due to incorrect credentials or an invalid endpoint, CleverTap displays a failure notification.

## Set Up SMS Callbacks

Setting up SMS callbacks lets CleverTap receive delivery status updates from Alot Solutions for accurate campaign reporting.

1. Go to _Settings > Channels > SMS_ in the CleverTap dashboard.
2. Open your Alot Solutions provider by clicking its nickname.
3. Copy the _Delivery Report Callback URL_ from the _Provider Setup_ page.


<Image src="https://files.readme.io/2dedf8fa1197adf67c4f8eba4f7d6b1757b6b484b300fab651723cf9ab542b4a-Screenshot_2026-10-12_at_16.25.56.png" alt="The Provider Configuration section for Alot Solutions in the SMS Channel" align="center" caption="Provider Configuration in SMS Channel" border={true} />


4. Share this URL with Alot Solutions support so they can configure it on the Alot Solutions platform.

## Verify Successful Integration

Your integration is successful when all three of the following criteria are met:

- The test SMS is delivered to the intended mobile number.
- You receive a DLR callback from Alot Solutions at the configured CleverTap callback URL, indicating delivery, failure, or queue status.
- CleverTap logs show no errors related to authentication, payload structure, or message transmission.

Once these conditions are met, you can proceed to build SMS campaigns or set up Journeys using Alot Solutions as your SMS provider.

## Create Campaign

For detailed instructions on creating an SMS campaign with FirstConnectt as your provider, refer to [Create SMS Campaign](doc:create-message-sms).

## Create Journey

For detailed instructions on creating an SMS journey using FirstConnectt as your provider, refer to [Journeys.](doc:journeys)&#x20;