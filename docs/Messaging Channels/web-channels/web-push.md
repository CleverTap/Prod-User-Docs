---
title: Web Push
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
Web push notifications are browser-based messages you can send to your website users even when they are outside of your website.

# Introduction

Web push notifications enable you to communicate brief yet important alerts to your users.

CleverTap’s rich segmentation and powerful infrastructure enables sending time-sensitive, relevant, and personalized push messages at scale.

The “Web” → “Push” module on the CleverTap dashboard (under “Campaigns”) makes it easy to set up web push campaigns to all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users clicked on them, how many users converted as a result, and more.

The prerequisite to set up web push campaigns requires the code configuration [documented here](https://developer.clevertap.com/docs/web).

# Web Push Campaign Creation

## Step 1: Create a New Campaign

To start creating a web push campaign, click Campaigns > +Campaign button > Web Push from the Desktop / Mobile web channels. The Engage page appears.

![1197](https://files.readme.io/a663fd0-Web_Push_select_channel.png "Web_Push_select_channel.png")

## Step 2: Select the Campaign Type

Past behavior campaigns can be scheduled to run

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up as follows

* In response to a user event.
* User event/inaction combination (Example: Abandoned cart scenario).
* Based on a date event property value of an event (Example: Reminder for upcoming travel booking).

<Image title="Web_Push_select_campaign_type.png" alt={1186} className="border" border={true} src="https://files.readme.io/dedb0ed-Web_Push_select_campaign_type.png" />

For instance, you can choose to create a live “Inaction within time” campaign that will target users as soon as they add a product to cart but do not finish transacting within 10 minutes, the golden window within which most users transact on our website.

## Step 3: Define the When

You can set up the “WHEN” to schedule the campaign start and end.

![1383](https://files.readme.io/f31caee-Web_Push_Select_When.png "Web_Push_Select_When.png")

Global campaign limits are limits you can apply to determine how many web push notifications each app user receives per day. If you would like to override these settings for an important campaign, you can click on the “Don’t apply global campaign limits to this campaign” checkbox.

You can also click on the “Advanced” checkbox to specify “Do Not Disturb” (DND) hours during which notifications from this web push campaign are prevented from going out, either by discarding them, or delaying delivery to after DND hours (say, 9PM to 9AM) complete.

Since past behavior campaigns can have scheduled times, you have the option to stop campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. You can read more on these [here](doc:notification-delivery-options).

Now, you can go on the next step that involves setting up web push campaign content (“WHAT”). 

## Step 4: Define the Who

The next step would be to indicate the target audience for your web push campaign. You can target your push campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 

<Image title="Campaign_Saved_Segment_PBS_Who.png" alt={1147} border={true} src="https://files.readme.io/6af1081-Campaign_Saved_Segment_PBS_Who.png">
  Saved Segments
</Image>

If you choose to create an ad-hoc segment, you can now select a type of segment on which to base your web push campaign. The target can be created either on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered web push campaigns).

<Image title="Web_Push_Select_Who.png" alt={1108} width="100%" border={true} src="https://files.readme.io/c5db5bb-Web_Push_Select_Who.png">
  Adhoc Segment
</Image>

On this basis, in the next step, here is how we would set up the “WHO”. You can also further check the “Filter this stream based on these users’ past behavior/user properties” checkbox to filter by any past user behavior or user properties. For past behavior campaigns, you will also have an option to “Estimate Reach” to see how many users qualify for the campaign criteria and are reachable via web push notifications.

## Step 4: Define the What

**Personalization**\
The web push notification text fields shown below can be personalized for every user based on specific user property or event property values.

To invoke the personalization menu, type “@” in the title or the text fields while typing out the web push message.

Emojis can be included in your web push notifications, just like regular text. You can use the CleverTap emoji picker, or copy-paste emojis from Emoji keyboards online.

<Image title="Web_Push_Select_What.png" alt={998} className="border" border={true} src="https://files.readme.io/0fce5f0-Web_Push_Select_What.png" />

You can specify a deeplink such that upon web push click, the user is taken back to a specific webpage of yours, like the checkout page. With dynamic replacements, you could in fact take the user right back to the webpage of the product they just added to cart and present them with an incentive to encourage the transaction. 

You can also specify a publicly-hosted image URL, perhaps, specifically of the product they just added to cart. You can add from a list of default web push notification icons we offer, specify a Time-To Live for the web push notification to remain viewable to users, prevent notification dismissal unless interacted with by user, and even include call to action links within the notification.

Once you are all done setting up the content of your campaign in “WHAT”, you have the option to send a test web push notification to any CleverTap user profile you have marked as a “Test profile”.

## Step 5: Setup

You can define your campaign setup at this stage. You can create the control groups, add labels, and setup conversion tracking. 

![1021](https://files.readme.io/eaa14f0-Web_Push_Select_Setup.png "Web_Push_Select_Setup.png")

After testing, when you are satisfied with the appearance of your campaign, you can “Continue” to view your campaign summary, then hit “Schedule notification”.

## Step 6: Overview & Schedule Campaign

It is now time to save and schedule your campaign. This will ensure that your message reaches your intended audience.

<Image title="Web_Push_Select_Overview.png" alt={984} className="border" width="100%" border={true} src="https://files.readme.io/a915280-Web_Push_Select_Overview.png" />

# Viewing Web Push Campaign Stats

After the campaign has gone out, you can view its stats from the dashboard by clicking Campaigns clicking on the campaign of interest to see its total sends, clicks, conversions, and revenue from conversions (if applicable).

<Image title="Web_Push_Campaign_Report.png" alt={1335} width="100%" src="https://files.readme.io/ad05981-Web_Push_Campaign_Report.png" />

## Campaign Considerations

### **Safari Considerations**

Safari being a proprietary browser has some inbuilt restrictions. Following are the considerations with Safari web push as compared to Chrome or Firefox:

* Deep-link URL is mandatory or else the notifications will not be rendered.
* Custom icons are not rendered in the notifications as Safari uses the icons available in the Safari push package
* Image and Call to action buttons are not available for Safari notifications.
* Sent and Viewed events are not supported as there is no handler unlike Service Worker in Chrome and Firefox to capture the click and view events

#### **Safari Errors**

You may see the following errors while sending web push notification on safari:  

* Invalid Authentication,
* BadRequest(400),
* DeviceTokenInactiveForTopic(410),
* ServerUnavailable(503)
