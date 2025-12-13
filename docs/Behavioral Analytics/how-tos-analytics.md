---
title: Analytics How-tos
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
## Overview

This section provides more insights into how you can maximize the benefits of analytics and user retention for your app. 

# Track Analytics

Following are how-tos on tracking certain analytics related to UTM and revenue.

## Track UTM Parameters

To track UTM parameters, perform the following steps:

1. From the dashboard, navigate to *Segments* > *Find People*.
2. Enter the search criteria and click **View details**. 
3. Open the sample profile and scroll down to the *Profile* tab. 

This section displays all details, including:

* UTM source
* UTM medium
* UTM campaign

<Image title="UTM_parameter_tracking.png" alt={876} className="border" width="80%" border={true} src="https://files.readme.io/09f6815-UTM_parameter_tracking.png" />

## Check the Revenue Amount Generated in a Day after Sending a Push Notification

The revenue for each campaign is already available on the *Campaign Stats* page. However, to view the revenue for all campaigns, perform the following steps:

1. From the dashboard, navigate to *Analytics* > *Funnels*.
2. Select *STEP 1 - Push Impressions*.
3. Click **+ Filter by**.
4. Select *wzrk\_pid* with *contains* as the operator, then enter the campaign ID in the text field.
5. Select *STEP 2 - Charged*.
6. Check that the *Funnel conversion time* is set to one day. 

![1440](https://files.readme.io/b1a86cf-funnel_criteria_-_charged.png "funnel criteria - charged.png")

7. Click **View funnel**. The funnel results display. 

![1155](https://files.readme.io/cc85f8a-funnels_create_segment.png "funnels_create_segment.png")

This funnel displays users that have charged within 24 hours of getting an impression which are actionable funnels. You can click the funnel to save a segment from it, and then, you can analyze this saved segment in the [Revenue View](doc:revenue-view).

### View Revenue 

To view the revenue, perform the following steps:

1. From the dashboard, navigate to *Boards* > *Revenue*.
2. Select your segment from the *For segments* list.

<Image title="funnels_revenue_board.png" alt={1174} className="border" width="80%" border={true} src="https://files.readme.io/e746cfa-funnels_revenue_board.png" />

# Uninstalled Apps

Following are how-tos on tracking certain analytics related to uninstalled apps.

## Find the Installation Date of a User That Uninstalled the App

You have two ways to find this information:

* Through the *Profile* page, to view the user's actions, perform the following steps: 
  1. From the dashboard, navigate *Segments* > *Find People*. 
  2. Search for users who uninstalled the app. 
  3. Scroll down to the *Sample People* section and open any profile. 
  4. Check the *Initially acquired from* and the *Last session* sections.

![1156](https://files.readme.io/d466297-uninstall_date.png "uninstall_date.png")

You can also click the *Activity* tab to view the user activity. 

![1178](https://files.readme.io/a2eb8c2-uninstall_activity.png "uninstall_activity.png")

* Through an API, you can use the [Get Profile](https://developer.clevertap.com/docs/get-events-api) API to get a list of all events for *First time* and *Last time* that a user was on the app.

## Find Users That Uninstalled after Receiving a Push Notification from Clevertap 

To find these users, perform the following steps:

1. From the dashboard, navigate to *Analytics* > *Funnels*. 
2. Select *STEP 1 - Push Impressions*.
3. Click **+ Filter by**.
4. Select *wzrk\_pid* with *contains* as the operator, then enter the campaign ID in the text field.
5. Select *STEP 2 - App uninstalled*.
6. Click **View funnel**.

![1405](https://files.readme.io/30dc31b-funnel_criteria.png "funnel criteria.png")

7. Click the *Frequency* tab to view the number of times the event (App uninstall) was performed after sending a push notification. 

![504](https://files.readme.io/5eed296-funnel2.png "funnel2.png")

# User Activity Analytics

Following are how-tos on tracking certain analytics related to user activities.

## Check If the User Was Active Some Days of the Week

In this scenario, you want to find out if users were active for three days from the past seven days (or past week). These active users can be users that have launched the app at least twice. To find this user, perform the following steps:

1. From the dashboard, navigate to *Analytics* > *Cohorts* > *Advanced Options*. The *Cohorts* page displays. 
2. Select *Retention modes* > *Power User*.
3. Click **View Cohorts**.

![1197](https://files.readme.io/506ade8-Cohorts_Power_user.png "Cohorts_Power_user.png")

The cohort results display the active users for a particular number of days.

<Image title="Cohorts_Power_user_results.png" alt={1197} className="border" width="80%" border={true} src="https://files.readme.io/cac31e8-Cohorts_Power_user_results.png" />

# Identify the Time Period When Most Users Open an Email

To identify this time period, perform the following steps:

1. From the dashboard, navigate to *Analytics > Pivots*. 
2. Create a query.
3. Click **Calculate**.

<Image title="Pivots_query.png" alt={1497} className="border" border={true} src="https://files.readme.io/33ff3e5-Pivots_query.png" />

The result displays the number of times that the email was opened per hour and week of the day. 

The following results show that the maximum number of times that the email was opened was between 3:00 PM to 4:00 PM.

<Image title="Pivots_results.png" alt={1497} className="border" border={true} src="https://files.readme.io/0712878-Pivots_results.png" />

# Determine the Number of Users That Have Installed the App but Did Not Make a Purchase

To analyze the funnel drop-off, perform the following steps:

1. From the dashboard, navigate to *Analytics* > *Funnels*. 
2. Select *STEP 1 - App Installed*.
3. Select *STEP 2 - Charged*.
4. Click **View funnel**. The funnel displays. 

In the following example, there are 28 users who performed the *App Installed* event. From these users, 14 users performed the *Charged* event (displayed in the blue area). The gray area is the drop-off users that did not perform the *Charged* event.

<Image title="funnel_dropoff_query_results.png" alt={1158} className="border" width="80%" border={true} src="https://files.readme.io/439b852-funnel_dropoff_query_results.png" />

These funnels are actionable. Click the funnels to create a campaign to target these drop-off users and send them a nudge, or save the users in a segment for future reference.

![1164](https://files.readme.io/9c3a86b-funnel_dropoff_query_results_click.png "funnel_dropoff_query_results_click.png")
