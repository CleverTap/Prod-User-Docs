---
title: Create Message
excerpt: Learn how to create a webhook campaign message in CleverTap.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

A Custom Channels (Webhooks) campaign delivers messages to your users through a configured webhook endpoint. In the campaign editor, you select a template from the Template Library, fill in the variable values defined in that template, and schedule delivery to your target audience. This document covers the full campaign creation flow for webhook campaigns, from setup through publish.

This document covers the following:

- [Create a New Campaign](#create-a-new-campaign)
- [Start Campaign Setup](#start-campaign-setup)
- [Define the Audience](#define-the-audience)
- [Define the Message Content](#define-the-message-content)
- [Define the Campaign Schedule](#define-the-campaign-schedule)
- [Delivery Preferences](#delivery-preferences)
- [Publish Campaign](#publish-campaign)
- [Next Steps](#next-steps)

## Create a New Campaign

To create a new webhook campaign:

1. From the CleverTap dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the messaging channels list, select **Webhook**.

{/* Screenshot: New Webhook Campaign page */}

Enter a _Name_ for the campaign. Optionally, assign one or more _Labels_ to organize the campaign.

## Start Campaign Setup

The _Setup_ section defines the delivery type, the webhook endpoint, and the conversion goal for the campaign.&#x20;


<Image src="https://files.readme.io/abd90917cd3b160a46b182397a177d6ffb120964b3f11486d24aced64713e297-create_message_webhook_1.png" align="center" caption="Start Campaign Setup" border={true} />


This section contains the following:

**Qualification criteria**: Select how users qualify for the campaign:

- _Past behavior/Custom list_: Targets users based on historical events or a manually uploaded list.
- _Live Behavior_: Targets users in real time as they perform events.
- _External Trigger_: Triggers the campaign through an external API call. (@jithendra this will be there right?)

**Webhook**: Select the webhook to use for this campaign. The webhook you select here also determines which templates are available to build the message.

**Set a goal (optional)**: Track campaign conversions by defining a goal event and a conversion time window. The _Conversion Time_ field accepts numeric values with units, such as minutes, hours, days, weeks, or months, ranging from 1 minute to 5 months. For example, if you set a conversion window of 5 minutes, CleverTap counts any occurrence of the goal event within 5 minutes of message delivery as a conversion. Your campaign goal can be as broad or as specific as needed. For example, you can track how many users purchased a product at a specific price point after receiving the notification.

{/* Screenshot: Setup section showing Qualification criteria, Webhook, and Goal */}

## Define the Audience

The _Who_ section defines which users receive the campaign.

You can target a webhook campaign to a new ad-hoc segment or to a previously saved segment from the segment list. CleverTap supports targeting based on past user behavior and user properties, or on live (ongoing) user behavior for real-time triggered campaigns.

### Deliver Action-Based Webhook Notifications

You can trigger a webhook notification when users perform a specific action, making notifications more contextual and increasing conversion. For instance, you can send a webhook notification to users who complete a booking or add a product to their cart.

<Callout icon="📘" theme="info">
  ### Note

  The instant webhook message is not triggered for campaigns with delays or when App Inbox is coupled with a webhook message.
</Callout>

### Filter Webhook Notifications Based on Past Behavior

You can also target users based on their past behavior. For past behavior campaigns, you have the option to calculate estimated reach to preview:

- The number of users that qualify for the campaign criteria.
- The number of users that are reachable via webhook.

<Callout icon="🚧" theme="warn">
  ### Delay Greater Than 24 Hours

  We recommend creating a Past Behavior campaign for all campaigns where the delay is greater than 24 hours for a live inaction campaign. For instance, you can create a live Inaction within time campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on online platforms.
</Callout>

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can narrow your campaign to users who meet specific criteria. For example, you can send webhook notifications only to users from a specific city who are subscribed to a particular membership tier.

The following table describes the available property types:

| Property Type    | Description                                                                                                             | Example                         |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| User Properties  | Custom user profile properties that you define and send to CleverTap                                                    | Customer Type = Gold            |
| Demographics     | Filters include Age and Gender                                                                                          | Age = 25 to 40, Gender = Female |
| Geography        | User's coarse location. Includes Country, Region, and City. CleverTap's SDK can detect this from the user's IP address. | Country = India, City = Mumbai  |
| Geography Radius | User's exact location. You can select a city and define a target radius, or select multiple cities.                     | Locations = Mumbai, Delhi       |
| Reachability     | Includes Has email address, Has phone number, Unsubscribed email, and Unsubscribed SMS                                  | Unsubscribed SMS = No           |
| App Fields       | Includes App Version, Device Make, Device Model, OS Version, and CleverTap SDK Version                                  | OS Version = 14                 |

### Communication Preferences

If an opt-in property is configured for the webhook under _Identity & Callbacks_, CleverTap uses it as a channel-level eligibility filter before delivery. Only users with this property enabled on their profile receive the campaign message, even if they otherwise qualify for the target segment. Users without this property set are excluded from delivery.

To configure the opt-in property for a webhook, refer to [Set Up Webhooks](doc:webhook-setup).

### Control Group

You can define a control group to compare and measure the results of your campaign. For more information, refer to [Control Groups](https://docs.clevertap.com/docs/control-groups).

<Callout icon="📘" theme="info">
  ### Note

  The control group for webhook campaigns is enabled only if the Webhook Delivered system event is available for your account. To enable the Webhook Delivered event, contact your Customer Success Manager.
</Callout>

### Targeting Cap

Targeting Cap lets you send a campaign to only a subset of the qualifying audience, or prevent delivery if the qualified audience exceeds a specified number. A relevant use case is a limited offer where you want to distribute a fixed number of coupon codes: if the total reach for your campaign exceeds the number of coupons available, you can cap delivery to exactly that number.

<Callout icon="📘" theme="info">
  ### Campaign Limit

  Set a targeting cap of 100 or more, regardless of the qualified segment size. If the limit specified is less than 100, an error occurs.
</Callout>

<Callout icon="📘" theme="info">
  ### Note

  The maximum reach for the target segment may be less than the limit specified in Targeting Cap.
</Callout>

## Define the Message Content

The _What_ section is where you build the message content for the campaign. Click **Go to Editor** to open the campaign editor. The editor that opens depends on how the webhook was configured during setup. For more information, refer to [Set Up Webhooks](doc:webhook-setup).

### Webhook URL

_Webhook URL_ displays the destination endpoint from the webhook configuration. This value is read-only and cannot be modified from the campaign editor.

<Tabs>
  <Tab title="Template Library">
    The Template Library displays all Webhook Templates built against the webhook selected in _Setup_. For steps on creating Webhook Templates, refer to [Webhook Templates](doc:webhook-templates). Browse or search for a template by name, then select it.

    {/* Screenshot: Template Library showing templates filtered to the selected webhook */}

    The editor loads with the selected template name displayed at the top left. To switch to a different template at any point before clicking **Done**, click **Change**.

    #### Message Payload

    _Message Payload_ displays a named input field for each `$$variable` defined in the selected template. The input type for each field reflects the datatype assigned to that variable in the template:

    - An _Image_ variable displays **Image URL**, **Upload Image**, and **Generate with AI** options.
    - A _Text_ variable displays a single-line personalization field.
    - A _Number_ variable displays a numeric input field.
    - A _Boolean_ variable displays a _True_ / _False_ radio button selector.
    - An _Audio_ variable displays _Audio URL_ and _Upload Audio_ options.
    - A _Video_ variable displays **Video URL** and **Upload Video**.
    - A _Document_ variable displays **Document URL** and **Upload Document** options.
    - A _Textarea_ variable displays a multi-line text field that supports Liquid personalization.
    - A _Dropdown_ variable displays the list of allowed values configured in the template for you to select from.

    Fill in all required fields, indicated by a red asterisk. Each value field supports inline personalization. Click **@** to insert a user profile property, event property, or other dynamic value. Click {[]} to insert a Liquid tag. For more information, refer to [Personalize Message](doc:webhook-personalize-message).

    {/* Screenshot: Message Payload section with variable fields rendered by datatype */}

    #### Set Up Personalization

    Clicking **Set up Personalization** in the top bar opens a panel for configuring advanced personalization sources that feed into your variable values.

    1. Click **Set up Personalization**.
    2. Select the tab for the personalization source you want to configure:
       - _Linked Content_: Select an API to fetch real-time external data and make its mapped properties available in the variable value fields.
       - _Recommendations_: Configure a recommendation model to surface personalized content per user.
       - _Catalog_: Set up catalog send-time personalization to pull product or inventory data into variable values.
    3. Configure the selected source and click **Apply**.

    For more information, refer to [Personalize Message](doc:webhook-personalize-message).

    {/* Screenshot: Set up Personalization panel with Linked Content tab open */}
  </Tab>

  <Tab title="Webhook Content Editor">
    Select a _Content Format_ for the message.

    <Tabs>
      <Tab title="JSON">
        Select how to build the JSON payload:

        - **Custom Body**: Write or paste a JSON payload directly in the editor. The editor supports inline personalization. Click **@** to insert a user profile property, event property, or other dynamic value. Click {[]} to insert a Liquid tag.
        - **Profile variables & custom key-value pairs**: Select the user data to include in the payload, then add any additional key-value pairs.

        When _Profile variables & custom key-value pairs_ is selected, the following options are available:

        | Option                                | Description                                                                                       |
        | ------------------------------------- | ------------------------------------------------------------------------------------------------- |
        | Email, Identity, Phone & CleverTap ID | Always included and cannot be deselected.                                                         |
        | Custom Profile Attributes             | Custom properties defined on user profiles.                                                       |
        | System Profile Attributes             | CleverTap system-level profile properties.                                                        |
        | GCM/APNS Tokens                       | Push notification tokens associated with the user.                                                |
        | Event Properties                      | Properties from the qualifying event. Not available for Batch or External Trigger delivery types. |

        Click **+ Key-Value Pair** under _Custom key-value pairs_ to append additional parameters to the payload.

        {/* Screenshot: Webhook Content Editor with JSON format and Profile variables selected */}
      </Tab>

      <Tab title="Plain Text">
        Enter the message content in the plain text field. The field supports inline personalization. Click **@** to insert a user profile property, event property, or other dynamic value. Click {[]} to insert a Liquid tag.

        {/* Screenshot: Webhook Content Editor with Plain Text format */}
      </Tab>
    </Tabs>
  </Tab>
</Tabs>

### URL Key-Value Pairs

_URL key-value pairs_ lets you append additional query parameters to the destination URL for this specific campaign. Click **+ Key-Value Pair** to add a parameter. Each pair consists of a key and a value, and both fields support inline personalization. For example, adding a key of `campaign_id` and a value of `summer_sale` would send the request to `https://api.example.com/send?campaign_id=summer_sale`. You can also personalize the value using a profile property, such as setting the value to `{{ Profile.Identity | default: "" }}` to append the user's identity to every request.

### Preview and Test

1. Click **Preview & Test** in the top bar.
2. In the _Preview and test template notification_ modal, select a profile from the _Select from test profiles_ dropdown, or search for a profile by email address, CleverTap ID, or identity in the _Search from all profiles_ field.
3. Click **Send Test**.

CleverTap sends the notification to the selected profile. The result appears as a notification in the editor.

{/* Screenshot: Preview and test template notification modal */}

4. Click **Done** to return to the campaign builder.

The _What_ section displays a summary of the configured message, including the webhook name, URL key-value pairs, and the template used. A full preview of the resolved JSON payload that CleverTap will send to the destination endpoint is shown on the right side of the summary panel.

{/* Screenshot: What section summary showing Webhook URL and Content with JSON payload preview on the right */}

## Define the Campaign Schedule

Each webhook campaign must be scheduled for a specific timeline.

In the _When_ section, specify the _Start date and time_ and _End date and time_ for the campaign. You can also start a campaign immediately by selecting **Now**. You can additionally define a delay in seconds, minutes, hours, or days after a user qualifies for the target segment before the notification is sent.

{/* Screenshot: Define the Campaign Schedule */}

## Delivery Preferences

Global frequency caps operate on a per-channel basis and control message cadence, dwell time between messages, and throttle limits. To control the maximum number of messages users receive for this webhook channel, select _Global campaign limits_. To control the delivery rate for your campaigns, select _Global throttle limits_. For more information, refer to [Messaging Frequency Caps](https://docs.clevertap.com/docs/messaging-frequency-caps).

For both Past Behavior and Live campaigns, you can set Do Not Disturb (DND) hours during which notifications are prevented from going out, either by discarding them or delaying delivery until after DND hours complete, such as 9 PM to 9 AM.

For Past Behavior campaigns, check the _Timezone_ checkbox to adjust delivery times to each user's local time zone. For more information, refer to [Delivery in User's Timezone](https://docs.clevertap.com/docs/delivery-in-users-timezone).

<Callout icon="🚧" theme="warn">
  ### DND Not Supported in Journeys

  Webhooks currently support the Do Not Disturb (DND) feature exclusively in campaigns, not in journeys.
</Callout>

{/* Screenshot: Delivery Preferences */}

## Publish Campaign

After reviewing your campaign settings and previewing the overall campaign configuration, click **Publish Campaign** to make the campaign live.

{/* Screenshot: Publish Campaign */}

## Next Steps

After publishing, you can monitor delivery and engagement for the campaign.

- Refer to [Webhooks Stats](https://docs.clevertap.com/docs/webhooks-stats) to track campaign delivery metrics and engagement data.
- Refer to [Personalize Message](https://staging.docs.user.clevertap.net/docs/webhook-personalize-message) to learn about advanced personalization options for webhook message variables.
