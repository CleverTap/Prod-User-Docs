---
title: Create Message
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
Get started with creating an app inbox message by using the following steps:

## Create a Campaign

1. Navigate to *Messages* > *Campaigns*.
2. Click on **+ Campaign**.
3. Select **App Inbox** from the *Messaging Channels* list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4fc4993-Campaigns_list_first.png",
        "Campaigns_list_first.png",
        1152,
        854,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
The campaign page displays. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1de9fd3-App_Inbox_editor_main.png",
        "App_Inbox_editor_main.png",
        1180,
        1211,
        "#fbfafb"
      ],
      "sizing": "80",
      "border": true
    }
  ]
}
[/block]
After all the sections have been defined, you can publish the campaign. 

## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:

* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve in the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to *How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount?*. 

Create focused conversions using event properties.  For more information on event properties, see [Events](doc:events). 

Define the conversion period by selecting the *Funnel Conversion Time*. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4fbbeb2-Push_notification_set_goal_track_conversion.png",
        "Push_notification_set_goal_track_conversion.png",
        919,
        361,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]


## Define the Who

You must indicate the target audience for your App Inbox campaign. You can target your app inbox campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 


### Ad-hoc Segment
If you want to create an ad-hoc segment, you can select a type of segment on which to base your App Inbox campaign. You can create the target on the basis of user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered App Inbox campaign).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 


### Deliver Action Based App Inbox Messages
You can trigger an App Inbox message based on an action. Users receive an App Inbox message when they perform an action in the app instead of waiting for the next app launch. This makes the message more contextual and increases conversion. The App Inbox message is not triggered for campaigns with delays.


### Deliver App Inbox Notifications based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via App Inbox as of now.

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send an App Inbox notification to English-speaking female users who live in the United States. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3ef0749-campaigns_user_properties.png",
        "campaigns_user_properties.png",
        516,
        204,
        "#f7f8fc"
      ]
    }
  ]
}
[/block]
The following table explains the various property types:
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
    "5-1": "App fields filters include *App Version*, *Device Make*, *Device Model*, *OS Version*, and CleverTap *SDK Version*. This information is sent by CleverTap's SDK for each device that has your app which means a single user can have multiple devices associated with their user profile.",
    "4-1": "Reachability filters include *Has email address*, *Has phone number*, *Unsubscribed email*, and *Unsubscribed SMS*.",
    "3-1": "User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides.",
    "2-1": "User's coarse location. Filters include *Country*, *Region*, and *City*. CleverTap's SDK can automatically detect this from the user's IP address.",
    "1-1": "Demographics filters include *Age* and *Gender*.",
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

To know more about what segments can be used, see [Segments](doc:segments).

### Constant event property

You can also hold a property constant across the selected events.  For more information, see [Constant Event Property](doc:constant-property).

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a739a68-campaign_control_group_targeting_cap.png",
        "campaign_control_group_targeting_cap.png",
        1107,
        555,
        "#fbfbfd"
      ]
    }
  ]
}
[/block]
### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.




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
This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit delivery of the messages to a specified number.

For triggered campaigns based on live user segments, the users receive a message as they qualify until the total quantity specified has been delivered after which the campaign ends. For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

  * Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.
   
  * Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

  *  It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 
[block:callout]
{
  "type": "success",
  "body": "A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.",
  "title": "Safety Check Example"
}
[/block]

## Define the What

Now, you can set up the *What* which is the App Inbox campaign content where you have four different options:

* [Single Message](https://docs.clevertap.com/docs/create-message-app-inbox#section-single-message)
* [AB Test](https://docs.clevertap.com/docs/create-message-app-inbox#section-a-b-testing)
* [Split Delivery](https://docs.clevertap.com/docs/create-message-app-inbox#section-split-delivery)
* [By User Property](https://docs.clevertap.com/docs/create-message-app-inbox#section-by-user-property)

Click *Go To Editor* to create your message. The message templates display. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a258a9-Editor_What.png",
        "Editor_What.png",
        1188,
        233,
        "#faf5f7"
      ]
    }
  ]
}
[/block]

### App Inbox Templates
You have the following four choices of message templates to create your message:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63a8c31-App_Inbox_templates.png",
        "App_Inbox_templates.png",
        807,
        769,
        "#ece7f0"
      ],
      "border": true
    }
  ]
}
[/block]
#### Simple Message 
A simple message consists of the following elements:
(a) Title.
(b) Message.
(c) Media (optional): jpg, gif, mp4 video, and mp3 formats are supported.
(c) Call to action (optional).

Below is a message template showing an image with a message and a CTA:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3b5c15-Screenshot_2019-01-18_at_6.26.52_PM.png",
        "Screenshot 2019-01-18 at 6.26.52 PM.png",
        585,
        627,
        "#f16782"
      ],
      "caption": "",
      "border": true
    }
  ]
}
[/block]

#### Carousel Message with Content
This is a multi-slide template where you can draft up to five slides containing images with content. The carousel in the user app displays in the form of right and left scrolls. This is a rich template that can be used in situations such as, promoting a list of products or movies that will release this weekend.
[block:callout]
{
  "type": "info",
  "body": "CTAs in carousel messages are click-on-image without provisions for external buttons.",
  "title": "CTAs in Carousel Messages"
}
[/block]
#### Carousel Message without Content
This template is similar to the one right above but without a title text and messages. 

#### Message with Icon
This template is similar to the simple message with the extra ability to include an additional icon placeholder.


### App Inbox Editor

The message builder for *App Inbox* is where you can create a rich message to engage your targeted audience.

Enter your text and message.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18bc49e-App_Inbox_editor_create_message.png",
        "App_Inbox_editor_create_message.png",
        1205,
        2151,
        "#f0eef4"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]

#### Call to Action 
*App Inbox* enables various types of call to action (CTA) to cater to different use cases for the client.

 Choose from one of the following five types (Optional):

  * Click-on-message CTA: This opens a deep link when you click anywhere on the message (text or image or both).
  * Click-on-link CTA: You can add additional, colored links at the bottom of your message to attract the user's attention. 
  * Copy to clipboard CTA: The user can copy text to their clipboard such as, copying discount codes to your products and applying them at the time of checkout.
  * Open URL CTA: The user can open deep links for iOS or Android.
  * Custom key-value pairs CTA: The key-value pairs send back custom data when a user clicks the *App Inbox* button. This data is not visible to the user. This feature is available for apps that use Clevertap Android SDK version 3.6.1 or above and iOS SDK version 3.7.1 or above. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3f0fd39-App_Inbox_editor_call_to_action.png",
        "App_Inbox_editor_call_to_action.png",
        681,
        832,
        "#fafafb"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
#### Message Tags
You can tag an inbox message with one or more comma-separated strings (Optional). 

These tags help you identify the messages inside the user's device. Also, these tags help you classify your messages into different tabs in your app.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19799ac-App_Inbox_editor_message_tags.png",
        "App_Inbox_editor_message_tags.png",
        678,
        309,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Using Message Tags",
  "body": "Message tags are an excellent way to engage your users contextually. For example, some of your app users might be interested in offers while others in news updates. You can have two separate tabs to categorize your inbox messages into those two buckets. Note that it is not compulsory to have tabs.\n\nYou can define the names of the inbox tabs during the configuration of *App Inbox* with your app. The same names should be entered as tags. In case you do not specify any tag, the message will go into the default bucket *All*."
}
[/block]

### Time to Live (TTL)
*App Inbox* campaigns are by design persisted on the user device for a number of days. 

1. You can configure the number of days (or hours) to keep the message on the user's device by setting the *time to live*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbd5393-Campaigns_message_time_to_live.png",
        "Campaigns_message_time_to_live.png",
        710,
        246,
        "#f9f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
The TTL can range from 1 day to 60 days. The default value for TTL is 2 days. You can define the TTL for a maximum of 28 days. The message on the user's device stays there for the specified TTL after which it is automatically removed. You can also have *Infinite TTL* which means the message will never be deleted from the user's device. 
[block:callout]
{
  "type": "warning",
  "title": "Choosing the Right TTL",
  "body": "You should choose a TTL that resonates with the purpose of your campaign. Some messages need to stay on the user's device for a longer period (coupon codes which are valid for a month) while some should last for a day or two (weekend discount offers)."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "How a Message is Accounted For",
  "body": "Each message stored on the CleverTap platform for *App Inbox* is accounted for as a user event."
}
[/block]

### Supported Media Types

The supported media types include:
[block:parameters]
{
  "data": {
    "h-0": "Media Type",
    "h-1": "16:9 Aspect Ratio",
    "h-2": "1:1 Aspect Ratio",
    "0-0": "Image (jpg, png, gif)",
    "0-1": "Yes",
    "0-2": "Yes",
    "h-3": "Max Size",
    "0-3": "500 KB",
    "1-0": "Video (mp4)",
    "1-1": "Yes",
    "1-2": "Yes",
    "2-0": "Audio (mp3)",
    "2-1": "N/A",
    "2-2": "N/A",
    "2-3": "5 MB",
    "1-3": "50 MB"
  },
  "cols": 4,
  "rows": 3
}
[/block]

### Preview & Test

Once you are all done setting up the content of your campaign in *What* section, you have the option to send a test notification to any CleverTap user profile you have marked as a *Test profile* 
Click the **Preview & Test** button from the message editor to test a message.

### Message Types
You can create the following types of messages:

* [Single Message](https://docs.clevertap.com/docs/create-message-app-inbox#section-single-message)
* [AB Test](https://docs.clevertap.com/docs/create-message-app-inbox#section-a-b-testing)
* [Split Delivery](https://docs.clevertap.com/docs/create-message-app-inbox#section-split-delivery)
* [By User Property](https://docs.clevertap.com/docs/create-message-app-inbox#section-by-user-property)

#### Single Message
In this campaign, we send the same message to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.


### A/B Testing
A/B testing helps you understand what type of message copy works best to get clicks from users.

You can test up to three message variants on a test group and the variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.

When you create multiple variants for a campaign, you can also auto-copy what is already present in a current variant.


###Split Delivery
With split delivery, you can decide what percentage of your audience receives each message variant for the duration of the campaign.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/198a9fd-app_inbox_split_delivery.png",
        "app_inbox_split_delivery.png",
        582,
        588,
        "#fafbfb"
      ],
      "border": true
    }
  ]
}
[/block]

#### Split Delivery to Past Behavior Segments
For campaigns sent to *Past Behavior Segments* (grouping of users based on what they have done in the past), you have two options: launch the A/B test to a percentage of your target audience or send out an absolute number of messages. In either case, we deliver the variants equally to the test audience.

For example:
  * If you are testing three messages (e.g., Variant A, Variant B, Variant C).
  * Your campaign reach is 2,000,000 users.
  * You choose a test population of 15% of campaign reach (300,000 users).

Then, we send:
  * Variant A to 100,000 users.
  * Variant B to 100,000 users.
  * Variant C to 100,000 users.

After all 300,000 messages have been delivered, we calculate the winning message over this test group based on the number of click-throughs. We then automatically send the winning message to the remainder of your target audience which is 1,700,000 users in this example.

Note that for A/B testing, we ensure there is always an equal number of messages sent for each variant, so there is no bias introduced during the test phase and that the best-performing message is always declared the winner.

#### Split Delivery to Live User Segments 

With campaigns sent to live user segments (triggered campaigns), messages are delivered immediately when a user’s activity matches the criteria you have selected. For example, you can send a message when the user has completed a booking or purchase. Since it is not possible to determine the reach of triggered campaigns upfront, you need to decide how many total messages to send for A/B testing before a winner is declared.
[block:callout]
{
  "type": "success",
  "body": "If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of clicks and continue only with this winning message for the duration of the campaign.",
  "title": "Triggered Campaign Example"
}
[/block]
Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense of how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no winner will be declared and each message variant will be alternatively delivered for the duration of the campaign.

### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the *Customer Type* user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af26a47-campaigns_user_properties.png",
        "campaigns_user_properties.png",
        516,
        204,
        "#f7f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
## Define the When

You can set up the *When* to schedule the campaign start and end using the options below:

Past behavior campaigns can be scheduled to run at a specific time:

  * Send Now - Send the message after the campaign creation is complete.
  * Schedule for later - On multiple specified dates and times.
  * Set as Recurring - Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:
  * In response to a user event.
  * User event/inaction combination (e.g., abandoned cart scenario).
  * Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

###Delivery preferences
 
Global campaign limits are limits you can apply to determine how many push notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox. <<@vishal somani there are no global campaign limits for app inbox right? >>

You can specify *Do Not Disturb* (DND) hours during which notifications from this App Inbox campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b6e217-Push_notification_editor_when.png",
        "Push_notification_editor_when.png",
        978,
        485,
        "#fbfaf8"
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
  "body": "If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]

## Publish Campaign


After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:
1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b521e92-campaign_Publish.png",
        "campaign_Publish.png",
        1193,
        356,
        "#f0f0fc"
      ],
      "border": true
    }
  ]
}
[/block]