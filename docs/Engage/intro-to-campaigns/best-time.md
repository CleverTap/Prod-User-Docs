---
title: Best Time for Batch Campaigns
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

Best Time is a feature that recommends the most optimal time to send a message to each user for a Batch campaign. 

We optimize the message send time for each user based on when that user is most active with your application. If you send a campaign with the Best Time feature enabled, users will be more likely to engage with your message when receiving it.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6b2bdc-image1.png",
        "image1.png",
        717,
        440,
        "#faf9fa"
      ],
      "border": true
    }
  ]
}
[/block]
You can use the Best Time feature with the following channels: [Email](doc:email), [Push Notification](doc:push), [Web Push](doc:web-push), and [SMS](doc:sms).

You can use the Best Time feature with the following campaign types:
* One Time → Later → Best Time
* Multiple Dates → Best Time on Every Date
* Multiple Dates → Combination of Best Time and Fixed Time
* Recurring -> Best Time

# How It Works

We identify the "Best Time" based on a specific event that is chosen by you.

CleverTap sends Best Time campaigns by splitting the day into 12 two-hour buckets, and assigning your users to one of these buckets based on the time of the day they are most active with your app. The user is then sent the campaign in that two-hour window.

If there is any user who has not performed the said event in the last 180 days, they will be sent the campaign at the CleverTap default time. The default time is right after the 12th bucket

For example, if a Best Time campaign is created on January 1 at 5:15 pm, then all users who are most active between 5:00pm to 7:00pm will qualify for the first bucket and receive the campaign immediately. The next run will happen at 7:15pm, and users who are most active in the 7:00pm to 9:00pm bucket will receive the message then. 


# Feature Guide

## Step 0: Best Time Setup

Under settings -> Campaign integrations and limits -> Best Time Campaign Setting, you can setup the event which will be used to calculate the best time. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dced14a-Screen_Shot_2018-10-16_at_7.34.00_PM.png",
        "Screen Shot 2018-10-16 at 7.34.00 PM.png",
        887,
        450,
        "#f4f5f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 1: Create a Campaign

You can use the Best Time feature with the following channels: Email, Push Notification, Web Push, and SMS.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3c46ca9-image2.png",
        "image2.png",
        1189,
        520,
        "#f5f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 2: Choose the Campaign Type 

You can use the Best Time feature with the following campaign types:
* One Time → Later → Best Time
* Multiple Dates → Best Time on Every Date
* Multiple Dates → Combination of Best Time and Fixed Time
* Recurring -> Best Time
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/653ede1-image3.png",
        "image3.png",
        836,
        542,
        "#f5f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 3: Select the Best Time Option
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0ca65c-image1.png",
        "image1.png",
        717,
        440,
        "#faf9fa"
      ],
      "border": true
    }
  ]
}
[/block]
# Notes

If Best Time is chosen as the delivery option, the following advanced options will not be applicable:

* **User Time Zone:** Since the Best Time feature chooses the time when the user is most active, the [user time zone](https://docs.clevertap.com/docs/notification-delivery-options#section-delivery-in-user-s-timezone) does not apply.
* **Global Throttle Limits:** [Message throttling](https://docs.clevertap.com/v1.0/docs/notification-delivery-options#section-message-frequency-caps) cannot be applied with the Best Time feature.