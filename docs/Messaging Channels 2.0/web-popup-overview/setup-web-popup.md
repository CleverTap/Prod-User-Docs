---
title: Setup
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
# Define a Custom Callback

Using the following custom callback functions, you can control the look, feel, and location of your web pop-up.

You need to explicitly call `clevertap.raiseNotificationViewed();` and `clevertap.raiseNotificationClicked();` to ensure that notification views and clicks are tracked on CleverTap.

To define the callback and raise the clicked and viewed events, you need to add the following snippet to the JavaScript embed code comprising your CleverTap web integration:
[block:code]
{
  "codes": [
    {
      "code": "clevertap.notificationCallback = function(msg){\n      // Raise the notification viewed and clicked events in the callback\n      clevertap.raiseNotificationViewed();\n      console.log(JSON.stringify(msg));// Your custom rendering implementation here\n      var $button = jQuery(\"<button></button>\");// Element on whose click you want to raise the notification clicked event\n      $button.click(function(){\n         clevertap.raiseNotificationClicked();\n      });\n};",
      "language": "javascript"
    }
  ]
}
[/block]
The message will be in the following format:
[block:code]
{
  "codes": [
    {
      "code": "{\n    \"msgContent\": {\n        \"title\": \"hello title!\",\n        \"description\": “hello message!\"\n    },\n    \"msgId\": \"1439796272_20160219\",\n    \"kv\": {\n        \"key1\":\"value1\",\n        \"key2\":\"value2\"\n    }\n}",
      "language": "json"
    }
  ]
}
[/block]
`msgId` contains the campaign ID and the date-stamp so that you can programmatically decide whether to display the notification. `kv` contains the custom key value pairs.