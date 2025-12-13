---
title: Notification Delivery Options
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
# Delivery in User’s Timezone

CleverTap gives the option for delivering notifications in the user’s timezone while creating scheduled campaigns. This is a relevant feature for businesses having international users and who’d want to send time-sensitive notifications to their users. If you select this option, CleverTap will stagger the delivery of notifications and qualify users according to their timezone.

To set the timezone of the users, you will have to push it via the Tz key in the profile update push.

When setting up a campaign to be delivered in the User’s Timezone you’ll need to distinguish between the timezone of your Account (Account Timezone) and the local timezone of your users receiving the campaign.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b4dbc67-Campaign_Notification_Delivery_options.png",
        "Campaign_Notification_Delivery_options.png",
        903,
        1405,
        "#fafafc"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
Let’s assume a marketer in San Francisco (Pacific Time) creates a campaign at 4:14pm in their CleverTap Dashboard. The campaign is scheduled to deliver messages to users at 8:00pm in their local timezone.

At 5:00pm Pacific Time (Account’s Timezone) the first set of messages will deliver to users in the East Coast Timezone (8:00pm in the Eastern Timezone). One hour later (6:00pm Pacific or 8:00pm Central time) the second set of messages will be delivered to anyone qualifying in this timezone. Two hours after that (8:00pm Pacific) the next set of messages are delivered to users on the West Coast, and so forth. A typical campaign will execute for every timezone around the globe, delivering messages to any user who qualifies in each timezone.

After the marketer finishes creating the above campaign, it will move into a Scheduled State as shown here.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a4cba74-Screenshot_2020-06-09_at_8.40.26_PM.png",
        "Screenshot 2020-06-09 at 8.40.26 PM.png",
        1366,
        463,
        "#f7f9f8"
      ]
    }
  ]
}
[/block]
Once the campaign starts executing it will move into the Running State and you’ll be able to see exactly which timezone was last delivered to and which timezone is next.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba972ee-n3.png",
        "n3.png",
        1280,
        560,
        "#d1d4d6"
      ]
    }
  ]
}
[/block]
There are two additional delivery options: drop the campaign or hold the campaign for delivery the next day.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a85fe79-Screenshot_2020-06-09_at_8.55.29_PM.png",
        "Screenshot 2020-06-09 at 8.55.29 PM.png",
        742,
        229,
        "#fbfbfb"
      ],
      "border": true
    }
  ]
}
[/block]
How these delivery options work:

Consider the above marketer to be located in the Midwest (Central Time). At 11:30am, a lunchtime campaign has been scheduled to be delivered in each user’s local time. As above, the Campaign Start Time is set to 12:00pm and the first set of messages will go out at noon Central Time. Two hours later, West Coast users receive the campaign.

Since this campaign was initiated at 11:30am Central, it was already 12:30pm Eastern, which is after the specified delivery time for the East Coast users.

The campaign will continue to deliver messages in each timezone moving from East to West until it reaches the first timezone.

If “Drop the Message” was selected, any user whose timezone had already been passed when the campaign kicked off will NOT receive this campaign.

If however the option to Hold and Deliver the Next Day was selected, then the campaign will continue executing for every timezone around the globe and eventually deliver the campaign to the East Coast users at noon (eastern time) the next day.

If it is critical for a campaign to be delivered on a certain calendar day (say it’s an Easter campaign) and the message has to arrive on Easter Sunday or not at all choose the “Drop the Message” option.

Alternatively, if the date doesn’t matter, then select “Hold and Deliver” the Next Day.

# Do Not Disturb Hours

CleverTap gives the option for setting the “Do Not Disturb” hours for notification delivery while creating a campaign. You can set this to ensure that the users who get qualified for the campaign are not disturbed during the specified DND hours.

If a user qualifies for a notification in DND hours, you can decide to either completely discard the notification, or specify to deliver the notification to him or her after the end of DND hours.

# Campaign Cut-Off

CleverTap gives the option for setting the campaign “cut-off” time for every scheduled campaign while creating it. You can set this to ensure that the delivery of notifications is stopped after the specified cut-off time. This is useful if the campaign is time-sensitive and if the notification won’t be relevant later.

# Message Frequency Caps

If you have multiple marketing campaigns running simultaneously for any one channel (Push, Email, etc), the same user may qualify to receive a message from more than one campaign in a given day (or week/month). Frequency Caps allow you to limit the number of notifications a user will receive from all the campaigns running for that channel

Frequency are channel specific. Frequency Caps allows you to limit the total notifications received in a given timeframe for one delivery channel and not across all the channel as a whole.

Frequency Caps are set under Campaign Limits in Settings > Setup:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/564c098-Screenshot_2020-06-09_at_9.01.49_PM.png",
        "Screenshot 2020-06-09 at 9.01.49 PM.png",
        1232,
        790,
        "#f6f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
For more information about frequency caps, please visit [this page](doc:messaging-frequency-caps).

## Error Reporting with Frequency Caps

In the Error Reporting section of the campaign report, you can find the number of users that did not receive the campaign because of this frequency cap setting.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/160274c-find3.png",
        "find3.png",
        2256,
        936,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]