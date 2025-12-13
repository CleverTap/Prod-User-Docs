---
title: Post Action Webhooks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[block:api-header]
{
  "title": "Overview"
}
[/block]
A *post action* webhook is used to trigger a payload to your specified endpoint after sending a push notification.

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Contact our sales team at sales@clevertap.com to enable post action webhooks for your organization"
}
[/block]
# Use Case

You may want exact copies of all messages sent to each user and the message statuses as input to your recommendation engine. This can be solved by using a *post action* webhook.

You can enable the *post action* webhook during campaign creation under the *Setup* section.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99b654a-Post_Action_Webhooks_1.png",
        "Post Action Webhooks 1.png",
        1958,
        122,
        "#f5f6f7"
      ]
    }
  ]
}
[/block]
After the configuration is enabled, the webhook endpoint is listed in the *Setup* section. Select the required webhook endpoint from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7c57c31-Post_Action_Webhooks_2.png",
        "Post Action Webhooks 2.png",
        1982,
        334,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]

#  Send Data

You can stream all the message-level data from a push campaign on your server by using a *post action* webhook. 

Following is the sample payload structure for push data: 
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"targetId\": 1628144342,\n  \"profiles\": [\n    {\n      \"identity\": \"6425\",\n      \"all_identities\": [\n        \"jane.doe@domain.com\",\n        \"6425\"\n      ],\n      \"objectId\": \"-gdf3d1d914a65406a862bac176fb279f1\",\n      \"payload\": {\n        \"title\": \"Welcome to Acme!\",\n        \"body\": \"Click here to register for the next event.\",\n        \"kvs\": {\n          \"wzrk_cid\": \"ChannelID\",\n          \"wzrk_bi\": \"2\",\n          \"wzrk_bc\": \"\",\n          \"wzrk_ttl_s\": 86400,\n          \"wzrk_ttl\": 24,\n          \"wzrk_acct_id\": \"WZZ-ZZZ-ZZZZ\"\n        }\n      }\n    }\n  ]\n}",
      "language": "json"
    }
  ]
}
[/block]

Following are the key types in the payload:
[block:parameters]
{
  "data": {
    "h-0": "Key",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "wzrk_cid",
    "0-1": "String",
    "0-2": "Refers to Channel ID.",
    "7-2": "Open rate tracking ID (can be empty or it may not be present).",
    "7-1": "string",
    "8-1": "string",
    "7-0": "wzrk_id",
    "8-0": "wzrk_bp",
    "9-0": "wzrk_sound",
    "9-2": "If present, it signifies that the default or custom Android notification sound must be played.",
    "8-2": "If present, the value will be a URL of an image  displayed in the notification.",
    "9-1": "boolean or string",
    "10-0": "nt",
    "11-0": "nm",
    "12-0": "wzrk_dl",
    "13-0": "wzrk_d",
    "14-0": "ico",
    "15-0": "wzrk_pivot",
    "10-1": "string",
    "11-1": "string",
    "12-1": "string",
    "13-1": "N/A",
    "14-1": "string",
    "15-1": "string",
    "15-2": "If present and not empty, it contains the URL of an image. It signifies the type of variant in A/B campaigns.",
    "14-2": "If present and not empty, it contains the URL of an image, that must be used as the small notification icon.",
    "13-2": "If present, ignore this notification.",
    "12-2": "If present, this is a deep link that must be followed at the time of notification open.",
    "11-2": "Notification Body. If absent or empty, ignore this notification.",
    "10-2": "Notification Title. If absent or empty falls back to the app name.",
    "16-0": "wzrk_rnv",
    "16-1": "string",
    "16-2": "If present and not empty, it will raise Push Impressions event.",
    "17-0": "wzrk_nms",
    "18-0": "wzrk_st",
    "19-0": "wzrk_clr",
    "17-1": "string",
    "17-2": "If present and not empty, it contains the summary text to be displayed along with the image.",
    "18-1": "string",
    "18-2": "If present and not empty, it contains the subtitle text which is displayed next to the App name.",
    "19-1": "string",
    "19-2": "If present and not empty, it contains the *Hex* value of the color to be applied on the small icon (and app name for Android Pie and below)",
    "6-0": "wzrk_pn",
    "6-1": "N/A",
    "6-2": "If present, this notification is sent from CleverTap.",
    "1-0": "wzrk_bi",
    "1-2": "Keys Badge icon in push notifications.",
    "2-0": "wzrk_bc",
    "2-2": "Key refers to badge count.",
    "3-0": "wzrk_ttl_s",
    "4-0": "wzrk_ttl",
    "4-2": "Time to live of notification.",
    "5-0": "wzrk_acct_id",
    "5-2": "CleverTap account ID",
    "1-1": "String",
    "2-1": "String",
    "3-1": "Integer",
    "4-1": "Integer",
    "5-1": "String",
    "3-2": "Time to live in seconds."
  },
  "cols": 3,
  "rows": 20
}
[/block]
The post action webhook can collect data only after the successful delivery of push messages.