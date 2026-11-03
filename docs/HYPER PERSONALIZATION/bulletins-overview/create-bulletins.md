---
title: Create Bulletins
excerpt: >-
  Learn how to create a bulletin, define who qualifies, and add campaigns that
  send when a business event occurs.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

A bulletin defines which business event starts the messages and which users qualify to receive them. Create the[ business event ](doc:create-business-events)first. The Bulletins list shows each bulletin's name, ID, creator, creation date, Business Event ID, and channel.

The following image shows the Bulletins listing page.


<Image src="https://files.readme.io/d61558a74da800a5c4cde98bbc1dbf19e51e0d57afc8c643e34a493dd1c2c9ec-image.png" align="center" caption="Bulletins Listing" border={true} />


To create a bulletin, follow these steps.

1. In the left navigation, go to _Bulletins_.
2. Click **Create Bulletin**. The _Create Bulletin_ page opens on the _Setup_ tab.
3. In _Bulletin Name_, enter a name, for example `New Season Announcement`.
4. In _Send the bulletin on the trigger of_, select the business event that starts the bulletin.
5. In _Business event property unique ID_, select the business event property that CleverTap matches against user behavior. A message below the field confirms the match. For example, the bulletin is sent whenever a business event's Series ID matches the user behavior defined in the target segment.
6. In _Segment_, select the segment that contains the users who can receive the bulletin. The default is All Users.
7. In _Filter by_, select _Add Rule_, and then define who qualifies, as described in [Define Who Qualifies](doc:create-bulletins#define-who-qualifies).
8. Click **Save**. Saving a bulletin does not publish its campaigns. You publish each campaign separately.

The following image shows the _Create Bulletin_ page.


<Image src="https://files.readme.io/d172ae3e38742d9e29927ae9f2ca29aab87404c5d0fdba8ee39c14f3289899c2-2026-11-02_18-25-46_1.gif" align="center" caption="Create Bulletin" border={true} />


## Define Who Qualifies

A rule tells CleverTap how to recognize an interested user. Each rule maps the business event property that you selected to a user event or a user property.

- **Event rule**: Select a user event, such as Series watched, and select the event property that holds the value to match, such as the series ID. Set the occurrence condition that a user must meet in the last 30 days, for example, 10 occurrences. Select _+Filter_ to further narrow the event.
- **User property rule**: Select the user property that holds the value to match, such as Language.
- **Add Rule**: Add more rules. CleverTap shows OR between the rules, so a user qualifies when at least one rule is met.

The match is exact, and the values must be strings. A user qualifies for a given trigger when the value that you send for the business event property equals the value in the user's event or user property.

The following image shows the rule mapping in a bulletin:


<Image src="https://files.readme.io/c757329e5ab1f406cee2c6094d44955af8db8a0675e5b2060cfe15a0eb821d4e-image.png" align="center" caption="Define the Audience" border={true} />


After you save, the _Setup_ tab is read-only. To change the setup, create a new bulletin.

## Add Campaigns to a Bulletin

A campaign is the message that a bulletin sends. A bulletin can have several campaigns, each with its own channel and content. When your system raises the business event, CleverTap sends one message for each active campaign in the bulletin. If one campaign fails, the other campaigns still send. A bulletin with no active campaigns sends nothing.

A bulletin campaign works differently from a standard campaign. The following table lists the differences.

| Area            | Bulletin campaign                                                                                                                                                                       |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Audience        | The campaign uses the segment and rules that you defined in the bulletin setup. You do not choose an audience for the campaign.                                                         |
| Schedule        | The campaign has no start date, end date, or schedule. CleverTap sends the message when your system raises the business event, and the `when` value in the API call sets the send time. |
| Steps           | Setup, What, Delivery, and Publish. There is no Who step.                                                                                                                               |
| Variants        | A campaign has one message and no variants.                                                                                                                                             |
| Personalization | You insert business event properties into the message with Liquid.                                                                                                                      |

### View Campaigns in a Bulletin

You can access a bulletin's campaigns in the following two ways:

- In the left navigation, go to _Bulletins_, and then select _Bulletins_. Select a bulletin to open a side panel that shows its Segment, Business Event ID, and Channel. In the side panel, select _Campaigns_.
- Open the bulletin, and then select the _Campaigns_ tab.

The following image shows the campaigns in a bulletin.


<Image src="https://files.readme.io/8bf55f857f0b85b77f1b71ad855b1f32432197e7810def4b6c713addb0377a0f-2026-10-23_15-36-15_1.gif" align="center" caption="View Campaigns in Bulletins" border={true} />


The _Campaigns_ tab lists the bulletin's campaigns. You can search the list, filter it, and select _Create Campaign_. The list shows the following columns: Campaign name (with the campaign ID), Channel, Start date & time, Status, and Created by. When the bulletin has no campaigns, the tab shows _Create campaign to engage users_ and a _Create Campaign_ button.

### Create a Campaign

To create a campaign, follow these steps.

1. [Select a channel](#select-a-channel).
2. [Set up the campaign](#set-up-a-campaign).
3. [Create the message](#create-a-message).
4. [Set delivery preferences](#set-delivery-preferences).
5. [Publish the campaign](#publish-the-campaign).

You can save the campaign as a draft at any point. Select _Save Draft_, and CleverTap confirms with the message _Campaign draft saved_. A draft campaign does not send when your system raises the business event.

The following image shows how to create a campaign in a bulletin.


<Image src="https://files.readme.io/dd0d1223e442f2ba4ecdbfe3763ae09ac81cc6c41ff16fa3075f85127706f3eb-2026-10-23_15-40-46_1.gif" align="center" caption="Create a Campaign in Bulletin" border={true} />


#### Select a Channel

The channel decides which settings and message editor the campaign uses. A campaign uses one channel. To send a message across multiple channels, create a separate campaign for each channel within the same bulletin. When your system raises the business event, CleverTap sends it to each active campaign.

To select the channel, follow these steps.

1. On the _Campaigns_ tab, click **Create Campaign**.
2. In _Select the channels for your Bulletins campaigns_, select one of these channels: Push Notification, SMS, Email, or Web Push.

A sidebar opens with the heading New channel Campaign, for example, New Push Notification Campaign. The sidebar contains the Setup, What, Delivery, and Publish steps.

The following table shows how each channel changes the campaign.

| Channel           | What changes in the campaign                                                                                                                            |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Push Notification | The Setup step includes Deliver to (operating systems and device types) and Channel Settings. The Delivery step includes the push time-to-live setting. |
| SMS               | The Setup step includes the SMS Service Provider.                                                                                                       |
| Email             | The Setup step includes the Email Service Provider.                                                                                                     |
| Web Push          | The Setup step includes Deliver to (devices) and Channel Settings.                                                                                      |

In all channels, the What step shows the message editor for the channel that you select. The Setup step also includes a Webhook for Push Notification, SMS, and Email when cascade is enabled for your account.

Bulletins do not support WhatsApp, in-app, or App Inbox messages, so these channels do not appear in the list.

#### Set Up a Campaign

The Setup step opens with the heading _Start here_. The following table lists the settings in this step.

| Setting                | Channels         | Description                                                                                                                                                                                                                                    |
| ---------------------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Bulletin Campaign Name | All              | Required. Enter a name, for example `New season push`.                                                                                                                                                                                         |
| Label                  | All              | Optional. Add an existing label or create a new one. The list shows the first two labels, followed by the number of additional labels.                                                                                                         |
| Deliver to             | Push, Web Push   | Select the devices that receive the message. For Push, select the operating systems and device types. By default, CleverTap selects Android, iOS, and all device types. For Web Push, select the devices. You must select at least one option. |
| Channel Settings       | Push, Web Push   | Set the channel settings for the campaign, the same as for a standard campaign.                                                                                                                                                                |
| SMS Service Provider   | SMS              | Select the provider that sends the message.                                                                                                                                                                                                    |
| Email Service Provider | Email            | Select the provider that sends the message.                                                                                                                                                                                                    |
| Webhook                | Push, SMS, Email | Available only when cascade is enabled for your account.                                                                                                                                                                                       |

The Setup step does not include an audience. CleverTap uses the segment and rules from the bulletin setup.

#### Create a Message

The _What_ step is where you write the message. This step uses the same editor as a standard campaign for the channel that you selected, so the fields depend on the channel. A bulletin campaign has one message and no variants.

To personalize the message with a business event property, follow these steps.

1. In the message field, open the personalization picker.
2. Select the _Business Action Properties_ tab. The tab lists the properties of the business event that the bulletin uses.
3. Select a property. CleverTap inserts the Liquid tag in the message, for example `{{BusinessActionProperties.series_name}}`. When a property name has special characters, CleverTap inserts the property in brackets, for example `BusinessActionProperties["series-name"]`.
4. Optional: Add a default value, so that the message still reads correctly when the trigger does not send a value for the property. For example, `{{BusinessActionProperties.series_name | default: ""}}`.

For example, the push message `A new episode of {{BusinessActionProperties.series_name | default: ""}} is out` shows the series name that your system sends in the trigger.

Consider the following when you create the message:

- Your account settings determine profile and event personalization. Catalog and recommendation personalization are not available in bulletin campaigns.
- Legacy business action personalization, the older format that uses `##ba:` blocks, blocks publishing. You can still save the campaign as a draft. Replace the legacy personalization with Liquid before you publish. If you publish with legacy personalization, CleverTap shows the message _Resolve error(s) in the What section to continue_.

#### Set Delivery Preferences

The Delivery step opens with the heading _Delivery_ and the subheading _Set delivery preferences_. The following table lists the settings in this step.

| Setting                        | Channels | Description                                                                                                                                                                                                                                                     |
| ------------------------------ | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Control group                  | All      | Select System control group, a custom control group, or a campaign control group. For a campaign control group, enter a group size between 1 and 6. The System control group option is disabled and shows a link when your account has no system control group. |
| Preferences, push time to live | Push     | Set how long CleverTap tries to wait before delivering the push notification.                                                                                                                                                                                   |

A bulletin campaign does not include the following delivery settings available in a standard campaign: start and end dates, user time zone, Do Not Disturb, quiet hours, priority, delivery type, and conversion goals. Global frequency limits for your account still apply to bulletin messages.

#### Publish the Campaign

The Publish step becomes available after you complete the Setup, What, and Delivery steps. Until then, the step shows _Almost there. Complete all the above steps in order to publish this campaign_.

The following table outlines the Publish step for each user type.

| User                             | Button            | What happens                                                                                                                                                                                      |
| -------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Users who can publish            | Publish Campaign  | A Publish Campaign confirmation shows the campaign name. Select _Publish_. CleverTap shows _the Campaign as published_ and opens it in a read-only view. The status of the campaign is Completed. |
| Users who need approval (makers) | Send For Approval | CleverTap shows _Campaign sent for approval_ and closes the sidebar.                                                                                                                              |

### Manage a Campaign

The following table lists the statuses that a campaign can have.

| Status    | Meaning                                                                                                                                            |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Draft     | You saved the campaign but did not publish it. The campaign does not send.                                                                         |
| Completed | You published the campaign, and it is active. The campaign sends each time your system raises a business event, as long as the bulletin is active. |
| Stopped   | You stopped the campaign. The campaign does not send. The _Archived_ tab also shows archived campaigns as Stopped.                                 |

The following table lists the actions that you can take on a campaign from the list.

| Action  | Description                                                                                                                            |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Edit    | Opens the campaign. A draft campaign opens in the editor. A published campaign locks the Setup step. You can still edit the What step. |
| Stop    | Stops a completed campaign so that it no longer sends. CleverTap shows _Campaign stopped successfully_.                                |
| Clone   | Creates a copy of a completed or stopped campaign. You can edit every step of the copy.                                                |
| Label   | Adds a label to the campaign.                                                                                                          |
| Archive | Moves a stopped campaign to the Archived tab. You can archive only stopped campaigns.                                                  |

A campaign sends only when both the campaign and its bulletin are active. If you archive the bulletin, its campaigns do not send.

<Callout icon="far fa-circle-info" theme="info">
  ### Permissions

  You need write access to Bulletins to create, edit, clone, stop, or publish a campaign. A user without write access sees the message _You have limited access. To perform this action, contact the CleverTap admin in your organization_.
</Callout>

## Manage Bulletins

The following table lists what you can do from the Bulletins page and the Campaigns tab.

| Page          | What you can do                                                                                                                                                                                       |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Bulletins     | Search by bulletin name (up to 100 characters), filter by time period (the default is the last month), and switch between Active and Archived bulletins. Show 10, 20, 50, or 100 bulletins on a page. |
| Campaigns tab | Edit, stop, clone, label, and archive campaigns. See [Manage a Campaign](doc:create-bulletins#manage-a-campaign).                                                                                     |
