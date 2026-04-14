---
title: Message Central
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Message Central](https://www.messagecentral.com/) is a global messaging platform that enables brands to send transactional and promotional SMS messages worldwide. Integrating Message Central with CleverTap allows you to deliver messages directly from CleverTap’s engagement dashboard while leveraging Message Central’s connectivity.

This integration supports HTTP-based message delivery, secure header authentication, and event-based campaign triggers to deliver high-quality engagement experiences.

Businesses use Message Central with CleverTap to:

* **Send Transactional Messages**: Send OTPs, alerts, and notifications in real time.
* **Run Promotional Campaigns**: Deliver personalized offers and marketing messages to targeted audience segments.
* **Automate User Engagement**: Reconnect with inactive users through reminders and feedback messages.

Integrating Message Central with CleverTap combines CleverTap’s intelligent user segmentation and automation capabilities with Message Central’s scalable messaging infrastructure.

# Prerequisites for Integration

Before integrating, ensure the following:

* You have an active CleverTap account with SMS channels enabled.
* You have a Message Central account with SMS permissions.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and continuously improved by Message Central. For any questions or issues, contact [Message Central](mailto:support@messagecentral.com) for support and resolution.
</Callout>

# Integrate Message Central with CleverTap

To integrate Message Central with CleverTap, perform the following steps:

1. [Find Message Central Account Details](doc:message-central#find-message-central-account-details)
2. [Set Up CleverTap Dashboard](doc:message-central#set-up-clevertap-dashboard)
3. [Send Test SMS](doc:message-central#send-test-sms)

## Find Message Central Account Details

To retrieve your Message Central credentials, perform the following steps:

1. Log in to your Message Central Dashboard.
2. Note the following details from your account home page:

   * _Customer ID_: Available on the Message Central home page.
   * _Email_: The registered email used to create your account.
   * _Password_: The password you use to log in.

You will need these credentials when configuring CleverTap.

<Image align="center" alt="Message Central Dashboard" border={true} caption="Message Central Dashboard" src="https://files.readme.io/aece4b6ec5d88ca9876d4bc0526b8a6bdd0755275b2ba07476f695f49fd700da-Message_Central_Dashboard_.png" />

## Set Up CleverTap Dashboard

Once you have your Message Central credentials, set up the CleverTap dashboard to connect and authenticate your SMS provider.

1. Go to _Settings_ > _Engage_ > _Channels_ > _SMS_ in the CleverTap dashboard.
2. Click **+ Add Provider**. The Add SMS provider page opens.

<Image align="center" alt="Add Provider" border={true} caption="Add Provider" src="https://files.readme.io/8ca98feff96deb7a4d4b6c4a0576f0b108f3d696f98dfbaa9b61faca58641cf2-image.png" width="65%" />

3. Under **Provider**, select _Other (Generic)_ and enter the following details:

<Table>
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
        Enter a name such as `MessageCentral_SMS`.
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
        Paste the **Auth URL** from the Message Central account.  
        Ensure that the URL is in HTTPS format; that is, your URL must begin with `https://`.
      </td>
    </tr>
  </tbody>
</Table>

4. Under **Headers**, click **Add Pairs** to add the following required key-value pairs:

| Key            | Value                                                   |
| -------------- | ------------------------------------------------------- |
| `customerId`   | Your Customer ID (from the Message Central dashboard)   |
| `email`        | Your Email (used for Message Central login)             |
| `password`     | Your Password (used for Message Central login)          |
| `Content-Type` | `application/json`                                      |
| `account`      | Your CleverTap Account ID (for example, `6K9-***-**7Z`) |

<Image align="center" border={true} caption="Set Headers" src="https://files.readme.io/98456be92d573373bbfff932c01493e684e45ca9a0194d79fcee04f6459a40dd-image.png" width="35% " />

5. Under **Parameters**, select _JSON_ as the request type and paste the following code:

```json
{
  "to": "$$To",
  "text": "$$Body"
}
```

<Image align="center" alt="Add Parameters" border={true} caption="Add Parameters" src="https://files.readme.io/366474aabeccfec58222a5f9c2424f595a604535cfbfdd7368583c5ae8c4e162-image.png" width="55% " />

6. (Optional) Select the _Batch_ option, then enter the required details to send multiple SMS messages in a single API request.

<Callout icon="📘" theme="info">
  #### Single Batch Limit

  A single batch can have a maximum of 1,000 records.
</Callout>

7. Click **Save**. A pop-up box will appear, prompting you to [Send Test SMS](doc:message-central#send-test-sms).

<Callout icon="⚠️" theme="warn">
  #### Error

  If you see the message “_Dynamic Variable cannot be added or deleted_”, wait a few minutes and click **Save** again.
</Callout>

## Send Test SMS

Sending a test SMS helps ensure that your integration is set up correctly before launching campaigns.

To verify that the integration works, perform the following steps:

1. Click the **Send Test SMS** hyperlink before creating SMS campaigns and journeys.
2. Enter the following details:
   * _Country Code and Mobile Number_: Enter the country code and mobile number to which you want to send the message.
   * _Message_: Enter sample text, such as `Welcome to Message Central. We are delighted to have you here! - Powered by U2opia`

<Image align="center" alt="Send Test SMS" border={true} caption="Send Test SMS" src="https://files.readme.io/4087a1ba2b36b0d9c2276762e692f42afd1bdc22ceed2bd7cbcd6105e54b796c-image.png" width="65% " />

<Callout icon="📘" theme="info">
  #### Note

  Message Central’s current CleverTap integration does not support DLR (Delivery Report) callbacks. You should reach out to Message Central team for setting up CleverTap callback.
</Callout>

If the test SMS is delivered successfully, your integration is complete. You can now create and publish [SMS campaigns](doc:create-message-sms) or build [Journeys](doc:journeys) in CleverTap using Message Central as your SMS provider.
