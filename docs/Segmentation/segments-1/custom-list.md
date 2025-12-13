---
title: Custom List
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
@DOCS: ONCE APPROVED BY PM, REPLACE EXISTING USER DOC https://docs.clevertap.com/docs/custom-list-segments AND MOVE TO CORRECT SPOT IN THE TABLE OF CONTENT.
[block:api-header]
{
  "title": "Overview"
}
[/block]
Custom list segments are custom segments that you create based on your requirements and analytics. These can be users with the required interests and demographics. You can use these segments to re-engage your users without having to apply the same conditions or filters again. 

##Examples

A custom list segment can be useful in many use cases, including:
* A retail business running SMS campaigns: As a retail business, you may be generating user lists at your point of sale across different cities. You can upload city-based segments and run personalized campaigns to re-engage these users. 
* Engagement integrated with your segmentation engine: You may have a segmentation engine or a data science engine that has created a user set to engage with a specific message. In this case, you can use custom list segments to seamlessly create segments from your custom lists and schedule engagement for them. 
* Real-time sync for engagement with your in-house segments: An app streaming a football match can have millions of users. If your target audience is 10,000 users and the next match is even more interesting, you could expect a surge in users where you end up with a handy list of 15,000 users. You can create a segment using this list and run a campaign immediately.  

#Create Custom List Segments
You can create a custom list segment by uploading user lists via the dashboard or an API. 

##File Format
The user list for your segment must follow a specific format. You can upload the profiles with identity type as GUID or CleverTap ID (g) or the identity (i). 

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
  "title": "User Profile Qualification",
  "body": "You can only qualify the user profiles that are already available in CleverTap."
}
[/block]
##Create a Custom List from the Dashboard
To create a custom list, perform the following steps:
1. From the dashboard, navigate to *Segments* > *Segments*.
2. Click **+ Segment**.
3. . Select *Custom list segments*. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b0ea22-Select_custom_list.png",
        "Select custom list.png",
        789,
        633,
        "#f9f9f9"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
3. Click **Upload user list** and select a CSV file. 
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
4. Name the file and click **Save**. 
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
  "title": "File Size",
  "body": "You can upload a maximum file size of 50 MB from the dashboard. The maximum file size allowed from an API upload is 5GB."
}
[/block]
##Create a Custom List from an API

You can create a custom list segment from an API. For more information, refer to [Custom List Endpoints](https://developer.clevertap.com/docs/custom-list-endpoints).

###Replace via the Dashboard
@PM: THE 'REPLACE' ICON DOES NOT SEEM TO BE AVAILABLE ANYMORE. PLEASE CONFIRM WE SHOULD DELETE THIS ENTIRE SUB-SECTION: https://docs.clevertap.com/docs/custom-list#section-replace-via-the-dashboard

You can replace a custom list segment from the dashboard. However, if the segment is currently in use for engagement through a campaign or journey, then you must stop the campaign or journey before replacing the segment. 

To replace a segment, perform the following steps:
1. From the dashboard, navigate to *Segments* > *Segments*.
2. Search for your segment.
3. Click the ellipsis of the appropriate segment to bring up the segment actions. 
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
4. Click the replace icon <img src="https://files.readme.io/f7a63da-icon_replace.png" height="30px" width="30px" >
3. Click the Re-upload user list and select the CSV file.  
Upload the CSV file.
4. Name the file and save it. Wait for it to be processed. 
5. You will receive an email with the details after the file is processed. 

The uploaded segment is now available for use. 

###Troubleshoot Upload

You may see the following message when trying to upload the file:
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
    "h-0": "Segment Issue",
    "h-1": "Resolution",
    "0-0": "File Upload Failed",
    "0-1": "The segment could not be created from the uploaded file. Fix the errors and re-upload the file.",
    "1-0": "File Re-upload Failed",
    "1-1": "The segment could not be refreshed with the latest file. The segment will be available with the last successful update. Refer to [Segment Details](https://docs.clevertap.com/docs/custom-list-segments#section-segment-details) for the last updated file."
  },
  "cols": 2,
  "rows": 2
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Segment Processing",
  "body": "The custom list segment is available for use only after the process of creating or updating is complete."
}
[/block]
###Segment Details

The segment details can be viewed from the *Segments* dashboard. 
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
The segment details page shows all the available information for the segment, including:

  * Trend: If the users have increased or decreased over time. 
  * Campaigns and journeys: The number of campaigns and journeys currently using the custom list segment. 
  * Segment size and reachability: The total number of users in the segment and their reachability across various engagement channels. 
  * Sample users: These are samples from your list. You can open any of them to check their details. 
[block:callout]
{
  "type": "info",
  "title": "Download Tip",
  "body": "Here is a quick download tip:\n1. Hover over sample users to find the <img src=\"https://files.readme.io/f28fc62-icon_download.png\" height=\"30px\" width=\"30px\" > download icon. \n2. Click this button to download all the users in your segment."
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
#Use Custom List Segments

You can use the custom list segment from the *Who* section when creating a campaign. All the custom list segments are listed after choosing the *Custom list* selection. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a8db89-The_who_-_custom_list.png",
        "The who - custom list.png",
        1345,
        550,
        "#f8f7fc"
      ],
      "border": false
    }
  ]
}
[/block]