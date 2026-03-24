---
title: Mailmodo
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Mailmodo](https://www.mailmodo.com/) is a no-code email marketing platform that enables you to send interactive emails with app-like experiences directly inside the inbox. It supports AMP-powered widgets such as forms, calendars, and surveys to improve engagement and conversions.

The Mailmodo integration enables you to:

* Trigger Mailmodo campaigns directly from CleverTap using Webhooks.
* Sync campaign activity data back into CleverTap as custom events.
* Build segments, flows, or dashboards in CleverTap using Mailmodo engagement data.
* Personalize and automate follow-up campaigns across multiple channels.

For example, you can trigger a Mailmodo survey campaign from CleverTap and then use responses or non-engagement (such as unopened emails) to create and publish push notifications, SMS, or other follow-up campaigns from the CleverTap dashboard.

# Prerequisites for Integration

Ensure the following requirements are met before setting up the integration:

* An active Mailmodo account.
* A CleverTap account with a valid **Project ID** and **Passcode**.
* Access to Webhook configuration in CleverTap.

# Integrate Mailmodo with CleverTap

The integration involves the following three major steps:

1. [Configure Mailmodo with CleverTap](doc:mailmodo#configure-mailmodo-with-clevertap).
2. [Set Up Trigger Campaigns in Mailmodo](doc:mailmodo#set-up-trigger-campaigns-in-mailmodo).
3. [Set Up CleverTap Webhooks](doc:mailmodo#set-up-webhooks-in-clevertap).

Once the integration is enabled, Mailmodo sends the following engagement data back to CleverTap as custom events for every campaign triggered from CleverTap:

| Event Name                              | Description                                                                                                                                                      |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **MM Email Opened**                     | Triggered when a recipient opens the email.                                                                                                                      |
| **MM Email Link Clicked**               | Triggered when a recipient clicks a link in the email.                                                                                                           |
| **MM Email Form Submitted**             | Triggered when a recipient submits an AMP form or widget within the email.                                                                                       |
| **MM `<Template Name>` Form Submitted** | Triggered when a form or widget in a Mailmodo template is submitted. The event name dynamically includes the template name and contains detailed form responses. |
| **MM Email Bounced**                    | Triggered when the email cannot be delivered to the recipient.                                                                                                   |
| **MM Email Unsubscribed**               | Triggered when a recipient unsubscribes from the email.                                                                                                          |
| **MM Email Marked as Spam**             | Triggered when the email is marked as spam by the recipient.                                                                                                     |

Each event also includes additional properties (campaign name, subject line, campaign type, email type, and so on) to help filter and analyze campaign performance inside CleverTap.

<Callout icon="🚧" theme="warn">
  #### Important

  Mailmodo requires the CleverTap user ID of the recipient to push activity data back to CleverTap. Ensure that the `clevertap_id` property is included in the JSON payload when configuring the trigger campaign in CleverTap.
</Callout>

## Configure Mailmodo with CleverTap

Configure your Mailmodo account using CleverTap credentials. To do so, perform the following steps:

1. In your Mailmodo dashboard, go to _Integrations_.

2. Under _Available for Connection_, find _CleverTap_ and click **Click to authenticate**.

<Image align="center" alt="Authenticating CleverTap Integration" border={true} caption="Authenticating CleverTap Integration" src="https://files.readme.io/1786728896fe38673f1871736f13cbe8bb1cefec79c354c304fbc195fa77b1e5-image.png" width="75% " />

3. Select your [Rest API Host](https://developer.clevertap.com/docs/idc) from the dropdown.

<Image align="center" border={true} caption="Select Rest API Host" src="https://files.readme.io/9bf957512f2380fa1f19447326abf3114bc6732a741caa04f5a50850aa988a07-image.png" width="75% " />

4. Enter your **Project ID** and **Passcode** (available in your CleverTap Settings page).
5. Click **Test and Save**. A _Setup successful_ message confirms the integration. And, Mailmodo sends a sample _MM Email Opened_ event with `user_id = hello@mailmodo.com` to CleverTap. You can verify this event in your CleverTap dashboard.

## Set Up Trigger Campaigns in Mailmodo

Once your accounts are connected, you can create and publish campaigns in Mailmodo that CleverTap will trigger:

1. In Mailmodo, create or select a _Template_ for your campaign.

<Image align="center" alt="Create or Select Template" border={true} caption="Create or Select Template" src="https://files.readme.io/0e48de5a70867b26b6522078cb42a4a1f40ea61572174d566f8daa00b95d9f3c-Screen_Recording_2025-07-03_at_3.29.59_PM_1.gif" width="75% " />

2. Go to _Campaigns_ > _Triggers_  > **+ Create Trigger Campaign**.
3. Select your template, configure campaign details, and proceed to the next step.

<Image align="center" alt="Create Trigger Campaign" border={true} caption="Create Trigger Campaign" src="https://files.readme.io/8a9029cba808801ca0c93cec99de9029f237aede752228ba6ab23bde9cfba94b-Screen_Recording_2025-07-03_at_3.32.21_PM_1.gif" width="75% " />

4. Under _Trigger App_, select **CleverTap**.
5. Review the configuration and click **Enable Campaign**.

<Image align="center" alt="Configuring Trigger Campaign with CleverTap" border={true} caption="Configuring Trigger Campaign with CleverTap" src="https://files.readme.io/528e9b53b10985578cc97b0afe9b02bd343b9a1c8d3c9d2eb6a769aaf7f3c090-Screen_Recording_2025-07-03_at_3.34.10_PM_1.gif" width="75% " />

6. Once enabled, click **Show Setup Steps** to view the _Webhook URL_ and _JSON Body_. You must copy both, as you will need them to configure the webhook in CleverTap.

<Image align="center" alt="Webhook URL and Body" border={true} caption="Webhook URL and Body" src="https://files.readme.io/ad8c41b1691dd5a95e3f9df1985aa4d246053b8fa4d56f63f3fd9bec156f6f51-Screen_Recording_2025-07-03_at_3.37.36_PM_1.gif" width="75% " />

## Set Up Webhooks in CleverTap

To ensure CleverTap can trigger Mailmodo campaigns, you need to configure a Webhook in CleverTap.

### Configure Webhook

Set up a Webhook in CleverTap using the URL and body obtained in _Step 6_ of Set Up Trigger Campaigns in Mailmodo. This allows CleverTap to call Mailmodo whenever a campaign is triggered. To do so, perform the following steps:

1. In your CleverTap dashboard, go to _Settings_ > _Channels_  >  _Webhook_ > **+ Webhook**.
2. Provide a descriptive name for the Webhook (for example, _Mailmodo Trigger_).
3. Set the HTTP method to _POST_.
4. Paste the _Webhook URL_ copied from _step 6_ of [Set Up Trigger Campaigns in Mailmodo](doc:mailmodo#set-up-trigger-campaigns-in-mailmodo).
5. Click **Save**.

<Image align="center" alt="Webhook Setup in CleverTap" border={true} caption="Webhook Setup in CleverTap" src="https://files.readme.io/87223e8f928c6c641c71b4f4402364772a901b5825d7a472cd9c03a3c17b6727-image.png" width="65% " />

### Create a Webhook Campaign in CleverTap

Once the Webhook is configured, create a campaign that uses it. This ensures CleverTap can send campaign data (including `clevertap_id`) to Mailmodo in real time. To do so, perform the following steps:

1. In CleverTap, go to _Campaigns_ > _+ Campaign_ > _Webhook_.
2. Enter campaign details.
3. In the **What** section, select **Custom Body**.
4. Paste the JSON Body copied from _step 6_ of [Set Up Trigger Campaigns in Mailmodo](doc:mailmodo#set-up-trigger-campaigns-in-mailmodo).

Replace static values with dynamic values using [Liquid tags](doc:personalize-message-all#liquid-tags) to personalize the email. For example:

```json
{
  "email": "${user_email}",
  "data": {
    "first_name": "${first_name}",
    "subscription_plan": "${plan_type}"
  }
}
```

* `${user_email}` is replaced dynamically with each recipient’s email address.
* Additional properties (such as `first_name`, `plan_type`) can be added inside `data` for more personalization.

<Image align="center" alt="Liquid Tags in Webhook Body" border={true} caption="Liquid Tags in Webhook Body" src="https://files.readme.io/e16948b8581c4fa1a33c0a722723ec2ce08d7f699e56ecf167e79472b2597119-image.png" />

### Publish Campaign

Publishing the campaign activates the connection. Once live, Mailmodo sends engagement data (opens, clicks, unsubscribes, form submissions) back to CleverTap as custom events tied to the user profile.

* CleverTap sends campaign data (email ID, `clevertap_id`) to Mailmodo.
* Mailmodo triggers the configured email to the recipient.

<Image align="center" alt="Email Response" border={true} caption="Email Response" src="https://files.readme.io/660ad1e11fc14bc903172f2c274f314d1ad42936efb38c151871bc8034ffeb39-image.png" width="75% " />

* Mailmodo sends campaign engagement events (opens, clicks, unsubscribes, form submissions) back into CleverTap as **custom events** tied to the recipient’s profile.

<Image align="center" alt="CleverTap dashboard showing tracked custom events" border={true} caption="CleverTap dashboard showing tracked custom events" src="https://files.readme.io/24ce9fc8094d179938e04abe12279966d42abc31423eb24e66541ba2166cbd9b-image.png" width="75% " />

# FAQs

### How do CleverTap and Mailmodo work together?

This example shows the end-to-end flow of the integration:

* A CleverTap Webhook campaign triggers a Mailmodo interactive survey email.
* The recipient opens and submits the survey.
* Mailmodo sends **MM Email Opened** and **MM Email Form Submitted** events to CleverTap.
* CleverTap logs these events under the user’s profile, enabling segmentation and automated follow-ups (for example, sending an SMS to non-responders).
