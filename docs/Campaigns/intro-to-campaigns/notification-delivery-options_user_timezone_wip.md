---
title: Notification Delivery Options_User_Timezone_WIP
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

CleverTap provides the capability of delivering notifications in the user’s timezone while creating scheduled campaigns or journeys. This is a relevant feature for businesses having international users and who want to send time-sensitive notifications to their users. If you select this option, CleverTap staggers the delivery of notifications and qualifies users according to their timezone.

# Use Case

A marketer in San Francisco (Pacific Time) creates a campaign at 4:14 PM in their CleverTap dashboard. The campaign is scheduled to deliver messages to users at 8:00 PM in their local timezone.

At 5:00 PM Pacific Time (account’s timezone), the first set of messages will deliver to users on the East Coast (8:00 PM in the Eastern timezone). One hour later (6:00 PM Pacific or 8:00 PM Central Time), the second set of messages will be delivered to anyone qualifying in this timezone. Two hours after that (8:00 PM Pacific), the next set of messages are delivered to users on the West Coast, and so forth. A typical campaign will execute for every timezone around the globe delivering messages to any user who qualifies in each timezone.

After the marketer finishes creating the campaign, it moves into a scheduled state. Then once the campaign starts executing, it moves into a running state where you can see that the campaign is scheduled to deliver in the user's timezone on the overview page. 

# User Timezone for Campaigns

@VISHAL SOMANI: SHOULD THIS NEXT SENTENCE BE A CALLOUT PREREQUISITE NOTE INSTEAD?\
To set the timezone of the users, push it via the Tz key in the profile update push.

To set up a campaign to be delivered in the user’s timezone, perform the following steps:

1. From the dashboard, navigate to *Campaigns*. 
2. Click **+ Campaign**.
3. Select a messaging channel.

<Image title="2x Create a campaign.png" alt={1571} className="border" border={true} src="https://files.readme.io/5de46d2-2x_Create_a_campaign.png" />

4. Navigate to *When* > *Delivery preferences*.
5. Select *Timezone*.
6. Select a delivery option: *Drop the campaign* or *Deliver the campaign the next day*.
7. Click **Done**.

<Image title="1 Timezone.png" alt={1325} className="border" width="100%" border={true} src="https://files.readme.io/f360178-1_Timezone.png" />

## How the Delivery Options Work 

The following example involves a marketer located in the Midwest (Central Time). At 11:30 AM, a lunchtime campaign has been scheduled to be delivered in each user’s local time. The campaign start time is set to 12:00 PM and the first set of messages will go out at noon Central Time. Two hours later, West Coast users receive the campaign.

Since this campaign was initiated at 11:30 AM Central, it was already 12:30 PM Eastern Time which is after the specified delivery time for the East Coast users.

The campaign continues to deliver messages in each timezone moving from East to West until it reaches the first timezone.

If *Drop the campaign* was selected, any user whose timezone had already been passed when the campaign kicked off will not receive this campaign.

If *Deliver the campaign the next day* was selected, then the campaign continues executing for every timezone around the globe and eventually delivers the campaign to the East Coast users at noon (Eastern Time) the next day.

> 📘 Critical Delivery Dates
>
> If it is critical for a campaign to be delivered on a certain calendar day (e.g., an Easter campaign) and the message has to arrive on Easter Sunday or not at all, choose the *Drop the campaign* option.

# User Timezone for Journeys

You can increase conversion by delivering messages in the user's timezone. Using the same example as the campaign section with a marketer located in the Midwest (Central Time). A lunchtime journey has been scheduled to deliver messages in each user’s local time. The first set of messages following a past behavior segment is set to go out at 11:30 AM Central Time. Two hours later, West Coast users receive the message.

Since this message was scheduled to be delivered at 11:30 AM Central, it was already 12:30 PM Eastern Time which is after the specified delivery time for the East Coast users. The message is delivered the next day for the users for whom the time of delivery has already passed.

The journey continues to deliver messages in each timezone moving from East to West until it reaches the first timezone.

To set up a journey to be delivered in the user’s timezone, perform the following steps:

1. From the dashboard, navigate to *Journeys*. 
2. Click **+ Journey**.

![1580](https://files.readme.io/60c8008-Journeys0_-_plus_journey.png "Journeys0 - plus journey.png")

3. Create a journey. 

For more information, refer to [Journeys](https://docs.clevertap.com/docs/journeys).

<Image title="Journeys1 - create a journey.png" alt={1361} className="border" border={true} src="https://files.readme.io/6674a48-Journeys1_-_create_a_journey.png" />

THIS NEXT SECTION MIGHT NOT BE APPLICABLE ANYMORE - VISHAL SOMANI TO VERIFY

2. Click the entry node....AND NOT SURE WHAT HAPPENS NEXT.

<Image title="Journeys2 - entry node.png" alt={1354} className="border" border={true} src="https://files.readme.io/fa2dee5-Journeys2_-_entry_node.png" />

THIS NEXT SECTION MIGHT NOT BE APPLICABLE ANYMORE - VISHAL SOMANI TO VERIFY

3. You can also exclude any subsequent message nodes from the user timezone. Open the node and select "Exclude this node from user timezone."

![1136](https://files.readme.io/84ceb2e-Journey_User_Timezone_Message_Node_Exclude.png "Journey_User_Timezone_Message_Node_Exclude.png")

# Do Not Disturb Hours

CleverTap provides the option for setting the Do Not Disturb hours for notification delivery while creating a campaign. You can set this to ensure that the users who get qualified for the campaign are not disturbed during the specified DND hours.

If a user qualifies for a notification in DND hours, you can decide to completely discard the notification or specify to deliver the notification to the user after the end of DND hours.

## Set DND for Mobile Push, SMS, Email, Web Push, or WhatsApp

To set DND for mobile push, SMS, email, web push, or WhatsApp campaigns, perform the following steps:

1. From the new campaign page, navigate to *When* > *Delivery preferences*. 
2. Select the *Do Not Disturb (DND)* checkbox to display the DND options. 

![1564](https://files.readme.io/7c80394-DND1_checkbox.png "DND1 checkbox.png")

3. Select the days and input the times you do not want to send campaign notifications. If you want to use the same time inactive period for each day, click the *Copy Time To All* link.
4. Select a message handling type.
5. Click **Done**.

![836](https://files.readme.io/f624d12-DND2_schedule.png "DND2 schedule.png")

# Campaign Frequency for Mobile In-App or Web Pop-up

@VISHAL SOMANI TO CONFIRM IF THIS ENTIRE SECTION STILL EXISTS. IF SO, WHERE? 

Campaign frequency provides the ability to define when the messages should be delivered. If a user qualifies outside this window, the message is discarded.

To set campaign frequency for mobile In-App or web popup campaigns, perform the following steps: 

1. From *Channel* > *When* click the **Set campaign frequency** checkbox.

REPLACE IMAGE BELOW with new screenshot and EDIT TEXT AS NEEDED

![1875](https://files.readme.io/38f0f41-2020-08-17_15-39-09_Online_Mobile_InApp.png "2020-08-17_15-39-09_Online_Mobile InApp.png")

2. Select the days and input the times you do not want to send campaign notifications. If you want to use the same time inactive period for each day, click the **Copy Time To All** link.

REPLACE IMAGE BELOW with new screenshot and EDIT TEXT AS NEEDED

![1115](https://files.readme.io/56ec59c-2020-08-17_15-43-06_Set_campaign_frequency.png "2020-08-17_15-43-06_Set campaign frequency.png")

3. Click **Continue**.

# Campaign Cut-off

CleverTap gives the option for setting the campaign cut-off time for every scheduled campaign while creating it. You can set this to ensure that the delivery of notifications is stopped after the specified cut-off time. This is useful if the campaign is time-sensitive and if the notification will not be relevant later.

# Message Frequency Caps

If you have multiple marketing campaigns running simultaneously for any one channel (push, email, and so on), the same user may qualify to receive a message from more than one campaign in a given day, week, or month. Frequency caps provide you the capability to limit the number of notifications a user will receive from all the campaigns running for that channel.

Frequency is channel-specific. Frequency caps let you limit the total notifications received in a given timeframe for one delivery channel and not across all the channels as a whole.

To set frequency caps, navigate to *Settings* > *Engage* > *Setup* > *Campaign Limits*:

<Image title="564c098-Screenshot_2020-06-09_at_9.01.49_PM.png" alt={984} className="border" border={true} src="https://files.readme.io/20ad6dc-564c098-Screenshot_2020-06-09_at_9.01.49_PM.png" />

For more information, refer to [Frequency Caps](doc:messaging-frequency-caps).

## Error Reporting with Frequency Caps

In the error reporting section of the campaign report, you can find the number of users who did not receive the campaign because of this frequency cap setting.

<Image title="find3.png" alt={2256} className="border" border={true} src="https://files.readme.io/160274c-find3.png" />
