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
# Overview

SMS notifications are brief text messages sent to your app or website users even when they are outside of your app. SMS notifications provide the capability to send brief communication to your users, such as one-time passwords to authorize their use on your app or links enabling users to download the latest version of your mobile app. CleverTap’s rich segmentation offers the ability to send time-sensitive, relevant, and personalized SMS messages on a large scale. 
[block:callout]
{
  "type": "warning",
  "title": "Prerequisite",
  "body": "The prerequisite to send SMS campaigns is to integrate your SMS provider of choice. For more information, refer to [SMS](https://docs.clevertap.com/docs/sms-partners) in the integration guides."
}
[/block]
The SMS module on the CleverTap dashboard makes it easy to set up SMS campaigns for all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users converted as a result, and more.

##Add a New Provider

To add a new SMS provider, perform the following steps:
1. From the dashboard, navigate to *Settings* > *Channels* > *SMS*.
2. Click **+ Add Provider**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ea1f1a5-1_Add_Provider_dashbboard.png",
        "1 Add Provider dashbboard.png",
        1074,
        423,
        "#f7f8fb"
      ]
    }
  ]
}
[/block]
3. Enter all the required information.
4. Click **Save**. 

Once the phone number is validated by the SMS service provider, you can send a test SMS to test the integration before you start creating SMS campaigns and journeys.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bdfd5b-2_Add_a_new_provider.png",
        "2 Add a new provider.png",
        814,
        739,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Twilio SMS Integration",
  "body": "For Twilio integration, CleverTap also supports the capability to add a CoPilot id instead of a phone number in the *From* section.\n\nTwilio CoPilot improves the SMS delivery by letting you add multiple phone numbers to send the same campaign. For more information, refer to the [Twilio CoPilot](https://www.twilio.com/copilot) page."
}
[/block]
##Add a Provider Group

The failure of an SMS provider may affect your SMS campaigns, so it is always better to have another SMS provider. By grouping providers, you can provide your users a seamless experience. 

For example, if you have a subscriber base across different countries, it helps to have a provider group for each country. You can assign a preferred provider to send a message. A provider group is used based on its assigned priority for each message. If provider 1 is unavailable, then we attempt the message with provider 2, and so on. In the end, this ensures higher message deliverability for your campaigns.
[block:callout]
{
  "type": "info",
  "body": "Each provider group can have a maximum of 10 providers.",
  "title": "Provider Group Maximum"
}
[/block]
To create a provider group, perform the following steps:
1. From the dashboard, navigate to *Settings* > *SMS* > *Provider Groups* tab. 
2. Click **+ Add Provider Group**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9f0479-3_Provider_Group_dashboard.png",
        "3 Provider Group dashboard.png",
        1064,
        415,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
2. Enter a group name.
3. Select the providers by priority.
4. Click **Save Provider Group**.
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
### Edit a Provider Group

To edit a provider group, perform the following steps:

1. Click the ellipsis next to the required provider from the *Provider Groups* tab. 
2. Click **Edit settings** to add or remove providers or change the priority for any providers. 

You can also mark a provider group as a default by clicking on **Mark as Default**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72b25cf-4_Edit_Provider_Group.png",
        "4 Edit Provider Group.png",
        1062,
        509,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
# Create an SMS Campaign 

This section covers how to create a new SMS campaign.

## Create a New Campaign

To create an SMS campaign, perform the following steps:
1. Navigate to *Campaigns*. 
2. Click on the **+ Campaign** button.
3. Select *SMS* under the *Mobile channels* section. 


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
### Select the Campaign Type

To select the campaign type, use the following to make your selection:

Past behavior campaigns can be scheduled to run:
  * One time: On a specific date and time.
  * Multiple dates: On multiple specified dates and times.
  * Recurring: On a recurring basis.

Live campaigns can be set up as follows:
  * Single action: In response to a user event.
  * Inaction within time: User event or inaction combination, such as an abandoned cart scenario.
  * On a date/time: Based on a date event property value of an event, such as a reminder for upcoming travel booking.
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
## Define the When

Set up the *When* to schedule the campaign start and end.
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
Global campaign limits are limits you can apply to determine how many SMS notifications each user receives per day. If you would like to override these settings for an important campaign, you can click on the *Don’t apply global throttle limits to this campaign* checkbox.

You can also click on the *Advanced* checkbox to specify *Do Not Disturb (DND)* hours during which notifications from this SMS campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to deliver at the specified time in the user’s timezone. For more information, refer to [Notification Delivery Options](doc:notification-delivery-options).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/057f9d5-1_When_Advanced_DND.png",
        "1 When Advanced DND.png",
        587,
        827,
        "#f9f9fb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recurring Day",
  "body": "If you specify a recurring day for a campaign, such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]
## Define the Who

Next, indicate the target audience for your SMS campaign. 

You can target your SMS campaign to a new user segment by clicking on **Create an ad-hoc segment** or use a previously saved user segment from the list of pre-saved segments shown in the table as shown below. 

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
For example, we can create a live, *Inaction within time* campaign that targets users as soon as they add a product to cart but do not finish transacting within five minutes, the golden window within which most users transact on our iOS and Android app platforms.

To set up the next step in the *Who* section, you can send this campaign to all users who qualify or only a portion of the users who qualify under *Campaign reach*. You can also further check the *Filter on past user behavior and common properties* checkbox to filter by any past user behavior or user properties. For past behavior campaigns, you also have an option to estimate reach to see how many users qualify for the campaign criteria and are reachable via SMS as of now.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8109784-1a_Filter_this_stream.png",
        "1a Filter this stream.png",
        1631,
        818,
        "#fcfdfd"
      ]
    }
  ]
}
[/block]
### Deliver to a Subset of the Target Audience

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.


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
This section explains the campaign creation flow when you are determining who to send your message to. Under the *Campaign Reach* section, select the option to limit delivery of the messages to the number you choose.

For triggered campaigns based on live user segments, as users qualify, they will receive the message until the total quantity specified has been delivered after which the campaign ends. For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

  * Daily Limit: Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.
   
  * Campaign Run Limit: Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

  * Safety Check: It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 
[block:callout]
{
  "type": "success",
  "body": "A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.",
  "title": "Safety Check Example"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/884466b-2_Subset_of_the_Target_Audience.png",
        "2 Subset of the Target Audience.png",
        1614,
        812,
        "#fbfbf9"
      ]
    }
  ]
}
[/block]

## Define the What

Now, you can set up the SMS campaign content in the *What* section.


### Personalization

You can personalize the SMS notification body for every user based on specific user property or event property values. For more information on user profile properties and events (dynamic replacements), refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles).

To invoke the personalization menu, type "@" in the text fields while typing out the SMS message.

You can include emojis in your SMS notifications as you would in a regular text. You can copy-paste emojis from an emoji keyboard online. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c3c9e55-3_Define_the_What.png",
        "3 Define the What.png",
        1608,
        462,
        "#f7f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
###Liquid Tags

Liquid tags offer great flexibility in composing your message. You can have fixed or variable values and change the look and feel of your message by using liquid tags.
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
For more information, refer to [Liquid Tags](doc:liquid-tags).

### Linked Content

Linked content provides the ability to personalize emails with rich and contextual data available outside of the CleverTap platform. With linked content, you can send messages with send-time personalization.

For example, you deliver food across different geographies and you want to personalize offers to each user based on the weather and on their location. The location can come from CleverTap personalization and the weather information can come from an API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

For more information, refer to [Linked Content](https://docs.clevertap.com/docs/linked-content#write-linked-content).

## Test and Schedule a Campaign

Once you are all done setting up the content of your campaign in *What*, you have the option to send a test SMS notification to any mobile phone number of your choice, including to any country code. 

To send a test, perform the following steps:

1. Click the **Send a test SMS** link. 
2. Select an SMS service provider.
3. Enter a mobile number.
4. Click **Send**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3fb10b2-4_Test__Schedule_Campaign.png",
        "4 Test & Schedule Campaign.png",
        1604,
        500,
        "#575859"
      ],
      "border": true
    }
  ]
}
[/block]
After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:
1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Schedule notification**.
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