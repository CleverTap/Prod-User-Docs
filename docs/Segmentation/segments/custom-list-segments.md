---
title: Custom List Segments
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
  pages:
    - type: link
      title: Use an API to upload custom list segments
      url: https://developer.clevertap.com/docs/custom-list-endpoints
    - type: link
      title: Use Custom list as an entry point in Journeys
      url: https://docs.clevertap.com/docs/journeys#section-journey-components
---
#Introduction

Custom List Segments are custom segments that you can create based on your requirements and analytics. These can be users with the required interests, demographics, and so on. You can use these segments to re-engage your users without having to apply the same conditions or filters again. 

##Examples

A custom list segment can be handy in many scenarios. Typical use cases can be any of the following and more:

  * A retail business running SMS campaigns:
  As a retail business, you may be generating user lists at your point of sale across different cities. You can upload city-based segments and run personalized campaigns to re-engage these users. 
  
  * Engagement integrated with your segmentation engine:
  You may have a segmentation engine or a data science engine that has created a user set to engage with a specific message. In this case, you can use custom list segments to seamlessly create segments from your custom lists and schedule engagement for them. 
  
  * Real-time sync for engagement with your in-house segments:
For example, an app streaming a football match can have millions of users. However, let us assume that the target audience is 10,000 users. The next match is even more interesting and you are expecting a surge in the number of users. You have a list of 15,000 users handy that you can use to run the campaign. You create a segment on this list and run a campaign immediately.  


#Create a custom list segment

You can create a custom list segment by uploading user lists via the dashboard or an API. 

##File Format
The list of the users for your segment must follow a specific format. You can upload the profiles with identity type as GUID or CleverTap ID (g) or the identity (i). 

The format of the CSV file is as follows:
[block:parameters]
{
  "data": {
    "h-0": "Type",
    "h-1": "Identity",
    "0-0": "g",
    "0-1": "a1e2723cba7c4518bea8ef95b036ac83",
    "1-0": "i",
    "1-1": "identity"
  },
  "cols": 2,
  "rows": 2
}
[/block]
The type and identity columns are mandatory for uploading a custom list segment.  
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can only qualify the user profiles that are already available in CleverTap."
}
[/block]
##Create from dashboard

1. Click the + Segment button. 

2. Click Custom Lists. The Create new Window appears. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c3e7478-Segments_Custom_lists_select.png",
        "Segments_Custom_lists_select.png",
        1048,
        633,
        "#f5f6f8"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
3. Click the Upload user list button and select the CSV file. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff7420d-Segments_Custom_lists_upload.png",
        "Segments_Custom_lists_upload.png",
        1236,
        443,
        "#f5f4ef"
      ],
      "border": true
    }
  ]
}
[/block]
4. Name the file and save it. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f377dc-Segments_Custom_lists_Name.png",
        "Segments_Custom_lists_Name.png",
        1237,
        539,
        "#9fa0a1"
      ],
      "border": true
    }
  ]
}
[/block]
5. You will receive an email with the details after the file is processed. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/772be36-Segments_Custom_list_email_successful.png",
        "Segments_Custom_list_email_successful.png",
        1109,
        611,
        "#e8ebf8"
      ]
    }
  ]
}
[/block]
The uploaded segment is now available for use. 
[block:callout]
{
  "type": "info",
  "title": "File size",
  "body": "You can upload maximum file size of 50 MB from the dashboard. The maximum file size allowed from an API upload is 5GB."
}
[/block]
##Create from API

You can create a custom list segment from API. For more information, see  [Custom list API](https://developer.clevertap.com/docs/custom-list-endpoints).

##Replace via dashboard

You can replace a custom list segment from the dashboard. However, if the segment is currently in use for engagement through a Campaign or Journey, then you must stop the Campaign or Journey before replacing the segment. 

*To replace a segment*:

1. Click the ellipsis for segment action from the Segments dashboard. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/efc2bc5-Segments_Custom_lists_replace.png",
        "Segments_Custom_lists_replace.png",
        1222,
        632,
        "#f6f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
2. Click the replace icon <img src="https://files.readme.io/f7a63da-icon_replace.png" height="30px" width="30px" >
3. Click the Re-upload user list and select the CSV file.  
Upload the CSV file.
4. Name the file and save it. Wait for it to be processed. 
5. You will receive an email with the details after the file is processed. 

The uploaded segment is now available for use. 

##Troubleshoot Upload

You may see the following messages when trying to upload the file. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e3712c0-Segments_Custom_lists_email_reupload.png",
        "Segments_Custom_lists_email_reupload.png",
        1107,
        583,
        "#e8eaf8"
      ]
    }
  ]
}
[/block]
If the file is not uploaded correctly, you may have to upload it again. 
[block:parameters]
{
  "data": {
    "h-0": "Segment issue",
    "h-1": "Resolution",
    "0-0": "File upload failed",
    "0-1": "The segment could not be created from the uploaded file. Fix the errors and re-upload the file.",
    "1-0": "File re-upload failed",
    "1-1": "The segment could not be refreshed with the latest file. The segment will be available with the last successful update. Refer to the [Segment Details](https://docs.clevertap.com/docs/custom-list-segments#section-segment-details) page for the last updated file."
  },
  "cols": 2,
  "rows": 2
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Segment processing",
  "body": "The custom list segment is available for use only after the process of creating or updating is complete."
}
[/block]
##Segment details

The segment details can be viewed from the Segment dashboard. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/736e185-Segments_Custom_lists_view_report.png",
        "Segments_Custom_lists_view_report.png",
        1246,
        537,
        "#f2f3f4"
      ]
    }
  ]
}
[/block]
The segment details page shows all the available information for the segment such as:

  * Trend - If the users have increased or decreased over time. 
  * Campaigns and Journeys - The number of campaigns and Journeys currently using the custom list segment. 
  * Segment size and reachability - The total number of users in the segment and their reachability across various engagement channels. 
  * Sample Users - These are samples from your list. You can open any of them to check their details. 
[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "Hover over sample users to find the <img src=\"https://files.readme.io/f28fc62-icon_download.png\" height=\"30px\" width=\"30px\" > download icon. \nClick this button to download all the users in your segment."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81840d5-Segments_Custom_lists_report.png",
        "Segments_Custom_lists_report.png",
        1193,
        1139,
        "#eaecf2"
      ],
      "border": true
    }
  ]
}
[/block]
#Use Custom List Segment

You can use the custom list segment from the "Who" section when creating a campaign. All the custom list segments are listed under the Custom list segment tab. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f11a255-segments_custom_lists_WHO.png",
        "segments_custom_lists_WHO.png",
        1067,
        639,
        "#f5f4f7"
      ],
      "border": false
    }
  ]
}
[/block]