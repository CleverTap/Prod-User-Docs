---
title: Discord
excerpt: Messenger Partner
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

[Discord](https://discord.com/) is a popular real-time communication platform used by tech communities, gaming groups, startups, and Web3 brands. It offers voice, video, and text-based interaction, and supports powerful customizations via bots and integrations.

With the CleverTap and Discord integration, you can automate syncing of events between Discord and CleverTap to:

* Onboard new community members with personalized journeys
* Trigger targeted CleverTap messages based on Discord activity
* Track engagement through reactions or mentions
* Segment users by roles, channel behavior, or message activity

To streamline community engagement, this integration captures Discord events, such as new users joining a server, and automatically pushes them to CleverTap as user profiles or events. You can also trigger outbound messages from CleverTap to Discord using webhooks.

# Prerequisites for Integration

The following are the prerequisites for this integration:

* A verified Discord account with administrator access to the server
* An active Zapier account.
* A CleverTap account with a valid **Account ID** and **Passcode**.

# Integrate Discord with CleverTap

The integration process involves the following four major steps:

1. [Create Passcode on CleverTap Dashboard](doc:discord#create-passcode-on-clevertap-dashboard)
2. [Set up a Zap in Zapier](doc:discord#set-up-a-zap-in-zapier)
3. [Set Up a Webhook in CleverTap](doc:discord#set-up-webhook-in-clevertap-to-send-messages-to-discord)
4. [Create Webhook Campaign](doc:discord#create-webhook-campaign-in-clevertap)

## Create Passcode on CleverTap Dashboard

CleverTap uses a header-based authentication model to authenticate requests to the API. Every CleverTap API call must include the Account ID and Passcode as the request headers. To create a passcode, refer to [Create Account Passcode](https://developer.clevertap.com/docs/authentication#create-account-passcode).

## Set up a Zap in Zapier

Set up a Zap in Zapier to automatically push data from Discord into CleverTap. You will configure Discord as the trigger source and CleverTap as the destination. To do so, follow these steps:

1. Go to your [Zapier Dashboard](https://zapier.com/) and click **+ Create Zap**.
2. Set _Discord_ as the trigger app.
   1. Select a trigger event. For this example, select _New User Added_.
   2. Authorize Zapier to access your Discord account.
   3. Select the server you want to connect to. Grant required permissions to Zapier.

<Image align="center" alt="Create Zap" border={true} caption="Create Zap" src="https://files.readme.io/cff7f73456b620056f785cbd2c117b99587a176d4ef30258e8f9e4af5d94cd9c-2025-07-21_11-32-28_1.gif" width="75% " />

3. Click **Test Trigger** to fetch recent event data and confirm the connection. This step will display the most recent events, such as details of newly added users in your Discord server.

<Image align="center" alt="Configure Trigger" border={true} caption="Configure Trigger" src="https://files.readme.io/e624d5e5e5e0f924674af3186196a4a6e16fcd176d6ac4f2a9c61122a6f43e74-image.png" width="75% " />

4. Set CleverTap as the destination.
   1. For the **Action App**, select _CleverTap_.
   2. Select _Create User Profile_ or _Update User Profile_ as the action event.
   3. Enter your **CleverTap Account ID**, **Passcode**, and **Region**. For detailed steps, refer to [Create a Passcode on CleverTap Dashboard](doc:discord#create-passcode-on-clevertap-dashboard).
   4. **Configure the Action**. Map Discord data fields to CleverTap fields as follows:

| **CleverTap Field** | **Description**                                       |
| ------------------- | ----------------------------------------------------- |
| Identity            | Discord user ID or email                              |
| Object ID           | Unique identifier (optional)                          |
| Creation Date       | Date the user joined the server                       |
| Profile Properties  | Name, email, role, or other attributes in JSON format |

> ⚠️ Map Identity and Object ID
>
> You can keep the Identity field blank if you provide an Object ID, and vice versa.

<Image align="center" alt="Configure the Action" border={true} caption="Configure the Action" src="https://files.readme.io/e3d943cfb306edd13e1261ac3004c10a93c77786052bb192d2b2f15b9553b283-2025-07-21_12-05-36_1.gif" width="75% " />

5. Click **Test & Review** to confirm the setup.
6. Check your CleverTap dashboard for the test event.

<Image align="center" alt="Verify user in CleverTap" border={true} caption="Verify user in CleverTap" src="https://files.readme.io/d9135cdfbfaec94d5dcbabbf01c5b11671b2d2d51c444a578ddaafc2d6b37ffa-image.png" width="75% " />

## Set Up Webhook in CleverTap to Send Messages to Discord

To send welcome messages to users who join your Discord server, you'll first need to generate a webhook URL in Discord and then configure CleverTap to use that webhook. This setup enables CleverTap to send outbound messages to your server based on predefined campaign logic.

### Generate a Discord Webhook URL

Follow these steps to generate a Discord webhook URL:

1. Go to your Discord server settings.
2. Go to _Integrations_ > _Webhooks_, click on **New Webhook** to generate a webhook URL.
3. Copy the webhook URL.

<Image align="center" alt="Generate a Discord Webhook URL" border={true} caption="Generate a Discord Webhook URL" src="https://files.readme.io/6190627bb77a6b99198aea25abdffa3966dd21cb91e98597af6e04f3d0aed7df-image.png" width="75% " />

### Configure Webhook in CleverTap

Set up the Discord webhook in CleverTap to send real-time messages to your server when a campaign is triggered. To do so, follow these steps:

1. Go to _Settings_ > _Channels_ > _Webhooks_ from the CleverTap dashboard.
2. Click **+ Add Webhook** and provide a meaningful name for the webhook.
3. Set the _HTTP Method_ to `POST` and paste the URL copied in _Step 3_ of [Generate a Discord Webhook URL](doc:discord#generate-a-discord-webhook-url).

<Image align="center" alt="Create Webhook" border={true} caption="Create Webhook" src="https://files.readme.io/8c33312554ac1aea1ed98c3564e6fd35aee92bfceb8453dba903831c484675b4-eb92e5bb-c8a8-46a1-aea3-7b2668437495.png" width="65% " />

4. Click **Save** to create the webhook.

Once saved, your CleverTap account will be ready to trigger outbound messages to your Discord server via webhook campaigns.

## Create Webhook Campaign in CleverTap

Set up a CleverTap campaign to automatically send welcome messages to Discord users when they join your server. Follow these steps:

1. Go to _Campaigns_ on the CleverTap dashboard, click **+ Campaign** and select _Webhook_ from the list of messaging channels.
2. Configure the campaign settings, such as the target audience, schedule, and other basic preferences.
3. In the _What_ section:

   1. Select the webhook you created in [Set Up a Webhook in CleverTap](doc:discord#set-up-webhook-in-clevertap-to-send-messages-to-discord).
   2. Set the content format to `JSON`.
   3. Select _Custom Body_ and paste the following payload:

   ```json
   {
     "content": "Welcome to the server, <@{{ Profile.Identity | default: "null" }}>! :tada: Glad to have you here."
   }
   ```

   This message uses the `Identity` field (mapped earlier from Discord to CleverTap) to dynamically mention the user in Discord. To personalize your message further, use the `{{` button or type `{` to insert dynamic content.
4. Click **Preview and Test** to push default values and validate the setup.
5. Once confirmed, click **Publish**. Users who join your Discord server will now receive a personalized welcome message, like the one shown below:

<Image align="center" alt="Example Welcome Message in Discord" border={true} caption="Example Welcome Message in Discord" src="https://files.readme.io/dd4b3b694a2117e5434b49124443a69484daeaaed2265454f96b7f4e810ed826-image.png" width="50% " />

# Verify Integration Results

After publishing:

* If you selected _Create or Update User Profile_, CleverTap creates or updates a user profile using the mapped Discord data.
* If you configured a Webhook campaign, users will receive a personalized welcome message directly in Discord.

This integration enables real-time onboarding and contextual engagement within your Discord community without writing any code.
