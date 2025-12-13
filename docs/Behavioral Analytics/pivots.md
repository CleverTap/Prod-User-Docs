---
title: Pivots
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
> 📘 Being a part of CleverTap's 'Discovery platform',**Pivots** is available for Enterprise customers.

Pivots help you derive significance and insights from your user data. 

The Pivot analysis tool summarizes your data, and helps you slice it and dice it with the help of tables and other data visualizations. A Pivot analysis is especially useful when you are dealing with a large volume of data as it allows you to create incisive summaries and view custom reports to gleam insights.

Pivot Analysis will help you answer questions like:

* At what time of the day, which categories of my products are selling best?
* In which city are my sales for Nike Shoes the lowest?
* How many mins of sports content do my platinum customers consume each day of the week?

# Getting Started with Pivots

## Step 1: Pick Your Event

Once you are on the Pivot analysis section, you need to select the event which you’d like to analyze. This event will form the basis of your analytics, and you will be able to couple this event & its properties along with all the information CleverTap has for your users.

<Image title="Pivots_select_event.png" alt={1189} className="border" border={true} src="https://files.readme.io/f2319fd-Pivots_select_event.png" />

## Step 2: Select Your Segment

After you’ve selected the event you’d like to analyze, you can decide if you’d like to analyze this event for all your users, or if you’d like to examine this event for “all your users” or for a particular segment of users. This feature is extremely useful, as behavior for users varies across segments. 

Example: Content consumption for your new user segment will be very different from the consumption of people that have already consumed at least 50 hours of content.

![870](https://files.readme.io/9ed3243-Pivots_segments_create.png "Pivots_segments_create.png")

## Step 2: Picking the Properties to Pivot On

Here, you have to select the properties on which you would like to carry out your analysis. These properties could be:

* Event properties
* User properties
* Geography
* Technographics
* App Fields 

<Image title="Pivots_on_properties.png" alt={890} className="border" border={true} src="https://files.readme.io/29a925b-Pivots_on_properties.png" />

## Step 4: Aggregating Your Query by Count vs Conversion Property

You can group your data by either the “occurrences” of an event, which are the number of times this event has happened. 

If the event you are analyzing is your conversion event, and your conversion property is an integer, you can group your data by the sum of this property. For example, a flight aggregator can view this data by either the count of “flight booked” event, or by the sum of the “amount” pro.

## Step 5:  Understanding the Pivot Analysis

**Understanding the Pivot Table**

* Pool of available properties: This is a list of properties, that you selected while creating the pivot table. You can use these properties in any combination to slice and dice your data to derive insights. These properties could act as rows, or columns in the tabular view, and as cartesian axes in the graphical view.
* Row(s) – The properties you’d like to select as rows in your tabular views.
* Column(s) – The properties you’d like to select as columns in your tabular views.
* Data visualizations – Here, you can select what visualization you’d like to see the data you’ve sliced and diced in.

# Example Analysis

Let’s take up an example to understand the output of our pivot analysis. In this example, we are a video application, we’re using the Pivot analysis to understand content consumption patterns in our platform. To do so, we’ve selected the event “video watched” which is raised after someone is done watching a video.

The properties we’re selecting for this pivot analysis are

* Hour of the day
* Day of the week
* Video Name

We will also be picking our measurement property as “video duration watched”, since it’s critical for us to measure video performance not just by number of views, but also by duration of content consumption.

We’ll now explain each view and tell you what insight can be drawn for each view supported by our pivot analysis.

## Table

This is best for getting a quick overview of selected data.

<Image title="Pivots_result_table.png" alt={1197} className="border" border={true} src="https://files.readme.io/6f678ed-Pivots_result_table.png" />

## Table Heat Map

This is best for analyzing highest contributor in a given data set. 

For example, if your row is day of the week and column is video name, this heat map will tell you which video was played the most, and on which day of the week did this happen.

<Image title="Pivots_heat_map.png" alt={1194} className="border" border={true} src="https://files.readme.io/5258a1a-Pivots_heat_map.png" />

## Columnar Heatmap

This is best for analyzing outliers in any column. 

For example, if your row is day of the week and column is video name, this heat map will tell you which video was played the most on each day of the week.

<Image title="Pivots_heat_map_columnar.png" alt={1193} className="border" border={true} src="https://files.readme.io/631d4e0-Pivots_heat_map_columnar.png" />

## Row-Wise Heatmap

This is best for analyzing outliers in any row. 

For example, if your row is day of the week and and column is video name, this heat map will tell you on which day of the week, each video has performed well. Game of Thrones performs best on Sundays, whereas Friends works best on Saturdays.

<Image title="Pivots_heat_map_row.png" alt={1199} className="border" border={true} src="https://files.readme.io/ebb44ce-Pivots_heat_map_row.png" />

## Stacked Bar Chart

This is best best for visualizing the change in performance of one variable over time, when compared to several other variables. 

For example, if your row is day of the week and column is video name, you might see that the performance of Game of Thrones peaks around Sunday/Monday. Game of Thrones is a lot lower for the rest of the week, as compared to the consumption of Friends, Prison Break, and Breaking Bad, which are all consistent across the week.

<Image title="Pivots_heat_map_stacked_bar.png" alt={1192} className="border" border={true} src="https://files.readme.io/29a3b30-Pivots_heat_map_stacked_bar.png" />

## Barchart

Best for – Visualizing categorical or qualitative data over time. Example: if your row is day of the week, and column is video name. You will see how the consumption of Game of Thrones has been over the week.

<Image title="Pivots_heat_map_bar_chart.png" alt={1198} className="border" border={true} src="https://files.readme.io/23868d6-Pivots_heat_map_bar_chart.png" />

## Line Chart

This is best for visualizing the change of variables over time. Since all lines are plotted on the same graph, this visualization helps you determine the relationship between different variables.

For example, if your row is day of the week and column is video name, you might see that Breaking Bad and Prison Break follow the same trend across the week. This implies that the demand for these videos is consistent.

<Image title="Pivots_heat_map_line_chart.png" alt={1198} className="border" border={true} src="https://files.readme.io/bcf83e5-Pivots_heat_map_line_chart.png" />

## Area Chart

Similar to Line charts, but better for analyzing part to whole relationships. 

For example, if your row is day of the week and column is show name, the area chart will not only show you the trend variation of Game of Thrones over the week, but it will also show you the contribution of Game of Thrones to your total video views, as compared to the rest of your titles.

<Image title="Pivots_heat_map_area_chart.png" alt={1192} className="border" border={true} src="https://files.readme.io/49659b9-Pivots_heat_map_area_chart.png" />

# Notes

* We sample your data to ensure that results load faster, so you might see a minor difference in counts when you compare these numbers to numbers in the rest of your dashboard. 
* This sampling has been optimized for accuracy and your numbers will be directionally correct.
