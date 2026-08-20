---
title: Stats
excerpt: 'Learn to read how Lifecycle Agent is performing over a selected date range. '
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The _Stats_ tab shows how a Lifecycle Agent is performing over a selected date range. Use it to track how many users have entered the agent, how many converted or timed out, how each message channel is contributing, and how the agent's target group is performing against the control group. The default date range is the last 30 days.&#x20;

The following image shows the _Stats_ tab with the _Analysis_ panel, _Conversion Performance_ chart, and _Engagement Trend_ section:


<Image src="https://files.readme.io/2eef3248b00109ea33e3cf59386db97ce11e0e396ca462119627703e48f74cd3-image_2.png" alt="Lifecycle Agent Stats" align="center" caption="Lifecycle Agent Stats" border={true} />


<br />

## Metric Categories

The _Stats_ tab groups metrics into the following sections:

- **Analysis:** Key engagement metrics are displayed in this section. Use the  _Unique_ / _Total_ toggle to switch between user counts and event counts.
- **Conversion Performance:** A side-by-side comparison of conversions in the target group and the control group, highlighting conversion uplift over the control group.
- **Engagement Trend:** A trend chart of engagement metrics across the selected date range.
- **Channel-wise Engagement:** A per-channel breakdown of messages sent, delivered, viewed, and clicked.

## Analysis Section

The _Analysis_ section reports the following metrics for the selected date range:

| Metric      | Description                                                              |
| ----------- | ------------------------------------------------------------------------ |
| _Entered_   | Users who entered the agent.                                             |
| _Converted_ | Users who performed the agent's goal event within the conversion window. |
| _Timed Out_ | Users who exited the agent without meeting the goal.                     |
| _Sent_      | Messages the agent sent across all channels.                             |
| _Delivered_ | Messages confirmed as delivered across all channels.                     |
| _Viewed_    | Messages the user opened or viewed.                                      |
| _Clicked_   | Messages the user clicked.                                               |

## Conversion Performance

The _Conversion Performance_ section compares the target group with the control group, allowing you to measure the agent's incremental uplift.&#x20;

The section shows:

- **A conversion count** for the selected date range.&#x20;
- **A percentage delta** labeled _Compared to Control Group_, expressed as relative uplift using the formula (target group conversion rate − control group conversion rate) / control group conversion rate × 100.&#x20;
- **A horizontal bar chart** with two bars for the conversion rate, that is, the _Target Group_ and _the Control Group._

## Engagement Trend

The _Users Engagement Trend_ chart plots engagement metrics across the selected date range.&#x20;


<Image src="https://files.readme.io/334dc9784974904fab36c90899c370960aef5bbe68240e3123abbef45d2ee7d0-image.png" alt="Engagement Trend" align="center" caption="Engagement Trend" border={true} />


The chart plots four series:

- _Sent_
- _Delivered_
- _Viewed_
- _Clicked_

## Channel-Wise Engagement

The _Channel-wise Engagement_ table breaks down engagement metrics by channel for the selected date range.&#x20;

The table has the following columns:

| Column            | Description                                                                                      |
| ----------------- | ------------------------------------------------------------------------------------------------ |
| _Channel Name_    | Delivery channel used by the agent.                                                              |
| _No of Campaigns_ | Number of campaigns the agent ran on that channel.                                               |
| _Sent_            | Messages sent through that channel.                                                              |
| _Delivered_       | Messages confirmed as delivered. Shows `N/A` for channels that do not report delivery callbacks. |
| _Viewed_          | Messages viewed.                                                                                 |
| _Clicked_         | Messages clicked.                                                                                |
| _CTR_             | Click-through rate for the channel.                                                              |

The Lifecycle Agent supports the following channels: Push Notifications, Email, SMS, WhatsApp, Web Push, and Inbox.

##

<br />

<br />

<br />
