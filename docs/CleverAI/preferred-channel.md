---
title: Preferred Channel
excerpt: >-
  Learn how Preferred Channel ensures every user gets messages through the
  channel they engage with most, maximizing reach and response.
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

Preferred Channel identifies each user’s most effective communication channel based on their engagement across Push, Email, SMS, and WhatsApp.

CleverAI analyzes user interactions over a rolling 90-day window to determine the channel that consistently drives the highest engagement. The identified channel is stored as a system user property called _Preferred Channel_, which can be used across Segments, Campaigns, and Journeys.

With Preferred Channel, marketers can:

- **Personalize Communication**: Deliver messages via the channel each user prefers.
- **Improve Engagement**: Boost open and click rates.
- **Reduce Communication Fatigue**: Avoid sending the same message across multiple channels.
- **Optimize Cost**: Target users efficiently based on their engagement behavior.
- **Streamline Orchestration**: Use across Segments, Campaigns, and Journeys for targeted engagement and performance insights.

<Callout icon="📘" theme="info">
  #### **NextGen Segment Builder**

  The Preferred Channel user property is available only for projects using the NextGen Segment Builder.
</Callout>

# Preferred Channel Functionality

CleverAI evaluates user engagement across Push, Email, SMS, and WhatsApp to identify the channel that performs best for each user. It analyzes message interactions, such as sent, viewed, and clicked over the past 90 days, and assigns the channel with the highest engagement as the user’s Preferred Channel.

This property updates automatically as users interact with new messages and is refreshed daily to ensure it reflects recent behavior. Each interaction, whether a view or a click, is treated equally to maintain consistency.

Preferred Channel helps deliver messages through the channel that users respond to most often, improving engagement while reducing message fatigue.

**Example**

Consider a user who regularly engages with multiple channels. Over a given period, they open and click a few Push notifications, occasionally read SMS messages, and also interact with WhatsApp updates.

CleverAI evaluates engagement trends and recency of interactions, giving greater weight to the most recent activity. When two or more channels show similar engagement patterns, the system selects the one where the user interacted most recently as the Preferred Channel.

This ensures that user preferences remain accurate and up to date, enabling marketers to deliver messages through the channel that offers the highest likelihood of engagement.

### Applies Recency Weighting

CleverAI gives higher weight to the most recent interactions. When two channels show identical engagement levels, the system selects the one where the user engaged most recently. For example, if Push and WhatsApp both show similar engagement, but the user’s latest interaction occurred on WhatsApp, WhatsApp becomes the Preferred Channel.

### Assigns and Refreshes

After identifying the most relevant channel using engagement and recency signals, CleverAI saves that channel as the user’s Preferred Channel property. This value updates automatically as users continue to engage with messages and refreshes daily to ensure it always reflects the latest interaction trends.

<Callout icon="📘" theme="info">
  ### **Optimizing Preferred Channel Through Re-Engagement**

  Re-engagement campaigns for users with _Not Enough Data_ help CleverAI gather additional behavioral data, which in turn allows the system to assign a Preferred Channel once enough interactions are recorded.
</Callout>

## 'Not Enough Data' Explained

A Preferred Channel is recorded only when all of the following conditions are met:

- The account has at least two active channels (for example, Push and Email).
- The user has been reached through two or more channels within the last 90 days.
- The user has recorded at least three total engagements during that period.

If any of these conditions are not met, CleverAI cannot determine a Preferred Channel. In such cases, the property is stored as _Not Enough Data_, ensuring that segmentation, campaign targeting, and journey-based use cases rely only on meaningful and verified engagement data.

If you want users with a defined preference for Push to receive a Push campaign, but also want to include users whose channel preference is _Not Enough Data_, you can create a rule such as:

`Preferred Channel = Push`<br />or<br />`Preferred Channel = Not Enough Data`

This setup ensures both groups' users are proven to prefer Push, and those without sufficient data receive the same message.

You can also create separate campaigns for each channel (for example, Push, Email, or SMS) and include users with _Not Enough Data_ in one of them to maintain consistent reach while collecting more engagement data for future classification.)

# Using Preferred Channel Across Dashboard

You can use the Preferred Channel property across core CleverTap modules, Segments, Campaigns, Journeys, Analytics, and Profile Exports, to target users through the channels they engage with most.

| Product Area    | How Preferred Channel Helps                                                                                                                                                |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Segmentation    | Filter users by their most engaged channel to create precise, channel-specific segments.<br />For example: Users whose Preferred Channel = WhatsApp.                       |
| Campaigns       | Use the Preferred Channel property in the _Who_ section to refine targeting and ensure messages are delivered through the channel where users are most responsive.         |
| Journeys        | Branch users dynamically in a Conditional Split node based on their Preferred Channel. The property is read-only and can only be used for segmentation or branching logic. |
| Analytics       | Track and analyze engagement performance by comparing metrics across different Preferred Channels.                                                                         |
| Profile Exports | Export the Preferred Channel property for analysis to external analytics or CRM systems.                                                                                   |

## Create Segments Using Preferred Channel

Use the Preferred Channel property in the NextGen Segment Builder to create audience filters based on each user’s most engaged communication channel.

For example,<br />`User Property > Preferred Channel  equals  Push`

This filter selects users who primarily engage through Push notifications. Once saved, the segment can be reused in Campaigns or Journeys for targeted communication, helping marketers identify users’ engagement preferences and understand how effectively these users can be reached on their preferred channel.

This image shows the creation of a user segment using the Preferred Channel property. The Reachability metrics in the _Segment Insights_ section display how many users in the segment can currently receive messages across each active channel, such as Push, Email, SMS, and WhatsApp. Reachability depends on device and channel availability, not on user preference.

<Callout icon="📘" theme="info">
  ### **Preferred Channel and Estimate Reach**

  - **Preferred Channel** identifies the channel where a user shows the highest engagement based on past interactions.
  - **Estimated Reach** shows how many users in this segment (whose Preferred Channel is Push) are currently reachable across all channels based on delivery eligibility.

  Preferred Channel reflects engagement behavior, while Estimated Reach represents delivery potential.
</Callout>

The following image shows how preferred channel differs from estimated reach:


<Image src="https://files.readme.io/4cdf28aadc0e6bfcf384afd4d776111c4f0b146f00fdac4713df2fb90fe099dc-Preferred_Channel_vs._Est._Reach.png" alt="Preferred Channel vs. Estimate Reach" align="center" width="80% " caption="Preferred Channel and Estimate Reach" border={true} />


## Personalize Campaigns Using Preferred Channel

When creating a Campaign, use the _Preferred Channel_ property in the Who section to target users who are most likely to engage on that channel.

For example, for a product update or feature announcement, you can use `Preferred Channel = Push` to reach users who regularly engage with push notifications, while excluding those whose preferred channel is Email or SMS. This ensures the message reaches users where they are most likely to interact, reducing overlap and message fatigue.


<Image src="https://files.readme.io/c3eaeda6af0240ec4d598a99327f796f8409a895aa36ace4fe8878729ceb8835-Define_Who_Using_Preferred_Channel.png" alt="Preferred Channel in Campaigns" align="center" caption="Using Preferred Channel in Campaigns" border={true} />


## Personalize Journeys Using Preferred Channel

Within Journeys, use the Preferred Channel property to branch users by their most engaged channel using a _Conditional Split_ node.

For example, you can use Preferred Channel in a reactivation journey to route users via their most active channel, send Emails to users with Preferred Channel set to Email, and push messages to those who primarily engage through Push.

| Path   | Condition                 | Engagement Action      |
| ------ | ------------------------- | ---------------------- |
| Path 1 | Preferred Channel = Push  | Send Push Notification |
| Path 2 | Preferred Channel = Email | Send Email Campaign    |

This setup automatically routes users through the channel that drives the highest engagement, eliminating the need for separate journeys.


<Image src="https://files.readme.io/ce090f631fe289914a4480207ccc614024ba6f484a7999ab02f129b5f745a6ce-image.png" alt="Preferred Channel Setup in Conditional Split Journeys" align="center" caption="Preferred Channel Setup in Conditional Split Journeys" border={true} />


The following image shows the Journey with a conditional split node that branches users by their most engaged channel:


<Image src="https://files.readme.io/3c15b597dc0d65a91adb55bf09915590e48ca8dc2fd695749a3b406277430a5c-image.png" alt="Personalize Journey Basis Preferred Channel" align="center" caption="Personalize Journey Basis Preferred Channel" border={true} />


# FAQs

The following are the answers to common questions about how Preferred Channel works and how to use it effectively.

### What happens if a user unsubscribes from their Preferred Channel?

If a user unsubscribes from their Preferred Channel, CleverAI detects it during the next daily refresh and re-evaluates their engagement across active channels. The Preferred Channel is then updated automatically to SMS, Email, or another channel where the user has shown the highest recent engagement.

### Why am I not able to see the Preferred Channel property in my Segment Builder?

The Preferred Channel property is available in all entities using the NextGen Segment Builder. If you are using Legacy Segment Builder, the property does not appear in the list of available user properties.
