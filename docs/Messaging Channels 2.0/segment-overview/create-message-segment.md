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

Create a campaign to export your CleverTap data. You can create either a Past Behavior Segment export or an Action export.

You can use all the capabilities of the campaign like scheduling it for later, recurring, and so on. to leverage the power of sending your CleverTap data into Segment. To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **Segment** . 

<Image title="campaign_all_channels.png" alt={1195} className="border" border={true} src="https://files.readme.io/7963bf1-campaign_all_channels.png" />

The campaign page displays.

<Image title="Segment_Campaign_main.png" alt={1151} className="border" width="80%" border={true} src="https://files.readme.io/8323eb6-Segment_Campaign_main.png" />

After all the sections have been defined, you can publish the campaign. 

## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:

* Start here: Check that the required platforms are integrated and ready for campaigns. 
* Qualification criteria: Deliver the notification by [Past Behavior](https://docs.clevertap.com/docs/push-campaign#section-whatsapp-based-on-past-behavior-pbs), [Custom List](doc:custom-list-segments), or [events](https://docs.clevertap.com/docs/push-campaign#section-deliver-action-based-push-notifications). 
* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve with the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to \*How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ". 

Click the *Filter* link to create more focused conversions using event properties.  For more information on event properties, see [Events](doc:events) ]. 

Define the conversion period by selecting the *Funnel Conversion Time*.  

![919](https://files.readme.io/89c1404-Push_notification_set_goal_track_conversion.png "Push_notification_set_goal_track_conversion.png")

## Define the Who

You must indicate the target audience for your Segment campaign. You can target your Segment campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 

<Image title="Push_notification_editor_Who.png" alt={1168} className="border" border={true} src="https://files.readme.io/d9c8455-Push_notification_editor_Who.png" />

### Ad-hoc Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your Segment campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered Segment campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 

### Deliver Action Based Segment Notifications

You can trigger a Segment message based on an action. Users receive Segmentnotifications when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant Segment export is not triggered for campaigns with delays. 

### Deliver Segment Notifications based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via Segment as of now.

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send a Segment export for English-speaking female users who live in the United States. 

<Image title="campaigns_user_properties.png" alt={516} className="border" border={true} src="https://files.readme.io/1eb5bd6-campaigns_user_properties.png" />

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

![933](https://files.readme.io/b79e920-Control_Group_Editor.png "Control_Group_Editor.png")

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

> 👍 Safety Check Example
>
> A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.

## Define the What

Now, you can set up the *What* which is the Segment campaign content where you have four different options. Click *Go To Editor* to create your message. 

![1165](https://files.readme.io/ba60761-campaign_what_single_message.png "campaign_what_single_message.png")

### Segment Editor

Select the details to send in the payload, such as Email, Identity & CleverTap ID, User profile attributes, GCM / APNS tokens.

You can also use custom key-value pairs to send custom data.

<Image title="Segment_Editor.png" alt={1252} className="border" border={true} src="https://files.readme.io/b63cef3-Segment_Editor.png" />

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

![978](https://files.readme.io/ed19319-Push_notification_editor_when.png "Push_notification_editor_when.png")

### Delivery preferences

Global campaign limits are limits you can apply to determine the number of segment exports. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox.

You can also specify *Do Not Disturb* (DND) hours during which notifications from this Segment campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

<Image title="amazon_eventbridge_delivery_preference.png" alt={936} className="border" border={true} src="https://files.readme.io/e8e7226-amazon_eventbridge_delivery_preference.png" />

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.

<Image title="campaign_Publish.png" alt={1193} className="border" border={true} src="https://files.readme.io/b521e92-campaign_Publish.png" />
