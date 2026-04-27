---
title: Messaging Frequency Caps
excerpt: >-
  Frequency caps limit how often users receive messages when they qualify for
  multiple or recurring campaigns.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Frequency Management helps you control how often users receive messages across campaigns and journeys. When running multiple campaigns simultaneously, users may qualify for several messages in a short period or repeatedly qualify for recurring and triggered campaigns. Without proper controls, this can lead to message fatigue, reduced engagement, and a poor user experience.

To address this, CleverTap provides multiple frequency control capabilities that help you manage message volume, spacing, and delivery:

* [Message Limits](https://staging.docs.user.clevertap.net/docs/messaging-frequency-caps#message-limits): control how many messages a user can receive over a defined time period
* [Message Gaps](https://staging.docs.user.clevertap.net/docs/messaging-frequency-caps#message-gaps): control the minimum time interval between messages
* [Throttle Limits](https://staging.docs.user.clevertap.net/docs/messaging-frequency-caps#throttle-limits): control the rate at which messages are delivered
* [Session Limits](https://staging.docs.user.clevertap.net/docs/messaging-frequency-caps#session-limits): control how many messages a user receives within a single session

Together, these controls ensure that users receive relevant communication without being overwhelmed.

<Image align="center" alt="Frequency Management" border={true} caption="Frequency Management" src="https://files.readme.io/6cf0c7cd245818fc4320feb56983b8af69c0859a42b98510c3a78ee94766446e-image.png" />

For example, let's assume a user qualifies for multiple campaigns simultaneously. Without any limits on messaging, the user could receive several messages within minutes. Even if you set a limit of 3 messages per day, those messages could still be delivered back-to-back. To prevent this, you need to control both how many messages are sent and how they are spaced out.

Frequency Management provides multiple controls to help you manage different aspects of messaging. In this case, a daily message limit of 3 and a message gap of 2 hours would mean the user receives no more than 3 messages per day, each spaced at least 2 hours apart. This setup ensures a balanced and non-intrusive experience.

# Message Limits

Message Limits let you control how many messages a user can receive over a defined time period. You can define limits based on conditions such as channel, campaign type, labels, segment type, or team. This allows you to apply granular, rule-based controls across different messaging use cases, such as promotional campaigns, alerts, or lifecycle communications.

Message Limits are part of Frequency Management and help ensure users receive relevant communication without being overwhelmed.

<Image align="center" border={true} caption="Message Limits" src="https://files.readme.io/a0258157efcafc7a336a089a4300728573985cd7e93d3e4f6f4757dadef474b5-image.png" />

## Rule Types

Message Limits are configured using rules. Each rule defines who the limit applies to and how it is enforced.

You can create rules based on the following attributes:

* **Channel**: Applies to Push Notifications, Email, SMS, WhatsApp, Web Push, and Webhook.

* **Campaign Type**: Includes Campaigns, Journeys, Bulletins, and Reminders.

* **Labels**: Used to categorize campaigns (for example, Promotional, Lifecycle).

* **Segment Type**: Includes Past Behavior (PBS), Live, and External Trigger campaigns.

* **Team**: Applicable only for accounts with Teams enabled (Beta feature). Limits can be scoped to specific teams.

You can use any one or multiple attributes to define a rule. For each attribute, you can select only one value. Combine multiple attributes to create more specific and targeted rules.

For example, you can set a cadence of 3 push notifications over 7 days. This guarantees that users will receive no more than three push messages within that time period, regardless of the number of campaigns for which they qualify.

<Callout icon="📘" theme="info">
  #### Note

  You can create a maximum of 25 Message Limit rules per account.
</Callout>

## Create a Message Limit

To create a Message Limit:

1. Go to _Settings_ > _Frequency Management_.
2. Click **Create Message Limit**.
3. In the _Setup_ section, enter a **Name** for the limit. Define **Conditions**:
   * Select attributes such as Label, Engagement Type, Channel, Segment Type, or Team.
   * Click **Add Rule** to include additional conditions.
4. In the _Send Limit_ section, configure daily, weekly, and monthly advance limits. Enter the maximum number of messages allowed per user.

<Image align="center" alt="Create New Message Limits" border={true} caption="Create New Message Limits" src="https://files.readme.io/30104d2dde63a87f3aa9e4bb0dca36e92487fe0bc5360c6d8462d69ea7158708-2026-04-22_12-55-21_2.gif" />

5. If you have previously configured limits using the older setup, click **Switch to Advance Limits** to configure Message Limits. Once you switch, your existing limits will be removed, and you can recreate limits using the new rule-based setup.

<Image align="center" alt="Create Message Limit" border={true} caption="Create Message Limit" src="https://files.readme.io/8933aee5151eb727ed314c9b8d2485ef4f4746941df3ba6397b30a057b5fc0ce-2026-02-11_14-51-56_1.gif" />

6. Click **Create** to save the configuration.

> 📘 Applying Multiple Limits
>
> A user may qualify for multiple message limits at the same time, for example, limits defined across different time durations such as daily, weekly, and monthly. When this happens, CleverTap evaluates all applicable limits and enforces the most restrictive limit to determine whether a message can be delivered.
>
> This ensures that users are not over-messaged across different time windows. For example, assume the following limits are configured:
>
> * Daily limit = 3 messages
> * Weekly limit = 10 messages
>
> If a user has already received 3 messages in a day:
>
> * No additional messages will be delivered on that day, even though the weekly limit has not been reached.
>
> Similarly, if a user has received 10 messages in a week:
>
> * No further messages will be delivered for the rest of the week, even if the user has not reached the daily limit for the remaining days of the week.
>
> In all cases, CleverTap enforces the strictest applicable limit at the time of delivery.

## Counting Towards Limits

By default, Global Message Limits are enabled for a campaign. If you clear this option, you can then decide how the message should interact with Message Limits.

When sending a campaign, you can decide whether the message counts toward the overall limits. This gives you flexibility to control how specific messages are treated within your frequency rules. In a campaign, go to _Delivery Preferences_, and select either of the following options:

* _Count towards limits_: The sent message is counted toward the user’s limit. If the limit is reached, no further messages are sent. This is useful for standard marketing campaigns. For example, if a user has a limit of 3 messages per day and receives 4 campaigns with one message each that count toward limits, the fourth campaign will not be delivered.
* _Don't count towards limits_: The sent message is delivered but does not count toward the user’s limit. This is useful for notifications such as time-sensitive updates or critical alerts. For example, let's say the daily limit is 3 messages, and 2 campaigns have already been counted and sent. If a third campaign marked as _Don’t count towards limits_ is sent, it will be delivered without affecting the limit. This means another campaign that counts toward limits can still send messages.

<Image align="center" border={true} caption="Global Message Limits" src="https://files.readme.io/29ec28c7e315bb445ee761afe738472edc2a8b677c471f6cbbc32a318280d392-image.png" />

## Cross-Channel Limits

A default Cross-Channel Limit is set under Message Limits. This rule applies to all channels, labels, engagement types, and segment types by default (that is, all attributes are selected) and controls the total number of messages a user can receive across all engagements.

<Image align="center" alt="Cross-Channel Limits" border={true} caption="Cross-Channel Limits" src="https://files.readme.io/531fed5f828a62bf9d8ab8208e71386e5ebb670e45c18d1f80f5831b80c65df0-image.png" />

## Use Cases and Scenarios

The following scenarios demonstrate how Message Limits can be configured for different use cases.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Scenario
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Scenario 1: Cross-channel message limit**
      </td>

      <td>
        You want to control the total number of messages a user receives across all engagements and channels. Configure a limit of 4 messages per day without adding any conditions. This ensures the user receives a maximum of 4 messages per day, regardless of how many campaigns they qualify for.

                <Image border={true} width="75% " src="https://files.readme.io/ff83d99e3496af7a861500e7fc34384798c184f5bf479b3f6b9d88e218faba76-image.png" className="border" />
      </td>
    </tr>

    <tr>
      <td>
        **Scenario 2: Channel-specific limit**
      </td>

      <td>
        You want to restrict communication on a specific channel. Add a rule that sets Channel to Email and limits it to 2 emails per week. This ensures the user receives no more than 2 emails per week, even if they qualify for multiple email campaigns.

                <Image border={true} width="75% " src="https://files.readme.io/6aa1ddc9922042dce16b6f9cb25979263f7be23ad38c373501a68b32c38979f5-image.png" className="border" />
      </td>
    </tr>

    <tr>
      <td>
        **Scenario 3: Engagement based limit**
      </td>

      <td>
        You want to limit messages sent through a specific engagement type. Add a rule that sets Engagement Type to Journeys and limits it to 3 messages per month. This ensures that messages sent via journeys are capped, regardless of other journeys or campaigns running in the same journey in parallel.

                <Image border={true} width="75% " src="https://files.readme.io/03e883306d3f4e548e6e2850be326a5e5d193ad4debe5091b84aa133982ce26c-image.png" className="border" />
      </td>
    </tr>

    <tr>
      <td>
        **Scenario 4: Combined rule (multiple conditions)**
      </td>

      <td>
        You want to apply a more specific rule for specific engagements. Add conditions such as Channel = Push, Engagement Type = Campaigns, and Label = monsoon sale, and set the limit to 5 messages per day. This ensures only push campaigns are restricted to 5 per day.

                <Image border={true} width="75% " src="https://files.readme.io/d0db1e93af6af3169e9d5056954c8dcb415373ee29cc76c2e5512e3311fff119-image.png" className="border" />
      </td>
    </tr>

    <tr>
      <td>
        **Scenario 5: Multi-duration limits**
      </td>

      <td>
        You want to apply stricter limits to batch campaigns while controlling messaging across different time windows. Add a rule where Segment Type = PBS, set a Daily limit = 3, and a Weekly limit = 10. This ensures users receive no more than 3 messages per day and no more than 10 per week, with the most restrictive limit applied at any given time.

                <Image border={true} width="75% " src="https://files.readme.io/b3da92bf788cf76979129bdd3cd6fd1ac9fe7a2688b0fd463b35bf882a0eb8da-image.png" className="border" />
      </td>
    </tr>

    <tr>
      <td>
        **Scenario 6: Multiple rules applied (most restrictive rule)**
      </td>

      <td>
        You want to apply limits when a user qualifies for multiple rules at the same time. For example, a rule with Channel = Email (limit: 2/day) and another rule with Engagement Type = Journeys (limit: 3/day) are both applicable. If a campaign satisfies both conditions (for example, an email sent via a journey), CleverTap evaluates both rules and applies the most restrictive limit. In this case, the user will receive no more than 2 messages per day, as defined by the stricter rule.
      </td>
    </tr>

    <tr>
      <td>
        **Scenario 7: Urgent campaign excluded from limits**
      </td>

      <td>
        You need to send a high-priority or urgent campaign (for example, a critical alert) that should not be restricted by any limits. While setting up the campaign, you can disable Global Message Limits and select **Don’t count towards limits**. This ensures that the message is delivered to all eligible users regardless of existing limits, and it also does not consume the user’s limit quota, allowing regular campaigns to continue unaffected.
      </td>
    </tr>
  </tbody>
</Table>

## Editing Message Limits

You can modify an existing Message Limit at any time. The impact depends on what is changed:

* **Updating Send Limits**: If you change the send limit (daily, weekly, or monthly), then:
  * The updated limit is applied immediately, and the user’s existing usage is adjusted accordingly.
* **Updating Conditions**: If you modify the rule conditions (such as channel, label, or segment type), then:
  * The rule is treated as a new rule.
  * Previous frequency limits are not carried forward.

## Filter Message Limits

You can use filters to quickly search your Message Limits by Channel, Time Period, creator, and more. To do so, perform the following steps:

1. Click the ![](https://files.readme.io/ac0ed6a-Filter_icon.png) icon. The _Filters_ window opens on the left side of the screen.

<Image align="center" border={true} caption="Filter Message Limits" src="https://files.readme.io/672567760095d36bcf502c8cbd1a6b881a41cd6acfa8dc6dcf2431d926d1a9bf-image.png" />

2. Select the required filters and click **Apply** to view results. Filters are organized separately for Active and Archived campaigns. Deleted Limits can be viewed using the _Archived_ Filter.

<Image align="center" border={true} caption="Apply and Reset Filters" src="https://files.readme.io/ddf5ee64e431915640f30bc09acd69e19685a99832daf08fae2d56251a979b7e-2026-02-13_18-17-08_1.gif" />

The following table describes the available filters:

| Filter Section             | Description                                                                                                                                                                                                                                                                                            |
| :------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Mobile Channel**         | Filter campaigns by mobile channels, such as Push Notification, In-App Message, App Inbox, and Native Display.                                                                                                                                                                                         |
| **Web Channel**            | Filter campaigns by web channels, such as Web Push Notifications.                                                                                                                                                                                                                                      |
| **Direct-to-User Channel** | Filter campaigns by direct communication channels such as Email, SMS, and WhatsApp.                                                                                                                                                                                                                    |
| **Engagement Type**        | Filter campaigns by engagement types such as Campaign, Journey, Bulletin, and Reminder.                                                                                                                                                                                                                |
| **Segment Type**           | Filter campaigns based on segment types such as Past Behavior, In-Action, Action, On Date/Time, and External Trigger.                                                                                                                                                                                  |
| **Created By**             | Filter campaigns by the creator's email ID.                                                                                                                                                                                                                                                            |
| **Label**                  | Filter campaigns based on assigned labels. Click **Manage Labels** to navigate to the _Labels_ page under Account Setup, where you can create or manage labels based on your role. For more information, refer to [Message Labels](https://docs.clevertap.com/docs/intro-to-campaigns#message-labels). |
| **Teams**                  | Filter campaigns based on the associated teams.                                                                                                                                                                                                                                                        |

You can click **Reset** to reset all the applied filters.

# Message Gaps

Message Gaps let you control the minimum time interval between messages sent to a user across campaigns and journeys. This ensures that users do not receive multiple messages in quick succession, even if they qualify for multiple campaigns simultaneously. For example:

* If the Message Gap is set to 4 hours, and a user receives a message at 10:00 AM
* The next message can only be delivered after 2:00 PM
* If a user qualifies for multiple messages within the gap window:

  * Only the first message is delivered
  * Subsequent messages are skipped until the gap is satisfied

## Supported Range

You can configure message gaps within the following range:

* **Minimum:** 15 minutes
* **Maximum:** 7 days

## Supported Channels

You can configure message gaps for the following channels: Push Notifications, Email, SMS, WhatsApp, and Web Push.

<Image align="center" border={true} caption="Message Gaps" src="https://files.readme.io/ac8962d99d19c9410aa0805b5e0e8c68b09c8100402682dc613c7abbb04cb2f6-image.png" />

# Throttle Limits

Throttle is a feature that lets you control the rate at which notifications are sent to end users. Instead of sending messages to all users at once, throttling spreads delivery over a period of time. This helps avoid sending a large number of notifications simultaneously. By controlling notification delivery, throttling indirectly reduces sudden spikes in user activity on your platform (for example, during events like limited stock sales). This ensures a smoother user experience and helps maintain system performance.

Finding the optimal throttling rate is crucial in ensuring the effectiveness of your engagements. A high throttling rate can overload your platform, while a low rate can cause engagements to run longer than expected, affecting the relevance of your messages to end users. Therefore, it is important to strike a balance by setting a reasonable throttling rate that aligns with your engagement reach and frequency, ensuring your messaging stays relevant without overloading your platform.

<Callout icon="📘" theme="info">
  #### Throttle Limit Recommendations

  Check that you always set throttle limit to more than 100 messages when setting the Ad Hoc limit.

  Always check that your throttle limit is set high enough to prevent messages from running for multiple days, as they will stop delivering after the third day. This ensures that the relevance of messages is maintained.

  The _restricted reach_ of your messages is displayed in a banner below the _Global throttle limits_. Check that the restricted reach is higher than your expected reach to ensure that all users receive the messages.
</Callout>

## Types of Throttle

There are two types of throttle:

* _Global Limit_: Select this option to apply global throttle settings to control the overall rate of message delivery. This setting ensures a consistent throttling rate across all campaigns or engagement nodes in journeys.
* _Ad hoc Limit_: Select this option if you want to override the global throttle limits for specific campaigns or engagement nodes in journeys. This option provides more granular control over message delivery rates tailored to individual requirements.

### Global Limit

The Global Limit is a default throttle setting that applies to all campaigns. This limit is set globally and can be configured from the _Settings_ section.

<Image align="center" border={true} caption="Throttle Limits" src="https://files.readme.io/8fbb4e4dc2ffec6a6d46501181e06ca4c684a9416392fdb668b866a79605e7d2-image.png" />

This is now the global limit for all your campaigns. You can check this limit from the Campaigns by navigating to _Delivery preferences_ under the  _When_ section.

<Image align="center" border={true} caption="Global Limits" src="https://files.readme.io/d7499e692c7bcaa828393c4fa1bef72fef61c20ea3971b817c3c48f81b85f260-image.png" />

<Callout icon="📘" theme="info">
  #### Note

  * If Global Throttle Limits (GTL) are not set in global settings, you can still configure them for a specific campaign or journey.
    * For a Campaign, navigate to the  _When_ section > _Delivery Preferences_ > _Ad Hoc limit_.
    * For a Journey, select the specific Engagement node in the _Journey_ setup > _When_ section >  _Delivery Preferences_ > _Ad Hoc limit_.
  * The GTL checkbox is always enabled in Campaigns, similar to Journeys, allowing users to set ad hoc limits even if GTL is not configured in global settings.

  <Image align="center" alt="Delivery Preferences" border={true} caption="Delivery Preferences" src="https://files.readme.io/3d991d9012fa04d6733f6492077aa9cac5144c48704c96faf1918256379fb2ad-2025-03-07_21-20-08_2.gif" />
</Callout>

### Ad hoc Limit

The Ad hoc Limit lets you set a custom throttle limit for a specific campaign, overriding the Global Throttle settings for that specific campaign. This is useful when you want to apply a different throttle limit for a particular campaign without changing the global settings.

1. Go to the _When_ section > _Delivery preferences_. The Delivery preferences section displays the _Global Limit_ and the _Ad Hoc Limit_.
2. Select _Ad Hoc_ Limit to change throttle the message from the current campaign.
3. Enter the value and click **Done**.

<Image align="center" alt="Set Adhoc Limit" border={true} caption="Set Adhoc Limit" src="https://files.readme.io/c2f7a0e87b66c3982f6bdbbfa8ea5be7f2909bbb0fcfabbdc1980f77a14a5180-Screenshot_2025-03-05_at_1.04.27_PM.png" />

The Ad Hoc limit applies only to the current campaign or an engagement node in journeys.

### Throttling in Journeys

For Journeys, throttle limits for the engagement nodes are the same as the Campaign throttle limits for Push notifications, SMS, Email, Webhooks, and WhatsApp.

<Image align="center" alt="Set Up Throttle Limits from Journeys" border={true} caption="Set Up Throttle Limits from Journeys" src="https://files.readme.io/922bb5856b33369c8cfd49ca4cef6f556207ba2ed333bbfc2f7c834c319176bf-2025-03-07_21-40-12_1.gif" />

Depending on the time settings within a Journey, throttling may be allowed or disallowed:

* **Timezone**: The Account Timezone setting provides a centralized way to manage and schedule campaigns, ensuring consistency in timing and reporting across the entire user base. User Timezone settings are designed to send messages at the timezone the user was last active. Applying throttling in this context could cause delays in message delivery, disrupting optimal engagement times and reducing the overall effectiveness of the communication. To avoid this, throttling is allowed only when the messages are scheduled based on the Account Timezone. If you still schedule messages based on the User Timezone, a popup notifies you that throttling will be disabled for campaign limits. Throttling is permitted when you schedule messages based on the User Timezone only if you select the _Exclude the node from user timezone_ option.

<Image align="center" alt="Throttling Permitted When Scheduling Campaigns Based on Account Timezone" border={true} caption="Throttling Permitted When Scheduling Campaigns Based on Account Timezone" src="https://files.readme.io/acbe90c-Available_in_Account_Timezone.gif" />

* **Best Time Campaigns**: The Best Time setting optimizes message delivery by sending messages at times when users are most likely to engage, based on their individual behavior and activity patterns.  
  Throttling is not permitted in this context because it could delay message delivery, disrupt the optimized timing, and reduce the overall effectiveness of the campaign. Additionally, throttling would undermine the personalized nature of Best Time messaging by introducing delivery inconsistencies, potentially diminishing the user experience. To ensure messages are delivered at the optimal time, CleverTap disables throttling for campaigns that use Best Time, helping maximize engagement success.

<Image align="center" border={true} src="https://files.readme.io/132f464-Throttling_Not_Permitted_for_Best_Time_Campaigns_.gif" className="border" />

* **Past Behavior Segment (PBS) Node followed by Engagement Node**: When a PBS node is followed by an engagement node, throttling is allowed on the engagement node. This setup supports controlling message delivery while targeting users based on their past behavior.
* **Segment Action Node with Zero Sleep Time**: When a segment action node with zero sleep time is added before an engagement node, CleverTap automatically removes throttling for the following engagement node. Zero sleep time indicates that users must proceed immediately from the segment action to the next step without delay. In this scenario, throttling, which controls message delivery rates by spreading them out over time, conflicts with the intent of instant progression. By disabling throttling, CleverTap ensures that messages are delivered in real time, preserving their relevance and impact.  
  Additionally, when this configuration is applied, the system prompts for user confirmation, ensuring you are aware that the following engagement node will no longer be subject to throttling limits.

<Image align="center" alt="Segment Action Node with Zero Sleep Time" border={true} caption="Segment Action Node with Zero Sleep Time" src="https://files.readme.io/694d0f1-Segment_Action_with_Zero_Sleep_Time.gif" />

However, if you set a sleep time of more than 24 hours, throttle limits will apply for the engagement node that follows the segment action node. 

<Image align="center" alt="Segment Action Node with Sleep Time Greater Than One Day" border={true} caption="Segment Action Node with Sleep Time Greater Than One Day" src="https://files.readme.io/0e1157d-Segment_Action_Node_with_Sleep_Time_Greater_than_One_Day.gif" />

* **Segment Action Node with Sleep Time without Send at Specific Time**: When a sleep time is added after a node without enabling _Send at specific time_, CleverTap carries forward the throttle configuration from the previous engagement node. For example, if there is a 1-day sleep time after a throttled engagement node, CleverTap ensures that the subsequent engagement is sent exactly 1 day after the previous engagement was delivered to each user. Allowing throttle configuration in the second engagement node, in this case, would introduce additional delays, as both nodes would apply throttling sequentially. This could lead to unintended gaps in message delivery, extending the overall time it takes users to progress through the journey.
* **Segment Action Node with Sleep Time with Send at Specific Time**: When a sleep time is added with _Send at specific time_ enabled, CleverTap allows throttle configuration for the subsequent engagement node. Consider a scenario with a 1-day sleep time set to trigger at 10:00 AM and a throttle applied in the previous node. If a user received the first engagement at 10:00 AM on March 11, they would reach the next node at 10:00 AM on March 12. Users who received the first message later in the day on March 11 would then receive the next message at 10:00 AM on March 13, and so on. Since delivery is already scheduled to a fixed time, additional throttling can be configured safely, helping control volume without causing excessive delays.

## Session Limits

Session Limits let you control how many messages a user can receive within a single session, per day. A session refers to a period of continuous user activity in your app. A new session typically starts when a user opens the app and becomes active, or the app is brought to the foreground after being inactive for a defined period.

Session Limits prevent users from being overwhelmed with multiple messages during an active session with your app, enhancing the in-app user experience. They are supported for In-App Messages, Web Inbox, and Web Popup channels.

For example, if you set a session limit of 2 messages per session per day, a user who opens your app will receive at most two messages during that session, even if the user is qualified for multiple campaigns. If the user closes the app and returns later, starting a new session, they can again receive up to 2 messages (subject to daily limits).

<Callout icon="📘" theme="info">
  Note

  Session Limits operate independently of Advanced Frequency Limits and campaign-level caps.
</Callout>

To configure Session Limits:

1. Go to _Settings_ > _Frequency Management_.
2. Navigate to the _Session Limits_ tab.
3. Click **Add Session Limits**.
4. Enter the maximum number of messages allowed per user, per session, per day.
5. Click **Save**.

<Image align="center" border={true} caption="Session Limits" src="https://files.readme.io/6b82e67170ba2602fb6b12794c8722483fb3ccd2832ad124d027d7fb8383b99f-image.png" />

# FAQs

### What happens when a frequency cap applies to a user?

In such cases, CleverTap does not deliver the associated message. The dropped messages are accounted for in the campaign report error table.

### What happens when I edit an existing Message Limit?

If you update the send limits (daily/weekly/monthly), the new limits are applied immediately and existing usage is adjusted accordingly.

If you update the rule conditions (such as channel, label, or segment type), the rule is treated as a new rule and previous usage is not carried forward.

### What happens when multiple message limits apply to the same user?

If multiple limits apply, CleverTap evaluates all applicable rules and enforces the most restrictive limit. For example, if:

* Global limit = 10 messages/day
* Promotional limit = 3 messages/day

The user will receive a maximum of 3 promotional messages per day, even though the global limit allows more.

### What happens when both Message Limits and Message Gaps are configured?

Both controls are evaluated independently. Message Limits control how many messages can be sent. Message Gaps (dwell time) control when the next message can be sent. A message is delivered only if:

* The user is within the allowed limit, and
* The required time gap since the last message has passed.

### How does the User DND Set error occur?

The _User DND Set_ error occurs when you qualify users for a campaign despite unsubscribing on the target device. This error indicates that these users have been routed to the error bucket.

### Is there a limit to the number of Message Limit rules I can create?

Yes, you can create a maximum of 25 Message Limit rules per account.

### What is the Frequency Caps Exceed error?

This feature limits the total number of messages that can be scheduled per day for a user, taking into account all active devices and across different communication channels.

Navigate to _Settings_ > _Engage_ > _Setup_ > _Frequency Management_ to cap the frequency for various channels.

From the _Frequency Management_ page, you can define the number of messages you want to send to each user in X number of days.

You can also specify the following:

* _Message Gap_ is the gap you want to keep between messages.
* _Throttle_ controls the flow of your messages.

For more information on Message Gaps, refer to [Message Gaps](doc:messaging-frequency-caps#section-message-gaps-between-messages).

For more information on throttling, refer to [Throttle](doc:messaging-frequency-caps#section-throttle).

Now, when you create a campaign, and you want to disable the _Global frequency limit_, clear the _Global Campaign Limit_ option under the _Who_ section. The _Global Campaign Limit_ is enabled by default.

### Do Message Limits apply across both campaigns and journeys?

Yes, Message Limits are applied across all campaigns and journey nodes, unless explicitly bypassed.

### What happens if a user qualifies for multiple campaigns at the same time?

If multiple campaigns are triggered simultaneously, _Message Limits_ ensure the user's notifications does not exceed allowed volume, while _Message Gaps_ ensure messages are spaced out. Only the messages that satisfy both conditions are delivered.
