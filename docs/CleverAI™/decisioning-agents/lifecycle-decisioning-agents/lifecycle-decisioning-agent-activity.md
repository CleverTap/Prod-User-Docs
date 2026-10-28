---
title: Activity
excerpt: Learn how to view the interaction and messages between the agent and the user.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
The Activity tab shows the messages the Lifecycle Agent sent to individual users. Use it to check which users the agent reached, the order in which each user received messages, and the content of each message.

<Callout> Example To confirm the agent is working as intended, select a user who hasn't purchased and check that the 10% off reminder appears in their timeline.

The following image shows the Activity tab with a user selected in the Sample Users panel. (@soumya, please verify the screenshot so that the UI is recent)


<Image src="https://files.readme.io/68b4df947ebc40b821434593f84e58c66824f11a3c288b6702ef21872354fb79-image.png" align="center" border={true} />


The tab is organized into three panels:

| Panel          | Purpose                                                     |
| -------------- | ----------------------------------------------------------- |
| _Sample Users_ | Select a user from a sample of users the agent has reached. |
| _Engagement_   | View the messages sent to the selected user, newest first.  |
| _Message_      | Preview the selected message.                               |

## Sample Users

The _Sample Users_ panel lists a sample of users from the agent's audience. Select any user to load their engagement history and message details in the panels on the right.

Each entry displays:

- The user's identity name&#x20;
- The user's CleverTap ID&#x20;

To find a specific user, enter their name or ID in the **Search users** field at the top of the panel.

## Engagement

The _Engagement_ panel shows the timeline of interactions the selected user has had with the agent.

The panel header displays the selected user's name and a **View Profile** link. Select **View Profile** to open the user's full [CleverTap profile](doc:find-people). &#x20;

The _Timeline_ view lists engagements in reverse chronological order, grouped by date. Each entry shows:

- The delivery timestamp (for example, _12:50:30 PM_).
- The message name (for example, _Push Notification Recovery_, _SMS Cart Alert_, _WhatsApp Cart Reminder_).

Select an entry to preview the message.

## Message

The _Message_ panel shows the specific message the agent sent to the selected user and explains why the agent chose it.

The panel header displays the name of the message tied to the currently selected timeline entry (for example, _Push Notification Recovery_).&#x20;

### Preview

The _Preview_ view renders the message exactly as the user received it.&#x20;

<br />

<br />