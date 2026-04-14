---
title: Azmarq
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Azmarq](https://www.azmarq.com/) is a global messaging and communications platform that enables enterprises to deliver transactional, OTP, and promotional SMS messages worldwide. Integrating Azmarq with CleverTap allows you to send SMS messages directly from CleverTap’s engagement dashboard for automated and event-driven communication.

This integration supports HTTP-based message delivery, secure API authentication, and dynamic payload handling, enabling scalable, reliable campaigns.

Businesses integrate Azmarq with CleverTap to:

* **Send Transactional Messages**: Deliver OTPs, notifications, and real-time updates.
* **Run Promotional Campaigns**: Engage users through personalized and targeted offers.
* **Automate Customer Journeys**: Trigger SMS messages based on user activity or lifecycle events.

Integrating Azmarq with CleverTap combines Azmarq’s global SMS reach with CleverTap’s intelligent segmentation and campaign automation capabilities.

# Prerequisites for Integration

Before integrating, check the following:

* You have an active CleverTap account with SMS channels enabled.
* You have an Azmarq account with API access for SMS services.
* You have your _Azmarq API Key_ and _Sender ID_.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and continuously improved by Azmarq. For any questions or issues, contact [Azmarq](mailto:support@azmarq.com) or visit the [Azmarq Support Center](https://www.azmarq.com/contact/) for support and resolution.
</Callout>

# Integrate Azmarq with CleverTap

To integrate Azmarq with CleverTap, perform the following steps:

1. [Find Azmarq Account Credentials](doc:azmarq#find-azmarq-account-credentials)
2. [Set Up CleverTap Dashboard](doc:azmarq#set-up-clevertap-dashboard)
3. [Send Test SMS](doc:azmarq#send-test-sms)

## Find Azmarq Account Credentials

Before configuring CleverTap, gather the following credentials from your Azmarq account:

1. Log in to your Azmarq Dashboard and go to _Settings_ > _API Keys_.
2. Copy your _API Key_.

Note your registered _Sender ID_ used for sending SMS messages.

## Set Up CleverTap Dashboard

Once you have your Azmarq credentials, configure CleverTap to connect with Azmarq:

1. Go to _Settings_ > _Engage_ > _Channels_ > _SMS_ in the CleverTap dashboard.
2. Click **+ Add Provider**. The Add SMS provider page opens.

<Image align="center" alt="Add Provider" border={true} caption="Add Provider in CleverTap" src="https://files.readme.io/8ca98feff96deb7a4d4b6c4a0576f0b108f3d696f98dfbaa9b61faca58641cf2-image.png" width="65%" />

3. Under **Provider**, select _Other (Generic)_ and enter the following details:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Nickname**
      </td>

      <td>
        Enter a name such as `Azmarq_SMS`.
      </td>
    </tr>

    <tr>
      <td>
        **Request Type**
      </td>

      <td>
        Select `POST`.
      </td>
    </tr>

    <tr>
      <td>
        **Delivery Report Callback URL**
      </td>

      <td>
        Enter this URL in the Azmarq portal to receive delivery reports. Refer to [Set Up SMS Callbacks](doc:azmarq#set-up-sms-callbacks).
      </td>
    </tr>

    <tr>
      <td>
        **HTTP Endpoint**
      </td>

      <td>
        Paste `https://api.azmarq.com/v1/sms`.  
        Ensure that the URL is in HTTPS format, that is, your URL must begin with `https://`.
      </td>
    </tr>
  </tbody>
</Table>

4. Under **Headers**, enter the following keys and values:

| Key            | Value               |
| -------------- | ------------------- |
| `apiKey`       | Your Azmarq API Key |
| `Content-Type` | `application/json`  |

<Callout icon="📘" theme="info">
  #### Note

  Ensure your API Key is copied correctly. An incorrect API Key will return an authentication error.
</Callout>

5. Under **Parameters**, select `JSON` as the request type and paste the following JSON configuration:

```json
{
  "from": "<Your Sender ID>",
  "type": "sms",
  "data_coding": "plain",
  "campaign_id": "<Campaign ID>",
  "to": "$$To",
  "dlt_template_id": "$$TemplateID",
  "body": "$$Body",
  "message_id": "$$MessageID",
  "callback": "<CleverTap Callback URL>"
}
```

<Callout icon="📘" theme="info">
  #### Note

  Replace `<Your Sender ID>` and `<Campaign ID>` with your actual Azmarq SMS sender ID and campaign identifier.
  The parameters `$$To`, `$$TemplateID`, `$$Body`, and `$$MessageID` are dynamically replaced by CleverTap during campaign execution.
</Callout>

6. (Optional) Select the _Batch_ option, then enter the required details to send multiple SMS messages in a single API request.

<Callout icon="📘" theme="info">
  #### Single Batch Limit

  A single batch can have a maximum of 1,000 records.
</Callout>

7. Click **Save**. A pop-up opens, prompting you to [Send Test SMS](doc:azmarq#send-test-sms).

<Image align="center" alt="Set Parameters" border={true} caption="Set Parameters for Azmarq in CleverTap" src="https://files.readme.io/4eab04e531dbbf3dc25169984b38734ff42560ad76cfd4d1a4b415a5b40ba1d7-image.png" width="65% " />

## Send Test SMS

Before launching campaigns, verify that the integration is configured correctly by sending a test SMS.

To verify that the integration works, perform the following steps:

1. Click the **Send Test SMS** hyperlink before creating SMS campaigns and journeys.
2. Enter the following details:
   * _Country Code and Mobile Number_: Enter the country code and mobile number to which you want to send the message.
   * _Message_: Enter sample text, such as `This is a test message powered by Azmarq.`
3. Click **Send Test**.

<Image align="center" alt="Send Test SMS" border={true} caption="Send a Test SMS using Azmarq in CleverTap" src="https://files.readme.io/8be3ee13d2fb6100577fb6b60ac08029c8999657aa5c35663bbadbd27f02c5fb-e7e63cd39f78b8fc3b9e1afb937653a43940bd341d37c130e909eddce89c45ba-test_.png" width="65%" />

If the setup is correct, youn will receive a success message in CleverTap, and the SMS will be delivered to the target number.

## Set Up SMS Callbacks

To track SMS requests, perform the following steps:

1. Copy the _Delivery Report Callback URL_ from CleverTap and add it to the JSON payload. You can find the Delivery report callback URL on the CleverTap dashboard under the Provider  
   Setup page _Settings_ > _Channels_ > _SMS_ > _Provider Nickname_.
2. Add it to the JSON payload field `"callback": "<CleverTap Callback URL>"`.
3. Save the configuration to enable CleverTap to receive DLR updates from Azmarq.

<Image align="center" alt="Set Up SMS Callbacks" border={true} caption="Set Up SMS Callbacks in CleverTap" src="https://files.readme.io/27be1e248b9101270026cf9be1bc09c56248d3f3b3c6cbbb4feef98e3bb6c85f-image.png" width="65%" />

## Verify Successful Integration

Your integration is successful when the following criteria are met:

* The test SMS is successfully delivered to the target mobile number.
* No authentication or endpoint errors appear in CleverTap logs.
* Message delivery can be verified from your Azmarq dashboard.

Once verified, you can build and publish [SMS campaigns](doc:create-message-sms) or set up [Journeys](doc:journeys) using Azmarq as your SMS provider.
