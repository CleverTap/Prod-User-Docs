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

Using the following custom callback functions, you can control the look, feel, and location of your web exit intent. \<\<@vishal somani, is this applicable to exit intent ??>>

You need to explicitly call `clevertap.raiseNotificationViewed();` and `clevertap.raiseNotificationClicked();` to ensure that notification views and clicks are tracked on CleverTap.

To define the callback and raise the clicked and viewed events, you need to add the following snippet to the JavaScript embed code comprising your CleverTap web integration:

```javascript
clevertap.notificationCallback = function(msg){
      // Raise the notification viewed and clicked events in the callback
      clevertap.raiseNotificationViewed();
      console.log(JSON.stringify(msg));// Your custom rendering implementation here
      var $button = jQuery("<button></button>");// Element on whose click you want to raise the notification clicked event
      $button.click(function(){
         clevertap.raiseNotificationClicked();
      });
};
```

The message will be in the following format:

```json
{
    "msgContent": {
        "title": "hello title!",
        "description": “hello message!"
    },
    "msgId": "1439796272_20160219",
    "kv": {
        "key1":"value1",
        "key2":"value2"
    }
}
```

`msgId` contains the campaign ID and the date-stamp so that you can programmatically decide whether to display the notification. `kv` contains the custom key value pairs.
