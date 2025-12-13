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
[block:api-header]
{
  "title": "Overview"
}
[/block]
*Real Impact* is a reporting dashboard that shows how and by what extent users respond to your CleverTap marketing campaigns—everything from the revenue generated to churn. With *Real Impact*, you can move beyond vanity metrics and optimize your campaigns based on which campaigns are driving business results.
[block:callout]
{
  "type": "warning",
  "title": "System Control Group Requirement and Performance",
  "body": "To view *Real Impact* performance metrics, you need to enable a system control group for your account; this system control group is an account-level categorization of profiles that will never receive any of your campaigns. For more information, refer to [Control Groups](doc:control-groups).\n\nIt might take some time for target groups to show a marked improvement in performance over a system control group. For instance, if you have created a system control group 5 to 10 days ago, your performance numbers might not be as distinctive. \n\nIt is recommended to wait for a few weeks after creating a system control group to visualize accurate figures in the *Real Impact* dashboard."
}
[/block]
*Real Impact* helps you measure the impact of your campaigns:
- Visualize the boost in performance in your target segments as compared to users who have not received any campaigns.
- Estimate what percentage of users have churned in the target group by contrasting it with control groups.
- Calculate the segment-wise impact of essential business metrics and know which segments have been performing better compared to others.
- Visualize user movement from one RFM segment to another.
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
To access *Real Impact*, navigate to *Analytics* > *Real Impact*. *Real Impact* deals with boost/drop percentage.
[block:api-header]
{
  "title": "How is Real Impact Calculated"
}
[/block]
As mentioned above in order to calculate *Real Impact*, we use system control groups and the calculation is done on the basis of comparison of the performance of target group vs. system control groups.
[block:callout]
{
  "type": "info",
  "title": "Formula",
  "body": "The formula consists of:\n* TG = Target group metric value\n* SCG = System control group metric value\n\nBoost or drop % = (TG-SCG) / SCG * 100"
}
[/block]

[block:api-header]
{
  "title": "Performance Metrics"
}
[/block]
You can check performance metrics for any segment at any date range. CleverTap offers the capability to measure the following performance metrics out of the box:
[block:parameters]
{
  "data": {
    "h-0": "Performance Metrics",
    "h-1": "Interpretation",
    "h-2": "Derivation",
    "0-0": "Sticky Quotient",
    "0-1": "How often your audience engages with your product after receiving your campaign over a given duration.",
    "0-2": "Daily active users / Monthly active users.",
    "1-0": "Retention",
    "2-0": "Conversion",
    "3-0": "Revenue per User",
    "4-0": "RFM Segments: RFM Score",
    "5-0": "RFM Segments: Matrix",
    "6-0": "RFM Segments: Transitions",
    "1-1": "Indicates how many users come back to your product to perform a set of actions based on your marketing efforts over a given period. For example, what percentage of users who made a purchase came back for a repeat purchase in the last 30 days?",
    "2-1": "Measures the real impact of your campaigns on a target group for a conversion event. This metric tells you what percentage of target group users converted on your product as compared to the conversion rate of control group users.",
    "3-1": "Select an event and its corresponding revenue property to identify the revenue per user over a period of time. For example, compare the average revenue per user in the target group who received campaigns and control group who did not receive campaigns in the last 30 days.",
    "4-1": "This *Real Impact* metric gives the boost in health score of the target group based on recency, frequency, and monetary parameters. \n\nFor example, what is the RFM health score for all users who launched an app and made a purchase in the last 30 days?",
    "3-2": "Sum of amount property of *Charged* / Total number of active users.",
    "1-2": "Similar to [Cohorts](doc:cohorts).",
    "2-2": "Similar to [Funnels](doc:funnels).",
    "5-1": "Increases/decreases percentage of users in each of RFM sub-segments from two consecutive date ranges.",
    "6-1": "Views users movements from one sub-segment to another.",
    "7-0": "Recency",
    "8-0": "Frequency",
    "5-2": "Visualization.",
    "6-2": "Visualization.",
    "7-1": "Tracks how recently target users visited your product in the last 30 days as compared to the control group.",
    "7-2": "Median number of days users have been recent.",
    "8-1": "Frequency of an event being done on the app by users.",
    "8-2": "Median number of times an event is performed within the time range.",
    "4-2": "Refer to [RFM Score](https://docs.clevertap.com/docs/real_impact#section-rfm-score) below."
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
RFM scores denote the value of your app/website's users. The value of the user is measured across three dimensions including, recency, frequency, and monetary, then the user is automatically assigned a score.
[block:callout]
{
  "type": "info",
  "body": "CleverTap uses a unique method to calculate RFM scores. Recency, frequency, and monetary values are calculated for all users. Users are divided into five different sections according to their percentiles. Therefore, the bottom 20% will be in the first percentile and get a score of 1. The next 20% get a score of 2 and so on up to a score of 5. \n\nThe scores are calculated for all the three dimensions including, recency (R), frequency (F), and monetary (M). Finally, the RFM score is also calculated by taking into considerations the weights of the individual dimensions.\n\nRFM Score = 4xR + 2xF + M",
  "title": "How RFM Score is Calculated"
}
[/block]