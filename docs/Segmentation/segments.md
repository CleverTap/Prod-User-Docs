---
title: Intro to Segments
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
# Overview

A segment in CleverTap is a group of users whose actions taken, actions not taken, or user profile properties match a set of criteria you’ve defined.

For example, a segment can be users who launched the app for the first time in the past 30 days. A more complex segment could be users who live in New York, were acquired via a Facebook campaign in April, transacted three or more times in May and June, and have not transacted in the last two weeks.

Once you’ve identified segments of interest, you can save and then target them with any type of messaging campaign. You can also trend segments over time to understand how a segment behaves in response to your marketing initiatives. 

The entire CleverTap dashboard can be filtered by any segment you create including any of our analytics features.

# Types of Segments

There are two types of behavioral segments in CleverTap: Past Behavior segments and Live User segments.

## Past Behavior Segments

Past Behavior segments let you group users based on what they have done in the past. 

You can group users based on a single activity (i.e. all my users who App Launched in the past 30 days) to complex combinations of actions, inactions, and user properties.

## Live User Segments

While Past Behavior segments let you evaluate users based on historic criteria, Live User segments let you track what is happening in your app right now.

When you define a set of behaviors of interest, CleverTap will monitor for these behaviors as they happen in your app, and immediately add a user to a segment the moment their behavior matches your criteria.

You can create Live User segments for a single activity (booked a movie ticket), inaction (did not buy a movie ticket in a certain time), off of date/time properties of events, or website related actions such as page visit, count or referrer.

## System User Segments

These are system defined user segments that are available for your use. 
  * **All Users**: This user segment contains all the users available for your account.
  * **Test Users**: This user segment contains users that you can test for your campaign response. A Campaign or Journey can now be tested on this Test Users segment before it is sent to an actual segment. The Test User segment is available by default for engagement and UI experiences. 
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

To create new segments, go to Segments under the Segmentation tab on the dashboard.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d99e397-Screenshot_2020-06-08_at_12.12.29_PM.png",
        "Screenshot 2020-06-08 at 12.12.29 PM.png",
        2880,
        1626,
        "#f6f7f8"
      ],
      "border": true
    }
  ]
}
[/block]
Then, click the **+ Segment** button.

The main segment creation page, you will be presented with a list of options of types of Past Behavior and Live User segments you can create. Select any one, based on the segment you would like to set up.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c3a09b1-Segments_Select_Segment.gif",
        "Segments_Select_Segment.gif",
        1218,
        658,
        "#fcfcfd"
      ],
      "border": true
    }
  ]
}
[/block]
Past Behavior segments can be based on:
  * Past user actions, e.g., users who added a product to the cart in the past 30 days
  * Past user action/inaction combination, e.g., users who added a product to the cart but didn’t purchase in the last 30 days
  * Past user action/inaction combination along with common user properties, e.g., platinum-level users who added a product to the cart but didn’t purchase in the last 30 days

Live User segments can add users to the segment as soon as users qualify based upon:
  * Single action, e.g., users who have added a product to the cart
  * Inaction within time, e.g., users who have added a product to the cart but did not purchase within 10 minutes of adding product to cart
  * On a date/time, for example, users whose appointment date is 5 days from today
  * Page visit, for example, users who have visited a certain URL on your website
 * Referrer entry, for example, users who have visited your website via a certain external referrer URL
 * Page count, for example, users who have visited a certain number of pages on your website

# Segment List Page

The Segments list page shows all existing segments available for you. You can choose to do various tasks with these listed segments. 
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
## Create Live User Segments

To create a live segment with CleverTap, simply choose any of the options underneath “Live user segments” from the main segment creation page.

For instance, in the current example, we will create an “Inaction within time” segment for which users will qualify in realtime, as soon as they add a product to cart but do not purchase the product within 10 minutes (the golden window within which most users transact on our iOS and Android app platforms).

Select the “Inaction within time” box, which displays the following page where you can set up the segment as follows.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c9213f-Segments_Inaction_with_Time.png",
        "Segments_Inaction_with_Time.png",
        1197,
        439,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
We can choose to check the “Filter this stream based on these users’ past behavior/user properties” checkbox to apply past action/inaction/common user property filters.

The next step would be to click “Save segment,” name the segment, and then see it show up in the main “Segments” menu by its name, which in this case is “Added to cart but no charge 10 mins.” 
[block:callout]
{
  "type": "success",
  "title": "Segment Naming Best Practices",
  "body": "Convey the core meaning of the segment while keeping the name brief."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ccf346b-Segments_Created_Segment.png",
        "Segments_Created_Segment.png",
        788,
        505,
        "#f4f6f6"
      ]
    }
  ]
}
[/block]
### View Live User Segment Report

The top portion of the live user segment report consists of a way to first “Show segment definition” in order to understand its underlying query. 

There are also two graphs: 
  * One on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation.
  * One on the right-hand side showing the real-time rate at which users are qualifying for the segment (vs all user activity on your app/website). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2b9ceec-Segment_Live_Segment_Report.gif",
        "Segment_Live_Segment_Report.gif",
        1218,
        658,
        "#faf9fa"
      ]
    }
  ]
}
[/block]
The lower portion of the live user segment report consists of a list of sample users trickling into your segment in real-time on the right-hand side. 

It also shows the reachability percentages for these users within each messaging channel on the left-hand side. 

The lower-most part of the report shows you how to “do more with this segment” by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

## Create Past Behavior Segments

To create a Past Behavior segment with CleverTap, choose any of the options underneath “Past behavior user segments” from the main segment creation page.

For example, we will create an “Action” based segment where users will qualify if they have applied a payment offer at least one time in the past 30 days.

So, we’ll select the box “Action,” and then be taken into the following page where we can set up our segment as follows.
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
The next step would be to click “Save segment,” name the segment, and then see it show up in the main “Segments” menu by its name, which in our case, is “Frequent Buyers.”
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1a1ce2-Segments_PSB_Created_Segment.png",
        "Segments_PSB_Created_Segment.png",
        800,
        494,
        "#f3f5f6"
      ],
      "border": true
    }
  ]
}
[/block]
### View a Past Behavior Segment Report

The top portion of the past behavior user segment report consists of a way to first “Show segment definition” in order to understand its underlying query. There are graphs on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation. The list on the right-hand side shows the sample list of users who qualified for the segment on this day.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/77138b9-Segment_PSB_Report.gif",
        "Segment_PSB_Report.gif",
        1218,
        658,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
The lower portion of the live user segment report consists of reachability percentages for these users within each messaging channel. The lower-most part of the report shows you how to “do more with this segment” by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

# View Analytics Filtered by Segment

Under the “Do more with this segment” section, you have the option to view an analytics report. This will be for the chosen segment alone and not your entire user base. 

Analysis dashboard views have the following filter at the top to enable this.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/321ce60-Screenshot_2020-06-08_at_1.18.47_PM.png",
        "Screenshot 2020-06-08 at 1.18.47 PM.png",
        2878,
        1628,
        "#fafafa"
      ],
      "border": true
    }
  ]
}
[/block]
Realtime dashboard views such as the Today dashboard only enables filtering by Live User segments. Analytics based on past behavior such as Mobile App, Revenue, Funnels, Cohorts, Trends, and Events will only enable filtering their stats by Past Behavior segments.

# Create Campaigns for a Chosen Segment

Under the “Do more with this segment” section, under “Engage,” you have the option to create a campaign to message a specific segment.

This immediately takes you the messaging channel with your segment criteria pre-populated in the target.
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
# Video Tutorial
[block:html]
{
  "html": "<div>\n  <iframe width=\"560\" height=\"315\" src=\"https://www.youtube.com/embed/JJzfuZZ9zGQ?rel=0&amp;showinfo=0\" frameborder=\"0\" allow=\"autoplay; encrypted-media\" allowfullscreen></iframe>\n</div>\n\n"
}
[/block]