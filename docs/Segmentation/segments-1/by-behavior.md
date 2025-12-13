---
title: By Behavior
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
DOCS NOTES: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE IS UNPUBLISHED AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES: [https://docs.clevertap.com/docs/segments](https://docs.clevertap.com/docs/segments)

## Overview

This section covers how to create past behavior segments and filter with *AND By behavior*.

# Create Past Behavior Segments

To create a past behavior segment, perform the following steps: 

1. From the dashboard, navigate to *Segments* > *Segments*.
2. Select any of the options underneath *Past behavior user segments* from the main segment creation page.

For example, we can create an action-based segment where users will qualify if they have applied a payment offer at least one time in the past 30 days.

3. Select the box *Actions* which takes you to the segment setup page.

<Image title="Segments_PSB_Create_New.png" alt={1228} className="border" border={true} src="https://files.readme.io/6f6d353-Segments_PSB_Create_New.png" />

4. Click **Save segment** and name the segment. You can now view your new segment on the overview page.

### View a Past Behavior Segment Report

The top portion of the past behavior user segment report consists of a way to first view the segment definition to understand its underlying query. There are graphs on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation. The list on the right-hand side shows the sample list of users who qualified for the segment on this day.

<Image title="report.png" alt={1204} className="border" border={true} src="https://files.readme.io/1225063-report.png" />

The lower portion of the live user segment report consists of reachability percentages for these users within each messaging channel. The lower-most part of the report shows you how to do more with this segment by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

![1206](https://files.readme.io/8f416de-lower_report.png "lower report.png")

# Additional AND By Behavior Filters

*AND By Behavior* let you create segments with queries based on certain actions taken and certain other actions not taken by the users. These filters provide the capability to segment users based on the count, average, or total sum of a property value.

## Count

The count filter lets you filter users by event count. The query finds all users who performed a charged event greater than five times in the past 30 days. 

![1192](https://files.readme.io/0678593-2020-11-24_17-51-01_Count.png "2020-11-24_17-51-01_Count.png")

## Average of Property Filter

The average of property filter lets you filter users by the average of a chosen event property. 

For example, you can find out the average revenue earned from all users who performed purchases worth $10 or less. Five users charged each for $3, $5, $7, $2, and $8. The average value of all the purchases lower than $10 is ($3+ $5 + $7 + $2 + $8)/5 events = 25/5 = $5 per event.

Assume that the value for two charged events is missing from the event properties. The charged event values received are $3, $5, and $7. The value of the events with missing even properties will be considered as 0. The average of property is now ($3 + $5 + $7 + $0 + $0)/5 events = 15/5 = $3 per event.

If you want to exclude all such events that do not have event properties, you can select the property *exists* condition in the filter by section.

![1192](https://files.readme.io/09c3239-2020-11-24_17-52-22_Average_of_property.png "2020-11-24_17-52-22_Average of property.png")

## Total Sum of Property

The total sum of property filter provides the capability to filter users by the sum of a chosen event property. For example, the query finds all users who performed a charged event, such that the total sum of the Revenue event property is greater than $10.

![1194](https://files.readme.io/d973ab4-2020-11-24_17-53-50_Total_sum_of_property.png "2020-11-24_17-53-50_Total sum of property.png")

> 📘 Include Users Who Did Not Do the Event
>
> If the query is to find people who performed the charged event fewer than five times, by default, the users who have not performed the charged event are not included in the result set. Only the users who did the charged event but did it fewer than five times are included; however, if the checkbox for *Include users who didn’t do the event* is selected, those users are also included in the result set. The same is true for sum and average.

![1187](https://files.readme.io/db44a26-2020-11-24_17-56-46_Checkbox_message.png "2020-11-24_17-56-46_Checkbox message.png")
