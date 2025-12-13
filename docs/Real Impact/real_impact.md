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
[block:callout]
{
  "type": "warning",
  "title": "Important",
  "body": "Please note that in order to view Real Impact performance metrics, you will need to enable a **System Control Group** for your account. A System Control Group is an account level categorization of profiles, who will never receive any of your campaigns. To know more check [Control Groups](doc:control-groups).\n\n**Note:** It might take some time for target groups to show a marked improvement in performance over system control group. For instance, if you have created a system control group 5-10 days back, your performance numbers might not be as distinctive. \n\n**Hence, it is advisable to wait for a few weeks after creating system control group to visualise accurate figures in Real Impact dashboard.**"
}
[/block]
With Real Impact, you can:
- Visualize the boost in performance in your target segments as compared to users who have not received any campaigns
- Estimate what percentage of users have churned in the target group by contrasting it with control groups
- Calculate segment wise impact of essential business metrics and know which segments has been performing better compared to others
- Visualize user movement from one RFM segment to another
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af4e987-Screenshot_2019-03-13_at_9.23.03_PM.png",
        "Screenshot 2019-03-13 at 9.23.03 PM.png",
        1216,
        382,
        "#e3eaf5"
      ],
      "border": true
    }
  ]
}
[/block]
To access Real Impact, click on the **Real Impact** menu in the left navigation bar.

Real Impact deals with boost/drop percentage
[block:api-header]
{
  "title": "How is Real Impact calculated"
}
[/block]
As mentioned above, in order to calculate Real Impact, we use system control groups and the calculation is done on the basis of comparison of the performance of target group vs system control groups.
[block:callout]
{
  "type": "info",
  "title": "Formula",
  "body": "**Boost or drop % = (TG-SCG) / SCG * 100**\n\nwhere,\nTG = Target group metric value\nSCG = System control group metric value"
}
[/block]

[block:api-header]
{
  "title": "Performance metrics"
}
[/block]
You will be able to check performance metrics for any segment at any date range. CleverTap offers the capability to measure the following performance metrics out of the box:
[block:parameters]
{
  "data": {
    "h-0": "Performance Metrics",
    "h-1": "Interpretation",
    "h-2": "Derivation",
    "0-0": "Sticky quotient",
    "0-1": "How often your audience engages with your product after receiving your campaign over a given duration.",
    "0-2": "Daily active users / Monthly active users.",
    "1-0": "Retention",
    "2-0": "Conversion",
    "3-0": "Revenue per user",
    "4-0": "RFM segments: RFM Score",
    "5-0": "RFM segments: Matrix",
    "6-0": "RFM segments: Transitions",
    "1-1": "Indicates how many users come back to your product to perform a set of actions based on your marketing efforts over a given period. For example, what percentage of users that made a purchase came back for a repeat purchase in the last 30 days?",
    "2-1": "Measure the Real Impact of your campaigns on a target group for a conversion event. This metric tells you what percent of target group users converted on your product as compared to the conversion rate of control group users.",
    "3-1": "Select an event and its corresponding revenue property to identify the revenue per user over a period of time. For example, compare the average revenue per user in the target group (who received campaigns) and control group (who didn’t receive campaigns) in the last 30 days.",
    "4-1": "This Real Impact metric gives the boost in health score of the target group based on recency, frequency, and monetary parameters. For example: what is the RFM health score for all users that launched an app and made a purchase in the last 30 days?",
    "3-2": "Sum of amount property of Charged / Total number of active users",
    "1-2": "Similar to [Cohorts](doc:cohorts)",
    "2-2": "Similar to 2 step [Funnels](doc:funnels)",
    "5-1": "Increase/decrease percentage of users in each of RFM sub segments from two consecutive date range",
    "6-1": "Viewing users movements from one subsegment to another",
    "7-0": "Recency",
    "8-0": "Frequency",
    "5-2": "Visualization",
    "6-2": "Visualization",
    "7-1": "Track how recently target users visited your product in the last 30 days as compared to the control group.",
    "7-2": "Median number of days users have been recent",
    "8-1": "Frequency of an event being done on the app by users",
    "8-2": "Median number of times an event is performed within the time range",
    "4-2": "See **RFM score** below"
  },
  "cols": 3,
  "rows": 9
}
[/block]

[block:api-header]
{
  "title": "RFM Score"
}
[/block]
RFM scores denote the value of your app/website's users. The value of the user is measured across 3 dimensions - recency, frequency and monetary and then the user is automatically assigned a score.
[block:callout]
{
  "type": "info",
  "body": "CleverTap uses a unique method to calculate RFM scores. Recency, Frequency and Monetary values are calculated for all users. Users are divided into 5 different sections according to their percentiles. So, the bottom 20% will be in the first percentile and get a score of 1. The next 20% get a score of 2 and so on upto a score of 5. \n\nThe scores are calculated for all the three dimensions - recency (R), frequency (F) and monetary (M). Finally, RFM score is arrived at by taking into considerations the weights of the individual dimensions.\n\n**RFM Score = 4xR + 2xF + M**",
  "title": "How RFM score is calculated"
}
[/block]