---
title: Post Action Webhooks
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

A *post action* webhook is used to trigger a payload to your specified endpoint after sending a push notification.

> 📘 Note
>
> Contact our sales team at [sales@clevertap.com](mailto:sales@clevertap.com) to enable post action webhooks for your organization

# Use Case

You may want exact copies of all messages sent to each user and the message statuses as input to your recommendation engine. This can be solved by using a *post action* webhook.

You can enable the *post action* webhook during campaign creation under the *Setup* section.

![1958](https://files.readme.io/99b654a-Post_Action_Webhooks_1.png "Post Action Webhooks 1.png")

After the configuration is enabled, the webhook endpoint is listed in the *Setup* section. Select the required webhook endpoint from the list.

![1982](https://files.readme.io/7c57c31-Post_Action_Webhooks_2.png "Post Action Webhooks 2.png")

# Send Data

You can stream all the message-level data from a push campaign on your server by using a *post action* webhook. 

Following is the sample payload structure for push data: 

```json
{
  "targetId": 1628144342,
  "profiles": [
    {
      "identity": "6425",
      "all_identities": [
        "jane.doe@domain.com",
        "6425"
      ],
      "objectId": "-gdf3d1d914a65406a862bac176fb279f1",
      "payload": {
        "title": "Welcome to Acme!",
        "body": "Click here to register for the next event.",
        "kvs": {
          "wzrk_cid": "ChannelID",
          "wzrk_bi": "2",
          "wzrk_bc": "",
          "wzrk_ttl_s": 86400,
          "wzrk_ttl": 24,
          "wzrk_acct_id": "WZZ-ZZZ-ZZZZ"
        }
      }
    }
  ]
}
```

Following are the key types in the payload:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        wzrk\_cid
      </td>

      <td>
        String
      </td>

      <td>
        Refers to Channel ID.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_bi
      </td>

      <td>
        String
      </td>

      <td>
        Keys Badge icon in push notifications.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_bc
      </td>

      <td>
        String
      </td>

      <td>
        Key refers to badge count.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_ttl\_s
      </td>

      <td>
        Integer
      </td>

      <td>
        Time to live in seconds.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_ttl
      </td>

      <td>
        Integer
      </td>

      <td>
        Time to live of notification.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_acct\_id
      </td>

      <td>
        String
      </td>

      <td>
        CleverTap account ID
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_pn
      </td>

      <td>
        N/A
      </td>

      <td>
        If present, this notification is sent from CleverTap.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_id
      </td>

      <td>
        string
      </td>

      <td>
        Open rate tracking ID (can be empty or it may not be present).
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_bp
      </td>

      <td>
        string
      </td>

      <td>
        If present, the value will be a URL of an image  displayed in the notification.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_sound
      </td>

      <td>
        boolean or string
      </td>

      <td>
        If present, it signifies that the default or custom Android notification sound must be played.
      </td>
    </tr>

    <tr>
      <td>
        nt
      </td>

      <td>
        string
      </td>

      <td>
        Notification Title. If absent or empty falls back to the app name.
      </td>
    </tr>

    <tr>
      <td>
        nm
      </td>

      <td>
        string
      </td>

      <td>
        Notification Body. If absent or empty, ignore this notification.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_dl
      </td>

      <td>
        string
      </td>

      <td>
        If present, this is a deep link that must be followed at the time of notification open.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_d
      </td>

      <td>
        N/A
      </td>

      <td>
        If present, ignore this notification.
      </td>
    </tr>

    <tr>
      <td>
        ico
      </td>

      <td>
        string
      </td>

      <td>
        If present and not empty, it contains the URL of an image, that must be used as the small notification icon.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_pivot
      </td>

      <td>
        string
      </td>

      <td>
        If present and not empty, it contains the URL of an image. It signifies the type of variant in A/B campaigns.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_rnv
      </td>

      <td>
        string
      </td>

      <td>
        If present and not empty, it will raise Push Impressions event.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_nms
      </td>

      <td>
        string
      </td>

      <td>
        If present and not empty, it contains the summary text to be displayed along with the image.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_st
      </td>

      <td>
        string
      </td>

      <td>
        If present and not empty, it contains the subtitle text which is displayed next to the App name.
      </td>
    </tr>

    <tr>
      <td>
        wzrk\_clr
      </td>

      <td>
        string
      </td>

      <td>
        If present and not empty, it contains the *Hex* value of the color to be applied on the small icon (and app name for Android Pie and below)
      </td>
    </tr>
  </tbody>
</Table>

The post action webhook can collect data only after the successful delivery of push messages.
