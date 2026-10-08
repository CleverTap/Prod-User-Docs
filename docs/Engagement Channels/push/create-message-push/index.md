---
title: Create Message
excerpt: Learn how to create a Push campaign using the CleverTap dashboard.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Create a New Push Campaign

Create a campaign to deliver your push message.<br />To create a new campaign:

1. From the dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select the **Push Notifications**.


<Image src="https://files.readme.io/48bb98ae84998635a4cc9830f29b22511a1f1055aad20f4001af18327258d115-Select_the_Push_Campaign.png" alt="1360" align="center" width="80%" caption="Select Messaging Channel" border={true} />


The Push Notification campaign page displays.


<Image src="https://files.readme.io/a805f56-Campaign_Creation_Page.jpg" alt="1404" align="center" width="80%" caption="Create Campaign" border={true} />


4. Define all the sections and publish the campaign.

## Start Campaign Setup

The _Start here_ section displays the setup information.

This section has the following parts:

- **Integrated Platforms**:  Displays the information on platforms such as FCM, Xiaomi, or iOS. Check that the required platforms are integrated and ready for campaigns.
- **Qualification criteria**: Delivers the notification by Past behavior /Custom list, Live behavior, or [External trigger](doc:external-trigger-1). For more information about segmenting users, refer to [Segments](https://docs.clevertap.com/docs/segments).
- **Set a goal**: Tracks your campaign conversions by setting a goal. This step is optional, but it helps you measure how effectively your campaign meets its goal.<br />You can define your conversion goal by selecting the **Event** and specifying the **Conversion Time**. The _Conversion Time_ field accepts any numeric value along with a time unit such as Minutes, Hours, Days, Weeks, or Months. This allows you to define conversion windows such as 10 days, 72 hours, or 2 months. The value can range from a minimum of 1 minute to a maximum of 5 months.<br />For example, if you set the conversion time to 5 Minutes, the system counts conversions within 5 minutes of the goal event.<br />Your campaign goal can be as broad or as specific as you want. For example, you can answer questions such as: _How many users were influenced to purchase an X amount?_ or _How many first-time visitors purchased red shoes worth at least X and blue jackets worth at least Y?_


<Image src="https://files.readme.io/d960f90056d978b5c9f8832e66c2b3c15b6e387d3caa38ea6bc0b138c57d6b29-Conversion_Tracking.png" alt="Set Conversion Time" align="center" width="75% " caption="Set Conversion Time" border={true} />


## Define the Audience-Who

You must indicate the target audience for your campaign from the _Who_ section. You can specify your target audience from the _Target segment_ section. You can create a new segment or use a previously saved user segment from the _segment_ list.

For Past Behavior segments, you also calculate the estimated reach.


<Image src="https://files.readme.io/030202d-Push_notification_editor_Who.png" alt="1168" align="center" width="80%" caption="Define Target Segment - Who" border={true} />


### Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your campaign. You can create the target based on past user behavior and user properties or live (ongoing) user behavior. The latter is helpful to send out real-time, triggered campaigns.

<Callout icon="🚧" theme="warn">
  #### Live Campaigns with Delay > 24 Hours

  - Live campaigns support delays greater than 24 hours, as follows:
    - Scheduling: Messages are sent after the configured delay.
    - **Per-event triggering**: One message is sent per qualifying event occurrence.
    - **Event personalization**: Trigger event properties are available in message content, including via Linked Content.
    - **Message frequency**: If the trigger event occurs frequently, configure limits under Delivery Preferences to control how many messages a user receives.
  - **Constant Event Property**: If the campaign uses Constant Event Property personalization with a delay greater than 24 hours, default values are sent.
  - **Delay calculation**: The delay is counted from each user's trigger event, not from the campaign's go-live date. Users who performed the trigger event before the campaign went live are also eligible and will receive the message once their delay period elapses.

  For more information, refer to​ [Event Personalization by Campaign Type.](https://staging.docs.user.clevertap.net/docs/personalize-message-all#event-personalization-by-campaign-type)
</Callout>

For instance, you can create a live _Inaction within time_ campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes; that is the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the _Who_ by sending this campaign to all users who qualify or limit the users who qualify under _Estimated reach_.

### Deliver Action-Based Messages

You can trigger a message based on an action. Users receive messages when they perform an action in the app instead of waiting for the next app launch. It makes the messages more contextual and increases conversion. Campaigns with delays and app inbox coupled with a push message do not trigger instant messages.

### Deliver Messages based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach. The estimated reach shows the number of users that qualify for the campaign criteria and the number of reachable users via mobile push.

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can segment your campaign to reach users who meet specific criteria.

For example, you can send a push notification to English-speaking female users who live in the United States.


<Image src="https://files.readme.io/cbc719c-user_properties_all.png" alt="486" align="center" caption="Filter by User Properties" border={true} />


The following table explains the various property types:

| Property Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Example                                                                   |
| :--------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------ |
| User Properties  | Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Customer Type = Platinum                                                  |
| Demographics     | Demographics filters include _Age_ and _Gender_.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Age = 25 to 40 years<br />Gender = Female                                 |
| Geography        | User's coarse location. Filters include _Country_, _Region_, and _City_. CleverTap's SDK can automatically detect this from the user's IP address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Country = United States<br />State = California<br />City = San Francisco |
| Geography Radius | User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Locations = San Francisco, USA; Paris, France                             |
| Reachability     | <li> _MSG-push_: Indicates that the user has enabled push notification from the application. Works in combination with the DDND Flag.</li>  <li> _MSG-sms_: When set to true, it indicates that the user has subscribed to SMS notifications. When set to false, it indicates that the user does not want to receive SMS notifications.</li> <li> _MSG-email_: When set to true, it indicates that the user has subscribed to Email notifications. When set to false, it indicates that the user does not want to receive email notifications.</li> <li> _MSG-whatsapp_: When set to true, it indicates that the user has subscribed to WhatsApp notifications. When set to false, it indicates that the user does not want to receive WhatsApp notifications. </li>For more information about each of these flags, refer to communication preferences listed under the [Manually Updating Predefined User Profile Properties]() section. |                                                                           |
| App Fields       | App fields filters include _App Version_, _Device Make_, _Device Model_, _OS Version_, and CleverTap _SDK Version_. This information is sent by CleverTap's SDK for each device that has your app which means a single user can have multiple devices associated with their user profile.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | OS Version = 10                                                           |

To know more about what segments can be used, see [Segments](doc:segments).

### Constant event property

This is an advanced feature that allows you to hold a property constant across the selected events. For more information, refer to [Constant Event Property](doc:constant-property).

### Calculate Estimated Reach

The Estimated Reach option allows you to preview how many users meet your targeting criteria in an online trigger campaign before publishing it. This helps you validate audience size and adjust filters to ensure the campaign reaches the intended users.

Estimated Reach is particularly useful when you select the _Filter on past behavior and user properties_ option. You can view both the estimated user count and device count.

To calculate the estimated reach, perform the steps below:

1. Select **Filter on past behavior and user properties**.
2. Click **Calculate** in the right panel. The result shows the estimated number of users or devices for that segment. You can view the following:
   - **Total Users**: The number of users that match the filters.
   - **Breakdown by Platform and Devices**: The users count on Android, iOS, or both, and on different devices.
   - **Visual Indicator**: A chart summarizing the share by operating system.<br />The estimate, based on the latest available event data, updates each time you apply or modify filters. It reflects stored event data and is not a real-time count. This helps you plan and refine your audience before sending the campaign.


<Image src="https://files.readme.io/cd0a9385b9c0efa8d0ff7d6a5af9fc000b5b164910dfadb31c9ae6565670e23b-2026-01-30_19-12-06_1.gif" align="center" width="85% " caption="Calculate Estimate Reach" border={true} />


<Callout icon="📘" theme="info">
  ### Estimated Reach vs. Actual Qualified Count

  When creating a campaign with the Send to All Devices option enabled, the Estimated Reach shown before publishing the campaign may differ slightly from the actual qualified user count after the campaign is published.

  This occurs because the estimate is calculated using an optimized approach that evaluates only a limited number of devices per user. As a result, inactive or outdated devices (for example, devices without valid push tokens) may be included in the estimate.

  During actual campaign execution, only valid and reachable devices are considered. This ensures that all eligible users are targeted, and in some cases, the final qualified count may be slightly higher than the estimate.

  The difference is typically small and depends on factors such as:

  - Number of devices associated with each user
  - Presence of inactive or historical devices
  - Campaign constraints (for example, limits or dwell time)

  Estimated Reach should be used as an approximate indicator of campaign size and not as an exact user count. This discrepancy does not impact campaign delivery, and all eligible users and devices are correctly targeted when the campaign is sent.
</Callout>

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups).


<Image src="https://files.readme.io/c730cf7-Control_Group_and_Target_Cap.png" alt="Control Group" align="center" caption="Control Group" border={true} />


### Targeting Cap

You can limit the number of users receiving the message.

A relevant use case is a limited offer where you want to distribute a fixed number of coupon codes. If the total reach for your campaign exceeds the number of coupon codes you can distribute, then you can limit the number of users who will receive the message to precisely the number of coupons you want to distribute.

<Callout icon="🚧" theme="warn">
  ### Campaign Limit

  - Ensure that you set a limit of at least 100, regardless of the qualified user segment size.
  - For Past Behavior A/B Test campaigns, CleverTap recommends setting the _Send campaign to at most_ value slightly above the _Variant distribution_ percentage. Click **Calculate** to find the estimated reach of the campaign and adjust the value accordingly. For example:<br />Qualified users = 2000<br />Variant distribution = 10%<br />Calculated users for the variant = 200<br />Recommended cap: Slightly above the _Calculate users for the variant_ value (for example, 210)<br />This ensures the campaign limit accounts for the A/B Test sample size, enabling the declaration of a winner without the campaign getting stuck.
</Callout>


<Image src="https://files.readme.io/5fdf9fb-Control_Campaign_Reach.png" alt="Target Cap in Campaign" align="center" caption="Target Cap in Campaign" border={true} />


## Define Message Content- What

You can have up to four variations of message content in the _What_ section:

### Message Types

You can create the following types of messages for your notification:

- Single Message
- AB Test
- Split Delivery
- By User Property

### Single Message

This message type allows a single message copy to be set up for the entire audience. This message copy can be [personalized](https://docs.clevertap.com/docs/personalize-message-all) for each qualifying user. This message type is best suited for use cases where the message doesn’t vary much based on user properties such as language, geography, and so on.

### A/B Testing

A/B testing helps you understand what type of message copy works best to get clicks from users.

You can test up to three message variants on a test group, and the variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.

When creating multiple variants for a campaign, you can also auto-copy what is already present in a current variant.


<Image src="https://files.readme.io/4d99162-AB_Test_all.png" alt="881" align="center" caption="A/B Test  Variant Distribution" border={true} />


#### A/B Testing for Past Behavior Segments

For campaigns sent to _Past Behavior Segments_ (grouping of users based on what they have done in the past), you have two options: launch the A/B test to a percentage of your target audience or send out an absolute number of messages. In either case, we deliver the variants equally to the test audience.

For example:

- If you test three messages (Variant A, Variant B, Variant C).
- Your campaign reach is 2,000,000 users.
- Your test population is 15% of the campaign reach (300,000 users).

Then, we send:

- Variant A to 100,000 users.
- Variant B to 100,000 users.
- Variant C to 100,000 users.

After delivering 300,000 messages, we calculate the winning message over this test group based on the number of click-throughs. In this example, we then automatically send the winning message to the remainder of your target audience, which is 1,700,000 users.

Note that for A/B testing, we ensure there is always an equal number of messages sent for each variant, so there is no bias introduced during the test phase and that the best-performing message is always declared the winner.

#### A/B Testing for Live User Segments

With campaigns sent to live user segments (triggered campaigns), messages are delivered immediately when a user’s activity matches your selected criteria. For example, you can send a message when the user has completed a booking or purchase. Because it is impossible to determine the reach of triggered campaigns upfront, you need to decide how many total messages to send for A/B testing before a winner is declared.

<Callout icon="👍" theme="okay">
  ### Triggered Campaign Example

  If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of clicks and continue only with this winning message for the duration of the campaign.
</Callout>

Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages sent for similar triggered campaigns in the past to get a sense of how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. Suppose your test group size exceeds the total number of users who ultimately qualify for that campaign. In that case, no winner will be declared, and each message variant will be alternatively delivered for the campaign's duration.

### Split Delivery

For some campaigns, you want to send multiple variants of a message to your entire target audience without selecting a winner. With split delivery, you choose what percentage of your target audience receives each variant and we deliver them accordingly. After the campaign is completed, navigate to the campaign stats to compare how each message performed.


<Image src="https://files.readme.io/890fc40-Push_notification_split_delivery.png" alt="Screen shows split Delivery Variant Distribution and message preview" align="center" caption="Split Delivery Variant Distribution" border={true} />


You can add up to three message variants when creating a campaign. You specify the percentage of your audience that will receive each variant. The messages are delivered in the specified proportions throughout the campaign.

For example:

If you have a campaign reach of 2,000,000 users and you want to test three variants (A, B, and C) with equal distribution, you might set it up as follows:

- Variant A: 33.33% (approximately 666,667 users)
- Variant B: 33.33% (approximately 666,667 users)
- Variant C: 33.33% (approximately 666,667 users)

After the campaign is completed, you can analyze the performance of each variant.

### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be sending a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value.


<Image src="https://files.readme.io/4abd93d-Message_Variant_by_User_Property.png" alt="2780" align="center" caption="Message Variant by User Property" border={true} />


In the example below, we have used the _Customer Type_ user property so users with different customer type property values receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).


<Image src="https://files.readme.io/3f61b2f-2022-12-22_10-15-38.png" alt="2532" align="center" caption="Message by Customer Type" border={true} />


## Define Campaign Schedule- When

You can set up the _When_ section to schedule the campaign start and end using the options below:

Past behavior campaigns can be scheduled to run:

- On a specific date and time.
- On multiple specified dates and times.
- Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:

- In response to a user event.
- User event/inaction combination (e.g., abandoned cart scenario).
- Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

### Delivery preferences

You can apply global campaign limits to determine how many push notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the _Don’t apply global campaign limits to this campaign_ checkbox.

You can also click the _Advanced_ checkbox to specify _Do Not Disturb_ (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them or delaying delivery after DND hours such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).


<Image src="https://files.readme.io/60373b1-PBS_Delivery_Preferences.png" alt="2214" align="center" caption="Message Delivery Preference" border={true} />


<Callout icon="📘" theme="info">
  ### Recurring Day

  If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.
</Callout>

#### Time to Live

**Time to Live** is the notification's persistence sent to an end user. Push services such as FCM, APNS, XPS, Baidu, and HMS manage Time to Live. They regulate the time the system monitors user device status to deliver a push notification. Whenever the user is online during the set TTL period, the notification is delivered. Any user not coming online will not receive the push notification, and no notifications are attempted after the TTL period is over.

There are two ways to configure the TTL for push notification delivery. Conceptually, they are referred to as _Relative TTL_ or _Absolute TTL_.

- Relative TTL: Push services attempt to send the notification only for the duration mentioned here. Specify the _duration_ you want the notification to live.<br />Select the first option to specify a TTL duration and ensure a push notification is active until the user is online if unavailable and there are no hard time limits.
- Absolute TTL: Push services send the notification only _until the specified time_ here. State the time until when you want the notification to live.<br />Select the second option to specify a TTL time limit to ensure a push notification is active until the specified date and time.


<Image src="https://files.readme.io/d69dc51-TTL.png" alt="832" align="center" caption="Time to Live for a Message" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  Absolute TTL is available only for the following campaign types:

  - Send Now
  - Schedule for later except recurring schedules and _Best time for every user_.

  Absolute TTL is not available if global throttle limits are applied.

  Relative TTL is available for all campaign types.
</Callout>

##### Use Cases

| Industry Type and Target Group                                                                                                  | Need                                                                                                                          | Don't Need                                                                  | TTL Selection                                                                                                                                                                                 |
| :------------------------------------------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A ride-sharing app running campaigns to target office-goers in the morning.                                                     | They want the push notification to be sent to office goers during the morning peak hours, ideally between 7:30 and 10:30 a.m. | Notification should not be sent in the afternoon as it loses the relevance. | They would keep the campaign scheduled time at 7:30 a.m. and set the **_relative_** TTL for 3 hours. This would ensure that the notification is sent between 7:30 a.m. and 10:30 a.m.         |
| A cricket information app wants to provide latest updates to their users' regarding the cricket match/es scheduled for the day. | They want to send a push notification to their users advising on the coin toss of a particular match scheduled at 7pm.        | Notification should not be sent after 7:10 pm as it is no more relevant.    | Campaign will be triggered at 7 pm and the **_absolute_** TTL will be set to 7:10 pm. Any user who comes online after 7:10 pm will not get the notification even if they qualified initially. |

## Cut-off

The campaign cut-off time sets a daily boundary for message delivery, stopping notifications after that time each day the campaign runs. Select the _Cut-off_ checkbox and specify a time to stop sending notifications when the target audience is large enough to cause a significant delay in processing the user queue. This is useful when the campaign is time-sensitive, and a later delivery would make the notification irrelevant.&#x20;


<Image src="https://files.readme.io/5048266-Cut_Off.png" alt="456" align="center" width="smart" caption="Campaign Cut-Off Time" border={true} />


#### Use Case

| Industry Type and Target Group                                                                          | Need                                                                            | Don't Need                                                                  | Usage Scenario                                                                |
| :------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------ | :-------------------------------------------------------------------------- | :---------------------------------------------------------------------------- |
| An ECommerce app has around 10 million users and is running a 'Discount' sale offer that ends at 12 am. | They want to send the push notification to all of their users at the same time. | Notifications should not be sent after 12 am, as they would lose relevance. | Assuming the user queue processing takes 10 mins, set the cutoff to 11:50 pm. |

However, it is important to note that the cut-off setting does not stop the campaign permanently if there are notifications left to dispatch. If notifications cannot be delivered before the cut-off time (due to throttling or queue backlogs), they will be sent after midnight the next day, provided they are still eligible for delivery.

For example, if a campaign is configured with a Throttle limit (100 messages/minute) and a Cut-off time of 9:00 PM, CleverTap stops sending notifications to the push services after 9:00 PM that day. Specifically:

- Message delivery pauses at 9:00 PM.
- Any unsent notifications in the queue resume delivery at midnight, the following day.

<Callout icon="📘" theme="info">
  ### Tip

  To prevent undelivered messages from being sent the next day, combine the cut-off setting with a DND window or restrict the campaign's end date and time.

  For example, an ECommerce app above sets a cut-off of 11:50 PM, but the user queue takes longer than expected and messages remain undelivered at 12:00 AM. With cut-off alone, those messages would resume at midnight the following day, well past the sale, when they are no longer relevant. By also setting the campaign end date and time to 12:00 AM, the leftover messages are suppressed instead of being sent later.
</Callout>

## Preview & Test

Once you are all done setting up the content of your campaign in the _What_ section, you have the option to send a test push notification to any CleverTap user profile you have marked as a _Test profile_. You can also send a test message to your internal audience with personalized values. For more information, refer to [Preview & Test](doc:send-test-personalization).<br />Click the **Preview & Test** button from the message editor to test a message.

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.


<Image src="https://files.readme.io/b521e92-campaign_Publish.png" alt="1193" align="center" caption="Publish Campaign" border={true} />


Explore our [Push Notification: Best Practices](https://clevertap.com/blog/push-notification-best-practices/) blog for actionable insights on crafting compelling push notifications.

Check out our [Creative Push Notifications](https://clevertap.com/blog/creative-push-notifications/) guide for ideas that go beyond the basics and drive engagement.
