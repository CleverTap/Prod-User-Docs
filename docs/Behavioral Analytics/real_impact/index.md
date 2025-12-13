---
title: Real Impact
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

*Real Impact* is a reporting dashboard that shows how and by what extent users respond to your CleverTap marketing campaigns—everything from the revenue generated to churn. With *Real Impact*, you can move beyond vanity metrics and optimize your campaigns based on which campaigns are driving business results.

> 🚧 System Control Group Requirement and Performance
>
> To view *Real Impact* performance metrics, you need to enable a system control group for your account; this system control group is an account-level categorization of profiles that will never receive any of your campaigns. For more information, refer to [Control Groups](doc:control-groups).
>
> It might take some time for target groups to show a marked improvement in performance over a system control group. For instance, if you have created a system control group 5 to 10 days ago, your performance numbers might not be as distinctive. 
>
> It is recommended to wait for a few weeks after creating a system control group to visualize accurate figures in the *Real Impact* dashboard.

*Real Impact* helps you measure the impact of your campaigns:

* Visualize the boost in performance in your target segments as compared to users who have not received any campaigns.
* Estimate what percentage of users have churned in the target group by contrasting it with control groups.
* Calculate the segment-wise impact of essential business metrics and know which segments have been performing better compared to others.
* Visualize user movement from one RFM segment to another.

<Image title="Screenshot 2019-03-13 at 9.23.03 PM.png" alt={1216} className="border" border={true} src="https://files.readme.io/af4e987-Screenshot_2019-03-13_at_9.23.03_PM.png" />

To access *Real Impact*, navigate to *Analytics* > *Real Impact*. *Real Impact* deals with boost/drop percentage.

## How is Real Impact Calculated

As mentioned above in order to calculate *Real Impact*, we use system control groups and the calculation is done on the basis of comparison of the performance of target group vs. system control groups.

> 📘 Formula
>
> The formula consists of:
>
> * TG = Target group metric value
> * SCG = System control group metric value
>
> Boost or drop % = (TG-SCG) / SCG \* 100

## Performance Metrics

You can check performance metrics for any segment at any date range. CleverTap offers the capability to measure the following performance metrics out of the box:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Performance Metrics
      </th>

      <th>
        Interpretation
      </th>

      <th>
        Derivation
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Sticky Quotient
      </td>

      <td>
        How often your audience engages with your product after receiving your campaign over a given duration.
      </td>

      <td>
        Daily active users / Monthly active users.
      </td>
    </tr>

    <tr>
      <td>
        Retention
      </td>

      <td>
        Indicates how many users come back to your product to perform a set of actions based on your marketing efforts over a given period. For example, what percentage of users who made a purchase came back for a repeat purchase in the last 30 days?
      </td>

      <td>
        Similar to [Cohorts](doc:cohorts).
      </td>
    </tr>

    <tr>
      <td>
        Conversion
      </td>

      <td>
        Measures the real impact of your campaigns on a target group for a conversion event. This metric tells you what percentage of target group users converted on your product as compared to the conversion rate of control group users.
      </td>

      <td>
        Similar to [Funnels](doc:funnels).
      </td>
    </tr>

    <tr>
      <td>
        Revenue per User
      </td>

      <td>
        Select an event and its corresponding revenue property to identify the revenue per user over a period of time. For example, compare the average revenue per user in the target group who received campaigns and control group who did not receive campaigns in the last 30 days.
      </td>

      <td>
        Sum of amount property of *Charged* / Total number of active users.
      </td>
    </tr>

    <tr>
      <td>
        RFM Segments: RFM Score
      </td>

      <td>
        This *Real Impact* metric gives the boost in health score of the target group based on recency, frequency, and monetary parameters. 

        For example, what is the RFM health score for all users who launched an app and made a purchase in the last 30 days?
      </td>

      <td>
        Refer to [RFM Score](https://docs.clevertap.com/docs/real_impact#section-rfm-score) below.
      </td>
    </tr>

    <tr>
      <td>
        RFM Segments: Matrix
      </td>

      <td>
        Increases/decreases percentage of users in each of RFM sub-segments from two consecutive date ranges.
      </td>

      <td>
        Visualization.
      </td>
    </tr>

    <tr>
      <td>
        RFM Segments: Transitions
      </td>

      <td>
        Views users movements from one sub-segment to another.
      </td>

      <td>
        Visualization.
      </td>
    </tr>

    <tr>
      <td>
        Recency
      </td>

      <td>
        Tracks how recently target users visited your product in the last 30 days as compared to the control group.
      </td>

      <td>
        Median number of days users have been recent.
      </td>
    </tr>

    <tr>
      <td>
        Frequency
      </td>

      <td>
        Frequency of an event being done on the app by users.
      </td>

      <td>
        Median number of times an event is performed within the time range.
      </td>
    </tr>
  </tbody>
</Table>

## RFM Score

RFM scores denote the value of your app/website's users. The value of the user is measured across three dimensions including, recency, frequency, and monetary, then the user is automatically assigned a score.

> 📘 How RFM Score is Calculated
>
> CleverTap uses a unique method to calculate RFM scores. Recency, frequency, and monetary values are calculated for all users. Users are divided into five different sections according to their percentiles. Therefore, the bottom 20% will be in the first percentile and get a score of 1. The next 20% get a score of 2 and so on up to a score of 5. 
>
> The scores are calculated for all the three dimensions including, recency (R), frequency (F), and monetary (M). Finally, the RFM score is also calculated by taking into considerations the weights of the individual dimensions.
>
> RFM Score = 4xR + 2xF + M
