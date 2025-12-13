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

Create a campaign to deliver your Web Popup message. To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **Web Popup**. 

<Image title="campaign_all_channels.png" alt={1195} className="border" border={true} src="https://files.readme.io/7963bf1-campaign_all_channels.png" />

The campaign page displays.

<Image title="Web_pop_up_Editor_main.png" alt={1100} className="border" width="80%" border={true} src="https://files.readme.io/4bf6219-Web_pop_up_Editor_main.png" />

After all the sections have been defined, you can publish the campaign. 

## Start Campaign

The *Start here* section displays the setup information. 

* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve in the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to \*How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ". 

Create focused conversions using event properties.  For more information on event properties, see [Events]\(doc: events). 

Define the conversion period by selecting the *Funnel Conversion Time*. 

<Image title="Push_notification_set_goal_track_conversion.png" alt={919} className="border" border={true} src="https://files.readme.io/4fbbeb2-Push_notification_set_goal_track_conversion.png" />

## Define the Who

You must indicate the target audience for your Web Popup campaign. You can target your Web Popup campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 

<Image title="campaign_Who_Live_segment.png" alt={964} className="border" border={true} src="https://files.readme.io/a92d833-campaign_Who_Live_segment.png" />

Campaigns can be set up as follows:

* Single action: User does an action on one of your web pages.
* Page visit: User visits one of your specific webpage URLs.
* Page referral: User visits your website via an external ad referral URL.
* Page count: Number of your web pages a user has visited so far in their session.

### Ad-hoc Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your Web Popup campaign. You can create the target on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered Web Popup campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 

### Deliver Action Based Web Popup Notifications

You can trigger a Web Popup message based on an action. Users receive Web Popup notifications when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. 

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send a Web Popup notification to English-speaking female users who live in the United States. 

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

Now, you can set up the *What* which is the Web Popup campaign content.

 Click *Go To Editor* to create your message. 

![1048](https://files.readme.io/8a73e71-Webhook_what_without_options.png "Webhook_what_without_options.png")

The *Create Web Popup Message* window displays.

### Web Popup Templates

Select the required template. 

![941](https://files.readme.io/e927af1-Web_pop_up_templates.png "Web_pop_up_templates.png")

You can use the built-in editor to type your message title and body or use our custom HTML editor to paste your own custom HTML templates. 

With our built-in web pop-up campaign creator, you can customize the look of your web pop-up: 

1. Choose a web pop-up from one of the following layouts: *Box*, *Banner*, or *Interstitial*. 
2. Specify whether to show on: *Desktop*, *Tablet*, or *Mobile*.
3. Select a pop-up background color, text color, and pop-up position.
4. Specify a pop-up icon by choosing from our default icon images or provide your own publicly hosted icon URL.
5. Use the checkboxes to select the look with rounded corners and whether to show a close icon.

### Web Popup Editor

The web popup notification text fields shown below can be personalized for every user based on specific user property or event property values. For more information, refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles).

Enter all the required information. 

<Image title="Web_pop_up_editor_create_message.png" alt={933} className="border" width="80%" border={true} src="https://files.readme.io/62a7961-Web_pop_up_editor_create_message.png" />

* Deep Link: Specify a deep link, so that upon a web popup click, the user is taken back to one of your specific webpages, such as the checkout page. With dynamic replacements, you can take the user right back to the webpage of the product they just added to their cart and present them with an incentive to encourage the transaction. 
  * Image Link: Specify an image link. You can specify a publicly hosted image URL, such as a product they just added to their cart. You can add from a list of default web popup notification icons. 
  * Icon: Specify an icon or select the checkbox *Don't use icon* if you do not need to use one.
  * Time To Live: Select a time for the web popup notification to remain viewable to users, prevent notification dismissal unless interacted with by the user, and even include a call to action link within the notification.
  * Custom key-value pairs: Add any key-value pairs. 

> 🚧 Browser Considerations
>
> Some of the optional items only apply to a certain browser, such as Firefox, Chrome, or KaiOS.

### Preview & Test

Once you are all done setting up the content of your campaign in the *What* section, you have the option to send a test notification to any CleverTap user profile you have marked as a *Test profile*.\
Click the **Preview & Test** button from the message editor to test a message.

### Message Types

You can create the following types of messages:

* [Single Message](https://docs.clevertap.com/docs/create-message-web-popup#section-single-message)
* [By User Property](https://docs.clevertap.com/docs/create-message-web-popup#section-by-user-property)

### Single Message

In this campaign, we send the same message to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the *Customer Type* user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).

<Image title="campaigns_user_properties.png" alt={516} className="border" border={true} src="https://files.readme.io/7dbd024-campaigns_user_properties.png" />

## Define the When

You can set up the *When* to schedule the campaign's start and end.

Past behavior campaigns can be scheduled to run at a specific time:

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:

* In response to a user event.
* User event/inaction combination (e.g., abandoned cart scenario).
* Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

### Delivery preferences

Global campaign limits are limits you can apply to determine how many popup notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox.

You can also specify *Do Not Disturb* (DND) hours during which notifications from this popup campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

<Image title="campaign_when_PBS.png" alt={1196} className="border" border={true} src="https://files.readme.io/a1f9337-campaign_when_PBS.png" />

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.

<Image title="campaign_Publish.png" alt={1193} className="border" border={true} src="https://files.readme.io/b521e92-campaign_Publish.png" />
