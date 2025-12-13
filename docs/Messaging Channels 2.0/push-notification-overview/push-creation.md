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
## Create a New Campaign

Create a campaign to deliver your push message. To create a new campaign, perform the following:

1. From the dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **Push Notifications**. 

<Image title="campaign_all_channels.png" alt={1195} className="border" width="80%" border={true} src="https://files.readme.io/7963bf1-campaign_all_channels.png" />

The campaign page displays.

<Image title="Push_notification_editor_main.png" alt={1176} className="border" width="80%" border={true} src="https://files.readme.io/0bdaa08-Push_notification_editor_main.png" />

After all the sections have been defined, you can publish the campaign. 

## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:

* Start here:  Displays the information for platforms such as FCM, Xiaomi, or iOS. Check that the required platforms are integrated and ready for campaigns. 
* Qualification criteria: Deliver the notification by [Past Behavior](https://docs.clevertap.com/docs/push-creation#section-deliver-push-notifications-based-on-past-behavior-pbs), [Custom List](doc:custom-list-segments), [Live behavior](https://docs.clevertap.com/docs/push-creation#section-deliver-action-based-push-notifications), or API. 
* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve in the campaign. This selection is optional.
* Select App: If you have multiple apps, select the app for running this campaign. 

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to \*How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ". 

Create focused conversions using event properties.  For more information on event properties, see [Events](doc:events). 

Define the conversion period by selecting the *Funnel Conversion Time*. 

<Image title="Push_notification_set_goal_track_conversion.png" alt={919} className="border" border={true} src="https://files.readme.io/4fbbeb2-Push_notification_set_goal_track_conversion.png" />

## Define the Who

You must indicate the target audience for your push campaign. You can target your push campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 

<Image title="Push_notification_editor_Who.png" alt={1168} className="border" border={true} src="https://files.readme.io/030202d-Push_notification_editor_Who.png" />

### Ad-hoc Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your push campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered push campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 

### Deliver Action Based Push Notifications

You can trigger a push message based on an action. Users receive push notifications when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant push message is not triggered for campaigns with delays or when the app inbox is coupled with a push message.

### Deliver Push Notifications based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via mobile push as of now.

![223](https://files.readme.io/91a9aa3-image11.png "image11.png")

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send a push notification to English-speaking female users who live in the United States. 

<Image title="campaigns_user_properties.png" alt={516} className="border" border={true} src="https://files.readme.io/f8e66b4-campaigns_user_properties.png" />

The following table explains the various property types:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Property Type
      </th>

      <th>
        Description
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        User Properties
      </td>

      <td>
        Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.
      </td>

      <td>
        Customer Type = Platinum
      </td>
    </tr>

    <tr>
      <td>
        Demographics
      </td>

      <td>
        Demographics filters include *Age* and *Gender*.
      </td>

      <td>
        Age = 25 to 40 years\
        Gender = Female
      </td>
    </tr>

    <tr>
      <td>
        Geography
      </td>

      <td>
        User's coarse location. Filters include *Country*, *Region*, and *City*. CleverTap's SDK can automatically detect this from the user's IP address.
      </td>

      <td>
        Country = United States\
        State = California\
        City = San Francisco
      </td>
    </tr>

    <tr>
      <td>
        Geography Radius
      </td>

      <td>
        User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides.
      </td>

      <td>
        Locations = San Francisco, USA; Paris, France
      </td>
    </tr>

    <tr>
      <td>
        Reachability
      </td>

      <td>
        Reachability filters include *Has email address*, *Has phone number*, *Unsubscribed email*, and *Unsubscribed SMS*.
      </td>

      <td>
        Unsubscribed email = No
      </td>
    </tr>

    <tr>
      <td>
        App Fields
      </td>

      <td>
        App fields filters include *App Version*, *Device Make*, *Device Model*, *OS Version*, and CleverTap *SDK Version*. This information is sent by CleverTap's SDK for each device that has your app which means a single user can have multiple devices associated with their user profile.
      </td>

      <td>
        OS Version = 10
      </td>
    </tr>
  </tbody>
</Table>

To know more about what segments can be used, see [Segments](doc:segments).

### Constant event property

You can also hold a property constant across the selected events.  For more information, see [Constant Event Property](doc:constant-property).

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups]\(doc:control-groups.

![933](https://files.readme.io/0eacc15-Control_Group_Editor.png "Control_Group_Editor.png")

### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

![406](https://files.readme.io/3aa9241-subset_image.png "subset_image.png")

This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit delivery of the messages to a specified number.

For triggered campaigns based on live user segments, the users receive a message as they qualify until the total quantity specified has been delivered after which the campaign ends. For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

* Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.

* Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

* Prevent sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 

> 👍 Example
>
> A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.

## Define the What

Now, you can set up the *What* which is the push campaign content where you have four different options:

* [Single Message](https://docs.clevertap.com/docs/push-creation#section-single-message)
* [AB Test](https://docs.clevertap.com/docs/push-creation#section-a-b-testing)
* [Split Delivery](https://docs.clevertap.com/docs/push-creation#section-split-delivery)
* [By User Property](https://docs.clevertap.com/docs/push-creation#section-by-user-property)

Click *Go To Editor* to create your message. 

![1188](https://files.readme.io/d51dd1a-Editor_What.png "Editor_What.png")

### Push Editor

The Push Editor allows you to create and edit beautiful and timely messages for your push campaign. From the *What* section, click *Go To Editor* to create your message. This section displays the editor to create your push message. You can see various options that will help you create a contextual and timely message. 

#### Sound File (iOS)

You have to specify the name of the sound file which is included in your app bundle. Apple supports .aiff, .caf and .wav extensions. 

#### Badge Count (iOS)

This updates the badge count for your app to the one specified while creating the campaign. Please note that this does not increment the badge count or set the value to 0 (zero) to hide the badge number. This should be handled manually at the application level.

#### Category (iOS)

You can input the name of the category while creating the campaign. Each category has to be registered with the app. Each such category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it, although the number of actions actually displayed depends on the type of notification delivered. This provides users the ability to take multiple actions for the notification. 

> 👍 Multiple Buttons Example
>
> A single media push notification can have two buttons such as, *Buy Now* and *Save for Later*.

#### Content Available (iOS)

If you include the content-available key with a value of 1 to send out a silent notification to your users. It will not alert the user in any way (update badge count/play a sound/show a notification), but it will wake your app up in the background so you can fetch new content and prepare it for the next time the user opens your app.

Key: content-available\
Value: 1

#### Deep Link/Open URL

Deep links allow you to land the user to a particular part of your app. Your app’s OpenURL method is called with the deep link specified here. If you want to use external URLs, then you have to whitelist the IPs or provide http/https before the URL so they can be handled properly by the SDK.

#### Mutable Content

Check this box if you would like to send the mutable-content flag along with your payload. This invokes your app’s notification service extension. For more information, refer to [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications) in the Apple documentation.

### Rich Push Notifications

You can add a fixed (or with dynamic replacements) URL for Android (Image only) and iOS (Image and video) for push notifications.

![1274](https://files.readme.io/eeec895-Push_notification_image_URL_Android.png "Push_notification_image_URL_Android.png")

You can add an image carousel with each image having its own caption, sub caption, and call to action URL (fixed or with dynamic replacements) to your iOS push notifications.

<Image title="Push_notification_ios_advanced_editor.png" alt={1294} className="border" width="80%" border={true} src="https://files.readme.io/b0bb0ab-Push_notification_ios_advanced_editor.png" />

You can add default or custom (fixed or with dynamic replacements) sound files to your Android and iOS push notifications.

You can add deep links (fixed or with dynamic replacements) to the overall Android or iOS push notification so users can access specific screens within the app upon clicking.

To replace an existing notification with the same collapse key, you can use the collapse notification option. For example, if push 1 and push 2 have a collapse key A, the push 1 notification is present on the mobile device and now, push 2 notification is received on the device. The push 1 notification will no longer be visible (it will be collapsed) and push 2 will be displayed. The collapse key must be added under the collapse notification field.

### Add Custom Actions to Android Notifications

A simple way to urge users to respond to your calls to action is by adding button-like actions right into your Android push notifications. 

<Image title="Push_notification_android_action_button.png" alt={1307} className="border" width="80%" border={true} src="https://files.readme.io/630d0b1-Push_notification_android_action_button.png" />

Once set up, the various calls to action would display below the push as displayed below.

![223](https://files.readme.io/7933e01-imagetest.png "imagetest.png")

On Android, you can also set a priority level for each notification to influence how prominently it gets displayed. The higher the priority, the more noticeable it will be.

#### Maximum Priority

Use for urgent, time-sensitive notifications. These notifications will get higher placement inside the user’s tray and display as heads-up notifications.

#### High Priority

Use for important communications that require extra attention such as chat messages. These will also display as heads-up notifications and be given a higher priority in the user’s tray.

#### Default Priority

Use for the majority of your messages that are not time-sensitive such as general notifications and promotional offers.

#### Setting Priority for Notifications with CleverTap

You can set these priority levels from the CleverTap dashboard as you create your Android push campaigns.

<Image title="campaign_Android_notification_tray_priority.png" alt={687} className="border" border={true} src="https://files.readme.io/bc0cf2e-campaign_Android_notification_tray_priority.png" />

Have your app running our latest SDK (versions v3.1.4 or higher) and follow the steps outlined above to send actionable push notifications and set notification priority on Android devices.

### Preview & Test

Once you are all done setting up the content of your campaign in *What* section, you have the option to send a test push notification to any CleverTap user profile you have marked as a *Test profile* .\
Click the **Preview & Test** button from the message editor to test a message.

<Image title="Campaigns_Previews_Test.png" alt={995} className="border" border={true} src="https://files.readme.io/1604478-Campaigns_Previews_Test.png" />

### Message Types

You can create the following types of messages:

* [Single Message](https://docs.clevertap.com/docs/push-creation#section-single-message)
* [AB Test](https://docs.clevertap.com/docs/push-creation#section-a-b-testing)
* [Split Delivery](https://docs.clevertap.com/docs/push-creation#section-split-delivery)
* [By User Property](https://docs.clevertap.com/docs/push-creation#section-by-user-property)

### Single Message

In this campaign, we send the same message to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### A/B Testing

A/B testing helps you understand what type of message copy works best to get clicks from users.

You can test up to three message variants on a test group and the variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.

When you create multiple variants for a campaign, you can also auto-copy what is already present in a current variant.

![223](https://files.readme.io/9469a2e-imagetest.png "imagetest.png")

### Split Delivery

With split delivery, you can decide what percentage of your audience receives each message variant for the duration of the campaign.

<Image title="Push_notification_split_delivery.png" alt={992} className="border" border={true} src="https://files.readme.io/890fc40-Push_notification_split_delivery.png" />

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

> 👍 Triggered Campaign Example
>
> If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of clicks and continue only with this winning message for the duration of the campaign.

Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense of how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no winner will be declared and each message variant will be alternatively delivered for the duration of the campaign.

### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the *Customer Type* user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).

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

### Delivery preferences

Global campaign limits are limits you can apply to determine how many push notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox.

You can also click the *Advanced* checkbox to specify *Do Not Disturb* (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them or delaying delivery after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

<Image title="Push_notification_editor_when.png" alt={978} className="border" border={true} src="https://files.readme.io/5e3de30-Push_notification_editor_when.png" />

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.

<Image title="campaign_Publish.png" alt={1193} className="border" border={true} src="https://files.readme.io/b521e92-campaign_Publish.png" />
