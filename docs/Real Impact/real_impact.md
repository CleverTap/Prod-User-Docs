---
title: Real Impact
excerpt: Measure the impact of your campaigns
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Real Impact is a reporting dashboard that shows you exactly how and by what extent users respond to your CleverTap marketing campaigns – everything from the revenue generated to churn. With Real Impact, you can move beyond vanity metrics and optimize your campaigns based on which campaigns are driving business results.

> 🚧 Important
>
> Please note that in order to view Real Impact performance metrics, you will need to enable a **System Control Group** for your account. A System Control Group is an account level categorization of profiles, who will never receive any of your campaigns. To know more check [Control Groups](doc:control-groups).
>
> **Note:** It might take some time for target groups to show a marked improvement in performance over system control group. For instance, if you have created a system control group 5-10 days back, your performance numbers might not be as distinctive. 
>
> **Hence, it is advisable to wait for a few weeks after creating system control group to visualise accurate figures in Real Impact dashboard.**

With Real Impact, you can:

* Visualize the boost in performance in your target segments as compared to users who have not received any campaigns
* Estimate what percentage of users have churned in the target group by contrasting it with control groups
* Calculate segment wise impact of essential business metrics and know which segments has been performing better compared to others
* Visualize user movement from one RFM segment to another

<Image title="Screenshot 2019-03-13 at 9.23.03 PM.png" alt={1216} className="border" border={true} src="https://files.readme.io/af4e987-Screenshot_2019-03-13_at_9.23.03_PM.png" />

To access Real Impact, click on the **Real Impact** menu in the left navigation bar.

Real Impact deals with boost/drop percentage

## How is Real Impact calculated

As mentioned above, in order to calculate Real Impact, we use system control groups and the calculation is done on the basis of comparison of the performance of target group vs system control groups.

> 📘 Formula
>
> **Boost or drop % = (TG-SCG) / SCG \* 100**
>
> where,\
> TG = Target group metric value\
> SCG = System control group metric value

## Performance metrics

You will be able to check performance metrics for any segment at any date range. CleverTap offers the capability to measure the following performance metrics out of the box:

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
        Sticky quotient
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
        Indicates how many users come back to your product to perform a set of actions based on your marketing efforts over a given period. For example, what percentage of users that made a purchase came back for a repeat purchase in the last 30 days?
      </td>

      <td>
        Similar to [Cohorts](doc:cohorts)
      </td>
    </tr>

    <tr>
      <td>
        Conversion
      </td>

      <td>
        Measure the Real Impact of your campaigns on a target group for a conversion event. This metric tells you what percent of target group users converted on your product as compared to the conversion rate of control group users.
      </td>

      <td>
        Similar to 2 step [Funnels](doc:funnels)
      </td>
    </tr>

    <tr>
      <td>
        Revenue per user
      </td>

      <td>
        Select an event and its corresponding revenue property to identify the revenue per user over a period of time. For example, compare the average revenue per user in the target group (who received campaigns) and control group (who didn’t receive campaigns) in the last 30 days.
      </td>

      <td>
        Sum of amount property of Charged / Total number of active users
      </td>
    </tr>

    <tr>
      <td>
        RFM segments: RFM Score
      </td>

      <td>
        This Real Impact metric gives the boost in health score of the target group based on recency, frequency, and monetary parameters. For example: what is the RFM health score for all users that launched an app and made a purchase in the last 30 days?
      </td>

      <td>
        See **RFM score** below
      </td>
    </tr>

    <tr>
      <td>
        RFM segments: Matrix
      </td>

      <td>
        Increase/decrease percentage of users in each of RFM sub segments from two consecutive date range
      </td>

      <td>
        Visualization
      </td>
    </tr>

    <tr>
      <td>
        RFM segments: Transitions
      </td>

      <td>
        Viewing users movements from one subsegment to another
      </td>

      <td>
        Visualization
      </td>
    </tr>

    <tr>
      <td>
        Recency
      </td>

      <td>
        Track how recently target users visited your product in the last 30 days as compared to the control group.
      </td>

      <td>
        Median number of days users have been recent
      </td>
    </tr>

    <tr>
      <td>
        Frequency
      </td>

      <td>
        Frequency of an event being done on the app by users
      </td>

      <td>
        Median number of times an event is performed within the time range
      </td>
    </tr>
  </tbody>
</Table>

## RFM Score

RFM scores denote the value of your app/website's users. The value of the user is measured across 3 dimensions - recency, frequency and monetary and then the user is automatically assigned a score.

> 📘 How RFM score is calculated
>
> CleverTap uses a unique method to calculate RFM scores. Recency, Frequency and Monetary values are calculated for all users. Users are divided into 5 different sections according to their percentiles. So, the bottom 20% will be in the first percentile and get a score of 1. The next 20% get a score of 2 and so on upto a score of 5. 
>
> The scores are calculated for all the three dimensions - recency (R), frequency (F) and monetary (M). Finally, RFM score is arrived at by taking into considerations the weights of the individual dimensions.
>
> **RFM Score = 4xR + 2xF + M**
