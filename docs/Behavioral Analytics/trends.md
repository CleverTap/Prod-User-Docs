---
title: Trends
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
#Introduction
Trends can be used to understand exactly how your users are using your platform. You can slice and dice your data in a number of ways using all your powerful building blocks in CleverTap: your events, event properties, user properties, and segments.

In a nutshell, you can do the following:
  * Plot a trend of event occurrences
  * Compare the trend of multiple events to reveal and understand the underlying patterns
  * Compare the trend across multiple event property values of an event
  * Compare the trend of events across user properties
  * Summarize the trend by event properties
  * Compare trends by multiple segments

#View a trend

To set up your trend analysis, you have to select the event which you’d like to analyze, and you can optionally further restrict your analysis to a specific property of that event.

To view a trend:
1. Go to Analytics -> Trends.
2. Select an event to analyze and view a trend. You can also further filter your analysis by the event property. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d17bb1-Trends_search_sample.png",
        "Trends_search_sample.png",
        1183,
        741,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
The trend results are displayed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f537a57-Trends_Create.png",
        "Trends_Create.png",
        1172,
        564,
        "#f6f6f9"
      ]
    }
  ]
}
[/block]
##Filter by Event Property
When selecting an event for analysis, you can narrow the search criteria by filtering the underlying event properties. All subsequent analysis is performed on these filtered event properties. All other event properties of the selected are not considered. 

# Advanced Filtering
Advanced filters allow you to restrict your analysis to a specific segment of users. Create a segment based on any combination of past behaviors in combination with any set of user properties. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8aa228b-Trends_Advanced_Filter.png",
        "Trends_Advanced_Filter.png",
        861,
        1752,
        "#faf9fa"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
The trend results are displayed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a611360-Trends_Advanced_Filter_results.png",
        "Trends_Advanced_Filter_results.png",
        1164,
        726,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Advanced filter is a general feature available for all analytics features and most campaigns. Read more in the [Segmentation guide](doc:segments).",
  "title": "Note"
}
[/block]
#Add Trends

You can view trends for multiple events. For example, you wish to understand the correlation between two events, such as song played and song downloaded.

To view a trend:
1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. You can also further filter your analysis by the event property. 
3. Click + Event to add an event. 
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can add up to 5 events for analysis."
}
[/block]
4. Click View Trend. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/422d59b-Trends_search_Add_Event.png",
        "Trends_search_Add_Event.png",
        1183,
        984,
        "#f8f9fa"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
The trends for the selected events are displayed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed1a737-Trends_search_Add_Event_Result.png",
        "Trends_search_Add_Event_Result.png",
        1183,
        774,
        "#fafbfb"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
##Split by event property

You can choose to split the analysis of your event by the underlying event properties. For example, consider the event Content Started. This event indicates that the user started watching content. Here you can split this event by its underlying event properties such as `Primary Genre`. Now, this will split your single `Content Started` trend line into multiple trend lines, that is, each trend line displays the event property value for each of the event property. For example, `Primary_Genre` displays trend lines for values such as Romance, Drama, Action and so on. 

To split a trend by event property: 
1. Go to Analytics > Trends.
2. Select an event to analyze and view a trend. 
3. Click the + Split by link to filter the trend by the event properties. 
4. Click View Trend. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46a0978-Trends_Split_by_Event_Property.png",
        "Trends_Split_by_Event_Property.png",
        1169,
        760,
        "#f7f8f9"
      ],
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]
The trend for each event property is displayed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ecf0cc0-Trends_Split_by_Event_Property_Result1.png",
        "Trends_Split_by_Event_Property_Result1.png",
        1154,
        553,
        "#ebeded"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
All the split event properties are listed at the bottom. 
You can do the following:
  * Search through the listed event properties
  * Select or clear the event properties from the trend
  * Sort the event properties from highest to lowest value and vice versa. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc1caaf-Trends_Split_by_Event_Property_Result2.png",
        "Trends_Split_by_Event_Property_Result2.png",
        1185,
        645,
        "#f9f8f8"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can split by a maximum of 3 event properties per event."
}
[/block]
##Split by user property

You can choose to analyze your trend by the underlying user properties. For example, consider the event Content Started. This event indicates that the user started watching content. Here you can split this trend by its underlying user properties such as `Customer_Type`. Now, this will split your single `Content Started` trend line into multiple trend lines, that is, each trend line references the user property value. For example, the user property `Customer_Type`  is split by user property values such as "Subscribers",  "Free Users", and so on. 

To split a trend by user property: 
1. Go to Analytics > Trends.
2. Select an event to analyze and view a trend. 
3. Select the user property from the "Select by user property" list.
4. Click View Trend. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2848b94-Trends_Split_By_User_Property.png",
        "Trends_Split_By_User_Property.png",
        1186,
        713,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]
The trend for each user property is displayed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4590691-Trends_Split_By_User_Property_Result1.png",
        "Trends_Split_By_User_Property_Result1.png",
        1177,
        558,
        "#fbfbfb"
      ],
      "border": true
    }
  ]
}
[/block]
All the split user properties are listed at the bottom. 
You can do the following:
  * Search through the listed user properties
  * Select or clear the user properties from the trend
  * Sort the user properties from highest to lowest value and vice versa. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bce9574-Trends_Split_By_User_Property_Result2.png",
        "Trends_Split_By_User_Property_Result2.png",
        1175,
        251,
        "#f8f8f7"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can split by a maximum of 2 user properties."
}
[/block]
##Compare trends across segments

You can choose to compare your event trend with different segments. For example, compare the trend for the "Content Started" event across the "New York Users" segment and the “London Users" segment. The differences in the segment trends could reveal a difference in the behavior of your users in each segment and hence result in an insight that could be invaluable. For example, you can compare the trend of content watched by users in both cities. If the trend in either of the cities is lower, you may want to check for competing content in that city. 

To compare trends across segments: 
1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. You can also further filter your analysis by the event property. 
3. Select the "Compare to another segment" box. Select a segment from the list or create an adhoc segment. For more information on segments, see [Intro to Segments](doc:segments).
4. Click View Trend. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cbe0355-Trends_compare_segment.png",
        "Trends_compare_segment.png",
        1169,
        717,
        "#f9f9fa"
      ],
      "sizing": "full",
      "border": true
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
        "https://files.readme.io/dde8d24-Trends_compare_segment_result.png",
        "Trends_compare_segment_result.png",
        1169,
        752,
        "#fafbfb"
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
  "title": "Notes",
  "body": "* You can compare by a saved or an ad-hoc segment.\n* You can compare a maximum of 5 segments\n* You cannot simultaneously split the trend by user property and compare the trend by segments."
}
[/block]
#Reading the trend

The trend has various tabs and statistics. Let us understand each. 

To view a trend:
1. Go to Analytics>Trends.
2. Select an event to analyze and view a trend. 
3. Click View Trend. 

The trend appears with the stats at the bottom. 

##Scale

You can select the scale from the list on the top right of a trend. The trend is scaled in two ways:

* Linear - The data is scaled with an absolute count. 
* Relative - The data is scaled with relative percentages.

##Frequency
You can change the frequency of the trend on a daily, weekly, or monthly basis:
* Daily - The trend is plotted on a daily basis. The subsequent table also shows data points on a daily basis.
* Weekly - The trend is plotted on a weekly basis. The subsequent table also shows data points on a weekly basis.
* Monthly - The trend is plotted on a monthly basis. The subsequent table also shows data points on a monthly basis.

##Event Count
This tab allows you to trend the count of events. For example, the number of ‘content started’ events that occurred in the selected period.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0407fde-Trends_Stats_Event_count.png",
        "Trends_Stats_Event_count.png",
        1177,
        770,
        "#fafbfb"
      ],
      "border": true
    }
  ]
}
[/block]
The stats available in this tab are:
  * Total events: Sum of events in the selected period.
  * Daily average: Total events/no. of days in the selected period.

##Unique users
This tab allows you to trend the number of unique users that performed the chosen events in the selected period.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/439fc6a-Trends_Stats_Unique_user.png",
        "Trends_Stats_Unique_user.png",
        1177,
        782,
        "#fafbfb"
      ],
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]
The stats available in this tab are:
   * Total users: Number of unique users in the selected period
   * Daily average: Sum of daily unique users/Number of days

[block:callout]
{
  "type": "info",
  "body": "If the trend analysis is split by an event or user property, then this split is ignored on this tab.",
  "title": "Note"
}
[/block]
##Events per user
This tab allows you to trend the number of events per user in the time period. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f67292c-Trends_Stats_Event_per_user.png",
        "Trends_Stats_Event_per_user.png",
        1151,
        757,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]
The stats available in this tab are:
 * Events per user: Sum of total events/number of unique users in the period
 * Daily average: Sum of daily events per user/number of days in the period

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If the trend analysis is split by an event or user property, then this split is ignored on this tab."
}
[/block]

##Active %

This tab allows you to trend the count of the users that have performed the selected event as a proportion of the active users. 

For example, there are  100 users who launched your app. These are your active users. However, you wish to find out the percentage of active users that actually made a purchase. Let us assume that a total of 40 users made a purchase. Therefore, 40% of your active users made an actual purchase.

###Set the Qualifying event

Go to Settings> Schema> Qualifying Event
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbda530-Trends_Settings_Qualifying_Event.png",
        "Trends_Settings_Qualifying_Event.png",
        1061,
        617,
        "#f4f3f4"
      ],
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]
###View Trend and Stats
 [View](https://docs.clevertap.com/docs/trends_updated#section-view-a-trend) the trend result from the Trends page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/191bca4-Trends_Stats_Active_percent_result.png",
        "Trends_Stats_Active_percent_result.png",
        1184,
        720,
        "#fbfbfc"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
The stats available in this tab are:

Summary stats: 
  * Active %: Unique users who performed the chosen event/total unique active users in the whole period
  * Daily avg: Unique users/total unique active users calculated per day and averaged over the period.

##Properties
You can choose to summarize the trend by an event property. You can see this in the “Property” tab. For example, consider the trend for the event ‘Content Started’. It has a property called "duration" that stores the duration of the content watched. You can view the trend by "Sum of property value" or "Average of property value"

###Sum of property value

This trend will display the sum of the value of the property. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0a6ab5-Trends_Stats_Properties_Summarize.png",
        "Trends_Stats_Properties_Summarize.png",
        1165,
        767,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
The stats available in this tab are:

Summary stats: 
* Total: Sum of property in the period
* Avg per user: Sum of property/number. of unique users in the period
* Daily avg: Sum of property/number of days in period.

###Average of property value

This trend will display the average of the value of the property. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04de555-Trends_Stats_Properties_Average.png",
        "Trends_Stats_Properties_Average.png",
        1161,
        759,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
The stats available in this tab are:

Summary stats: 
* Avg per user: Sum of property/number of unique users in the period
* Daily avg: Sum of property/number of events calculated per day and averaged over the period

#Custom Formula
[block:callout]
{
  "type": "warning",
  "body": "This feature is currently available in closed beta. In the meanwhile, you can check this feature in our demo account.",
  "title": "Note"
}
[/block]
Custom formulas enable you to track metrics that are unique to your business. You can create these custom formulas using our event or property level functions. For example, you want to find out the popularity of a movie genre, say Action.  You can analyze the trend for this genre using a ratio of the watched time for action movies (A) to the watched time for all movies (B). The ratio A/B will give you the popularity of action movies compared to all movies and its trend.
 
You can also use formulas to simultaneously track metrics that are a part of other tabs on the Trends graph. For example, you can view event count and unique users simultaneously on the same graph.

## Create Formula
1. From the CleverTap dashboard, go to Analytics > Trends.
2. Select the event to analyze and view a trend. For example, select watched time for action movies (people watched 10 hours).
3. Select another event that denotes watched time for all movies (people watched 10 hours).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a50d78e-Trends_Formula_Select_Events.png",
        "Trends_Formula_Select_Events.png",
        1164,
        1057,
        "#f8f8fa"
      ]
    }
  ]
}
[/block]
4. Click View Trend. The trend appears. 
5. Click the "Formula" tab.
6. Enter the formula. In our example, property sum of Event A / Event B.
7. Click Apply to view the results. It will show the popularity of Action movies over the selected time period.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9e22fa-Trends_Formula_Select_Events_Create_formula.png",
        "Trends_Formula_Select_Events_Create_formula.png",
        1164,
        978,
        "#fafafb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "You can compare up to 4 formulas together on the same chart by adding a “;” between the formulas.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aba21bc-Trends_Formula_Factors_result.png",
        "Trends_Formula_Factors_result.png",
        1157,
        959,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
You can use the following functions to create your formulas:

##Event level functions

Use any of the following functions for your analysis.

  * TOTALS - Count of selected event performed
  * UNIQUES - Unique number of users who performed the selected event
  * AVERAGE - Average number of events performed per unique users. This can also be created using: TOTALS/UNIQUES.
  * ACTIVE - Proportion of users who did the selected event/ users who did the active event. To set the qualifying event, see [Set the qualifying event](https://docs.clevertap.com/docs/trends#section-set-the-qualifying-event)
[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "A function must always be upper case, that is, TOTALS not ToTals."
}
[/block]
##Property level functions

Use any of the following functions for your analysis. 

  * PROPSUM - Total value of the selected event property for all the events performed.
  * PROPAVG -  Average value of the selected event property per occurrence of the event. This can also be created using PROPSUM/TOTALS.

[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "A function must always have upper case, that is, PROPSUM and not PropSum.  An event must be summarized by event property for a property level function."
}
[/block]
##Operators
You can use the following operators to combine the functions into custom formulas that are relevant to your business.

* ()
* /
* X
* +
* -

##Formula comparison
You can compare up to 4 formulas together on the same chart by adding a “**;**” between the formulas. For example, you want to see the Trend for Number of content consumed and the unique users who consumed the content. You can compare the formulas, such as TOTALS and UNIQUES for the same event, that is, Content Started. 

Select and analyze events.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/800f264-Trends_Formula_Select_Events_parallel_formula.png",
        "Trends_Formula_Select_Events_parallel_formula.png",
        1163,
        1041,
        "#f8f9fa"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
Add up to 4 formulas separated by a semicolon ";".
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4dbc15f-Trends_Formula_Select_Events_Create_formula_parallel.png",
        "Trends_Formula_Select_Events_Create_formula_parallel.png",
        1163,
        1010,
        "#fafbfb"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]