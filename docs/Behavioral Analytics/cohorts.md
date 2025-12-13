---
title: Cohorts
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

Cohort analysis is a way of grouping users who are similar (based on who or what they have done), and tracking their behavior over time. 

Cohorts let you isolate a group of users who have performed a certain event, and determine how long it takes for them to come back and perform a second event.

Cohorts are a powerful way to understand how people are using your applications and are commonly used to measure user retention and churn. You can use cohort analysis to answer questions such as:
  * What is my 4th-week retention like for new users?
  * How many repeat buyers does my e-commerce application have?
  * How soon do new users uninstall my music application if they don't create playlists?

You can also use cohorts for more nuanced use-cases that involve different segments. One such use-case of cohorts is to validate hypotheses. For example, if you are a video application, you would have a hypothesis in mind “People return to watch videos in my applications because of the recommendations section of my application”. 

You can easily use cohorts to validate this hypothesis.

Your “First event” & “Return event” would both be “video watched”. As this would help answer - How many people who watched videos, came back to watch videos on my application. 

You will view this cohort with 2 segments of users. In the advanced filter, you will first view your Video watched → Video watched cohort for people who have used the recommendations feature, then you will compare it to people who haven’t used the recommendations feature.

# Creating a Cohort

To create a cohort, select your desired first event & its properties. This is the event that users must perform to qualify for your analysis. Select your return event and its properties. The users who have performed the first event must perform the return event to be considered for cohorts. ,
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/41d91ad-image1.png",
        "image1.png",
        903,
        281,
        "#cdcdce"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5c737fb-image3.png",
        "image3.png",
        905,
        281,
        "#cdcdce"
      ],
      "border": true
    }
  ]
}
[/block]

##Compare by user properties
While creating your cohort, you choose to compare your analysis by: 
  * Geography - user's last known country, region, and city.
  * Session details - UTM source/medium/campaign & session source/referrer for the “First event”.
  * Technographics - browser/device/OS.

##Compare by Segments

You can choose to compare your retention across different segments. For example, compare the retention for ‘Charged’ to ‘Charged’ event across the "All Users" segment and the “Frequent Buyers" segment. The differences in the retention trends could reveal a difference in the behavior of your users in each segment and hence result in an insight that could be invaluable. You can then dig deeper into buyer behavior. 

To compare retention across segments:

1. Go to Analytics>Cohorts.
2. Select the first and return event to analyze and view the retention cohort. 
3. Select the "Compare to another segment" box. Select a segment from the list or create an adhoc segment. For more information on segments, see Intro to Segments.
4. Click View Cohort.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75848cc-Cohorts_Compare_Segments_Search.png",
        "Cohorts_Compare_Segments_Search.png",
        1169,
        1333,
        "#f9f9fb"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
The results are displayed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9c4cf5-Cohorts_Compare_Segments_Search_Results.png",
        "Cohorts_Compare_Segments_Search_Results.png",
        1171,
        944,
        "#f9fafa"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "  * You can compare by a saved or an ad-hoc segment.\n  * You can compare a maximum of 5 segments\n  * You cannot simultaneously compare your retention by user property and segments.\n",
  "title": "Note"
}
[/block]
##Retention modes
CleverTap offers you multiple retention modes. You can use our retention modes to track user behavior and increase retention with additional insights into user behavior. You can group your users by behavior and track their usage over a timeline. You can also define a goal, compare your marketing strategy and get actionable insights. 

###Nth Day
This mode shows user actions on specific days. For example, a user reads the news on Week 2 but not on Week 1 or Week 3. If you view a cohort for 3 weeks, you will see the following:
[block:parameters]
{
  "data": {
    "h-0": "Week 0",
    "h-1": "Week 1",
    "h-2": "Week 2",
    "h-3": "Week 3",
    "h-4": "Day4",
    "0-0": "50%",
    "0-1": "0",
    "0-2": "75%",
    "0-3": "0"
  },
  "cols": 4,
  "rows": 1
}
[/block]
Notice the Week 0? This shows the first user action such as app install or app launch in Week 0. 

Let us assume another example where you want to engage users who have installed your news app. You have managed to convince them to use the app but you want to ensure that they are engaged.  Some of these users installed the app and have started reading the news regularly. However, some of these users may install the app and still not read the news. We need to identify the trend for such users because these users are a churn risk.  

We select the first user action as "app install" and the second action (return event) as "read news". 

The Week 0 cohort will tell you how many users installed your app in the past 3 weeks. You can then check the number of users that installed your app and then actually read the news.  The Nth day cohort will show you user behavior for 3 weeks after the users have installed the app.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f316676-Cohorts_retention_Nth_Chart.png",
        "Cohorts_retention_Nth_Chart.png",
        1215,
        631,
        "#fbfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
The table will show you the actual retention percentages. The Week 0 is when the user qualified for the cohort.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72f5afb-Cohots_retention_Nth_Table.png",
        "Cohots_retention_Nth_Table.png",
        1190,
        441,
        "#f6f9f8"
      ],
      "border": true
    }
  ]
}
[/block]
###Power User
Power users are the cornerstone of a company’s success. These are the users that are most engaged, the most likely to give great feedback, the most profitable in terms of customer lifetime value, and they contribute invaluable data to your business. These can be the users that play songs daily, or hail a ride every day, or read the news every hour. 

You can use this retention mode to analyze the frequency of their return and gain insight into their behavior and experience. 

For example, you want to see how many users play songs over a month. You can select the first event as "App launched". You can select the return event as "Song Listened". Select a 30 day period and then click the View cohort button to analyze user behavior over a month.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18bb013-cohorts_retention_power_user_selection.png",
        "cohorts_retention_power_user_selection.png",
        1236,
        710,
        "#f8f8fb"
      ],
      "border": true
    }
  ]
}
[/block]
An ideal power user curve is a smile curve that shows user engagement over a period. When more of your users return daily,  the smile will shift to the right. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/314e9aa-Cohots_retention_Power_user_Trend.png",
        "Cohots_retention_Power_user_Trend.png",
        1193,
        646,
        "#fbfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
The point at which the curve bends is the inflection point in user behavior. You can cross-reference your app features or offering to the curve and see what value it brings to your power users. 
[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "You can test your product features or offering with [Product Experiences](doc:product-experiences) and then come back and check the power user curve. This will give you a more comprehensive understanding of your user reactions before you roll them out to your most coveted users."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "* This feature is currently available in closed beta. In the meanwhile, you can check this feature in our demo account.\n\n* Creating a campaign or segment is not supported for this cohort."
}
[/block]
###Unbounded

An Unbounded retention cohort shows your user retention over a time period but more importantly, it measures if your users return after a given point in time. For example, you can find out if a user returns to the app after day 10. This retention is especially useful if your user engagement is spread out over a longer time period. For example, users who want to book vacations, or buy/renew insurance,  or credit their online wallet. These user actions do not have a fixed date for the return action. However, you do want to know when they perform an action (after a specified time period). Here, you can use the Unbounded retention mode. 

For example, you want to see how many users bought groceries after 2 weeks. You can select the first event as "Purchased". You can select the return event again as "Purchased". Select a one month period and then click the View cohort button to analyze user behavior over a month.

The cohort results will tell you how many times your users are buying groceries after their first shopping. This result can give you insight into the user activity and point you to the period when there is a dip in shopping. You can use our engagement channels to engage and retain your users over this time period.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6fac0f2-Cohorts_retention_Unbounded_trend.png",
        "Cohorts_retention_Unbounded_trend.png",
        1203,
        643,
        "#fbfcfc"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This feature is currently available in closed beta. In the meanwhile, you can check this feature in our demo account.",
  "title": "Note"
}
[/block]
## Advanced Filtering
Advanced filters allow you to restrict your analysis to a specific segment of users. Create a segment based on any combination of past behaviors in combination with any set of user properties. 
[block:callout]
{
  "type": "success",
  "body": "Advanced filters is a general feature available for all analytics features and most campaigns. Read more in the [Segmentation guide](doc:segments)."
}
[/block]
# Reading Cohort Results

The cohort result first gives you an overview of your result in the form of a trend graph. This graph plots the total % of users who came back to perform your return event, after performing your desired first event.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dcfa132-image2.png",
        "image2.png",
        1213,
        612,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
The Y-axis shows the % of users that came back to perform your return event & the X-axis shows you the time frame in which the return event was performed. 

You can also see the details of the trend view in a tabular form in this analysis. The tabular view helps you track the performance of each cohort, and also easily compare it to other cohorts. 

For example, in the image below, you can see that in the cohort of Aug 20, a total of 44,431 users launched the application in week 0 (the week of Aug 20). In Week 1, 12.2%  of these users returned to perform the “Charged” event.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a12b589-image5.png",
        "image5.png",
        1214,
        448,
        "#f3f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
##Retention Frequency
You can choose from 4 frequencies for your cohort results.
  * Hourly: Useful for high engagement apps such as live sports scores, social media, and so on. You can view the user the behavior by the hour.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/91c01e4-Cohorts_retention_Hourly.png",
        "Cohorts_retention_Hourly.png",
        1178,
        703,
        "#fafbfc"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
 * Daily: Useful for high engagement apps such as news, social media, productivity apps and so on. You can view the user the behavior by the day.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63d1247-Segments_Cohorts_Daily.png",
        "Segments_Cohorts_Daily.png",
        1198,
        584,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
  * Weekly: Useful for high engagement apps such as music streaming, video streaming, fitness apps, and so on. You can view the user the behavior by the week.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bf22b7-Segments_Cohorts_Weekly.png",
        "Segments_Cohorts_Weekly.png",
        1177,
        567,
        "#fbfcfd"
      ],
      "border": true
    }
  ]
}
[/block]
  * Monthly: Useful for engagement apps such as grocery, e-commerce, and so on. You can view the user the behavior by the month.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70c413f-Segments_Cohorts_Monthly.png",
        "Segments_Cohorts_Monthly.png",
        1192,
        574,
        "#f6f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
  * Custom Bracket: You can define a custom criterion for your cohort. For example, you want to see the retention for different time periods such as Day 1, Week 1, Month 1, Month 2, and Month 3. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b14df2-Cohorts_retention_Custom_Bracket.png",
        "Cohorts_retention_Custom_Bracket.png",
        1201,
        640,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This feature is currently available in closed beta. In the meanwhile, you can check this feature in our demo account.",
  "title": "Note"
}
[/block]

##Retention Metric
The default metric to view retention is by % of users. However, you can view the Retention metric in multiple ways:
  * Return Event (Total): You can view retention by the return event, say the total number of videos streamed over an OTT app. 
  * Percentage of users (Total): You can view the retention by the total percentage of users in the app. For example, the total percentage of users who hailed a ride each week.  This will give you an insight if there is a dip in a particular week of the month and remedy the dropoff with increased engagement during that week. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d805d6a-Cohorts_retention_metrics_percentage.png",
        "Cohorts_retention_metrics_percentage.png",
        1184,
        638,
        "#f8fafc"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
  * Events per User: You can view the retention by events for each user. For example, the number of times a user listened to songs in week 2. 
  * Custom Metric: You can sum up by event property. For example, total revenue earned from all the users who purchased in week 7. 

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "This feature is currently available in closed beta. In the meanwhile, you can check this feature in our demo account."
}
[/block]
**Comparing Cohorts**
In the default view, you see a trend for “all cohorts”, this is the average progression of all users across cohorts, over time. You can choose to compare the performance of one or more cohorts with each other.  You can compare cohorts for different user properties. For example,  retention for Android vs iOS users.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0fca254-image4.png",
        "image4.png",
        1211,
        613,
        "#f7f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
#Re-enter users
A user is counted once in a cohort analysis even if they perform the event multiple times. For example, if a user performs an app launch on days January 1st, January 3rd, and January 5th, the user is counted only once in the January 1st cohort. If you allow re-entry of users into subsequent cohorts, then these users are counted in each of the cohorts. 

# Bookmarks
You can bookmark any funnel, cohort or event query and save it to quickly retrieve later. Bookmarks are specific to each logged in user. No other dashboard users will see the bookmarks you save. 

Bookmarks are convenient for recalling a specific analysis that you want to see frequently. For example, you can bookmark your important conversion funnels and view them each day or week to see how they are changing over time.

# Real Impact
Cohorts retention is measured against the system control group. If you wish to see the impact of your engagement:

1. Go to Analytics > Cohorts.
2. Select events and view Cohorts. 
3. Click the Real Impact tab.

For example, you send engagement campaigns to 100 users. The system control group is 5 percent, which is 5 users. These 5 users did not receive any engagement. You want to check the boost in retention because of your engagement efforts. 

The Real Impact results show that you have increased your retention rate by  14.3 % by taking timely action.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2766722-Analytics_Cohorts_Real_Impact.png",
        "Analytics_Cohorts_Real_Impact.png",
        1212,
        577,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]
# Any Event

This event is available as the first and return event in Cohorts for analysis.
[block:parameters]
{
  "data": {
    "h-0": "Event Type",
    "h-1": "Description",
    "h-2": "How event is tracked",
    "0-1": "This event can track any user event performed on the app.",
    "0-0": "Any Event",
    "0-2": "The event is tracked when the user performs any event on the app.  Any event includes all the system and custom events except the following:\n  * Notification Sent\n  * Notification Viewed\n  * Push impressions\n  * Experiment rendered\n  * Identity Set\n  * Identity Reset\n  * Identity error\n  * App Uninstalled\n  * App Version Changed\n  * Reachable By"
  },
  "cols": 3,
  "rows": 1
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "  * Any Event is not actionable in Cohorts.\n  * This feature is currently available in closed beta. In the meanwhile, you can check this feature in our demo account. "
}
[/block]