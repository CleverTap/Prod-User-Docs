---
title: Create Message
excerpt: Learn how to create an Email campaign using the CleverTap dashboard.
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

Create a campaign to deliver your message.<br />To create a new campaign:

1. From the dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select the messaging channel.


<Image src="https://files.readme.io/ed10fa95546bc3dda0943fad7f9f0f2dd1ae39190c4b0cdfc02db1d617c13403-3.png" alt="Select Messaging Channel" align="center" width="smart" caption="Select Messaging Channel" border={true} />


The _Campaign_ page displays.


<Image src="https://files.readme.io/a805f56-Campaign_Creation_Page.jpg" alt="1404" align="center" width="80%" caption="Create Campaign" border={true} />


Define all the sections and publish the campaign.

## Start Campaign Setup

The _Start here_ section displays the setup information.

This section has the following parts:

* Qualification criteria: Deliver the notification by Past behavior/Custom list, Live behavior, or  [External trigger](doc:external-trigger-1). For more information about segmenting users, refer to [Segments](doc:segmentation).
* Email Service Provider: Select a provider.
* **Set a goal**: Tracks your campaign conversions by setting a goal. This step is optional, but it helps you measure how effectively your campaign meets its goal.<br />You can define your conversion goal by selecting the _Event_ and specifying the _Conversion Time_. The _Conversion Time_ field accepts any numeric value along with a time unit such as Minutes, Hours, Days, Weeks, or Months. This allows you to define conversion windows such as 10 days, 72 hours, or 2 months. The value can range from a minimum of 1 minute to a maximum of 5 months.<br />For example, if you set the conversion time to 5 Minutes, the system counts conversions within 5 minutes of the goal event.<br />Your campaign goal can be as broad or as specific as you want. For example, you can answer questions such as: _How many users were influenced to purchase an X amount?_ or _How many first-time visitors purchased red shoes worth at least X and blue jackets worth at least Y?_


<Image src="https://files.readme.io/d960f90056d978b5c9f8832e66c2b3c15b6e387d3caa38ea6bc0b138c57d6b29-Conversion_Tracking.png" alt="Set Conversion Time" align="center" width="75% " caption="Set Conversion Time" border={true} />


## Define the Audience

You must indicate the target audience for your campaign. You can specify your target audience from the  _Target segment_ section. Here, you can create a new segment or use a previously saved user segment from the _segment_ list.

For Past Behavior segments, you also calculate the estimated reach.


<Image src="https://files.readme.io/030202d-Push_notification_editor_Who.png" alt="1168" align="center" width="80%" caption="Define - Who" border={true} />


### Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your campaign. You can create the target based on past user behavior and user properties or live (ongoing) user behavior. The latter is helpful to send out real-time, triggered campaigns.

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

For instance, you can create a live _Inaction within time_ campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes; that is the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the _Who_ by sending this campaign to all users who qualify or limit the users who qualify under _Estimated reach_.

### Deliver Action Based Messages

You can trigger a message based on an action. Users receive messages when they perform an action in the app instead of waiting for the next app launch. It makes the messages more contextual and increases conversion. Campaigns with delays and app inbox coupled with a push message do not trigger instant messages.

### Deliver Messages based on Past Behavior (PBS)

You can also target users based on their past user behavior. For past behavior campaigns, you also have the option to calculate estimated reach. The estimated reach shows the number of users that qualify for the campaign criteria and the number of reachable users via mobile push.

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can segment your campaign to only reach users who meet specific criteria.

For example, you can send a push notification to English-speaking female users who live in the United States.


<Image src="https://files.readme.io/3d4faa2-Filter_By_User_Properties.png" alt="486" align="center" caption="Filter by User Properties" border={true} />


To know more about what segments can be used, see [Segments](doc:segmentation).

### Constant event property (Optional)

You can also hold a property constant across the selected events.  For more information, see [Constant Event Property](doc:constant-property).

### Calculate Estimated Reach

The Estimated Reach option allows you to preview how many users meet your targeting criteria in an online trigger campaign before publishing it. This helps you validate audience size and adjust filters to ensure the campaign reaches the intended users.

Estimated Reach is particularly useful when you select the _Filter on past behavior and user properties_ option. You can view both the estimated user count and device count.

To calculate the estimated reach, perform the steps below:

1. Select **Filter on past behavior and user properties**.
2. Click **Calculate** in the right panel. The result shows the estimated number of users or devices for that segment. You can view the following:

   * **Total Users**: The number of users that match the filters.
   * **Breakdown by Platform and Devices**: The users count on Android, iOS, or both, and on different devices.
   * **Visual Indicator**: A chart summarizing the share by operating system.<br />The estimate, based on the latest available event data, updates each time you apply or modify filters. It reflects stored event data and is not a real-time count. This helps you plan and refine your audience before sending the campaign.


   <Image src="https://files.readme.io/d1b6fd3f6f84cfe6c16f30989a460c16f81bb12f3172da4a2ffa26ec1b513aef-2026-01-30_19-12-06_1.gif" align="center" width="85% " caption="Calculate Estimate Reach" border={true} />


### Control Group

You can define a control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups).


<Image src="https://files.readme.io/c1847be-Email_Control_Group.png" alt="Control Group" align="center" width="75% " caption="Control Group" border={true} />


### Targeting Cap

You can limit the number of users receiving the message.

A relevant use case is a limited offer where you want to distribute a fixed number of coupon codes. If the total reach for your campaign exceeds the number of coupon codes you can distribute, then you can limit the number of users who will receive the message to precisely the number of coupons you want to distribute.

<Callout icon="📘" theme="info">
  ### Campaign Limit

  Ensure that you set up a limit of 100 or more, regardless of the qualified user segment size. If the limit specified is less than 100, an error occurs.
</Callout>


<Image src="https://files.readme.io/af07d3a-Set_Target_Segment_Cap_.png" alt="Target Cap" align="center" caption="Target Cap" border={true} />


This section explains the campaign creation flow when you are determining who to send your message to. Under the _Estimated Reach_ section, select the option to limit the delivery of the messages to a specified number.<br />The campaign limits can also be configured using the following options:

* **All target segment users**: Select this option to send the campaign to all the target segment users. You can also prevent sending out unwanted campaigns by _Don't send the campaign if target segment exceeds_ checkbox and entering the value for the number of users. When selecting this option, a campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action.
* **Only**: Select this option to limit the number of users for each run of a campaign.

For triggered campaigns based on live user segments, the users receive a message as they qualify until the total quantity specified has been delivered, after which the campaign ends. For campaigns based on _Past Behavior Segments_, we randomly select the users who receive the message.

### Override Communication Preferences for Email

You must use this option only when you want to send critical emails of a non-promotional nature, such as privacy policy updates, legal/regulatory information, and downtime/outage-related updates to customers. To do so, select _Send email to users who have opted out of your emails_ to send the emails to all qualified users, including those who have opted out (i.e., unsubscribed from email campaigns).


<Image src="https://files.readme.io/af08a90-image.png" alt="Override Communication Preferences for Emails" align="center" width="85% " caption="Override Communication Preferences for Emails" border={true} />


Once you select this option, you are prompted to confirm that this email is in compliance with spam regulations.


<Image src="https://files.readme.io/37c60cd-Compliance_Confirmation_Prompt.png" alt="Compliance Confirmation Prompt" align="center" width="75% " caption="Compliance Confirmation Prompt" border={true} />


As you cannot unsubscribe from this type of email, it is advisable to refrain from including unsubscribe links in these emails. If you still choose to use the unsubscribe links, clicking on the link results in the user being unsubscribed only from promotional emails. If the user is marked unsubscribed at the Email Service Provider's end, this email would still not be delivered to the end user. Therefore, this feature is most effective when using CleverTap’s [Handling Unsubscribes](doc:handling-unsubscribes) method instead of adding ESP-specific unsubscribe links to your emails.

<Callout icon="🚧" theme="warn">
  ### Warning

  To avoid spamming the recipient's inbox and potentially harming your domain reputation, exercise utmost caution when enabling this option for your email campaign. It is important to note that any legal issues resulting from the violation of relevant anti-spamming laws will not be the responsibility of CleverTap.
</Callout>

### Exclude Unsubscribe groups

Select the subscription groups to exclude from your campaign. For more information, refer to [unsubscribe subscription groups in campaigns](https://docs.clevertap.com/docs/group-unsubscribe)


<Image src="https://files.readme.io/b69404c-Email_subscription_group_include_exclude.png" alt="926" align="center" width="smart" caption="Select Subscription Groups" border={true} />


### Include Selected Subscription Groups

Subscription groups allow users to select the content they want to receive, reducing unsubscription rates and fostering strong brand-user relationships. This approach enhances user satisfaction and builds a more personalized connection with your audience.

Select the groups you want to include in your campaign from the _Select Subscription Groups_ list. This allows you to target users who have subscribed to all the groups you selected for the campaign.


<Image src="https://files.readme.io/18f16e4-Email_Control_Group1.png" alt="Select Subscription Groups" align="center" caption="Select Subscription Groups" border={true} />


## Define the Message Content

Now, you can set up the _What_ which is the email campaign content where you have four different options. Click _Go To Editor_ to create your message.


<Image src="https://files.readme.io/56de1b4-Email_editor.png" alt="959" align="center" caption="Select Message Type" border={true} />


### Email Editor

Select the templates and create a message. You can also get inbox previews and spam reports for your email message before you send out the campaign. For more information on the Email editor, see [Email Editor](https://docs.clevertap.com/docs/email-editor-templates).


<Image src="https://files.readme.io/e63eee8-Email_editor_main.png" alt="1121" align="center" caption="Select Email Editor" border={true} />


### Sender Details

After setting up the content of your campaign in the _What_ section, you can configure how your email appears to recipients. This helps ensure that the email adheres to best practices for deliverability and compliance.


<Image src="https://files.readme.io/2f21ba5-image.png" alt="Sender Details" align="center" width="65% " caption="Sender Details" border={true} />


The _Sender Details_ section encompasses the following:

* From: This is a mandatory field. This name is displayed as the sender of the email. It is important as it helps recipients recognize the sender, thereby increasing the likelihood of them opening the email.
* Subject: This is a mandatory field. It is crucial for grabbing the recipient's attention and giving them a reason to open the email.
* Preheader: This is the short summary text that follows the subject line when the email is viewed in the inbox. It provides additional context and can encourage recipients to open the email. For example, if you are running a campaign for the Black Friday Sale, you can define this text as Get 50% OFF only for today.
* Plain-Text For Body: This text displays in the campaign body if the recipient's inbox provider does not support HTML or formatted text. It can only contain plain text and cannot include images, styled content, or hyperlinks.
* CC/BCC: This field allows you to send a copy of your email campaigns to additional recipients directly from the CleverTap dashboard. For more information, refer to the [CC/BCC](doc:create-message-email#ccbcc) section.
* Highlight with Gmail Promotional Annotations: This field enables you to highlight your email on the Gmail Promotions tab. Your email can include additional information, such as promotion codes, a featured image, and deal expiration dates. For more information, refer to [Gmail Promotional Annotations](doc:gmail-promotional-annotations-product-carousel).

#### CC/BCC

<Callout icon="📘" theme="info">
  ### Private Beta

  This feature is released in Private Beta. You can now add CC/BCC recipients in emails for the following providers: Sendgrid, Amazon SES, and Generic SMTP setup
</Callout>

This feature allows users to send a copy of their email campaigns to additional recipients directly from the CleverTap dashboard. Using this feature, brands can ensure that key stakeholders receive necessary email communications simultaneously, facilitating better tracking, compliance, and customer relationship management. Here are some of the use cases:

* E-commerce, Travel, and Hotel brands often need to send email campaigns to their customers and sellers while keeping the respective account managers informed. In this case, the marketers can use the CC feature to copy account managers on all relevant communications, ensuring they stay updated and can provide timely support.
* In the case of the Real estate industry, the realtors can use the CC feature to copy agents or brokers when sending emails to high-intent users to ensure these agents can track and nurture those prospects toward making a purchase.
* FinTech companies can use the BCC feature to discretely send emails to their legal team, ensuring that all communications comply with legal standards without the primary recipient's awareness.

You can add up to a total of 20 CC and BCC recipients to your campaign.


<Image src="https://files.readme.io/2452c86-Adding_CC_BCC_recipients.png" alt="Adding CC/BCC Recipients to Email Campaigns" align="center" width="65% " caption="Adding CC/BCC Recipients to Email Campaigns" border={true} />


<Callout icon="📘" theme="info">
  ### Key Points to Remember

  * In the case of Generic SMTP, ensure that your email service provider supports the CC/BCC feature to use it on CleverTap.
  * Using CC/BCC in emails lead to increased email consumption because the copy of each mail sent to the recipient is also sent to the CC and/or BCC recipients, resulting in greater email traffic.
</Callout>

### Preview & Test

After setting up the content of your campaign in the _What_ section, you have the option to send a test email notification to any CleverTap user profile you have marked as a _Test profile_.<br />Click the **Preview & Test** button from the message editor to test a message.

You can also check view [Inbox Previews](https://docs.clevertap.com/docs/email-editor-templates#inbox-previews-with-code-analysis) and [Spam Report](https://docs.clevertap.com/docs/email-editor-templates#spam-report).

### Message Types

You can create the following types of messages:

* Single Message
* A/B Test
* Split Delivery
* By User Property

#### Single Message

In this campaign, we send the same message to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

#### A/B Testing

A/B testing helps you understand what type of message copy works best to get clicks from users.

You can test up to three message variants on a test group and the variant that gets the most views is declared the winning variant and is automatically sent to the rest of your target audience.

When you create multiple variants for a campaign, you can also auto-copy what is already present in a current variant.

#### Split Delivery

With split delivery, you can decide what percentage of your audience receives each message variant for the duration of the campaign.

##### Split Delivery to Past Behavior Segments

For campaigns sent to _Past Behavior Segments_ (grouping of users based on what they have done in the past), you have two options: launch the A/B test to a percentage of your target audience or send out an absolute number of messages. In either case, we deliver the variants equally to the test audience.

For example:

* If you are testing three messages (e.g., Variant A, Variant B, Variant C).
* Your campaign reach is 2,000,000 users.
* You choose a test population of 15% of campaign reach (300,000 users).

Then, we send:

* Variant A to 100,000 users.
* Variant B to 100,000 users.
* Variant C to 100,000 users.

After all 300,000 messages have been delivered, we calculate the winning message over this test group based on the number of views. We then automatically send the winning message to the remainder of your target audience, which is 1,700,000 users in this example.

Note that for A/B testing, we ensure there is always an equal number of messages sent for each variant, so there is no bias introduced during the test phase and that the best-performing message is always declared the winner.

##### Split Delivery to Live User Segments

With campaigns sent to live user segments (triggered campaigns), messages are delivered immediately when a user’s activity matches the criteria you have selected. For example, you can send a message when the user has completed a booking or purchase. Since it is not possible to determine the reach of triggered campaigns upfront, you need to decide how many total messages to send for A/B testing before a winner is declared.

<Callout icon="👍" theme="okay">
  ### Triggered Campaign Example

  If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of views and continue only with this winning message for the duration of the campaign.
</Callout>

Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense of how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no winner will be declared and each message variant will be alternatively delivered for the duration of the campaign.

#### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the _Customer Type_ user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).

## Define the Campaign Schedule

You can set up the _When_ to schedule the campaign start and end using the options below:

Past behavior campaigns can be scheduled to run:

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:

* In response to a user event.
* User event/inaction combination (e.g., abandoned cart scenario).
* Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

### Delivery preferences

Global campaign limits are limits you can apply to determine how many messages each app user receives per day. If you want to override these settings for an important campaign, you can click on the _Don’t apply global campaign limits to this campaign_ checkbox.

You can also _Do Not Disturb_ (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them or delaying delivery after DND hours are complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Notification delivery options](doc:notification-delivery-options).


<Image src="https://files.readme.io/a1f9337-campaign_when_PBS.png" alt="1196" align="center" caption="Define - When" border={true} />


<Callout icon="📘" theme="info">
  ### Recurring Day

  If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.
</Callout>

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Publish Campaign**.


<Image src="https://files.readme.io/b521e92-campaign_Publish.png" alt="1193" align="center" caption="Publish Campaign" border={true} />
