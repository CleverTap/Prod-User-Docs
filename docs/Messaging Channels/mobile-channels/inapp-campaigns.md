---
title: In-App Messages
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
As of October 29, 2018, we have released a new and improved in-apps with crisper message rendering capability which provides the capability to send in-app messages with images, GIFs, video, and audio. You can also do A/B testing on your in-apps.

[block:callout]
{
  "type": "warning",
  "title": "SDK Version",
  "body": "To use the template-based in-app campaigns, update your app with the CleverTap SDK version 3.3.0 or above.\n\nA/B test does not need an SDK update. You can still send an A/B test on any SDK (including version below 3.3.0) version as long as all the variants are HTML templates."
}
[/block]

#Create In-App Messages

The following section shows how to create various types of in-app messages.

##Create a Campaign

1. Navigate to *Messages* > *Campaigns*.
2. Click on **+ Campaign**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42b642b-Create_an_App_Inbox_Message_-_new_1.png",
        "Create an App Inbox Message - new 1.png",
        1334,
        623,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
3. Select *Mobile In-app* from the channel selection page.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e12bbd-Mobile_in-app_selection.png",
        "Mobile in-app selection.png",
        1126,
        834,
        "#f7f8fa"
      ]
    }
  ]
}
[/block]
4. Select the start date and time of the campaign as well as the end date and time. 
5. Click **Continue**.
[block:callout]
{
  "type": "info",
  "title": "Recurring Day",
  "body": "If you specify a recurring day for a campaign such as the 7th of each month, the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]

6. You must indicate the target audience for your mobile in-app campaign. You can target your in-app campaign to a new user segment by clicking on **+ Create an ad-hoc segment** or use a previously saved user segment from the *Saved Segments* list.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f32a5a2-Mobile_in-app_ad-hoc_segment.png",
        "Mobile in-app ad-hoc segment.png",
        1610,
        265,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]
Once done, follow the steps from one of the sections below:

##HTML In-Apps 
This section shows the steps for HTML in-app campaigns.

 1. Select one of the following message types: 
* Single message
* A/B test
* Message on user property
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d976c0-In-app_Messages.png",
        "In-app Messages.png",
        1230,
        663,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
2. Select any or all of the following device types:

  * iOS
  * Android
  * Mobile 
  * Tablet
  * TV (Android) 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9769e08-In-app_Messages.png",
        "In-app Messages.png",
        1230,
        663,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
3. Select the *Custom HTML* template. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/33ebd64-In-app_Messages_-_Custom_HTML.png",
        "In-app Messages - Custom HTML.png",
        837,
        459,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "SDK Version and Typeform",
  "body": "Other templates are only supported on SDK versions 3.3.0 and above.\n\nWe do not currently support Typeform because its rendering requires access to local storage which is a security risk. CleverTap SDK WebView does not allow access to local storage."
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Source Event Property",
  "body": "The CleverTap source event property is not supported for web pop-up and mobile in-app campaigns."
}
[/block]
4. Choose the builder option to create HTML in-apps via a drag-drop method. As an alternative, you can also choose to use the *Custom HTML* option to build your own campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/23cf7b8-In-app_Messages_-_Builder.png",
        "In-app Messages - Builder.png",
        1369,
        665,
        "#ebeef1"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Create Interactive In-Apps",
  "body": "You can create interactive in-app campaigns such as scratch card campaigns and swipe interaction campaigns using JavaScript.\n\nUsing the *Custom HTML* option, you can use Javascript in the HTML and create deep interactive in-app campaigns by adding the JavaScript code along with the HTML code. \n\n*Note*: JavaScript-based campaigns are available on version 3.5.0 and above."
}
[/block]
## Native In-Apps

This section shows the steps for native in-app campaigns.

1. Select one of the following message types:
  * Single message
  * A/B test
  * Message on user property

2. Select any or all of the following device types:
  * iOS
  * Android
  * Mobile 
  * Tablet
  * TV (Android) 

3. Pick any template.

Since your entire user base is on SDK version 3.3.0 and above, you can select any of the templates or *Custom HTML* template.

You must choose the canvas size and type before you start creating the message. The campaign canvas provided by default are the following:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2c48b1-In-app_Messages_-_Any_template.png",
        "In-app Messages - Any template.png",
        1226,
        661,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]
4. Build the in-app message by entering all the necessary information.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1741219-In-app_Messages_-_Build_a_message.png",
        "In-app Messages - Build a message.png",
        1379,
        654,
        "#f5f5f5"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Character Limit",
  "body": "The character limit for a message in English is 30 for the title and 128 for the message. \nThe character limit for a message in Chinese is 9 for the title and 38 for the message."
}
[/block]
4a. Select *Personalize media* to personalize in-app messages. 

This option helps to create recommendations in-apps and to upload personalized images for each of your users.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4931315-Screenshot_2019-07-03_at_11.04.11_PM.png",
        "Screenshot 2019-07-03 at 11.04.11 PM.png",
        643,
        532,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
4b. Select *On click action*.

Mobile in-app enables various types of call-to-action (CTA) to cater to different use cases for clients, such as the following: 

  * Close notification: It closes the notification after a tap. 
  * Open URL: A special type of CTA that enables the user to open a deeplink for Android or iOS.
  * Custom key-value pairs: The key-value pairs send back custom data when a user clicks the in-app button. This data is not visible to the user. This feature is available for apps that use Clevertap Android SDK version 3.6.1 or above and iOS SDK version 3.7.1 or above.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b5a2a2-Campaign_Inapp_CTA.png",
        "Campaign_Inapp_CTA.png",
        663,
        106,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]
5. Pick the media for each orientation while noting:

  * Using the background option in in-app, you can choose the media that you want your end-users to see when the app is in portrait mode and in landscape mode.
  * You can choose to add the same image with different form factors or completely different images to give a unique experience on portrait and landscape. 

## Users on New and Old SDK Versions
[block:callout]
{
  "type": "warning",
  "title": "Users on Both Old and New App Versions",
  "body": "The information provided below is for customers whose entire audience has not updated their app to support the native in-app capability.\n\nPost releasing the app update, there will be users who will be on both old and new app versions. In this case, to send a campaign to both your user base, follow the steps below.\n\nYou will *not* be able to use the A/B test and message on user property with this option."
}
[/block]
Depending on your SDK version, use one of the following steps to create in-app campaigns:

###New Version (SDK 3.3.0 and Above)

This section shows the steps for in-app campaigns with the new SDK.

1. Select *New in-app* if you are using a new version.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd0bfa8-In-app_Messages_-_Latest_SDK.png",
        "In-app Messages - Latest SDK.png",
        1348,
        549,
        "#eff0f1"
      ],
      "border": true
    }
  ]
}
[/block]
###Legacy Version (SDK 3.2.0 and Below)
This section shows the steps for in-app campaigns with the old SDK.

1. Select *Legacy In-app* if you are using an old SDK version.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba383ba-In-app_Messages_-_Legacy_In-app.png",
        "In-app Messages - Legacy In-app.png",
        1342,
        614,
        "#edeef0"
      ],
      "border": true
    }
  ]
}
[/block]

#Template Aspect Ratio and Image Size Guide

Follow this guide while creating in-app messages:
[block:parameters]
{
  "data": {
    "h-0": "Canvas Type",
    "h-1": "Canvas Aspect Ratio",
    "h-2": "Sample Image Sizes",
    "0-0": "Cover",
    "0-1": "Full Screen",
    "1-0": "Interstitial",
    "1-1": "1.78:1",
    "2-0": "Half Interstitial",
    "3-0": "Header",
    "4-0": "Footer",
    "5-0": "Native Alert",
    "3-1": "Height: 1:1\nWidth: Fit to screen",
    "4-1": "Height: 1:1\nWidth: Fit to screen",
    "5-1": "Native",
    "5-2": "N/A",
    "h-3": "Image Type Supported",
    "0-3": "Image",
    "1-3": "Image, audio, video. GIF file type is supported only for images with content notification.",
    "2-3": "Image",
    "3-3": "Logo Image",
    "4-3": "Logo Image",
    "5-3": "N/A",
    "3-2": "N/A",
    "0-2": "Screen Resolution",
    "2-1": "1.30:1",
    "1-2": "16:9",
    "2-2": "4:3",
    "4-2": "N/A"
  },
  "cols": 4,
  "rows": 6
}
[/block]
##Image Only Template 
When selecting an *image only* template, you can send a message which only contains an image (without CTAs and/or title and/or message).

##With Content Notification
When selecting a *With Content Notification* template, you can send a message with a background image, title, message, and CTAs.
[block:callout]
{
  "type": "info",
  "title": "Image Cropping",
  "body": "Due to the multiple phone sizes on both Android and iOS, we will center crop images if the image does not fit the screen resolution.\n\nWe scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centered in the view."
}
[/block]
#FAQs 

## I need to send an A/B test and multivariant campaigns. Do I need to update my SDK?
  * No, you do not need an SDK update.
  * You can create a custom HTML campaign for all your variants.
  * You cannot send template campaigns in that case.

##I need to send crisp template campaigns. Do I need to update my SDK?
  * Yes, the new and improved templates only work with SDK version 3.3.0 and above.
  * You cannot send these campaigns on SDK versions below that.

## My partial user base is on an old SDK and the rest are on new. How do I send them the same campaign?
  * To send a campaign, you will have to pick the legacy option.
  * This will open two variants of the campaign.
  * The *New In-App* will send the campaign to users on SDK version 3.3.0 and above.
  * The *Legacy In-App* will send the campaign to users on SDK version 3.2.x and below.
  * This legacy option will be available until March 31, 2019, and will be deprecated after this date.

## When should I use the custom HTML builder?
  * If you have not upgraded to the SDK version 3.3.0 or above, your users will not receive the template-based campaigns. In this case, you will have to use the custom HTML builder.
  * If the templates provided (Cover, Interstitial, etc.) do not meet your business use case, you can create your own HTML.

## How does my image get cropped?
  * We follow the center crop.
  * We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centered in the view. 

## What size of media can I use?
  * Image: Less than 500 kb.
  * Audio: Less than 5 Mb.
  * Video: Less than 50 Mb.

## What is the character limit for my message?
[block:parameters]
{
  "data": {
    "h-1": "Title",
    "h-2": "Message",
    "h-0": "Language",
    "0-0": "English",
    "1-0": "Chinese",
    "1-1": "9",
    "1-2": "38",
    "0-1": "30",
    "0-2": "128"
  },
  "cols": 3,
  "rows": 2
}
[/block]
## What is the Time to Live (TTL) for my message?
The default value for TTL is two days. You can define the TTL for a maximum of 28 days. 

#Sample Images
Below is a list of sample images, such as:
  * [Cover iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover-iPad.jpg)
  * [Cover](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover.jpg)
  * [Half Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad-Pro.jpg)
  * [Half Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad.jpg)
  * [Half Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Intertitial.jpg)
  * [Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad-Pro.jpg)
  * [Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad.jpg)
  * [Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Intertitial.jpg)