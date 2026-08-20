---
title: Recommendation Strategy Stats
excerpt: >-
  Learn how to monitor the performance and usage of your recommendation strategy
  across engagements, messages, and channels.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Stats page provides a comprehensive view of how your recommendation strategy is performing across channels, items, and user engagement. Use it to evaluate effectiveness, identify top-performing recommendations, and optimize delivery strategies.

<Image align="center" border={true} caption="Recommendation Strategy Stats Page" src="https://files.readme.io/6a725e0a279cee712e4c21699997d85acb7dc9b60c46ca0733bf451b851fe43e-Recommendation_Strategy_Stats.png" />

It helps you understand the following:

* Channels driving the highest engagement
* Whether the recommendation volume aligns with engagement
* Items most frequently recommended versus most effective
* Opportunities to improve click-through rate by channel or item

# Date Range and Filters

Select a date range to analyze recommendation performance over a specific period. All metrics on this page update dynamically based on the selected timeframe.

# Key Metrics

At the top of the page, you can see a high-level summary of recommendation performance.

<Image align="center" border={true} caption="Key Metrics" src="https://files.readme.io/7b0acabd13dc7943adbc4820df474531f188926e726b24ea118f2e40cf87de7f-Key_Metric_-_Strategy_Stats.png" />

## Total number of engagements

The total number of campaigns, journeys, bulletins, and reminders using this strategy that recorded activity in the selected period, across all channels.

This metric helps you understand how broadly the strategy is being used across active engagements.

## Total number of recommended items

The total number of recommendation instances served to users by the base strategy during the selected timeframe. This includes multiple exposures of the same item, each counted separately.

This metric helps you measure recommendation volume and distribution.

## Engagement Channel-wise Breakdown

This section breaks down recommendation performance by delivery channel, helping you understand how each channel contributes to overall engagement. You can compare engagement volume, message delivery, recommendation count, and click-through efficiency across channels such as Push Notification, Email, SMS, and others.

<Image align="center" border={true} caption="Channel-wise Breakdown of Recommendation Strategy" src="https://files.readme.io/fefe41460444c12dc972e73e19ebea0a5b2da9633640fd410c67640a32d878a3-Channelwise_Breakdown.png" />

The following metrics are displayed for each channel:

| Metric                            | Description                                                                                                                                     |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Total number of engagements       | The total number of campaigns, journeys, bulletins, and reminders delivered through this channel that used the strategy in the selected period. |
| Total number of messages          | The number of messages sent through the channel that contained recommendations.                                                                 |
| Total number of items recommended | The total count of recommendation instances delivered through the channel.                                                                      |
| Average click-through rate        | The percentage of message views where at least one recommended item link was clicked.                                                           |

To drill into which engagements are active on a channel, click **View all [Channel] engagements** on the channel row, or use the three-dot menu to navigate directly to a specific engagement type:

<Image align="center" border={true} caption="View All Channel-wise Engagements" src="https://files.readme.io/63ab24f15a87b78e265621f08d33a585653f14508e2263be5dc60dfc16fbd975-Channel-wise_Drilldown.png" />

# Top Recommended

This section displays the most frequently recommended items.

<Image align="center" border={true} caption="Top Recommended Items" src="https://files.readme.io/87c774241a414a62471a1e58b6e8a5e5c813ce902d783e2c137f1eccc0854d23-Top_Recommended.png" />

Use it to:

* Evaluate the performance of individual items
* Identify high-converting recommendations
* Optimize item ranking strategies

The following table describes the columns in this section:

| Column            | Description                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------- |
| Item Name         | The name and ID of the recommended item. Click on an item to view its details in the Item Detail panel. |
| Total Recommended | The number of times the item was recommended to users in the selected period.                           |

To find a specific item, use the search bar to look up by name or ID.

## Item Detail

When you select an item from the Top Recommended list, the _Item Detail_ panel opens on the right side of the page.

<Image align="center" border={true} caption="Item Detail Panel" src="https://files.readme.io/4c3137bad1493ee7113244c3310169b577de1ffe593b8f8d3171ac0cad2cb403-Item_Detail_Panel.png" />

The Item Detail panel displays the following:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Detail
      </td>

      <td>
        Displays the following:

        * **Product Id**: The unique identifier of the item in the catalog.
        * **Times Recommended**: The number of times this item was recommended to users in the selected period.
      </td>
    </tr>

    <tr>
      <td>
        Attributes
      </td>

      <td>
        Dynamic key-value pairs from the item catalog, for example, genre, cast, language, and rating. The attributes displayed depend on the catalog schema configured for your account.
      </td>
    </tr>
  </tbody>
</Table>