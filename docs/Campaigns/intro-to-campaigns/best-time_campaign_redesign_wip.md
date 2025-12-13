---
title: Best Time_Campaign_redesign_WIP
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
# Overview

*Best Time* is a feature that recommends the most optimal time to send a message to each user for a batch campaign or a journey. 

We optimize the message send-time for each user based on when that user is most active with your application. If you send a campaign with the *Best Time* feature enabled, users are more likely to engage with your message when receiving it.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db4cc4a-1_Best_time_for_every_user.png",
        "1 Best time for every user.png",
        1562,
        517,
        "#fbfbfb"
      ],
      "border": true
    }
  ]
}
[/block]
# How It Works

We identify the best time based on a specific event that you choose.

CleverTap sends *Best Time* campaigns by splitting a day into two-hour buckets, 12 buckets in total. Your users are then assigned to one of these buckets based on the time of the day they are most active with your app. The user is then sent the campaign or journey in that two-hour window.

If there is any user who has not performed the selected event in the last 180 days, then they are sent the campaign or journey at the CleverTap default time. The default time is right after the 12th bucket.
[block:callout]
{
  "type": "success",
  "title": "Bucket Example",
  "body": "For example, if a *Best Time* campaign is created on January 1 at 5:15 PM, then all users who are most active between 5:00 PM to 7:00 PM qualify for the first bucket and receive the campaign immediately. The next run happens at 7:15 PM and users who are most active in the 7:00 PM to 9:00 PM bucket receive the message."
}
[/block]
#Best Time Setup

To set up *Best Time*, perform the following steps:

1. From the dashboard, navigate to *Settings* > *Setup* > *Best Time*.
2. Select the event to be used to calculate the best time. 
3. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6853c88-2_Select_attendance_event.png",
        "2 Select attendance event.png",
        746,
        329,
        "#f6f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
#Best Time for Campaigns

To create a campaign with this feature, perform the following steps:

1. From the dashboard, navigate to *Campaigns*. 
2. Click **+ Campaign**.
3. Select one of the following channels: [email](doc:email), [push notifications](doc:push), [web push](doc:web-push), and [SMS](doc:sms).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5de46d2-2x_Create_a_campaign.png",
        "2x Create a campaign.png",
        1571,
        621,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
4. Select a campaign type.

This feature works with the following campaign types:
  * One time > Later > Best time
  * Multiple dates >  Best time on every date
  * Multiple dates > Combination of the best time and fixed time
  * Recurring > Best time

5. Select the best time option. 

This option is available for multiple dates campaigns.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/89a9c9e-3a_Select_multiple_dates.png",
        "3a Select multiple dates.png",
        1575,
        575,
        "#fbfbfb"
      ],
      "border": true
    }
  ]
}
[/block]
Or it is available for recurring campaigns.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9860ca3-3b_Select_recurring_dates.png",
        "3b Select recurring dates.png",
        776,
        680,
        "#fbfafb"
      ]
    }
  ]
}
[/block]

#Best Time for Journeys

For campaigns following a past behavior segment, messages can be delivered at the best time with any of the following channels including, [email](doc:email), [push notifications](doc:push), [web push](doc:web-push), and [SMS](doc:SMS).

## Click Sleep Time

To set up a message to deliver at the best time, create a journey. For more information, refer to [Journeys](https://docs.clevertap.com/docs/journeys). Then, perform the following steps:
<<Mention this is only available post PBS nodes>>
1. Click on the sleep time (timer icon) between the segment and the next message.
2. Select the *Best time* option to send out a message at the best time. 
3. Click **Save & Close**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5660e8b-4_Click_sleep_time.png",
        "4 Click sleep time.png",
        1547,
        801,
        "#c6c6c8"
      ],
      "border": true
    }
  ]
}
[/block]
#Advanced Options

If *Best Time* is chosen as the delivery option, the following advanced options are applicable:

* User time zone: Considering the *Best Time* feature chooses the time when the user is most active, the [user time zone](https://docs.clevertap.com/docs/notification-delivery-options#section-delivery-in-user-s-timezone) is always implicitly applied.
* Global throttle limits: [Message throttling](https://docs.clevertap.com/v1.0/docs/notification-delivery-options#section-message-frequency-caps) cannot be applied with the *Best Time* feature.