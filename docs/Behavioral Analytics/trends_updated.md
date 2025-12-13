---
title: Trends_Updated
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
# Introduction

Trends can be used to understand exactly how your users are using your platform. You can slice and dice your data in a number of ways using all your powerful building blocks in CleverTap: your events, event properties, user properties, and segments.

In a nutshell, you can do the following:

* Plot a trend of event occurrences
* Compare the trend of multiple events to reveal and understand the underlying patterns
* Compare the trend across multiple event property values of an event
* Compare the trend of events across user properties
* Summarize the trend by event properties
* Compare trends by multiple segments

# View a trend

To set up your trend analysis, you have to select the event which you’d like to analyze, and you can optionally further restrict your analysis to a specific property of that event.

To view a trend:

1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. You can also further filter your analysis by the event property. 

<Image title="Trends_search_sample.png" alt={1183} className="border" border={true} src="https://files.readme.io/2d17bb1-Trends_search_sample.png" />

The trend results are displayed.

![1172](https://files.readme.io/f537a57-Trends_Create.png "Trends_Create.png")

## Filter by Event Property

When selecting an event for analysis, you can narrow the search criteria by filtering the underlying event properties. All subsequent analysis is performed on these filtered event properties. All other event properties of the selected are not considered. 

# Advanced Filtering

Advanced filters allow you to restrict your analysis to a specific segment of users. Create a segment based on any combination of past behaviors in combination with any set of user properties. 

<Image title="Trends_Advanced_Filter.png" alt={861} className="border" width="100%" border={true} src="https://files.readme.io/8aa228b-Trends_Advanced_Filter.png" />

The trend results are displayed. 

![1164](https://files.readme.io/a611360-Trends_Advanced_Filter_results.png "Trends_Advanced_Filter_results.png")

> 📘 Note
>
> Advanced filter is a general feature available for all analytics features and most campaigns. Read more in the [Segmentation guide](doc:segments).

# Add Trends

You can view trends for multiple events. For example, you wish to understand the correlation between two events, such as song played and song downloaded.

To view a trend:

1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. You can also further filter your analysis by the event property. 
3. Click + Event to add an event. 

> 📘 Note
>
> You can add up to 5 events for analysis.

4. Click View Trend. 

<Image title="Trends_search_Add_Event.png" alt={1183} className="border" width="100%" border={true} src="https://files.readme.io/422d59b-Trends_search_Add_Event.png" />

The trends for the selected events are displayed. 

<Image title="Trends_search_Add_Event_Result.png" alt={1183} className="border" width="100%" border={true} src="https://files.readme.io/ed1a737-Trends_search_Add_Event_Result.png" />

## Split by event property

You can choose to split the analysis of your event by the underlying event properties. For example, consider the event Content Started. This event indicates that the user started watching content. Here you can split this event by its underlying event properties such as `Primary Genre`. Now, this will split your single `Content Started` trend line into multiple trend lines, that is, each trend line displays the event property value for each of the event property. For example, `Primary_Genre` displays trend lines for values such as Romance, Drama, Action and so on. 

To split a trend by event property: 

1. Go to Analytics > Trends.
2. Select an event to analyze and view a trend. 
3. Click the + Split by link to filter the trend by the event properties. 
4. Click View Trend. 

<Image title="Trends_Split_by_Event_Property.png" alt={1169} className="border" width="smart" border={true} src="https://files.readme.io/46a0978-Trends_Split_by_Event_Property.png" />

The trend for each event property is displayed. 

<Image title="Trends_Split_by_Event_Property_Result1.png" alt={1154} className="border" width="100%" border={true} src="https://files.readme.io/ecf0cc0-Trends_Split_by_Event_Property_Result1.png" />

All the split event properties are listed at the bottom.\
You can do the following:

* Search through the listed event properties
* Select or clear the event properties from the trend
* Sort the event properties from highest to lowest value and vice versa. 

![1185](https://files.readme.io/cc1caaf-Trends_Split_by_Event_Property_Result2.png "Trends_Split_by_Event_Property_Result2.png")

> 📘 Note
>
> You can split by a maximum of 3 event properties per event.

## Split by user property

You can choose to analyze your trend by the underlying user properties. For example, consider the event Content Started. This event indicates that the user started watching content. Here you can split this trend by its underlying user properties such as `Customer_Type`. Now, this will split your single `Content Started` trend line into multiple trend lines, that is, each trend line references the user property value. For example, the user property `Customer_Type`  is split by user property values such as "Subscribers",  "Free Users", and so on. 

To split a trend by user property: 

1. Go to Analytics > Trends.
2. Select an event to analyze and view a trend. 
3. Select the user property from the "Select by user property" list.
4. Click View Trend. 

![1186](https://files.readme.io/2848b94-Trends_Split_By_User_Property.png "Trends_Split_By_User_Property.png")

The trend for each user property is displayed. 

<Image title="Trends_Split_By_User_Property_Result1.png" alt={1177} className="border" border={true} src="https://files.readme.io/4590691-Trends_Split_By_User_Property_Result1.png" />

All the split user properties are listed at the bottom.\
You can do the following:

* Search through the listed user properties
* Select or clear the user properties from the trend
* Sort the user properties from highest to lowest value and vice versa. 

<Image title="Trends_Split_By_User_Property_Result2.png" alt={1175} className="border" border={true} src="https://files.readme.io/bce9574-Trends_Split_By_User_Property_Result2.png" />

> 📘 Note
>
> You can split by a maximum of 2 user properties.

## Compare trends across segments

You can choose to compare your event trend with different segments. For example, compare the trend for the "Content Started" event across the "New York Users" segment and the “London Users" segment. The differences in the segment trends could reveal a difference in the behavior of your users in each segment and hence result in an insight that could be invaluable. For example, you can compare the trend of content watched by users in both cities. If the trend in either of the cities is lower, you may want to check for competing content in that city. 

To compare trends across segments: 

1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. You can also further filter your analysis by the event property. 
3. Select the "Compare to another segment" box. Select a segment from the list or create an adhoc segment. For more information on segments, see [Intro to Segments](doc:segments).
4. Click View Trend. 

<Image title="Trends_compare_segment.png" alt={1169} className="border" width="100%" border={true} src="https://files.readme.io/cbe0355-Trends_compare_segment.png" />

The results are displayed. 

<Image title="Trends_compare_segment_result.png" alt={1169} className="border" width="100%" border={true} src="https://files.readme.io/dde8d24-Trends_compare_segment_result.png" />

> 📘 Notes
>
> * You can compare by a saved or an ad-hoc segment.
> * You can compare a maximum of 5 segments
> * You cannot simultaneously split the trend by user property and compare the trend by segments.

# Reading the trend

The trend has various tabs and statistics. Let us understand each. 

To view a trend:

1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. 
3. Click View Trend. 

The trend appears with the stats at the bottom. 

## Scale

You can select the scale from the list on the top right of a trend. The trend is scaled in two ways:

* Linear - The data is scaled with an absolute count. 
* Relative - The data is scaled with relative percentages.

## Frequency

You can change the frequency of the trend on a daily, weekly, or monthly basis:

* Daily - The trend is plotted on a daily basis. The subsequent table also shows data points on a daily basis.
* Weekly - The trend is plotted on a weekly basis. The subsequent table also shows data points on a weekly basis.
* Monthly - The trend is plotted on a monthly basis. The subsequent table also shows data points on a monthly basis.

## Event Count

This tab allows you to trend the count of events. For example, the number of ‘content started’ events that occurred in the selected period.

<Image title="Trends_Stats_Event_count.png" alt={1177} className="border" border={true} src="https://files.readme.io/0407fde-Trends_Stats_Event_count.png" />

The stats available in this tab are:

* Total events: Sum of events in the selected period.
* Daily average: Total events/no. of days in the selected period.

## Unique users

This tab allows you to trend the number of unique users that performed the chosen events in the selected period.

<Image title="Trends_Stats_Unique_user.png" alt={1177} className="border" width="smart" border={true} src="https://files.readme.io/439fc6a-Trends_Stats_Unique_user.png" />

The stats available in this tab are:

* Total users: Number of unique users in the selected period
* Daily average: Sum of daily unique users/Number of days

> 📘 Note
>
> If the trend analysis is split by an event or user property, then this split is ignored on this tab.

## Events per user

This tab allows you to trend the number of events per user in the time period. 

![1151](https://files.readme.io/f67292c-Trends_Stats_Event_per_user.png "Trends_Stats_Event_per_user.png")

The stats available in this tab are:

* Events per user: Sum of total events/number of unique users in the period
* Daily average: Sum of daily events per user/number of days in the period

> 📘 Note
>
> If the trend analysis is split by an event or user property, then this split is ignored on this tab.

## Properties

You can choose to summarize the trend by an event property. You can see this in the “Property” tab. For example, consider the trend for the event ‘Content Started’. It has a property called "duration" that stores the duration of the content watched. 

<Image title="Trends_Stats_Properties_Summarize.png" alt={1146} className="border" border={true} src="https://files.readme.io/fb48ad6-Trends_Stats_Properties_Summarize.png" />

The stats available in this tab are:

Summary stats: 

* Total: Sum of property in the period
* Daily average: Sum of property/number of days in period
* Average per user: Sum of property/number. of unique users in the period
