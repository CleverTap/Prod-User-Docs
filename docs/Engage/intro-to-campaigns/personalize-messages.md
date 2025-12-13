---
title: Personalize Messages
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
# Overview

When you create campaigns in CleverTap, you can personalize messages for each user based on user profile properties.

For example, let's say you run a multilingual news application and you have users that speak many different languages, you can personalize each message based on the user's preferred language. 

Using this feature, instead of making one campaign for each language and splitting your campaign stats, you can create one campaign and see its result as a whole, and for each language individually.

# Step 1: Pick the User Property to Personalize Messages
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d576bcd-Campaign_Message_Types.png",
        "Campaign_Message_Types.png",
        1424,
        743,
        "#eceef3"
      ],
      "border": true
    }
  ]
}
[/block]
# Step 2: Create Default Message Copy

In this campaign, you have to specify a default copy, which will go to all users in your target segment that doesn’t have a user property you have selected a copy for. 

**Example**
If you are sending a message based on language and your app supports 50 languages, you may choose to create copy for Spanish and French, and keep your default copy as English, which will be sent to everyone else.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ade0ab-Campaigns_Message_Property_English.png",
        "Campaigns_Message_Property_English.png",
        1356,
        643,
        "#f3f5f7"
      ],
      "border": true
    }
  ]
}
[/block]
# Step 3: Choose and Create Your Message Copy Based on User Properties

After you have selected your default copy, you need to select the various user properties for which you’d like to create copies. Please note no message copy can be left blank.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70ff3a3-Campaign_Message_Property_Spanish.png",
        "Campaign_Message_Property_Spanish.png",
        1366,
        643,
        "#f4f4f7"
      ],
      "border": true
    }
  ]
}
[/block]