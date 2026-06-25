---
title: Journey Events
excerpt: >-
  Track when users enter and exit a CleverTap Journey using two system-generated
  events: Journey Qualified and Journey Exited and use them to power segments,
  campaigns, and follow-up journeys.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

When users move through a CleverTap Journey, entering, progressing, and eventually leaving, CleverTap now records these moments as system events.

Journey Events give you a clear, real-time record of which users entered a specific journey and how they left it. You can use this data to build smarter segments, trigger follow-up campaigns, analyze performance, and prevent users from receiving conflicting messaging across multiple journeys.

<Callout icon="📘" theme="info">
  ### Note

  Journey Events are only raised for journeys published after this feature is enabled on your account.

  Events will not be raised retroactively for journeys that were already running before the feature launch.
</Callout>

# Journey Events and Properties

CleverTap raises two Journey Events automatically:

- Journey Qualified: Raised when a user enters a journey
- Journey Exited: Raised when a user leaves a journey

Both events carry a set of properties that tell you more about the context of that entry or exit. These properties can be used in segments, analytics filters, and exports.

## Journey Qualified

The Journey Qualified event is raised every time a user enters a journey. If a user exits and re-enters the same journey (re-entry), a new Journey Qualified event is raised for each entry.

### Entry Types

There are six ways a user can qualify for a journey. Each has a different trigger and timing for when Journey Qualified is raised:

| Entry Type            | How it works                                                               | Timing                                                                   |
| :-------------------- | :------------------------------------------------------------------------- | :----------------------------------------------------------------------- |
| **Action Segment**    | User performs an action, on app or web, that triggers journey entry        | Immediate                                                                |
| **Inaction Segment**  | _User does not perform a specific action after a defined time period_      | After the inaction time period elapses                                   |
| **PBS Entry Segment** | User is evaluated against a Past Behavior Segment                          | Immediate for first run; midnight for subsequent runs (Account Timezone) |
| **Date-Time Target**  | User is scheduled for entry at a specific date and time                    | Immediate (same-day) or Midnight run (Future date)                       |
| **Journey Trigger**   | User reaches a specific step in Journey A, triggering entry into Journey B | Immediate if upstream is action-based; same-night if upstream is PBS     |

Journey Qualified is raised for every version of a journey published after this feature is enabled. The Version Number property tells you exactly which version the user entered. When you update and republish a journey, users entering the new version carry the updated version number.

### Event Properties

The following table lists the Journey Entry event properties:

| Property                      | Description                                                                                                                                   | Data Type | Example Value         |
| :---------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------- | :-------- | :-------------------- |
| **Journey ID**                | The unique numeric ID of the journey.                                                                                                         | Integer   | 10482                 |
| **Journey Name**              | The name of the journey.                                                                                                                      | String    | Onboarding Flow – Nov |
| **Entry Type**                | Indicates whether this entry can be used in a real-time (Live) segment or a batch (Past Behavior) segment. Values: 'Live' or 'Past Behavior'. | String    | Past Behaviour        |
| **Version Number**            | The version of the journey the user entered.                                                                                                  | Integer   | 2                     |
| **Control Group User**        | Set to _True_ if the user is part of any control group in this journey. If the user is not in a control group, this property is not raised.   | Boolean   | True                  |
| **Control Group Type**        | Populated only when _Control Group User_ is _True_.  Indicates which control group the user belongs to: _System_, _Journey_, or _Custom_.     | String    | Custom                |
| **Custom Control Group Name** | Populated only when _Control Group Type_ is _Custom_.  Contains the name of the custom control group.                                         | String    | High-Value Users CG   |

<Callout icon="📘" theme="info">
  ### Note

  For regular journey participants (Target Group users), control group properties are not raised; they are absent from the event record.
</Callout>

### Behavior Rules

The following table provides information about when and how quickly a Journey Qualified is raised, depending on the type of entry or goal segment configured in the journey:

| Entry Type                                                    | When is Journey Qualified raised?                                                                                                                                                                                                                     |
| :------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Live Action trigger (for example, user performs an event)** | Raised immediately with no delay. If the journey was itself triggered by a PBS entry in another journey (J1), there may be a delay of a few hours.                                                                                                    |
| **Live Action multi-trigger**                                 | Raised immediately with no delay. The same cross-journey PBS delay applies if J1 uses PBS.                                                                                                                                                            |
| **Live Inaction trigger (user did NOT do something)**         | Raised immediately with no delay. Cross-journey PBS delay applies if J1 used PBS.                                                                                                                                                                     |
| **Live Date trigger**                                         | Raised immediately with no delay. Mini-who evaluation may add a few hours of delay.                                                                                                                                                                   |
| **Page Visit / Page Count / Referrer**                        | Raised immediately with no delay.                                                                                                                                                                                                                     |
| **Journey Trigger (triggered from another journey)**          | Raised immediately with no delay. Not typically used for downstream segmentation.                                                                                                                                                                     |
| **Past Behavior Segment (PBS)**                               | Raised during the nightly batch run (typically at midnight in your account timezone). If this journey is nested within another journey whose entry is also PBS, the event will only be raised after the upstream journey's PBS computation completes. |

<Callout icon="📘" theme="info">
  ### **Nested PBS Journeys**

  If Journey 2 uses a PBS entry segment built on Journey Qualified from Journey 1 (also uses PBS entry segment), both evaluations happen as follows: Journey 1 PBS runs first, raises Journey Qualified, and Journey 2 PBS evaluation follows in the same run.

  This means there is no extra day of delay, but both runs occur within the same night window.**&#x20;**
</Callout>

## Journey Exited

The Journey Exited event is raised every time a user leaves a journey, regardless of how or why they left. The Exit Reason property tells you exactly what caused the exit.

### Exit Reasons

The Journey Exit Reason property will always be one of the following values:

| Exit Reason           | What it means                                                                                                                                                        |
| :-------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Journey Goal Met**  | The user completed the journey's defined goal, for example, making a purchase or completing a registration. This is a successful exit.                               |
| **Journey Completed** | The user reached the last node of the journey (an engagement or profile update node), and the journey had no goal defined. This is a natural, successful completion. |
| **Journey Timed Out** | The user was in the journey longer than the maximum allowed duration and was automatically removed.                                                                  |
| **Force Exited**      | The user was deliberately removed from the journey, either by a Force Exit node in the journey flow or manually by an admin.                                         |
| **Version Exit**      | The user was exited from a specific version of the journey, typically when a new version was published, and the user's prior version was retired.                    |

### Event Properties

The following table lists the Journey Exit event properties:

| Event Property                | Description                                                                                                                  | Data Type | Example Value         |
| :---------------------------- | :--------------------------------------------------------------------------------------------------------------------------- | :-------- | :-------------------- |
| **Journey ID**                | The unique numeric ID of the journey.                                                                                        | Integer   | 10482                 |
| **Journey Name**              | The name of the journey as set by you in the dashboard.                                                                      | String    | Onboarding Flow – Nov |
| **Journey Exit Reason**       | The reason the user left the journey. For more information about all possible values, refer to the Exit Reasons table above. | String    | Journey Goal Met      |
| **Journey Goal Name**         | The name of the goal the user completed. Raised only when Exit Reason is 'Journey Goal Met'.                                 | String    | Purchase Completed    |
| **Journey Goal ID**           | The numeric ID of the goal. Raised only when Exit Reason is _Journey Goal Met_.                                              | Integer   | 3                     |
| **Goal Type**                 | Indicates whether the goal was evaluated in real time (_Live_) or in batch (_Past Behavior_).                                | String    | Live                  |
| **Version Number**            | The version of the journey the user was on when they exited.                                                                 | Integer   | 2                     |
| **Control Group User**        | Set to _True_ if the user is part of any control group in this journey. Not raised if the user is not in a control group.    | Boolean   | True                  |
| **Control Group Type**        | Populated only when _Control Group User_ is True.  Values: _System_, _Journey_, or _Custom_.                                 | String    | System                |
| **Custom Control Group Name** | Raised only when _Control Group Type_ is _Custom_. Contains the name of the custom control group.                            | String    | High-Value Users CG   |

### Behavioral Rules

The following table provides information about when and how quickly a Journey Exited is raised, depending on the type of entry or goal segment configured in the journey:

| Exit Type                                                                      | When is Journey Exited raised?                             |
| :----------------------------------------------------------------------------- | :--------------------------------------------------------- |
| Live goal (user performs or does not perform the journey goal event)           | Immediately                                                |
| Past Behavior Segment (PBS) goal                                               | Overnight during the nightly evaluation (account timezone) |
| Journey Timeout (user exceeds the journey's maximum duration)                  | After a short delay, processed in the background           |
| Journey Completed (user reaches the last step with no goal defined)            | After a short delay, processed in the background           |
| Force Exit (user hits a Force Exit node in the journey)                        | Immediately or after a short delay                         |
| Version Exit (user journey version is retired when a new version is published) | After a short delay, processed in the background           |

<Callout icon="📘" theme="info">
  ### Control Group Users

  Journey Exited is only raised for Control Group users in two cases: when they meet the journey goal, or when they exceed the maximum journey duration. Force exits, version exits, and journey completions do not generate a Journey Exited event for Control Group users.
</Callout>

# Use Cases

Here are the most common ways marketers use Journey Events to improve targeting and analysis:

- **Re-engage users who dropped off without converting**<br />Create a Past Behavior segment of users where Journey Exited was raised and Exit Reason is not _Journey Goal Met_. Use this segment to launch a re-engagement campaign, such as a push notification, SMS, or a separate recovery journey.
- **Prevent users in one journey from entering another**<br />Build a live segment of users who have received a Journey Qualified event for your 'Seller Journey'. Use this as an exclusion condition in your _Buyer Journey_ entry criteria. This prevents users from receiving conflicting or overlapping messaging.
- **Analyze journey conversion rates**<br />In Analytics, use the Funnels or Events report with Journey Qualified and Journey Exited (Exit Reason = Journey Goal Met) to calculate the conversion rate for any journey. Compare across journey versions or time periods.
- **Export journey participation data for external analysis**<br />Use Partner Exports (S3, GCP, or other configured destinations) to export users who triggered Journey Qualified or Journey Exited events. This lets you bring journey participation data into BI tools, data lakes, or CRMs for deeper reporting.
- **Trigger a follow-up journey when a user exits**<br />Set up a new journey that uses Journey Exited as its entry trigger (via a Past Behavior segment). When a user exits your main onboarding journey, whether they converted or not, they can automatically enter a follow-up journey tailored to their outcome.
- **Measure campaign effectiveness with journey goals as conversion events**<br />In your campaign stats or campaign creation page, set the conversion event to Journey Exited with Exit Reason = 'Journey Goal Met'. This lets you measure how many users who received your campaign ultimately completed the journey goal.

# View Journey Events

Journey Events are available across the CleverTap dashboard, wherever you can filter or analyze by events.

## Schema Page

Go to _Settings_ > _Schema_ to view _Journey Qualified_ and _Journey Exited_ listed under the _System Events_ tab.


<Image src="https://files.readme.io/05073f2501a3b7d01ef593378f22f992f04e2b0a37bd94c7153ee812b80297f0-Schema_Page_-_View_Journey_Events.png" align="center" caption="View Journey Events from Schema Page" border={true} />


From here, you can view the event properties, check the data retention policy, and confirm the events are active for your account.

## User Profile — Activity Tab

On any individual user's _Profile_ page, select the _Activity_ tab. Both _Journey Qualified_ and _Journey Exited_ events appear in the user's event timeline alongside all other system and custom events, with all properties.

You can see the following:

- Journey Qualified event, along with the following properties if applicable: Journey ID, Journey Name, Entry Type, Version Number, and Control Group properties.
- Journey Exited event, along with the following properties if applicable: Journey ID, Journey Name, Exit Reason, Goal Name and Goal ID (if goal met), Goal Type, Version Number, and Control Group properties.


<Image src="https://files.readme.io/5d8e968dc313334103fecbc5a7253e87195254a3efee9362825f94159a3b57c7-User_Proile_-_Entered_and_Exited_Joruney.png" align="center" caption="View User's Event Timeline under Activity Tab" border={true} />


Typical reasons to check this:

- Verify that a user entered the correct journey and version
- Confirm the exit reason for a user who did not receive an expected message
- Check whether a user is in a control group and which type

# Analytics

Journey Qualified and Journey Exited are available in all Analytics features in CleverTap.<br />The following table lists the use cases where these events can be used in different analytics features:

| Report Type     | Use Case with Journey Events                                                                                                                                                                          |
| :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Events**      | You want to see the total number of Journey Qualified and Journey Exited over time. You can spot spikes or drops in entries and exits per journey.                                                    |
| **Funnels**     | You can use Journey Qualified as Step 1, and Journey Exited (Exit Reason = Journey Goal Met) as the final step to measure end-to-end conversion. Filter by Journey Name or Version Number to compare. |
| **Cohorts**     | You can group users for whom Journey Qualified was raised in a given week and track whether and when they converted. Compare Target Group vs. Control Group cohorts to measure journey impact.        |
| **Trends**      | Trend entry and exit volumes over time. Filter by Entry Type, Control Group User, or Journey Name to monitor the impact of publishing a journey or a new version.                                     |
| **Pivots**      | Break down entries and exits by user properties such as country, device type, or user tier to identify which segments convert best.                                                                   |
| **Flows**       | You want to understand the event paths users follow before entering a journey or after exiting a journey.                                                                                             |
| **Real Impact** | You want to measure the incremental uplift of a journey by comparing Converted Users vs. Control Group Users using the Control Group User and Control Group Type properties.                          |

# Using Journey Events in Engagements

Journey Qualified and Journey Exited can be used to power campaigns and journeys across CleverTap, with one important constraint depending on how the event was raised.

You can do the following:

- **Trigger Campaign When User Enters or Exits Journey**

  You can use Journey Qualified or Journey Exited as the trigger event in a campaign (push notification, SMS, email, WhatsApp). The campaign fires as soon as the event is raised.

  For example, send a re-engagement push when a user exits the Onboarding Journey without completing the goal.
- **Target Users Based on Past Journey Activity**

  Build a Past Behavior Segment of users who triggered Journey Qualified or Journey Exited within a time window. Use this segment in any campaign or as a journey entry condition.

  For example, target all users who exited the Upgrade Journey in the last 30 days with a discount offer.
- **Start New Journey When User Exits Another**

  Use Journey Exited as the entry condition for a follow-up journey. When a user exits Journey A, whether they converted or dropped off, they can automatically enter Journey B tailored to their outcome.

  For example, users who exit the Trial Journey with Exit Reason = Journey Goal Met enter a retention journey. Users who time out enter a win-back journey.

# Exports

Both Journey Qualified and Journey Exited are available in Partner Exports. You can export them to S3, GCP, or other configured destinations to use in BI tools, data warehouses, or CRMs.

For more information on creating an export, refer to [Profile and Events Export](https://docs.clevertap.com/docs/profile-and-events-legacy).
