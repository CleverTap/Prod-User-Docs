---
title: RFM Analysis
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
@DOCS: ONCE APPROVED BY PM, REPLACE EXISTING USER DOC https://docs.clevertap.com/docs/rfm AND MOVE TO CORRECT SPOT IN THE TABLE OF CONTENT.
[block:callout]
{
  "type": "info",
  "body": "Being a part of CleverTap's Discovery platform, RFM analysis is only available for Enterprise customers.",
  "title": "Enterprise Only"
}
[/block]
# Overview

The recency, frequency, monetary (RFM) analysis feature provides the capability to analyze the health of your user base and run engagement campaigns to target specific user segments that need improvement. 

The RFM analysis is a user segmentation model that segments your users based on how recently and frequently they performed a specific event. The output of the RFM analysis is a segmentation of your users into 10 RFM user types which range from champion users who are your best customers to hibernating users who are likely to churn. 
[block:callout]
{
  "type": "success",
  "title": "E-commerce App Example",
  "body": "With an e-commerce app, you can run an RFM analysis to understand the segmentation of your user base based on how recently and frequently they purchased a product. If you discover you have a lot of hibernating users, you can run a campaign to re-engage these users and encourage them to make a purchase by sending them a discount code."
}
[/block]
As part of our RFM Analysis feature, we provide two tools: 
* RFM grid: Visualization to show the number of users in each RFM segment, their average monetary value, and their reachability on different marketing channels.
* RFM transition: Visualization to show the flow of users from one RFM segment to another.

# RFM Grid 

The RFM grid is a visualization tool available in the CleverTap dashboard. This tool presents the results of the RFM analysis for your user base in a simple chart highlighting the number of users in each RFM segment, their average monetary value, and their reachability on different marketing channels.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ee1e81-rfm1.png",
        "rfm1.png",
        1171,
        593,
        "#c8d2c6"
      ],
      "border": true,
      "caption": ""
    }
  ]
}
[/block]
## RFM Grid Guide

To access the RFM grid, perform the following steps:
1. From the dashboard, navigate to *Segments* > *RFM*.
2. Select the date range and event for your RFM analysis. 
[block:callout]
{
  "type": "info",
  "body": "For your first analysis, *App Launched* over the past 30 days is a good choice.",
  "title": "Selection Range Tip for First-time Users"
}
[/block]
3. Click **Calculate** to run the analysis. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3309f79-RFM_grid.png",
        "RFM grid.png",
        2384,
        1506,
        "#f7f8fa"
      ]
    }
  ]
}
[/block]
4. The RFM grid displays at the bottom of the same page. Click on any segment to:
  * View more details.
  * Save it for later analysis.
  * Create a message. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f82a1cf-rfm4.png",
        "rfm4.png",
        1092,
        611,
        "#c5c7c6"
      ],
      "border": true
    }
  ]
}
[/block]
# RFM Transitions 

The RFM transition is a visualization tool available in the CleverTap dashboard. This tool helps you understand the flow of your users from one RFM segment to another, such as how many new users became champions.
[block:callout]
{
  "type": "success",
  "body": "For example, if you notice that a lot of your hibernating users are coming from the *New Users* segment, you can now pinpoint where your new users' churn is coming from. With this new information, you can improve the situation by creating a better onboarding experience.",
  "title": "New User Example"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The difference between a hibernating user and an inactive user is a hibernating user has performed the selected event at least once in the defined time range.",
  "title": "Hibernating vs. Inactive"
}
[/block]
The following is a sample RFM transition analysis:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c9cb21-rfm2.png",
        "rfm2.png",
        1201,
        702,
        "#f8f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
## RFM Transition Guide

To access the RFM transition guide, perform the following steps:
1. From the dashboard, navigate to *Segments* > *RFM*.
2. Select the date range and event for your RFM analysis. 

[block:callout]
{
  "type": "info",
  "title": "Selection Range Tip for First-time Users",
  "body": "For your first analysis, *App Launched* over the past 30 days is a good choice."
}
[/block]
3. Click **Calculate** to run the analysis. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fddeaf8-RFM_Transition_Guide.png",
        "RFM Transition Guide.png",
        2371,
        1506,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Tip for Optimal Results",
  "body": "For optimal results, check that the selected date range for the events is less than 512 days."
}
[/block]

4. Click on the **Transitions** tab. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/779b52c-RFM_transition_tab.png",
        "RFM transition tab.png",
        1196,
        639,
        "#dfdcd8"
      ],
      "border": true
    }
  ]
}
[/block]
5. Once the RFM transitions tool loads, click on any segment to understand the flow of users into that segment.
6. Click on the **Champions** segment to find out the sources of its users.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3de552e-2rfm.png",
        "2rfm.png",
        1176,
        647,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]
The visualization displays on the left and the table with data on the right. Both of these show the sources of users into the *Champions* segment.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/35956b6-3rfm.png",
        "3rfm.png",
        1164,
        651,
        "#faf9fa"
      ],
      "border": true
    }
  ]
}
[/block]
7. From the table on the right, click the vertical ellipsis on a segment to:
  * View more details.
  * Save it for later analysis.
  * Create a message. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5d8662-RFM_transition_tab_ellipsis.png",
        "RFM transition tab ellipsis.png",
        1173,
        457,
        "#f5f2f8"
      ],
      "border": true
    }
  ]
}
[/block]
# RFM User Segments

The RFM user segments are as follows:
[block:parameters]
{
  "data": {
    "h-0": "User Segment",
    "h-1": "Description",
    "0-0": "Champions",
    "0-1": "These users are your most active users. They have the highest recency and frequency scores.",
    "1-0": "Loyal Users",
    "1-1": "These users have the highest frequency of use with strong recency scores.",
    "2-1": "These users have visited your app very recently and have the potential to become loyalists or champions.",
    "2-0": "Potential Loyalists",
    "3-0": "New Users",
    "3-1": "These users are your most recent users with low frequency scores. Strong candidates to encourage repeat use.",
    "4-1": "These users have high recency scores with the potential to become high frequency users.",
    "4-0": "Promising",
    "5-0": "Needing Attention",
    "5-1": "These users have above average recency and frequency scores.",
    "6-0": "About to Sleep",
    "6-1": "These users have below-average recency and frequency scores. They may slip away if not engaged with.",
    "7-1": "These users have above average frequency but low recency scores. Strong candidates to re-engage.",
    "7-0": "At Risk",
    "8-0": "Cannot Lose Them",
    "8-1": "These users were active at one point in your app, but haven’t been back recently. Strong candidates to re-engage.",
    "9-1": "These users have the lowest recency and frequency scores. They may be lost.",
    "9-0": "Hibernating"
  },
  "cols": 2,
  "rows": 10
}
[/block]
# How RFM Analysis Works

For every user who has performed the selected event, our RFM analysis segment users based on:
  * How many times a user performed the event.
  * The last time a user performed the event.

##Calculate Recency Score
Once we have determined how recently each user in your analysis performed the selected event, we rank them in order of percentile (person who has performed it most recently would constitute the 100th percentile), then we rank the users on a score of 1 to 5 based on their percentile with 5 being the highest.

##Calculate Frequency Score
Once we have figured out how frequently each user in your analysis performed the event, we rank them in order of percentile (person who has performed it most frequently would constitute the 100th percentile), then we rank the users on a score of 1 to 5 based on their percentile with 5 being the highest.

##Average Monetary Value
The average monetary value (AVM) is the average spend for each user in the RFM user segment. The monetary value can be any kind of user spend on your app, such as money or time. The formula for calculating AVM is the sum of all user spend/number of users. 

###Examples
In this example, you have 100 users in your champion segment. If the combined spend for all champion users is $500, then the AVM is 500/100 = $5 for each champion user. 

Another example can be calculating the number of videos watched by each user for a video streaming app or the number of hours spent by each user for watching those videos.
[block:callout]
{
  "type": "info",
  "title": "Minor Difference in Counts",
  "body": "You may see a minor difference in counts when you compare these numbers with the numbers in your dashboard. However, the numbers are directionally correct."
}
[/block]