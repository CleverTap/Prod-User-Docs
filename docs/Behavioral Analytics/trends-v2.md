---
title: Trends 2.0
excerpt: >-
  Learn to use the new and improved visualization of your data using Trends to
  gain deeper insights and make informed decisions.
deprecated: false
hidden: false
metadata:
  title: Trends Vnext
  description: ''
  keywords:
    - New Trends
  robots: index
next:
  description: ''
---
# Overview

CleverTap's Trends feature provides advanced tools for analyzing and visualizing data, offering a comprehensive understanding of user behavior. The key functions include the following:

* _Selection Capabilities_: Users can choose event-level data, event properties, and user properties and specify analysis periods for deeper insights.
* _Advanced Filtering and Segmentation_: Robust filtering options and the ability to segment data for a targeted analysis.
* _Visualization Tools_: Trends can be visualized using various metrics, such as trendlines, conversion metrics, anomaly detection, and retention metrics.

These capabilities give users a powerful way to optimize platform usage and enable them to make informed decisions to drive business outcomes.

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information about this feature or any queries, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

Using the _Trends_ dashboard, users can:

* Plot and analyze trends of event occurrences.
* Compare trends of multiple events to uncover patterns.
* Examine trends across different event property values.
* Compare event trends by user properties.
* Summarize trends using event properties.
* Compare trends across multiple segments.

# Getting Started

The Trends dashboard enables you to visualize data by segmenting events based on event properties and user-defined segments. You can further refine these segments by splitting them based on user properties.

Results can be displayed in various formats, such as trendlines, pie charts, and more, and can be viewed over different time periods, such as days, or months. You also have the option to download the resulting visualizations or pin the analysis to a board for continuous updates. Additionally, you can download these results in a CSV file.

<Callout icon="📘" theme="info">
  ### Event and Segment Limit

  You can select up to five events and five segments for analysis.
</Callout>


<Image src="https://files.readme.io/79923bce74d05b0178c3541a856d3dc7bc7315b9d7ea2b06e75e5fb0e7668587-image.png" alt="Trend Analysis" align="center" caption="Trend Analysis" border={true} />


# View a Trend

To set up a trend analysis, select the event you would want to analyze. You can also restrict your analysis further to a specific property of that event.

To view a trend:

1. Go to _Analytics_ > _Trends_ and select an event to analyze from the _EVENTS_ section to view a trend. For example, you want to analyze all the users who launched the app.
2. Click **View Analysis**.


<Image src="https://files.readme.io/f07eb1911a1e56da4f0f3fbe668a21f313b57abfd37ce778851a4fd5beeb5c0c-View_Trends_Main.jpg" alt="View a Trend" align="center" caption="View a Trend" border={true} />


The trend results are displayed. Hovering over the trendline shows the percentage increase or decrease for the selected time frame and other event information.

You can change the view period of the trend on a daily or monthly basis:


<Image src="https://files.readme.io/4430a0dfe39b74984c3aa6b32c7e07ac3f23831f4c38b5838a148f3755d33ea6-image.png" alt="Viewing period" align="center" caption="Viewing period" border={true} />


* _Daily_: The trend and data points are plotted on a daily basis.
* _Monthly_: The trend and data points are plotted on a daily basis.

# Measure a Trend

The Measure section defines how the selected event is quantified in your trend analysis. While the event determines what user action you are analyzing, the Measure determines how that action is calculated and displayed over time. It gives you the flexibility to switch between volume, participation, intensity, value, penetration, and derived metrics, allowing you to explore trends from multiple analytical perspectives without changing the underlying event selection.

In Trends 2.0, you can choose from the following measurement options:

* [Total Events](doc:trends-v2#total-events)
* [Unique Users](doc:trends-v2#unique-users)
* [Average per User](doc:trends-v2#average-per-user)
* [Summarize By (Event Property)](doc:trends-v2#summarize-by-event-property)
* [Active Percentage (%)](doc:trends-v2#active-percentage-)
* [Formula](doc:trends-v2#formula)

Each option changes both the trend visualization and the summary statistics displayed in the table.

## Total Events

_Total Events_ displays the sum of event occurrences during the selected time period. Every occurrence of the event is counted, even if the same user performs the event multiple times.

For example, if a user places 3 orders in one day, all 3 `Order Placed` events are counted.


<Image src="https://files.readme.io/f14752741c967e3d7f9e740f64e96d85d060a272c2ad46344219f8e61c13e0aa-image.png" align="center" caption="Measure by Total Events" border={true} />


Use this measure when you want to understand overall activity volume, such as:

* Total number of orders placed
* Total number of restaurants viewed
* Total number of app launches

## Unique Users

_Unique Users_ displays the number of distinct users who performed the selected event in the specified time period. Each user is counted once per time interval, regardless of how many times they performed the event.

For example, if a user places multiple orders in a single day, they are counted once for that day in the trend.


<Image src="https://files.readme.io/b61527e787f0b50129a68a77dfa97bcff0de733c64ebe199a1add2aba983814c-image.png" align="center" caption="Measure by Unique Users" border={true} />


Use this measure when you want to understand user participation, such as:

* How many users placed at least one order
* How many users viewed a restaurant
* How many users added items to cart

## Average per User

_Average per User_ displays the average number of times each unique user performed the selected event in the specified time period. It is calculated as `Total Events / Unique Users`.

For example, if 1,000 users placed 5,000 orders during the selected period, the average per user is 5 orders.


<Image src="https://files.readme.io/1de717c723d5f607e9aa52b7819d41629d88889bf2530d4743b89fcda638d279-image.png" align="center" caption="Measure by Average per Users" border={true} />


Use this measure when you want to analyze engagement intensity, such as:

* Average number of orders per user
* Average number of app launches per user
* Average number of items added to cart per user

## Summarize By (Event Property)

_Summarize By_ allows you to aggregate trends using a numeric event property rather than simply counting events or users. Use Summarize By when analyzing value-based metrics such as revenue, order size, watch time, or duration.

This option becomes available when the selected event contains a numeric property, such as, `order_amount`, `delivery_time`, `discount_value`, `duration` and so on.


<Image src="https://files.readme.io/9a79d96f6ea417505a373e038eee7a6ef80ac7ed2fcfeafae5e937728bd4992f-image.png" alt="Measure by Summarize by (Event Property)" align="center" caption="Measure by Summarize by (Event Property)" border={true} />


You can summarize the trend using:

* [Sum of Property Value](doc:trends-v2#sum-of-property-value)
* [Average of Property Value](doc:trends-v2#average-of-property-value)


<Image src="https://files.readme.io/a15a0fc8337db2823db99c2bdac8f07d754e8bb2509e629da22ba3cf84bdcdb7-image.png" alt="Measure Sum and Average of a Trend Analysis" align="center" caption="Measure Sum and Average of a Trend Analysis" border={true} />


### Sum of Property Value

Displays the total value of the selected numeric property across all event occurrences.

For example, summarizing `Order Placed` by `order_amount` shows total revenue over time.

### Average of Property Value

Displays the average value of the selected property per event occurrence.

For example, summarizing `Order Placed` by `order_amount` using average shows the average order value over time.

## Active Percentage (%)

Active Percentage displays the proportion of users who performed the selected event out of the total active users during the selected period.

For example, if 10,000 users launched the app (qualifying event) and 4,000 users placed an order, the Active Percentage for `Order Placed` is 40%.


<Image src="https://files.readme.io/21bf244d0982952c0be416bbef173e699fc8bfb7d86e9e258c1a4411ef5be98f-image.png" align="center" caption="Measure by Active Percentage (%)" border={true} />


Use this measure to understand behavioral penetration among active users, such as:

* What percentage of active users placed an order?
* What percentage of active users added items to cart?
* What percentage of active users completed checkout?

<Callout icon="📘" theme="info">
  #### Configure Qualifying Events

  Active users are defined based on a qualifying event configured in the Schema settings. To configure the qualifying event, refer to [Qualifying Events](doc:schema#qualifying-event).
</Callout>

## Formula

The Formula option allows you to create custom metrics. You can do so by combining event-level and property-level functions using mathematical expressions. Use Formula when you want to calculate derived business metrics that are not directly available through standard measures, such as Total Events or Unique Users.

For example, in a food delivery app, you may want to:

* Measure revenue per active user
* Compare total orders vs total users
* Track average order value alongside total revenue
* Analyze order conversion relative to app launches

### How Formulas Work?

When you select Formula as the measurement, you define a formula using supported functions. The system then computes the result for each time interval, and the computed values are plotted as a trend line. The same values appear in the table view as well.

You can use predefined event-level and property-level functions to create meaningful business trends. These functions must always be written in uppercase.

<Tabs>
  <Tab title="Event-Level Functions">
    These functions use the selected event and measure its frequency or user participation:

    * **TOTALS**: Counts every occurrence of the selected event during the chosen time period. For example, if an event such as Video Played occurred 12,000 times, TOTALS returns 12,000 even if the same user triggered the event multiple times.
    * **UNIQUES**: Counts the number of distinct users who performed the selected event. For example, if 2,000 unique users triggered the event, UNIQUES returns 2,000; each user is counted only once, regardless of how many times they performed the event.
    * **AVERAGE**: Shows the average number of times each unique user performed the selected event. For example, if 3,000 users triggered the event 15,000 times in total, AVERAGE returns 5 events per user. This can also be derived using TOTALS / UNIQUES.
    * **ACTIVE**: Counts users who were active by performing the selected event within the chosen time period. For example, if 800 users triggered the event during the selected range, ACTIVE returns 800 active users.
  </Tab>

  <Tab title="Property-Level Functions">
    Property-level functions use a numeric event properties such as revenue amount, duration, quantity, or price. These functions are available only when a numeric event property is selected.

    * **PROPSUM**: Adds up the total value of the selected numeric event property across all event occurrences. For example, if you select the amount property for a purchase event, PROPSUM returns the total revenue generated in the selected period.
    * **PROPAVG**: Calculates the average value of the selected numeric event property per event occurrence. For example, if you select the duration property for a video event, PROPAVG returns the average watch time per video play. This can also be derived using PROPSUM / TOTALS.
  </Tab>
</Tabs>

### Formula Guidelines

When creating a custom metric, follow these guidelines:

* You can combine available metrics using operators such as +, -, \*, /, and parentheses ().
* You can compare up to four formulas in the same configuration by separating them with a semicolon (;).
* The formula must be mathematically valid.

### Example Formula: Average Order Value

Consider an example where you want to measure how much revenue each purchasing user generates (that is, Average Order Value) over time.

You can define the following formula as:

`PROPSUM ( Charged.Amount) / TOTALS ( Charged )`


<Image src="https://files.readme.io/950fd5560b351627bc469a195d0ce630ad318bb8933f3ea63c042ce98f73eb80-image.png" align="center" caption="Measure by Formula" border={true} />


### Using Multiple Formulas in One Analysis

Trends 2.0 allows you to compare up to four formulas in a single chart. Each formula is calculated independently and plotted as its own series on the same chart. This allows you to visually compare related business metrics without creating multiple analyses. Keep formulas logically related to avoid clutter and improve interpretability.


<Image src="https://files.readme.io/efbd2f5b3aa77f09d8d86b48791b61159e1be6b908441f7683bb092cc1426fdf-image.png" align="center" caption="Multiple Formulas in One Analysis" border={true} />


Use multiple formulas when you want to:

* Compare volume vs value (for example, orders vs revenue)
* Compare totals vs averages
* Analyze both the numerator and the denominator of a ratio
* Identify what is driving growth (more users vs higher spend per user)

To add multiple formulas, separate each formula using a semicolon (;).

For example, `PROPSUM ( Charged.Amount ); UNIQUES ( Charged ); PROPSUM ( Charged.Amount ) / UNIQUES ( Charged )`

This will display the following three separate trend lines:

* Total Revenue
* Total Purchasing Users
* Revenue per Purchasing User


<Image src="https://files.readme.io/d8faa03164c0e2cdde28a3cad4999a844d4a0b0e61b0918fcc887f6fd0f2e809-image.png" align="center" caption="Measure by Multiple Formulas in One Trend" border={true} />


### Using the Y-Axis Title Field Effectively

When using formulas, especially ratio or derived metrics, the Y-axis may no longer represent simple counts. The Y-axis Title field lets you clearly describe what the chart measures. The axis title should reflect the metric being calculated, not the underlying event. Using clear axis titles ensures that anyone viewing the chart can immediately understand what the trend represents without needing to interpret the formula itself.

The following examples illustrate how to translate formulas into stakeholder-friendly axis titles:

| Formula                                             | Recommended Y-axis Title    |
| :-------------------------------------------------- | :-------------------------- |
| PROPSUM ( order.amount ) / UNIQUES ( Order Placed ) | Revenue per Purchasing User |
| PROPSUM ( Order Placed ) / TOTALS ( App Launched )  | Orders per App Launch       |

### Best Practices for Y-Axis Titles

Follow these best practices when writing Y-Axis Titles for your formulas:

* Use business-friendly language instead of function names
* Avoid technical terms like PROPSUM or UNIQUES
* Clearly indicate if the metric is a percentage or a ratio
* Keep titles concise but descriptive
* If comparing multiple formulas, choose a neutral but descriptive title such as:
  * Revenue & User Metrics
  * Order Performance Ratios

# Compare Trends for Events

You can compare trends for multiple events. For example, you can understand the correlation between two events, such as App Launched and Notification Viewed.

To view a trend, perform the following steps:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. You can also filter your analysis further by the event property.
2. Click **Add Event** to add another event for comparison.
3. Click **View Analysis**.


<Image src="https://files.readme.io/9123233f0a9485ce41f62ece0f3a3f26421a450f9da8233d9bf4933d4c16384d-Compare_Trends.jpg" alt="Compare Trends for different events" align="center" width="100%" caption="Compare Trends" border={true} />


## Filter by Event Property

When selecting an event for analysis, you can restrict the search criteria by filtering based on the specific event properties. All subsequent analyses are performed using these filtered event properties, while other properties of the selected event are excluded.

To filter a trend by event property:

1. Go to _Analytics_ > _Trends_ and select an event to analyze from the _EVENTS_ section and view a trend. For example, you want to analyze only those users who viewed In-App notifications.
2. Click **+ Filter** to filter by an event property that is In-App.
3. Click **View Analysis**.

The resulting trend filters users who viewed notifications from an in-app notification. It does not include users who viewed other types of notifications, such as Email or the Web. Any further analysis of this event will focus exclusively on users who viewed notifications from the In-App campaign.


<Image src="https://files.readme.io/0ae068a6ae0702833c24dff297308064596016dc0cd218f9416d585b4b4028ff-Trends_filter_by_event.jpg" alt="Filter Event by Property" align="center" caption="Filter Event by Property" border={true} />


## Split by Event Property

You can split your event analysis by specific event properties. For example, consider the `Charged` event, which indicates a user has made a purchase. You can split this event by its underlying properties, such as `Payment Mode`, `Amount`. This divides your single `Charged` trend line into multiple lines, with each trend line representing the value of a different event property. This allows you to visualize the payment method your users prefer.

To split a trend by event property:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. For example, `Charged`.
2. Click **+ Split by** to divide the trend by the event properties, such as `payment method`.
3. Click **View Analysis**.


<Image src="https://files.readme.io/d5b72c9af7314d6543c2acc901717ba58a02e2d1c194ce415390b80799b7ee36-image.png" alt="Compare trends by event properties" align="center" caption="Compare trends by event properties" border={true} />


The trend for each event property is displayed.

All the split event properties are listed at the bottom of the right pane. You can perform the following actions:

* Use the search box to find specific event properties.
* Select or deselect event properties from the trend by selecting the corresponding boxes.
* Sort the event properties from highest to lowest values, or vice versa, by clicking the arrows.

<Callout icon="📘" theme="info">
  ### Maximum Split

  You can split an event by up to two event properties at a time.
</Callout>

# Compare Trends for Segments

You can compare your event trend across different user segments. For example, you can compare the _App Uninstalled_ event trend across segments, such as _Loyal Customers,_ _Champion Users_, and _Match Day Players_. Differences in the segment trends reveal variations in user behavior, providing invaluable insights. For instance, if many Booster Abandoners are uninstalling the app, it may indicate a need for alternative engagement strategies rather than offering them game boosters.

To compare trends across segments:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. You can also filter your analysis further by the event property.
2. Click **Add Segment** from the _SEGMENT_ section.
3. Select a segment from the list or create an Ad hoc segment.
4. Click **View Analysis**.


<Image src="https://files.readme.io/372d2522452f6264308263ee5c232a65feca2aef22f238c82cb8e5c4433993ba-image.png" alt="Compare Trends Across Segments" align="center" caption="Compare Trends Across Segments" border={true} />


<Callout icon="📘" theme="info">
  ### Comparison Considerations

  You must consider the following when comparing trends across different segments:

  * You can compare a saved or an ad-hoc segment.
  * You can compare a maximum of five segments.
  * You cannot split the trend by user property and compare it by segments simultaneously.
</Callout>

## Ad hoc Segments

When performing a trend analysis, you can use available user segments or create ad-hoc segments at run time. To create ad hoc segments:

1. From the _SEGMENT_ section, click the edit icon.


<Image src="https://files.readme.io/3eb2702d462e999b6155fa3b76bce5ff4dd9efb5e9265c676f5ef8bb7d452046-image.png" alt="Create Adhoc Segment" align="center" width="40% " caption="Create Adhoc Segment" border={true} />


2. Click **Add Rule** to add a condition or click [Add Rule Group](doc:segmentation-rules) to add multiple conditions.


<Image src="https://files.readme.io/0f6c55c2577f3d86d157776fcb521eff4938a783049e90261cd57c621105ee11-image.png" alt="Add Rules" align="center" width="70% " caption="Add Rules" border={true} />


For information about creating segments, refer to [Segmentation](https://docs.clevertap.com/docs/segmentation).

## Split by User Property

You can analyze a trend based on the specific user properties. For example, consider the event `Charged`, which indicates that the user has started watching content. Here, you can split this trend based on the underlying user property, such as `Customer_Type`.

This splits your single `Charged` trend line into multiple trend lines, each referencing the user property value. For example, the user property `Customer_Type` is split by user property values such as _Platinum_, _Silver_, and so on.

To split a trend by user property:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend.
2. Select the user property from the _Split by user_ property list under the _SEGMENT_ section
3. Click **View Analysis**.


<Image src="https://files.readme.io/1729dee2d0d09682ba1fcef09cfdad337364111ec2c738a9271690c1cb046d75-image.png" alt="Split Segment by User Property" align="center" caption="Split Segment by User Property" border={true} />


The trend for each user property displays.  All the split user properties are listed at the bottom. You can do the following:

* Search through the listed user properties using the search box.
* Select or clear the user properties from the trend by selecting the specific checkbox.
* Sort the user properties from highest to lowest value and vice versa using the arrows.

<Callout icon="📘" theme="info">
  ### Maximum Split

  You can split by a maximum of two user properties. Split by properties is not available when comparing two or more segments.
</Callout>

### Split by Age

Age is available as a user property in the _Split by user_ property list. Age is a derived property. CleverTap calculates it from the user's Date of Birth at the time you run the analysis. Users are then grouped into the following fixed age groups:

- Unknown

- \<18

- 18-24

- 25-40

- 41-60

- 60+

These age groups are fixed. After you split a trend by Age, you can create a segment from any data point in the trend. For more information, refer to [Save as Segment](doc:trends-v2#save-as-segment).

# Operations

Once you generate a trend analysis, you can perform several actions from the Analysis pane to compare results, change visualizations, save the analysis, and take follow-up actions based on the chart data.

The available operations help you move from analysis to action without rebuilding the query.

## Compare with the Previous Period

You can compare the selected trend with a previous period to determine whether the metric is increasing, decreasing, or remaining stable.

From the **Compare** dropdown, you can compare the current analysis with:

* Previous Day
* Previous Week
* Previous Month
* Previous Year


<Image src="https://files.readme.io/f6594b38d2ec432dcda05ce29d00943f1a0c19eba037b41e47ddfaf8e7aa3b9b-image.png" alt="Compare Trends with the Previous Period" align="center" caption="Compare Trends with the Previous Period" border={true} />


## Change Chart Type

You can switch the analysis view to a different chart type to interpret the data differently.

The available chart types are:

* [Line](doc:trends-v2#line)
* [Bar](doc:trends-v2#bar)
* [Pie](doc:trends-v2#pie)
* [Number](doc:trends-v2#number)


<Image src="https://files.readme.io/176733ea271f70bf590c0233bfb9a73d74bbf0503d3bc62acc05feb20ca8f95f-image.png" align="center" caption="View Trend Types" border={true} />


### Line

Use the line chart to analyze how the selected metric changes over time. This is the default view for most trend analyses.


<Image src="https://files.readme.io/0cb962f9b78703ad8162a873ba119def4544d5024930ad043e29a29dc71f82f0-image.png" align="center" caption="View Trend in Line Chart" border={true} />


### Bar

Use the bar chart to clearly compare metric values across selected events or time buckets.


<Image src="https://files.readme.io/d0fce7cdd59a06cf9707586781d1ce3c63a87971596dec0d9d46f635434456db-image.png" align="center" caption="View Trend in Bar Chart" border={true} />


### Pie

Use the pie chart to understand the contribution to the total value across selected events or categories.


<Image src="https://files.readme.io/fa7d097d372f350aaab73ee299f1f59a57091c04f01ef1d6bba944477d3556b5-image.png" align="center" caption="View Trend in Pie Chart" border={true} />


### Number

Use the number view when you want to display the selected metric as a single summarized value rather than as a time-series chart.


<Image src="https://files.readme.io/09a86c3584af383e55aaee28467fe7317a6254e4b2640878a8f4ade5c3569cdf-image.png" align="center" caption="View Trend in Number Chart" border={true} />


## Inspect Data Points

Hover over any point or bar in the chart to view detailed values for that time bucket. This helps you inspect outliers, spikes, and dips without switching to the table view.

The tooltip can show information such as:

* Event name
* Date or time bucket
* Metric value
* Split-by value, if applicable


<Image src="https://files.readme.io/dbb69c34c27970e90cc91f5ba998174b805ab1e28ea4bfee751514c6b1b8af9a-image.png" alt="Inspect Data Points from a Trend" align="center" caption="Inspect Data Points from a Trend" border={true} />


## Save as Segment

You can create a user segment directly from a data point in the Trend chart to analyze or target users who performed a specific action during a selected time interval. Once you save a segment from Trend Analysis, it becomes available across the CleverTap dashboard and can be used in campaign targeting, analytics, segmentation, and other product features.

To save as a segment:

1. Click a data point on the Trends chart.
2. Click **Save as Segment**. The dashboard opens the Segment Builder, where the system automatically generates a segment query based on the event, filters, segment conditions, and the selected data point.


<Image src="https://files.readme.io/ec1d2f535006f7284fc68933bf2be3c970900b3c5669099aaf066f22faf6f687-2026-09-10_15-12-18_1.gif" alt="Save as Segment" align="center" caption="Save as Segment" border={true} />


You can then:

* Review the automatically generated segment query
* Modify the conditions or add additional filters
* Save the segment for future analysis or campaign targeting

This feature is useful when you want to:

* Identify users responsible for spikes or drops in a trend
* Retarget users who performed a specific event within a time window
* Build campaigns based on behavioral insights discovered in the trend analysis

## Create Campaign

Engage users directly from your Trends analysis behind a data point, without rebuilding a separate segment.

To create a campaign from a data point:

1. Click a data point on the Trends chart.
2. Click **Create Campaign**.
3. Review the _Reachable users_ section. It displays the total number of targetable users and their channel-wise reachability across Mobile Push, Email, SMS, WhatsApp, and Web Push.
4. Select the channel for your engagement, for example, Email.
5. Click **Continue**. The campaign creation page opens with the selected users as your target audience.


<Image src="https://files.readme.io/905ee448da025ed25bdc25176fb19c883e4faf1ab66175210e514941c831c550-2026-09-10_15-06-45_1.gif" alt="Create Campaign" align="center" caption="Create Campaign" border={true} />


For more information, refer to [Create Message](doc:create-message-email).

## View Sample Users

View a sample of the users behind any data point in your Trends analysis. This helps you validate your analysis by inspecting the real user profiles that contributed to the numbers.

To view sample users:

1. Click a data point on the Trends chart.
2. Click **View Sample Users**. The _Sample users_ window displays a sample of the user profiles that performed the event on the selected date.


<Image src="https://files.readme.io/42483c974b6e7833881eb87a2403d6058f2a7b3d6a696d739cf36c316cb97e73-2026-09-10_15-07-40_1.gif" alt="View Sample Users" align="center" caption="View Sample Users" border={true} />


You can click a user to open their user profile page and inspect their events and properties. Use it to spot-check your analysis rather than as a complete user list.

<Callout icon="📘" theme="info">
  ### Sample Users Are Indicative

  The _Sample Users_ window displays up to 20 sample users.
</Callout>

## Add to Board

You can add a Trends analysis to a Board to monitor it alongside other saved analyses.

To add a trend to a board:

1. Click **Add to Board** from the top-right corner of the dashboard after generating the trend analysis.
2. Enter the Trend Analysis name in _Chart name_ and select an existing board or create a new one.
3. Click **Add to board**.


<Image src="https://files.readme.io/e8c2b75e4edea678d552504241a8bc32a1904441e7183f11c011af9e93ebfc40-2026-03-09_11-00-18_1.gif" align="center" caption="Add a Trend Analysis to the Board" border={true} />


Use boards when you want to:

* Track the same trend regularly
* Combine Trends with Funnels, Flows, Cohorts, or Pivots
* Share a monitoring dashboard with your team

## Bookmark a Trend Analysis

You can bookmark any Trend analysis to quickly revisit it later. Bookmarks are user-specific, meaning only the logged-in user can view their saved bookmarks on the CleverTap dashboard. You can save up to 50 bookmarks.

Bookmarks are especially useful for tracking frequently accessed trends. For example, if you regularly monitor a trend such as `Charged` split by `Payment Method`, bookmarking it lets you instantly return to the same setup without recreating the analysis each time.

To bookmark a Trend:

1. Click **Bookmark** in the top-right corner of the dashboard after generating the trend analysis.
2. Enter a descriptive name to help you identify the analysis later.
3. Click **Bookmark**.


<Image src="https://files.readme.io/995c8821d9737cb62e89dd0f456fd44fbbc254178a0b7b84bb36296b1e3ca1ef-2026-03-09_11-06-23_1.gif" align="center" caption="Bookmark a Trend Analysis" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  You can save up to 50 bookmarks and access all your saved bookmarks from the bookmark list under the _Trends_ section.
</Callout>

## Export Trend Analysis

You can export the generated trend analysis for reporting or offline analysis.


<Image src="https://files.readme.io/876685f7bb8d6ea2a8796f2009e3d7aa66b34b4c14e5ef7b85ce8f78de852fb4-image.png" align="center" caption="Export a Trend Analysis" border={true} />


Depending on the selected view, Trends supports export options such as:

* PNG image
* PDF document
* CSV file

Use exports when you want to:

* Share the chart in presentations or documents
* Download the raw tabular values for further analysis
* Archive analysis snapshots for reporting
