---
title: Create Message
excerpt: Learn how to create a Web Push campaign using the CleverTap dashboard
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

Create a campaign to deliver your Web Push message. To create a new campaign:

1. From the dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select **Web Push**.


<Image src="https://files.readme.io/ecc3c479d66bf81738ef728eb1fb137bc82793123188a2627b398a3394c0981d-wepuchs.png" alt="Select Messaging Channel" align="center" caption="Select Messaging Channel" border={true} />


The campaign page displays.


<Image src="https://files.readme.io/16ca3e5-Web_push_Editor_main.png" alt="1109" align="center" width="80%" caption="Create Campaign" border={true} />


Define all the sections and publish the campaign.

## Start Campaign Setup

The _Start here_ section displays the setup information.

This section has the following parts:

* **Start here**:  Displays the list of integrated and available browsers.
* **Qualification criteria**: Here you need to define the criteria for your target audience. You can deliver the web push notification based on _Past behavior/Custom list_ or _Live behavior_.
* **Set a goal**: Tracks your campaign conversions by setting a goal. This step is optional, but it helps you measure how effectively your campaign meets its goal.<br />You can define your conversion goal by selecting the _Event_ and specifying the _Conversion Time_. The _Conversion Time_ field accepts any numeric value along with a time unit such as Minutes, Hours, Days, Weeks, or Months. This allows you to define conversion windows such as 10 days, 72 hours, or 2 months. The value can range from a minimum of 1 minute to a maximum of 5 months.<br />For example, if you set the conversion time to 5 Minutes, the system counts conversions within 5 minutes of the goal event.<br />Your campaign goal can be as broad or as specific as you want. For example, you can answer questions such as: _How many users were influenced to purchase an X amount?_ or _How many first-time visitors purchased red shoes worth at least X and blue jackets worth at least Y?_


<Image src="https://files.readme.io/d960f90056d978b5c9f8832e66c2b3c15b6e387d3caa38ea6bc0b138c57d6b29-Conversion_Tracking.png" alt="Set Conversion Time" align="center" width="75% " caption="Set Conversion Time" border={true} />


## Define the Audience

You must indicate the target audience for your campaign. You can specify your target audience from the _Target segment_ section. Here, you can create a new segment or use a previously saved user segment from the segment list.


<Image src="https://files.readme.io/ffefe62-Web_push_Who.png" alt="Define the audience for your web push campaign." align="center" caption="Define Target Segment - Who" border={true} />


You can also create the target audience based on past user behavior and user properties or live (ongoing) user behavior. The latter helps send out real-time, triggered campaigns.

<Callout icon="🚧" theme="warn">
  #### Inaction Campaigns with Delay > 24 hours

  - Live Inaction campaigns support delays greater than 24 hours, as follows:
    - Scheduling: Messages are sent after the configured delay.
    - Per-event triggering: One message is sent per qualifying event occurrence.
    - Event personalization: Trigger event properties are available in message content, including via Linked Content.
    - Message frequency: If the trigger event occurs frequently, configure limits under Delivery Preferences to control how many messages a user receives.
  - Constant Event Property: If the campaign uses Constant Event Property personalization with a delay greater than 24 hours, default values are sent.

  For more information, refer to​ [Event Personalization by Campaign Type.](doc:personalize-message-all#event-personalization-by-campaign-type)
</Callout>

For instance, you can create a live _Inaction within time_ campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes; the golden window within which most users transact on online platforms.

### Deliver Action Based Web Push Notifications

You can trigger a web push message based on an action. For example, a web push message with a promo code can be shown to a set of customers who have just completed a purchase. This will help in incentivizing an existing user. Moreover, such push messages make notifications more contextual and result in increased conversion.

### Filter Users based on Past Behavior

You can also target users basis their past behavior. For example, you might want to target customers who have purchased a specific product in the past.

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can segment your campaign to only reach users who meet specific criteria.

For example, you can send a Web Push notification to all the customers from **Mumbai** who are currently subscribed to _Platinum_ membership.


<Image src="https://files.readme.io/5fb2969-User_properties_whatsapp.png" alt="2376" align="center" caption="Filter by User Properties" border={true} />


The following table explains the various property types:

| Property Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                        | Example                                                                   |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------ |
| User Properties  | Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.                                                                                                                                                                                                                                                                             | Customer Type = Platinum                                                  |
| Demographics     | Demographics filters include _Age_ and _Gender_.                                                                                                                                                                                                                                                                                                                                                                                   | Age = 25 to 40 years<br />Gender = Female                                 |
| Geography        | User's coarse location. Filters include _Country_, _Region_, and _City_. CleverTap's SDK can automatically detect this from the user's IP address.                                                                                                                                                                                                                                                                                 | Country = United States<br />State = California<br />City = San Francisco |
| Geography Radius | User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides. | Locations = San Francisco, USA; Paris, France                             |
| Reachability     | Reachability filters include _Has email address_, _Has phone number_, _Unsubscribed email_, and _Unsubscribed SMS_.                                                                                                                                                                                                                                                                                                                | Unsubscribed email = No                                                   |
| App Fields       | App fields filters include _App Version_, _Device Make_, _Device Model_, _OS Version_, and CleverTap _SDK Version_. This information is sent by CleverTap's SDK for each device that has your app which means a single user can have multiple devices associated with their user profile.                                                                                                                                          | OS Version = 10                                                           |

To know more about what segments can be used, see [Segments](doc:segments).

### Calculate Estimated Reach

The Estimated Reach option allows you to preview how many users meet your targeting criteria in an online trigger campaign before publishing it. This helps you validate audience size and adjust filters to ensure the campaign reaches the intended users.

Estimated Reach is particularly useful when you select the _Filter on past behavior and user properties_ option. You can view both the estimated user count and device count.

To calculate the estimated reach, perform the steps below:

1. Select **Filter on past behavior and user properties**.
2. Click **Calculate** in the right panel. The result shows the estimated number of users or devices for that segment. You can view the following:

   * **Total Users**: The number of users that match the filters.
   * **Breakdown by Platform and Devices**: The users count on Android, iOS, or both, and on different devices.
   * **Visual Indicator**: A chart summarizing the share by operating system.<br />The estimate, based on the latest available event data, updates each time you apply or modify filters. It reflects stored event data and is not a real-time count. This helps you plan and refine your audience before sending the campaign.


   <Image src="https://files.readme.io/f50fcc85e575c60b8f2e7ca66360c82c17d5c9a1aab350e8b408fe5c41037b0d-2026-01-30_19-12-06_1.gif" align="center" width="85% " caption="Calculate Estimate Reach" border={true} />


### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups).


<Image src="https://files.readme.io/b5eaab1-Control_Group_and_Target_Cap.png" alt="Control Group" align="center" caption="Control Group" border={true} />


### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (_Target Reach_) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.


<Image src="https://files.readme.io/3aa9241-subset_image.png" alt="406" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Campaign Limit

  Ensure that you set up a limit of 100 or more, regardless of the qualified user segment size. If the limit specified is less than 100, an error occurs.
</Callout>

## Web Push Message Types

You can create the following types of messages for your web push campaigns:

* Single Message
* A/B Test
* Split Delivery
* By User Property

### Single Message

In this campaign, a standard push message is sent to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### A/B Test

A/B testing helps you understand what type of message copy works best in the push messages to get clicks from users.<br />You can test up to three push message variants on a test group. The variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.


<Image src="https://files.readme.io/36974fb-Web_Push_AB_Test.png" alt="2312" align="center" caption="A/B Test Variant Distribution" border={true} />


### Split Delivery

With split delivery, you can define what percentage of your audience receives the respective push message variant for that campaign duration. You can test up to three message variants.


<Image src="https://files.readme.io/fb2f266-split_delivery_web_push.png" alt="2332" align="center" caption="Split Delivery Variant Distribution" border={true} />


### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, click **+ Variant** to add multiple variants based on a user property value. You can send up to 50 message variants to different users based on a user property. In the example below, we have used the _Language_ user property so users with different language preferences will receive corresponding copies of the campaign in their preferred language.


<Image src="https://files.readme.io/cc65841-user_property_web_push.png" alt="2330" align="center" caption="Message Variant by User Property" border={true} />


## Web Push Editor

After you select a particular message type, the web push editor displays.

From the What section, click **Go To Editor** to create your message. This section displays the editor, where you can craft your web push message using various tools to make messages more relevant and impactful. For the Title and Message fields, you can use the following options to create personalized and engaging web push notifications:

* Personalization: Use @ [Personalization](doc:personalize-message-all) or \{\{\}\} to dynamically insert user-specific details.
* Emoticons: Enhance your notifications with emoticons to grab attention and convey emotions more effectively than plain text. The emojis may vary in size depending on the device and platform.
* Scribe: Use [Scribe](doc:scribe), the AI-powered writing assistant, to refine your message tone, improve readability, and generate compelling content. Scribe helps ensure your web push notifications are engaging and emotionally resonant.


<Image src="https://files.readme.io/9bbf8095e473ef4ab8b30b9d9204fc7589bdba176349bbe8e1617e2650151360-image.png" alt="Web Push Editor Options for Title and Message" align="center" caption="Web Push Editor Options for Title and Message" border={true} />


The following web push notification text fields can be personalized for every user based on specific user property or event property values. For more information, refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles). Enter all the required information.


<Image src="https://files.readme.io/2a54fa4-Web_Push_What.png" alt="2876" align="center" caption="Web Push Editor" border={true} />


* Deep Link: Specify a deep link, so that upon a web push click, the user is taken back to one of your specific webpages, such as the checkout page. With dynamic replacements, you can take the user right back to the webpage of the product they just added to their cart and present them with an incentive to encourage the transaction.

* Image Link: Specify an image link for the image you wish to send along with the web push message. The supported image ratio for the image is 4:3 and the most commonly preferred image sizes are 512x256 and 1440x720 pixels. The supported file formats are JPG, JPEG, and PNG for desktop. Only JPEG is supported for mobile.

* Icon Link: Specify an icon link. This is primarily used for displaying brand logos. The recommended size of the icon is 192x192 pixels.

* Time To Live: It defines how long the push message is preserved for delivery if the device is offline or due to OEM device restrictions.

* Custom key-value pairs: It lets you send custom data when a user clicks on the button. This data is not visible to the customers.

<Callout icon="🚧" theme="warn">
  ### Browser Considerations

  Some of the optional items only apply to a certain browser, such as Firefox, Chrome, or KaiOS.
</Callout>

### Preview & Test

Once you are all done setting up the content of your campaign in the _What_ section, you have the option to send a test notification to any CleverTap user profile you have marked as a _Test profile_.<br />Click the **Preview & Test** button from the message editor to test a message.

## Define the Campaign Schedule

You can set up the _When_ to schedule the campaign's start and end.


<Image src="https://files.readme.io/4974c50-Push_notification_editor_when.png" alt="978" align="center" caption="Campaign Schedule" border={true} />


Past behavior campaigns can be scheduled to run at a specific time:

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:

* In response to a user event.
* User event/inaction combination (e.g., abandoned cart scenario).
* Based on a date event property value of an event (for example, a reminder for upcoming travel booking).

For Live behaviour campaigns, go to the _Who_ section and select the users from the segment.


<Image src="https://files.readme.io/18f736c7cd005d1ad7ee3e226d9d43a51398c9604654e6ca51e99ef6cbb7c8b1-Who_section.png" alt="Target Segment" align="center" caption="Target Segment" border={true} />


For example, for a date event property, you can select **Date Time** and define the campaign schedule.


<Image src="https://files.readme.io/089932c40e599b0bb842ef35c1343ae706351aec0e84ea2f5f0d67d528ee0d62-Who.png" alt="Who Section" align="center" caption="Who Section" border={true} />


### Delivery preferences

You can also set the _Do Not Disturb_ (DND) hours during which notifications from this Web Push campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

If you want your campaign to adapt delivery times according to the user’s timezone, check the _Timezone_ checkbox. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).


<Image src="https://files.readme.io/8f97d75-Campaign_Adwords_delivery_preferences.png" alt="777" align="center" caption="Delivery Preferences" border={true} />


<Callout icon="📘" theme="info">
  ### Recurring Day

  If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.
</Callout>

## Publish Campaign

After previewing the appearance of your overall campaign, finalize your campaign by clicking **Publish Campaign.**


<Image src="https://files.readme.io/b521e92-campaign_Publish.png" alt="1193" align="center" caption="Publish Campaign" border={true} />
