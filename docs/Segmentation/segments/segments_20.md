---
title: Segments_2.0
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

A segment in CleverTap is a group of users whose actions performed, actions not performed, or user profile properties match a set of defined criteria. For example, a segment can be users who launched the app for the first time in the past 30 days. A more complex segment could be users who live in New York, were acquired via a Facebook campaign in April, transacted three or more times in May and June, and have not transacted in the past two weeks.

After you have identified segments of interest, you can save and then target them with any type of messaging campaign. You can also trend segments over time to understand how a segment behaves in response to your marketing initiatives. The entire CleverTap dashboard can be filtered by any segment you create, including any of our analytics features.

# Types of Segments

There are two types of behavioral segments in CleverTap: *Past behavior* segments and *Live* segments.

## Past Behavior Segments

Past behavior segments are users grouped by their actions in the past. 

You can group users based on a single activity to complex combinations of actions, inactions, and user properties.
[block:callout]
{
  "type": "success",
  "body": "An example would be to segment by all my users who launched the app in the past 30 days.",
  "title": "Past Behavior Segments Example"
}
[/block]
## Live User Segments

While past behavior segments let you evaluate users based on historic criteria, live user segments let you track what is happening in your app right now.

When you define a set of behaviors of interest, CleverTap monitors for these behaviors as they happen in your app and immediately adds a user to a segment the moment their behavior matches your action criteria.

You can create live user segments for a single activity (booked a movie ticket), inaction (did not buy a movie ticket in a certain time), off of date/time properties of events, or website-related actions, such as page visit, count, or referrer.

## System User Segments

The following are system-defined user segments that are available for your use: 
  * All Users: This user segment contains all the users available to your account.
  * Test Users: This user segment contains the users who you can test for your campaign response. A campaign or journey can now be tested on this *Test Users* segment before it is sent to an actual segment. The *Test User* segment is available by default for engagement and UI experiences. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb9b8b9-1a9589c-Segment_System.png",
        "1a9589c-Segment_System.png",
        1208,
        672,
        "#f0f4f8"
      ],
      "border": true
    }
  ]
}
[/block]
# Create Segments

To create a new segment, , perform the following steps:
1. From the dashboard, navigate to *Segments* > *Segments*.
2. Click **+ Segment**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/471192b-3_main_section.png",
        "3 main section.png",
        1396,
        733,
        "#f8f9f9"
      ],
      "border": true
    }
  ]
}
[/block]
3. The main segment creation page displays a list of options for types of past behavior and live user segments. Select an option based on the required segment.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c000bf0-select_an_option.png",
        "select an option.png",
        1199,
        664,
        "#f9f9f9"
      ],
      "border": true
    }
  ]
}
[/block]
Past behavior segments can be based on:
  * Past user actions (for example, users who added a product to the cart in the past 30 days)
  * Past user action/inaction combination (for example, users who added a product to the cart but did not purchase in the last 30 days)
  * Past user action/inaction combination along with common user properties (for example, platinum-level users who added a product to the cart but did not purchase in the last 30 days)

Live user segments can add users to the segment as soon as users qualify based on the following:
  * Single action (for example, users who have added a product to the cart)
  * Inaction within time (for example, users who have added a product to the cart but did not purchase within 10 minutes of adding product to the cart)
  * On a date/time (for example, users who have an appointment five days from today)
  * Page visit (for example, users who have visited a certain URL on your website)
 * Referrer entry (for example, users who have visited your website via a certain external referrer URL)
 * Page count (for example, users who have visited a certain number of pages on your website)

# Segment List Page

The *Segments* list page shows all existing segments available for you. You can choose to do various tasks with these listed segments. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e1fcdb-Segments_all_operations.png",
        "Segments_all_operations.png",
        1221,
        732,
        "#ecebe8"
      ],
      "caption": "Segment list page"
    }
  ]
}
[/block]
# Create Live User Segments
Live user segments can add users to the segment as soon as users qualify based on the following:
  * Single action: users who have added a product to the cart.
  * Inaction within time: users who have added a product to the cart but did not purchase within 10 minutes of adding a product to the cart.
  * On a date/time: users who have an appointment five days from today.
  * Page visit: users who have visited a certain URL on your website.
     * Referrer entry: users who have visited your website via a certain external referrer URL.
     * Page count: users who have visited a certain number of pages on your website.

In this example, we can create an *Inaction within time* segment for which users will qualify in real-time as soon as they add a product to cart but do not purchase the product within 10 minutes.
[block:callout]
{
  "type": "info",
  "body": "The golden window within which most users transact on our iOS and Android app platforms is within 10 minutes.",
  "title": "Golden Window for Mobile Transactions"
}
[/block]
To create a live segment with CleverTap, perform the following steps:

1. From the dashboard, navigate to *Segments* > *Segments*.
2. Click **+ Segment**.
3. Under *Live user segments*, select the *Inaction within time* box.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db039c0-1_live_user_segment_selection.png",
        "1 live user segment selection.png",
        1207,
        741,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]
5. Select the appropriate properties for your live user segment. 

You may choose to select the *Filter on past user behavior and common properties* checkbox to apply past action, inaction, or common user property filters.
6. Click **Save segment**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/033db1c-2_set_up_Live_user_segment_-_Inaction_within_time.png",
        "2 set up Live user segment - Inaction within time.png",
        1403,
        609,
        "#fafafc"
      ]
    }
  ]
}
[/block]
7. Name the segment, then click **Save**.
[block:callout]
{
  "type": "info",
  "title": "Segment Naming Best Practices",
  "body": "Convey the core meaning of the segment while keeping the name brief."
}
[/block]
8. You can now see your new segment in the main section as *Added to cart but no charge within 10 minutes*.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d546264-3_main_section.png",
        "3 main section.png",
        1396,
        733,
        "#f8f9f9"
      ]
    }
  ]
}
[/block]
##View Live User Segment Reports

To view a live user segment report, perform the following steps:
1. From the dashboard, navigate to *Segments* > *Segments*.
2. Search for the segment you are looking for, then click on it.  

At the top of the report, you can click *View segment definition* to understand more about the underlying query. 

The two graphs describe the following:
  * The left-hand side shows the plot of the number of users who qualified for the segment going forward from the first complete day after creating the segment.
  * The right-hand side shows the real-time rate at which users are qualifying for the segment vs. all user activity on your app/website. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/821380f-4a_top_report.png",
        "4a top report.png",
        1272,
        692,
        "#faf9fa"
      ]
    }
  ]
}
[/block]
* The lower portion of the live user segment report consists of a list of sample users trickling into your segment in real-time on the right-hand side. It also shows the reachability percentages for these users within each messaging channel on the left-hand side.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/25d5194-4b_middle_report.png",
        "4b middle report.png",
        1269,
        681,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
* The lower-most part of the report shows how to do more with this segment by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/44308a1-4c_bottom_report.png",
        "4c bottom report.png",
        1266,
        679,
        "#f7f6f6"
      ]
    }
  ]
}
[/block]
# Create Past Behavior Segments

To create a past behavior segment, perform the following steps: 
1. From the dashboard, navigate to *Segments* > *Segments*.
2. Select any of the options underneath *Past behavior user segments* from the main segment creation page.

For example, we can create an action-based segment where users will qualify if they have applied a payment offer at least one time in the past 30 days.

3. Select the box *Actions* which takes you to the segment setup page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f6d353-Segments_PSB_Create_New.png",
        "Segments_PSB_Create_New.png",
        1228,
        682,
        "#fbfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
4. Click **Save segment** and name the segment. You can now view your new segment on the overview page.

## View a Past Behavior Segment Report

The top portion of the past behavior user segment report consists of a way to first view the segment definition to understand its underlying query. There are graphs on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation. The list on the right-hand side shows the sample list of users who qualified for the segment on this day.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1225063-report.png",
        "report.png",
        1204,
        649,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
The lower portion of the live user segment report consists of reachability percentages for these users within each messaging channel. The lower-most part of the report shows you how to do more with this segment by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8f416de-lower_report.png",
        "lower report.png",
        1206,
        647,
        "#f6f7f9"
      ]
    }
  ]
}
[/block]

# View Analytics Filtered by Segment

Under the *Do more with this segment section,* you have the option to view an analytics report. This is for the chosen segment alone and not your entire user base. 

Analysis dashboard views have the following filter at the top to enable this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a8df120-321ce60-Screenshot_2020-06-08_at_1.18.47_PM.png",
        "321ce60-Screenshot_2020-06-08_at_1.18.47_PM.png",
        2310,
        1552,
        "#fbfbfb"
      ],
      "border": true
    }
  ]
}
[/block]
Real-time dashboard views such as, the *Today* dashboard only enables filtering by live user segments. Analytics based on past behavior such as mobile app, revenue, funnels, cohorts, trends, and events will only enable filtering their stats by past behavior segments.

# Create Campaigns for a Chosen Segment

Under the *Do more with this segment* section, under *Engage*, you have the option to create a campaign to message a specific segment.

This immediately takes you to the messaging channel with your segment criteria pre-populated in the target.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3c7905e-Segments_Do_More_Campaign.png",
        "Segments_Do_More_Campaign.png",
        617,
        292,
        "#fcfcfd"
      ],
      "border": true,
      "caption": ""
    }
  ]
}
[/block]
#Include and Exclude Segments

You can simplify complex queries by including or excluding the existing user segments. Create segments with complex conditions once and then reuse them in different scenarios. 

You can create powerful segmentation that is valid for a variety of scenarios. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30d054b-0fd3c96-Find_people_include_exclude_segments.png",
        "0fd3c96-Find_people_include_exclude_segments.png",
        715,
        382,
        "#f6f7fb"
      ]
    }
  ]
}
[/block]
##Exclude Segments

There may be instances when you want to exclude some users based on specific criteria. 

For example, you want to offer discounts to all the users who have expressed interest by adding the product to the cart in the past 30 days; however, you want to save your engagement dollars by excluding the power users. 
The parameters for these power users can be the following:
  * Users who have charged three times in the past three months, and 
  * Users who have launched the app 15 times in the past month, and
  * Users who rated a product 10 times in the past year

Now, you can create a segment with these criteria called *Power Users* and use it every time rather than creating a complex query each time. You can save all these parameters in a segment called *Power Users* and exclude them from the discount message. 

The following is a campaign query for an e-commerce app that excludes the *Power Users* segment.

<<@DK: NEED A NEW IMAGE HERE>>


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2fb7f6a-exclude_segments_campaign.png",
        "exclude_segments_campaign.png",
        1050,
        1506,
        "#fafaf9"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
##Include Segments

There may be instances when you want to include some users based on specific criteria. 

Consider the example of a ride-hailing app. You want to nudge your users to enroll for a monthly pass as soon as they open the app. The parameters for these users can be the following:
  * The users must be power users, and
  * The users have booked more than five rides in a month, and
  * They belong to select cities in the country
 
Now, you can create a segment with these criteria called *Power Users* and using it repeatedly rather than creating a complex query each time. 

The following is a campaign query for a ride-hailing app that includes the *Power Users* segment.

<<@DK: NEED A NEW IMAGE HERE>>
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f9f341a-include_segments_campaign.png",
        "include_segments_campaign.png",
        1067,
        1270,
        "#fbfbfc"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "* You can include and exclude segments in the same query. It is considered as an *AND* condition between the two segments.\n  * The include and exclude segments are currently unavailable for bulletins and A/B Testing.\n  * The segments available for including or excluding users can only be of the type [PBS](https://docs.clevertap.com/docs/segments#section-past-behavior-segments) segment.",
  "title": "Include and Exclude Segments"
}
[/block]
# Additional AND By Behavior Filters
*AND By behavior* filters provide customers the ability to segment users based on the count, average, or total sum of a property value.

### Count
The count filter allows customers to filter users by event count. The query finds all users who performed a *Charged* event greater than 5 times in the past 30 days. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0678593-2020-11-24_17-51-01_Count.png",
        "2020-11-24_17-51-01_Count.png",
        1192,
        378,
        "#fafbfd"
      ]
    }
  ]
}
[/block]
### Average of Property Filter
The *Average of property* filter allows customers to filter users by the average of a chosen event property. The query finds all users who performed a *Charged* event such that the average *Revenue* event property per event is greater than $10. 

The *Average of property* filter allows averaging the value of the selected event property. For example, you can find out the average revenue earned from all users who performed purchases worth $10 or less. Let us assume that 5 users charged for each for $3, $5, $7, $2, and $8. The average value of all the purchases lower than $10 is ($ 3+ 5 +7+2+8)/5 events = 25/5= $5 per event. 

Let us assume that the value for 2 charged events is missing. The charged event values received are $3, $5, and $7. The value of the missing events will be considered as 0. The average of property is now ($3 + 5 +7 +0 +0)/5 events = 15/5 =$3 per event. 

If you want to exclude all the events that do not have event properties, you can select the property that exists a condition in the *Filter by* section.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09c3239-2020-11-24_17-52-22_Average_of_property.png",
        "2020-11-24_17-52-22_Average of property.png",
        1192,
        382,
        "#fafbfd"
      ]
    }
  ]
}
[/block]
### Total Sum of Property
The *Total sum of property* filter allows customers to filter users by the sum of a chosen event property. The query finds all users who performed a *Charged* event such that the *Revenue* event property is greater than $10.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d973ab4-2020-11-24_17-53-50_Total_sum_of_property.png",
        "2020-11-24_17-53-50_Total sum of property.png",
        1194,
        382,
        "#fafbfd"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Include Users Who Did Not Do the Event",
  "body": "If the query is to find people who performed the charged event fewer than five times, by default, the users who have not performed the charged event are not included in the result set. Only the users who did the charged event but did it fewer than five times are included; however, if the checkbox for *Include users who didn’t do the event* is selected, those users are also included in the result set. The same is true for sum and average."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db44a26-2020-11-24_17-56-46_Checkbox_message.png",
        "2020-11-24_17-56-46_Checkbox message.png",
        1187,
        412,
        "#fdfdfd"
      ]
    }
  ]
}
[/block]