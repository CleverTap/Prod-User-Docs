---
title: FirstConnectt
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

FirstConnectt is a Communications Platform as a Service (CPaaS) provider that enables businesses to engage customers across multiple channels. When integrated with CleverTap, FirstConnectt delivers transactional and promotional SMS messages directly from the CleverTap dashboard, with full DLR (Delivery Receipt) tracking for visibility into campaign performance and delivery status.

Here are a few use cases where businesses can integrate FirstConnectt with CleverTap:

- **Transactional Alerts:** Deliver real-time OTPs, order confirmations, and payment updates.
- **Promotional Campaigns:** Announce offers, discounts, or product launches to targeted user segments.
- **Abandoned Cart Reminders:** Prompt users to complete their purchase with time-sensitive nudges.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and supported by FirstConnectt. For any questions or issues related to this integration, contact [FirstConnectt support](mailto:care@firstconnectt.com).
</Callout>

## Prerequisites for Integration

Before integrating FirstConnectt with CleverTap, ensure the following are in place:

- An active CleverTap account with SMS channels enabled.
- A FirstConnectt account with the following credentials, provided by your FirstConnectt point of contact:
  - Username and password
  - Sender ID
  - DLT credentials (required for accounts registered in India)
- DLT compliance for your FirstConnectt account, if you are registered in India.

## Integrate FirstConnectt with CleverTap

Integrating FirstConnectt with CleverTap involves the following three steps:&#x20;

1. [Find your API credentials](doc:firstconnectt-sms#find-firstconnectt-api-credentials)
2. [Set Up CleverTap Dashboard](doc:firstconnectt-sms#set-up-clevertap-dashboard)
3. [Send Test SMS](doc:firstconnectt-sms#send-test-sms)

### Find FirstConnectt API Credentials

To complete the setup, gather the following details from your FirstConnectt account or FirstConnectt support:

<Table>
  <thead>
    <tr>
      <th>
        Credential
      </th>

      <th style={{ width: "32.7%" }}>
        Description
      </th>

      <th style={{ width: "51.5%" }}>
        Where to Find
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Endpoint URL
      </td>

      <td>
        The API endpoint for FirstConnectt
      </td>

      <td>
        Fixed value: `https://connecttone.io/api/v1/sms/clevertap`
      </td>
    </tr>

    <tr>
      <td>
        API Key
      </td>

      <td>
        Used in the `Authorization` request header
      </td>

      <td>
        _Profile Settings_ in your FirstConnectt Customer Portal
      </td>
    </tr>

    <tr>
      <td>
        Sender ID (SID)
      </td>

      <td>
        The sender ID linked to your account
      </td>

      <td>
        Provided by your FirstConnectt point of contact
      </td>
    </tr>
  </tbody>
</Table>

### Set Up CleverTap Dashboard

Configuring the CleverTap dashboard connects and authenticates your FirstConnectt SMS provider using the Generic SMS provider option. To set up your CleverTap dashboard, perform the following steps:

1. Go to _Settings > Channels > SMS_ in the CleverTap dashboard.
2. Click **+ Add Provider**. The _Add SMS provider_ page opens.
3. Under _Provider_, select _Other (Generic)_ and enter the following details:

| Field         | Description                                                                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname      | Enter a unique name for this provider. For example: `FirstConnectt SMS`.                                                                                      |
| Callback URL  | Contact your FirstConnectt point of contact to obtain the callback URL and configure it on the FirstConnectt platform to receive SMS delivery status updates. |
| Request Type  | Select **POST** as the HTTP method.                                                                                                                           |
| HTTP Endpoint | Enter the FirstConnectt API endpoint: `https://connecttone.io/api/v1/sms/clevertap`                                                                           |


<Image src="https://files.readme.io/10db89a7897d54b5c878c3f8fa6617dfeb87bce16100e00e3f735b3b48d28aea-Screenshot_2026-10-07_at_15.31.51.png" alt="The provider configuration section in the SMS Channel section" align="center" caption="Provider Configuration in SMS Channel" border={true} />


4. Under the _Headers_ section, enter the following key-value pairs:

| Key             | Value              |
| --------------- | ------------------ |
| `Authorization` | `Bearer <API_KEY>` |
| `Content-Type`  | `application/json` |

Replace `<API_KEY>` with the API key from your FirstConnectt Customer Portal.


<Image src="https://files.readme.io/4e473631c862c264b07f1b4845c1cef7fd2f49c91afa89836c8afb2bbb26c822-Screenshot_2026-10-07_at_15.33.07.png" alt="The Headers tab in the Providers Configuration section" align="center" caption="Headers Tab in the Providers Configuration section" border={true} />


5. Under _Parameters_, select _JSON_ as the request type. Use the following sample payload:

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

  CleverTap replaces `$$Body`, `$$To`, `$$TemplateID`, and `$$MessageID` dynamically at send time with the actual message content, recipient number, template ID, and a unique message identifier. `$$MessageID` is required for accurate DLR (Delivery Report) tracking: FirstConnectt must return the same ID in the delivery callback for CleverTap to match and record the delivery status.
</Callout>

6. Select the _Batch_ option to send multiple SMS records in a single request. A single batch supports a maximum of 1,000 records.
7. Click **Save**. A prompt appears to send a test SMS.


<Image src="https://files.readme.io/5e608ce00036e19a513207538d96b1668232556787b34c3dbd24a83f4e141b9d-Screenshot_2026-10-07_at_15.39.12.png" alt="The Parameters tab in the Providers Configuration section" align="center" caption="Parameters Tab in the Providers Configuration section" border={true} />


### Send Test SMS

Sending a test SMS confirms that the FirstConnectt integration is working before you launch a live campaign. To do so, perform the following steps:

1. Click the **Send Test SMS** link after saving your provider configuration.
2. Enter the following details:

| Value         | Description                       |
| ------------- | --------------------------------- |
| Country Code  | Extension Code of the Country     |
| Mobile number | The mobile number of the User     |
| Template ID   | Unique ID for the template        |
| Message       | A custom message seen by the user |

3. Click **Send Test**.


<Image src="https://files.readme.io/e03621eb64ce782f6d02a242ddff619bd14babb111f3eaf21ba2189994b15c6d-Screenshot_2026-10-07_at_15.48.51.png" alt="The test-SMS pop-up in the SMS Configuration section" align="center" caption="Test SMS Pop-Up" border={true} />


If the configuration is correct, the test message is delivered, and FirstConnectt returns a DLR update. If an error occurs, for example, due to incorrect credentials or an invalid endpoint, CleverTap displays a failure notification.

## Set Up SMS Callbacks

Setting up SMS callbacks enables CleverTap to receive delivery status updates from FirstConnectt for accurate campaign reporting. To do so, perform the following steps:

1. Go to _Settings > Channels > SMS_ in the CleverTap dashboard.
2. Open your FirstConnectt provider by clicking its nickname.
3. Copy the _Delivery Report Callback URL_ from the _Provider Setup_ page.


<Image src="https://files.readme.io/10db89a7897d54b5c878c3f8fa6617dfeb87bce16100e00e3f735b3b48d28aea-Screenshot_2026-10-07_at_15.31.51.png" alt="The provider configuration section in the SMS Channel section" align="center" caption="Provider Configuration in SMS Channel" border={true} />


5. Share this URL with FirstConnectt support so they can configure it on the FirstConnectt platform.

## Verify Successful Integration

Your integration is successful when all three of the following criteria are met:

- The test SMS is delivered to the intended mobile number.
- You receive a DLR callback from FirstConnectt at the configured CleverTap callback URL, indicating delivery, failure, or queue status.
- CleverTap logs show no errors related to authentication, payload structure, or message transmission.

Once these conditions are met, you can proceed to build SMS campaigns or set up Journeys using FirstConnectt as your SMS provider.

## Create Campaign

For detailed instructions on creating an SMS campaign with FirstConnectt as your provider, refer to [Create SMS Campaign](doc:create-message-sms).

## Create Journey

For detailed instructions on creating an SMS journey using FirstConnectt as your provider, refer to [Journeys.](doc:journeys)&#x20;