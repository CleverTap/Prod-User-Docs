---
title: Pivots 2.0
excerpt: >-
  Learn how to analyze event data across multiple dimensions using interactive
  tables and visualizations to uncover patterns, trends, and insights.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Pivots 2.0 is an analytics capability that helps you derive meaningful insights from your user data by summarizing events in interactive tables and visualizations. It lets you break down large volumes of data across multiple dimensions, such as events, segments, properties, and time, so you can quickly spot patterns, trends, and outliers without writing complex queries.

A pivot analysis helps answer questions such as:

* Which product categories are performing best, and at what time of day?
* In which city are sales for a specific brand or product the lowest?
* How much sports content do premium users consume across different days of the week?

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information about this feature or any queries, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

# Create a Pivot Analysis

To build a pivot analysis, you configure a query in the Query Builder. The Query Builder is organized into four core steps that define what data you analyze, which users it applies to, how results are grouped, and what metric is calculated.

To get started, go to _Analytics_ > _Pivots_ and select the following fields:

* [Select Event](doc:pivots-v2#select-event)
* [Select Segment](doc:pivots-v2#select-segment)
* [Select Properties](doc:pivots-v2#select-properties)
* [Select Metric](doc:pivots-v2#select-metric)

## Select Event

Start by selecting the event you want to analyze. The selected event serves as the foundation for the pivot. It defines the underlying dataset and determines which event properties are available for grouping and filtering.

For example, you can analyze events such as `App Launched`, `UTM Visited`, `Product Viewed`, `Video Watched`, or `Charged`. Choose an event that represents the user action you want to measure. For value-based analysis (for example, revenue or watch time), select an event that includes a numeric property you can aggregate.


<Image src="https://files.readme.io/b3cddc152ed699635284236f480f6ab6cfc94a7632f97bd04720cf16fa72aad4-image.png" align="center" caption="Select an Event" border={true} />


The selected event determines:

* The event data included in the analysis
* The event properties available to pivot on
* The metric options available (for example, event count or sum of a numeric property)

## Select Segment

After you select an event, choose who you want to analyze it for. By default, Pivots analyzes the event for All Users, but you can restrict the analysis to a specific segment. You can also create a new segment directly from the Query Builder.


<Image src="https://files.readme.io/c3c3caf4dbbb5d3680c62c71aec1cf2f1b4fc0f67ec54f4b1958bd21e025de2b-image.png" align="center" caption="Select a Segment" border={true} />


Segmenting is useful because user behavior often varies significantly across segments. For example, you can:

* Compare engagement between New Users and Returning Users
* Analyze purchases for High-Value Users
* Understand content consumption for Subscribed vs Free users

<Callout icon="📘" theme="info">
  #### Content Consumption Example

  Viewing behavior for new users is often different from users who have already consumed 50+ hours of content. Segmenting helps you compare these groups and tailor campaigns accordingly.
</Callout>

## Select Properties

Properties define how you break down the selected event and compare results across dimensions. In Pivots, you can mix and match properties to explore different analytical angles. Selected properties can be used as rows, columns, or axes (depending on the visualization).


<Image src="https://files.readme.io/cc2b583f401c8525c7d35cb0d634f9070dea2f4d967e79402ada93494d778ff9-image.png" align="center" caption="Select Properties" border={true} />


You can pivot on:

* Event properties (for example, product name, content category)
* User profile properties (for example, language, customer type)
* Geographic properties (for example, city, country)
* Technographic properties (for example, device type, OS)
* App fields (for example, app version)

<Callout icon="❗️" theme="error">
  #### Property Selection Limit

  In a pivot analysis, you can select a maximum of seven properties at once. Using too many properties at once can make results harder to interpret, especially for properties with highly unique values (for example, user IDs or URLs). Therefore, we recommend that you start with one or two properties and expand gradually.
</Callout>

### Query Nested Properties

If your events carry [Nested Objects](doc:nested-objects) in their [event properties](doc:nested-objects-in-custom-event-properties), the query builder lets you drill down into them. In Pivots, you can use a nested property in the following places in your query:

* Filter
* Properties (count toward the limit of seven properties)
* Metric

To select a nested property in a Pivot's event filter:

1. Go to _Analytics_ > _Pivots_ and select an event to analyze and view a trend. For example, `Order Placed`.
2. Click the option for the action you want, such as **+ Filter**, and then select **Event Property**.
3. Select the parent property, such as `Order`. A dropdown for the next level appears.
4. Keep selecting a property at each level until you reach the one you want, such as `Order ↳` `Shipping ↳` `Address ↳` `City`.
5. (Optional) To change a level, click its pill and select a different property. After the pills are removed, you can select the remaining levels again.
6. Click **View Analysis**.

<Image src="https://files.readme.io/b8c496d95ec4acf8e1391b27f794d9f5912e1834c5fae2097f73c0ba10899876-image.png" alt="Using Nested Properties in a Query" align="center" caption="Using Nested Properties in a Query" border={true} />

Each level you select appears as its own pill, and a `↳` marks a level that has more properties inside it. Arrays are shown with square brackets, such as `Items[]`. For example, the `Order Placed` event can carry the following nested properties:

* `Order ↳` `Shipping ↳` `Address ↳` `City`
* `Items[] ↳` `Attributes ↳` `Size`
* `Items[] ↳` `Price`

## Select Metric

The Metric setting defines what you want to measure for the selected event. It controls whether Pivots reports results as event frequency, property values, or aggregated totals.)


<Image src="https://files.readme.io/39c790815dbde2684adf511253cca8e897f81af7c5b40c3ed35d2fb31fe098cc-image.png" align="center" caption="Select a Metric" border={true} />


Pivots 2.0 supports the following metric types:

* [Event Count](doc:pivots-v2#event-count)
* [Event Property](doc:pivots-v2#event-property)

### Event Count

Event Count measures the number of times the selected event occurred. Use this option to measure how often something happens.

For example, count of `Product Viewed` events by `Product Category` and `Day of Week`.

### Event Property

Event Property lets you measure event data using a specific event property. Use this option when you want to measure how much value is generated.

For example, you can analyze `Charged` events broken down by the `payment_method` property to compare conversion contribution across payment types.

### Metric Display Options

The Metric Display dropdown controls how the selected metric is calculated and presented in the pivot table. The available options in this dropdown depend on whether you are analyzing Event Count or an Event Property.

#### When Event Count is Selected

If no event property is selected and the metric is set to Event Count, the following display options are available:

* **Count**: Displays the absolute number of times the event occurred.
* **Count as Fraction of Total**: Displays each value as a percentage of the total event count across the entire table. Use this option to understand overall contribution.
* **Count as Fraction of Rows**: Displays each value as a percentage of the total count within the same row. Use this option to compare distribution across columns for each row.
* **Count as Fraction of Columns**: Displays each value as a percentage of the total count within the same column. Use this option to compare distribution across rows for each column.

These options are useful when your analysis focuses on frequency and distribution rather than numeric values.


<Image src="https://files.readme.io/5f80ff38e8f5f6d26635118b9f5daf0a1538083937139c6f4b53ab96034836c2-image.png" align="center" caption="When Event Count is Selected" border={true} />


#### When an Event Property is Selected

When you select an Event Property as the metric (for example, `CT App Version`, `amount`, or `duration`), additional information is displayed. This information is dynamically generated based on the selected property.

For example, if the selected event property is _Duration_, the following options appear:

* **Total Duration**: Displays the total aggregated value of the selected event property
* **Average Duration**: Displays the average value of the selected event property for each cell.
* **Duration as Fraction of Total**: Displays each value as a percentage of the total aggregated value across the entire table. Use this option to understand overall contribution of each segment or category.
* **Duration as Fraction of Rows**: Displays each value as a percentage of the total aggregated value within the same row. Use this option to compare how values are distributed across columns for each row.

These additional options allow you to move beyond event frequency and analyze value-based performance, such as revenue contribution, average duration, or property-level impact.


<Image src="https://files.readme.io/e333fd745e2679f0e82e23c9441c4495985b23007872b662516c60151945ecb4-image.png" align="center" caption="When Event Property is Selected" border={true} />


<Callout icon="📘" theme="info">
  #### Dynamic Metric Options

  The names of these metric display options change automatically based on the event property you select. For example, selecting the `Duration` property will show options such as `Total Duration`, `Average Duration`, `Duration as Fraction of Total`, and `Duration as Fraction of Rows`.
</Callout>

# Best Practices

Follow these best practices to choose the right metric display and interpret pivot results accurately:

* Use _Count-based options_ to analyze how often an event occurs.
* Use _Total_ or _Average_ property options to analyze value-driven metrics.
* Use _Fraction of Total_, _Rows_, or _Columns_ to understand distribution and relative contribution.

# Example Use Case: Content Consumption Analysis

A video streaming app that wants to understand content performance beyond simple view counts. Instead of measuring only how often a video is watched, the team wants to measure total watch time per video, which better reflects engagement.

To do this, the team builds the following pivot query:

* **Event:** `Video Started` (triggered when a user starts watching a video)
* **Segment**: All Users
* **Properties**:
  * Day of Week (Session)
  * Title (Event Property)
* **Rows:** Day of Week
* **Columns:** Title (Video name)
* **Metric:** Duration (Event Property)


<Image src="https://files.readme.io/b619008fe450e12c37eff89d0a9da80c8d12863db69d81d523c071f4860b585b-image.png" align="center" width="50% " caption="Pivot Query" border={true} />


Using the `Duration` event property measures performance by total consumption time, not just the number of views. This is useful when some videos have fewer views but generate more watch time due to longer duration or stronger retention.

With this pivot query, you can derive insights such as:

* Which videos drive the highest total watch time?
* Which days of the week contribute most to consumption for each video?
* Which videos have consistent engagement vs. sharp spikes on specific days?
* Where to optimize promotion and scheduling based on consumption patterns?

# Reading the Pivot Analysis

After you run a pivot query, Pivots generates an analysis that you can explore and interpret using the following components:

* [Pivot Distribution](doc:pivots-v2#pivot-distribution)
* [Visualizations](doc:pivots-v2#visualizations)

Together, these components help you rearrange your data and view it from multiple perspectives to uncover patterns, contributors, and trends.

## Pivot Distribution

Pivot distribution allows you to arrange the set of properties you selected in the query builder. You can use these properties in different combinations by dragging and dropping to break down the selected event and explore patterns in the data.

Depending on the view you choose, these properties can be applied as Rows and Columns in a table.

* **Rows**: Represent the primary dimension used to group results in the table view. For example, a row can represent the video Title in your analysis table.
* **Columns**: Represent the secondary dimension used to group results in the table view. For example, a column can represent Day of the Week in your analysis table.


<Image src="https://files.readme.io/08676d8e03979c5db30f85ee04c70cff275024bd605321a6d1380b81229e6049-image.png" align="center" caption="Arranging Rows and Columns" border={true} />


Using rows and columns together creates a matrix that makes it easy to compare values across multiple dimensions.

## Visualizations

Pivots support multiple visualization types to help you interpret the same grouped data in different ways. Each visualization highlights a different aspect of your data, depending on whether you want precision, comparison, or trend-based insights.

You can switch between the following visualization options without changing the underlying query:

* [Table](doc:pivots-v2#table)
* [Heatmaps](doc:pivots-v2#heatmaps)
* [Row Heatmap](doc:pivots-v2#row-heatmap)
* [Column Heatmap](doc:pivots-v2#column-heatmap)
* [Bar Chart](doc:pivots-v2#bar-chart)
* [Stacked Bar Chart](doc:pivots-v2#stacked-bar-chart)
* [Line Chart](doc:pivots-v2#line-chart)
* [Area Chart](doc:pivots-v2#area-chart)

### Table

Tables are best for getting a quick, precise overview of the selected breakdown. Use this view when you need exact numbers or want to export results. This view is best for identifying the highest contributors in the dataset.

For example, if the rows are _Day of the Week_ and the columns are _Title_, this view helps you quickly identify which video contributes the most watch time and which day it peaks.


<Image src="https://files.readme.io/61e3e6f03da0ea9a3c59c556c51cd27e6873ddc2abb5a66de6ba367c6564b3d1-image.png" align="center" caption="Table View" border={true} />


### Heatmaps

Heatmaps use color intensity to represent magnitude, making it easy to identify high-performing and low-performing areas in your data at a glance. This view is especially useful when you want to quickly spot patterns across rows and columns, identify peaks, dips, and anomalies, or compare relative performance without focusing on exact values.

For example, if rows represent _Day of the Week_ and columns represent _Title_, the heatmap helps you quickly identify which videos and days contribute the most watch time.


<Image src="https://files.readme.io/5e88518dc17a179a242102a0068e22779a157683e063b090a8ff79f83a93682e-image.png" align="center" caption="Row Heatmap View" border={true} />


### Row Heatmap

The Row Heatmap highlights variations within each row, making it easy to identify outliers and strong performers for a given row dimension.

Use this view when you want to:

* Understand how different values perform within the same row group
* Detect row-specific patterns or preferences
* Identify which columns stand out for a particular row

For example, if each row represents a _Day of the Week_ and columns represent _Title_, this view helps you identify which videos perform best on each day. This is useful for spotting day-specific engagement patterns, such as certain videos peaking on weekends.


<Image src="https://files.readme.io/ea1cb25a8b52f3c1bf178996a119110ef7d834229dc6b38170af70a323a5e497-image.png" align="center" caption="Row Heatmap View" border={true} />


### Column Heatmap

The Column Heatmap highlights variations within each column, helping you compare how values perform relative to other entries in the same column.

Use this view when you want to:

* Identify the strongest and weakest values for each column dimension
* Compare performance patterns across columns independently
* Spot deviations from a column’s typical trend

For example, if each rows represent _Day of the Week_, and column represents a _Title_, this view helps you identify:

* The best-performing day for each video
* Days where a specific video significantly outperforms or underperforms its usual behavior


<Image src="https://files.readme.io/3734b7e3b73e69abfbd1ba70d622d54e3bfc2ac0ba7a40f58b355f8c7d413c98-image.png" align="center" caption="Column Heatmap View" border={true} />


<Callout icon="📘" theme="info">
  #### Zero Event Occurrences in Heatmap Views

  If there are zero event occurrences for a given combination of row and column values, heatmap views may show that cell as whitespace.
</Callout>

### Bar Chart

The Bar Chart is best for comparing categorical performance along a primary dimension, with clearly distinguishable bars.

Use this view when you want to:

* Compare values across categories at a glance
* Highlight differences between groups
* Focus on relative performance rather than trends over time

For example, you can compare watch time for a specific video across different days of the week to quickly see which days perform better or worse.


<Image src="https://files.readme.io/397ef8bd21836ac91c452c1e64302bd322a6538b705139a666159613db0b4963-image.png" align="center" caption="Bar Chart View" border={true} />


### Stacked Bar Chart

The Stacked Bar Chart shows how multiple categories contribute to a total across a primary dimension. Each bar represents the total value for a category on the x-axis, while the stacked segments within the bar show the contribution of individual subcategories.

Use this view when you want to:

* Understand how different categories contribute to an overall total
* Compare contributors within the same category
* Identify which segments or properties drive overall performance

For example, if the x-axis represents _Day of Week_ and each stacked segment represents a _Title_, this view shows how different videos contribute to total watch time on each day. This helps you identify which titles dominate consumption on specific days, which remain consistent across the week, and where spikes or drop-offs occur.


<Image src="https://files.readme.io/9fd68ad09905e77103a287e300fd0d04e9128a2c94266b4ba079624429a097b4-image.png" align="center" caption="Stacked Bar Chart View" border={true} />


### Line Chart

The Line Chart is best for visualizing changes over time and comparing trends across multiple categories on the same timeline.

Use this view when you want to:

* Track how values evolve over time
* Compare trend patterns across categories
* Identify correlations or parallel behavior

For example, you can identify videos that follow similar engagement trends across the week, which may indicate comparable audience interest or content affinity.


<Image src="https://files.readme.io/bbc62357a79d5e1be9fd5be269d018816eccd9feb9608a672272239dc3b4c2e8-image.png" align="center" caption="Line Chart View" border={true} />


### Area Chart

The Area Chart is similar to a line chart but emphasizes part-to-whole relationships by stacking or filling values.

Use this view when you want to:

* Understand how individual categories contribute to the total over time
* Visualize cumulative impact
* Compare relative contribution alongside trends

For example, you can track how a single video contributes to total watch time across the week compared to all other videos combined.


<Image src="https://files.readme.io/e55a4167664485b1d8c5423e1d5d1cc64df8be6abac5a6cad3a50945f4a36530-image.png" align="center" caption="Area Chart View" border={true} />


# Bookmark a Pivot Analysis

You can bookmark any Pivot analysis to revisit it later quickly. Bookmarks are user-specific, meaning only the logged-in user can view their saved Pivot analyses in the CleverTap dashboard.

Bookmarks are especially useful for tracking frequently used analyses. For example, if you regularly monitor revenue by product and day of week, bookmarking the Pivot analysis allows you to return to the same configuration without rebuilding the query each time.

To bookmark a Pivot analysis:

1. Click **Bookmark** in the top-right corner of the dashboard after running the Pivot analysis.
2. Enter a descriptive name to help you easily identify the analysis later.
3. Click **Bookmark**.


<Image src="https://files.readme.io/f2e2c814ca8f6c6f7fd89089fc35238d80667d923bda5b8e3716c103f9959f66-2026-01-27_16-12-26_1.gif" align="center" border={true} />


<Callout icon="📘" theme="info">
  #### Bookmarking a Pivot Analysis

  You can add up to 50 bookmarks. Pivot analyses are accessible only to the user who created them. You can access all your saved bookmarks from the bookmark list under the _Pivots_ section.
</Callout>

<br />

<br />