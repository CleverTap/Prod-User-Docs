---
title: Create Message
excerpt: Create a message for your webhook.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Create a New Campaign

Create a campaign to deliver your Webhook. To create a new campaign

1. From the CleverTap dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select **Webhooks**.

<Image align="center" alt="Create a New Webhook Campaign " border={true} caption="Create a New Webhook Campaign" title="Create a New Webhook Campaign" src="https://files.readme.io/6b3a7dc269d3b42bc2f7127119a31cdabf307f4c3413166a50e52bd468691968-google_adds.png" />

<Image align="center" alt={2760} border={true} caption="Webhook Setup" title="Webhook Campaign Configuration" src="https://files.readme.io/cfb9567-Webhook_campaign.png" />

Define all the sections to publish the campaign.

## Start Campaign Setup

The _Start here_ section displays the setup information.

This section has the following parts:

* **Qualification criteria**: Deliver the notification based on Past behavior/Custom list, Live Behavior, or [External Trigger](doc:external-trigger).
* **Webhook**: Select from the available Webhooks. Alternatively, you may create a new webhook.
* **Set a goal**: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve with the campaign. This selection is optional. Define the conversion period by selecting the _Conversion Time_. You can define your conversion goal further by filtering an event by event properties. For more information on event properties, refer to [Events](https://docs.clevertap.com/docs/events).

<Image align="center" alt={919} border={true} caption="Enable Conversion Tracking" title="Enable Goal Conversion Tracking" src="https://files.readme.io/7d83483-Push_notification_set_goal_track_conversion.png" />

## Define the Audience

You need to indicate the target audience for your Webhook campaign. You can target your Webhook campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the _segment_ list.

<Image align="center" alt={2672} border={true} caption="Define the Target Audience" title="Define the Campaign Target Audience" src="https://files.readme.io/7884aa0-webhooks_who.png" />

You can create the target based on past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered Webhook campaigns).

> 🚧 Delay > 24 Hours
>
> We recommend creating a Past Behavior campaign for all campaigns where the delay is greater than 24 hours for a live inaction campaign.

For instance, you can create a live _Inaction within time_ campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on online platforms.

### Deliver Action Based Webhook Notifications

You can trigger a Webhook notification based on an action. Users receive Webhook notifications when they perform a certain action. This makes notifications more contextual and increases conversion. The instant Webhook message is not triggered for campaigns with delays or when the app inbox is coupled with a Webhook message.

### Filter Webhook Notifications based on Past Behavior

You can also target users basis their past behavior. For past behavior campaigns, you also have the option to calculate estimated reach to view:

* Number of users that qualify for the campaign criteria.
* Number of users that are reachable via Webhook.

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can segment your campaign to only reach users who meet specific criteria.

For example, you can send webhook notifications only for female users who live in the United States. The image below represents a sample target segment that is filtered using specific user properties to target the required audience.

<Image align="center" alt={2202} border={true} caption="Target Audience Based on User Properties" title="Filer by User Properties" src="https://files.readme.io/9289ee7-Screenshot_2021-10-26_at_2.53.00_PM.png" />

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups).

<Callout icon="📘" theme="info">
  **Note**

  The control group for Webhook campaigns is enabled only if the **Webhook Delivered** system event is available for your account. To enable the Webhook Delivered event, contact your Customer Success Manager.
</Callout>

<Image align="center" alt="Define Control Group" border={false} caption="Define Control Group" title="Control Group and Target Cap" src="https://files.readme.io/b4eb37d-Control_Group_and_Target_Cap.png" />

### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (_Target Reach_) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

> 📘 Campaign Limit
>
> Ensure that you set up a limit of 100 or more, regardless of the qualified user segment size. If the limit specified is less than 100, an error occurs.

> 📘 Note
>
> The maximum reach for the target segment may be less than the limit specified in Targeting Cap.

## Define the Webhook Content

Now, you can set up the _What_ which is the Webhook campaign content. Click _Go To Editor_ to create your message.

<Image align="center" alt={1048} border={true} caption="Webhook Editor" title="Webhook Editor" src="https://files.readme.io/6dfb26c-Webhook_what_without_options.png" />

### Webhook Editor

From the Webhook Editor:

1. Add query parameters in the URL key-value pairs section.
2. Select the content type (JSON or plain text).
3. Add the webhook content to send or receive the data.

<Image align="center" alt={1425} border={true} caption="Webhook Setup" title="Setup Webhook Content" src="https://files.readme.io/a1faeb5-Webhook_Editor_What.png" />

You can either use _Profile Variables & custom key value pairs_ or _Custom Body_. You have the option to send/receive an email, identity, objectId (CleverTap ID), profileData (custom profile variables), event properties (applicable only for Live behavior), and push_token for each user.

<Image align="center" alt={839} border={true} caption="Define the Webhook Content" title="Create Webhook Content" src="https://files.readme.io/5589ea5-Create_Webhook_Content.png" />

You can also choose a custom payload.

<Image align="center" alt={1672} border={true} caption="Custom Payload in Webhook" title="Configure Custom Payload" src="https://files.readme.io/dead0f2-webhooks_custom_json.png" />

The preview for your payload is displayed on the right side of the pane.

<Image align="center" alt={2832} border={true} caption="Preview Webhook Payload" title="Payload Preview" src="https://files.readme.io/ae38cd3-webhooks_preview.png" />

#### Sample Payload

Following is a sample webhook payload containing all possible fields for profile variables. The `targetId` corresponds to the webhook campaign ID for which you receive the payload.

```json
{
  "targetId": 1659684581,
  "key_values": {
    "SomeKey1": "SomeValue1"
  },
  "profiles": [
    {
      "key_values": {
        "SomeKey1": "SomeValue1"
      },
      "email": "webhook227@gmail.com",
      "identity": "webhook227@gmail.com",
      "all_identities": [
        "webhook227@gmail.com"
      ],
      "objectId": "__Webhook227",
      "phone": "+917872483227",
      "systemProfileData": {
        "webPushSubscription": "Unsubscribed",
        "mobilePushSubscription": "Unsubscribed",
        "emailSubscription": "Subscribed",
        "smsSubscription": "Subscribed",
        "whatsappSubscription": "Subscribed",
        "timezone": "Eastern Standard Time",
        "country": "Unknown",
        "region": "Unknown",
        "city": "Unknown",
        "latitude": 19.16670036315918,
        "longitude": 72.84851837158203,
        "age": "2 years 1 months"
      },
      "profileData": {
        "customer type": "gold",
        "customer id": 11384938,
        "language": “english”,
        "last score": 308,
        "high score": 308,
        "replayed": true,
                "multi": [
          "foo",
          "bar"
        ],
        "ts": 1586937505801
      },
      "name": "Nick",
      "event_properties": {
        "zip-code": "0500",
        "Product Id": 1,
        "test prop 2": 100,
        "prop1": 19.16670036315918,
        "prop2": 72.84851837158203,
        "Make": "random make",
        "Model": "s",
        "SDK Version": 30200,
        "OS Version": "9.1.11111",
        "Version": 6.55,
        "date": "$D_1664890781",
        "ct_sdk_version": 30700,
        "ct_latitude": 19.16670036315918,
        "ct_longitude": 72.84851837158203,
        "ct_os_version": "9.1.11111",
        "ct_app_version": 6.55,
        "CT Source": "Mobile"
      },
      "session_props": {}
    }
  ]
}
```

### Response Formats

The following are the two types of response formats sent by CleverTap when creating a webhook campaign:

#### Broadcast Message:

A message is termed as _Broadcast_ when the following four conditions are met:

* User selects _JSON_ from the _Webhook content format_ dropdown
* User selects _Profile variables& custom key value pairs_ as the message body
* Webhook URL does not include any personalization component
* Key-value pairs do not include any liquid tags. However, the message still qualifies as a broadcast message if the key-value pairs use _@Personalization_.

For broadcast messages, the payload includes an array of profile variables. The following is a sample webhook payload containing all possible fields for profile variables. The `targetId` corresponds to the webhook campaign ID for which you receive the payload.

```json
{
    "targetId": 1472124953,
    "key_values": {
        "PromoCode": "MT50",
        "PowerUser": "true"
    },
    "profiles": [
        {
            "Email": "jack@gmail.com",
            "Identity": "foo",
            "ObjectId": "-g55b74fb1030740e4a4931910a8abb862",
            "ProfileData": {
                "Last Score": 308,
                "High Score": 308,
                "Replayed": true
            },
            "Event_properties": {
                "Score": 1200,
                "Game Mode": "Practice",
                "Rating": 1
            },
            "Push_token": "19403aa5d3bb376769a8101c9cbf22159cb1836117659cc684a71243589982ea"
        },
        {
            "Email": "jill@gmail.com",
            "Identity": "bar",
            "ObjectId": "__g09c9bf3b0d374a259c86f5b855ec9b19",
            "ProfileData": {
                "Last Score": 309,
                "High Score": 309,
                "Replayed": true
            },
            "Event_properties": {
                "Score": 500,
                "Game Mode": "Tournament",
                "Rating": 2
            },
            "Push_token": "fiCjRO_opjw:APA91bH0yzS_eBj1Xx8TcakMzz4yTc3id29A79GOjnaaMtIQLrjztNfzzRz7slqWmNzndECx_hHh7qiL0LZJOkGwzr9Zp_g1mC9B6BVuEbsjrMFoxXX830zMRuvxtU_AhFTC0JPHejZh"
        }
    ]
}
```

#### Non-broadcast Message

The messages other than broadcast messages are termed Non-broadcast messages. The following is a sample webhook payload containing all possible fields for profile variables. The `targetId` corresponds to the webhook campaign ID for which you are receiving the payload.

```json
{
    "targetId": 1472124953,
    "key_values": {
        "PromoCode": "MT50",
        "PowerUser": "true"
    },
    "profiles":
        {
            "Email": "jack@gmail.com",
            "Identity": "foo",
            "ObjectId": "-g55b74fb1030740e4a4931910a8abb862",
            "ProfileData": {
                "Last Score": 308,
                "High Score": 308,
                "Replayed": true
            },
            "Event_properties": {
                "Score": 1200,
                "Game Mode": "Practice",
                "Rating": 1
            },
            "Push_token": "19403aa5d3bb376769a8101c9cbf22159cb1836117659cc684a71243589982ea"
        }
```

## Define the Campaign Schedule

Each webhook campaign needs to be scheduled for a specific timeline. To define the schedule for your webhook campaign, you need to specify the _Start date and time_ and _End date and time_. You also have the option to start a campaign immediately by selecting _Now_.

Besides, you can also define a delay (by seconds, minutes, hours, or days) once a user qualifies for the target segment. Once you define the schedule and click _Done_; the campaign will be triggered and terminated as per the defined timings.

<Image align="center" alt={1886} border={true} caption="Define the Campaign Schedule" title="Define the Campaign Schedule" src="https://files.readme.io/b635c3a-webhook_when.png" />

<Callout icon="📘" theme="info">
  #### First-Day Delivery Behavior

  Recurring campaigns have first-day exceptions:

  - Daily or weekly repeat
    - If you publish before the scheduled send time, the first send is today at the scheduled time. For weekly campaigns, today must be one of the selected days.
    - If you publish after the scheduled send time, today is skipped. A daily campaign first sends the next day. A weekly campaign first sends on the next selected day, which can fall in the following week.
    - The first send is not delayed by the repeat interval. For example, with “Repeat every 2 weeks”, the first send still happens in the first applicable week.
      For example, you publish at 10 AM and schedule the send for 2 PM. The first send is today at 2 PM. If you publish at 3 PM, the first send is tomorrow at 2 PM.

  **Monthly Repeat:**

  Monthly recurring campaigns do not send on the day you publish, even if that day matches the schedule. The first send is the next matching date. This applies to all monthly repeat options.

  - **Day of the month**: You publish amd start a campaign on January 20 and repeat on the 20th. No messages are sent on January 20. The first send is February 20.
  - **Days of the week**: If you publish and start a campaign on Sunday, May 10, 2026, at 10:30 AM and repeat it on the second Sunday, no messages are sent on May 10. The first send is on Sunday, June 14, 2026.
  - **Last Day of the month**: If a campaign is scheduled for Last day of the month and created on June 30, it does not run on June 30. It runs on July 31 only. To also run it on June 30, create it on June 29 or earlier.

  To send on a matching day in the first month, publish the campaign before that day.
</Callout>

### Delivery Preferences

Global frequency caps operate on a per-channel basis and let you specify the message cadence, dwell time between messages, and throttle limits (delivery rates). To control the maximum number of messages users receive for a given channel of communication, select _Global campaign limits_. And, to control the delivery rates for your campaigns, select _Global throttle limits_. For more information about _Global campaign limits_ and _Global throttle limits_, refer to [Messaging Frequency Caps](doc:messaging-frequency-caps).

For both Past Behavior and Live Campaigns, you can also set the _Do Not Disturb_ (DND) hours during which notifications from the campaign are prevented from going out, either by discarding them or delaying delivery until after DND hours are complete, such as 9 PM to 9 AM.

For Past Behavior Campaigns, if you want your campaign to adapt delivery times according to the user’s timezone, check the _Timezone_ checkbox. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

<Image align="center" alt="Delivery Preferences" border={true} caption="Delivery Preferences" src="https://files.readme.io/8180abf-Webhook_Delivery_Preferences.png" />

> 📘 DND Feature Not Supported in Journeys
>
> Webhook currently supports the Do Not Disturb (DND) feature exclusively in Campaigns, not in Journeys.

## Publish Campaign

After previewing the appearance of your overall campaign, finalize your campaign by clicking **Publish Campaign.**

<Image align="center" alt={1193} border={true} caption="Publish the Campaign" title="Publish Campaign" src="https://files.readme.io/b521e92-campaign_Publish.png" />