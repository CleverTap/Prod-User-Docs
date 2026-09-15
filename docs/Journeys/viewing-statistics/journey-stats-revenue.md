---
title: Journey Stats
excerpt: >-
  Gain actionable insights into user behavior, goal completion, and campaign
  effectiveness, version by version.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Journey Stats provides comprehensive performance metrics for journeys, enabling you to track how users progress through the journey, evaluate goal achievement, and compare target versus control group results.

The calendar widget lets you customize the date range to view journey performance data. The Users in journey count reflects real-time data; all other metrics are calculated for the selected date range.


<Image src="https://files.readme.io/88323336844ed9ec7f1201f3d34719c0d8c26611d64359e39eea1e2790faff40-Users_in_Journey.png" align="center" caption="Users in Journey" border={true} />


The top section shows the following metrics for the selected journey version (refer to the above image):

| Metric          | Description                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------- |
| Entered Journey | Count of users who initiated the journey. Updates in real time, independent of the selected date range. |
| Qualified       | Users who met the entry conditions and were processed by journey nodes.                                 |
| Control Group   | Random users excluded from the journey for A/B comparison purposes.                                     |
| Goal Met        | Users who fulfilled the defined journey goal.                                                           |
| Timed Out       | Users who did not complete the journey within the allowed timeframe.                                    |
| Force Exits     | Users removed from the journey due to defined exit conditions.                                          |

The Journey Stats is further organized into the following two tabs:

| Tab                    | Description                                                                                                                                                            |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Entry & Exit Trend     | Includes the line graphs for entries, completions, goal achievement, and timeouts.                                                                                     |
| Conversion Performance | Includes the goal Conversion Rate and Revenue Performance cards. This tab appears only when a revenue attribute is configured on at least one Action or Inaction goal. |

<Callout icon="📘" theme="info">
  #### Conversion Performance Tab

  The Conversion Performance tab is not visible for journeys where no revenue attribute has been configured. For detailed setup instructions, refer to Define Goals. (@amrita to add cross-reference here.)
</Callout>

# Entry & Exit Trends Tab

The Trends tab provides daily, weekly, and monthly trends for the following:

- Journey entries
- Journey completions
- Goal achievement
- Timeout occurrences


<Image src="https://files.readme.io/39d94572437f91e549048e5861412d82ea82c3a1fbc420ada4343cc96d537694-Entry__Exit_Trend.png" align="center" caption="Entry & Exit Trends" border={true} />


<br />

Use these trends to identify behavioral patterns and performance changes over time.

# Conversion Performance Tab

The Conversion Performance tab is available when revenue tracking is configured for the journey via an Action or Inaction goal. It contains the following two cards:&#x20;


<Image src="https://files.readme.io/1fc10ba7c1b7f91f6fe497889adb6815be5dea590e938dab7327021beaa133b4-Conversion_Performance_Tab.png" align="center" caption="Conversion Performance Tab" border={true} />


- Conversion Performance&#x20;
- Revenue Performance

Both cards have the same selectors as follows:

| Selector      | Options                                                                                                              | Effect                                      |
| ------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| Goal          | All Goals / Goal 1 / Goal 2/ Goal 3                                                                                  | Filters cards to the selected goal          |
| Control Group | Shows only the control group types configured for this journey (Custom Control Group, System Control Group, or both) | Switches  cards between control group types |

<Callout icon="📘" theme="info">
  #### Note

  Revenue tracking is only supported for Action and Inaction goals. Past Behavior Segment (PBS) goals do not support revenue tracking. If a PBS goal is selected, both cards display NA for all revenue and conversion rate values. (@saby: Please verify if this is correct.)
</Callout>

## Conversion Performance Card

Displays a chart of the goal conversion rate, showing what percentage of journey users successfully completed the goal.

- **Conversion Rate**

  `Conversion Rate = (Conversions ÷ Entered) × 100`&#x20;
- **Conversion Boost**

  `Conversion Boost = [(Target Group % − Control Group %) ÷ Control Group %] × 100`

The card shows separate rates for:

- **Conversion Boost**: The percentage uplift of the Target Group conversion rate over the Control Group conversion rate
- **Target Group**: Number of users in the main campaign.
- **Control Group:**  Number of users in the selected control group.

## Revenue Performance Card

Displays the following three revenue figures attributed to users who converted through the selected goal:

| Metric                | Description                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| Target Group Revenue  | Total revenue from users in the main campaign (not in any control group) |
| Control Group Revenue | Total revenue from users in the selected control group                   |
| Revenue Boost         | Absolute revenue uplift: Target Group Revenue − Control Group Revenue    |

**Revenue Boost formula**

`Revenue Boost = Target Group Revenue − Control Group Revenue`

<Callout icon="📘" theme="info">
  #### Note

  Revenue Boost here is an absolute value (currency difference), not a percentage uplift. This is distinct from Conversion Boost in the Conversion Performance card, which is a percentage uplift.
</Callout>
