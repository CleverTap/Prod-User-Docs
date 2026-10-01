---
title: Cohorts 2.0
excerpt: >-
  Understand how user behavior evolves over time by grouping users into cohorts
  and analyzing retention, frequency, and re-engagement patterns.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Cohorts help you understand how groups of users behave over time after performing a specific action. By organizing users into time-based cohorts and tracking their return behavior, Cohorts enables you to analyze retention, frequency, and re-engagement patterns across days, weeks, or months.

A cohort analysis helps answer questions such as:

* How many users return after their first app launch?
* How frequently do users re-engage after completing a purchase?
* Which acquisition cohorts retain better over time?
* How does retention differ across user segments or regions?

By visualizing user behavior across cohorts, you can identify drop-off points, measure long-term engagement, and optimize retention strategies.&#x20;

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information or questions, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

# Create a Cohort Analysis

To build a cohort analysis, you configure a query in the Query Builder. The Query Builder includes a set of steps that define how cohorts are created, how return behavior is measured, and how results are displayed.

To get started, go to _Analytics_ > _Cohorts_ and configure the following fields:

* [Select Start and Return Events](doc:cohorts-v2#select-events)
* [Select Segment](doc:cohorts-v2#select-segment)
* [Select Analysis Type](doc:cohorts-v2#select-analysis-type)
* [Select Return Metric](doc:cohorts-v2#select-return-metric)

## Select Events

Start a cohort analysis query by selecting the required events. Events define how cohorts are created and how return behavior is measured. These events define the lifecycle stage you want to analyze, from the first action to subsequent engagement.

In a cohort analysis, you select the following two types of events:

* [Start Event](doc:cohorts-v2#start-event)
* [Return Event](doc:cohorts-v2#return-event)

### Start Event

A _Start Event_ determines when users enter a cohort. Users are grouped into cohorts based on the date on which they perform this event.

For example, common start events include `App Installed`, `App Launched`, `Signed Up`, `First Purchase`, and `Video Watched`. For example, the start event is `App Installed`, so each cohort contains all users who installed the app on the same day.


<Image src="https://files.readme.io/4894fe9227020f711c0515f8250766d3fc4ede68f09fbd265da88028e51afa49-image.png" alt="Start Event" align="center" caption="Start Event" border={true} />


The selected start event determines:

* How cohorts are formed
* The cohort date (Day 0)
* Which users are included in the analysis

### Return Event

A _Return Event_ determines which action qualifies as a user returning. The return event can be the same as the start event or a different event, depending on the behavior you want to measure.

For example, the return event is `Charged`, so the analysis measures how many newly installed users go on to make a purchase.


<Image src="https://files.readme.io/cec0d144d0811daf485d5b182406c5627f216be17d9df287125dbf66c0884dd7-image.png" align="center" caption="Return Event" border={true} />


The selected return event determines:

* What action qualifies as a return
* How user re-engagement is measured
* Which interactions are counted in the retention or frequency calculation

#### Example Start and Return Events

For example, the following can be the start and return events in a Cohorts query:

| Start Event   | Return Event  | Analysis                                                                                                    |
| ------------- | ------------- | ----------------------------------------------------------------------------------------------------------- |
| App Launched  | App Launched  | Measures app retention, that is, how consistently users come back and open the app again.                   |
| Signed Up     | App Launched  | Measures onboarding stickiness, that is, whether newly registered users return to the app after signing up. |
| App Installed | Charged       | Measures install-to-purchase conversion, that is, how quickly new installs become paying customers.         |
| Video Started | Video Watched | Measures content completion, that is, whether users who start watching content return to finish it.         |

## Select Segment

Segmenting your cohort analysis helps you compare retention patterns across different user groups. By default, Cohorts analyzes behavior for _All Users_, but you can restrict the analysis to a specific user segment or create a new segment from the Query Builder.

For example, you can do the following:

* Compare retention for Paid vs. Free users to see which group converts to purchase faster
* Compare retention between New Users and Returning Users
* Compare engagement across geographies or acquisition channels


<Image src="https://files.readme.io/46ee7b99737c075f353eee969b62b40a137a28ae2e4ff5c56d3ce88708644ed4-image.png" align="center" caption="Segments" border={true} />


### Add Segments

Use **Add Segment** to add custom user segments in the same cohort analysis. This allows you to compare retention behavior across multiple segments within a single view.


<Image src="https://files.readme.io/50fab14320072c852c985121960ca7eb4b786b43e3112bd9aa2ea15bf0f90388-image.png" align="center" width="55% " caption="Add Segments" border={true} />


For example, you can:

* Compare retention between New Users and Returning Users
* Analyze retention for Paid vs Free users
* Compare engagement across different acquisition channels

Each added segment appears as a separate row or series in the cohort analysis, making it easy to identify differences in retention patterns.

### Split By Properties

Use **Split By** to further break down cohort results by a selected user or event property. This option is available only when the analysis contains a single segment. For example, you can split the All Users cohort by Country to compare retention across regions.

Splitting helps you understand how retention varies within a segment based on attributes such as:

* Geography (for example, country or city)
* Device or OS
* Campaign or source


<Image src="https://files.readme.io/8c4fcb235539726ee842b47fa8a8c0ac475495e6c2a81065f45f480d24aace34-image.png" align="center" width="55% " caption="Split By Properties" border={true} />


## Select Analysis Type

The _Analysis Type_ defines how user return behavior is measured over time after the start event. It determines whether Cohorts tracks exact-day returns, cumulative returns, or return frequency, allowing you to analyze different engagement and retention patterns.

The following table explains the three types of analysis and the business question each answers:

| Analysis Type                                             | What It Counts                                                           | Business Question It Answers                                                                                                 |
| :-------------------------------------------------------- | :----------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------- |
| Returned on a specific day (N-day Retention)              | Users who return on an exact day after the start event                   | On which exact day do users return? For example, how many users returned exactly on Day 7 after onboarding?                  |
| Number of days user returned (Power User)                 | The number of distinct days each user returned within the selected range | How frequently do users re-engage? For example, how many days did users remain active in their first 30 days?                |
| Returned on or after a specific day (Unbounded Retention) | Users who return at any point on or after a given day                    | How many users are still active after a certain point? For example, how many users returned at least once on or after Day 7? |


<Image src="https://files.readme.io/9d74a2790d59d933d37ddcf2b0b58f5c706b20142b81c5c878b1849eb758162a-image.png" align="center" caption="Analysis Types" border={true} />


### Entry in Subsequent Cohorts

This option modifies the selected analysis type to track whether users from one cohort reappear in later cohorts based on the start event. This option is especially useful for analyzing reactivation and lifecycle movement, such as users returning after periods of inactivity or responding to re-engagement campaigns.

For example, consider a food delivery app where the start event is `Order Placed`. A user who ordered in the first week of January belongs to that week's cohort. If the same user goes inactive and then orders again in March after a win-back campaign, this option determines whether that March order is tracked as a fresh cohort entry.

The difference is as follows:

* **When _Entry in Subsequent Cohorts_ is unselected**: A user is counted only in the cohort they first entered. The March order is treated as return behavior for the January cohort.
* **When _Entry in Subsequent Cohorts_ is selected**: The user also re-enters the March cohort as a new start. This lets you see reactivation and lifecycle movement, such as users coming back after periods of inactivity.


<Image src="https://files.readme.io/79da5a183d64056ea6ced08172f469fcfd70ad116da572d730928e010292f0a1-image.png" align="center" caption="Entry in Subsequent Cohorts Checkbox" border={true} />


This option works in combination with the selected analysis type and changes how return behavior is interpreted as follows:

* **With Returned on a Specific Day**: It tracks users who re-enter in later cohorts on an exact day after their original start event.
* **With Returned on or After a Specific Day**: It tracks users who reappear in later cohorts on or after the specified day.
* **With Number of Days User Returned**: It tracks how frequently users re-enter across multiple cohorts over time.

## Select Return Metric

The _Return Metric_ defines how return behavior is measured and displayed in the cohort analysis. Choose a metric based on whether you want to analyze retention, frequency, or value-based re-engagement.


<Image src="https://files.readme.io/88add7743a806628837bc054515990ba97889d8d0d3850727a5652ffc27ac707-image.png" align="center" caption="Return Metrics" border={true} />


Available return metrics include:

* **Retention Rate**: Measures the ratio of returning users to the total number of users in the cohort, highlighting retention strength over time. For example, which signup cohort shows the highest Day-14 retention rate?
* **Total Events**: Measures the total number of return events performed by users in a cohort. For example, how many times did users from a cohort launch the app in the first 7 days?
* **Events per User**: Measures the average number of return events performed per returning user. For example, on average, how many sessions does a returning user generate per week?
* **Sum of Event Property**: Measures the aggregated value of a numeric event property for returning users. For example, what is the total revenue generated by users within 14 days of their first purchase?

# Example Use Case: First Purchase After App Install

An e-commerce app team wants to understand how quickly newly installed users convert into paying customers. Specifically, they want to measure when users make their first purchase after installing the app, and how conversion rates change over time.

This analysis helps the team identify whether users convert early, require longer consideration, or drop off before purchasing.

To answer this question, the team builds the following cohort query:

| Field         | Value                                  | Description                                                                                                                                                     |
| :------------ | :------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event   | App Installed                          | Defines cohorts based on the day users install the app. Each cohort represents users who installed the app on the same day.                                     |
| Return Event  | Charged with filter `Frist Time = Yes` | Tracks when users make their first-ever purchase after installing the app. Applying the `First Time = Yes` filter ensures only the initial purchase is counted. |
| Segment       | All Users                              | Analyzes conversion behavior across the entire user base.                                                                                                       |
| Analysis Type | Returned on a specific day             | Measures the exact day (Day 0, Day 1, Day 2, and so on) on which users complete their first purchase after installation.                                        |
| Return Metric | Retention rate                         | Shows the percentage of users in each install cohort who make their first purchase on a given day after install.                                                |


<Image src="https://files.readme.io/fb8715143990a1c909ac3ab7a0fc299ccacc16fd7182ef225cb9f5a0536cf1b2-image.png" align="center" width="50% " caption="Example Query Builder" border={true} />


This cohort analysis helps the team understand:

* How quickly users convert from install to first purchase
* Whether purchases tend to happen on Day 0 or after multiple days
* The optimal time window to trigger discounts, reminders, or onboarding nudges
* How conversion speed varies when combined with segments or split-by dimensions such as campaign source, platform, or geography

# Reading the Cohort Analysis

Once you run a cohort query, CleverTap generates a cohort table and supporting visualizations that help you interpret user behavior over time.

The cohort analysis consists of the following visualizations:

* [Cohort Table](#cohort-table)
* [Trend Line](#visualizations)

## Cohort Table

The table view provides a precise, detailed breakdown of cohort performance over time. Use this view when you need exact values or want to export results.

The cohort table displays users grouped by cohort date (rows) and return periods (columns).

* Each row represents a cohort (for example, users who started on Jan 3)
* Each column represents time since the start event (Week 1, Week 2, Week 3)
* Each cell shows the selected return metric

For example, the following cohort table shows weekly repeat purchases for an e-commerce app over five weeks. Retention is strongest in Week 1 and gradually declines in later weeks. Darker cell shades indicate higher values, so you can spot strong and weak periods at a glance without reading every number.


<Image src="https://files.readme.io/502cd4d46717b183fefb09a5288d38f6e71497f4af003c4289e72951e7e830a6-image.png" align="center" caption="Cohort Table" border={true} />


This structure allows you to:

* Compare retention across cohorts. For example, check whether users acquired during a festive sale retain better than users acquired in a regular week.
* Identify decay patterns. For example, spot that most users stop returning after Week 2, which tells you when to schedule a re-engagement campaign.
* Spot high-performing or underperforming cohorts. For example, identify that a cohort acquired through a referral program retains twice as long as cohorts from paid ads.

## Trend Line

The Trend Line visualizes how retention or frequency changes over time. For example, the following trend line shows repeat purchases of a product across several weeks. Purchases hold steady through the monsoon weeks and decline as the rainy season ends, making the seasonal drop easy to spot at a glance.

Use this view to:

* Identify trends and seasonality
* Compare retention curves across cohorts
* Spot anomalies or sudden changes in engagement


<Image src="https://files.readme.io/136866b9f467b7da000b9373e09f845f242ada5ddaae6020391cb770ac1e92b6-image.png" align="center" caption="Trend Line" border={true} />


### Switch Trend Line Views

You can switch between the following trendline views to view the cohort for rows and columns:

* [Cohorts](doc:cohorts-v2#cohorts)
* [Frequency](doc:cohorts-v2#frequency)

#### Cohorts View

In the Cohorts trend line view, each line represents a single cohort from the table, plotted over time based on the selected return metric. For example, if you shipped a new onboarding flow in February, you can compare the January and February signup cohorts side by side to see whether the new flow improved retention.

The trend line is directly derived from the cohort table:

* The **x-axis** represents time since the start event (for example, Week 1, Week 2, Week 3).
* The **y-axis** represents the selected return metric (for example, retention rate).

Each data point on the line corresponds to a value from the same cohort’s row in the table below the trend line. This view helps you visually compare how retention or engagement evolves for different cohorts over time.

For example, you can quickly identify:

* Which cohorts retain users better over time
* How retention decays for newer vs older cohorts
* Sudden drops or improvements in retention patterns


<Image src="https://files.readme.io/637c97e203d08218a3b8da169cbf8d70a33373fe34df40dbcb10a557cd56ee7e-image.png" align="center" caption="View Cohort Analysis with Cohort View" border={true} />


#### Frequency View

In the Frequency trend line view, the chart visualizes how often users from a cohort return, rather than whether they return. For example, a media app can use this view to see how many episodes users from each signup cohort watch per week, revealing whether viewing habits deepen or fade after onboarding.

This view is also linked directly to the cohort table:

* The **x-axis** represents time since the start event.
* The **y-axis** represents the frequency metric (for example, events per user).

Each line maps to frequency values calculated from the corresponding cohort row in the table below the trend line. This view is useful for understanding the depth of engagement, such as how actively users continue to interact over time.

For example, you can identify:

* Cohorts that return frequently vs infrequently
* Changes in engagement intensity over time
* Whether engagement drops gradually or sharply after onboarding


<Image src="https://files.readme.io/61223963884e89cca8c8089a81f5e2589bb5f230d9b24fb6d312f9529e03f149-image.png" align="center" caption="View Cohort Analysis with Frequency View" border={true} />


### Multi-Select and View Cohorts

Multi-select lets you isolate and compare specific cohorts by visualizing only the selected rows from the cohort table in the trend view. For example, you can select only the cohorts acquired during a campaign week and compare them against a regular week to measure the campaign's impact on retention, without the other cohorts cluttering the chart.

#### Cohorts View

You can select multiple cohorts directly from the cohort table to compare them in the trend line view.

When multiple cohorts are selected:

* Each selected row in the table appears as a separate line in the Cohorts trend chart.
* The chart updates in real time to reflect only the selected cohorts.
* This allows you to isolate and compare specific cohorts without visual noise.


<Image src="https://files.readme.io/024fc02e0ebe744db72722b7e18d710d9e40fb6def21a4d798bbf8ddbe2fe7a8-image.png" align="center" caption="View Multi-Select Cohort Analysis with Cohort View" border={true} />


This interaction helps you focus on:

* Comparing specific time periods (for example, post-campaign cohorts)
* Identifying performance differences between selected cohorts
* Removing outliers from the trend view

#### Frequency View

When multiple cohorts are selected in the table, the **Frequency** trend view plots a separate line for each selected cohort, showing how engagement frequency changes over time.

This view highlights differences in repeat behavior across cohorts:

* Some cohorts may return often but drop off quickly
* Others may show lower frequency but sustained engagement


<Image src="https://files.readme.io/b228ce3118a6a784c9e9c349a300a4f76f9d43a2eb7b3b8b9e81e6dc24513c97-image.png" align="center" caption="View Multi-select Cohort Analysis with Frequency View" border={true} />


Using multi-select with the Frequency view helps you compare:

* Engagement intensity across cohorts
* Long-term usage patterns
* Behavioral differences that are not visible in retention alone

# Operations

Once you generate a Cohort analysis, you can perform several actions from the analysis to compare results, change visualizations, save the analysis, and take follow-up actions based on the analysis data. The available operations help you move from analysis to action without rebuilding the query.

## Save as Segment

You can create a user segment directly from a cell in the Cohort table to analyze or target users who performed a specific action during a selected time interval. Once you save a segment from Cohort Analysis, it becomes available across the CleverTap dashboard and can be used in campaign targeting, analytics, segmentation, and other product features.

To save as a segment:

1. Click a cell in the Cohort table.
2. Click **Save as Segment**. The dashboard opens the Segment Builder, where the system automatically generates a segment query based on the event, filters, segment conditions, and the selected data point.


<Image src="https://files.readme.io/bd601a1adbbc09f4ddbddb25859beefd48e2ec3ab66e9356d0d6416225d4d2e2-2026-09-10_19-05-36_1.gif" alt="Save a Segment from a Retention Table" align="center" caption="Save a Segment from a Retention Table" border={true} />


## Create Campaign

Engage users in any retention cell directly from your Cohorts analysis, without rebuilding a separate segment. For example, you can create a re-engagement campaign for a cohort whose Week 2 retention dropped.

To create a campaign from a Cohort table:

1. Click a cell in the retention table.
2. Click **Create Campaign**.
3. Review the _Reachable users_ section. It displays the total number of targetable users and their channel-wise reachability across Mobile Push, Email, SMS, WhatsApp, and Web Push.
4. Select the channel for your engagement, for example, WhatsApp.
5. Click **Continue**. The campaign creation page opens with the selected users as your target audience.


<Image src="https://files.readme.io/a9052b9d878976c8669d0303ce475f339b621ad2736b3bf235ae2d874e1c144e-2026-09-10_19-07-23_1.gif" alt="Create Campaign from a Retention Table" align="center" caption="Create Campaign from a Retention Table" border={true} />


For more information, refer to [Create Message](doc:create-message-push).

## View Sample Users

View a sample of the users behind any cell in your retention table. This helps you understand which users returned in a given period before you act on the data.

To view sample users:

1. Click a cell in the retention table.
2. Click **View Sample Users**. The _Sample users_ window displays some of the user profiles that performed the return event.


<Image src="https://files.readme.io/0cbfb29379174f113c5398e3495a66c48329612f76da13a91dbaae7ea7509429-2026-09-10_19-09-19_1.gif" alt="View Sample Users from a Retention Table" align="center" caption="View Sample Users from a Retention Table" border={true} />


You can click a user to open their user profile page and inspect their events and properties. Use it to spot-check your analysis rather than as a complete user list.

<Callout icon="📘" theme="info">
  ### Sample Users Are Indicative

  The _Sample Users_ window displays up to 20 sample users.
</Callout>

## Bookmark a Cohort Analysis

You can bookmark any Cohort analysis to quickly revisit it later. Bookmarks are useful for tracking frequently monitored retention reports, such as weekly retention or long-term engagement trends. Bookmarks are user-specific and visible only to the logged-in user.

To bookmark a Cohort analysis:

1. Click **Bookmark** in the top-right corner after running the analysis.
2. Enter a descriptive bookmark name.
3. Click **Bookmark**.


<Image src="https://files.readme.io/1f79ebfb248ad1361fcf4002f2e59613d7b9badb8d9cae161cc65ea88472929b-2026-02-03_16-35-34_1.gif" align="center" caption="Book a Cohort Analysis" border={true} />


<Callout icon="📘" theme="info">
  #### Bookmark Limits

  You can add up to 50 bookmarks. All saved cohort analyses are accessible from the _Cohorts_ section.
</Callout>
