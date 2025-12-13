---
title: Push Notifications _Campaign redesign_rework_WIP
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
  "title": "Overview"
}
[/block]
Push notifications provide the capability to communicate brief, yet important alerts to your mobile app users. CleverTap’s rich segmentation and powerful infrastructure lets you send time-sensitive, relevant, and personalized push messages on a large scale.

The *Push* module on the CleverTap dashboard under *Campaigns* makes it easy to set up push campaigns for all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. 

Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users clicked on them, and how many users converted as a result.

Push notifications display in the notification tray or the notification inbox of the user as displayed below.
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
# Create a Push Campaign

This section covers how to create a push campaign.

## Create a New Campaign

To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **Push Notifications**. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a0b23d-1_Campaign_creation.png",
        "1 Campaign creation.png",
        1579,
        501,
        "#f7f9f9"
      ],
      "border": true
    }
  ]
}
[/block]
The push notification campaign page displays. There is no specific order to defining the campaign. After all the sections have been defined, you can publish the campaign. 

## Set up the campaign

This section displays the setup information.  To make edits to the settings, click the **Go to Setup** link.  

The setup section has three parts:
* Setup:  Displays the information for the integrated platforms such as FCM, Xiaomi, or iOS.
* Delivery type: Deliver the notification by time, event, or API.
* Goal: Setup conversion tracking.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe9a905-1_Select_a_channel.png",
        "1 Select a channel.png",
        1095,
        784,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
## Define the Who

You must indicate the target audience for your push campaign. You can target your push campaign to a new user segment by clicking on the **Target segment** section. Here you can create a new segment or use a previously saved user segment from the *Segments* list.
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
If you want to create an ad-hoc segment, you can select a type of segment on which to base your push campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered push campaigns).


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bf6652-3_Who_Select.png",
        "3 Who Select.png",
        1613,
        809,
        "#fbfbfb"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on our iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Campaign reach*. 

###Deliver Action Based Push Notifications Instantly
You can trigger a push message instantly for an action. Users receive push notifications instantly when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant push message is not triggered for campaigns with delays or when the app inbox is coupled with a push message.

You can also filter users their past user behavior or user properties. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via mobile push as of now.
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

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send a push notification to English female users who live in the United States. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c53ebf-4_Display_common_properties.png",
        "4 Display common properties.png",
        1014,
        292,
        "#fbfbfb"
      ],
      "border": true
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
        "https://files.readme.io/a5d0afc-Deliver_to_a_Subset_of_the_Target_Audience.png",
        "Deliver_to_a_Subset_of_the_Target_Audience.png",
        1416,
        709,
        "#fbfbfb"
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

###Constant event property

You can also hold a property constant across the selected event. 

### Limits and Control Group

You can define the control group to measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups) ].


## Define the What

Now, you can set up the *What* which is the push campaign content where you have three different options.

### Single Message Campaign
In this campaign, we send the same message to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### A/B Testing
A/B testing helps you understand what type of message copy works best to get clicks from users.

You can test up to three message variants on a test group and the variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.

When you create multiple variants for a campaign, you can also auto-copy what is already present in a current variant.
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

###Split Delivery
With split delivery, you can decide what percentage of your audience receives each message variant for the duration of the campaign.




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0da75d0-5_Split_Delivery_percentages.png",
        "5 Split Delivery percentages.png",
        1614,
        471,
        "#f6f8f9"
      ],
      "border": true
    }
  ]
}
[/block]

### Multi-message Campaign

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the *Customer Type* user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f93952b-6_Multi-message_Campaign.png",
        "6 Multi-message Campaign.png",
        1611,
        696,
        "#f4f5f7"
      ],
      "border": true
    }
  ]
}
[/block]

### Advanced Settings
####Sound File (iOS)
You have to specify the name of the sound file which is included in your app bundle. Apple supports .aiff, .caf and .wav extensions. 

####Badge Count (iOS)
This updates the badge count for your app to the one specified while creating the campaign. Please note that this does not increment the badge count or set the value to 0 (zero) to hide the badge number. This should be handled manually at the application level.

####Category (iOS)
You can input the name of the category while creating the campaign. Each category has to be registered with the app. Each such category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it, although the number of actions actually displayed depends on the type of notification delivered. This provides users the ability to take multiple actions for the notification. 
[block:callout]
{
  "type": "success",
  "body": "A single media push notification can have two buttons such as, *Buy Now* and *Save for Later*.",
  "title": "Multiple Buttons Example"
}
[/block]

####Content Available (iOS)
If you include the content-available key with a value of 1 to send out a silent notification to your users. It will not alert the user in any way (update badge count/play a sound/show a notification), but it will wake your app up in the background so you can fetch new content and prepare it for the next time the user opens your app.

Key: content-available
Value: 1


####Deep Link/Open URL
Deep links allow you to land the user to a particular part of your app. Your app’s OpenURL method is called with the deep link specified here. If you want to use external URLs, then you have to whitelist the IPs or provide http/https before the URL so they can be handled properly by the SDK.

####Mutable Content
Check this box if you would like to send the mutable-content flag along with your payload. This invokes your app’s notification service extension. For more information, refer to [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications) in the Apple documentation.



####Campaigns Sent to Past Behavior Segments
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

### Live User Segment (Triggered) Campaigns

With campaigns sent to live user segments (triggered) campaigns, messages are delivered immediately when a user’s activity matches the criteria you have selected. For example, you can send a message when the user has completed a booking or purchase. Since it is not possible to determine the reach of triggered campaigns upfront, you need to decide how many total messages to send for A/B testing before a winner is declared.
[block:callout]
{
  "type": "success",
  "body": "If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of clicks and continue only with this winning message for the duration of the campaign.",
  "title": "Triggered Campaign Example"
}
[/block]
Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense for how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no winner will be declared and each message variant will be alternatively delivered for the duration of the campaign.


### Personalization for All Campaign Types

You can personalize the push notification title and message body for every user based on specific user property or event property values. For more information on user profile properties and events (dynamic replacements), refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles).

To invoke the personalization menu, type the @ symbol in the title or the text fields while typing out the push notification message.

You can include emojis in your push notifications as you would in a regular text. You can use the CleverTap emoji picker or copy-paste emojis from an emoji keyboard online.

You can also add dynamic replacements in the push title and body. Notice a preview of the available push notification as displayed below.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/734a4e2-7_At_sign_Personalization_for_All_Campaign_Types.png",
        "7 At sign Personalization for All Campaign Types.png",
        1610,
        669,
        "#f4f5f8"
      ],
      "border": true
    }
  ]
}
[/block]
You can add emojis using CleverTap’s built-in emoji picker by clicking on the smiley face icon.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/802a229-8_emoji_picker.png",
        "8 emoji picker.png",
        1617,
        781,
        "#f4f4f6"
      ],
      "border": true
    }
  ]
}
[/block]
In the *Advanced* section, you can add rich media such as, images/image carousels, GIFs, and even videos using publicly-hosted media URLs. A preview displays on the right-hand side as you add your media. 

### Rich Push Notifications 

You can add a fixed (or with dynamic replacements) URL for Android (Image only) and iOS (Image and video) for push notifications.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5280fff-8_rich_media.png",
        "8 rich media.png",
        1600,
        803,
        "#f0f1f4"
      ],
      "border": true
    }
  ]
}
[/block]
You can add an image carousel with each image having its own caption, sub caption, and call to action URL (fixed or with dynamic replacements) to your iOS push notifications.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/267d64e-8_original_carousel.png",
        "8 original carousel.png",
        1264,
        778,
        "#f2f3f6"
      ],
      "border": true
    }
  ]
}
[/block]
You can add default or custom (fixed or with dynamic replacements) sound files to your Android and iOS push notifications.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fefadab-9_sound_files.png",
        "9 sound files.png",
        1374,
        785,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
You can add deep links (fixed or with dynamic replacements) to the overall Android or iOS push notification so users can access specific screens within the app upon clicking.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/34c97b3-10_Deep_links.png",
        "10 Deep links.png",
        1202,
        712,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
To replace an existing notification with the same collapse key, you can use the collapse notification option. For example, if push 1 and push 2 have a collapse key A, the push 1 notification is present on the mobile device and now, push 2 notification is received on the device. The push 1 notification will no longer be visible (it will be collapsed) and push 2 will be displayed. The collapse key must be added under the collapse notification field.

###Raising Push Impression Event 

You can raise and record push notifications delivered to your users’ Android devices.

1. Navigate to *Settings* > *Schema* > *Events*.
2. Search for *Push Impressions*, then click on the vertical ellipsis.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ebf8ae7-Push_Impression_event_FAQ.png",
        "Push Impression event FAQ.png",
        1161,
        454,
        "#f7f7f9"
      ]
    }
  ]
}
[/block]
3. Click on **Setup push impressions**. A new window displays.
4. Turn on the *Mobile Push* toggle. 
5. Click on **Save** to enable the option.

After the toggle is on, all the push notifications delivered are recorded under the *Push Impressions* event. The viewed and conversion count from this event is also available under *Analytics* > *Events*.


[block:callout]
{
  "type": "warning",
  "body": "Some things to consider include:\n1. The push event can only be raised for CleverTap SDK version 3.5.1 and above for Android and version 3.5.0 and above for iOS.\n2. If the notification channel is incorrect, the push notification is not delivered on the device and therefore, no event is raised for the push impression.",
  "title": "SDK Considerations"
}
[/block]
### Raising Notification Viewed Event for iOS
To raise the *Notification Viewed* event for iOS, it is mandatory to enable the *Mutable Content* under the iOS section of the campaign creation.

For more information on how to enable *Notification Viewed* for your account, refer to our [developer documentation](https://developer.clevertap.com/docs). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4c0f519-11_Raising_Notification_Viewed_Event_for_iOS.png",
        "11 Raising Notification Viewed Event for iOS.png",
        1200,
        476,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
### Add Custom Actions to Android Notifications

A simple way to urge users to respond to your calls to action is by adding button-like actions right into your Android push notifications. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb95d80-12_Add_Custom_Actions_to_Android_Notifications.png",
        "12 Add Custom Actions to Android Notifications.png",
        1552,
        758,
        "#edeff2"
      ],
      "border": true
    }
  ]
}
[/block]
Once set up, the various calls to action would display below the push as displayed below.
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

####Maximum Priority
Use for urgent, time-sensitive notifications. These notifications will get higher placement inside the user’s tray and display as heads-up notifications.

####High Priority
Use for important communications that require extra attention such as chat messages. These will also display as heads-up notifications and be given a higher priority in the user’s tray.

####Default Priority
Use for the majority of your messages that are not time-sensitive such as general notifications and promotional offers.

####Setting Priority for Notifications with CleverTap
You can set these priority levels from the CleverTap dashboard as you create your Android push campaigns.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f32e106-Setting_Priority_for_Notifications_with_CleverTap.png",
        "Setting Priority for Notifications with CleverTap.png",
        276,
        77,
        "#eeeef1"
      ],
      "border": true
    }
  ]
}
[/block]
Have your app running our latest SDK (versions v3.1.4 or higher) and follow the steps outlined above to send actionable push notifications and set notification priority on Android devices.


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
For more information on using tags, refer to [Liquid Tags](doc:liquid-tags).

### Linked Content

Linked content provides the ability to personalize emails with rich and contextual data available outside of the CleverTap platform. With linked content, you can send messages with send-time personalization.

For example, you deliver food across different geographies and you want to personalize offers to each user based on the weather and on their location. The location can come from CleverTap personalization and the weather information can come from an API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

For more information, refer to [Linked Content](https://docs.clevertap.com/docs/linked-content#write-linked-content).

## Define the When

You can set up the *When* to schedule the campaign start and end using the options below:

Past behavior campaigns can be scheduled to run:
  * On a specific date and time.
  * On multiple specified dates and times.
  * Recurring at a periodicity you set.

Live campaigns can be set up as follows:
  * In response to a user event.
  * User event/inaction combination (e.g., abandoned cart scenario).
  * Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).
 
Global campaign limits are limits you can apply to determine how many push notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox.

You can also click on the *Advanced* checkbox to specify *Do Not Disturb* (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/efa3b27-3_When_section.png",
        "3 When section.png",
        1610,
        808,
        "#fafbfc"
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

Once you are all done setting up the content of your campaign in *What*, you have the option to send a test push notification to any CleverTap user profile you have marked as a *Test profile*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9893ffd-Push_Notifications_-_Test_and_Schedule_Campaign_1.png",
        "Push Notifications - Test and Schedule Campaign 1.png",
        454,
        242,
        "#f0f3fb"
      ],
      "border": true
    }
  ]
}
[/block]
After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:
1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de7e8eb-Push_Notifications_-_Test_and_Schedule_Campaign_2.png",
        "Push Notifications - Test and Schedule Campaign 2.png",
        195,
        69,
        "#a1b4f6"
      ],
      "border": true
    }
  ]
}
[/block]
# Push Campaign Throttling

You can throttle the rate at which CleverTap delivers push notifications under *Settings* > *Setup* > *Campaign Limits*. If your user base is large and all users receive and click on a push notification at roughly the same time to open the app, you could experience a significant, unwanted load on your systems.

By using push campaign throttling, you can meter how quickly CleverTap delivers your notifications.
[block:callout]
{
  "type": "success",
  "title": "Push Campaign Throttling Example",
  "body": "If your reachable audience for a campaign is 500,000 users and your back-end systems can only support up to 20% of them, you can set a throttle limit to 100,000 notifications per 15-minute interval. The entire campaign will then deliver in 1 hour 15 minutes."
}
[/block]

# View Push Campaign Stats
Once the campaign has gone out, you can view its stats by going into *Push* under *Campaigns* on the CleverTap dashboard and clicking on the campaign of interest to view its deliveries, clicks, and conversions.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb78487-1_Viewing_Push_Campaign_Stats_dashboard.png",
        "1 Viewing Push Campaign Stats dashboard.png",
        1579,
        508,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]
Under the *Sent Conversions* card, you can track the following stats for push notification campaigns:

  * Sent: Number of deliveries attempted on devices.
  * Errors: Number of errors for the campaign. These errors can be both technical errors such as FCM related errors or non-technical errors such as messages frequency exceeded.
 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42fac73-2_Sent_Conversions.png",
        "2 Sent Conversions.png",
        1571,
        729,
        "#edf6fb"
      ]
    }
  ]
}
[/block]
Under the *Impressions* card, you can track the following stats for push notification campaigns:
* Impressions: Number of views generated for a Push or Facebook campaign.
* Uplift: Click to get details of uplift achieved by Push Amplification and sending to App inbox.
* OS Distribution: The impressions by the OS, such as iOS or Android.


Under the *Clicked* card, you can track the following stats for push notification campaigns:

 * Clicked: Number of clicks generated by the campaign.
 * CTR: The clickthrough rate of the campaign. It is measured by dividing the total number of clicks by the total number of impressions or viewed.  
 * Uplift: Click to get details of uplift achieved by Push Amplification and sending to App inbox.

Under the *Converted users* card, you can also track the following:
It displays the number of users that converted after receiving the campaign. 
* View through: The users who converted after viewing the notification. View through conversions are measured by *Users who converted after viewing / Users who were sent the notification*.
* Click through: The users who converted after clicking the notification. Click through conversions are measured by *Users who converted after clicking / Users who were sent the notification*.

Under the *Control group* card, you can track the following stats for push notification campaigns:

The number of users considered in the control group for the campaign.


##Single Message Campaign

Below is a stats example of a single message campaign report:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c65cd37-4_Single_Message_Campaign.png",
        "4 Single Message Campaign.png",
        1606,
        778,
        "#f3f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
##A/B Testing

Following is a stats example of an A/B testing campaign report:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d483859-Campaign_Stats.png",
        "Campaign_Stats.png",
        1432,
        655,
        "#eaeaed"
      ],
      "border": true
    }
  ]
}
[/block]
The table will display results by the variants. The stats include *Sent*, *Viewed*, *Clicked*, *CTR*, and *Errors*, according to the channel.

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
  "body": "If your settings require you to add a notification channel ID, the list of valid channels will be available in campaign creation.",
  "title": "Notification Channel ID for Android 8.0 and Above"
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
  "title": "Optimize Delivery"
}
[/block]
You can optimize push delivery with push implication and sending to app inbox. 

##Optimize with Push Amplification

Push notifications are a great way to engage customers despite the issue of low deliverability on certain device manufacturers. In addition, more and more users choose to opt-out of push notifications.

With push amplification at your disposal, you can counter this challenge by enhancing the delivery of push notifications to devices that missed receiving it.

To enable this feature, navigate to *Settings* > *Engage* > *Setup* > *Push Amplification*. Turn on the push amplification toggle as displayed below:
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
  "title": "Toggling Push Notification Amplification",
  "body": "Once you turn on push amplification, all the push campaigns created will be amplified from that moment onward and this applies the same way when you turn it off."
}
[/block]
Once push amplification is turned on, your campaigns reach more users through your push notifications. You can check these boost numbers on your push campaign stats page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65a05d4-Push_amplification_report.png",
        "Push amplification report.png",
        1580,
        476,
        "#f8f9f9"
      ]
    }
  ]
}
[/block]
Push amplification can be achieved via retrying the *Push* message as is (where messages are suppressed by the device) and *App Inbox* where the user has chosen to DND the push messages.
[block:callout]
{
  "type": "info",
  "title": "Support for Push Amplification via Inbox",
  "body": "We support *Push Amplification via Inbox* and retrying push notifications due to delivery issues with certain OEMs. \n\nIf the app is online when *Push* is delivered, the Inbox delivery is done on the next *App Launch* and not immediately after the *Push* is delivered."
}
[/block]
##Optimize with App Inbox

Apart from push amplification, you can further increase delivery of push notification by sending a copy of the same message to *App Inbox*. 

To send a copy of the push message to **App Inbox**, click the checkbox that appears at the bottom of the message builder of push notification in the *What* section.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/777a4b6-New_1.png",
        "New 1.png",
        1318,
        623,
        "#ededed"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "*App Inbox* also exists as a stand-alone channel. For more information, refer to [App Inbox](https://docs.clevertap.com/docs/app-inbox).",
  "title": "App Inbox as its Own Channel"
}
[/block]
  From this screen, you can do the following:
* You can customize the same push message for *App Inbox*. 
  * You can change the title color, message color, background color, and also add filter tags that classify your message into tabs. For more information, refer to [Message Tags](https://docs.clevertap.com/docs/app-inbox#section-message-tags). 
  * You can set a time to live (TTL) for *App Inbox* message in the setup section. For more information on setting up TTL, refer to [Time to Live](https://docs.clevertap.com/docs/app-inbox#section-time-to-live).

##Push Amplification and App Inbox Stats
You can view the stats for push messages copied to *App Inbox* on the *Push stats* page. The percentage boost represents the percentage of messages boosted by *App Inbox* as compared to the total of messages sent via *App Inbox* and *Push Amplification*.

To view the stats for the copied messages, you can use the tab *App Inbox stats*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1401bf8-Push_amplification_report_for_App_Inbox.png",
        "Push amplification report for App Inbox.png",
        1580,
        476,
        "#f8f9f9"
      ],
      "border": true
    }
  ]
}
[/block]