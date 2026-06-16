---
title: Create Message
excerpt: Learn how to create a WhatsApp campaign using the CleverTap dashboard.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Refer to the pages listed below to learn more about the following WhatsApp
    sections:
---
## Create a New Campaign

Create a campaign to deliver your WhatsApp message. Follow the steps below to create a new WhatsApp campaign:

1. From the CleverTap dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select **WhatsApp**.


<Image src="https://files.readme.io/6e7ec8fe82fca33ce48d386bc587ae0aff1eeedb404fcf917effee2da67f5ff9-giffe.png" alt="Click the +Campaign button and Select WhatsApp to create a new WhatsApp campaign" align="center" caption="Create a New WhatsApp Campaign" border={true} />


The campaign page displays.


<Image src="https://files.readme.io/19ccbc0-whatsapp_sections.png" alt="The image represents the WhatsApp campaign builder where you need to configure the overall campaign" align="center" caption="WhatsApp Campaign Configuration Page" border={true} />


Define all the sections and publish the campaign.

## Start Campaign Setup

The _Start here_ section displays the setup information.

This section has the following parts:

- **Start here**: Check that the required platforms are integrated and ready for campaigns.
- **Qualification criteria**: Deliver the notification based on _Past behavior_, [Custom list](doc:custom-list-segments), or _Live behavior_ For more information about segmenting users, refer to [Segments](https://docs.clevertap.com/docs/segments).
- **WhatsApp Service Provider**: Select the available WhatsApp service provider from the list.
- **Set a goal**: Tracks your campaign conversions by setting a goal. This step is optional, but it helps you measure how effectively your campaign meets its goal.<br />You can define your conversion goal by selecting the _Event_ and specifying the _Conversion Time_. The _Conversion Time_ field accepts any numeric value along with a time unit such as Minutes, Hours, Days, Weeks, or Months. This allows you to define conversion windows such as 10 days, 72 hours, or 2 months. The value can range from a minimum of 1 minute to a maximum of 5 months.<br />For example, if you set the conversion time to 5 Minutes, the system counts conversions within 5 minutes of the goal event.<br />Your campaign goal can be as broad or as specific as you want. For example, you can answer questions such as: _How many users were influenced to purchase an X amount?_ or _How many first-time visitors purchased red shoes worth at least X and blue jackets worth at least Y?_


<Image src="https://files.readme.io/d960f90056d978b5c9f8832e66c2b3c15b6e387d3caa38ea6bc0b138c57d6b29-Conversion_Tracking.png" alt="Set Conversion Time" align="center" width="75% " caption="Set Conversion Time" border={true} />


## Define the Audience

You must indicate the target audience for your WhatsApp campaign. You can target your WhatsApp campaign to a new user segment by clicking on the **Target Segment** section. Here, you can create a new segment or use a previously saved user segment from the _segment_ list.


<Image src="https://files.readme.io/cb455cd-WA_Who.png" alt="Segment your target audience based on the user properties and events" align="center" caption="Segment Your Target Audience" border={true} />


You can create the target based on past user behavior and user properties or live (ongoing) user behavior. The latter is helpful to send out real-time, triggered campaigns.

> 🚧 Delay > 24 Hours
>
> We recommend creating a Past Behavior campaign for all campaigns where the delay is greater than 24 hours for a live inaction campaign.

For instance, you can create a live _Inaction within time_ campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes; the golden window within which most users transact on online platforms.

### Deliver Action Based WhatsApp Notifications

You can trigger a WhatsApp message to users when they perform a specific action. This makes notifications more contextual and increases conversion. For example, sending a cab booking link to customers who have just booked a hotel or flight.

### Deliver WhatsApp Notifications based on Past Behavior (PBS)

You can also target users basis their past behavior. For example, you might want to target customers who have purchased a specific product in the past.

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can segment your campaign to reach users who meet specific criteria.

For example, you can send a WhatsApp notification to all the customers from **Mumbai** who are currently subscribed to _Platinum_ membership.


<Image src="https://files.readme.io/d56a113-User_properties_whatsapp.png" alt="Target the audience basis their user properties like name, email, geolocation" align="center" caption="Filter by User Properties" border={true} />


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

### Constant event property

You can also hold a property constant across the selected events.  For more information, see [Constant Event Property](doc:constant-property).

### Calculate Estimated Reach

The Estimated Reach option allows you to preview how many users meet your targeting criteria in an online trigger campaign before publishing it. This helps you validate audience size and adjust filters to ensure the campaign reaches the intended users.

Estimated Reach is particularly useful when you select the _Filter on past behavior and user properties_ option. You can view both the estimated user count and device count.

To calculate the estimated reach, perform the steps below:

1. Select **Filter on past behavior and user properties**.
2. Click **Calculate** in the right panel. The result shows the estimated number of users or devices for that segment. You can view the following:
   - **Total Users**: The number of users that match the filters.
   - **Breakdown by Platform and Devices**: The users count on Android, iOS, or both, and on different devices.
   - **Visual Indicator**: A chart summarizing the share by operating system.<br />The estimate, based on the latest available event data, updates each time you apply or modify filters. It reflects stored event data and is not a real-time count. This helps you plan and refine your audience before sending the campaign.


<Image src="https://files.readme.io/44bb9f5c34466e181b1934a67365951c488221905a4373e546dfa48b7b152db8-2025-09-08_16-57-15_1.gif" alt="Calculate Estimate Reach" align="center" width="85% " caption="Calculate Estimate Reach" border={true} />


### Control Group

You can define the control group to compare and measure the results of your campaign. For more information, refer to [Control Groups](doc:control-groups).


<Image src="https://files.readme.io/0a96db9-Control_Group_and_Target_Cap.png" alt="Control Group Editor" align="center" caption="Control Group Editor" border={true} />


### Targeting Cap

In certain cases, you may need to send a message to only a subset of the qualifying audience (_Target Reach_) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

> 📘 Campaign Limit
>
> Ensure that you set up a limit of 100 or more, regardless of the qualified user segment size. If the limit specified is less than 100, an error occurs.

## WhatsApp Message Types

You can create the following types of messages in your WhatsApp campaign:

- Single Message
- A/B Test
- Split Delivery
- By User Property

> 📘 Legacy UI
>
> A/B Test and Split Delivery message types are only available for new campaign UI.

### Single Message

In this campaign, a standard message is sent to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### A/B Testing

A/B testing helps you understand what type of message copy works best to get clicks from users.<br />You can test up to three message variants on a test group.


<Image src="https://files.readme.io/6139527-WhatsApp_AB_Test.png" alt="The image represents a sample distribution between two variants for A/B testing" align="center" caption="WhatsApp A/B Tests" border={true} />


> 📘 Winning Variant
>
> The variant that gets the most views is declared the winning variant and is automatically sent to the rest of your target audience.

When you create multiple variants (max: 3 variants) for a campaign, you can also auto-copy the content present in the current variant. Further, let us understand A/B Test delivery for Live user segments.

#### A/B Test Delivery To Live User Segments

With campaigns sent to live user segments (triggered campaigns), messages are delivered immediately when a user’s activity matches the criteria you have selected. For example, you can send a message when the user has completed a booking or purchase. Since it is not possible to determine the reach of triggered campaigns upfront, you need to decide how many total messages to send for A/B testing before a winner is declared.

> 👍 Triggered Campaign Example
>
> If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of views and continue only with this winning message for the duration of the campaign.

Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense of how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no winner will be declared and each message variant will be alternatively delivered for the duration of the campaign.

### Split Delivery

With split delivery, you can decide what percentage of your audience receives each message variant for the duration of the campaign.


<Image src="https://files.readme.io/1b5d9aa-Whatsapp_Split_delivery.png" alt="As the image represents, you can define the percentage split for your message variants" align="center" caption="WhatsApp Split Delivery" border={true} />


### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the _+Variant_ button to add multiple variants based on a user property value. In the example below, we have used the _Language_ user property so users with different language preferences will receive corresponding copies of the campaign in their preferred language (English, Hindi, etc.)


<Image src="https://files.readme.io/7fe4f5c-WhatsApp_user_property.png" alt="You can add multiple variants based on a user property value." align="center" caption="Targetting Based on User Property" border={true} />


## Define the Message Content

Now, you need to set up the _What_ section where you have to define the content for the WhatsApp campaign  Click _Go To Editor_ to create your message.


<Image src="https://files.readme.io/e4cc8d9-WhatsApp_What.png" alt=" Define the Message Type for the campaign creation" align="center" caption="Define Message Type" border={true} />


## WhatsApp Editor

Select from the approved templates.


<Image src="https://files.readme.io/95deed88d021bfbfeb1c8f9c63f27276e946ef14e028cae678af0af7482fa033-select_a_template.png" align="center" caption="Select a Template" border={true} />


Fill in the details and click **Done**. For information about using WhatsApp editor, refer to [WhatsApp editor](https://docs.clevertap.com/docs/whatsapp-message-templates).


<Image src="https://files.readme.io/98aa909-Whatsapp_editor_create_message.png" alt="Personalize the placeholders based on user/event properties and craft the template" align="center" caption="Personalizing Message" border={true} />


### Custom Key-Value Pair

Marketers utilizing Generic integration can leverage custom Key-Value pairs to transmit additional data within the message payload.

> 🚧 Generic Integration Support
>
> The Custom Key-Value feature support is currently supported for Generic WhatsApp Integrations.

### Preview & Test

Once you are all done setting up the content of your campaign in the _What_ section, you can send a test notification to any CleverTap user profile you have marked as a _Test profile_.<br />Click the **Preview & Test** button from the message editor to test a message.

### Import Templates

> 🚧 Template Import Limitations for External Providers
>
> Importing templates is exclusive to CleverTap BSP, and for other providers, you must recreate templates separately within their interfaces.

You can also import templates when creating a new message.

1. Click _Go To Editor_ to create your message.
2. From the message editor, click **Import Templates**. A window for _Import Templates_ displays.


<Image src="https://files.readme.io/d48c8e0-2023-09-25_17-21-03.jpg" alt="Add or Replace Templates" align="center" width="60% " caption="Add or Replace Templates" border={true} />


4. Click _Import_ to replace all the templates on your CleverTap dashboard.
5. Click **Continue** to replace templates.  The CleverTap dashboard shows the new templates. Your previous templates are mailed to your email account.

> 📘 Template Import Impact on Failing WhatsApp Campaigns
>
> Importing templates will not automatically resolve errors or issues related to the existing WhatsApp campaigns or journeys. These campaigns and journeys will continue to fail until you manually update the imported template in the affected campaign's _What_ section.
>
> To address campaign failures resulting from template-related errors, please follow the below steps:
>
> 1. Identify the specific campaign or journey that is encountering the error.
> 2. Access the _What_ section of the campaign or the specific journey node.
> 3. Edit the campaign or journey and select the specific imported templates.
> 4. Save and publish the changes, and check that the campaigns and journeys use the updated templates.

### Quick Reply Button with Custom Payload

CleverTap's _Quick Reply_ feature lets you easily collect user information, track responses, and trigger chat workflows using custom payloads.<br />Key-Value Pair

The custom payload Marketers utilizing Generic integration can include custom attributes with the _Quick Reply_ button in the Quick Reply templates when creating campaigns. These custom attributes are not visible to the end user. The purpose of these attributes is to track end-user responses when interacting with specific Quick Reply buttons.

To send a leverage custom payload from the Quick Reply button, you can utilize the [WhatsApp Editor](https://docs.clevertap.com/docs/create-message-whatsapp#whatsapp-editor) provided by CleverTap. When users reply Key-Value pairs to the Quick Reply, the custom payloads are returned along with their responses. These custom payloads can trigger chat workflows and enable further actions based on the user's reply.

To send a custom payload from the WhatsApp Editor, select a Quick Reply template and then select _Add Custom Payload_.

Add a custom payload. You can also [personalize](https://docs.clevertap.com/docs/personalize-message-whatsapp#message-personalization) transmit additional data within the custom message payload.


<Image src="https://files.readme.io/862aa69-small-quick_reply_button.png" alt="Add a Custom Payload" align="center" caption="Add a Custom Payload" border={true} />


> 📘 Character Limit for Custom Payload
>
> 🚧 Generic Integration Support
>
> Check that your custom payload is under **128** characters to ensure deliverability. Although CleverTap does not restrict characters in a custom payload, WhatsApp limits it to 128 characters.

For example, a bus service called ACME operates within a city. ACME wants to make it easy for regular passengers to confirm their daily bus rides. To do this, ACME sends reminder notifications in the evening and morning, matching each user's typical travel schedule.

When a passenger receives the notification, they see a _Confirm Ride_ button. This button enables them to quickly respond and indicate their intention to travel with the bus service immediately. Now, depending on how ACME sets up its system, there are two possible scenarios:

- Without Custom Payload: If ACME does not use a custom payload when a user clicks on the _Confirm Ride_ button, the user's response is sent directly to ACME's WhatsApp phone number. However, it is unclear to which specific notification the user is responding. For example, ACME does not know whether the user is confirming their ride for today's notification or a previous one. In this case, ACME needs more information, such as the ride details and route, to generate a payment link and complete the transaction.
- With The Custom Payload - When ACME sends the WhatsApp notification, it includes personalized information about the user's route and timing. There is also a _Confirm Ride_ button with a unique identifier attached as a custom payload. This allows ACME to distinguish between different notifications and campaigns. The response and custom payload are captured when the user clicks the _Confirm Ride_ button. This means ACME knows the exact notification that received a user response. ACME can now directly share the payment link with the user to complete the transaction.

The custom payload Key-Value feature simplifies the process for ACME and its passengers. It eliminates the need for additional confirmation workflows and ensures users receive the correct payment link for their intended ride. Ultimately, this helps ACME provide its customers with a smoother and more efficient experience.

### Track Clicks in WhatsApp Campaigns

The WhatsApp click tracking feature in Meta Dashboard allows you to track the clicks on the CTA (Call To Action) included in your WhatsApp messages. By enabling click tracking, you can gain valuable insights into user engagement and optimize the performance of your WhatsApp campaigns.


<Image src="https://files.readme.io/d82dc12-Whatsapp_click_track_end_user.jpg" alt="WhatsApp Click Tracking Message " align="center" width="25% " caption="WhatsApp Click Tracking Message" border={true} />


### Branded Domain (Optional)

A branded domain is a custom domain name that replaces CleverTap’s default short URL domains (like `ct3.io`) in your messages. It allows you to display your own company-branded link, improving brand visibility and customer trust.

When **Track Links** is enabled, CleverTap shortens your URLs using a default regional domain. To maintain brand identity and improve user trust, you can configure a branded domain for these links. Once configured, all shortened links in your WhatsApp messages will use your custom domain instead of the default.


<Image src="https://files.readme.io/9bc74aeb0814633f881aa3b1ddaadca049e395bb61df7f9f55379bad0c76a63c-image.png" alt="System Domain Creation" align="center" caption="System Domain Creation" border={true} />


To set up your branded domain, follow the steps in the [Branded Domain documentation](https://docs.clevertap.com/docs/branded-domain).

> 📘 Note
>
> If you send messages to Indian users, ensure your branded domain is also whitelisted on your DLT platform to comply with TRAI regulations.

#### Key Points to Remember

Let us understand how to track a click for various template fields in WhatsApp campaigns.

##### Headers

- Click tracking support is available only for text headers.
- When using custom variables (for example, {{1}}) in text headers, the system automatically detects URLs in the input box and provides an option to enable click tracking.


<Image src="https://files.readme.io/e14bea3-Whatsapp_editor_click_track_header_.jpg" alt="Click Track Text Header" align="center" caption="Click Track Text Header" border={true} />


- _Example_: If you enter a URL such as  [https://example.com](https://example.com) in a custom variable, the system will automatically detect it and give you the option to enable click tracking. The link will be wrapped (for example, [https://ct1.io/8eytiry](https://ct1.io/8eytiry)), capturing click information before redirecting the user to the actual URL.

##### Body

- When using custom variables (for example, {{1}}) in the message body, the system automatically detects URLs in the input box and provides an option to enable click tracking.


<Image src="https://files.readme.io/3234965-Whatsapp_editor_click_track_body.jpg" alt="Click Track Message Body" align="center" caption="Click Track Message Body" border={true} />


- _Example_: If you include a URL like [https://example.com](https://example.com) in a custom variable input box, the system will detect it and allow you to enable click tracking. The link will be wrapped (for example, [https://ct1.io/8eytiry](https://ct1.io/8eytiry)), capturing click information before redirecting the user to the actual URL.

##### Footer

Click tracking is not currently supported for footers because footers cannot be dynamic.

##### CTAs

- To track clicks on CTAs within WhatsApp templates, you must create _Dynamic URL type CTA_ templates with CleverTap tracking domains in the Generic WhatsApp Account Manager.
- Save these templates as _CleverTap click tracking type templates_ in the CleverTap dashboard.
- _Example_: To track clicks on a _Visit Website_ CTA, create a template with the CTA set as a CleverTap click tracking type. Enter the complete redirection URL in the _What_ section during the campaign creation. The link will be wrapped (for example, [https://ct1.io/8eytiry](https://ct1.io/8eytiry)), capturing click information before redirecting the user to the actual URL.


<Image src="https://files.readme.io/92ab31c-Whatsapp_editor_click_track_button.jpg" alt="Click Track CTA" align="center" caption="Click Track CTA" border={true} />


## Define the Campaign Schedule

The WhatsApp message campaign needs to be scheduled to run actively for a specific timeline. To define the schedule for your WhatsApp campaign, you need to specify the _Start date and time_ and _End date and time_ under the _When_ section. You also have the option to start a campaign immediately by selecting _Now_.  Besides, you can also define a delay (by seconds, minutes, hours, or days) once a user qualifies for the target segment. Once you define the schedule and click on _Done_, the campaign will be triggered and terminated as per the defined timings.


<Image src="https://files.readme.io/748dd43-WhatsApp_When.png" alt="In the When section, you need to define the start and end time for the campaign" align="center" caption="Define The Campaign Schedule" border={true} />


### Delivery preferences

In certain scenarios, you might not want a campaign to run actively on a particular day and time. In such cases, you can set the frequency for that particular campaign.

You can select the _Do Not Disturb_ (DND) hours during which messages from this WhatsApp campaign are prevented from going out, either by discarding them or delaying delivery after DND hours complete, such as 9 PM to 9 AM.

If you want your campaign to adapt delivery times according to the user’s timezone, check the _Timezone_ checkbox. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).

Additionally, you can check the _Cut-Off_ checkbox to avoid sending messages to users after a set cut-off time. This is important for time-sensitive campaigns, for example, live events.


<Image src="https://files.readme.io/eedc2b04f0f2875b24c0e5c66d05d9fdceaa2de0cf0090bea95a8f5b1abf4eb0-delivery_pref_whatsapp.png" align="center" width="65% " caption="WhatsApp Delivery Preferences" border={true} />


#### Remove Duplicate Profiles

> 📘 Private Beta
>
> This feature is currently released in Private Beta. If you want to enable this feature for your account, contact  Customer Success Manager.

CleverTap offers the _Remove duplicate profiles_ option for for Past Behavior campaigns WhatsApp campaigns and Journey WhatsApp nodes to prevent sending the same WhatsApp message to multiple qualified user profiles that share the same phone number. When enabled, CleverTap sends the message to only one profile per unique phone number.


<Image src="https://files.readme.io/6e2ce2ff522bc61a2fd94c35654ed4c92bc860f6a608a508401bccc01b6db096-Remove_Duplicate_Profiles.png" alt="Remove Duplicate Profiles" align="center" width="75% " caption="Remove Duplicate Profiles" border={true} />


If multiple profiles with the same phone number qualify for the campaign, only one will receive the WhatsApp message, while the others are reported as errors under _Duplicates excluded_.


<Image src="https://files.readme.io/ed29c14692cb7f9237a442df1da30deb61fad731adf05076ddb9e73821eda9ff-Screenshot_2026-05-28_at_3.41.37_PM.png" align="center" caption="Duplicates Excluded" border={true} />


## Publish Campaign

After previewing the appearance of your overall campaign, finalize your campaign by clicking **Publish Campaign.**


<Image src="https://files.readme.io/b521e92-campaign_Publish.png" alt="After setting up the overall campaign, click the Publish Campaign button" align="center" caption="Publish Campaign" border={true} />


<br />
