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

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **SMS**. 

<Image title="campaign_all_channels.png" alt={1195} className="border" border={true} src="https://files.readme.io/7963bf1-campaign_all_channels.png" />

The campaign page displays.

<Image title="SMS_Editor_main.png" alt={1107} className="border" width="80%" border={true} src="https://files.readme.io/3afb28a-SMS_Editor_main.png" />

After all the sections have been defined, you can publish the campaign. 

## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:

* Start here:  Displays the information for platforms such as FCM, Xiaomi, or iOS. Check that the required platforms are integrated and ready for campaigns. 
* Qualification criteria: Deliver the notification by [Past Behavior](https://docs.clevertap.com/docs/push-campaign#section-deliver-push-notifications-based-on-past-behavior-pbs), [Custom List](doc:custom-list-segments), [events](https://docs.clevertap.com/docs/push-campaign#section-deliver-action-based-push-notifications), or API. 
* SMS Service Provider: Select a provider or a provider group.
* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve with the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to \*How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ". 

Click the *Filter* link to create more focused conversions using event properties.  For more information on event properties, see [Events](doc:events) ]. 

Define the conversion period by selecting the *Funnel Conversion Time*.  

<Image title="Push_notification_set_goal_track_conversion.png" alt={919} className="border" border={true} src="https://files.readme.io/6001c3f-Push_notification_set_goal_track_conversion.png" />

## Define the Who

You must indicate the target audience for your push campaign. You can target your push campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 

<Image title="SMS_Who.png" alt={961} className="border" border={true} src="https://files.readme.io/074ff4c-SMS_Who.png" />

### Ad-hoc Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your push campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered push campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 

### Deliver Action Based SMS

You can trigger a push message based on an action. Users receive SMS when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant push message is not triggered for campaigns with delays or when the app inbox is coupled with a push message.

### Deliver SMS based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via SMS as of now.

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

![516](https://files.readme.io/7995f3b-campaigns_user_properties.png "campaigns_user_properties.png")

For example, you can send an SMS to English-speaking female users who live in the United States. 

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

![1107](https://files.readme.io/a739a68-campaign_control_group_targeting_cap.png "campaign_control_group_targeting_cap.png")

### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

![406](https://files.readme.io/3aa9241-subset_image.png "subset_image.png")

This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit delivery of the messages to a specified number.

For triggered campaigns based on live user segments, the users receive a message as they qualify until the total quantity specified has been delivered after which the campaign ends. For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

* Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.

* Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

* It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 

> 👍 Safety Check Example
>
> A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.

## Define the What

Now, you can set up the *What* which is the SMS campaign content.

 Click *Go To Editor* to create your message. 

![1048](https://files.readme.io/e241760-Webhook_what_without_options.png "Webhook_what_without_options.png")

The Create SMS Notification window displays. 

![851](https://files.readme.io/29c4894-SMS_Editor_What.png "SMS_Editor_What.png")

This section of the campaign creation flow will be dependent upon the SMS provider selected for the campaign.

### Out-of-the-box Providers

All SMS service providers are listed on the **Personalization Setup** page, including Msg91, Nexmo, Twilio, Exotel, and Netcore). The connection with these providers is configured by default and the mandatory input required for these providers is the message.

### Preview & Test

Once you are all done setting up the content of your campaign in *What* section, you have the option to send a test notification to any CleverTap user profile you have marked as a *Test profile*\
Click the **Preview & Test** button from the message editor to test a message.

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

<Image title="Push_notification_editor_when.png" alt={978} className="border" border={true} src="https://files.readme.io/8ca1af6-Push_notification_editor_when.png" />

### Delivery preferences

Global campaign limits are limits you can apply to determine how many SMS notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox. 

You can also specify *Do Not Disturb* (DND) hours during which notifications from this SMS campaign are prevented from going out, either by discarding them or delaying delivery after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

<Image title="SMS_delivery_preferences.png" alt={838} className="border" border={true} src="https://files.readme.io/be4fee7-SMS_delivery_preferences.png" />

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

## Publish Campaign

Once you are all done setting up the content of your campaign in *What*, you have the option to send a test SMS notification to any CleverTap user profile you have marked as a *Test profile* \<\<@vishal, where do we see this testing option?>>.

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.

<Image title="campaign_Publish.png" alt={1193} className="border" border={true} src="https://files.readme.io/b521e92-campaign_Publish.png" />
