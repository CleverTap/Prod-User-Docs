---
title: Email Notify Stats
excerpt: Learn how to track and analyze the performance of your Notify campaigns.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The _Stats_ tab provides a comprehensive view of your Notify campaign performance for the Email channel, helping you track requests, message delivery, user engagement, and errors. This data is vital for understanding message flow health, diagnosing issues, and optimizing delivery outcomes.

The _Stats_ section can be classified into two parts:

- [Request-Level Stats](doc:notify-email-stats#request-level-stats)
- [Channel-Level Stats](doc:notify-email-stats#channel-performance)&#x20;

## Request-Level Stats

The Request-Level Stats provide a high-level summary of the requests made to the Notify API within a selected time period. These metrics help you track the flow of incoming requests and understand how many were successfully processed and how many failed.

- **Requests Received**: Number of API requests received by CleverTap to trigger the Notify message.
- **Requests Processed**: Number of requests successfully processed and sent to the Email Service Provider.
- **Requests Failed**: Number of requests that failed during processing or delivery to the provider.

The **Trend** section, below the metric cards, displays a request timeline to help you track performance patterns, such as volume spikes or error bursts. You can toggle between the following tabs:

- **Trend**: Graphical view of total received, processed, and failed requests over a selected time range. You can click the ![](https://files.readme.io/2c2ca5affab31cbb70db7e89ac65e65e04219bfe463755836373077b5f63f049-Hide_icon.png) icon to view or hide a specific metric, as shown in the image below.
- **Errors**: Lists failed Notify API requests grouped by error type, along with the count for each. This helps identify the root cause of failures.

Use the date range selector to filter stats within a specific time window, then download the data for audits or internal analysis.


<Image src="https://files.readme.io/b93a1b1365899978747cd2e7a67132b08a6e71e0e20509c4c17c1383d2601522-2025-07-16_16-34-29_1.gif" alt="Request-Level Stats" align="center" caption="Request-Level Stats" border={true} />


## Channel-Level Stats

The _Channels_ section provides a detailed breakdown of email-specific performance, helping you understand how recipients interact with transactional messages post-delivery.


<Image src="https://files.readme.io/ef00347e4433aa3e205007696649510a23b7fce0ab661c7a42db80f4456fb9fe-2025-07-16_16-29-33_1.gif" alt="Channel Performance" align="center" caption="Channel-Level Stats" border={true} />


### Trends

Use the Trends view to analyze how performance changes over time, including spikes in message volume and engagement rates, helping you uncover behavior patterns. Use the date range selector to filter stats within a specific time window, then export the data for audits or internal analysis.

- **Sent**: Number of emails sent to the delivery provider.
- **Delivered**: Number of emails delivered to the recipient.
- **Viewed**: Number of times users viewed the email.
- **Clicked**: Number of times users clicked on any links within the email.

You can click the ![](https://files.readme.io/94031640d02b525c886f55910f9367fc3e7798ed5cf84387a8d8456277239892-Hide_icon.png) icon to view or hide a specific metric. For more information on email stats, refer to [Email Stats](doc:email-stats).

For Message by User Property campaigns, the Trends view also includes a per-variant breakdown showing performance across variants, including the default. Use the Sent, Delivered, Viewed, and Clicked tabs above the chart to switch which metric is plotted for each variant over time. The table below the chart lists all four metrics for every variant regardless of the selected tab. You can export the full table using **Export As CSV**.

The following image shows the variant-level trends:


<Image src="https://files.readme.io/db5ca9f84a1a0c4f9c88f81bcfea6ca07eac26cb5eace4c9c3c51cca50a26d9d-image.png" align="center" caption="Trend Chart for Variants" border={true} />


### Errors

The _Errors_ section provides visibility into issues encountered during Email delivery to the recipient. Use this section to identify and investigate failed deliveries. You can view the number of errors, a breakdown by error type, and the count for each.

-
  <Image src="https://files.readme.io/c299d937c4cd5030f64bc08ed536b2f34c8d2aa1ea1ee236803614558f2e4b35-image.png" align="center" caption="Email Notify Errors" border={true} />


<br />

<br />