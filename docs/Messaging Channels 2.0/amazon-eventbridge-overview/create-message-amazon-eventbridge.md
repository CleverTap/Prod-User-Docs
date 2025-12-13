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
[block:api-header]
{
  "title": "Create a New Campaign"
}
[/block]
Create a campaign to deliver your Amazon EventBridge message. To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **Amazon EventBridge **. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7963bf1-campaign_all_channels.png",
        "campaign_all_channels.png",
        1195,
        1249,
        "#f6f7f9"
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
        "https://files.readme.io/9fde14f-Whatsapp_Editor_main.png",
        "Whatsapp_Editor_main.png",
        1132,
        1444,
        "#fbfafb"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
After all the sections have been defined, you can publish the campaign. 


## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:
* Start here: Check that the required platforms are integrated and ready for campaigns. 
* Qualification criteria: Deliver the notification by [Past Behavior](https://docs.clevertap.com/docs/push-campaign#section-whatsapp-based-on-past-behavior-pbs), [Custom List](doc:custom-list-segments), [events](https://docs.clevertap.com/docs/push-campaign#section-deliver-action-based-push-notifications). 
* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve with the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to *How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ". 

Click the *Filter* link to create more focused conversions using event properties.  For more information on event properties, see [Events](doc:events) ]. 

Define the conversion period by selecting the *Funnel Conversion Time*.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32d63db-Push_notification_set_goal_track_conversion.png",
        "Push_notification_set_goal_track_conversion.png",
        919,
        361,
        "#fafafc"
      ]
    }
  ]
}
[/block]
## Define the Who

You must indicate the target audience for your Amazon EventBridge campaign. You can target your Amazon EventBridge campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9c8455-Push_notification_editor_Who.png",
        "Push_notification_editor_Who.png",
        1168,
        771,
        "#f8f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
### Ad-hoc Segment
If you want to create an ad-hoc segment, you can select a type of segment on which to base your Amazon EventBridge campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered Amazon EventBridge campaigns).


For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 


### Deliver Action Based Amazon EventBridge Notifications
You can trigger an Amazon EventBridge message based on an action. Users receive Amazon EventBridge notifications when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant Amazon EventBridge message is not triggered for campaigns with delays or when the app inbox is coupled with an Amazon EventBridge message.

### Deliver Amazon EventBridge Notifications based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via Amazon EventBridge as of now.
[block:image]
{
  "images": [
    {
      "image": [],
      "border": true
    }
  ]
}
[/block]

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send an Amazon EventBridge notification to English-speaking female users who live in the United States. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eee565b-campaigns_user_properties.png",
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


### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b79e920-Control_Group_Editor.png",
        "Control_Group_Editor.png",
        933,
        549,
        "#fbfbfc"
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

  * Prevent sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 
[block:callout]
{
  "type": "success",
  "body": "A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.",
  "title": "Safety Check Example"
}
[/block]
## Define the What

Now, you can set up the *What* which is the Amazon EventBridge campaign content where you have four different options. Click *Go To Editor* to create your message.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2f8d628-campaign_what_single_message.png",
        "campaign_what_single_message.png",
        1165,
        178,
        "#f9f2f5"
      ]
    }
  ]
}
[/block]
### Amazon EventBridge Editor 

Select the details to send in the payload, such as Email, Identity & CleverTap ID, User profile attributes, GCM / APNS tokens.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d199531-amazon_eventbridge_editor_create_messge.png",
        "amazon_eventbridge_editor_create_messge.png",
        989,
        638,
        "#c8c4d2"
      ],
      "border": true
    }
  ]
}
[/block]


## Define the When

You can set up the *When* to schedule the campaign start and end using the options below:

Past behavior campaigns can be scheduled to run at a specific time:

  * On a specific date and time.
  * On multiple specified dates and times.
  * Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:
  * In response to a user event.
  * User event/inaction combination (e.g., abandoned cart scenario).
  * Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed19319-Push_notification_editor_when.png",
        "Push_notification_editor_when.png",
        978,
        485,
        "#fbfaf8"
      ]
    }
  ]
}
[/block]
###Delivery preferences
 
Global campaign limits are limits you can apply to determine how many Amazon EventBridge notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox.

You can also specify *Do Not Disturb* (DND) hours during which notifications from this Amazon EventBridge campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e8e7226-amazon_eventbridge_delivery_preference.png",
        "amazon_eventbridge_delivery_preference.png",
        936,
        397,
        "#fbfbfd"
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