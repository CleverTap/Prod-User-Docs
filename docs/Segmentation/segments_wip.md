---
title: Segments_WIP
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
# Overview

A segment in CleverTap is a group of users whose actions taken, actions not taken, or user profile properties match a set of criteria you’ve defined. For example, a segment can be users who launched the app for the first time in the past 30 days. A more complex segment could be users who live in New York, were acquired via a Facebook campaign in April, transacted three or more times in May and June, and have not transacted in the last two weeks.

Once you’ve identified segments of interest, you can save and then target them with any type of messaging campaign. You can also trend segments over time to understand how a segment behaves in response to your marketing initiatives. The entire CleverTap dashboard can be filtered by any segment you create including any of our analytics features.

# Types of Segments

There are two types of behavioral segments in CleverTap: *Past behavior* segments and *Live* segments.

## Past Behavior Segments

Past behavior segments let you group users based on what they have done in the past. 

You can group users based on a single activity (i.e., all my users who App Launched in the past 30 days) to complex combinations of actions, inactions, and user properties.

## Live User Segments

While past behavior segments let you evaluate users based on historic criteria, live user segments let you track what is happening in your app right now.

When you define a set of behaviors of interest, CleverTap monitors for these behaviors as they happen in your app, and immediately add a user to a segment the moment their behavior matches your criteria.

You can create live user segments for a single activity (booked a movie ticket), inaction (did not buy a movie ticket in a certain time), off of date/time properties of events, or website related actions such as page visit, count, or referrer.

## System User Segments

The following are system-defined user segments that are available for your use: 

* **All Users**: This user segment contains all the users available for your account.
* **Test Users**: This user segment contains users that you can test for your campaign response. A campaign or journey can now be tested on this Test Users segment before it is sent to an actual segment. The Test User segment is available by default for engagement and UI experiences. 

<Image title="1a9589c-Segment_System.png" alt={1208} className="border" border={true} src="https://files.readme.io/eb9b8b9-1a9589c-Segment_System.png" />

# Create Segments

To create new segments, go to *Segments* under the *Segmentation* tab on the dashboard.

<Image title="Screenshot 2020-06-08 at 12.12.29 PM.png" alt={2880} className="border" border={true} src="https://files.readme.io/d99e397-Screenshot_2020-06-08_at_12.12.29_PM.png" />

Click the **+ Segment** button.

The main segment creation page displays with a list of options of types of past behavior and live user segments you can create. Select any one based on the segment you want to set up.

<Image title="Segments_Select_Segment.gif" alt={1218} className="border" border={true} src="https://files.readme.io/c3a09b1-Segments_Select_Segment.gif" />

Past Behavior segments can be based on:

* Past user actions  (e.g., users who added a product to the cart in the past 30 days)
* Past user action/inaction combination (e.g., users who added a product to the cart but didn’t purchase in the last 30 days)
* Past user action/inaction combination along with common user properties (e.g., platinum-level users who added a product to the cart but didn’t purchase in the last 30 days)

Live User segments can add users to the segment as soon as users qualify based upon:

* Single action (e.g., users who have added a product to the cart)
* Inaction within time (e.g., users who have added a product to the cart but did not purchase within 10 minutes of adding product to cart)
* On a date/time, (e.g., users whose appointment date is five days from today)
* Page visit (e.g., users who have visited a certain URL on your website)
* Referrer entry (e.g., users who have visited your website via a certain external referrer URL)
* Page count (e.g., users who have visited a certain number of pages on your website)

# Segment List Page

The *Segments* list page shows all existing segments available for you. You can choose to do various tasks with these listed segments. 

<Image title="Segments_all_operations.png" alt={1221} src="https://files.readme.io/4e1fcdb-Segments_all_operations.png">
  Segment list page
</Image>

## Create Live User Segments

To create a live segment with CleverTap, choose any of the options underneath *Live user segments* from the main segment creation page.

For instance, in the current example, we will create an *Inaction within time* segment for which users will qualify in realtime, as soon as they add a product to cart but do not purchase the product within 10 minutes (the golden window within which most users transact on our iOS and Android app platforms).

Select the *Inaction within time* box, which displays the following page where you can set up the segment as follows.

<Image title="Segments_Inaction_with_Time.png" alt={1197} className="border" border={true} src="https://files.readme.io/2c9213f-Segments_Inaction_with_Time.png" />

We can choose to check the “Filter this stream based on these users’ past behavior/user properties” checkbox to apply past action/inaction/common user property filters.

The next step would be to click “Save segment,” name the segment, and then see it show up in the main “Segments” menu by its name, which in this case is “Added to cart but no charge 10 mins.” 

> 👍 Segment Naming Best Practices
>
> Convey the core meaning of the segment while keeping the name brief.

![788](https://files.readme.io/ccf346b-Segments_Created_Segment.png "Segments_Created_Segment.png")

### View Live User Segment Report

The top portion of the live user segment report consists of a way to first “Show segment definition” in order to understand its underlying query. 

There are also two graphs: 

* One on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation.
* One on the right-hand side showing the real-time rate at which users are qualifying for the segment (vs all user activity on your app/website). 

![1218](https://files.readme.io/2b9ceec-Segment_Live_Segment_Report.gif "Segment_Live_Segment_Report.gif")

The lower portion of the live user segment report consists of a list of sample users trickling into your segment in real-time on the right-hand side. 

It also shows the reachability percentages for these users within each messaging channel on the left-hand side. 

The lower-most part of the report shows you how to “do more with this segment” by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

## Create Past Behavior Segments

To create a Past Behavior segment with CleverTap, choose any of the options underneath “Past behavior user segments” from the main segment creation page.

For example, we will create an “Action” based segment where users will qualify if they have applied a payment offer at least one time in the past 30 days.

So, we’ll select the box “Action,” and then be taken into the following page where we can set up our segment as follows.

<Image title="Segments_PSB_Create_New.png" alt={1228} className="border" border={true} src="https://files.readme.io/6f6d353-Segments_PSB_Create_New.png" />

The next step would be to click “Save segment,” name the segment, and then see it show up in the main “Segments” menu by its name, which in our case, is “Frequent Buyers.”

<Image title="Segments_PSB_Created_Segment.png" alt={800} className="border" border={true} src="https://files.readme.io/f1a1ce2-Segments_PSB_Created_Segment.png" />

### View a Past Behavior Segment Report

The top portion of the past behavior user segment report consists of a way to first “Show segment definition” in order to understand its underlying query. There are graphs on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation. The list on the right-hand side shows the sample list of users who qualified for the segment on this day.

<Image title="Segment_PSB_Report.gif" alt={1218} className="border" border={true} src="https://files.readme.io/77138b9-Segment_PSB_Report.gif" />

The lower portion of the live user segment report consists of reachability percentages for these users within each messaging channel. The lower-most part of the report shows you how to “do more with this segment” by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

# View Analytics Filtered by Segment

Under the *Do more with this segment section,* you have the option to view an analytics report. This will be for the chosen segment alone and not your entire user base. 

Analysis dashboard views have the following filter at the top to enable this.

<Image title="Screenshot 2020-06-08 at 1.18.47 PM.png" alt={2878} className="border" border={true} src="https://files.readme.io/321ce60-Screenshot_2020-06-08_at_1.18.47_PM.png" />

Realtime dashboard views such as the Today dashboard only enables filtering by Live User segments. Analytics based on past behavior such as Mobile App, Revenue, Funnels, Cohorts, Trends, and Events will only enable filtering their stats by Past Behavior segments.

# Create Campaigns for a Chosen Segment

Under the “Do more with this segment” section, under “Engage,” you have the option to create a campaign to message a specific segment.

This immediately takes you to the messaging channel with your segment criteria pre-populated in the target.

<Image title="Segments_Do_More_Campaign.png" alt={617} className="border" border={true} src="https://files.readme.io/3c7905e-Segments_Do_More_Campaign.png" />

# Include/Exclude Segments

You can simplify complex queries by including or excluding the existing user segments. Create segments with complex conditions once and then reuse them in different scenarios. 

You can create powerful segmentation that is valid for a variety of scenarios. 

![998](https://files.readme.io/0fd3c96-Find_people_include_exclude_segments.png "Find_people_include_exclude_segments.png")

## Exclude Segments

There may be instances when you want to exclude some users based on specific criteria. 

For example, you want to offer discounts to all the users who have expressed interest by adding the product to the cart in the past 30 days; however, you want to save your engagement dollars by excluding the power users.\
The parameters for these power users can be the following:

* Users who have charged three times in the past three months, and 
* Users who have launched the app 15 times in the past month, and
* Users who rated a product 10 times in the past year

Now you can create a segment with these criteria called *Power Users* and use it every time rather than creating a complex query each time. You can save all these parameters in a segment called *Power Users* and exclude them from the discount message. 

The following is a campaign query for an e-commerce app that excludes the *Power Users* segment.

<Image title="exclude_segments_campaign.png" alt={1050} className="border" width="100%" border={true} src="https://files.readme.io/2fb7f6a-exclude_segments_campaign.png" />

## Include Segments

There may be instances when you want to include some users based on specific criteria. 

Consider the example of a ride-hailing app. You want to nudge your users to enroll for a monthly pass as soon as they open the app. The parameters for these users can be the following:

* The users must be power users, and
* The users have booked more than five rides in a month, and
* They belong to select cities in the country

Now you can create a segment with these criteria called "Power Users" and using it repeatedly rather than creating a complex query each time. 

The following is a campaign query for a ride-hailing app that includes the "Power Users" segment.

<Image title="include_segments_campaign.png" alt={1067} className="border" width="100%" border={true} src="https://files.readme.io/f9f341a-include_segments_campaign.png" />

> 📘 Include and Exclude Segments
>
> * You can include and exclude segments in the same query. It is considered as an AND condition between the two segments.
> * The include and exclude segments are currently unavailable for bulletins and A/B Testing.
> * The segments available for including or excluding users can only be of the type [PBS](https://docs.clevertap.com/docs/segments#section-past-behavior-segments) segment. 

# Additional AND By Behavior Filters

*AND By behavior* filters provide customers the ability to segment users based on the count, average, or total sum of a property value.

### Count

The *Count* filter allows customers to filter users by event count. The query finds all users who performed a *Charged* event greater than five (5) times in the past 30 days. 

### Total Sum of Property

The *Total sum of property* filter allows customers to filter users by the sum of a chosen event property. The query finds all users who performed a *Charged* event such that the *Revenue* event property is greater than $10.

### Average of Property Filter

The *Average of property* filter allows customers to filter users by the average of a chosen event property. The query finds all users who performed a *Charged* event such that the average *Revenue* event property per event is greater than $10. 

> 📘 Include users who did not do the event
>
> If the query is to find people who performed the charged event fewer than five times, by default, the users who have not performed the charged event are not included in the result set. Only the users who did the charged event but did it fewer than five times are included; however, if the checkbox for *Include users who didn’t do the event* is selected, those users are also included in the result set. The same is true for sum and average.
