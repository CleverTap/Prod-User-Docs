---
title: Calendar Widgets
excerpt: |-
  A trend report when chosen on a weekly basis can be seen from Sunday-Saturday.
  I want to see the report from Monday-Sunday duration on a weekly basis.
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

There are two types of calendar widgets available in the CleverTap dashboard: Relative Date and Calendar Date. The features and differences between these two calendar widgets are described below.

> 👍 New Calendar Widget
>
> We recently added the Relative Date calendar widget to the CleverTap dashboard to provide more functionality and a better user experience.

# Relative Date

When you use the Relative Date calendar widget, the data will be populated based on today's date and the relative date option you select. 

For example, if you select the last 7 days option on January 15, the data will be populated from January 8 to January 15. Similarly, if you select January 16 with the last 7 days option, the data will be available from January 9 to January 16. 

<Image title="image2.png" alt={320} className="border" border={true} src="https://files.readme.io/9c2fb0e-image2.png" />

## Relative Date Options

The relative date provides the following predefined options:

* Today
* Last 7 days
* Last 15 days
* Last 30 days
* Last 90 days
* This Month
* Previous Month

You can also set a custom relative date with the following options:

* **In the last:** This option lets you choose the number of days (or weeks/months/years) to go back from the current date. You will be able to see data from the selected days (or weeks/months/years) to the current date.
* **Was exactly:** This option lets you choose the exact number of days ago to populate data from.

<Image title="image3.png" alt={407} className="border" border={true} src="https://files.readme.io/f235979-image3.png" />

# Calendar Date

When you select the calendar date range, you can choose the exact days for which you want data populated. For example, you can specify you only want data between April 16 and April 23.

<Image title="image1.png" alt={573} className="border" border={true} src="https://files.readme.io/6857ae8-image1.png" />

## Calendar Date Options

The Calendar Date widget provides the following options:

* **Between:** You can choose to get data for all dates within the date range selected.
* **Before:** When you select Before, you will get data for all dates before the date selected. The lower date bound will be the earlier option of these two possibilities: (A) the [Data Retention Policy](doc:data-retention-policy) set for the event(s) needed, or (B) 10 years.
* **After:** When you select After, you will get data for all dates after the date selected until today's date.
* **On:** You can choose to view data for just a specific date by selecting the On option.

# Operators

Operators is a feature only available under the event property section. This feature gives you two options: 

* **Exists:** Filter your data based on if the date is present for the event. For example, if you are a travel booking company, you can find data for the Charged event where the departure date you select exists.
* **Does Not Exist:** Filter your data based on if the date is absent for the event. For example, if you are a movie streaming app, you can find data for the Subscribed event where the upload date you select does not exist.
