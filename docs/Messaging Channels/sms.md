---
title: SMS
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

SMS notifications are brief text messages sent to your app or website users even when they are outside of your app. SMS notifications provide the capability to send brief communication to your users or links enabling users to download the latest version of your mobile app. CleverTap’s rich segmentation offers the ability to send time-sensitive, relevant, and personalized SMS messages on a large scale. 

> 🚧 Prerequisite
>
> The prerequisite to send SMS campaigns is to integrate your SMS provider of choice. For more information, refer to [SMS](https://docs.clevertap.com/docs/sms-partners) in the integration guides.

The SMS module on the CleverTap dashboard makes it easy to set up SMS campaigns for all your users or specific user segments. These segments can be created on the basis of past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent and how many users converted as a result.

## Add a New Provider

To add a new SMS provider, perform the following steps:

1. From the dashboard, navigate to *Settings* > *Channels* > *SMS*.
2. Click **+ Add Provider**.

![1074](https://files.readme.io/ea1f1a5-1_Add_Provider_dashbboard.png "1 Add Provider dashbboard.png")

3. Enter all the required information.
4. Click **Save**. 

Once the phone number is validated by the SMS service provider, you can send a test SMS to test the integration before you start creating SMS campaigns and journeys.

<Image title="2 Add a new provider.png" alt={814} className="border" border={true} src="https://files.readme.io/9bdfd5b-2_Add_a_new_provider.png" />

> 📘 Twilio SMS Integration
>
> For Twilio integration, CleverTap also supports the capability to add a CoPilot id instead of a phone number in the *From* section.
>
> Twilio CoPilot improves the SMS delivery by letting you add multiple phone numbers to send the same campaign. For more information, refer to the [Twilio CoPilot](https://www.twilio.com/copilot) page.

## Add a Provider Group

The failure of an SMS provider may affect your SMS campaigns, so it is always better to have another SMS provider. By grouping providers, you can provide your users a seamless experience. 


For example, if you have a subscriber base across different countries, it helps to have a provider group for each country. You can assign a preferred provider to send a message. A provider group is used based on its assigned priority for each message. If provider 1 is unavailable, then we attempt the message with provider 2, and so on. In the end, this ensures higher message deliverability for your campaigns.

> 📘 Provider Group Maximum
>
> Each provider group can have a maximum of 10 providers.

To create a provider group, perform the following steps:

1. From the dashboard, navigate to *Settings* > *SMS* > *Provider Groups* tab. 
2. Click **+ Add Provider Group**.

<Image title="3 Provider Group dashboard.png" alt={1064} className="border" border={true} src="https://files.readme.io/a9f0479-3_Provider_Group_dashboard.png" />

2. Enter a group name.
3. Select the providers by priority.
4. Click **Save Provider Group**.

<Image title="SMS_provider_group_create.png" alt={576} className="border" border={true} src="https://files.readme.io/663186b-SMS_provider_group_create.png" />

### Edit a Provider Group

To edit a provider group, perform the following steps:

1. Click the ellipsis next to the required provider from the *Provider Groups* tab. 
2. Click **Edit settings** to add or remove providers or change the priority for any providers. 

You can also mark a provider group as a default by clicking on **Mark as Default**.

<Image title="4 Edit Provider Group.png" alt={1062} className="border" border={true} src="https://files.readme.io/72b25cf-4_Edit_Provider_Group.png" />

# Create an SMS Campaign

This section covers how to create a new SMS campaign.

## Create a New Campaign

To create an SMS campaign, perform the following steps:

1. Navigate to *Campaigns*. 
2. Click on the **+ Campaign** button.
3. Select *SMS* under the *Mobile channels* section. 

<Image title="Campaign_SMS_channel_select.png" alt={1380} className="border" border={true} src="https://files.readme.io/d5e246d-Campaign_SMS_channel_select.png" />

### Select the Campaign Type

To select the campaign type, use the following to make your selection:

Past behavior campaigns can be scheduled to run:

* One time: On a specific date and time.
* Multiple dates: On multiple specified dates and times.
* Recurring: On a recurring basis.

Live campaigns can be set up as follows:


* Single action: In response to a user event.
* Inaction within time: User event or inaction combination, such as an abandoned cart scenario.
* On a date/time: Based on a date event property value of an event, such as a reminder for upcoming travel booking.

<Image title="Campaigns_SMS_segment_type.png" alt={1381} className="border" border={true} src="https://files.readme.io/6cdd47b-Campaigns_SMS_segment_type.png" />

## Define the When

Set up the *When* to schedule the campaign start and end.

<Image title="Campaign_SMS_When.png" alt={1381} className="border" border={true} src="https://files.readme.io/b955aaf-Campaign_SMS_When.png" />

Global campaign limits are limits you can apply to determine how many SMS notifications each user receives per day. If you would like to override these settings for an important campaign, you can click on the *Don’t apply global throttle limits to this campaign* checkbox.

You can also click on the *Advanced* checkbox to specify *Do Not Disturb (DND)* hours during which notifications from this SMS campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to deliver at the specified time in the user’s timezone. For more information, refer to [Notification Delivery Options](doc:notification-delivery-options).

<Image title="1 When Advanced DND.png" alt={587} className="border" border={true} src="https://files.readme.io/057f9d5-1_When_Advanced_DND.png" />

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign, such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

## Define the Who

Next, indicate the target audience for your SMS campaign. 

You can target your SMS campaign to a new user segment by clicking on **Create an ad-hoc segment** or use a previously saved user segment from the list of pre-saved segments shown in the table as shown below. 

<Image title="Campaign_Saved_Segment_PBS_Who.png" alt={1147} className="border" border={true} src="https://files.readme.io/573901c-Campaign_Saved_Segment_PBS_Who.png" />


If you choose to create an ad-hoc segment, you can now select a type of segment on which to base your SMS campaign. The target can be created either on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered SMS campaigns).

<Image title="Campaign_SMS_adhoc_segment.png" alt={1389} className="border" border={true} src="https://files.readme.io/47da5b9-Campaign_SMS_adhoc_segment.png" />

For example, we can create a live, *Inaction within time* campaign that targets users as soon as they add a product to cart but do not finish transacting within five minutes, the golden window within which most users transact on our iOS and Android app platforms.

To set up the next step in the *Who* section, you can send this campaign to all users who qualify or only a portion of the users who qualify under *Campaign reach*. You can also further check the *Filter on past user behavior and common properties* checkbox to filter by any past user behavior or user properties. For past behavior campaigns, you also have an option to estimate reach to see how many users qualify for the campaign criteria and are reachable via SMS as of now.

![1631](https://files.readme.io/8109784-1a_Filter_this_stream.png "1a Filter this stream.png")

### Deliver to a Subset of the Target Audience

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

![406](https://files.readme.io/7facb10-subset_image.png "subset_image.png")

This section explains the campaign creation flow when you are determining who to send your message to. Under the *Campaign Reach* section, select the option to limit delivery of the messages to the number you choose.

For triggered campaigns based on live user segments, as users qualify, they will receive the message until the total quantity specified has been delivered after which the campaign ends. For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.


The campaign limits can also be configured as follows: 

* Daily Limit: Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.

* Campaign Run Limit: Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

* Safety Check: It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 

> 👍 Safety Check Example
>
> A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.

![1614](https://files.readme.io/884466b-2_Subset_of_the_Target_Audience.png "2 Subset of the Target Audience.png")

## Define the What

Now, you can set up the SMS campaign content in the *What* section. This section of the campaign creation flow will be dependent upon the SMS provider selected for the campaign.

### Out-of-the-box Providers

All SMS service providers are listed on the **Personalization Setup** page, including Msg91, Nexmo, Twilio, Exotel, and Netcore). The connection with these providers is configured by default and the mandatory input required for these providers is the message.

![1240](https://files.readme.io/51c1a24-Screenshot_2021-05-12_at_7.28.46_PM.png "Screenshot 2021-05-12 at 7.28.46 PM.png")

### Personalization

You can personalize the SMS notification body for every user based on specific user property or event property values. For more information on user profile properties and events (dynamic replacements), refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles).

To invoke the personalization menu, type the @ symbol in the text fields while typing out the SMS message.

You can include emojis in your SMS notifications as you would in a regular text. You can copy-paste emojis from an emoji keyboard online. 

<Image title="3 Define the What.png" alt={1608} className="border" border={true} src="https://files.readme.io/c3c9e55-3_Define_the_What.png" />

For more information, refer to [Personalize Messages](https://docs.clevertap.com/docs/personalize-messages).

### Generic SMS Provider

For SMS providers not listed, you can connect them by configuring the APIs directly on the dashboard. For more information, refer to [Generic SMS](https://docs.clevertap.com/docs/generic-sms).


The following blocks are available on the *What* section for generic SMS provider cases:

1. Template ID: If the configuration has the key "$$TemplateID" in *Headers*/*URL*/*Parameters*, this field shows up within the *What* section.

![496](https://files.readme.io/c41a1eb-Screenshot_2021-05-18_at_1.17.54_AM.png "Screenshot 2021-05-18 at 1.17.54 AM.png")

2. Template Variables: If the configuration has the key "$$TemplateVariables" in *Headers*/*URL*/*Parameters*, this field shows up within the *What* section. This field is used to define the different variables in a given template. 

In this example, "Hey &lt;User&gt;, you have &lt;percentage&gt;% OFF on your next purchase." The user and percentage are variables whose value can be defined while creating the campaign. 

The input is only variables, so it needs to be in the order of occurrence. As shown below, the first variable should be the user value and the second variable value should be the percentage.

![1022](https://files.readme.io/823f1d9-Screenshot_2021-05-18_at_1.21.36_AM.png "Screenshot 2021-05-18 at 1.21.36 AM.png")

3. Message Body Key-Value Pairs: If the configuration has any custom dynamic replacement inside the message body or URL, this field shows up within the *What* section. The section contains all the predefined custom dynamic replacements which are defined while creating the campaign. These are mandatory keys that need to have value while creating the campaign. This option also allows the addition of new key-value pairs which were not already defined while creating the configuration and are specific to the campaign.

![1032](https://files.readme.io/e2963d1-Screenshot_2021-05-18_at_1.19.12_AM.png "Screenshot 2021-05-18 at 1.19.12 AM.png")

4. Header Key-Value Pairs: If the configuration has any custom dynamic replacement inside the headers, this field shows up within the *What* section. The section contains all the predefined custom dynamic replacements which are defined while creating the campaign. These are mandatory keys that need to have value while creating the campaign. This option also allows the addition of new key-value pairs which were not already defined while creating the configuration and are specific to the campaign.

![1008](https://files.readme.io/88d3825-Screenshot_2021-05-18_at_1.19.32_AM.png "Screenshot 2021-05-18 at 1.19.32 AM.png")
5. Global Key-Value Pairs: If the configuration has any custom dynamic replacement within paramaters with the batching option enabled but outside the batched key, this field shows up within the *What* section. The section contains all the predefined custom dynamic replacements which are defined while creating the campaign. These are mandatory keys that need to have value while creating the campaign. This option also allows the addition of new key-value pairs which were not already defined while creating the configuration and are specific to the campaign.

![816](https://files.readme.io/8be21ab-Screenshot_2021-05-18_at_1.22.20_AM.png "Screenshot 2021-05-18 at 1.22.20 AM.png")

For more information on SMS configuration, refer to [Generic SMS](https://docs.clevertap.com/docs/generic-sms).

> 🚧 Personalization
>
> Here are some things to consider for personalizations: 
>
> 1. Global key-value pairs do not support personalization since they are outside the batched payload.
> 2. Header key-value pairs do not support personalization if the batching option is enabled in the configuration.

### Liquid Tags

Liquid tags offer great flexibility in composing your message. You can have fixed or variable values and change the look and feel of your message by using liquid tags.

![1357](https://files.readme.io/ed642bf-campaigns_liquid_tags_common_example.png "campaigns_liquid_tags_common_example.png")

Each notification is personalized to the receiver. 






















































































For more information, refer to [Liquid Tags](doc:liquid-tags).

### Linked Content

Linked content provides the ability to personalize emails with rich and contextual data available outside of the CleverTap platform. With linked content, you can send messages with send-time personalization.

For example, you deliver food across different geographies and you want to personalize offers to each user based on the weather and on their location. The location can come from CleverTap personalization and the weather information can come from an API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

For more information, refer to [Linked Content](https://docs.clevertap.com/docs/linked-content#write-linked-content).

## Test and Schedule a Campaign


Once you are all done setting up the content of your campaign in *What*, you have the option to send a test SMS notification to any mobile phone number of your choice, including to any country code. 

To send a test, perform the following steps:

1. Click the **Send a test SMS** link. 
2. Select an SMS service provider.
3. Enter a mobile number.
4. Click **Send**.

<Image title="4 Test & Schedule Campaign.png" alt={1604} className="border" border={true} src="https://files.readme.io/3fb10b2-4_Test__Schedule_Campaign.png" />

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, then click **Schedule notification**.

<Image title="SMS_setup_provider_group_select.png" alt={982} className="border" border={true} src="https://files.readme.io/665f358-SMS_setup_provider_group_select.png" />