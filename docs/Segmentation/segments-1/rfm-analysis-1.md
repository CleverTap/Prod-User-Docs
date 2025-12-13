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
@DOCS: ONCE APPROVED BY PM, REPLACE EXISTING USER DOC [https://docs.clevertap.com/docs/rfm](https://docs.clevertap.com/docs/rfm) AND MOVE TO CORRECT SPOT IN THE TABLE OF CONTENT.

> 📘 Enterprise Only
>
> Being a part of CleverTap's Discovery platform, RFM analysis is only available for Enterprise customers.

# Overview

The recency, frequency, monetary (RFM) analysis feature provides the capability to analyze the health of your user base and run engagement campaigns to target specific user segments that need improvement. 

The RFM analysis is a user segmentation model that segments your users based on how recently and frequently they performed a specific event. The output of the RFM analysis is a segmentation of your users into 10 RFM user types which range from champion users who are your best customers to hibernating users who are likely to churn. 

> 👍 E-commerce App Example
>
> With an e-commerce app, you can run an RFM analysis to understand the segmentation of your user base based on how recently and frequently they purchased a product. If you discover you have a lot of hibernating users, you can run a campaign to re-engage these users and encourage them to make a purchase by sending them a discount code.

As part of our RFM Analysis feature, we provide two tools: 

* RFM grid: Visualization to show the number of users in each RFM segment, their average monetary value, and their reachability on different marketing channels.
* RFM transition: Visualization to show the flow of users from one RFM segment to another.

# RFM Grid

The RFM grid is a visualization tool available in the CleverTap dashboard. This tool presents the results of the RFM analysis for your user base in a simple chart highlighting the number of users in each RFM segment, their average monetary value, and their reachability on different marketing channels.

<Image title="rfm1.png" alt={1171} className="border" border={true} src="https://files.readme.io/7ee1e81-rfm1.png" />

## RFM Grid Guide

To access the RFM grid, perform the following steps:

1. From the dashboard, navigate to *Segments* > *RFM*.
2. Select the date range and event for your RFM analysis. 

> 📘 Selection Range Tip for First-time Users
>
> For your first analysis, *App Launched* over the past 30 days is a good choice.

3. Click **Calculate** to run the analysis. 

![2384](https://files.readme.io/3309f79-RFM_grid.png "RFM grid.png")

4. The RFM grid displays at the bottom of the same page. Click on any segment to:

* View more details.
* Save it for later analysis.
* Create a message. 

<Image title="rfm4.png" alt={1092} className="border" border={true} src="https://files.readme.io/f82a1cf-rfm4.png" />

# RFM Transitions

The RFM transition is a visualization tool available in the CleverTap dashboard. This tool helps you understand the flow of your users from one RFM segment to another, such as how many new users became champions.

> 👍 New User Example
>
> For example, if you notice that a lot of your hibernating users are coming from the *New Users* segment, you can now pinpoint where your new users' churn is coming from. With this new information, you can improve the situation by creating a better onboarding experience.

> 📘 Hibernating vs. Inactive
>
> The difference between a hibernating user and an inactive user is a hibernating user has performed the selected event at least once in the defined time range.

The following is a sample RFM transition analysis:

<Image title="rfm2.png" alt={1201} className="border" border={true} src="https://files.readme.io/5c9cb21-rfm2.png" />

## RFM Transition Guide

To access the RFM transition guide, perform the following steps:

1. From the dashboard, navigate to *Segments* > *RFM*.
2. Select the date range and event for your RFM analysis. 

> 📘 Selection Range Tip for First-time Users
>
> For your first analysis, *App Launched* over the past 30 days is a good choice.

3. Click **Calculate** to run the analysis. 

<Image title="RFM Transition Guide.png" alt={2371} className="border" border={true} src="https://files.readme.io/fddeaf8-RFM_Transition_Guide.png" />

> 📘 Tip for Optimal Results
>
> For optimal results, check that the selected date range for the events is less than 512 days.

4. Click on the **Transitions** tab. 

<Image title="RFM transition tab.png" alt={1196} className="border" border={true} src="https://files.readme.io/779b52c-RFM_transition_tab.png" />

5. Once the RFM transitions tool loads, click on any segment to understand the flow of users into that segment.
6. Click on the **Champions** segment to find out the sources of its users.

<Image title="2rfm.png" alt={1176} className="border" border={true} src="https://files.readme.io/3de552e-2rfm.png" />

The visualization displays on the left and the table with data on the right. Both of these show the sources of users into the *Champions* segment.

<Image title="3rfm.png" alt={1164} className="border" border={true} src="https://files.readme.io/35956b6-3rfm.png" />

7. From the table on the right, click the vertical ellipsis on a segment to:

* View more details.
* Save it for later analysis.
* Create a message. 

<Image title="RFM transition tab ellipsis.png" alt={1173} className="border" border={true} src="https://files.readme.io/e5d8662-RFM_transition_tab_ellipsis.png" />

# RFM User Segments

The RFM user segments are as follows:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        User Segment
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Champions
      </td>

      <td>
        These users are your most active users. They have the highest recency and frequency scores.
      </td>
    </tr>

    <tr>
      <td>
        Loyal Users
      </td>

      <td>
        These users have the highest frequency of use with strong recency scores.
      </td>
    </tr>

    <tr>
      <td>
        Potential Loyalists
      </td>

      <td>
        These users have visited your app very recently and have the potential to become loyalists or champions.
      </td>
    </tr>

    <tr>
      <td>
        New Users
      </td>

      <td>
        These users are your most recent users with low frequency scores. Strong candidates to encourage repeat use.
      </td>
    </tr>

    <tr>
      <td>
        Promising
      </td>

      <td>
        These users have high recency scores with the potential to become high frequency users.
      </td>
    </tr>

    <tr>
      <td>
        Needing Attention
      </td>

      <td>
        These users have above average recency and frequency scores.
      </td>
    </tr>

    <tr>
      <td>
        About to Sleep
      </td>

      <td>
        These users have below-average recency and frequency scores. They may slip away if not engaged with.
      </td>
    </tr>

    <tr>
      <td>
        At Risk
      </td>

      <td>
        These users have above average frequency but low recency scores. Strong candidates to re-engage.
      </td>
    </tr>

    <tr>
      <td>
        Cannot Lose Them
      </td>

      <td>
        These users were active at one point in your app, but haven’t been back recently. Strong candidates to re-engage.
      </td>
    </tr>

    <tr>
      <td>
        Hibernating
      </td>

      <td>
        These users have the lowest recency and frequency scores. They may be lost.
      </td>
    </tr>
  </tbody>
</Table>

# How RFM Analysis Works

For every user who has performed the selected event, our RFM analysis segment users based on:

* How many times a user performed the event.
* The last time a user performed the event.

## Calculate Recency Score

Once we have determined how recently each user in your analysis performed the selected event, we rank them in order of percentile (person who has performed it most recently would constitute the 100th percentile), then we rank the users on a score of 1 to 5 based on their percentile with 5 being the highest.

## Calculate Frequency Score

Once we have figured out how frequently each user in your analysis performed the event, we rank them in order of percentile (person who has performed it most frequently would constitute the 100th percentile), then we rank the users on a score of 1 to 5 based on their percentile with 5 being the highest.

## Average Monetary Value

The average monetary value (AVM) is the average spend for each user in the RFM user segment. The monetary value can be any kind of user spend on your app, such as money or time. The formula for calculating AVM is the sum of all user spend/number of users. 

### Examples

In this example, you have 100 users in your champion segment. If the combined spend for all champion users is $500, then the AVM is 500/100 = $5 for each champion user. 

Another example can be calculating the number of videos watched by each user for a video streaming app or the number of hours spent by each user for watching those videos.

> 📘 Minor Difference in Counts
>
> You may see a minor difference in counts when you compare these numbers with the numbers in your dashboard. However, the numbers are directionally correct.
