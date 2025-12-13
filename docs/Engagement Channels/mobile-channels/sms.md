---
title: SMS
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
SMS notifications are brief text messages you can send to your app or website users even when they are outside of your app.

# Introduction

SMS notifications enable you to send brief communication to your users, such as one-time passwords to authorize their use on your app, or even links enabling users to download the latest version of your mobile app. CleverTap’s rich segmentation enables sending time-sensitive, relevant, and personalized SMS messages in large-scale. 

The prerequisite to sending out SMS campaigns is [integrating your SMS provider of choice](doc:sms-partners).

The SMS module on the CleverTap dashboard (under “Campaigns”) makes it easy to set up SMS campaigns to all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users converted as a result, and more.

# Adding a new Provider

CleverTap allows you to add a new SMS provider from the Settings -> Integration -> SMS section of the dashboard
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a022f7a-Screenshot_2019-09-20_at_12.53.18_PM.png",
        "Screenshot 2019-09-20 at 12.53.18 PM.png",
        2832,
        1374,
        "#f8f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
Once the Phone Number is validated by the SMS Service Provider, you can send a 'test sms' to test the integration before you start creating SMS Campaigns and Journeys
[block:callout]
{
  "type": "info",
  "title": "Twilio SMS Integration",
  "body": "For Twilio integration, CleverTap also supports the capability to add a CoPilot id instead of a Phone Number in the 'From' section\nTwilio CoPilot improves the SMS delivery by allowing you to add multiple phone numbers to send the same campaign. Check the [Twilio CoPilot](https://www.twilio.com/copilot) page for more details"
}
[/block]
# SMS Campaign Creation Steps

## Step 1: Create a New Campaign

To start creating an SMS campaign, first go into “SMS” under “Campaigns” on the CleverTap dashboard, then click on “Create New +” on the top-right.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/200324c-image5.png",
        "image5.png",
        1299,
        345,
        "#f1f3f5"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 2: Define the Who
The next step would be to indicate the target audience for your SMS campaign. You can target your SMS campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa3981d-image3.png",
        "image3.png",
        1300,
        341,
        "#f2f3f5"
      ],
      "border": true
    }
  ]
}
[/block]
If you choose to create an ad-hoc segment, you can now select a type of segment on which to base your SMS campaign. The target can be created either on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered SMS campaigns).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dae3161-image7.png",
        "image7.png",
        1300,
        773,
        "#dfedee"
      ],
      "border": true
    }
  ]
}
[/block]
For instance, we can choose to create a live “Inaction within time” campaign that will target users as soon as they add a product to cart but do not finish transacting within 5 minutes, the golden window within which most users transact on our iOS and Android app platforms.

On this basis, in the next step, here is how we would set up the “WHO”. You can choose to send this campaign to all users who qualify, or just a portion of the users who qualify, under “Campaign reach”. You can also further check the “Filter this stream based on these users’ past behavior/user properties” checkbox to filter by any past user behavior or user properties. For past behavior campaigns, you will also have an option to “Estimate Reach” to see how many users qualify for the campaign criteria and are reachable via SMS as of now.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/624f33d-image8.png",
        "image8.png",
        1302,
        789,
        "#f8f9fa"
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
        "https://files.readme.io/7facb10-subset_image.png",
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
        "https://files.readme.io/433ccaf-campaign_Campaign_reach_SMS.png",
        "campaign_Campaign_reach_SMS.png",
        1390,
        742,
        "#fbfafa"
      ]
    }
  ]
}
[/block]
## Step 3: Define the When

Then, you can set up the “WHEN” to schedule the campaign start and end, as shown below.

Past behavior campaigns can be scheduled to run
  * On a specific date and time
  * On multiple specified dates and times
  * Recurring at a periodicity you set

Live campaigns can be set up as follows
  * In response to a user event
  * User event/inaction combination (Example: Abandoned cart scenario)
  * Based on a date event property value of an event (Example: Reminder for upcoming travel booking)

Global campaign limits are limits you can apply to determine how many SMS notifications each user receives per day. If you would like to override these settings for an important campaign, you can click on the “Don’t apply global campaign limits to this campaign” checkbox.

You can also click on the “Advanced” checkbox to specify “Do Not Disturb” (DND) hours during which notifications from this SMS campaign are prevented from going out, either by discarding them, or delaying delivery to after DND hours (say, 11PM to 9AM) complete.

Since past behavior campaigns can have scheduled times, you have the option to deliver at the specified time in the user’s timezone. You can read more on this here.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/11e26f0-image6.png",
        "image6.png",
        379,
        582,
        "#f2f4f7"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 4: Define the What

Finally, you can go on the next step that involves setting up SMS campaign content (“WHAT”):

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3c7f1e-image4.png",
        "image4.png",
        553,
        358,
        "#ecf0f4"
      ],
      "border": true
    }
  ]
}
[/block]
**Personalization**
The SMS notification body can be personalized for every user based on specific user property or event property values. See User Profiles to learn more about user profile properties and events (dynamic replacements).

To invoke the personalization menu, type “@” in the text fields while typing out the SMS message.
Emojis can be included in your SMS notifications, just like regular text. You can copy-paste emojis from Emoji keyboards online.

## Step 5: Test & Schedule Campaign

Once you are all done setting up the content of your campaign in “WHAT”, you have the option to send a test SMS notification to any mobile phone number of choice, with country code.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9bc0c3-image1.png",
        "image1.png",
        730,
        359,
        "#f1f4f7"
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
        "https://files.readme.io/47465ba-image2.png",
        "image2.png",
        138,
        35,
        "#51a8ea"
      ],
      "border": true
    }
  ]
}
[/block]