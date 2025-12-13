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

Create a campaign to deliver your message using mParticle. To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **mParticle**. 

<Image title="1 Plus campaign mParticle.png" alt={1579} className="border" border={true} src="https://files.readme.io/9a65b1a-1_Plus_campaign_mParticle.png" />

The campaign page displays.

<Image title="2 Main dashboard.png" alt={1616} className="border" width="80%" border={true} src="https://files.readme.io/6a7fee3-2_Main_dashboard.png" />

After all the sections have been defined, you can publish the campaign. 

## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:

* Start here:  Displays the information whether the mParticle account has been set up or not.
* Qualification criteria: Deliver the notification by Past Behavior, [Custom List](doc:custom-list-segments), or Live Behavior. \<DOCS NOTE: ADD HYPERLINKS FOR 'PAST BEHAVIOR' AND 'LIVE BEHAVIOR' LATER.>

![1575](https://files.readme.io/d1f7940-3_Start_here.png "3 Start here.png")

## Define the Who

You must indicate the target audience for your mParticle campaign. You can target your mParticle campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 

<Image title="SMS_Who.png" alt={961} className="border" border={true} src="https://files.readme.io/86fa2f2-SMS_Who.png" />

### Ad-hoc Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your mParticle campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered mParticle campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 

### Deliver Action Based mParticle Notifications

You can trigger an mParticle message based on an action. Users receive mParticle notifications when they perform an action in the app instead of waiting for the next app launch. This makes the message more contextual and increases conversion. The mParticle message is not triggered for campaigns with delays.

### Deliver mParticle Notifications based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via a message as of now.

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send an mParticle notification to English-speaking female users who live in the United States. 

<Image title="campaigns_user_properties.png" alt={516} className="border" border={true} src="https://files.readme.io/f866484-campaigns_user_properties.png" />

#### User Properties

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

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups]\(doc:control-groups.

![1107](https://files.readme.io/5ff0139-campaign_control_group_targeting_cap.png "campaign_control_group_targeting_cap.png")

### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

![406](https://files.readme.io/3aa9241-subset_image.png "subset_image.png")

This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit the delivery of the messages to a specified number.

For triggered campaigns based on live user segments, the users receive a message as they qualify until the total quantity specified has been delivered after which the campaign ends. For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

* Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.

* Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

* Prevent sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 

> 👍 Safety Check Example
>
> A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.

## Define the What

Now, to set up the *What* for the mParticle campaign content, perform the following steps:

1. Click **Go To Editor**. 

![1326](https://files.readme.io/688b77d-5_The_What.png "5 The What.png")

2. Select the *User Profiles Attributes* and/or GCM/APNS Tokens, if required.
3. Enter your key-value pair.
4. Click **Done**.

![1427](https://files.readme.io/0a186e2-6_mParticle_Content.png "6 mParticle Content.png")

## Define the When

You can set up the *When* for the campaign delivery to now, later, or as a recurring date. 

Past behavior campaigns can be scheduled to run at a specific time:

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:

* In response to a user event.
* User event/inaction combination (e.g., abandoned cart scenario).
* Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

![978](https://files.readme.io/ea2a1f5-Push_notification_editor_when.png "Push_notification_editor_when.png")

### Delivery preferences

You can also click the *Advanced* checkbox to specify *Do Not Disturb* (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them or delaying delivery after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

<Image title="amazon_eventbridge_delivery_preference.png" alt={936} className="border" border={true} src="https://files.readme.io/7f552c4-amazon_eventbridge_delivery_preference.png" />

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.

<Image title="8 Publish campaign.png" alt={1324} className="border" border={true} src="https://files.readme.io/0b0acad-8_Publish_campaign.png" />
