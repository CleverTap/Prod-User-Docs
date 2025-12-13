---
title: Native Display_Campaign redesign
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
Native Display provides the ability to embed content natively within your app screen without interrupting the app experience. It also provides the ability to change the content of your app dynamically and deliver relevant and contextual content to your users. 
[block:callout]
{
  "type": "success",
  "body": "You can create a native display campaign to display recommended content to users on a carousel as soon as they launch the app.",
  "title": "Native Display Example"
}
[/block]

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
The native display campaign gives you the ability to modify sections of your app or show banner advertisements on live triggers and segmentation. This capability is available for iOS (SDK version 3.7 and above) and Android (SDK version 3.6.2 and above). 

Follow the steps for the integration of native display with your app for [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) and [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios).

#Create a Native Display Campaign
Perform the following steps to create a native display campaign:

1. Click **Native Display** under *Campaigns* on the CleverTap dashboard.
2. Click **+ Campaign**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cbc1c6c-7809a74-Screenshot_2020-06-09_at_4.47.07_PM.png",
        "7809a74-Screenshot_2020-06-09_at_4.47.07_PM.png",
        2752,
        1322,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
3. Select ** Native Display** from the *Messaging Channels* list.
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
## Set up the campaign. 

Set a goal with conversion tracking. 
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
## Define the Who
1. Select the target segment. 
2. Configure the Limits and Control group
3. Set the [Constant Event Property](doc:constant-property) .

## Define the What

 Define the message for the campaign.
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
1. Select one of the following message types:
  * Single message
  * [A/B and multivariate test](https://docs.clevertap.com/docs/ab-multivariate-testing) 
  * Message on user property

2. Select any or all of the following device types:
  * iOS
  * Android
  * Mobile
  * Tablet
  * TV (Android)

3. Select the template for the campaign. Check that you have completed the integration steps for [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) and [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios) before you set up a campaign. 
[block:parameters]
{
  "data": {
    "h-0": "Template",
    "h-1": "Template Category",
    "h-2": "Banner size",
    "0-0": "Single banner",
    "0-1": "Media (images, gif, video) only",
    "0-2": "320*50",
    "1-1": "Media (images, gif, video) + Text",
    "1-2": "320*100",
    "2-0": "Carousel banners",
    "2-1": "Media (images, gif) only",
    "3-1": "Media (images, gif) + Text",
    "3-2": "",
    "2-2": "320*250",
    "4-0": "Banner with icon",
    "4-1": "Media (images, gif, video) only",
    "5-1": "Media (images, gif, video) + Text",
    "6-0": "Custom key value",
    "6-1": "Any",
    "6-2": "Not Applicable"
  },
  "cols": 2,
  "rows": 7
}
[/block]
4. Personalize your content by typing the @ symbol in the *Title* box and other text boxes to list all the available *Profile* and *Event* variables. 
5. Select a variable and provide the default value. For more information, refer to [Personalize Messages](doc:personalize-messages).
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
  "body": "The maximum sizes are as follows:\n* Image: 500 KB\n* Audio file: 5 MB\n* Video file: 50 MB\n\nThe supported file formats include .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color).",
  "title": "Maximum Image Sizes"
}
[/block]
6. Enter the custom key-value pairs. You can enter a value or type the @ symbol in the *Value* box to list specific *Profile* and *Event* properties. The key can have any value. 

For example, if you want to change the carousel images for your users based on their language and favorite food, you can set the custom key-value pairs for this change.
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

## Define the When

Currently, the frequency of the campaign is not managed by CleverTap. We send the configured content when the event is triggered. 

<<@vishal is this still true ?>>

[block:callout]
{
  "type": "info",
  "title": "Recurring Day",
  "body": "If you specify a recurring day for a campaign, such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]

Select any live segment or create an ad-hoc live segment. You can filter by any event property for the selected event. You can also filter on any past behavior or user property.
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

## Publish Campaign

1. Review your campaign and check if everything is in order. 
2. Click the **Publish Campaign** button to schedule and send out your campaign.  
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

Open the native display campaign from the campaign list page. The *Notification Clicked* and *Notification Viewed* events are tracked after you send the events and after the integration is complete.
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