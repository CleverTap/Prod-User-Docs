---
title: ROI Insights
excerpt: >-
  Learn how to configure, analyze, and interpret ROI Insights for your campaigns
  from the CleverTap dashboard.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

ROI Insights connects your campaign to real business outcomes, such as conversions, revenue, and custom KPIs from a single dashboard.

With ROI Insights, you can:

* Track up to five conversion goals (purchases, subscriptions, bookings, and so on)
* Measure revenue impact alongside engagement metrics
* Filter and compare campaigns by channel, status, label, and more
* Build custom KPIs for business-specific analysis
* Export performance data for reporting.

# Attribution Model

ROI Insights uses a Last Touch Attribution model for attributing conversions to campaigns and journeys. In this model, attribution is based on the most recent _Notification Clicked_ event that occurs before a conversion. This means the conversion is credited to the last campaign or journey message the user clicked on before completing the configured conversion event. Note that the Last Touch model attributes conversions based on the recency of the click, not the relevance of the campaign content to the conversion event.

For example, if a user clicks a push notification promoting shoes and then purchases a mobile phone within the set conversion window, the conversion is still attributed to the Shoes campaign. This is because the promotional push for  Shoes was the last touchpoint before the conversion.

<Callout icon="📘" theme="info">
  #### Data Recency

  ROI Insights data is refreshed periodically and may take up to 6 hours to reflect recent campaign activity, conversions, or custom metric updates. Custom metrics may also take additional processing time before appearing in the _[Engagement Performance Table](doc:roi-insights#engagement-performance-table)_ because the Last Touch model updates conversion metrics only after it processes both click and conversion events.
</Callout>

# Prerequisites

Before using ROI Insights, you must configure at least one global conversion event, such as _Charged_, in the Schema. These conversion events apply across all campaigns and journeys and are used as the basis for attribution and ROI calculation.

You can configure up to five conversion events to track different business goals simultaneously. Each event supports its own filters to narrow qualifying conversions, and its own lookback window to define how long after a click a conversion counts.

## Configure ROI Conversion Events

Before analyzing ROI, you must define what constitutes a conversion for your business. A conversion event represents a meaningful user action, such as a purchase, subscription, booking, or app upgrade. You can configure up to five conversion events.

To add a conversion event from the CleverTap dashboard:

1. Go to **ROI Insights** in the CleverTap dashboard, then click **Add conversion event**.
2. Select the required event that represents a meaningful user action, such as Charged for purchases or Subscription Started for subscriptions. You can optionally add a display nickname to identify the event clearly in the ROI dashboard.
3. (Optional) Apply filters to narrow qualifying conversions. For example, filter a Purchase event by product category or transaction value.
4. Enter the _Lookback window_ to define the time period during which a user action is attributed to a campaign.
5. Click **Save**.

<Image align="center" border={true} src="https://files.readme.io/d81cd93bee33f5859d1aceae319fa6b1c10ae2f51a985a7320e5449d27df7bb2-2026-02-16_10-57-16_1.gif" className="border" />

<Callout icon="📘" theme="info">
  #### Changing a Conversion Event

  Changes such as updating filters, renaming, or modifying the lookback window for a conversion event may take time to reflect on the dashboard. If you delete a conversion event, associated metrics will no longer be visible in ROI Insights.
</Callout>

## Apply Filters

Filters help you narrow down the ROI analysis to specific campaigns by name, channel, time period, owner, and more. When you apply filters, both the _Metric_ tiles and the _Engagement_ performance table update dynamically to reflect only the data that matches your selected criteria.

Use filters to focus on relevant business questions, such as:

* Which campaigns drove the most revenue this quarter?
* How did email campaigns perform compared to push notifications?
* Which campaigns generated the highest conversion rate?
* How are running campaigns performing compared to completed ones?

<Image align="center" border={true} caption="Apply Filters for ROI Data" src="https://files.readme.io/9f2621feb3960da5c4ab3430835459d5e64f5d36428f734c0a41b881d693e439-image.png" />

The following filter fields are available:

| Field Name       | Description                                                                                                                                                                                                                                                                          |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Conversion Event | Select the conversion event to analyze. Update conversions, unique conversions, and conversion rate based on the selected event (for example, compare Total Purchases vs Subscription Started).                                                                                      |
| Campaign Name    | Filter campaigns by name or partial name. Enter an exact campaign name or use a keyword to find campaigns matching a keyword.                                                                                                                                                        |
| Time Period      | Set the date range for analysis. Metrics are filtered by the conversion timestamp, that is, the date and time the conversion event occurred, rather than when the campaign was clicked. This ensures the time period reflects actual conversion activity within the selected window. |
| Campaign Labels  | Filter campaigns by assigned labels. Group and analyze campaigns by themes (for example, Promotional or Onboarding).                                                                                                                                                                 |
| Channels         | Filter campaigns by channel (for example, Email, Push, In-App, SMS). Compare ROI performance across channels.                                                                                                                                                                        |
| Created By       | Filter campaigns by creator. Analyze performance by user or team ownership.                                                                                                                                                                                                          |
| Status           | Filter campaigns by statuses (for example, Running or Completed). Compare active and historical campaign performance.                                                                                                                                                                |
| Delivery Type    | Filter campaigns by delivery type (for example, On Publish or Recurring). Compare always-on and time-bound campaigns.                                                                                                                                                                |

After selecting your required filters, click **Apply** to update the dashboard.

# Understand the ROI Dashboard

After conversion events are configured, the ROI dashboard displays campaign performance in two primary sections:

* [Metric Tiles](doc:roi-insights#metric-tiles)
* [Engagement Performance Table](doc:roi-insights#engagement-performance-table)

## ROI Metric

The _Metrics_ section provides a summary view of the key performance indicators (KPIs) based on selected conversion events and filters. Use metric tiles to quickly assess overall campaign effectiveness before diving into detailed analysis. This information updates dynamically based on applied filters, selected conversion events, and selected time range.

For example, in the following dashboard, the conversion rate appears healthy, but Total Conversions (35.2K) and Unique Conversions (31.5K) are very close, suggesting that most users converted only once. This could indicate an opportunity to drive repeat conversions.

<Image align="center" border={true} caption="View ROI Metric Tiles" src="https://files.readme.io/448d38d6430f775a5beee37067af98ebafcbda373af9fbdb1b6400d32ba055b8-image.png" />

The _Metrics_ section includes the following default metrics:

| Tile Name               | Description                                                                                         |
| ----------------------- | --------------------------------------------------------------------------------------------------- |
| Total Sent              | Messages sent across selected campaigns.                                                            |
| Total Delivered         | Messages successfully delivered to users. It also includes push impressions for Push Notifications. |
| Total Clicked           | Clicks on campaign messages.                                                                        |
| Total Viewed            | Message views (for supported channels like In-App and Push).                                        |
| CTR                     | Percentage of delivered messages that received at least one click.                                  |
| Total Conversions       | Conversion events attributed to selected campaigns within the conversion window.                    |
| Unique Conversions      | Unique users who completed the conversion event.                                                    |
| Conversion Rate Percent | Percentage of delivered (or eligible) messages that led to at least one conversion.                 |

<Callout icon="📘" theme="info">
  Note

  Large metric values are automatically formatted using shorthand notation. For example, 1,000 displays as 1K, 1,000,000 as 1M, 1,000,000,000 as 1B, and 1,000,000,000,000 as 1T for easier readability across tiles and the table.
</Callout>

## Engagement Performance Table

The engagement table displays campaign-level performance metrics. This table allows you to identify top-performing and underperforming campaigns at a glance. For example, the top campaigns by conversion count are email campaigns, while push notifications show a higher CTR but lower conversion rate, useful for deciding where to invest future budget.

<Image align="center" border={true} caption="Engagement Performance Table" src="https://files.readme.io/aceedc4a3372b7e8445397694e07fe296fc34005585ec3b836b0a2ca6d31d671-image.png" />

The following table describes each column in the _Engagement Performance Table_:

| Field Name                  | Description                                                                                            |
| --------------------------- | ------------------------------------------------------------------------------------------------------ |
| Name                        | The campaign name.                                                                                     |
| Status                      | The current campaign status (for example, Running or Completed).                                       |
| Channel                     | The icon representing the campaign's delivery channel (for example, Push, Email, In-App).              |
| Created by                  | The user who created the campaign.                                                                     |
| Campaign Label              | The campaign label for grouping or categorization.                                                     |
| Journey Id                  | The associated journey ID, if available.                                                               |
| Sent                        | Messages sent for the campaign.                                                                        |
| Delivered                   | Messages successfully delivered for the campaign.                                                      |
| Viewed                      | Total message views for the campaign.                                                                  |
| Clicked                     | Total clicks for the campaign.                                                                         |
| CTR                         | The percentage of delivered messages that received clicks.                                             |
| Conversions                 | Conversion events attributed to the campaign.                                                          |
| Unique Conversions          | Unique users who completed the conversion event.                                                       |
| Conversion Rate             | The percentage of delivered (or eligible) messages that led to a conversion.                           |
| Custom KPIs (if configured) | Custom metrics defined to track business-specific goals (for example, revenue or average order value). |

<Callout icon="📘" theme="info">
  #### Note

  In the [Engagement Performance Table](doc:roi-insights#engagement-performance-table):

  * You can click on any campaign in the table row to open its campaign stats page. This gives you quick access to detailed performance data without leaving the ROI dashboard.
  * By default, the table is sorted by Conversion Count in descending order, so the highest-converting campaigns appear at the top.
  * The engagement performance table also includes archived campaigns to ensure your historical ROI data remains accessible even after campaigns are archived.
</Callout>

# Custom Metrics

Custom Metrics let you create derived metrics from the engagement and conversion data available in the ROI dashboard. These metrics help you track business-specific performance indicators that are not available as default tiles or table columns.

Once created, custom metrics appear as additional columns in the Engagement Performance Table and can be used alongside standard metrics. For example, a Revenue metric calculated using `PROPSUM(Purchase.amount)` will appear as a new column alongside Sent, Delivered, and Conversions.

## Create Custom Metrics

To create a custom metric:

1. Click **Add Custom Metric** in the top-right corner of the ROI dashboard.
2. Enter a clear and descriptive name for the KPI. For example, enter _Revenue_ if you are measuring total purchase value.
3. In the formula builder, select a metric from the list. For example, select `PROPSUM` from the function list and select the amount property of your _Purchase_ event.
4. Combine metrics using supported operators.
5. Click **Save**.

   <Image align="center" border={true} caption="Create a Custom Metric" src="https://files.readme.io/9c7ab0fc41f4b367063f352ee1005ff4298dcd91aeed2d89f86f7be9f3c7f03f-image.png" width="70% " />

## How Custom Metrics Work?

Custom Metrics are built using formulas based on your configured conversion events and their properties. Using the formula builder, you can apply event-level and property-level functions to conversion event data to compute totals, ratios, averages, or derived values. Custom KPIs are calculated dynamically and update automatically when filters, the selected conversion event, or the time range are changed.

The following examples illustrate how Custom Metrics can be built from conversion event data to measure business-specific outcomes:

| KPI Name                        | Formula                                           | What does it help you measure?                                                                                                                                                                                                   | Example                                                                                                                                                    |
| ------------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Revenue                         | PROPSUM(Purchase.amount)                          | The total revenue generated from all Purchase conversion events in the selected period. It sums up the value of the `amount` property across every Purchase event occurrence.                                                    | If 500 users made purchases of amounts such as $20, $50, and $100, Revenue returns the total purchases. For example, $35,000 for the selected time period. |
| Average Order Value (AOV)       | PROPAVG(Purchase.amount)                          | The average transaction value per Purchase event. It divides the total value of the `amount` property by the number of Purchase event occurrences, helping you understand what a typical order is worth.                         | If the total revenue from 500 purchases is $35,000, AOV returns $70, meaning customers spend $70 on average per order.                                     |
| Average Revenue Per User (ARPU) | PROPSUM(Purchase.amount) / UNIQUES(Purchase)      | The average revenue generated per unique user who completed a Purchase event. Unlike AOV, which is per transaction, ARPU accounts for users who may have purchased multiple times, giving you a per-user revenue view.           | If 300 unique users generated $35,000 in total revenue, ARPU returns approximately $116.67, meaning each converting user contributed $116.67 on average.   |
| Profit                          | PROPSUM(Purchase.amount) - PROPSUM(Purchase.cost) | The net profit from all Purchase events in the selected period, calculated by subtracting the total cost from the total revenue. This helps you evaluate whether your campaigns are driving financially sustainable conversions. | If total revenue (PROPSUM of `amount`) is $35,000 and total cost (PROPSUM of `cost`) is $22,000, Profit returns $13,000.                                   |

### Formula Functions

When creating a Custom Metric, you can use predefined event-level and property-level functions to build meaningful business metrics. These functions must always be written in uppercase.

#### Event-Level Functions

These functions operate on the selected event and measure the event's frequency or user participation:

* **TOTALS**: Counts every occurrence of the selected event during the chosen time period. For example, if an event such as `Video Played` occurred 12,000 times, TOTALS returns 12,000 even if the same user triggered the event multiple times.
* **UNIQUES**: Counts the number of distinct users who performed the selected event. For example, if 2,000 unique users triggered the event, UNIQUES returns 2,000; each user is counted only once, regardless of how many times they performed the event.
* **AVERAGE**: Shows the average number of times each unique user performed the selected event. For example, if 3,000 users triggered the event 15,000 times in total, AVERAGE returns 5 events per user. This can also be derived using TOTALS / UNIQUES.

#### Property-Level Functions

Property-level functions operate on numeric event properties such as revenue amount, duration, quantity, or price. These functions are available only when a numeric event property is selected.

* **PROPSUM**: Adds up the total value of the selected numeric event property across all event occurrences. For example, if you select the `amount` property for a purchase event, PROPSUM returns the total revenue generated in the selected period.
* **PROPAVG**: Calculates the average value of the selected numeric event property per event occurrence. For example, if you select the `duration` property for a video event, PROPAVG returns the average watch time per video play. This can also be derived using PROPSUM / TOTALS.

### Formula Guidelines

When creating a custom metric, keep the following in mind:

* You can combine available metrics using operators such as +, -, *, /, and parentheses ().
* The formula must be mathematically valid.
* KPI names should clearly describe the metric being calculated.
* Custom Metrics are calculated per campaign row in the table.

## Custom Metric Operations

You can edit or delete any existing custom metric directly from the ROI dashboard.

### Edit

To edit a custom metric:

1. Click the ![](https://files.readme.io/6b504ffa8b8740dfb7348087b0c7871d61c1fd30c7bdc67f9cffdd978e4d01ec-Ellipsis_icon_Boards.png) icon next to the metric name you want to edit.
2. Update the _Name_, _Description_, or _Formula_ as needed.
3. Click **Save**.

<Image align="center" border={true} caption="Edit a Custom Metric" src="https://files.readme.io/3f9a279704e9d47def9f525fa7205ed326d27acf374facf018afb195ee0b2ea0-2026-05-05_17-12-32_1.gif" />

### Delete

To delete a custom metric:

1. Click the <Image border={true} src="https://files.readme.io/6b504ffa8b8740dfb7348087b0c7871d61c1fd30c7bdc67f9cffdd978e4d01ec-Ellipsis_icon_Boards.png" className="border" /> icon next to the metric name you want to delete.
2. Click **Delete**.

<Image align="center" border={true} caption="Delete a Custom Metric" src="https://files.readme.io/2794052449b14e9e8076eee75209227f19bd3860338c38d23dd05dabea3a6db9-2026-05-05_17-14-51_1.gif" />

<Callout icon="📘" theme="info">
  #### Note

  Deleting a custom metric removes it permanently from the table. This action cannot be undone.
</Callout>

# Best Practices

Follow these best practices to ensure that your ROI analysis remains accurate, actionable, and aligned with your business objectives

* Define conversion events aligned with business goals.
* Use revenue events when analyzing financial impact.
* Apply filters before drawing conclusions.
* Limit custom metrics to meaningful business metrics.
* Regularly review and refine conversion windows.

# FAQs

Find answers to the following common questions about using ̉ROI Insights:

### How many conversion events can I configure?

You can configure up to five conversion events.

### Can I track revenue without defining a revenue property?

No. Revenue metrics require a numeric property associated with the conversion event.

### Do filters affect exports?

Yes. Exports reflect the current filter and conversion event selection.

### Can I compare multiple conversion events at once?

ROI Insights allows switching between configured conversion events, but metrics are displayed for one selected conversion event at a time.

### What attribution model does ROI Insights use?

ROI Insights uses a Last Touch Attribution model based on the most recent Notification Clicked event prior to conversion. For more information, refer to [Attribution Model](doc:roi-insights#attribution-model).

### Can I use a different attribution model?

No. Only Last Touch Attribution is supported in this version. Alternative attribution models, such as first-touch or time-decay, are not available.

### Are conversion goals campaign-specific?

No. ROI Insights uses account-level conversion events configured. These apply across all campaigns and journeys in your CleverTap account.
