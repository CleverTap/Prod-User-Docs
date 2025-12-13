---
title: In-App Campaigns
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
[block:callout]
{
  "type": "warning",
  "title": "Important Note",
  "body": "To be able to use the template based In-app campaigns, please update your app with the CleverTap SDK version **3.3.0** or above\n\nA/B test does not need an SDK update. You can still send A/B on any SDK (including below 3.3.0) version as long as all the variants are **HTML templates**"
}
[/block]
## Introduction
As of **October 29, 2018**, we have released a new and improved In-apps with crisper message rendering capability

The capability also allows you to send InApp messages with Images, GIFs, Video and Audio

You can also do A/B testing on your InApps


## How to Guide

#### HTML InApps

**Step 1: Pick the Message Type**
You can select one of the following message types
1. Single Message
2. A/B Test
3. Message on user property
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/618b664-Screen_Shot_2018-10-25_at_2.08.33_PM.png",
        "Screen Shot 2018-10-25 at 2.08.33 PM.png",
        1161,
        654,
        "#fbfafb"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 2: Pick the Device**
You can send the campaign to iOS and/or Android
You can send the campaign to Mobile and/or Tablet
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac59c8b-Screen_Shot_2018-10-25_at_2.10.58_PM.png",
        "Screen Shot 2018-10-25 at 2.10.58 PM.png",
        1163,
        648,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
**Step 3: Pick the Custom HTML Template**
Pick the custom HTML template. Note that other templates are supported only on SDK versions 3.3.0 and above
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1e44e50-Screen_Shot_2018-10-29_at_6.09.04_PM.png",
        "Screen Shot 2018-10-29 at 6.09.04 PM.png",
        674,
        391,
        "#fcfbfb"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 4: Use the 'Builder' option**
When you pick the 'Builder' option, you will be able to create HTML In-apps via a drag-drop method
Alternatively, you can also choose to use the 'Custom HTML' option to build your own campaign
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9544986-Screen_Shot_2018-10-29_at_6.12.53_PM.png",
        "Screen Shot 2018-10-29 at 6.12.53 PM.png",
        1162,
        624,
        "#e6eaee"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Create Interactive InApps",
  "body": "You can create interactive InApp campaigns like scratch card campaigns, swipe interaction campaigns etc. using Javascript.\nUsing the Custom HTML option, you can use Javascript in the HTML and create deep interactive InApp campaigns. Just add the Javascript code along with the HTML code \nNote: Javascript based campaigns are available on v3.5.0 and above"
}
[/block]
#### Native InApps

**Step 1: Pick the Message Type**
You can select one of the following message types
1. Single Message
2. A/B Test
3. Message on user property


**Step 2: Pick the Device**
You can send the campaign to iOS and/or Android
You can send the campaign to Mobile and/or Tablet


**Step 3: Pick ANY Template**
Since your entire user base is on SDK v3.3.0 and above, you can select any one of the below templates or Custom HTML template
You will have to choose the canvas size and type before you start creating the message. The campaign canvas provided by default are the following
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc872ca-Screen_Shot_2018-10-25_at_2.16.21_PM.png",
        "Screen Shot 2018-10-25 at 2.16.21 PM.png",
        1156,
        642,
        "#faf8f9"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 4: Build the In-app message**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d1f57b-Screenshot_2019-05-17_at_9.09.53_AM.png",
        "Screenshot 2019-05-17 at 9.09.53 AM.png",
        1322,
        681,
        "#f4f4f5"
      ],
      "border": true
    }
  ]
}
[/block]
Step 4a: Personalize Media
Optionally, you can personalize In-App messages by using the 'personalized media' option. This option helps you to create recommendation In-Apps and also to upload personalized images for each of your user
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
**Step 5: Pick the media for each orientation**
* Using the background option in InApps, you can choose the media that you want your end users to see when the app is in portrait mode and in landscape mode
* You can choose to add the same image with different form factors or different images altogether to give a unique experience on portrait and landscape
[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "The information provided below is for customers whose entire audience have not updated their app to support the Native InApp capability\n\nPost releasing the app update, there will be users who will be on both old and new app versions. In this case, to send a campaign to both your user base, follow the steps below\n\n- You will NOT be able to use the A/B test and Message on User Property with this option"
}
[/block]
#### Users on older sdk versions

This will open 2 InApp builders
**1. New version (SDK 3.3.0 and above)**
New version will allow you to create the new InApp campaigns

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65c710b-Screen_Shot_2018-10-25_at_5.12.57_PM.png",
        "Screen Shot 2018-10-25 at 5.12.57 PM.png",
        1346,
        697,
        "#f6f6f7"
      ],
      "border": true
    }
  ]
}
[/block]
**2. Legacy version (SDK 3.2.0 and below)**
This will open the Legacy InApp builder.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/acff800-Screen_Shot_2018-10-25_at_5.16.10_PM.png",
        "Screen Shot 2018-10-25 at 5.16.10 PM.png",
        1368,
        715,
        "#e7ebee"
      ],
      "border": true
    }
  ]
}
[/block]



## Template Aspect Ratio and Image Size Guide
[block:parameters]
{
  "data": {
    "h-0": "Canvas Type",
    "h-1": "Canvas Aspect Ratio",
    "h-2": "Sample Image Sizes",
    "0-0": "Cover",
    "0-1": "Full Screen",
    "1-0": "Interstitial",
    "1-1": "1.78 : 1",
    "2-0": "Half Interstitial",
    "3-0": "Header",
    "4-0": "Footer",
    "5-0": "Native Alert",
    "3-1": "Height: \nWidth: Fit to screen",
    "4-1": "Height: \nWidth: Fit to screen",
    "5-1": "Native",
    "5-2": "NA",
    "h-3": "Image type supported",
    "0-3": "Image",
    "1-3": "Image, gif, audio, video",
    "2-3": "Image",
    "3-3": "Logo Image",
    "4-3": "Logo Image",
    "5-3": "NA",
    "3-2": "1:1",
    "0-2": "Screen Resolution",
    "2-1": "1.30 : 1",
    "1-2": "16:9",
    "2-2": "4:3",
    "4-2": "1:1"
  },
  "cols": 4,
  "rows": 6
}
[/block]
**Image only template** 
When selecting an *image only* template, you can send a message which only contains only an image (without CTAs and/or Title and/or Message)

**With Content Notification**
When selecting an *With Content Notification* template, you can send a message with a background image, Title, Message and CTAs
[block:callout]
{
  "type": "info",
  "title": "Image Cropping",
  "body": "Due to the multiple phone sizes on both Android and iOS, we will **centre crop** images if the image does not fit the screen resolution\n\nWe scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centred in the view"
}
[/block]
## FAQs 

####1. I need to send AB test and MV campaigns. Do I need to update my SDK?
  * **No**. MV and AB test does not need SDK update.
  * You can create a custom HTML campaign to all your variants.
  * You cannot send template campaigns in that case

####2. I need to send crisp template campaigns. Do I need to update my SDK?
  * **YES**. The new and improved templates work only with SDK v3.3.0 and above
  * You cannot send these campaigns on SDK versions below that

####3. My partial user base is on old SDK and rest are on new. How do I send them the same campaign?
  * To send such a campaign, you will have to pick the '**legacy**' option as per the screenshot below
  * This will open 2 variants of the campaign
  * The 'new In-app' will send the campaign to users on SDK v3.3.0 and above
  * The 'old In-app' will send the campaign to users on SDK v3.2.x and below
  * This legacy option will be available till March 31, 2019. It will be deprecated post that

####4. When should I use the Custom HTML builder?
  * If you have not upgraded to the SDK version 3.3.0 or above, your users will not receive the template based campaigns. In this case you will have to use the custom html builder
  * If the templates provided (Cover, Interstitial, etc.) does not meet your business use case, you can create your own HTML 

####5. How does my image get cropped?
  * We follow the **centre crop**
  * We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centred in the view 

####6. What size of media can I use?
  * Image: Less than 500 kb
  * Audio: Less than 5 Mb
  * Video: Less than 50 Mb 



##Sample Images
[1. Cover iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover-iPad.jpg)
[2. Cover](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover.jpg)
[3. Half Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad-Pro.jpg)
[4. Half Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad.jpg)
[5. Half Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Intertitial.jpg)
[6. Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad-Pro.jpg)
[7. Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad.jpg)
[8. Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Intertitial.jpg)

##Deprecation Notice