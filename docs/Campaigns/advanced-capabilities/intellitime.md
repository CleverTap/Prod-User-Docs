---
title: Best Time Campaign
excerpt: >-
  Learn how you can optimize the campaign conversion rates using the Best Time
  Campaign feature
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

*Best Time* is a feature that learns from your user's activity over time to recommend the most optimal time to send a message to each user for a campaign or a journey. This optimizes the message send-time for each user based on their time zone and the period they are most active with your application. These time-based messages help achieve the following for the Campaigns and Journeys built using the Best Time feature:

* Increased Engagement
* Personalized Experience
* Improved Conversion Rates

# Best Time Overview Video

Learn how to send campaigns based on contextual Best Time for users with a sample use case.

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

<br />

It enables you can create a Best Time Config based on the event and its properties. The Best Time Config refers to an event that triggers the determination of the best time to send a notification to your users. Thereby ensuring the optimal time to send messages or notifications to individual users based on their historical behavior and engagement patterns. 

With this feature, you can:

* Configure up to 10 different configurations based on specific event filters along with the properties.
* View the distribution of optimal times for your users, thereby maximizing the impact of the campaigns.
* Select a fallback time for those without a clear best time.

<Image title="Best Time Campaigns.png" alt={2122} align="center" className="border" width="smart" border={true} src="https://files.readme.io/aeedcd6-Best_Time_Campaigns.png" />

# How It Works

CleverTap identifies the best time based on a selected event. The  *Best Time* campaigns are sent by splitting a day into 12 buckets of two hours each. The users are then assigned to one of these buckets based on the time of the day they are most active on the app. The user is then sent the campaign or journey in that two-hour window. If any user has not performed the selected event in the last 180 days, you can select the time slot (fallback time) for sending the campaign based on the user distribution.

For example, you want to send personalized discount offers to your users based on the Product Viewed in the last 180 days. With the Best Time feature, you can optimize the timing of these messages to maximize user engagement and conversion rates based on user distribution.

<Image alt="Sample Best Time Config" align="center" width="75% " border={true} src="https://files.readme.io/a8a4f2d-Sample_Best_Time_Config.png">
  Sample Best Time Config
</Image>

> 👍 Bucket Example
>
> For example, if a *Best Time* campaign is created on January 1 at 5:15 PM, the campaign will start running based on the upcoming best time slot i.e. 6 P.M. and the users will receive campaigns based on the slot in which they are most active on the application.

> 📘 Best Time Campaign Handling During DND
>
> If the Best Time bucket coincides with the DND period defined by the user, then the campaign message is discarded.

# Create Best Time Campaigns

This is a two-step process that includes the following steps:

1. [Set Up the Best Time Event](https://docs.clevertap.com/docs/best-time#set-up-best-time-event). 
2. [Create a Campaign using the Best Time feature](https://docs.clevertap.com/docs/best-time#create-a-campaign-using-the-best-time-feature).

## Set Up Best Time Event

You can configure the best time option for one-time or recurring campaigns for **Email**, **SMS**, **Push**, **WhatsApp**, and **Web Push** channels. To set up Best Time campaigns:

1. Navigate to *Settings* > *Setup* > *Best Time* from the CleverTap dashboard.
2. Click **+ Best-Time Config**.

<Image alt="Set Up Best Time Event " align="center" border={true} src="https://files.readme.io/8a845b3-Set_Up_Best_Time_Event.png">
  Set Up Best Time Event 
</Image>

3. Enter the *Config name* to uniquely identify the Best Time event. 
4. Select the system/custom event for which you want to define the Best Time campaign. 
5. Click **+ Filter** to target a particular set of users for the campaign.\
   Consider an example where you want to send Best Time campaigns to users who have performed the *Added To Cart* event for the product *Ironman Helmet* on their mobile devices.
6. (Optional) Click **Preview User Distribution** to check the user distribution for the selected event in the last 180 days. You can also change the filter based on the user distribution to achieve optimal conversion rates.

<Image alt="Define Best Time Config" align="center" border={true} src="https://files.readme.io/de72691-Define_Best_Time_Config.gif">
  Define Best Time Config
</Image>

7. Click **Save** to save the Best Time event.

Currently, you can create journeys using the default Best Time config. So, it is mandatory to mark one of the Best Time configs as Default to refer to it later. You can do so by clicking the ![lEllipses](https://files.readme.io/3b92fb0-Ellipses.png) icon and selecting *Mark as Default*.

<Image alt="Marking Best Time Event as Default" align="center" border={true} src="https://files.readme.io/612bfbe-Mark_as_Default.png">
  Marking Best Time Event as Default
</Image>

Similarly, you can also delete a particular Best Time event by clicking the ![lEllipses](https://files.readme.io/3b92fb0-Ellipses.png) icon and then selecting *Delete*.

> 📘 Default Best Time Events
>
> The default Best Time events cannot be deleted. Also, deleting such events does not impact the already running campaigns.

## Create a Campaign using the Best Time Feature

Here, consider an example of the Best Time email campaign. To create a campaign with this feature, perform the following steps:

1. Navigate to *Campaigns* from the CleverTap dashboard.
2. Click **+ Campaign**.

<Image title="2x Create a campaign.png" alt={1571} align="center" border={true} src="https://files.readme.io/5de46d2-2x_Create_a_campaign.png">
  Create a Campaign
</Image>

3. Select *Email* from the list of messaging channels.

4. Define all the following information for the campaign:

   * Qualification Criteria
   * Email Service Provider
   * Campaign Goal
   * Who
   * What

   For more information about configuring the above details on the CleverTap dashboard, refer to [Create Email Campaign](doc:create-message-email).

5. Define the Best Time campaign schedule:\
   a. From the *When* section of the campaign, select *Schedule for later* or *Set as Recurring* under the Data and time section, depending on the nature of your campaign.\
   b. Select the date to send the campaign and select *Best time for every user* from the dropdown.

<Image title="Select Best Time option.gif" alt={1332} align="center" border={true} src="https://files.readme.io/d60c6db-Select_Best_Time_option.gif">
  Define Best Time Campaign Schedule
</Image>

   Best Time feature works with the following campaign types:

* One-time campaign, which is scheduled for a later time
* Campaigns scheduled for multiple dates
* Recurring campaign

> 🚧 Campaign Time Overlap
>
> If you have the Best Time campaign scheduled for the present day, you cannot schedule a Fixed Time campaign for the next day to avoid campaign time overlap between two dates.

  c. Click **Done**.\
  d.  Select the *Best Time event* under the *Delivery preferences* section or select *Ad hoc event* to define the Best Time event here if not done earlier.

<Image alt="Select Best Time Event" align="center" border={true} src="https://files.readme.io/b2581a5-Select_Best_Time_Event.gif">
  Select Best Time Event
</Image>

  e. Select the *Fallback time frame* if the best time is unavailable for the users or the user has not performed the selected event in the last 180 days.\
  f. Set up the remaining fields under the *When* section of the campaign and click **Done**.

The campaign is now ready to publish.

# Create Best Time Journeys

For campaigns following a past behavior segment, messages can be delivered at the best time with any of the following channels: [email](doc:email), [push notifications](doc:push), [web push](doc:web-push), and [SMS](doc:SMS).

1. [Set Up the Best Time Event](doc:best-time#set-up-best-time-event).
2. [Create Journeys with Best Time Feature](doc:best-time#create-a-campaign-using-the-best-time-feature).

## Create Journeys with Best Time Feature

To create journeys using the Best time feature:

1. [Create a journey](https://docs.clevertap.com/docs/journeys) as per your requirement.
2. Click on the ![Timer](https://files.readme.io/834daaa-Timer_icon.png) icon between the segment and the consecutive message node.
3. Select the *Best time* option to send a message at the best time. Currently, you can create journeys using the default Best Time config. So, it is mandatory to mark one of the Best Time configs as Default to refer to it later.
4. Click **Save & Close**.

<Image title="4 Click sleep time.png" alt={1547} align="center" border={true} src="https://files.readme.io/5660e8b-4_Click_sleep_time.png">
  Define Delivery Options
</Image>

# Advanced Options

If *Best Time* is chosen as the delivery option, the following advanced options are applicable:

* User time zone: Considering the *Best Time* feature chooses the time when the user is most active, the [user time zone](https://docs.clevertap.com/docs/notification-delivery-options#section-delivery-in-user-s-timezone) is always implicitly applied.
* Global throttle limits: Cannot be applied with the *Best Time* feature.
