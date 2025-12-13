---
title: Live User
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
Live user segments can add users to the segment as soon as users qualify based on the following:
  * Single action: users who have added a product to the cart.
  * Inaction within time: users who have added a product to the cart but did not purchase within 10 minutes of adding a product to the cart.
  * On a date/time: users who have an appointment five days from today.
  * Page visit: users who have visited a certain URL on your website.
     * Referrer entry: users who have visited your website via a certain external referrer URL.
     * Page count: users who have visited a certain number of pages on your website.

#Create Live User Segments
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
#View Live User Segment Reports

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