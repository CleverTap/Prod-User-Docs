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

To start creating a web push campaign, first go into “Web” → “Push” under “Campaigns” on the CleverTap dashboard, then click on “Create New +” on the top-right.

<Image title="image31.png" alt={1298} className="border" border={true} src="https://files.readme.io/698a4ef-image31.png" />

## Step 2: Define the Who

The next step would be to indicate the target audience for your web push campaign. You can target your push campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 

<Image title="image110.png" alt={1301} className="border" border={true} src="https://files.readme.io/04b6346-image110.png" />

If you choose to create an ad-hoc segment, you can now select a type of segment on which to base your web push campaign. The target can be created either on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered web push campaigns).

<Image title="image96.png" alt={1294} className="border" border={true} src="https://files.readme.io/7392e87-image96.png" />

For instance, we can choose to create a live “Inaction within time” campaign that will target users as soon as they add a product to cart but do not finish transacting within 10 minutes, the golden window within which most users transact on our website.

On this basis, in the next step, here is how we would set up the “WHO”. You can also further check the “Filter this stream based on these users’ past behavior/user properties” checkbox to filter by any past user behavior or user properties. For past behavior campaigns, you will also have an option to “Estimate Reach” to see how many users qualify for the campaign criteria and are reachable via web push notifications as of now.

<Image title="image84.png" alt={1302} className="border" border={true} src="https://files.readme.io/8143fc0-image84.png" />

## Step 3: Define the When

Then, you can set up the “WHEN” to schedule the campaign start and end, as shown below.

Past behavior campaigns can be scheduled to run

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up as follows

* In response to a user event.
* User event/inaction combination (Example: Abandoned cart scenario).
* Based on a date event property value of an event (Example: Reminder for upcoming travel booking).

Global campaign limits are limits you can apply to determine how many web push notifications each app user receives per day. If you would like to override these settings for an important campaign, you can click on the “Don’t apply global campaign limits to this campaign” checkbox.

You can also click on the “Advanced” checkbox to specify “Do Not Disturb” (DND) hours during which notifications from this web push campaign are prevented from going out, either by discarding them, or delaying delivery to after DND hours (say, 9PM to 9AM) complete.

Since past behavior campaigns can have scheduled times, you have the option to stop campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. You can read more on these [here](doc:notification-delivery-options).

<Image title="image75.png" alt={1298} className="border" border={true} src="https://files.readme.io/f8dd42e-image75.png" />

Finally, you can go on the next step that involves setting up web push campaign content (“WHAT”). 

## Step 4: Defining the What

**Personalization**\
The web push notification text fields shown below can be personalized for every user based on specific user property or event property values.

To invoke the personalization menu, type “@” in the title or the text fields while typing out the web push message.

Emojis can be included in your web push notifications, just like regular text. You can use the CleverTap emoji picker, or copy-paste emojis from Emoji keyboards online.

<Image title="image40.png" alt={412} className="border" border={true} src="https://files.readme.io/efc92e8-image40.png" />

You can specify a deeplink such that upon web push click, the user is taken back to a specific webpage of yours, like the checkout page. With dynamic replacements, you could in fact take the user right back to the webpage of the product they just added to cart and present them with an incentive to encourage the transaction. 

You can also specify a publicly-hosted image URL, perhaps, specifically of the product they just added to cart. You can add from a list of default web push notification icons we offer, specify a Time-To Live for the web push notification to remain viewable to users, prevent notification dismissal unless interacted with by user, and even include call to action links within the notification, as shown below.

<Image title="image32.png" alt={838} className="border" border={true} src="https://files.readme.io/abeef64-image32.png" />

## Step 5: Test & Schedule Campaign

Once you are all done setting up the content of your campaign in “WHAT”, you have the option to send a test web push notification to any CleverTap user profile you have marked as a “Test profile”.

<Image title="image90.png" alt={158} className="border" border={true} src="https://files.readme.io/6c4a5e6-image90.png" />

After testing, when you are satisfied with the appearance of your campaign, you can “Continue to Overview” to view your campaign summary, the hit “Schedule notification”.

<Image title="image23.png" alt={138} className="border" border={true} src="https://files.readme.io/2fab8dd-image23.png" />

# Viewing Web Push Campaign Stats

Once the campaign has gone out, you can view its stats by going into “Web” → “Push” under “Campaigns” on the CleverTap dashboard and clicking on the campaign of interest to see its total sends, clicks, conversions, and revenue from conversions (if applicable).
