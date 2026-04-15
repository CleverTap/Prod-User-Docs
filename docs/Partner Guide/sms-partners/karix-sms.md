---
title: Karix
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Karix](https://www.karix.com) is a global mobile engagement provider with more than 20 years of mobile CRM (mCRM) experience. Integrating Karix with CleverTap lets you send SMS messages directly from CleverTap's engagement dashboard for automated, event-driven communication.

This integration supports HTTP-based message delivery through the Pod3 JSON API, secure header-based authentication, and dynamic payload handling, enabling scalable, reliable campaigns.

Businesses integrate Karix with CleverTap to:

* **Send Transactional Messages**: Deliver essential, non-promotional information related to a user's activity or account, such as service updates, OTPs, and alerts.
* **Run Promotional Campaigns**: Engage users through personalized marketing messages and targeted offers.
* **Send OTPs**: Authenticate users and authorize transactions with secure one-time passwords.
* **Share Informational Updates**: Deliver non-promotional notifications such as reminders, confirmations, and status updates.

Integrating Karix with CleverTap combines Karix's global SMS reach and mCRM expertise with CleverTap's intelligent segmentation and campaign automation capabilities.

# Prerequisites for Integration

Before integrating, check the following:

* You have an active CleverTap account with SMS channels enabled.
* You have completed SMS onboarding with Karix and moved your account to Pod3 (AWS open API cluster).
* You have created a Karix TM Chain.
* You have configured PE ID and templates in your Karix account. (@Parth: What is PE ID?)
* You have your Karix _Authorization Key_ (AWS whitelisted key) and _API Key_.

<Callout icon="🚧" theme="warn">
  #### **Support for Integration**

  Karix has fully completed this integration and is committed to its ongoing maintenance and improvements. The CleverTap Karix integration was rigorously tested for flawless performance. For any support or issue resulution, reach out to [Karix Support Team](mailto:tech-support@karix.com).
</Callout>

# Integrate Karix with CleverTap

To integrate Karix with CleverTap, perform the following steps:

1. [Find Karix Account Credentials](doc:karix-sms#find-karix-account-credentials)
2. [Set Up CleverTap Dashboard](doc:karix-sms#set-up-clevertap-dashboard)
3. [Send Test SMS](doc:karix-sms#send-test-sms)

## Find Karix Account Credentials

Before configuring CleverTap, gather the following credentials from your Karix account:

1. Log in to your Karix account and go to your API or account settings.
2. Copy your _Authorization Key_ (AWS whitelisted key).
3. Note your _API Key_ and registered _Sender ID_ used for sending SMS messages.

Keep these credentials ready for configuring the CleverTap dashboard.

## Set Up CleverTap Dashboard

Once you have your Karix credentials, configure CleverTap to connect with Karix:

1. Go to _Settings_ > _Channels_ > _SMS_ in the CleverTap dashboard.

2. Click **+ Add Provider**. The Add SMS provider page opens.

3. Under **Provider**, select _Other (Generic)_ and enter the following details:

   <Image align="center" border={true} caption="Add Provider Details" src="https://files.readme.io/80b3dc9ee51348c3631c2ec2cc92c24d958d613c8b85f20e763d6b37b83828d0-Provider_Configuration.png" width="85% " />

| **Field**                        | **Description**                                                                                                                                    |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nickname**                     | Enter a name such as `Karix_SMS`.                                                                                                                  |
| **Delivery Report Callback URL** | Enter this URL in the Karix portal to receive delivery reports. Refer to [Set Up SMS Callbacks](doc:karix-sms#set-up-sms-callbacks).               |
| **Request Type**                 | Select `POST`.                                                                                                                                     |
| **HTTP Endpoint**                | Paste `https://pod3-japi.instaalerts.zone/receiver/jsonapi`. Ensure that the URL is in HTTPS format, that is, your URL must begin with `https://`. |
| **Authentication**               | Select `No Authentication` (authentication is handled via headers).                                                                                |

4. Under **Headers**, enter the following key-value pairs:

   <Image align="center" border={true} caption="Add Key-Value Pair" src="https://files.readme.io/097fc4263d6c3b8eada27babdb3ee8c1d14b66df9ebd33530fd24dbe37d47640-Add_Key-Value_Pairs.png" width="65% " />

| **Key**         | **Value**                      |
| --------------- | ------------------------------ |
| `Authorization` | Your Karix AWS whitelisted key |
| `Content-Type`  | `application/json`             |

<Callout icon="📘" theme="info">
  #### **Note**

  Ensure your Authorization key is copied correctly. An incorrect key will return an authentication error.
</Callout>

5. Under **Parameters**, select `JSON` as the request type and paste the following JSON configuration:

   <Image align="center" border={true} caption="JSON Payload" src="https://files.readme.io/98dad1a66668f92b9c3c1e372e1f489162d38088836d480a9d34722d47053ede-Additional_Parameters.png" width="85% " />

   **Request Payload**

```json
{
  "ver": "1.0",
  "key": "XXXXXXXXXXXXXXXXXXXXXXXX",
  "encrypt": "0",
  "messages": [
    {
      "dest": [
        "$$T0"
      ],
      "text": "$$Body",
      "send": "<Client Sender ID>",
      "type": "PM",
      "tag1": "$$CampaignID",
      "tag2": "$$MessageID",
      "tag3": "tag3_test",
      "tag4": "tag4_test",
      "tag5": "tag5_test"
    }
  ]
}
```

| **Parameter** | **Description**                                                    | **Required** |
| ------------- | ------------------------------------------------------------------ | ------------ |
| `dest`        | Recipient's mobile number. Use `$$To` for dynamic replacement.     | Yes          |
| `text`        | Message text content. Use `$$Body`.                                | Yes          |
| `send`        | Sender ID registered in Karix.                                     | Yes          |
| `type`        | Message type (e.g., `PM` for Promotional, `TM` for Transactional). | Yes          |
| `tag1`        | CleverTap Campaign ID. Use `$$CampaignID`.                         | Yes          |
| `tag4`        | CleverTap Message ID. Use `$$MessageID`.                           | Yes          |
| `tag2`        | Optional additional tag.                                           | Optional     |
| `tag3`        | Optional additional tag.                                           | Optional     |
| `tag5`        | Optional additional tag.                                           | Optional     |

<Callout icon="📘" theme="info">
  #### **Note**

  Replace `<Your Karix API Key>` and `<Your Sender ID>` with your actual Karix credentials. The parameters `$$To`, `$$Body`, `$$CampaignID`, and `$$MessageID` are dynamically replaced by CleverTap during campaign execution. For more information about `$$` variables, refer to the [System Dynamic Replacements](https://docs.clevertap.com/docs/generic-sms#system-dynamic-replacements) section listed under Generic SMS document.

  **Ensure that you do not select the _Batch_ option.**
</Callout>

6. Click **Save**. A pop-up opens, prompting you to **Send Test SMS**.

## Send Test SMS

Sending a test SMS helps confirm that your Karix integration is working before launching a live campaign. This ensures that the API endpoint is correctly configured, that authentication is valid, and that messages can be delivered.

To verify that the integration works, perform the following steps:

1. Click the **Send Test SMS** hyperlink before creating SMS campaigns and journeys.
2. Enter the following details:

   <Image align="center" border={true} caption="Send Test SMS" src="https://files.readme.io/53da4d969e880a747380fdec1f442ac0b021f20e2df5a894e367bced31917107-Send_Test_SMS_.png" width="65% " />

   * _Country Code and Mobile Number_: Enter the country code and mobile number to which you want to send the message.
   * _Message_: Enter sample text (DLT whitelisted), such as `This is a test message powered by Karix`.
3. Click **Send Test**.

If the configuration is correct, the test message will be delivered, and Karix will return a DLR update. If there is an error (for example, incorrect credentials or endpoint), CleverTap will display a failure notification.

# Set Up SMS Callbacks

To track SMS requests, perform the following steps:

1. Copy the _Delivery Report Callback URL_ from CleverTap and add it to the JSON payload. You can find this URL on the CleverTap dashboard under the Provider Setup page _Settings > Channels > SMS > Provider Nickname_.
2. Add it to the JSON payload field `"tag4": "$$MessageID"` or as the callback field in your Karix account.
3. Save the configuration to enable CleverTap to receive DLR updates from Karix.

<Callout icon="📘" theme="info">
  #### **Note**

  In the DLR handover, ensure to use the same tag values that are used in the send API payload. The `tag1` value maps to `$$CampaignID` and `tag4` maps to `$$MessageID`.
</Callout>

# Verify Successful Integration

Your integration is successful when the following criteria are met:

* The test SMS is successfully delivered to the target mobile number.
* No authentication or endpoint errors appear in CleverTap logs.
* Message delivery can be verified from your Karix dashboard.

Once verified, you can build and publish [SMS campaigns](https://docs.clevertap.com/docs/sms) or set up [Journeys](https://docs.clevertap.com/docs/journeys) using Karix as your SMS provider.
