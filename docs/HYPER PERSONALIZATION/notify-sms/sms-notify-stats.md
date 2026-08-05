---
title: SMS Notify Stats
excerpt: Learn how to track and analyze the performance of your Notify campaigns.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The _Stats_ tab provides a comprehensive view of your Notify campaign performance for the SMS channel, helping you track requests, message delivery, user engagement, and errors. This data is vital for understanding message flow health, diagnosing issues, and optimizing delivery outcomes.

The _Stats_ section can be classified into two parts:

- [Request-Level Stats](doc:notify-sms-stats#request-level-stats)
- [Channel-Level Stats](doc:notify-sms-stats#channel-performance)

## Request-Level Stats

The Request-Level Stats provide a high-level summary of the requests made to the Notify API within a selected time period. These metrics help you track the flow of incoming requests and understand how many were successfully processed and how many failed.

- **Requests Received**: Number of API requests received by CleverTap to trigger the Notify message.
- **Requests Processed**: Number of requests successfully processed and sent to the SMS Service Provider.
- **Requests Failed**: Number of requests that failed during processing or delivery to the provider.

The **Trend** section, below the metric cards, displays a request timeline to help you track performance patterns, such as volume spikes or error bursts. You can toggle between the following tabs:

- **Trend**: Graphical view of total received, processed, and failed requests over a selected time range. You can click the ![](https://files.readme.io/2c2ca5affab31cbb70db7e89ac65e65e04219bfe463755836373077b5f63f049-Hide_icon.png) icon to view or hide a specific metric, as shown in the image below.
- **Errors**: Lists failed Notify API requests grouped by error type, along with the count for each. This helps identify the root cause of failures.

Use the date range selector to filter stats within a specific time window, then export the data for audits or internal analysis.


<Image src="https://files.readme.io/b691134948afaa7c90cc6072550458939635f321b5b1428d7fcfce50a2a2ba2a-image.png" align="center" caption="Request-Level Stats" border={true} />


## Channel- Level Stats

The _Channels&#x20;_&#x73;ection provides a detailed breakdown of SMS-specific performance, helping you understand how recipients interact with transactional messages post-delivery.


<Image src="https://files.readme.io/1b7392b34c267f547e5dd6e9617b81e450b7cb1b2a96eb9ec2a684cb7844ab94-image.png" align="center" caption="Channel-Level Stats" border={true} />


### Trends

Use the Trends view to analyze how performance changes over time, including spikes in message volume and engagement rates, helping you uncover behavior patterns. Use the date range selector to filter stats within a specific time window, then export the data for audits or internal analysis.

- **Total Sent**: Number of SMS sent to the delivery provider.
- **Total Delivered**: Number of SMS delivered to the recipient.
- **Total Viewed:** Number of times recipients viewed the SMS (only populated when using a provider that supports read receipts).
- **Total Clicked**: Number of times users clicked on any links within the SMS.

You can click the ![](https://files.readme.io/94031640d02b525c886f55910f9367fc3e7798ed5cf84387a8d8456277239892-Hide_icon.png) icon to view or hide a specific metric. For more information on SMS stats, refer to [SMS Stats](doc:sms-stats).

### Errors

The _Errors_ section provides visibility into issues encountered during SMS delivery to the recipient. Use this section to identify and investigate failed deliveries. You can view the total number of errors, a breakdown by error type, and the count for each.


<Image src="https://files.readme.io/ab926184697ebea0e283d7e57e21e86dec097f7f28aed1c48062d84faf2d0b3e-image.png" align="center" caption="SMS Notify Errors" border={true} />


<br />