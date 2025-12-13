---
title: Troubleshooting
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
This section covers FAQs related to the app inbox. 

#FAQs
##Does the app inbox stay after the user has uninstalled the application?

The app inbox would not stay in the application after the user has uninstalled, as the messages are stored locally. Whenever the cache is cleared or if the app is uninstalled, the app inbox is deleted from the device and the application. CleverTap does not maintain a user’s App Inbox state at the backend.

##If a user opens the app after a very long time will all the pending App Inbox messages be fetched for the user?

The SDK will fetch the latest 10 messages only, if you have launched the application after a long time and have qualified for more than 10 app inbox messages, only 10 will be shown and the rest will be dropped.


##Are special characters supported in the filter tags for our app inbox campaigns? e.g. underscore, hyphen etc, chinese characters, vietnamese/ pinyin characters etc.

Yes, special unicode encoded characters are supported for the same.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47b359e-Special_characters.png",
        "Special characters.png",
        634,
        1000,
        "#b9a990"
      ]
    }
  ]
}
[/block]