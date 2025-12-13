---
title: App Inbox
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
App Inbox is a messaging channel that lets you deliver rich, individually customized content to your customers. Messages that are sent to App Inbox are saved on the user device. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/effe757-iPhoneXs_Max_-_black.png",
        "iPhoneXs Max - black.png",
        890,
        1720,
        "#8d8989"
      ],
      "caption": "CleverTap's App Inbox"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Why do you need App Inbox as a channel?"
}
[/block]
Push Notification and In-app campaigns are great for grabbing the attention of the app user but they are short-lived. Once swiped off, they lose their ability to engage the customer. If the user is not online or is busy, you lose the opportunity of engagement forever.

App Inbox allows you to send permanent content directly to your app from CleverTap dashboard. Moreover, the inbox messages are targetable to individual segments just like other messaging channels. Which means your inbox can look totally different from the inbox of another user. The possibilities are endless.
[block:api-header]
{
  "title": "How to get started?"
}
[/block]
To be able to use CleverTap's App Inbox in your app, you need to go through the following steps:
1. Update CleverTap SDK to version 3.4.0.
2. Follow the steps for integration of App Inbox with your app [here](https://developer.clevertap.com/v1.0/docs/android#section-app-inbox) for Android and [here](https://developer.clevertap.com/v1.0/docs/ios#section-app-inbox) for iOS.

That's it! Now your app is equipped with one of the most powerful channels for engagement. 
[block:api-header]
{
  "title": "Creating an App Inbox message"
}
[/block]
## Step 1: Create a Campaign

Click on the + Campaign button
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58cf670-Screenshot_2019-01-04_at_6.20.42_PM.png",
        "Screenshot 2019-01-04 at 6.20.42 PM.png",
        1440,
        625,
        "#dddfe3"
      ]
    }
  ]
}
[/block]
Select App Inbox from the channel selection page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d25d4f-Screenshot_2019-01-04_at_6.23.57_PM.png",
        "Screenshot 2019-01-04 at 6.23.57 PM.png",
        1440,
        714,
        "#f1f1f4"
      ]
    }
  ]
}
[/block]
Pick the message type, target segment.
Select the type of the message.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9dfd649-Screenshot_2019-01-04_at_6.37.45_PM.png",
        "Screenshot 2019-01-04 at 6.37.45 PM.png",
        1440,
        736,
        "#f3f4f6"
      ]
    }
  ]
}
[/block]
## Step 2: Drafting an App Inbox message 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/31e6f5c-Screenshot_2019-01-05_at_5.09.13_PM.png",
        "Screenshot 2019-01-05 at 5.09.13 PM.png",
        1440,
        768,
        "#dfe0e2"
      ]
    }
  ]
}
[/block]
The message builder for App Inbox is where you can create a rich message that you feel will be best to engage your **audience**.

## Message variants
You can select different variants of the message such as Simple Message or [A/B & Multivariate Testing](doc:ab-multivariate-testing).

## Call to Action 
App inbox enables various types of CTAs to cater to different use cases for the client. Here are the types:

**1. Click-on-message CTA**: Opens a deeplink when you click anywhere on the message (text or image or both)
**2. Button CTA**: Additonal links at the bottom that can be given different color to attract user's attention
**3. Click-to-copy CTA**: A special type of CTA that enables user to copy to clipboard. This can be used to enable users to copy discount codes to your products and apply them at the time of checkout.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e67cc7-Screenshot_2019-01-06_at_5.17.14_PM.png",
        "Screenshot 2019-01-06 at 5.17.14 PM.png",
        878,
        577,
        "#fcfcfd"
      ]
    }
  ]
}
[/block]
## Message tags
You can "tag" an inbox message with one or more comma separate strings. These tags help you identify the messages inside the user's device. Additionally, these tags also help you classify your messages into different tabs in your app.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b3dd25-Screenshot_2019-01-06_at_4.53.47_PM.png",
        "Screenshot 2019-01-06 at 4.53.47 PM.png",
        224,
        136,
        "#f7f7f8"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Using message tags effectively",
  "body": "Message tags are an excellent way to engage your users contextually. For example, some of your app users might be interested in \"offers\" while others in \"news updates\". You can have 2 separate tabs to categorise your inbox messages into those two buckets. Note that it's not compulsory to have tabs.\n\nYou can define the names of the inbox tabs during configuration of App Inbox with your app. The same names should be entered as tags. In case you do not specify any tag, the message will go into the default bucket \"All\"."
}
[/block]
## Message templates
App inbox allows 4 message templates:

**1. Simple message** 
A simple message consists of the following elements:
(a) Title
(b) Message
(c) Media (optional): Jpg, gif, mp4 vide and mp3 formats are supported
(c) Call to action (optional)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3b5c15-Screenshot_2019-01-18_at_6.26.52_PM.png",
        "Screenshot 2019-01-18 at 6.26.52 PM.png",
        585,
        627,
        "#f16782"
      ],
      "caption": "App Inbox message template: Image with message and CTA",
      "border": true
    }
  ]
}
[/block]
**Supported media types**
[block:parameters]
{
  "data": {
    "h-0": "Media Type",
    "h-1": "16:9 Aspect Ratio",
    "h-2": "1:1 Aspect Ratio",
    "0-0": "Image (jpg, png, gif)",
    "0-1": "Yes",
    "0-2": "Yes",
    "h-3": "Max Size",
    "0-3": "500 KB",
    "1-0": "Video (mp4)",
    "1-1": "Yes",
    "1-2": "Yes",
    "2-0": "Audio (mp3)",
    "2-1": "NA",
    "2-2": "NA",
    "2-3": "5 MB",
    "1-3": "50 MB"
  },
  "cols": 4,
  "rows": 3
}
[/block]
** 2. Carousel message with content** 
This is a multi-slide template, where you can draft up to 5 slides containting images with content. This appears in the form of right and left scrolling carousel in the user app. This is a rich template which can be used in situations such as promoting a list of products, or movies that will release this weekend etc.
[block:callout]
{
  "type": "info",
  "body": "CTAs in carousel messages are click-on-image and there are no provisions for external buttons.",
  "title": "Note"
}
[/block]
**3. Carousel message without content** 
Similar to the above template, but without title text and messages. 

**4. Message with icon** 
This template can be used when you want to also include an icon in the message. It is similar to the simple message, and it includes an additional icon placeholder

## Step 3: Setup and schedule the campaign 
The final step is to configure the setup of the campaign and scheduling it.

## Time to live 
App Inbox campaign are by design persisted on the user device for a number of days. You can configure the number of days to keep the message on the user's device by setting the TTL.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2dccbb3-Screenshot_2019-01-06_at_5.26.25_PM.png",
        "Screenshot 2019-01-06 at 5.26.25 PM.png",
        970,
        226,
        "#f4f5f8"
      ]
    }
  ]
}
[/block]
The TTL can range between 1 day to 60 days. The message on the user's device stays there for the specified TTL, after which it is automatically removed. You can also have Infinite TTL, which means the message will never be deleted from the user's device. 
[block:callout]
{
  "type": "warning",
  "title": "Choosing the right TTL",
  "body": "You should choose a TTL that resonates with the purpose of your campaign. Some messages need to stay on the user's device for a longer period (such as coupon codes which are valid for a month) while some should last for a day or two (such as weekend discount offers)."
}
[/block]

Finally, click on Schedule Campaign. And you are done.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Each message stored on the CleverTap platform for App Inbox is accounted for as a user event"
}
[/block]

[block:api-header]
{
  "title": "Viewing App Inbox Stats"
}
[/block]
Once the campaign has gone out, you can view its stats by going into “Campaigns” on the CleverTap dashboard and clicking on the App Inbox campaign of interest.

**Qualified:** Number of devices which have an updated SDK enabled for App Inbox
**Sent:** Number of messages sent to the qualified devices
**Viewed:** Number of messages viewed by users
**Clicked:** Number of clicks on the message CTAs