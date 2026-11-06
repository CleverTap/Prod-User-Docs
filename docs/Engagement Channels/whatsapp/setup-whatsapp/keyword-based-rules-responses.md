---
title: Rules & Responses for Subscription Management
excerpt: >-
  Learn how to automate WhatsApp subscription actions using keywords, segments,
  and delivery errors.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Rules & Responses for Subscription Management let you automate subscription-related actions on WhatsApp, SMS and RCS based on incoming user messages or message delivery errors. For example, when users respond with `STOP`, CleverTap automatically unsubscribes them from WhatsApp, SMS or RCS  communication and sends a confirmation message.&#x20;

You can trigger subscription actions in the following ways:

- **Keyword-based:** An incoming message matches a configured keyword. Used for subscribe, unsubscribe, and support actions.
- **Segment-based:** Unsubscribes all users who match a defined segment. Use this to remove a specific group from WhatsApp, SMS or RCS communication without waiting for them to opt out.
- **Error-based:** Unsubscribes users when a delivery error indicates their number is invalid or unreachable, for example when a number is not registered on WhatsApp, has been deactivated, or has never opted in. You configure which error types trigger this.

## Subscription Rule Behavior

When a subscription rule is triggered, CleverTap updates the user profile to reflect the change in subscription status.

When an inbound message or a delivery error is received, CleverTap evaluates it against your configured rules:

- For keyword rules, CleverTap compares the incoming message against the configured keyword regardless of the casing. Casing variations in the keyword STOP, such as `stop`, `STOP`, and `Stop` all trigger the same rule. The keyword, as configured, appears in the resulting event regardless of how the user entered it.
- For error rules, CleverTap compares the delivery error received from the provider against the error types configured in your error-based unsubscribe rule.
- For segment rules, CleverTap evaluates users against the criteria defined in your segment.

When an unsubscribe is triggered through any of these rules, CleverTap updates the user profile as follows:

* **Subscription Status:** The user's subscription for the channel is set to unsubscribed. CleverTap sets the channel's subscription property, listed in the following table, to `false`. This property controls whether messages are delivered to the user profile.
* **Reachability:** The user is added to Do Not Disturb (DND) for the channel, so CleverTap treats them as unreachable on it.
* **Campaign Eligibility:** Because campaign targeting honors the subscription property, the user is automatically excluded from subsequent campaigns on that channel. No separate exclusion list is maintained.

| Channel  | Subscription property |
| -------- | --------------------- |
| WhatsApp | `MSG-whatsapp`        |
| SMS      | `MSG-sms`             |
| RCS      | `MSG-rcs`             |

A `Channel Unsubscribed` system event is logged on the user's timeline. For keyword-based subscribe actions, a `Channel Subscribed` event is logged instead. These events are available for analytics and audit.

<Callout icon="🚧" theme="warn">
  ### Note

  Unsubscribes cannot be reversed from the rul&#x65;**.** Once a user is unsubscribed through any method (keyword, segment, or error), the rule cannot re-subscribe them. The user must opt back in through another method, such as replying with a matching keyword configured under **Keyword-based subscribe**.
</Callout>

## Access Rules & Responses&#x20;

Rules and Responses is available under Subscription Management in the CleverTap dashboard. To access Rules & Responses, perform the following steps:

1. From the dashboard, navigate to _Settings > Setup > Subscription Management_.
2. Select the **Rules & responses** tab.
3. Select **WhatsApp**/ **SMS**/ **RCS.**


   <Image src="https://files.readme.io/b7d97da806bb9251310f9984944dbe940587d6a8725357a8cee287210968454d-rules_and_responses_.png" align="center" caption="Rules and Responses" border={true} />


   The following options are available:

- **Keyword-based subscribe:** _Subscribes_ users when an incoming message matches a configured keyword.
- **Keyword-based unsubscribe:** _Unsubscribes_ users when an incoming message matches a configured keyword.
- **Segment-based unsubscribe:** Unsubscribes all users who match a defined segment.
- **Keyword-based support:** Identifies incoming messages as support requests when they match a configured keyword.
- **Error-based unsubscribe:** Unsubscribes users when a delivery error indicates their number is invalid or unreachable, for example when a number is not registered on WhatsApp, has been deactivated, or has never opted in. You configure which error types trigger this.

A status indicator on each option shows whether it is active.

## Configure Keyword-Based Rules

_Set up the keyword criteria that subscribe, unsubscribe, or route users to support._

Keyword rules define how incoming messages are matched. The setup process is the same for the subscribe, unsubscribe, and support options.&#x20;

<Image src="https://files.readme.io/d7a347bf1890e00a1b60e13b91ead1d534199e17eceaf3211b972bab676fbce2-keyword_based_unsub.png" align="center" caption="Keyword-based unsubscribe" border={true} />


<br />

To configure a keyword-based rule, perform the following steps:&#x20;

1. Select **Keyword-based subscribe**, **Keyword-based unsubscribe**, or **Keyword-based support**.&#x20;
2. The _Channel_ is pre selected and cannot be changed.
3. For **Keyword-based subscribe** only, select the _Subscription Type_:&#x20;
   - **Single opt-in:** Subscribes the user as soon as their message matches a configured keyword.
   - **Double opt-in:** Sends a confirmation message to the user after a keyword match. The user is subscribed only after they respond to the confirmation message.

4) If you selected **Double opt-in**, set the _Dwell Time_, which is the period CleverTap waits for the user to respond to the confirmation message before the pending state expires. Enter a number and select the unit: **Minute(s)**, **Hour(s)**, or **Day(s)**. Dwell Time defaults to 30 days if left unset.
5) Select the _Subscription criteria_:
   - **Contains keyword:** Triggers the rule when the keyword appears anywhere in the message.
   - **Exact keyword:** Triggers the rule only when the entire message matches the keyword and contains no other text.
6) Enter one or more _Keywords_. Add additional keywords using the **+** option.
7) Click **Save**.\`

Keyword matching is case-insensitive, so you do not need to add separate entries for different casings of the same word.

After you save your keywords, the **Rules** and **Responses** tabs appear. Open the **Responses** tab to configure the message sent when the rule is triggered:

- Click **Add Message** to add a message per service provider.
- Select the service provider and click **View Message** to assign a template.
- To set a provider as the default, click **Set as Default**.

For **Double opt-in** rules, this message is the confirmation prompt. It is sent after a keyword match and asks the user to confirm their subscription.

<Callout icon="🚧" theme="warn">
  ### **Double opt-in pending state**

  While a user's confirmation is pending, they are set to DND and will not receive messages until they confirm or the Dwell Time window expires.
</Callout>

## Configure Segment-Based Unsubscribe

_Unsubscribe a defined group of users from WhatsApp, SMS or RCS without waiting for an inbound keyword.&#x20;_

<Image src="https://files.readme.io/fb80864c4ebbd2387c4cca404ff8d03ce4e8e726c1e9c9bf77165def785d5907-segment_based_unsub.png" align="center" caption="Segment-based unsubscribe" border={true} />


<br />

To configure a segment-based unsubscribe rule, perform the following steps:

1. Select **Segment-based unsubscribe**.
2. Select the _Segment_ type:
   - **Ad-hoc:** Build the segment inline using filter rules.
   - **Saved:** Select an existing segment.
3. For an ad-hoc segment, define your criteria under _Filter users_ (for example, _User property > Email > contains_ a value). Use the following options to refine the segment:
   - **Add Rule:** Add a condition.
   - **Add Rule Group:** Group conditions together.
   - **Add Exclusion Rules:** Exclude users from the segment.
4. Click **Calculate** in the _Estimate_ field to preview the number of users who match the defined criteria.
5. Click **Save**.

Users who match the segment are unsubscribed from WhatsApp, SMS or RCS with the profile updates described in the [subscription-rule-behavior](doc:keyword-based-rules-responses#subscription-rule-behavior) section.

## Configure Error-Based Unsubscribe

Error-based unsubscribe automatically removes users from your selected channel's communication when a delivery error indicates their number is invalid or unreachable. For example, if a message fails because the recipient's number is not registered on WhatsApp, CleverTap unsubscribes that user and stops sending to that number. You select the error types that trigger this behavior when configuring the rule. This helps you maintain a clean subscriber list and avoid spending on unreachable users.

<Image src="https://files.readme.io/6e9e09a19949c37617e73a9efb824486bfca50daace5bb7996df116ca3abe0f3-error_based_unsub.png" align="center" caption="Error-based unsubscribe" border={true} />


<br />

To configure an error-based unsubscribe rule, perform the following steps:

1. Select **Error-based unsubscribe**.
2. The _Channel_ is pre selected and cannot be changed.
3. Click the _Error code_ field to open the error code list.
4. Search for and select one or more error types that indicate the recipient's number is invalid or unreachable. Examples include _Recipient phone number invalid_, _Recipient not a WhatsApp user_, _Not opted in_, _Blacklisted_, and _Not reachable_. The field displays a count of selected error types. Avoid selecting provider authentication or permission errors, as these indicate a configuration issue on the sending side and should be investigated and fixed, not used to unsubscribe users.
5. Click **Save**.

When a configured error is received for a user's message, CleverTap automatically unsubscribes that user and logs a `Channel Unsubscribed` event.

## Configure Responses

Responses define the automated reply CleverTap sends to a user on the selected channel when their inbound message matches a configured keyword. For example, when a user sends `STOP`, CleverTap unsubscribes them and sends the configured response confirming that they will no longer receive messages. Responses are available for **Keyword-based subscribe**, **Keyword-based unsubscribe**, and **Keyword-based support**. They are not available for segment-based or error-based unsubscribe.

The **Responses** tab appears after you save your keywords.

### Create a Response

To create a response, perform the following steps:

1. Open the **Responses** tab.


   <Image src="https://files.readme.io/1c277eb9cdf54054be85c54d38fe11d4cfc7b176a67105e5607d3f36c2b15954-create_response.png" align="center" caption="Create Response" border={true} />


2. Click **Create Response**.&#x20;


   <Image src="https://files.readme.io/88e5a413229ea7f29a4d5c9af5dbfc6430fab295804553ee55184542fce6fe38-create_response_1.png" align="center" caption="Details and Setup" border={true} />


3. Under _Details_, enter the response _Name_.

4. The _Channel_ and _Category_ are auto-populated based on the keyword rule you are configuring and cannot be changed.Under _Setup_, select a _Service provider_.

5. Next to _Message/ Response_, click **Create Message** to open the WhatsApp, SMS or RCS message selector.

6. Add the message for your channel:
   - **WhatsApp:** Select an approved WhatsApp message template. Only templates approved in your WhatsApp account in the WhatsApp Business Manager are available. For more information, refer to [Create WhatsApp Messages](doc:whatsapp-editor).
   - **SMS:** Enter the _Message_ body. For more information, refer to [SMS](doc:sms) and [Regulation Impact](doc:regulation-impact).
   - **RCS:** Select an RCS template saved for your provider. For carriers that require approval, such as in India, only approved templates are available. Their content is locked, and you can fill in only the placeholder values, such as `{{1}}`. For carriers that don't require approval, you can build a free-form template. For more information, refer to [RCS Message Templates](doc:rcs-message-templates) and [RCS Message Editor](doc:rcs-message-editor).&#x20;

7. Click **Publish**.&#x20;

The response is sent automatically when an incoming message matches a configured keyword. For unsubscribe rules, the user is marked as unsubscribed immediately on a keyword match, regardless of whether the response message is delivered successfully.

### Access Responses

All responses associated with the rule appear in the **Responses** tab, showing the response _Name_, _Service provider_, _Created on_ date, and _Created by_ user.

## Manage Responses

_Add, delete, or pause the responses associated with your rule._

From the **Responses** tab, you can perform the following actions:

- **Add responses:** Only one response per service provider can be configured.
- **Delete response:** Remove responses that are no longer required.
- **Pause rule:** Use the pause control in the rule header to stop responses. When a rule is paused, responses are not sent until the rule is resumed. A status indicator shows whether the rule is **Running** or paused.

## Monitor Performance

_Review how users interact with your configured subscription rules._

The **Stats** tab shows how users interact with a configured rule. The available metrics depend on the rule type.

The following controls are common to all Stats views:

- **Provider filter:** Filter metrics by a specific WhatsApp, SMS or RCS provider, where supported.
- **Overall / Keywords:** Switch between an aggregate trend and a per-keyword (or per-error) breakdown.
- **Granularity:** View the trend by **Day**, **Week**, or **Month**.
- **Trend:** A date-wise, time-series chart of users for the selected period.

### Keyword-Based Subscribe Stats

View the performance of your opt-in keywords and their numbers.

-


<Image src="https://files.readme.io/007e8f521c7f4861aa692bb1c45b4268f2709a91773dc417f19f389bf60a6888-stats.png" align="center" caption="Keyword-based subscribe stats" border={true} />


- **Total opt-ins:** Total number of users who subscribed using keyword-based requests.&#x20;

- **Opt-in rate:** Total opt-ins as a percentage of other inbound replies.

- **Re-subscribed users:** Users who were previously unsubscribed and subscribed again using a keyword.

- **Unmatched keywords:** The most common inbound replies that did not match any configured keyword.

- **Trend:** One trendline per configured opt-in keyword.

### Keyword-Based Unsubscribe Stats&#x20;

Track how many users opted out by keyword and which keywords drive the most unsubscribes.&#x20;


<Image src="https://files.readme.io/485f6e0cea49760a1ba45535330ce1dae45a9a6fb450103fe49b88828314e61e-stats_2.png" align="center" caption="Keyword-based unsubscribe stats" border={true} />


<br />

- **Total opt-outs:** Total number of users who unsubscribed using keyword-based requests.
- **Opt-out rate:** Total opt-outs as a percentage of active users.
- **Trend:** One line per configured opt-out keyword.

### Keyword-Based Support Stats

Track how many users requested support by keyword and how many later unsubscribed.&#x20;


<Image src="https://files.readme.io/03c708372682d1991e8d5a0b20c85ac39fb0bc1684b12d943dcd3b4ad5d8f262-stats_4.png" align="center" caption="Keyword-based support stats" border={true} />


<br />

- **Support Requests:** Total number of users who sent a configured support keyword.
- **Post-Support Unsubscribed:** Number of users who requested support and later unsubscribed, shown against the total support requests.
- **Trend:** A single line of inbound messages matching configured support keywords.

### Error-Based Unsubscribe Stats&#x20;

Track how many users were automatically unsubscribed and which errors triggered them.


<Image src="https://files.readme.io/3766965d5851399d07c8c84a01766fb736abb7acb8f8663fe0e2ba5054a98ea9-stats_5.png" align="center" caption="Error-based unsubscribe stats" border={true} />


<br />

- **Total auto-unsubscriptions:** Total number of users automatically unsubscribed due to a configured error.
- **Unsubscription rate:** Total auto-unsubscriptions as a percentage of active users.
- **Trend:** One trendline per selected error code.

### Segment-Based Unsubscribe Stats&#x20;

Track how many users were unsubscribed through the segment rule and how many returned.


<Image src="https://files.readme.io/cb279f6346fcd3a21a47007c77d3b440aca710d3b5ca7ae6b2b024393c3a80f1-stats_3.png" align="center" caption="Segment-based unsubscribe stats" border={true} />


<br />

- **Total unsubscriptions:** Total number of users unsubscribed through the segment rule.
- **Unsubscription rate:** Total unsubscriptions as a percentage of active users.
- **Reactivation rate:** Users who were unsubscribed through the segment rule and later subscribed again using a keyword.
- **Trend:** A single trendline of unsubscriptions over time.