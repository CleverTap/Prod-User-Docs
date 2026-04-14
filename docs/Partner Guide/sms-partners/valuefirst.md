---
title: ValueFirst
excerpt: 'SMS Provider '
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[ValueFirst](https://www.vfirst.com/) is a global enterprise communication platform enabling brands to deliver SMS notifications, alerts, and promotions worldwide. Integrating ValueFirst with CleverTap allows you to send transactional and promotional SMS messages directly from CleverTap’s engagement dashboard.

This integration enables real-time message delivery, delivery status tracking via callbacks, and event-based campaign triggering.

Businesses integrate ValueFirst with CleverTap to:

* **Send Transactional Messages**: Send OTPs, verification codes, or order updates.
* **Run Promotional Campaigns**: Deliver targeted SMS offers to user segments based on behavioral triggers.
* **Automate Customer Engagement**: Send reminders, feedback requests, or re-engagement messages.

Integrating ValueFirst with CleverTap combines scalable message delivery with advanced segmentation and journey orchestration.

# Prerequisites for Integration

Before integrating, check the following:

* You have an active CleverTap account with the SMS add-on enabled.
* You have a ValueFirst XML account for the SMS channel API.

  * If you don’t have one, email [partnerships@vfirst.com](mailto:partnerships@vfirst.com) to request credentials. You’ll receive your **Username**, **Password**, and **Sender ID**.
* Check that the CleverTap IP `43.205.172.215` is whitelisted on the ValueFirst side.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and continuously improved by ValueFirst. The CleverTap and ValueFirst integration has undergone stringent testing to ensure seamless functionality. For any questions or issues, contact [ValueFirst](mailto:partnerships@vfirst.com) for support and resolution.
</Callout>

# Integrate ValueFirst with CleverTap

To integrate ValueFirst with CleverTap, complete the following steps:

1. [Configure ValueFirst](doc:valuefirst-sms#configure-valuefirst)
2. [Set Up CleverTap Dashboard](doc:valuefirst-sms#set-up-clevertap-dashboard)
3. [Send a Test SMS](doc:valuefirst-sms#send-test-sms)

## Configure ValueFirst

Before configuring CleverTap, authenticate your SMS account in the ValueFirst portal.

To configure ValueFirst, perform the following steps:

1. Sign Up for the [ValueFirst – CleverTap Integration](https://ct.vfplugin.com/signup) by entering the required details and clicking **Sign Up**.

<Image align="center" alt="ValueFrist Sign Up" border={true} caption="ValueFrist Sign Up" src="https://files.readme.io/79b0fff38568248e70411b16566e7afd4ca5b4a5c2ac8d7af1647a801318f964-image.png" width="65% " />

2. After signing up, log in to the ValueFirst portal using the credentials created in the above step.
3. Enter the following:
   * **Username** and **Password**
   * **Default Sender ID** (from your ValueFirst account)
4. Click **Authenticate**. The message _“Successfully authenticated ValueFirst account.”_ displays.

<Image align="center" alt="ValueFirst Authentication" border={true} caption="ValueFirst Authentication" src="https://files.readme.io/0a2749c4cd0e68a25a229af6eaf2056c2ae325a8e97e91f7fc60dd3e850ec03a-image.png" width="65% " />

## Set Up CleverTap Dashboard

Once the ValueFirst account is configured, set up the CleverTap dashboard to connect and authenticate the SMS provider as follows:

1. Go to _Settings_ > _Engage_ > _Channels_ > _SMS_ in the CleverTap dashboard.
2. Click **+ Add Provider**. The Add SMS provider page opens.

<Image align="center" alt="Add Provider" border={true} caption="Add Provider" src="https://files.readme.io/8ca98feff96deb7a4d4b6c4a0576f0b108f3d696f98dfbaa9b61faca58641cf2-image.png" width="65% " />

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
        Enter a name such as `ValueFirst_SMS`.
      </td>
    </tr>

    <tr>
      <td>
        **Delivery Report Callback URL**
      </td>

      <td>
        Enter this URL in the ValueFirst portal to receive delivery reports. Refer to [Set Up SMS Callbacks](doc:valuefirst-sms#set-up-sms-callbacks).
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
        Paste the **Auth URL** from the ValueFirst plugin.  
        Ensure that the URL is in HTTPS format, that is, your URL must begin with `https://`.
      </td>
    </tr>
  </tbody>
</Table>

4. Enter the following details for the key-value pairs under the _Headers_ section.

| Key             | Value                                                       |
| --------------- | ----------------------------------------------------------- |
| `Authorization` | Paste the **Basic Token Value** from the ValueFirst plugin. |
| `Content-Type`  | `application/json`                                          |

<Callout icon="📘" theme="info">
  #### Note

  The Authorization token is generated by the ValueFirst plugin and must be copied exactly as displayed. Incorrect keys will result in a `401 Unauthorized` response.
</Callout>

<Image align="center" alt="Set Headers" border={true} caption="Set Headers" title="Set Headers" src="https://files.readme.io/2d150958aebb2dd35c5b3971d8cca19650dd768e4b387c106c726777c9adfb2e-image.png" width="55% " />

5. Under _Parameters_, select `JSON` as the request type for the `POST` request. Refer to the following sample payload for the expected structure.

   **Sample JSON Payload**

```json
{
  "from": "<Your Sender ID>",
  "to": "$$To",
  "text": "$$Body",
  "client_ref": "$$MessageID",
  "callback": "<CleverTap Callback URL>"
}
```

| Parameter    | Description                                                                                                                             | Required |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `from`       | Sender ID registered in ValueFirst.                                                                                                     | Yes      |
| `to`         | Recipient’s mobile number. Use `$$To` for dynamic replacement.                                                                          | Yes      |
| `text`       | Message text content. Use `$$Body`.                                                                                                     | Yes      |
| `client_ref` | Unique message ID (CleverTap dynamically replaces this).                                                                                | Yes      |
| `callback`   | CleverTap Delivery Report Callback URL. For more information, refer to [Set Up SMS Callbacks](doc:valuefirst-sms#set-up-sms-callbacks). | Optional |

<Image align="center" alt="Set Parameters" border={true} caption="Set Parameters" src="https://files.readme.io/4eab04e531dbbf3dc25169984b38734ff42560ad76cfd4d1a4b415a5b40ba1d7-image.png" width="65% " />

6. (Optional) Select the _Batch_ checkbox, then enter the required details to send multiple SMS messages in a single API request.

<Callout icon="📘" theme="info">
  #### Single Batch Limit

  A single batch can have a maximum of 1,000 records.
</Callout>

7. Click **Save**. A pop-up opens, prompting you to [Send Test SMS](doc:valuefirst-sms#send-test-sms).

## Send Test SMS

Sending a test SMS helps confirm that your ValueFirst integration is working before launching a live campaign. This ensures that the API endpoint is correctly configured, that authentication is valid, and that messages can be delivered.

To verify that the integration works, perform the following steps:

1. Click the **Send Test SMS** hyperlink before creating SMS campaigns and journeys.
2. Enter the following details:
   * _Country Code and Mobile Number_: Enter the country code and mobile number to which you want to send the message.
   * _Message_: Enter sample text, such as `This is a test message powered by ValueFirst.`

<Image align="center" alt="Send a Test SMS" border={true} caption="Send a Test SMS" src="https://files.readme.io/b0035111caeabd1680481547f55884ada927490cccb80eae1ebbadbac2803ea4-image.png" width="65% " />

3. Click **Send Test**.

If the configuration is correct, the test message will be delivered, and ValueFirst will return a DLR update. If there is an error (for example, incorrect credentials or endpoint), CleverTap will display a failure notification.

# Set Up SMS Callbacks

To track SMS requests, copy the Delivery report callback URL from CleverTap and add it to the JSON payload

1. You can find the Delivery report callback URL on the CleverTap dashboard under the Provider  
   Setup page _Settings_ > _Channels_ > _SMS_ > _Provider Nickname_.
2. Add it to the JSON payload.

<Image align="center" alt="Set Up SMS Callbacks" border={true} caption="Set Up SMS Callbacks" src="https://files.readme.io/27be1e248b9101270026cf9be1bc09c56248d3f3b3c6cbbb4feef98e3bb6c85f-image.png" width="35% " />

# Verify Successful Integration

Your integration is considered successful when the following criteria are met:

* The test SMS is delivered to the intended mobile number.
* You receive a DLR (Delivery Report) callback from ValueFirst at the configured CleverTap callback URL, indicating delivery, failure, or queue status.
* CleverTap logs show no errors related to authentication, payload structure, or message transmission.

Once these conditions are met, you can proceed to build and publish [SMS campaigns](doc:create-message-sms) or set up [Journeys](doc:journeys) using ValueFirst as your SMS provider.
