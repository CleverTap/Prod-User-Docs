---
title: EnableX
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[EnableX](https://www.enablex.io/) is a global communication platform that provides APIs for SMS, WhatsApp, and other messaging channels. Integrating EnableX with CleverTap allows you to send SMS notifications and promotional messages directly from CleverTap’s engagement dashboard.

This integration supports HTTP-based message delivery, DLT-compliant messaging, and secure authentication to ensure reliable delivery and compliance.

Businesses integrate EnableX with CleverTap to:

* **Send Transactional Messages**: Deliver OTPs, alerts, and account notifications in real time.
* **Run Promotional Campaigns**: Send offers and updates based on user segments and behavioral triggers.
* **Automate Engagement Journeys**: Reconnect with users through automated and targeted SMS workflows.

Integrating EnableX with CleverTap combines EnableX’s robust communication APIs with CleverTap’s intelligent engagement platform.

# Prerequisites for Integration

Before integrating, check the following:

* You have an active CleverTap account with SMS channels enabled.
* You have an EnableX account with SMS API permissions.
* You have your _EnableX Username_ and _Password_ (available from your EnableX portal).

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and continuously improved by EnableX. For any questions or issues, contact [EnableX](mailto:support@enablex.io) for support and resolution.
</Callout>

# Integrate EnableX with CleverTap

To integrate EnableX with CleverTap, perform the following steps:

1. [Find EnableX Account Credentials](#find-enablex-account-credentials)
2. [Set Up CleverTap Dashboard](#set-up-clevertap-dashboard)
3. [Send Test SMS](doc:enablex#send-test-sms)

## Find EnableX Account Credentials

Before configuring CleverTap, obtain your EnableX credentials. Once your EnableX SMS account is provisioned, you will receive your **Username** and **Password** from the EnableX team via your registered email. These credentials are required for authenticating the integration with CleverTap. If you have not received them, contact your EnableX account representative or email [support@enablex.io](mailto:support@enablex.io) to request your SMS API credentials.

Keep these details ready for configuring the CleverTap dashboard.

<Image align="center" alt="SMS API credentials via Email" border={true} caption="SMS API Credentials via Email" src="https://files.readme.io/46bcfd465a358f283e878df8d3568dd4767cf69448fae563c211c5a33ab46ee9-image.png" width="65% " />

## Set Up CleverTap Dashboard

Once you have your EnableX credentials, perform the following steps to connect EnableX to CleverTap:

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
        Enter a name such as `EnableX_SMS`.
      </td>
    </tr>

    <tr>
      <td>
        **Delivery Report Callback URL**
      </td>

      <td>
        Enter this URL in the EnableX portal to receive delivery reports. Refer to [Set Up SMS Callbacks](doc:enablex#set-up-sms-callbacks).
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
        **HTTP Endpoint**
      </td>

      <td>
        Paste `https://api.enablex.io/sms/v1/clevertap`.  
        Ensure that the URL is in HTTPS format, that is, your URL must begin with `https://`.
      </td>
    </tr>
  </tbody>
</Table>

4. Under **Authentication**, enter the _Username_ and _Password_ copied from your EnableX account.

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

  Replace `<Your Sender ID>` and `<Campaign ID>` with your actual EnableX SMS sender ID and campaign identifier.
  The parameters `$$To`, `$$TemplateID`, `$$Body`, and `$$MessageID` are dynamically replaced by CleverTap during campaign execution.
</Callout>

<Image align="center" alt="Set Parameters" border={true} caption="Set Parameters" src="https://files.readme.io/92137835ff6ca5b9885d3d04b6835288a232e0a6d84ff6bed71237f3f30af590-image.png" width="65% " />

6. (Optional) Select the _Batch_ option, then enter the required details to send multiple SMS messages in a single API request.

<Callout icon="📘" theme="info">
  #### Single Batch Limit

  A single batch can have a maximum of 1,000 records.
</Callout>

7. Click **Save**. A pop-up opens, prompting you to [Send Test SMS](doc:enablex#send-test-sms).

<Image align="center" alt="Set Parameters" border={true} caption="Set Parameters for EnableX in CleverTap" src="https://files.readme.io/4eab04e531dbbf3dc25169984b38734ff42560ad76cfd4d1a4b415a5b40ba1d7-image.png" width="65%" />

## Send Test SMS

Before launching campaigns, verify that the integration is working correctly by sending a test SMS.

To verify that the integration works:

1. Click the **Send Test SMS** hyperlink before creating SMS campaigns and journeys.
2. Enter the following details:
   * _Country Code and Mobile Number_: Enter the country code and mobile number to which you want to send the message.
   * _Message_: Enter sample text, such as `This is a test message powered by EnableX.`
3. Click **Send Test**.

<Image align="center" alt="Send Test SMS" border={true} caption="Send Test SMS" src="https://files.readme.io/456ae459bb9f19fb36e023f572e987c7093d3666ac7b1a418bc77876b6c8e09a-image.png" width="65% " />

If the setup is correct, the test message will be successfully delivered. If not, verify your credentials and endpoint configuration.

# Set Up SMS Callbacks

To track SMS requests, perform the following steps:

1. Copy the _Delivery Report Callback URL_ from CleverTap and add it to the JSON payload. You can find the Delivery report callback URL on the CleverTap dashboard under the Provider  
   Setup page _Settings_ > _Channels_ > _SMS_ > _Provider Nickname_.
2. Add it to the JSON payload field `"callback": "<CleverTap Callback URL>"`.
3. Save the configuration to enable CleverTap to receive DLR updates from EnableX.

<Image align="center" alt="Set Up SMS Callbacks" border={true} caption="Set Up SMS Callbacks in CleverTap" src="https://files.readme.io/27be1e248b9101270026cf9be1bc09c56248d3f3b3c6cbbb4feef98e3bb6c85f-image.png" width="35% " />

# Verify Successful Integration

Your integration is successful when the following criteria are met:

* The test SMS is successfully delivered to the target mobile number.
* No authentication or endpoint errors are shown in CleverTap logs.
* Delivery reports appear through callbacks or in the EnableX dashboard.

Once verified, you can proceed to build and publish [SMS campaigns](doc:create-message-sms) or set up [Journeys](doc:journeys) using EnableX as your SMS provider.
