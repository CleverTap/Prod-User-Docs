---
title: SMS_Provider_group_WIP
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
SMS notifications are brief text messages you can send to your app or website users even when they are outside of your app.

# Introduction

SMS notifications enable you to send brief communication to your users, such as one-time passwords to authorize their use on your app, or even links enabling users to download the latest version of your mobile app. CleverTap’s rich segmentation enables sending time-sensitive, relevant, and personalized SMS messages on a large-scale. 

The prerequisite to sending out SMS campaigns is [integrating your SMS provider of choice](doc:sms-partners).

The SMS module on the CleverTap dashboard (under “Campaigns”) makes it easy to set up SMS campaigns for all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users converted as a result, and more.

# Adding a new Provider

CleverTap allows you to add a new SMS provider from the Settings -> Channels -> SMS section of the dashboard
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30dfd06-Screenshot_2020-06-10_at_10.45.20_AM.png",
        "Screenshot 2020-06-10 at 10.45.20 AM.png",
        2736,
        1410,
        "#f7f8fa"
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
##Provider Groups

The failure of an SMS provider may affect your SMS campaigns.  It is always better to have another SMS provider. You can group these providers so that the users can have a seamless experience. For example, if you have a subscriber base across countries, it helps to have a provider group for each country. 
You can assign a preferred provider to send a message. A provider group is used based on its assigned priority for each message. For example, if provider 1 is unavailable, then we will attempt the message with provider 2 and so on. This ensures higher message deliverability for your campaigns. Each provider group can have a maximum of 10 providers.

To create a provider group:
1. Click Settings > SMS > Provider Groups tab. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/707782e-SMS_provider_group_tab.png",
        "SMS_provider_group_tab.png",
        755,
        473,
        "#f6f6fa"
      ],
      "border": true
    }
  ]
}
[/block]
2. Enter a group name.
3. Select the Providers by priority.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/663186b-SMS_provider_group_create.png",
        "SMS_provider_group_create.png",
        576,
        714,
        "#f7f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
### Edit Provider Group

To edit a provider group, click the ellipsis next to the required provider from the Provider Groups tab. You can add or remove providers or change the priority for any providers.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2786fd-SMS_provider_group_edit.gif",
        "SMS_provider_group_edit.gif",
        742,
        454,
        "#f5f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
# SMS Campaign Creation Steps

## Step 1: Create a New Campaign

To start creating an SMS campaign, first go into “SMS” under “Campaigns” on the CleverTap dashboard, then click on “Create New +” on the top-right.   The Channel Type page appears. Select the SMS Channel.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d5e246d-Campaign_SMS_channel_select.png",
        "Campaign_SMS_channel_select.png",
        1380,
        715,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
Select the campaign type. Select from past behavior segments or live user segments. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6cdd47b-Campaigns_SMS_segment_type.png",
        "Campaigns_SMS_segment_type.png",
        1381,
        571,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 2: Define the When


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b955aaf-Campaign_SMS_When.png",
        "Campaign_SMS_When.png",
        1381,
        546,
        "#f7f8fb"
      ],
      "border": true
    }
  ]
}
[/block]
You can set up the “WHEN” to schedule the campaign start and end, as shown below.

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

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If you specify a recurring day for a campaign, say the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]
## Step 3: Define the Who
The next step would be to indicate the target audience for your SMS campaign. You can target your SMS campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/573901c-Campaign_Saved_Segment_PBS_Who.png",
        "Campaign_Saved_Segment_PBS_Who.png",
        1147,
        290,
        "#f4f6f9"
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
        "https://files.readme.io/47da5b9-Campaign_SMS_adhoc_segment.png",
        "Campaign_SMS_adhoc_segment.png",
        1389,
        715,
        "#f9f8f6"
      ],
      "border": true
    }
  ]
}
[/block]
For instance, we can choose to create a live “Inaction within time” campaign that will target users as soon as they add a product to cart but do not finish transacting within 5 minutes, the golden window within which most users transact on our iOS and Android app platforms.

On this basis, in the next step, here is how we would set up the “WHO”. You can choose to send this campaign to all users who qualify, or just a portion of the users who qualify, under “Campaign reach”. You can also further check the “Filter this stream based on these users’ past behavior/user properties” checkbox to filter by any past user behavior or user properties. For past behavior campaigns, you will also have an option to “Estimate Reach” to see how many users qualify for the campaign criteria and are reachable via SMS as of now.

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

## Step 4: Define the What

Finally, you can go on the next step that involves setting up SMS campaign content (“WHAT”):

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c76eb9d-Campaign_SMS_What.png",
        "Campaign_SMS_What.png",
        1020,
        474,
        "#f3f4f9"
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

## Step 5: Test & Schedule Campaign

Once you are all done setting up the content of your campaign in “WHAT”, you have the option to send a test SMS notification to any mobile phone number of choice, with country code. Click the Send a test SMS link. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/263ded3-Campaigns_SMS_Test.png",
        "Campaigns_SMS_Test.png",
        1015,
        430,
        "#6a696b"
      ],
      "border": true
    }
  ]
}
[/block]
Post-testing, when you are satisfied with the appearance of your campaign, 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/665f358-SMS_setup_provider_group_select.png",
        "SMS_setup_provider_group_select.png",
        982,
        720,
        "#f6f7fa"
      ],
      "border": true
    }
  ]
}
[/block]
You can now click the  Continue button. The overview page appears. 

View your campaign summary and then click the “Schedule notification” button.

FAQs

Q. What does it mean by "User DND Set Error"?
A. "User DND set Error" occurs when you qualify users for a campaign even though they have unsubscribed on the target device. This error informs you that these users have been passed into the error bucket.