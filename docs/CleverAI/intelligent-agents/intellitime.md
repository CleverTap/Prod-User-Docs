---
title: IntelliTime
excerpt: >-
  Learn how you can optimize the campaign conversion rates using the IntelliTime
  Campaign feature.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

_IntelliTime_ is a feature that identifies the contextual Best Time for users. This ensures that each user receives messages at the most opportune moments, tailored to their individual contexts. This optimizes the message send time for each user based on their time zone and the period when they are most active in your application. These time-based messages help achieve the following for the Campaigns and Journeys built using the IntelliTime feature:

- Increased Engagement
- Personalized Experience
- Improved Conversion Rates

# IntelliTime Overview Video

Learn how to send campaigns based on contextual IntelliTime for users with a sample use case.

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/nFqLzQnNpQ3vd5hgBHmiyg/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

It enables you to create an IntelliTime Config based on the event and its properties. The IntelliTime Config refers to an event that triggers the determination of the best time to send a notification to your users. Thereby ensuring the optimal timing for sending messages or notifications to individual users based on their historical behavior and engagement patterns.

With this feature, you can:

- Configure up to 10 different configurations based on specific event filters along with the properties.
- View the distribution of optimal times for your users to maximize the impact of your campaigns.
- Select a fallback time for those without a clear best time.

# How It Works

CleverTap identifies the best time based on a selected config. The IntelliTime campaigns are sent by splitting a day into 12 buckets of two hours each in absolute clock time. The users are then assigned to one of these buckets based on their contextual Best Time. The user is then sent the campaign or journey in that two-hour window. If any user has not performed the selected event in the last 180 days, you can identify a fallback time for sending the campaign based on the user distribution graph.

For example, you want to send personalized discount offers to your users based on the Product Viewed in the last 180 days. With the IntelliTime feature, you can optimize the timing of these messages to maximize user engagement and conversion rates based on user distribution.


<Image src="https://files.readme.io/43f886eb77bcbbcc51ef6667b709becefe4432638af122713146296b73771dd0-a8a4f2d-Sample_Best_Time_Config-2.jpg" alt="Sample Best Time Config" align="center" width="75% " caption="Sample Best Time Config" border={true} />


<Callout icon="👍" theme="okay">
  ### Bucket Example

  For example, if a IntelliTime campaign is created on January 1 at 5:15 PM, the campaign will start running based on the upcoming best time slot i.e. 6 P.M. and the users will receive campaigns based on the slot in which they are most active on the application.
</Callout>

<Callout icon="📘" theme="info">
  ### IntelliTime Campaign Handling During DND

  If the IntelliTime bucket coincides with the DND period defined by the user, then the campaign message is discarded.
</Callout>

# Create Best Time Campaigns

This is a two-step process that includes the following steps:

1. Set Up the IntelliTime Event
2. Create a Campaign using the IntelliTime feature

## Set Up IntelliTime Config

You can configure the IntelliTime option for one-time or recurring campaigns for **Email**, **SMS**, **Push**, **WhatsApp**, and **Web Push** channels. To set up IntelliTime campaigns:

1. Navigate to _Settings_ > _Setup_ > IntelliTime from the CleverTap dashboard.
2. Click **Create New**.


<Image src="https://files.readme.io/ad3d2aa991f7e71729ba3874387503083c86ee99a89b56a75f2517e0552253a9-2026-08-19_10-46-12.jpg" alt="Set Up Best Time Event " align="center" caption="Set Up IntelliTime Event" border={true} />


3. Enter the _Config name_ to uniquely identify the IntelliTime event.
4. Select the system/custom event for which you want to define the IntelliTime campaign.
5. Click **+ Filter** to target a particular set of users for the campaign.<br />Consider an example in which you want to send IntelliTime campaigns to users who have performed the _Added To Cart_ event for the _Ironman Helmet_ product on their mobile devices.
6. (Optional) Click **Preview User Distribution** to check the user distribution for the selected event in the last 180 days. You can also change the filter based on the user distribution to achieve optimal conversion rates.


<Image src="https://files.readme.io/042c90f45d9080eea98e8a82175b5c84e1a6046bec69becae02036374454829b-2026-08-19_14-28-33_1.gif" alt="Define Best Time Config" align="center" width="70%" caption="Define Best Time Config" border={true} />


7. Click **Save** to save the IntelliTime event.

Currently, you can create journeys using the default IntelliTime config. So, it is mandatory to mark one of the IntelliTime configs as _Default_ so you can refer to it later. You can do so by clicking _Mark as Default_. Similarly, you can also delete a particular IntelliTime event by clicking _Delete_.


<Image src="https://files.readme.io/da34f6a1f8f63cf5dc89928563fef4a7d3bdcb4887760e10257b5c6f4d0a6584-2026-08-19_11-13-44.jpg" alt="Marking Best Time Event as Default" align="center" caption="Marking IntelliTime Event as Default" border={true} />


<br />

<Callout icon="📘" theme="info">
  #### Default IntelliTime Events

  The default IntelliTime events cannot be deleted. Also, deleting such events does not impact the already running campaigns.
</Callout>

## Create Campaign using IntelliTime

Here, consider an example of the IntelliTime email campaign. To create a campaign with this feature, perform the following steps:

1. Go to _Campaigns_ from the CleverTap dashboard.
2. Click **+ Campaign**.


<Image src="https://files.readme.io/e646c494011d86e8bc971fa4fe998fc3a1a18c4b2ef7fc8b39c7f5333eaf43d6-2026-08-19_14-31-37.jpg" alt="1571" align="center" border={true} />


3. Select _Email_ from the list of messaging channels.

4. Define all the following information for the campaign:

   - Qualification Criteria
   - Email Service Provider
   - Campaign Goal
   - Who
   - What

   For more information about configuring the above details on the CleverTap dashboard, refer to [Create Email Campaign](doc:create-message-email).

5. Define the IntelliTime campaign schedule:<br />a. From the _When_ section of the campaign, select _Schedule for later_ or _Set as Recurring_ under the Data and time section, depending on the nature of your campaign.<br />b. Select the date to send the campaign and select IntelliTim&#x65;_&#x20;for every user_ from the dropdown.


<Image src="https://files.readme.io/e95308f6e752ff769ae290cf8a2483ee3d85046135684b54bfd9b6e404445af6-2026-08-19_10-49-57.jpg" alt="2122" align="center" width="smart" caption="IntelliTime for every user" border={true} />


IntelliTime feature works with the following campaign types:

- One-time campaign, which is scheduled for a later time
- Campaigns scheduled for multiple dates
- Campaign scheduled for multiple dates
- Recurring campaign

<Callout icon="🚧" theme="warn">
  #### Campaign Time Overlap

  If you have the IntelliTime campaign scheduled for the present day, you cannot schedule a Fixed Time campaign for the next day to avoid campaign time overlap between two dates.
</Callout>

6. Click **Done**.
7. Select the IntelliTim&#x65;_&#x20;event_ under the _Delivery preferences_ section or select _Ad hoc event_ to define the IntelliTime event here if not done earlier.


<Image src="https://files.readme.io/b2581a5-Select_Best_Time_Event.gif" alt="Select Best Time Event" align="center" border={true} />


8. Select the _Fallback time frame_ if the best time is unavailable for the users or the user has not performed the selected event in the last 180 days.

<Callout icon="🚧" theme="warn">
  #### Fallback Time Frame

  Ensure that the fallback time frame that you set up does not overlap with the designated Do Not Disturb (DDND) hours configured for the campaign.
</Callout>

The campaign is now ready to publish.

# Create IntelliTime Journeys

For campaigns following a past behavior segment, messages can be delivered at the best time with any of the following channels: [email](doc:email), [push notifications](doc:push), [web push](doc:web-push), and [SMS](doc:SMS).

1. Set Up IntelliTime Event
2. Create Journeys with IntelliTime Feature

## Create Journeys with Best Time Feature

To create journeys using the Best time feature:

1. [Create a journey](https://docs.clevertap.com/docs/journeys) as per your requirement.
2. Click on the ![Timer](https://files.readme.io/834daaa-Timer_icon.png) icon between the segment and the consecutive message node.
3. Select the _Best time_ option to send a message at the best time. Currently, you can create journeys using the default Best Time config. So, it is mandatory to mark one of the Best Time configs as Default to refer to it later.
4. Click **Save & Close**.


<Image src="https://files.readme.io/bb2d014d971f3770f2e945bca1ed4094bc626214b620d3bf43e68b5b4b24ee44-Select_IntelliTime_under_Delivery_Options.png" alt="1547" align="center" caption="Define Delivery Options" border={true} />


# Advanced Options

If IntelliTime is chosen as the delivery option, the following advanced options are applicable:

- User time zone: Considering the IntelliTime feature chooses the time when the user is most active, the [user time zone](https://docs.clevertap.com/docs/notification-delivery-options#section-delivery-in-user-s-timezone) is always implicitly applied.
- Global throttle limits: Cannot be applied with the IntelliTime feature.