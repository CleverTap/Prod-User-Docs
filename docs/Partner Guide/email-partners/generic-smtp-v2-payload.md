---
title: Generic SMTP
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
# Overview

CleverTap supports integrating any Email Service Provider (ESP) using the SMTP protocol to send Email campaigns.

# Integrate Email Service Provider

To integrate the ESP with CleverTap, follow these steps:

1. Go to *Settings* > *Email* from the dashboard and click **+ Provider**.
2. Select *SMTP* from the *Provider* dropdown.
3. Enter the following details:

| Field                   | Description                                                                                                                                                                                                                                                                                                           |
| :---------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname                | A unique name to identify your SMTP configuration within the CleverTap dashboard.                                                                                                                                                                                                                                     |
| Callback URL            | The URL where CleverTap will receive the bounce, delivery, and subscription information from the ESP. This is a read-only field that is auto-populated with CleverTap's callback URL. For more information, refer to [SMTP Callbacks](doc:generic-smtp-v2-payload#smtp-callbacks).                                    |
| Host                    | Enter the publicly accessible IP address or hostname of your SMTP server.                                                                                                                                                                                                                                             |
| Port                    | Enter the SMTP port value.                                                                                                                                                                                                                                                                                            |
| Scheme                  | Select the security protocol for your SMTP connection (for example, SMTP/SMTPS).                                                                                                                                                                                                                                      |
| Username and Password   | Enter the Username and Password values that must be your SMTP credentials needed to connect to the service.                                                                                                                                                                                                           |
| Default From Name       | The sender's name will appear in the recipient's inbox, helping them identify the sender of the email.                                                                                                                                                                                                                |
| From Address            | Enter the sender's email address. Most people do not open an email unless they recognize the sender.                                                                                                                                                                                                                  |
| Reply Address           | The email address where replies from recipients are sent. Ensure this is monitored for effective communication.                                                                                                                                                                                                       |
| Email Preference Center | A landing page where users can [manage their email preferences](doc:manage-email-preferences), including opting out or selecting specific types of emails. You can also use CleverTap's system preference center. You can select from the following options: *None*, *CleverTap Preference Center*, and *Custom URL*. |

4. Click **Save** to save your settings.
5. Click **Send a test email**. You will receive an email in your inbox after the setup is complete. If you do not receive the email, refer to [Troubleshooting](doc:generic-smtp-v2-payload#troubleshooting).

# SMTP Callbacks

SMTP Callbacks provide insights into delivery success, failures, unsubscribes, and spam reports of your SMTP email provider. These insights help optimize strategies and improve email campaign performance through the following:

* *Notification Delivered Event*: The Notification Delivered event is raised when the campaign is delivered to the intended user. 
* *Notification Failed Event*: The *Notification Failed* event is raised to track delivery issues such as hard and soft bounces. The `error` parameter in this event specifies the reason for the failure, such as hard bounce, soft bounce, spam, or unsubscribed.
* *Profile Unsubscribes*: When users unsubscribe, mark emails as spam, or experience a hard bounce (excluding soft bounces), their profiles are automatically unsubscribed from future communications, triggering the Channel Unsubscribed event.

Callback requests must be made to CleverTap's *Callback URL*. The ESP must add this URL to their Email Provider Settings to pass these callback events to CleverTap. You can find the CleverTap *Callback URL* under the Provider *Setup* tab on the CleverTap dashboard.

<Image alt="Callback URL for Provider Setup" align="center" width="65%" border={true} src="https://files.readme.io/9fe779db4301b182af414e4d5208ea8d21a6b6659f3ad3b56f306da50a5bedd3-Callback_URL_on_CleverTap_dashboard.png" />

## Configure SMTP Callback

In the outgoing email SMTP payload, CleverTap sends the `X-CleverTap_META` key with a specific value. The provider must send the same value in the callback payload to CleverTap's callback URL within the `meta` key. When received along with the incoming callback payload, this helps attribute a callback to the correct profile and campaign.

## Send Callback Events

To send callback events to CleverTap, customers must send a POST request to CleverTap's *Callback URL*. The following is a sample callback payload:
The following table provides a brief description of the keys present in the callback payload:

```json
{
  "version": "v2",
  "events": {
		"success": [
      {
        "type": "delivered",	//Indicates the message was delivered to the intended recipient
        "email": "user5@example.com",	// Recipient email address
        "meta": "user5@example.com|1568798080|1730714617|20241104|0|wzrk_default|-17005907|"
      }
    ],
    "failed": [
      {
        "type": "unsubscribed", // Indicates the user has unsubscribed	
        "email": "user1@example.com",		// User email address
        "meta": "user1@example.com|1568798080|1730714617|20241104|0|wzrk_default|-17005907|",		
        "description": "Hard bounce detected"		// Additional details of the failure reason
      },
      {
        "type": "hard_bounce",
        "email": "user3@example.com",
        "meta": "user3@example.com|1568798080|1730799638|20241105|0|wzrk_default|-17005910|",
        "description": "Hard bounce detected"
      },
      {
        "type": "soft_bounce",
        "email": "user5@example.com",
        "meta": "usert5@example.com|1568798080|1730714617|20241104|0|wzrk_default|-17005905|",
        "description": "Recipient Inbox Full"
      },
      {
        "type": "spam",
        "email": "user4@example.com",
        "meta": "user4@example.com|1568798080|1730714617|20241104|0|wzrk_default|-17005904|",
        "description": "Marked as spam"
      }
    ]
  }
}
```

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>Key</th>
      <th>Description</th>
      <th>Required/Optional</th>
      <th>Values / Examples</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>version</td>
      <td>Denotes the payload version. This must be set to `v2` to track the delivery-related information such as success, failures, unsubscribes, and spam reports.</td>
      <td>Required</td>
      <td>`v2`</td>
    </tr>
    <tr>
      <td>event</td>
      <td>Denotes the event name.</td>
      <td>Required</td>
      <td>`failed`</td>
    </tr>
    <tr>
      <td>type</td>
      <td>Indicates the delivery status of the message. Possible values: `delivered` (denotes that the campaigns was delivered to the intended user), `hard_bounce` (denotes that an email delivery failed due to a permanent delivery issue, for example, an invalid email address), `soft_bounce` (denotes that an email delivery failed for temporary issues, for example, recipient inbox full, server errors, and so on), `spam` (denotes that the recipient marked the email as spam), `unsubscribed` (denotes that the recipient unsubscribed from emails).</td>
      <td>Required</td>
      <td>`hard_bounce`, `soft_bounce`, `spam`, `unsubscribed`</td>
    </tr>
    <tr>
      <td>email</td>
      <td>Denotes the email address of the recipient.</td>
      <td>Required</td>
      <td>`user1@example.com`</td>
    </tr>
    <tr>
      <td>meta</td>
      <td>CleverTap sends the key `X-CleverTap_META` in the SMTP payload with a specific value. The provider must return this value as is, in the callback payload under the `meta` key to properly attribute the callback to the correct profile and campaign.</td>
      <td>Required</td>
      <td>Replacement - `X-CleverTap_META`. For example, `user1@example.com\|1568798080\|1730714617\|20241104\|0\|wzrk_default\|-17005904\|`</td>
    </tr>
    <tr>
      <td>description</td>
      <td>An optional field to add more descriptive information regarding the callback event for analysis (for example, `User unsubscribed from campaign`). This is reflected in the `reason` event property of the *Channel Unsubscribed* event, offering additional details for error analysis.</td>
      <td>Optional</td>
      <td>`Soft bounce detected` - Denotes that the email to the intended user resulted in a soft bounce.</td>
    </tr>
  </tbody>
</Table>

> 📘 Note
>
> If the payload includes additional key-value pairs apart from the ones that are defined in the acceptable sample payload for each event, CleverTap does not throw any errors, but simply disregards those.

## Incoming Payload Mapping to System Events

CleverTap maps the following incoming payloads with their respective system events:

* *Notification Delivered*: This event is raised when the message is delivered to the intended user. The event property *Provider* specifies the email provider used to send the campaign, for example, `Generic email` indicates that the campaign was sent using a generic email provider configuration.

<Image alt="Payload Mapping for Notification Delivered Event" align="center" border={true} src="https://files.readme.io/880f068ac1c7354fbac73283f8dc5236108e6bd989f4111d234876bcaee028fd-Payload_Mapping_for_Notfication_Delivered.png" />

* *Notification Failed*: This event is raised if the callback event field`type` has values such as `hard_bounce` or `soft_bounce`. The event property `Error` of the *Notification Failed* event specifies the type of failure, that is, hard bounce or soft bounce.

<Image alt="Payload Mapping for Notification Failed Event " align="center" width="75% " border={true} src="https://files.readme.io/da2171626588fcede1fcc150339bcb29a6eaac74f52729a10d1e993fcb9d8464-Notification_Failed_Mapping_.png" />

* *Channel Unsubscribed*: This event is raised if the callback event field `type` has values such as `unsubscribed`, `spam`, or `hard_bounce`. The event property *Type* of the *Channel Unsubscribed* event specifies the reason for profile unsubscription.

<Image alt="Payload Mapping for Channel Unsubscribed Event" align="center" width="75% " border={true} src="https://files.readme.io/d3d70042a225770275afe3806cfedbe621416da884630cc3e5e8598e12eee078-Channel_Unsubscribed_Mapping.png" />

## Response Codes

CleverTap sends the following status codes and descriptions as a response to the ESP upon receiving callbacks:

| Status Code | Description                        | Explanation                                                                                               |
| :---------- | :--------------------------------- | :-------------------------------------------------------------------------------------------------------- |
| 200         | -                                  | Success                                                                                                   |
| 400         | Mandatory parameter missing        | This occurs when any mandatory keys are missing from the payload or when the payload format is incorrect. |
|             | More than allowed events were sent | This occurs if more than 1000 events are sent in a single API call.                                       |
|             | invalid payload                    | This occurs when the payload is not as per defined payload structure.                                     |
| 500         | Server error                       | CleverTap internal server error. Contact CleverTap support if the issue persists.                         |

### Sample Response

The following is the sample response sent by CleverTap to the provider upon processing the callback payload successfully:

```json
    "TOTAL_EVENTS": 4,
    "PROCESSED_EVENTS": 4,
    "UNPROCESSED_EVENTS": []
```

The following is the sample response sent by CleverTap to the providers upon partial processing of callback events:

```json
{
    "error": "2 event(s) failed to process",
    "TOTAL_EVENTS": 4,
    "PROCESSED_EVENTS": 2,
    "UNPROCESSED_EVENTS": [
        {
            "type": "hard_bounce",
            "email": "user1@clevertap.com",
            "description": "User hard bounce",
            "errorDescription": "invalid meta"
        },
        {
            "email": "user2@clevertap.com",
            "meta": "user2@clevertap.com|1568798080|1733728287|20241209|0|wzrk_default|-17006141|",
            "description": "User soft bounce",
            "errorDescription": "Could not map event to any bounce type"
        }
    ]
}
```

The following is the sample error response:

```json
{
   "error": "invalid payload",
    "TOTAL_EVENTS": 0,
    "PROCESSED_EVENTS": 0,
    "UNPROCESSED_EVENTS": []
}
```

# Troubleshooting

* As you are using your SMTP gateway, some email providers, such as Gmail and Yahoo, might not deliver the email to your inbox.
* Check if you have set up DKIM and SPF correctly.
* Check if Spamhaus has blacklisted your IP/domain.

> 🚧 Unsubscription Link
>
> The Unsubscribe link does not work test emails sent when creating an email campaign.

# Errors

The following table lists the errors that you may encounter after sending a campaign:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>Error Message</th>
      <th>Cause</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>SMTP invalid email ID</td>
      <td>**Cause 1**: The SMTP invalid email ID error occurs when the provided email address is not formatted correctly or does not exist. Typos or errors in the email address commonly cause this error.</td>
      <td>Double-check the email address and ensure the email ID is valid to fix this error.</td>
    </tr>
    <tr>
      <td></td>
      <td>**Cause 2**: This error can also occur if you are using a test email address.</td>
      <td>CleverTap recommends using an actual email address. If the issue persists, contact your ESP's customer support for further assistance.</td>
    </tr>
    <tr>
      <td>SMTP dispatching failed</td>
      <td>The email address you are trying to send to is incorrect. The email address's domain is invalid. The recipient's ESP blocks your IP address. The ESP is experiencing a temporary outage.</td>
      <td>To fix this error, check the recipient's email address and ensure that it is valid and that the email infrastructure is working correctly. If the issue persists, contact your provider's customer support.</td>
    </tr>
    <tr>
      <td>SMTP connection error</td>
      <td>Incorrect server details such as the server's hostname, port, or credentials. You can check the server details you have entered to confirm they are correct. There is a network issue that prevents the application from connecting to the SMTP server. It could be a temporary issue on your ESP's end.</td>
      <td>If the issue persists, contact your ESP's customer support for further assistance.</td>
    </tr>
    <tr>
      <td>SMTP timeout</td>
      <td>The email-sending process has taken longer than the allocated time frame for connection establishment or completion. The SMTP server of your ESP is experiencing high traffic. Your sending IP has been flagged as a source of spam. There is an issue with your ESP's infrastructure.</td>
      <td>If the issue persists, contact your ESP's customer support for further assistance.</td>
    </tr>
  </tbody>
</Table>