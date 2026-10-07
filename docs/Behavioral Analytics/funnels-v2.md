---
title: Funnels 2.0
excerpt: >-
  Learn how to use the new and improved visualization using Funnels to gain
  deeper insights into your data and make more informed decisions.
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

Funnels are a series of actions that a user performs in a particular order. They show users' progress through defined paths in your app and identify where they drop off between steps.

A typical example is a user onboarding sequence, where a user progresses from the app's initial launch through activities such as registration, profile completion, and orientation. Another example is a purchase sequence, where a user progresses through a shopping cart experience to complete a purchase.

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information about this feature or any queries, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

# Creating a Funnel

To analyze how users progress through a defined sequence of events, you can create a funnel using the Funnels feature in CleverTap.

To create a funnel, go to _Analytics > Funnels Beta_ and perform the following steps:

- [Select Events](doc:funnels-v2#select-events)
- [Select Segments](doc:funnels-v2#select-segments)
- [Split by Property](doc:funnels-v2#split-by-property)
- [Select Measured by Options](doc:funnels-v2#select-measured-by-options)
- [Hold Constant Property](doc:funnels-v2#hold-constant-property)

## Select Events

Select the events in the desired order to create a funnel with up to eight steps. You can also select event properties for each event to limit the analysis to users who performed the selected event with those properties.


<Image src="https://files.readme.io/9d00eea6cc79730a1874cfa2682a6453e669da260bdb65d8d7aa3f239caffbff-image.png" alt="Select Events for Funnel Analysis" align="center" width="50% " caption="Select Events for Funnel Analysis" border={true} />


You can add multiple events (up to four) within a single funnel step using an `OR` condition. This is useful when the same user action can be represented by different events but should be treated as a single step in the funnel.

For example, if users can log in through either a mobile app or a website, you can group the _Mobile Login_ and _Web Login_ events into a single funnel step using `OR` condition. This ensures that users are counted as having completed the step regardless of the platform they used, providing a more accurate view of user progression.


<Image src="https://files.readme.io/48fcf55da2304775b027cb438bc95d371bbbf0f4c99468ab84a1476c8663d265-image.png" alt="Add Multiple Events with an OR Condition" align="center" width="50% " caption="Add Multiple Events with an OR Condition" border={true} />


## Select Segments

You can compare funnel conversions across different user segments to analyze how behavior varies between user groups. For example, compare the funnel for _App Launched > Product Viewed > Charged_ across the _All Users_ and the _Engaged Users_ segments. Differences in conversion trends could reveal variations in your users' behavior across segments and yield invaluable insights.

Click **Add Segment** to include additional user segments in the same funnel analysis. This allows you to compare funnel analysis across multiple segments within a single view. You can also create a new segment directly from the Query Builder.


<Image src="https://files.readme.io/48192ccd937c21aad18b405be33cfef481be877b8f8ded272bdbd5fa2c0298e8-image.png" alt="Select Segment for Funnel Analysis" align="center" width="50% " caption="Select Segment for Funnel Analysis" border={true} />


You can compare funnel conversions across different user segments to analyze how behavior varies between user groups. For example, you can compare the funnel _App Launched > Product Viewed > Charged_ across the _All Users_ and _Engaged Users - at least 4 times in the past week_ segments to understand how engagement level impacts conversion.

In the following example, the _Engaged Users_ segment shows a higher conversion rate at each funnel step compared to _All Users_. This indicates that users who are already engaged with the app are more likely to progress through the funnel and complete a purchase. Insights such as these can help you prioritize high-value segments, refine your targeting strategies, and identify where less-engaged users tend to drop off.


<Image src="https://files.readme.io/43e742a8bb58141e7b4e4df19f4e34e2def6b01a73fdc78e43a3c2170c2c3f82-image.png" alt="Segment Comparison Results" align="center" caption="Segment Comparison Results" border={true} />


## Split by Property

You can split a funnel by event properties, user profile properties, or custom attributes, such as sessions, geographies, technographics, or any other custom attributes. This allows you to compare how different attributes influence user progression and conversion across the same funnel.

Splitting funnels helps you answer questions such as:

- Which products convert better?
- Which languages, regions, or devices show higher drop-offs?
- Where should optimization efforts be focused?

<Callout icon="📘" theme="info">
  #### Combining Split by Property with Compare

  You can not use Split by Property together with [Compare with the Previous Period](doc:funnels-v2#compare-with-the-previous-period). Split by Property can, however, be used together with [Hold Constant Property](doc:funnels-v2#hold-constant-property) as long as both reference the same event property.
</Callout>

### Split by Event Property

In the following example, the funnel is split by the _product_ event property. Each row represents a different product, allowing you to compare how users progress through the funnel for each product variant.

Here, the analysis shows that some products have higher overall conversion rates than others. This indicates which products are more effective at driving users to convert and which may require improvements in discovery, pricing, or user experience.


<Image src="https://files.readme.io/e14c46f7642db9bd7d37f3af5d4d2cbe8cfd24863870de4ac8b6ec50e1d5a89c-image.png" alt="Split Funnel by Event Property" align="center" caption="Split Funnel by Event Property" border={true} />


### Split by User Property

In the following example, the funnel is split by the _Language_ user property. Each row represents a language group, enabling you to compare conversion behavior across different user demographics.

Here, the analysis shows that users with different language preferences convert at different rates. These insights can help identify which language segments are performing well and which may benefit from localized content, messaging, or onboarding improvements.


<Image src="https://files.readme.io/f15ab33b060fb45d97ab16faf8cb588771d9fa415f16d816d26f26560f2b0c2c-image.png" alt="Split Funnel by User Property" align="center" caption="Split Funnel by User Property" border={true} />


## Select Measured By Options

The _MEASURED BY_ options control how funnel conversions are calculated, grouped, and evaluated. These settings directly impact how users are counted and how funnel results are displayed.

From the _MEASURED BY_ options, you can query:

- [Measurement Mode](doc:funnels-v2#measurement-mode)
- [Conversion Window](doc:funnels-v2#conversion-window)
- [Step Order](doc:funnels-v2#step-order)

## Measurement Mode

The measurement mode determines whether funnel performance is displayed as a single aggregated value or as a trend over time.

You can choose one of the following measurement modes:

- [Total Conversions](doc:funnels-v2#total-conversions)
- [Conversion Trend](doc:funnels-v2#conversion-trend)
- [Step Frequency](doc:funnels-v2#step-frequency)
- [Time to Convert](doc:funnels-v2#time-to-convert)
- [Conversion Growth](doc:funnels-v2#conversion-growth)

### Total Conversions

Selecting **Total Conversions** displays the aggregate conversion count or conversion rate for the selected time range. Results are shown as a single value and are not broken down by time.

For example, selecting total conversion for the funnel _App Installed > App Launched > Added to Cart_ over the last 30 days shows the overall percentage and number of users who completed the entire funnel during that period. This provides a quick snapshot of how effectively users convert from the first step to the final step, without focusing on daily or weekly fluctuations.


<Image src="https://files.readme.io/9694668b15c6372f69ad204bc99a2bf9fedca93e649621e6822f022db6282565-image.png" alt="View Funnel Analysis by Total Conversions" align="center" caption="View Funnel Analysis by Total Conversions" border={true} />


Use the Total Conversion option when you want to:

- Get a high-level summary of funnel performance
- Compare overall conversion rates across segments
- Report a single conversion metric for a given period

### Conversion Trend

Selecting **Conversion Trend** allows you to analyze how funnel conversions change over time. When **Conversion Trend** is selected, you must also choose a time granularity, that is, Day, Week, or Month, to view the trend.

For example, analyzing daily conversion trends for the funnel _App Installed > App Launched > Added to Cart_ over the last 30 days can help you identify when conversions increase or decline. These patterns may correlate with product releases, marketing campaigns, or external factors, enabling you to understand what influences user progression through the funnel and take timely action.


<Image src="https://files.readme.io/8d05baaf827776c5063164e8f5f546b8dac1658b59fdccdfa7116b54b41bc123-image.png" alt="View Funnel Analysis by Conversion Trend" align="center" caption="View Funnel Analysis by Conversion Trend" border={true} />


Use the Trends option when you want to:

- Track conversion performance over time
- Identify spikes, drops, or seasonality in funnel conversions
- Compare trends across segments or properties

### Step Frequency

Selecting **Step Frequency** displays how often users perform each step of the funnel. Instead of showing only whether users completed a step, this mode shows how many times the step was performed, helping you identify steps users repeat before progressing.

For example, if users perform the _Login Attempted_ step an average of 3 times before reaching _Logged In_, a higher step frequency at the _Login Attempted&#x20;_&#x73;tage can indicate friction, such as failed authentication or an unclear flow. In contrast, a step frequency close to one for the same stage suggests users move through that step smoothly.


<Image src="https://files.readme.io/302f64f398c5120267e9958c6a3c25768ef2ccc9266c32f02e9837b03b2bdaf0-image.png" alt="View Funnel Analysis by Step Frequency" align="center" caption="View Funnel Analysis by Step Frequency" border={true} />


Use the Step Frequency option when you want to:

- Identify steps that users repeat before moving forward
- Detect friction points such as failed or retried actions
- Compare repeat behavior across segments or split-by values

### Time to Convert

Selecting **Time to Convert** displays how long users take to complete the funnel. This mode shifts the analysis from how many users convert to how quickly they convert, helping you understand the pace of your user journeys.

For example, if most users complete the funnel _App Installed > App Launched > Added to Cart_ within one day, but a specific segment, such as _Paid Campaign Users_, takes over a week, you can time your campaigns to re-engage slower users before they drop off entirely.


<Image src="https://files.readme.io/123d2b21fc75bedc935b11c65487131ab44d25bcc0082234872b8e980598a6cb-image.png" alt="View Funnel Analysis by Time to Convert" border={true} />


Use the Time to Convert option when you want to:

- Understand how long a typical user journey takes
- Compare conversion speed across segments or properties
- Decide the timing of follow-up campaigns and reminders

### Conversion Growth

Selecting **Conversion Growth** displays how funnel conversions change relative to a previous period, allowing you to measure whether performance is improving or declining over time.

For example, in the funnel _App Launched > Added To Cart > Charged,_ the chart tracks the percentage of users who complete each step over time, counted from the first step. Both lines reach 100% within half a day, which shows that users who convert do so quickly. The table below provides details, such as the median time to reach _Added To Cart_ is 4 minutes, and _Charged_ is 6 minutes, while the slowest 5% of users take 16 and 24 minutes, respectively.


<Image src="https://files.readme.io/6c912ff5b48a43a639d878973ae69e5844effd15de58f5a3a74ad4ba686b1684-image.png" alt="View Funnel Analysis by Conversion Growth" align="center" caption="View Funnel Analysis by Conversion Growth" border={true} />


Use the Conversion Growth option when you want to:

- Measure the impact of product releases or campaigns on conversions
- Track whether funnel performance is improving or declining
- Report period-over-period conversion changes to stakeholders

## Conversion Window

Funnels are calculated using a conversion window, which defines the maximum time you allow users to complete all funnel steps. The conversion window is set to 5 days by default, but you can adjust it based on the type of analysis you want to perform.

A shorter conversion window applies stricter criteria and includes only users who complete the funnel within a shorter timeframe. A longer conversion window gives users more time to complete all steps, resulting in more users qualifying for the analysis, not necessarily more conversions.

Choose the conversion window based on the length of your typical user journey. For example, fast actions, such as onboarding, may require shorter windows, while high-consideration flows, such as purchases, may require longer ones.


<Image src="https://files.readme.io/97a73f12ec359477da234ef50ad379553f6bf28f38c59a1e6f165e2c9908aa9b-image.png" alt="Set Conversion Window" align="center" caption="Set Conversion Window" border={true} />


<Callout icon="📘" theme="info">
  #### Time Interval for Conversion Window

  CleverTap recommends setting the Conversion Window to a duration shorter than the selected date range of the analysis. This helps ensure consistent and reliable funnel results by avoiding partial or overlapping conversions.
</Callout>

## Step Order

The _Step Order_ setting determines whether users must follow the predefined funnel step sequence to be counted as converted. This order determines how users are counted as they progress through funnel steps, primarily when steps are repeated or performed out of sequence.


<Image src="https://files.readme.io/0a03b55656f6066ebb8ff9e59b3fe3344e6526a45ad37a317c64bff3fef5fcd2-image.png" alt="Funnel Step Orders" align="center" caption="Funnel Step Orders" border={true} />


You can select one of the following options:

- [Flexible Order](doc:funnels-v2#flexible-order)
- [Strict Order](doc:funnels-v2#strict-order)

### Flexible Order

By default, funnels count users who complete all defined steps in the specified sequence. Users may repeat earlier steps, but they must still complete every funnel step to be counted as converted. If a user skips a required step and completes it later, the funnel does not count that user as a conversion.

For example, a funnel's steps are defined in the following sequence:

**Step A > Step B > Step C > Step D**

The following table explains how different users are counted based on their progress through the funnel steps:

| User   | Step Sequence                              | Counted in Funnel? | Reason                                                                |
| ------ | ------------------------------------------ | ------------------ | --------------------------------------------------------------------- |
| User 1 | Step A > Step B > Step C > Step D          | Yes                | Completes all funnel steps in the correct order.                      |
| User 2 | Step A > Step C > Step D                   | No                 | Skips Step B, which is required in the funnel.                        |
| User 3 | Step A > Step C > Step B > Step D          | No                 | Performs funnel steps out of sequence.                                |
| User 4 | Step A > Step B > Step A > Step C > Step D | Yes                | Repeats Step A but still completes all steps in the correct sequence. |

#### Why Use Flexible Order?

Flexible ordering is useful when you want to measure overall funnel completion without ignoring users for repeated or exploratory behavior.

In many user journeys, users may repeat steps, navigate back and forth between screens, or perform actions multiple times before progressing. Flexible Order ensures that these natural behaviors do not prevent users from being counted as converted, provided they eventually complete all required steps in the correct sequence.

For example, consider the following conversion sequence of two users in an app:

**User A**: App Launched > Viewed Product > Viewed Product > Added to Cart > Viewed Product > Purchased

**User B**: App Launched > Viewed Product > Added to Cart > Purchased

With Flexible Order enabled, both users are counted as converted because they complete all funnel steps in the defined order, even though User A repeats some steps.

### Strict Order

When _Strict Order_ is selected, funnels count users only if they complete every step exactly in the defined sequence. Any repetition of a funnel step or deviation from the specified order disqualifies the user from being counted as converted.

For example, a funnel's steps are defined as follows:

**Step A > Step B > Step C > Step D**

The following table explains how different users are counted based on how they progress through the funnel steps:

| User   | Step Sequence                              | Counted in Funnel? | Reason                                                     |
| ------ | ------------------------------------------ | ------------------ | ---------------------------------------------------------- |
| User 1 | Step A > Step B > Step C > Step D          | Yes                | Completes all funnel steps exactly in the specified order. |
| User 2 | Step A > Step C > Step D                   | No                 | Skips Step B, breaking the required step sequence.         |
| User 3 | Step A > Step C > Step B > Step D          | No                 | Performs funnel steps out of order.                        |
| User 4 | Step A > Step B > Step A > Step C > Step D | No                 | Repeats Step A, which violates strict ordering rules.      |

#### Why Use Strict Order?

Strict ordering is useful for identifying friction or unexpected behavior within a process.

For example, consider the following Login sequence of two users in an app:

- **User A:** App Launched > Login Attempted > Login Attempted > Login Attempted > Logged In
- **User B:** App Launched > Login Attempted > Logged In

With strict order enabled, User A is not counted as a clean conversion, highlighting repeated login attempts and potential user friction. This makes strict order particularly valuable for diagnosing issues in critical sequences such as authentication, onboarding, or payments.

## Hold Constant Property

**Hold Constant Property** lets you measure funnel conversion based on user intent by requiring that a single event property keep the same value across every step of the funnel. This helps you distinguish intent-driven conversions from conversions that appear complete on the surface.

For example, in the funnel _App Launched > Product Viewed > Added to Cart > Charged_, holding the `product category` property constant means a user is counted as converted only if they viewed, added to cart, and purchased within the same product category. Without this setting, a user who viewed a shirt, added a pair of trousers to their cart, and purchased a jacket would still count as a full conversion, even though their actions do not reflect one consistent purchase intent.


<Image src="https://files.readme.io/80671c76edfa747e4eb38971b9daffbcd2f55a16187bb8c49ddb0722e41c4f91-image.png" alt="Hold Property Constant Checkbox" align="center" width="60%" caption="Hold Property Constant Checkbox" border={true} />


<Callout icon="📘" theme="info">
  #### Selected Property Values Consideration

  If the selected property has more than 20 distinct values, only the top 20 values are considered when evaluating the held property.
</Callout>

# Reading Funnel Analysis

CleverTap offers multiple views to help you interpret funnel performance effectively. Based on whether you want a visual overview or a detailed comparison, you can analyze funnel data using [Chart View](doc:funnels-v2#chart-view) or [Table View](doc:funnels-v2#chart-view). Each view highlights different aspects of user progression and conversion behavior.

## Chart View

Chart View provides a visual representation of how users progress through each step of the funnel, enabling easy identification of drop-offs and overall conversion trends at a glance.

The chart shows cumulative conversions per step for the selected time range. You can view the data either as an absolute count of users completing each step or as a percentage.

### Vertical Chart

The default chart orientation is vertical, displaying funnel steps from left to right. This layout supports funnels with up to 8 steps and split-by property values without visual crowding.


<Image src="https://files.readme.io/a1096807cc72530bedb2334f1df96992b4125cb62b01350a5d27b27216e53ecd-image.png" alt="Vertical Chart View of a Funnel Analysis" align="center" caption="Vertical Chart View of a Funnel Analysis" border={true} />


### Horizontal Chart

To switch to a horizontal layout, click the orientation toggle in the chart toolbar. The selected orientation persists throughout the analysis session.


<Image src="https://files.readme.io/252da6aa6578d70ec62cd5a41dcd409c65981ec494b90d2ad2adc756b74f06b5-image.png" alt="Horizontal Chart View of a Funnel Analysis" align="center" caption="Horizontal Chart View of a Funnel Analysis" border={true} />


## Table View

Table View presents the funnel results in a structured tabular format, allowing you to inspect detailed step-level metrics alongside the visual funnel chart.

Each row in the table represents a funnel breakdown, such as a selected segment or a property-based split used in the funnel analysis. The table helps you compare conversion performance across segments and understand where users drop off at each step.


<Image src="https://files.readme.io/b84f61b02b3e9403b40ed8004abd51c12ae79c033802da177925c46da9749052-image.png" alt="Table view of a Funnel Analysis" align="center" caption="Table View of a Funnel Analysis" border={true} />


The table includes the following columns:

- **Segment**: The segment or split value used in the funnel analysis. For example, _All Users_ or different property-based groups when the funnel is split by a property.
- **Total Conversion**: The overall conversion rate from the first step to the final step of the funnel.
- **Step Conversion Columns**: Each funnel step shows the number of users who reached that step, along with the corresponding percentage relative to the first step.
- **Median/Average Time Between Steps**: Displays the elapsed time between consecutive funnel steps. The metric shown depends on the selection in the time metric dropdown, either _Median Time_ (default) or _Average Time_. The selected metric updates elapsed time values in both the table and the chart labels simultaneously. Elapsed time values are displayed in the following format:
  - Values under 60 seconds display as seconds.
  - Values of 60 seconds or more display as minutes and seconds.

You can also use the _Search_ field in the table to quickly find specific segments or split values in large funnel analyses.

## Switch Display Controls

You can always switch between display controls to view how funnel results are displayed in the chart.

Depending on the analysis, you can view results as:

- [Percentage](doc:funnels-v2#percentage)
- [Count](doc:funnels-v2#count)
- [Time Metric](doc:funnels-v2#time-metric)
- [Compare with the Previous Period](doc:funnels-v2#compare-with-the-previous-period)

### Percentage

Use percentage (%) to understand relative conversion performance across steps.


<Image src="https://files.readme.io/f8696dc4698776cbbd7021de1dfdf02568b0e044780af8979028fb8547d87ba8-image.png" alt="View Funnel Analysis in Percentage" align="center" caption="View Funnel Analysis in Percentage" border={true} />


### Count

Use count (#) to inspect the actual number of users progressing through each step.


<Image src="https://files.readme.io/e643c632e1aff1926ce3221315170d02e320dcc1aba7619ea8743dbf6c11217f-image.png" alt="View Funnel Analysis in Count" align="center" caption="View Funnel Analysis in Count" border={true} />


### Time Metric

Use the time metric dropdown in the chart toolbar to switch between elapsed time display options. You can select one of the following options:

- **Median Time**: Displays the median elapsed time between steps. This is the default selection.
- **Average Time**: Displays the average elapsed time between steps.

The selected metric updates elapsed time values in the table, chart labels, and tooltips.


<Image src="https://files.readme.io/1c271a3fe7d363368c6073ad31250620973bca6f0eb2874f4ff34f5389d03f14-2026-05-18_14-35-28_1.gif" alt="View Median/Average Time Metric in a Funnel Analysis" align="center" caption="View Median/Average Time Metric in a Funnel Analysis" border={true} />


Use the time metric option when you want to:

- View the most representative elapsed time for typical users (Median Time).
- Understand the overall average time across all users, including outliers (Average Time).

## Compare with the Previous Period

You can compare the selected funnel with a previous period to determine whether the metric is increasing, decreasing, or remaining stable.

From the **Compare** dropdown, you can compare the current analysis with:

- Previous Day
- Previous Week
- Previous Month
- Previous Year


<Image src="https://files.readme.io/7c47199592901304d07778fe899b3282f9d9c83725bf97132efd6fe2eadbd252-image.png" alt="Compare with a Previous Period" align="center" caption="Compare with a Previous Period" border={true} />


# Operations

Once you generate a funnel analysis, you can perform several actions from the Analysis pane to compare results, switch views, save the analysis, and take follow-up actions based on the funnel data.

The available operations help you move from analysis to action without rebuilding the query.

## Inspect Funnel Data

Hover over any bar, step, or chart element in the funnel view to inspect detailed values for that stage of the funnel. This helps you inspect conversion values and drop-offs without switching to the table view.


<Image src="https://files.readme.io/20d4744d95cbfebe7e95be5f8260bb7cb6c0132b21e321cec04098542a1ba22f-image.png" alt="Inspect Data for a Funnel Step" align="center" caption="Inspect Data for a Funnel Step" border={true} />


The tooltip can show information such as:

- Step name
- User count
- Conversion percentage
- Segment or split-by value, if applicable

## Save as Segment

You can create a user segment directly from a funnel step to analyze or engage users who reached that stage. Once you save a segment from Funnel Analysis, it becomes available across the CleverTap dashboard and can be used in campaign targeting, analytics, segmentation, and other product features.

To save a segment after generating a funnel analysis:

1. Click a step bar on the funnel chart.
2. Click **Save as Segment.&#x20;**&#x54;he dashboard opens the Segment Builder, where the system automatically generates a segment query for users who qualified for the selected funnel step.


<Image src="https://files.readme.io/bcb9f445d1c8f6fcc5f73c45f165741033c8e8147a754e6ca2055aeca95f4812-2026-09-10_16-19-47_1.gif" alt="Save a Segment from a Funnel Step" align="center" caption="Save a Segment from a Funnel Step" border={true} />


You can then:

- Review or refine the generated segment conditions
- Add additional filters or rules
- Save the segment for future analysis or campaign targeting

This feature is useful when you want to:

- Retarget users who dropped off at a specific funnel step
- Build campaigns for users who completed or partially completed a funnel
- Perform a deeper analysis of users who reached a particular stage of a journey

## Create Campaign

Engage users at any funnel step directly from your Funnel analysis, without rebuilding a separate segment. For example, you can create a win-back campaign for users who dropped off between the _App Launched_ and _Product Viewed&#x20;_&#x73;teps.

To create a campaign from a funnel step after generating a funnel analysis:

1. Click a step bar on the funnel chart.
2. Click **Create Campaign**.
3. Review the _Reachable users_ section. It displays the total number of targetable users and their channel-wise reachability across Mobile Push, Email, SMS, WhatsApp, and Web Push.
4. Select the channel for your engagement, for example, Email.
5. Click **Continue**. The campaign creation page opens with the selected users as your target audience.


<Image src="https://files.readme.io/ca992e74ca558d61a39fd5d3927858c2c103edcbfc02ff75b114ae52868132e4-2026-09-10_16-21-44_1.gif" alt="Create a Campaign from a Funnel Step" align="center" caption="Create a Campaign from a Funnel Step" border={true} />


For more information, refer to [Create Message](doc:create-message-push).

## View Sample Users

View a sample of the users at any step of your funnel. This helps you understand who converted or dropped off at a step before you act on the data.

To view sample users after generating a funnel analysis:

1. Click a bar on the funnel chart.
2. Click **View Sample Users**. The _Sample users_ window displays a sample of the user profiles that performed the event on the selected date.


<Image src="https://files.readme.io/1550e95ddb3811c2aa37f2320b50a1170b4140810df168ff821e070048cc2498-2026-09-10_16-25-07_1.gif" alt="View Sample Users from a Funnel Step" align="center" caption="View Sample Users from a Funnel Step" border={true} />


You can click a user to open their user profile page and inspect their events and properties. Use it to spot-check your analysis rather than as a complete user list.

<Callout icon="📘" theme="info">
  ### Sample Users Are Indicative

  The _Sample Users_ window displays up to 20 sample users.
</Callout>

## Add to Board

You can add a Funnel analysis to a Board to monitor it alongside other saved analyses.

To add a funnel to a board after generating a funnel analysis:

1. Click **Add to Board** from the top-right corner of the dashboard after generating the funnel analysis.
2. Enter the name of the current analysis in _Chart name_. For example, _Charged Between April 18 to May 18_.
3. Select _Chart_ to add the funnel visualization as a chart tile, or select _Table_ to add the funnel analysis in a tabular format to the board.
4. Select an existing board or create a new one where you want the chart to be added.
5. Click **Add to board**.


<Image src="https://files.readme.io/b61eb4ed929cc71c05796470852422a7489b49a5d27b13e9db948a8abde23adc-2026-05-18_16-51-46_1.gif" alt="Add a Funnel Analysis to a Board" align="center" caption="Add a Funnel Analysis to a Board" border={true} />


Use boards when you want to:

- Track the same funnel regularly
- Combine Funnels with Trends, Flows, Cohorts, or Pivots
- Share a monitoring dashboard with your team

## Bookmark a Funnel Analysis

You can bookmark any Funnel analysis to quickly revisit it later. Bookmarks are user-specific, meaning only the logged-in user can view their saved funnel analyses on the CleverTap dashboard.

Bookmarks are especially useful for tracking frequently accessed conversion journeys. For example, if you regularly monitor a funnel such as _App Launched > Product Viewed > Added to Card > Charged_, bookmarking it lets you instantly return to the same setup without recreating the analysis each time.

To bookmark a Funnel analysis:

1. Click **Bookmark** in the top-right corner of the dashboard after generating the funnel analysis.
2. Enter a descriptive name to help you identify the analysis later.
3. Click **Bookmark**.


<Image src="https://files.readme.io/d30480b4184fdba86f08ea050a4fe5c7e7847d8b41e47d136ee7d5056ee2e51c-2026-05-18_15-30-44_1.gif" alt="Bookmark a Funnel Analysis" align="center" caption="Bookmark a Funnel Analysis" border={true} />


<Callout icon="📘" theme="info">
  #### Bookmark Limit

  You can save up to 50 bookmarks and access all your saved bookmarks from the bookmark list under the _Funnels_ section.
</Callout>

## Export Funnel Analysis

You can export the generated funnel analysis for reporting or offline analysis.


<Image src="https://files.readme.io/4714c84a0b8ed1c5b14faa786aaf6e108fb73422bac59651289c063ffc71b8b9-image.png" alt="Export a Funnel Analysis" align="center" caption="Export a Funnel Analysis" border={true} />


Depending on the selected view, Funnels supports export options such as:

- PNG image
- PDF document
- CSV file

Use exports when you want to:

- Share the chart in presentations or documents
- Download the raw tabular values for further analysis
- Archive analysis snapshots for reporting

# FAQs

Find answers to the following common questions about using ̉Funnels:

### How are users counted?

Each user is counted once per funnel evaluation period.

### What happens if a user completes the Funnel more than once?

If a user completes the funnel multiple times within the selected date range, only the first valid conversion within the conversion window is counted. Subsequent completions by the same user are ignored for that analysis.

### What if a user does not complete all Funnel steps?

Users who do not complete all defined funnel steps within the specified conversion window are not considered converted. They are included only in the steps they completed, which helps identify drop-off points in the funnel.

### How does the Conversion Window affect Funnel results?

The conversion window defines the maximum time a user has to complete all funnel steps. If a user exceeds this time, the funnel does not count them as converted, even if they eventually complete all steps. A shorter window results in stricter conversion criteria, while a longer window allows more users to qualify.

### Can I change Funnel settings after viewing results?

Yes. You can modify funnel settings such as events, segments, measurement mode, conversion window, or step order at any time. However, changing these settings triggers a new funnel calculation, and previously generated results are not retained.

### Are Funnel results calculated in real time?

Funnel results are near real-time, but may experience a short processing delay due to varying data volumes and query complexities. Recently ingested events may take a few minutes to appear in funnel analysis.

### Can I compare Funnels across different date ranges?

Yes. You can change the date range and re-run the same funnel configuration to compare performance across different periods. For trend-based analysis, using the Trends measurement mode is recommended.

### Can I use Compare with the Previous Period and Split by Property simultaneously?

No. Comparing with a previous period and splitting a funnel by property are mutually exclusive. Selecting one disables the other in the query builder.

### Can I hold more than one property constant?

No. Hold Constant Property supports holding a single event property constant per funnel. You also cannot hold a user profile property constant only event properties are supported.

### Can I use Hold Constant Property with Split by property?

Yes, but only if both settings reference the same event property. If you select different properties for each, the **View Analysis** option is disabled until you resolve the mismatch. Also, if Split by Property is set to a user property, Hold Constant Property is disabled entirely.

### How does the Hold Constant Property work?

The following are the points to remember when using the Hold Constant Property option:

* Hold Constant Property supports only event properties. You can not hold a user profile property constant. If [Split by Property](doc:funnels-v2#split-by-property) is set to a user profile property, the _Constant Property_ checkbox is disabled because it only applies to event properties.
* You can hold only one event property constant per funnel.

- The [Select Property](doc:funnels-v2#select-property) dropdown lists only properties common to all events currently used in the funnel's steps. If you later change a step's event so the held property is no longer available on every step, CleverTap clears your selection and notifies you.
- If a user performed a step without the held property present on that event, they are treated as not having continued the funnel with the held value, and are not counted as converted from that step onward.
- If any funnel step combines multiple events with an `OR` condition, the Hold constant property across all steps checkbox is disabled.