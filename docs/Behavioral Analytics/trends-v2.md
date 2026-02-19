---
title: Trends 2.0
excerpt: >-
  Learn to use the new and improved visualization of your data using Trends to
  gain deeper insights and make informed decisions.
deprecated: false
hidden: false
metadata:
  title: Trends Vnext
  description: ''
  keywords:
    - New Trends
  robots: index
next:
  description: ''
---
# Overview

CleverTap's Trends feature provides advanced tools for analyzing and visualizing data, offering a comprehensive understanding of user behavior. The key functions include the following:

* _Selection Capabilities_: Users can choose event-level data, event properties, and user properties and specify analysis periods for deeper insights.
* _Advanced Filtering and Segmentation_: Robust filtering options and the ability to segment data for a targeted analysis.
* _Visualization Tools_: Trends can be visualized using various metrics, such as trendlines, conversion metrics, anomaly detection, and retention metrics.

These capabilities give users a powerful way to optimize platform usage and enable them to make informed decisions to drive business outcomes.

> 📘 Public Beta
>
> Currently, this feature is a Private Beta Release. If you want access to this feature, contact your Account Manager.

Using the _Trends_ dashboard, users can:

* Plot and analyze trends of event occurrences.
* Compare trends of multiple events to uncover patterns.
* Examine trends across different event property values.
* Compare event trends by user properties.
* Summarize trends using event properties.
* Compare trends across multiple segments.

# Getting Started

The Trends dashboard enables you to visualize data by segmenting events based on event properties and user-defined segments. You can further refine these segments by splitting them based on user properties.

Results can be displayed in various formats, such as trendlines, pie charts, and more, and can be viewed over different time periods, such as days, or months. You also have the option to download the resulting visualizations or pin the analysis to a board for continuous updates. Additionally, you can download these results in a CSV file.

> 📘 Event and Segment Limit
>
> You can select up to five events and five segments for analysis.

<Image align="center" alt="Trend Analysis" border={true} caption="Trend Analysis" src="https://files.readme.io/79923bce74d05b0178c3541a856d3dc7bc7315b9d7ea2b06e75e5fb0e7668587-image.png" />

# View a Trend

To set up a trend analysis, select the event you would want to analyze. You can also restrict your analysis further to a specific property of that event.

To view a trend:

1. Go to _Analytics_ > _Trends_ and select an event to analyze from the _EVENTS_ section to view a trend. For example, you want to analyze all the users who launched the app.
2. Click **View Analysis**.

<Image align="center" alt="View a Trend" border={true} caption="View a Trend" src="https://files.readme.io/f07eb1911a1e56da4f0f3fbe668a21f313b57abfd37ce778851a4fd5beeb5c0c-View_Trends_Main.jpg" />

The trend results are displayed. Hovering over the trendline shows the percentage increase or decrease for the selected time frame and other event information.

You can change the view period of the trend on a daily or monthly basis:

<Image align="center" alt="Viewing period" border={true} caption="Viewing period" src="https://files.readme.io/4430a0dfe39b74984c3aa6b32c7e07ac3f23831f4c38b5838a148f3755d33ea6-image.png" />

* _Daily_: The trend and data points are plotted on a daily basis.
* _Monthly_: The trend and data points are plotted on a daily basis.

## Event Count

To measure the event count:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend.
2. From the _MEASURE_ section, select any one of the following:
   * _Total Events_: This measure displays the sum of events in the specified period. If an event is performed multiple times, each occurrence is accounted for separately in the total count. For example, if user A performs an event on Day 1 and again on Day 2, the _Total Events_ count will be cumulative, showing 2 for those two days combined.
   * _Unique Users_: This measure displays the trend for the number of unique users who performed the chosen events in the selected period. The _Unique Users_ column in the table shows the unique users that have performed the event, property, and segment combination in the entire period selected from the date picker. For example, if user A has done the event on Day 1 and Day 2, the user is counted once each day. However, user  A is counted only once in the _Unique User_ column.
3. Click **View Analysis**.

### View Event Count

To view the event count, hover over any trendline.  For example, the number of _App Launched_ events that occurred in the selected period. (This is repeated information - we have already stated earlier - hovering on the data point gives this information.)

<Image align="center" alt="Event Count in Trend" border={true} caption="Trend Event Count" title="View Trends Stats Event Count" src="https://files.readme.io/70480afa9d9015cab6214c0125afc565dce5e92374cb17b13880b8da5cc70079-View_Trends_Main.jpg" />

The stats available are:

* Total events: Sum of events in the selected period.
* Daily change: The change in percentage from the previous time period, that is, day, or month.

# Compare Trends for Events

You can compare trends for multiple events. For example, you can understand the correlation between two events, such as App Launched and Notification Viewed.

To view a trend, perform the following steps:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. You can also filter your analysis further by the event property.
2. Click **Add Event** to add another event for comparison.
3. Click **View Analysis**.

<Image align="center" alt="Compare Trends for different events" border={true} caption="Compare Trends" title="Select Trend Options and Click View Trend" src="https://files.readme.io/9123233f0a9485ce41f62ece0f3a3f26421a450f9da8233d9bf4933d4c16384d-Compare_Trends.jpg" width="100%" />

## Filter by Event Property

When selecting an event for analysis, you can restrict the search criteria by filtering based on the specific event properties. All subsequent analyses are performed using these filtered event properties, while other properties of the selected event are excluded.

To filter a trend by event property:

1. Go to _Analytics_ > _Trends_ and select an event to analyze from the _EVENTS_ section and view a trend. For example, you want to analyze only those users who viewed In-App notifications.
2. Click **+ Filter** to filter by an event property that is In-App.
3. Click **View Analysis**.

The resulting trend filters users who viewed notifications from an in-app notification. It does not include users who viewed other types of notifications, such as Email or the Web. Any further analysis of this event will focus exclusively on users who viewed notifications from the In-App campaign.

<Image align="center" alt="Filter Event by Property" border={true} caption="Filter Event by Property" src="https://files.readme.io/0ae068a6ae0702833c24dff297308064596016dc0cd218f9416d585b4b4028ff-Trends_filter_by_event.jpg" />

## Split by Event Property

You can split the analysis of your event based on specific event properties. For example, consider the `Charged` event, which indicates a user has made a purchase. You can split this event by its underlying properties, such as `Payment Mode` and `Amount`. This divides your single `Charged` trend line into multiple lines, with each trend line representing the value of a different event property. This allows you to visualize the payment method your users prefer.

To split a trend by event property:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. For example, `Charged`.
2. Click **+ Split by** to divide the trend by the event properties, such as `payment method`.
3. Click **View Analysis**.

<Image align="center" alt="Compare trends by event properties" border={true} caption="Compare trends by event properties" src="https://files.readme.io/d5b72c9af7314d6543c2acc901717ba58a02e2d1c194ce415390b80799b7ee36-image.png" />

The trend for each event property is displayed.

All the split event properties are listed at the bottom of the right pane. You can perform the following actions:

* Use the search box to find specific event properties.
* Select or deselect event properties from the trend by selecting the corresponding boxes.
* Sort the event properties from highest to lowest values, or vice versa, by clicking the arrows.

> 📘 Maximum Split
>
> You can split an event by up to two event properties at a time.

# Compare Trends Between Time Periods

You can compare event trends against the previous period, such as day, week, month, and year.

To compare trends across time periods, perform the following steps:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. You can also filter your analysis further by the event property.
2. Select the date range for the trend. The trend displays.
3. From the _Analysis_ pane, select the relevant time period from the _Compare_ list.

A new dotted line appears for each series of the event data to display the difference in the values.

<Image align="center" alt="Compare across time periods" border={true} caption="Compare across Time Periods" src="https://files.readme.io/ab0516780fae8f74f51e41ffbabc0bb0ca9d0f303dc43b9802d2ca69991800ff-Compare_across_timelines.gif" />

# Compare Trends for Segments

You can compare your event trend across different user segments. For example, you can compare the _App Uninstalled_ event trend across segments, such as _Loyal Customers,_ _Champion Users_, and _Match Day Players_. Differences in the segment trends reveal variations in user behavior, providing invaluable insights. For instance, if many Booster Abandoners are uninstalling the app, it may indicate a need for alternative engagement strategies rather than offering them game boosters.

To compare trends across segments:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend. You can also filter your analysis further by the event property.
2. Click **Add Segment** from the _SEGMENT_ section.
3. Select a segment from the list or create an ad hoc segment. For more information, refer to [Segments](doc:segmentation) .
4. Click **View Analysis**.

<Image align="center" alt="Compare Trends Across Segments" border={true} caption="Compare Trends Across Segments" src="https://files.readme.io/372d2522452f6264308263ee5c232a65feca2aef22f238c82cb8e5c4433993ba-image.png" />

> 📘 Comparison Considerations
>
> You must consider the following when comparing trends across different segments:
>
> * You can compare a saved or an ad-hoc segment.
> * You can compare a maximum of five segments.
> * You cannot split the trend by user property and compare it by segments simultaneously.

## Adhoc Segments

When performing a trend analysis, you can use available user segments or create ad-hoc segments in run time. To create adhoc segments:

1. From the _SEGMENT_ section, click the edit icon.

<Image align="center" alt="Create Adhoc Segment" border={true} caption="Create Adhoc Segment" src="https://files.readme.io/3eb2702d462e999b6155fa3b76bce5ff4dd9efb5e9265c676f5ef8bb7d452046-image.png" width="40% " />

2. Click **Add Rule** to add a condition or click **[Add Rule Group](https://docs.clevertap.com/docs/segmentation-rules)** to add multiple conditions.

<Image align="center" alt="Add Rules" border={true} caption="Add Rules" src="https://files.readme.io/0f6c55c2577f3d86d157776fcb521eff4938a783049e90261cd57c621105ee11-image.png" width="70% " />

For information about creating segments, refer to [Segmentation](https://docs.clevertap.com/docs/segmentation).

## Split by User Property

You can analyze a trend based on the specific user properties. For example, consider the event `Charged`, which indicates that the user has started watching content. Here, you can split this trend based on the underlying user property, such as `Customer_Type`.

This splits your single `Charged` trend line into multiple trend lines, each referencing the user property value. For example, the user property `Customer_Type` is split by user property values such as _Platinum_, _Silver_, and so on.

To split a trend by user property:

1. Go to _Analytics_ > _Trends_ and select an event to analyze and view a trend.
2. Select the user property from the _Split by user_ property list under the _SEGMENT_ section
3. Click **View Analysis**.

<Image align="center" alt="Split Segment by User Property" border={true} caption="Split Segment by User Property" src="https://files.readme.io/1729dee2d0d09682ba1fcef09cfdad337364111ec2c738a9271690c1cb046d75-image.png" />

The trend for each user property displays.  All the split user properties are listed at the bottom. You can do the following:

* Search through the listed user properties using the search box.
* Select or clear the user properties from the trend by selecting the specific checkbox.
* Sort the user properties from highest to lowest value and vice versa using the arrows.

> 📘 Maximum Split
>
> You can split by a maximum of two user properties. Split by properties is not available when comparing two or more segments.

# Bookmark a Trend Analysis

You can bookmark any Trend analysis to quickly revisit it later. Bookmarks are user-specific; only the logged-in user can view their saved bookmarks on the CleverTap dashboard.

Bookmarks are especially useful for tracking frequently accessed trends. For example, if you regularly monitor a trend such as Charged split by Payment Method, bookmarking it lets you instantly return to the same setup without recreating the analysis each time.

To bookmark a Trend, perform the following steps

1. Click **Bookmark** in the top-right corner of the dashboard after generating the Trend analysis.
2. Enter a descriptive name to help you easily identify the analysis later.
3. Click **Save**.

You can save up to 50 bookmarks.

> 📘 Note
>
> Bookmarked Trends are accessible only to the user who created them. You can access all your saved bookmarks from the bookmark list under the _Trends_ section.
