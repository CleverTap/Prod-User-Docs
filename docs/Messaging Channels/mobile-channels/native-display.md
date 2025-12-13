---
title: Native Display
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
Apps can increase their interactions per app-visit and conversion rate simply by serving up relevant content. This decreases your bounce rate. You can use Native Display to send content that speaks to your user and add up to 5 points to the existing CTR. 

Native display helps you display content natively within your app without interrupting the app experience. You can dynamically change the content of your app and deliver relevant and contextual content to your users. This gives you the ability to delight your users by displaying the content that they will love. 

For example, you can create a Native Display campaign to display recommended content to users on a carousel as soon as they launch the app.


 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d4364e-Campaigns_Ad_view_Example_Image.png",
        "Campaigns_Ad_view_Example_Image.png",
        4012,
        3716,
        "#bcbebc"
      ]
    }
  ]
}
[/block]
#Getting Started
The native display campaign gives you the ability to modify sections of your app or show banner advertisements on live triggers and segmentation. This capability is available for iOS (SDK version 3.7 and above) and Android (SDK version 3.6.2 and above). 

Follow the steps for the integration of Native Display with your app for [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) and [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios).

#Creating a Native Display campaign
To start creating a campaign, click "Native Display" under “Campaigns” on the CleverTap dashboard.

##Step 1: Create a Campaign
Click the "+ Campaign" button.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7809a74-Screenshot_2020-06-09_at_4.47.07_PM.png",
        "Screenshot 2020-06-09 at 4.47.07 PM.png",
        2878,
        1340,
        "#f7f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
Click Native Display from the Channel page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c05e66b-Screenshot_2020-06-10_at_10.49.12_AM.png",
        "Screenshot 2020-06-10 at 10.49.12 AM.png",
        2768,
        1304,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
##Step 2: Define the delivery for the campaign: The When
Select the start and end of the campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/15511c4-Screenshot_2020-06-10_at_10.49.37_AM.png",
        "Screenshot 2020-06-10 at 10.49.37 AM.png",
        2492,
        1338,
        "#f8fafa"
      ],
      "border": true
    }
  ]
}
[/block]
Currently, the frequency of the campaign is not managed by Clevertap. We send the configured content when the event is triggered. 

##Step 3: Define the users for the campaign: The Who
Select any live segment or create an ad-hoc live segment. You can filter by any event property for the selected event. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bd017ba-Screenshot_2020-06-10_at_11.02.36_AM.png",
        "Screenshot 2020-06-10 at 11.02.36 AM.png",
        2792,
        994,
        "#fbfcfd"
      ],
      "border": true
    }
  ]
}
[/block]
You can also filter on any past behavior or user property

##Step 4: Define the message for the campaign: The What
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5f7c20-Screenshot_2020-06-10_at_10.52.56_AM.png",
        "Screenshot 2020-06-10 at 10.52.56 AM.png",
        2776,
        1314,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]
###1: Select the Message Type
You can select one of the following message types:
  * Single Message
  * [A/B and Multivariate Test](https://docs.clevertap.com/docs/ab-multivariate-testing) 
  * Message on user property`

### 2: Select the OS and Devices
Select the operating system for your campaign, that is, iOS and/or Android.
Select Mobile and/or Tablet.

###3: Select the Template
Select the template for the campaign. Check that you have completed the integration steps for [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios) and [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) before you set up a campaign. 

[block:parameters]
{
  "data": {
    "h-0": "Template",
    "h-1": "Template category",
    "h-2": "Banner size",
    "0-0": "Single banner",
    "0-1": "Media(images, gif, video) only",
    "0-2": "320*50",
    "1-1": "Media(images, gif, video) + Text",
    "1-2": "320*100",
    "2-0": "Carousel banners",
    "2-1": "Media(images, gif) only",
    "3-1": "Media(images, gif) + Text",
    "3-2": "",
    "2-2": "320*250",
    "4-0": "Banner with icon",
    "4-1": "Media(images, gif, video) only",
    "5-1": "Media(images, gif, video) + Text",
    "6-0": "Custom key value",
    "6-1": "Any",
    "6-2": "Not Applicable"
  },
  "cols": 2,
  "rows": 7
}
[/block]

### 4: Personalize your Content

Entering "@" in the Title box and other text boxes will list all the available Profile and Event variables. Select a variable and provide the default value. For more information, see [Personalize Messages](doc:personalize-messages).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3dcc0b0-Screenshot_2020-06-10_at_10.53.38_AM.png",
        "Screenshot 2020-06-10 at 10.53.38 AM.png",
        2784,
        1342,
        "#f4f5f7"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "Max image size - 500KB | Max audio file size - 5MB | Max video file size - 50MB\nSupported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color)"
}
[/block]
### 5: Add Custom Key Value pairs for your app

Enter the custom key value pairs. You can either enter a value or enter the "@" key in the Value box to list all Profile and Event properties. The key can have any value. 

For example, you want to change the carousel images for your users based on their language and favorite food. You can set the custom key value pairs for this change.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5ec4b2-Campaign_Ad_View_Custom_Key_Value.png",
        "Campaign_Ad_View_Custom_Key_Value.png",
        884,
        339,
        "#f8f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
##Step 6: Setup the Campaign
Set up the control group and labels. Set up conversion tracking for events. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9233f68-Screenshot_2020-06-10_at_10.54.19_AM.png",
        "Screenshot 2020-06-10 at 10.54.19 AM.png",
        2778,
        1204,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]

#Step 6: Schedule notification

Review your campaign and check if everything is in order. Click the Schedule Notification button to schedule and send out your campaign.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/48e9afc-Screenshot_2020-06-10_at_11.03.21_AM.png",
        "Screenshot 2020-06-10 at 11.03.21 AM.png",
        2778,
        1334,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]
#View Campaign Stats

Open the Native Display campaign from the campaign list page. The "Notification Clicked" and "Notification Viewed" events are tracked after you send the events and after the integration is complete.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c13c9e-Campaigns_Ad_view_report.png",
        "Campaigns_Ad_view_report.png",
        1239,
        1324,
        "#eaf2f9"
      ],
      "border": true
    }
  ]
}
[/block]