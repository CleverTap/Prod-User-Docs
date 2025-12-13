---
title: Push Notification_clone for Liquid Scripting and linked content
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
Push notifications are brief messages you can send to your mobile app users. They appear in the notification tray, or the notification inbox of the user, as shown below.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/305e7c8-image9.png",
        "image9.png",
        873,
        276,
        "#3f4248"
      ]
    }
  ]
}
[/block]
# Overview

Push notifications enable you to communicate brief yet important alerts to your users. CleverTap’s rich segmentation and powerful infrastructure enables sending time-sensitive, relevant, and personalized push messages in large-scale.

The Push module on the CleverTap dashboard (under “Campaigns”) makes it easy to set up push campaigns to all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. 

Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users clicked on them, and how many users converted as a result.

# Push Campaign Creation

## Step 1: Create a New Campaign

To start creating a push campaign, first go into “Push” under “Campaigns” on the CleverTap dashboard, then click on “Create New +” on the top-right.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bc52cb-Screenshot_2020-06-09_at_4.47.07_PM.png",
        "Screenshot 2020-06-09 at 4.47.07 PM.png",
        2878,
        1340,
        "#f7f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Step2: Select the Engagement Channel

Click Mobile Push.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d8a40b6-Screenshot_2020-06-09_at_4.50.48_PM.png",
        "Screenshot 2020-06-09 at 4.50.48 PM.png",
        2436,
        1348,
        "#f8f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
##Step 3: Select a Campaign Type

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1793634-Screenshot_2020-06-10_at_9.49.52_AM.png",
        "Screenshot 2020-06-10 at 9.49.52 AM.png",
        1998,
        908,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 4: Define the Who

The next step would be to indicate the target audience for your push campaign. You can target your push campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3cdf8ec-Campaign_Saved_Segment_Who.png",
        "Campaign_Saved_Segment_Who.png",
        1147,
        290,
        "#f4f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
If you choose to create an ad-hoc segment, you can now select a type of segment on which to base your push campaign. The target can be created either on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered push campaigns).


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/51e6bfe-campaigns_push_Message_Who.png",
        "campaigns_push_Message_Who.png",
        1438,
        765,
        "#f5f5f6"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
For instance, we can choose to create a live “Inaction within time” campaign that will target users as soon as they add a product to cart but do not finish transacting within 10 minutes, the golden window within which most users transact on our iOS and Android app platforms.

On this basis, in the next step, here is how we would set up the “WHO”. You can choose to send this campaign to all users who qualify, or just a portion of the users who qualify, under “Campaign reach”. 

###Delivering action based push notification instantly
You can trigger a push message instantly for an action. This means that users receive push notifications instantly when they perform an action in the app, instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant push message is not triggered for campaigns with delays or when the app inbox is coupled with a push message.

You can also filter users their past user behavior or user properties. For past behavior campaigns, you will also have an option to calculate estimated reach to see how many users qualify for the campaign criteria and are reachable via mobile push as of now.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/91a9aa3-image11.png",
        "image11.png",
        223,
        446,
        "#8f9092"
      ],
      "border": true
    }
  ]
}
[/block]
### Filter by User Properties

Let's say you want to send a push notification to people who live in California, whose preferred language is English, and who are between the ages 25 to 40. Using the Common Properties Filter feature in CleverTap, you can segment your campaign to only reach users who meet this criteria. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7fb4286-screen1.png",
        "screen1.png",
        1090,
        276,
        "#f5f9f7"
      ],
      "border": true
    }
  ]
}
[/block]
# Deliver to a Subset of the Target Audience

Sometimes you want to send a message to only a subset of the qualifying audience (Target Reach) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A great use case for this is a limited offer you wish to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute you can simply limit the number of users who will receive the message to exactly the number of coupons you wish to distribute.




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3aa9241-subset_image.png",
        "subset_image.png",
        406,
        87,
        "#5faeb1"
      ]
    }
  ]
}
[/block]
Here’s how it works:

In the campaign creation flow, when you are determining who to send your message to, under the Campaign Reach section, select the option to limit delivery of the messages to the number you choose.

For triggered campaigns (based on Live User Segments), as users qualify, they will receive the message until the total quantity specified has been delivered, after which the campaign ends. For campaigns based on Past Behavior Segments we’ll randomly select the users that receive the message.

The campaign limits can also be configured as follows: 

  * Daily Limit - Limit the number of users for each day, for Best Time, User-Timezone, and Triggered campaigns.
   
  * Campaign Run Limit - Limit the number of users for each run of a campaign, for Fixed Time or Recurring campaigns.

  * Safety check - It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. For example, a customer has a budget for distributing 1000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eff7bab-Campaign_Campaign_reach_annotated.png",
        "Campaign_Campaign_reach_annotated.png",
        1360,
        793,
        "#fbf9fa"
      ]
    }
  ]
}
[/block]

[block:parameters]
{
  "data": {
    "h-2": "Example",
    "h-0": "Property Type",
    "h-1": "Description",
    "0-0": "User Properties",
    "1-0": "Demographics",
    "2-0": "Geography",
    "3-0": "Geography Radius",
    "4-0": "Reachability",
    "5-0": "App Fields",
    "5-1": "App Fields filters include App Version, Device Make, Device Model, OS Version, and CleverTap SDK Version. This information is sent by CleverTap's SDK for each device that has your app. This means a single user can have multiple devices associated with their user profile.",
    "4-1": "Reachability filters include Has email address, Has phone number, Unsubscribed email, and Unsubscribed SMS.",
    "3-1": "User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. Please see the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides for more information.",
    "2-1": "User's coarse location. Filters include Country, Region, and City. CleverTap's SDK can automatically detect this from the user's IP address.",
    "1-1": "Demographics filters include Age and Gender.",
    "0-1": "Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.",
    "1-2": "Age = 25 to 40 years\nGender = Female",
    "2-2": "Country = United States\nState = California\nCity = San Francisco",
    "0-2": "Customer Type = Platinum",
    "3-2": "Locations = San Francisco, USA; Paris, France",
    "5-2": "OS Version = 10",
    "4-2": "Unsubscribed email = No"
  },
  "cols": 3,
  "rows": 6
}
[/block]
## Step 5: Define the When

Then, you can set up the “WHEN” to schedule the campaign start and end, as shown below.

Past behavior campaigns can be scheduled to run:
  * On a specific date and time.
  * On multiple specified dates and times.
  * Recurring at a periodicity you set.

Live campaigns can be set up as follows:
  * In response to a user event.
  * User event/inaction combination (Example: Abandoned cart scenario).
  * Based on a date event property value of an event (Example: Reminder for upcoming travel booking).
 
Global campaign limits are limits you can apply to determine how many push notifications each app user receives per day. If you would like to override these settings for an important campaign, you can click on the “Don’t apply global campaign limits to this campaign” checkbox.

You can also click on the “Advanced” checkbox to specify “Do Not Disturb” (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them, or delaying delivery to after DND hours (say, 9PM to 9AM) complete.

Since past behavior campaigns can have scheduled times, you have the option to stop campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. You can read more on these [here](doc:notification-delivery-options).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0302430-image22.png",
        "image22.png",
        1313,
        440,
        "#f5f6f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 6: Define the What

Finally, you can go on the next step that involves setting up push campaign content (“WHAT”). You will have 3 different options here.

### Single Message Campaign
In this campaign, we will send the same message to all users who qualify in your target audience. This message type is best for broadcast messages and for applications that don’t vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### A/B Testing
Here, we will help you test up to 3 variants of a message to understand what type of message copy works best to get clicks from users.

A/B tests allow you to test up to 3 message variants on a test group, and the variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.

Creating multiple variants for a campaign (you can also auto-copy what is already present in a current variant).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9469a2e-imagetest.png",
        "imagetest.png",
        223,
        446,
        "#8f9092"
      ],
      "border": true
    }
  ]
}
[/block]
### Advanced Options
**Sound File**
You will have to specify the name of the sound file which is included in your app bundle. Apple supports .aiff, .caf and .wav extensions. 

**Badge Count**
This updates the badge count for your app to the one specified while creating the campaign. Please note that this doesn’t increment the badge count or set the value to 0 (zero) to hide the badge number. That should be handled manually at the application level.

**Category**
You can input the name of the category while creating the campaign. Each category has to be registered with the app. Each such category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it, although the number of actions actually displayed depends on the type of notification delivered. This enables users to take multiple actions for the notification. For example, a single media push notification can have two buttons – ‘Buy Now’ and ‘Save for Later’.

**Deep Link/External URL**
Deep links allow you to land the user to a particular part of your app. Your app’s OpenURL method is called with the deep link specified here. If you wish to use external URLs, then you will have to whitelist the IPs or provide http/https before the URL so that they can be handled properly by the SDK.

**Mutable Content**
Please check this box if you would like to send the mutable-content flag along with your payload. This will invoke your app’s notification service extension. For more information click here.

**Content Available**
If you include the content-available key with a value of 1 to send out a silent notification to your users. It will not alert the user in any way (update badge count/play a sound/show a notification), but it will wake your app up in the background, allowing you to fetch new content and prepare it for the next time the user opens your app.

Key: content-available
Value: 1




**Split Delivery**
With Split Delivery, you can decide what percentage of your audience receives each message variant. We’ll deliver the messages in exactly this proportion for the duration of the campaign.




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3550a7b-image7.png",
        "image7.png",
        497,
        398,
        "#ebf0f1"
      ],
      "border": true
    }
  ]
}
[/block]
**Campaigns Sent to Past Behavior Segments**
For campaigns sent to Past Behavior Segments (grouping of users based on what they have done in the past), you have two options – launch the A/B test to a percentage of your target audience, or send out an absolute number of messages. In either case, we’ll deliver the variants equally to the test audience.

For example:
  * If you are testing three messages (Variant A, Variant B, Variant C).
  * Your Campaign Reach is 2,000,000 users.
  * You choose a Test Population of 15% of Campaign Reach (300,000 users).

Then, we will send:
  * Variant A to 100,000 users.
  * Variant B to 100,000 users.
  * Variant C to 100,000 users.

After all 300,000 messages have been delivered, we’ll calculate the winning message over this test group based on the number of click-throughs. We will then automatically send the winning message to the remainder of your target audience, which is 1,700,000 users in this example.

Note that for A/B testing, we ensure there is always an equal number of messages sent for each variant. This a  there is no bias introduced during the test phase and that the best-performing message is always declared the winner.

### Live User Segment (Triggered) Campaigns

With campaigns sent to Live User Segments (triggered) campaigns messages are delivered immediately when a user’s activity matches the criteria you’ve selected. For example: Send a message when the user has completed a booking or purchase. Since it’s not possible to determine the reach of triggered campaigns up front, you’ll need to decide how many total messages to send for A/B testing before a winner is declared.

For example, if you select 500 users as your test audience: We’ll alternate delivery of Variant A and Variant B as users qualify for the campaign. After 500 total messages are sent (Variant A – 250 and Variant B – 250), we’ll decide the “Winner” based on the number of clicks and continue only with this winning message for the duration of the campaign.

Deciding on a test audience for A/B Testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense for how many users may qualify. If you select a test audience that’s too small (say 25 users), you’ll get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no “Winner” will be declared and each message variant will be alternatively delivered for the duration of the campaign.

### Multi-Message Campaign

If you’d like to send different message variants to your target audience based on the user-properties that they possess, this campaign type would be your best bet. Typical use-case: If you want to send a localized update to people based on their preferred language, this would be the type of campaign you go with.

Similar to creating A/B test variants, you can use the “+” button to add multiple variants based on user property value. In the example below, we have used the “Language” user property such that users with different “Language” property values will receive corresponding copies of the campaign in their regional language.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/adc318a-image10.png",
        "image10.png",
        1430,
        818,
        "#edf0f5"
      ],
      "border": true
    }
  ]
}
[/block]
### Personalization (for all campaign types)

The push notification title and message body can be personalized for every user based on specific user property or event property values. See User Profiles to learn more about user profile properties and events (dynamic replacements).

To invoke the personalization menu, type “@” in the title or the text fields while typing out the push notification message.

Emojis can be included in your push notifications, just like regular text. You can use the CleverTap emoji picker, or copy-paste emojis from Emoji keyboards online.

Adding in dynamic replacements in the push title and body. Notice a preview of the push notification is available to see below.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c857483-image1.png",
        "image1.png",
        1313,
        791,
        "#f3f4f7"
      ],
      "border": true
    }
  ]
}
[/block]
Adding in emojis using CleverTap’s in-built emoji picker.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b4a0c5d-image16.png",
        "image16.png",
        394,
        570,
        "#f2f2f2"
      ],
      "border": true
    }
  ]
}
[/block]
In the “Advanced” section, you have the ability to add in rich media such as images/image carousels, gifs, and even videos using publicly-hosted media URLs. See previews on the right-hand side as you add in the media. 

### Rich Push Notifications 

You can add in a fixed (or with dynamic replacements) media (image or video) URL for both your Android and iOS push notifications.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c04fedc-image14.png",
        "image14.png",
        1313,
        793,
        "#eff0f3"
      ],
      "border": true
    }
  ]
}
[/block]
You can add in an image carousel, with each image having its own caption, sub-caption, and call to action URL (fixed or with dynamic replacements), to your iOS push notifications.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63b54d8-image12.png",
        "image12.png",
        1264,
        778,
        "#f2f3f6"
      ],
      "border": true
    }
  ]
}
[/block]
You can easily add default or custom (fixed or with dynamic replacements) sound files to your Android and iOS push notifications.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c03d176-image20.png",
        "image20.png",
        994,
        788,
        "#f8f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
You can add deeplinks (fixed or with dynamic replacements) to the overall Android or iOS push notification to enable users to access specific screens within the app upon click.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c3d3dc-image19.png",
        "image19.png",
        979,
        668,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
The collapse notification option is used to replace an existing notification with the same collapse key. For example, say push 1 and push 2 have a collapse key "A". The push 1 notification is present on the mobile device and now push 2 notification is received on the device. The push 1 notification will no longer be visible (it will be collapsed) and push 2 will be displayed.
The collapse key must be added under the collapse notification field.

###Raising Push Impression Event 

You can raise and record push notifications delivered to your users’ Android devices.
Select Settings > Schema > Events and User properties > Push Impressions and turn on the Mobile Push toggle. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88810a4-Campaigns_Mobile_Push_Notification_Settings.png",
        "Campaigns_Mobile_Push_Notification_Settings.png",
        2366,
        1164,
        "#f8f8f6"
      ]
    }
  ]
}
[/block]
After the toggle is on, all the push notifications delivered are be recorded under the “Push Impressions event.” The viewed and conversion count from this event is also available on the Push campaign stats page.


[block:callout]
{
  "type": "warning",
  "body": "1. The push event can be raised only for CleverTap SDK version 3.5.1 and above for Android and version 3.5.0 and above for iOS.\n2. If the notification channel is incorrect, the push notification is not delivered on the device and therefore no event is raised for the push impression."
}
[/block]
### Raising Notification Viewed Event for iOS
To be able to raise the Notification viewed event for iOS, it is mandatory to enable the mutable-content under the iOS section of the campaign creation
To understand how to enable Notification Viewed for your account, please visit our [developer docs](https://developer.clevertap.com/docs) 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1ce4b7-Screenshot_2019-05-17_at_8.58.45_AM.png",
        "Screenshot 2019-05-17 at 8.58.45 AM.png",
        960,
        463,
        "#f8f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
### Add Custom Actions to Android Notifications

We have added a simple way to insert button-like actions right into your Android push notifications to urge users to respond to your calls to action.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/03987cf-image4.png",
        "image4.png",
        1264,
        546,
        "#ecedf2"
      ],
      "border": true
    }
  ]
}
[/block]
Once set up, the various calls to action would appear below the push as seen below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7933e01-imagetest.png",
        "imagetest.png",
        223,
        446,
        "#8f9092"
      ],
      "border": true
    }
  ]
}
[/block]
On Android, you can also set a priority level for each notification to influence how prominently it gets displayed. The higher the priority, the more noticeable it will be.

**Maximum Priority**
Use for urgent, time-sensitive notifications. These notifications will get higher placement inside the user’s tray and appear as heads-up notifications.

**High Priority**
Use for important communications that require a extra attention such as chat messages. These will also appear as heads-up notifications and be given a higher priority in the user’s tray.

**Default Priority**
Use for the majority of your messages that are not time-critical such as general notifications and promotional offers.

**Setting Priority for Notifications with CleverTap**
You can set these priority levels right from the CleverTap dashboard as you create your Android push campaigns.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6cfe0ec-image6.png",
        "image6.png",
        212,
        70,
        "#f1f2f3"
      ],
      "border": true
    }
  ]
}
[/block]
Have your app running our latest SDK (versions v3.1.4 or higher) and follow the steps outlined above to send actionable push notifications and set notification priority on Android devices.


###Liquid Tags

Liquid tags offer great flexibility in composing your message. You can have fixed or variable values and change the look and feel of your message by using Liquid Tags 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed642bf-campaigns_liquid_tags_common_example.png",
        "campaigns_liquid_tags_common_example.png",
        1357,
        470,
        "#fafafb"
      ],
      "caption": ""
    }
  ]
}
[/block]
Each notification is personalized to the receiver. 
[block:code]
{
  "codes": [
    {
      "code": "Hello John!\n\nHere is a special coupon for you: Gold4All\n",
      "language": "html",
      "name": "Output - Liquid"
    }
  ]
}
[/block]
For more information on using tags, see [Liquid Tags](doc:liquid-tags).

### Linked Content

Linked Content gives you the ability to personalize emails with rich and contextual data that is available outside of the CleverTap platform. Linked Content helps you to send messages with send-time personalization.

For example, you deliver food across different geographies and you want to personalize offers to each user based on the weather on their location. The location can come from CleverTap personalization and the weather information can come from an API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

For more information on using Linked Content, see [Linked Content](https://docs.clevertap.com/docs/linked-content#write-linked-content).

## Step 7: Test & Schedule Campaign

Once you are all done setting up the content of your campaign in “WHAT”, you have the option to send a test push notification to any CleverTap user profile you have marked as a “Test profile”.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/83de626-image2.png",
        "image2.png",
        158,
        100,
        "#c2dff5"
      ],
      "border": true
    }
  ]
}
[/block]
Post-testing, when you are satisfied with the appearance of your campaign, you can “Continue to Overview” to view your campaign summary, the hit “Schedule notification”.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f65ea30-image21.png",
        "image21.png",
        138,
        35,
        "#51a8ea"
      ],
      "border": true
    }
  ]
}
[/block]
# Push Campaign Throttling

You can also throttle the rate at which CleverTap will deliver push notifications under Settings → Global Campaign Limits. If your user base is large and all users receive and click on a push notification at roughly the same time to open the app, you could experience a significant (unwanted) load on your systems.

Push Campaign Throttling is used to meter how quickly CleverTap will deliver your notifications.

For example, if your reachable audience for a campaign is 500,000 users and your back-end systems can only support up to 20% of them, you can set a throttle limit to 100,000 notifications per 15 minute interval. The entire campaign will then deliver in 1 hour 15 minutes.

# Viewing Push Campaign Stats
Once the campaign has gone out, you can view its stats by going into “Push” under “Campaigns” on the CleverTap dashboard and clicking on the campaign of interest to see its deliveries, clicks, and conversions.

You can track the following stats for Push Notification Campagins
**Qualified** 
Number of users qualified to receive the campaign

**Sent**
Number of deliveries attempted on devices

**Viewed**
Number of times the notification was rendered on the notification tray of the qualified users

**Clicked**
Number of clicks generated by the campaign

**Errors**
Number of errors for the campaign. These errors can be both technical errors like FCM related errors or non technical errors like Fcaps exceeded
 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/350ef25-image_1.png",
        "image (1).png",
        2320,
        1068,
        "#f6f7fa"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbbd6b5-image5.png",
        "image5.png",
        1313,
        547,
        "#f3f5f6"
      ],
      "border": true
    }
  ]
}
[/block]
**Single Message Campaign** 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d721763-image18.png",
        "image18.png",
        1307,
        792,
        "#f2f7fb"
      ],
      "border": true
    }
  ]
}
[/block]
**A/B Testing**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c02ff08-image17.png",
        "image17.png",
        1108,
        714,
        "#f3f4f5"
      ],
      "border": true
    }
  ]
}
[/block]
**Multi-Message Campaign** 

You can view the overall performance of the campaign and analyze whether you’ve achieved your marketing goal.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8d9bad2-image24.png",
        "image24.png",
        1430,
        808,
        "#f2f4f6"
      ],
      "border": true
    }
  ]
}
[/block]
You can also split the campaign stats and view the performance of each variant of the campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47f362d-image3.png",
        "image3.png",
        1430,
        808,
        "#f2f4f6"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If adding Notification channel ID is mandatory as per your settings, the list of valid channels will be available in campaign creation.",
  "title": "Notification channel ID for Android 8.0 and above"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be46b37-Screenshot_2019-08-08_at_5.53.14_PM.png",
        "Screenshot 2019-08-08 at 5.53.14 PM.png",
        720,
        419,
        "#fbfcfd"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Optimizing delivery by Push Amplification"
}
[/block]
Push notifications are a great way to engage customers but they suffer from the issue of low deliverability on certain device manufacturers
Couple with this, more and more users chooses to opt-out of Push notifications

To counter this problem, you have now Push Amplification at your disposal. Push amplification enhances the delivery of push notifications to devices that missed receiving it.

To enable this feature, go to **Settings** -> **Push Notifications** -> **Turn on the push amplification toggle**. The final state should look as illustrated below:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/188e8ce-Screenshot_2019-01-09_at_6.58.11_AM.png",
        "Screenshot 2019-01-09 at 6.58.11 AM.png",
        945,
        164,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Toggling push notification amplification",
  "body": "Once you turn 'ON' push amplification, all the push campaigns created henceforth will be amplified. Same goes for when you turn it 'OFF'."
}
[/block]
Once push amplification is turned ON, your campaigns will reach more users through your push notifications. You can check this boost numbers in your push campaign stats page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ab089bc-Screenshot_2019-01-09_at_7.04.18_AM.png",
        "Screenshot 2019-01-09 at 7.04.18 AM.png",
        1322,
        290,
        "#f6f6f8"
      ]
    }
  ]
}
[/block]
Push Amplification can be achieved via retrying the Push message as is (where messages are suppressed by the device) AND App Inbox (where the user has chosen to DND the push messages)
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "We support Push Amplification via Inbox and retrying push notifications due to delivery issues with certain OEMs. \nIf the App is online when Push is delivered, the Inbox delivery is done on the next App Launch (and not immediately after the Push is delivered)"
}
[/block]

[block:api-header]
{
  "title": "Optimizing delivery by sending to App Inbox"
}
[/block]
Apart from push amplification, you can further increase delivery of push notification by sending a copy of the same message to App Inbox. 

To send a copy of the push message to App Inbox, click the checkbox that appears at the bottom of the message builder (what section) of push notification.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d0d86c-Screenshot_2019-01-09_at_10.06.53_AM.png",
        "Screenshot 2019-01-09 at 10.06.53 AM.png",
        1318,
        623,
        "#edecec"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "App Inbox also exists as a stand-alone channel. Read more about it [here](https://docs.clevertap.com/docs/app-inbox).",
  "title": "Note"
}
[/block]
  * You will see a section to customize the same push message for App Inbox. 
  * You can change the title color, message color and background color and also choose to add filter tags which will classify your message into tabs. 
  ** Know more about tags [here](https://docs.clevertap.com/docs/app-inbox#section-message-tags). 
  * You will have to set a TTL for App Inbox message in the setup section, which can be done like [this](https://docs.clevertap.com/docs/app-inbox#section-time-to-live).

**Push Amplification + Inbox Stats**
Stats for push messages copied to App Inbox can be viewed in the push stats page. The % boost represents the % of messages boosted by App Inbox as compared to total of messages sent via App Inbox and Push Amplification

There is a separate for App Inbox to represent the stats for the copied messages
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9f6638e-Screenshot_2019-01-09_at_10.18.58_AM.png",
        "Screenshot 2019-01-09 at 10.18.58 AM.png",
        1357,
        509,
        "#f1f2f4"
      ],
      "border": true
    }
  ]
}
[/block]