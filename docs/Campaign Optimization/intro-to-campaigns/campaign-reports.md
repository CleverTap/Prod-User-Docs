---
title: Campaign Reports
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
#Overview

You can view comprehensive reports for all campaigns you send out of CleverTap. You can use these reports to analyze campaign performance, compare performance across campaigns, and understand engagement trends.


Campaign reports allow monitoring campaign performance at a glance. You can mail either a summary report of all campaigns sent out in a particular date range or split it by day. This report includes metrics, such as campaign deliveries, engagements, conversions, and errors. To optimize dashboard performance, the data in the report is cached and you can receive data that has been generated up to 4 hours earlier. Also, it’s possible that the report is sent to you within 6 hours depending on the other activities happening at the time of requesting the report.

#Generate Reports

You can view the campaigns from the campaigns list page. Follow the steps to view a report:

1. Click *Campaigns* from the main menu. The Campaign List page appears.
2. Select the campaigns for the report or select the filter criteria.
3. Click the **Email Report icon** or **Subscribe to Reports** icon. The Campaign Summary Emails pane displays.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be30a03-Campaigns_Report_Main.png",
        "Campaigns_Report_Main.png",
        1068,
        569,
        "#f5f7f7"
      ]
    }
  ]
}
[/block]
4. Setup the campaign report. Select the report criteria. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7092227-Campaigns_Report_Setup_tab.png",
        "Campaigns_Report_Setup_tab.png",
        564,
        850,
        "#f8f9fb"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
* Create a report for - Select a report for the following:
 * Selected Campaigns - Generates reports only for the campaigns selected from the list. 
 * All campaigns with filters applied - Generates report for all the campaigns displayed after applying filters on the campaigns list page. 
* Data to include - Determine what data to include in the report. 
 * Campaign Overview - Provides an overview of all the campaigns in the report. 
 * Campaign stats - Provides important stats for the selected campaigns.
 * Campaign detailed stats - Shows all campaign-related stats, such as total campaigns sent, the total number of devices, and so on. 
 * Campaign errors - Displays all the campaign errors. 
* Split all data by - Split data by the required parameters.
 * Day - Shows reports by each day. 
 * OS - Shows reports by OS, that is Android and iOS.
 * Variant type - Shows report by the variant type for AB test campaigns.
* Split all data by - Split data by the required parameters.
* Frequency - Displays report based on the selected frequency. 
 * One-time - Sends report only once. 
 * Recurring - Sends recurring reports on the selected days or dates. 


You can have a one-time report or a recurring report and subscribe to it, based on the selected frequency. 

For a report subscription, you are redirected to the Subscribe tab.  The report is emailed to you on the selected days.

This report summarizes data on all campaigns that were sent out the previous week in CleverTap.

#Subscribe Reports

You may want to subscribe to a report in various scenarios. For example, select and subscribe to 4 campaigns on a monthly recurrence, or only subscribe to push campaigns that you created with a label for a monthly/daily recurrence.

To view your existing subscriptions, click the **Subscribe to Reports** link from the Campaigns list page. The subscriptions are displayed on the Subscriptions tab. 

To create new report subscriptions, follow the steps:

1.  Select the required campaigns from the Campaigns list page. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad91c14-Campaigns_Report_subscribe_link.png",
        "Campaigns_Report_subscribe_link.png",
        1065,
        564,
        "#f6f8f8"
      ]
    }
  ]
}
[/block]
2. Click the **Subscribe to Reports** link from the campaigns list page. The Campaign Summary Emails page displays. 
3. From the setup tab, select the required options and click **Send Report**. 
4. Your existing subscription to reports is displayed on the Subscribe tab.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1340f7-Campaigns_Report_subscribe_tab.png",
        "Campaigns_Report_subscribe_tab.png",
        561,
        861,
        "#f8f8fa"
      ]
    }
  ]
}
[/block]

#Edit/Delete Reports

The existing schedule for the reports is displayed on the Subscribe tab. 

1. To edit or delete a subscription to a report,  click **Subscribe to Reports** on the campaign list page. The Campaign Summary Emails pane displays.
2. Click the **... **icon to edit or delete a report subscription.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9e23ef-Campaigns_Report_subscribe_delete_edit.gif",
        "Campaigns_Report_subscribe_delete_edit.gif",
        1070,
        574,
        "#f6f8f7"
      ]
    }
  ]
}
[/block]
#Reports API
You can use the [Get Campaign Report API](https://developer.clevertap.com/docs/get-campaign-report-api) to programmatically generate campaign reports for your consumption.

#Campaign Report Data 

The following table provides all columns that will be part of the report, based on the selected data group. For example, the first column Campaign ID will be part of each report, irrespective of the data group. However, the campaign name will display as a column in your report, only if you select *Campaign overview* while requesting the report.


[block:parameters]
{
  "data": {
    "h-0": "Report Column",
    "h-1": "Campaign overview",
    "h-2": "Campaign stats",
    "h-3": "Campaign detailed stats",
    "h-4": "Campaign errors",
    "0-0": "Campaign ID",
    "0-1": "Yes",
    "0-2": "Yes",
    "0-3": "Yes",
    "0-4": "Yes",
    "1-0": "Campaign Name",
    "2-0": "Channel",
    "3-0": "Delivery",
    "4-0": "Type",
    "5-0": "Variant",
    "6-0": "OS",
    "7-0": "Device",
    "8-0": "DND / set campaign frequency",
    "9-0": "timezone",
    "10-0": "cutoff",
    "11-0": "fcap (global campaign limits)",
    "12-0": "throttle",
    "13-0": "Safety check limit",
    "14-0": "Campaign per day limit",
    "15-0": "Campaign overall limit",
    "16-0": "estimated reach",
    "17-0": "Reach (Send to all / last active)",
    "18-0": "WHO query",
    "19-0": "Constant event property",
    "20-0": "Title",
    "21-0": "Message",
    "22-0": "iOS Rich Media type",
    "23-0": "IOS Rich media URL",
    "24-0": "IOS sound file",
    "25-0": "IOS Badge Count",
    "26-0": "IOS Category",
    "27-0": "IOS Deep link / External URL",
    "29-0": "Android Subtitle",
    "28-0": "IOS Mutable content",
    "30-0": "Android Image URL",
    "31-0": "Android Summary",
    "32-0": "Android large Icon URL",
    "33-0": "Android Small App Icon colour",
    "34-0": "Android Deep link / External URL",
    "35-0": "Android Sound File",
    "36-0": "Android Notification tray priority",
    "37-0": "Android Notification delivery priority",
    "38-0": "Collapse notification",
    "39-0": "Notification channels",
    "40-0": "Badge ID",
    "41-0": "Badge Icon",
    "42-0": "Send to App Inbox as well",
    "43-0": "Time to live",
    "44-0": "SMS/ Email/ WA service provider",
    "45-0": "Start Date",
    "46-0": "Start Time",
    "47-0": "Conversion Event",
    "48-0": "Conversion Time (in minutes)",
    "49-0": "Campaign URL",
    "50-0": "Status",
    "51-0": "Created By",
    "52-0": "Created time",
    "53-0": "Labels",
    "54-0": "AmplifiedByInbox",
    "55-0": "AmplifiedByPush",
    "56-0": "Web Priority",
    "57-0": "Run Date",
    "58-0": "Total Sent (users)",
    "59-0": "Total Viewed (users)",
    "60-0": "Total Clicked (users)",
    "62-0": "Total Viewed (events)",
    "61-0": "Total Sent (events)",
    "63-0": "Total Clicked (events)",
    "64-0": "Errors",
    "1-1": "Yes",
    "2-1": "Yes",
    "3-1": "Yes",
    "4-1": "Yes",
    "5-1": "Yes",
    "6-1": "Yes",
    "7-1": "Yes",
    "8-1": "Yes",
    "9-1": "Yes",
    "10-1": "Yes",
    "11-1": "Yes",
    "12-1": "Yes",
    "13-1": "Yes",
    "14-1": "Yes",
    "15-1": "Yes",
    "16-1": "Yes",
    "17-1": "Yes",
    "18-1": "Yes",
    "19-1": "Yes",
    "20-1": "Yes",
    "21-1": "Yes",
    "22-1": "Yes",
    "56-1": "Yes",
    "55-1": "Yes",
    "54-1": "Yes",
    "53-1": "Yes",
    "52-1": "Yes",
    "51-1": "Yes",
    "50-1": "Yes",
    "49-1": "Yes",
    "48-1": "Yes",
    "47-1": "Yes",
    "46-1": "Yes",
    "45-1": "Yes",
    "44-1": "Yes",
    "43-1": "Yes",
    "42-1": "Yes",
    "41-1": "Yes",
    "40-1": "Yes",
    "39-1": "Yes",
    "38-1": "Yes",
    "37-1": "Yes",
    "36-1": "Yes",
    "35-1": "Yes",
    "34-1": "Yes",
    "33-1": "Yes",
    "32-1": "Yes",
    "31-1": "Yes",
    "30-1": "Yes",
    "29-1": "Yes",
    "28-1": "Yes",
    "27-1": "Yes",
    "26-1": "Yes",
    "25-1": "Yes",
    "24-1": "Yes",
    "23-1": "Yes",
    "57-2": "Yes",
    "65-0": "Click through conversions",
    "66-0": "Click through conversions %",
    "68-0": "Total control group count",
    "67-0": "Click through conversion revenue",
    "69-0": "Total control group conversions",
    "70-0": "Total control group conversions %",
    "71-0": "Total control group revenue",
    "73-0": "Unique Viewed Within Conversion Time",
    "72-0": "Unique Sent (users)",
    "74-0": "Unique Clicked Within Conversion Time",
    "75-0": "Unique Converted Within Conversion Time",
    "76-0": "Revenue Within Conversion Time",
    "78-0": "View through Conversions %",
    "77-0": "View through Conversions",
    "79-0": "View through conversions Revenue",
    "80-0": "System Control Group Conversions",
    "81-0": "System Control Group Conversions %",
    "82-0": "System Control Group Revenue",
    "83-0": "Campaign Control Group Conversions",
    "84-0": "Campaign Control Group Conversions %",
    "85-0": "Campaign Control Group Revenue",
    "86-0": "Custom Control Group Conversions",
    "87-0": "Custom Control Group Conversions %",
    "88-0": "Custom Control Group Revenue",
    "89-0": "Custom Control Group Name",
    "90-0": "System Control Group Count",
    "91-0": "Custom Control Group count",
    "92-0": "Campaign Control Group count",
    "93-0": "Invalid FCM key",
    "94-0": "App uninstalled(Android)",
    "95-0": "Wrong FCM API key",
    "96-0": "Invalid APNS certificate",
    "97-0": "APNS error",
    "98-0": "APNS Format error",
    "99-0": "APNS Account Temporarily Blacklisted",
    "100-0": "App Uninstalled(iOS)",
    "101-0": "Invalid Profiles",
    "102-0": "Duplicate APNS Token",
    "103-0": "Invalid token - FCM",
    "104-0": "Unknown error - FCM",
    "105-0": "Dispatch error",
    "106-0": "Internal error due to amplification",
    "107-0": "Global frequency cap exceeded",
    "108-0": "Campaign frequency cap exceeded",
    "109-0": "Campaign limit reached for day",
    "110-0": "Campaign limit reach for run",
    "111-0": "Profile not reachable",
    "112-0": "Campaign stopped",
    "113-0": "User DND",
    "114-0": "Duplicate profile for channel",
    "115-0": "APNS bad topic error",
    "116-0": "APNS disallowed topic",
    "117-0": "APNS bad device token",
    "118-0": "APNS device token and topic mismatch",
    "119-0": "APNS inactive device token for topic",
    "120-0": "APNS wrong environment certificate",
    "121-0": "APNS bad certificate",
    "122-0": "APNS idle timeout",
    "123-0": "APNS missing certificate topic",
    "124-0": "APNS Bad Priority",
    "125-0": "FCM payload too large",
    "126-0": "User not reachable",
    "127-0": "User not qualified",
    "128-0": "Notification during campaign DND",
    "129-0": "Campaign cut-off time reached",
    "58-2": "Yes",
    "71-2": "Yes",
    "70-2": "Yes",
    "69-2": "Yes",
    "68-2": "Yes",
    "67-2": "Yes",
    "66-2": "Yes",
    "65-2": "Yes",
    "64-2": "Yes",
    "63-2": "Yes",
    "62-2": "Yes",
    "61-2": "Yes",
    "60-2": "Yes",
    "59-2": "Yes",
    "72-3": "Yes",
    "92-3": "Yes",
    "91-3": "Yes",
    "90-3": "Yes",
    "89-3": "Yes",
    "88-3": "Yes",
    "87-3": "Yes",
    "86-3": "Yes",
    "85-3": "Yes",
    "84-3": "Yes",
    "83-3": "Yes",
    "82-3": "Yes",
    "81-3": "Yes",
    "80-3": "Yes",
    "79-3": "Yes",
    "78-3": "Yes",
    "77-3": "Yes",
    "76-3": "Yes",
    "75-3": "Yes",
    "74-3": "Yes",
    "73-3": "Yes",
    "93-4": "Yes",
    "94-4": "Yes",
    "95-4": "Yes",
    "96-4": "Yes",
    "97-4": "Yes",
    "98-4": "Yes",
    "99-4": "Yes",
    "100-4": "Yes",
    "101-4": "Yes",
    "102-4": "Yes",
    "103-4": "Yes",
    "104-4": "Yes",
    "105-4": "Yes",
    "106-4": "Yes",
    "107-4": "Yes",
    "108-4": "Yes",
    "109-4": "Yes",
    "110-4": "Yes",
    "111-4": "Yes",
    "112-4": "Yes",
    "113-4": "Yes",
    "114-4": "Yes",
    "115-4": "Yes",
    "116-4": "Yes",
    "117-4": "Yes",
    "118-4": "Yes",
    "119-4": "Yes",
    "120-4": "Yes",
    "121-4": "Yes",
    "122-4": "Yes",
    "123-4": "Yes",
    "124-4": "Yes",
    "125-4": "Yes",
    "126-4": "Yes",
    "127-4": "Yes",
    "128-4": "Yes",
    "129-4": "Yes",
    "h-5": "Description",
    "0-5": "The unique ID for the campaign.",
    "1-5": "The name provided for the campaign during its creation.",
    "2-5": "The channel such as Email, Mobile Push, and so on that is used for the campaign.",
    "3-5": "The campaign delivery such as Action, Inaction, One time, and so on.",
    "4-5": "The type of campaign such as single message, message on user property, or A/B test.",
    "5-5": "The message variant. Applicable only to A/B test messages and message on user property.",
    "6-5": "The device operating system, such as iOS and Android.",
    "7-5": "Devices such as mobile, TV, or a Tablet.",
    "8-5": "DND or campaign frequency setting configured at the time of campaign creation.",
    "9-5": "Configuration for the delivery in the user timezone.",
    "10-5": "Configuration of the cutoff period after which the campaign is not delivered.",
    "11-5": "Configuration for the  maximum number of messages that a user can receive in a day.",
    "12-5": "Configuration for the  throttle limits applied to the campaigns.",
    "13-5": "The campaign is not sent to any user if the number of qualified users exceed the limit.",
    "17-5": "Send to all devices or the last active device.",
    "18-5": "The who query defined in the campaign.",
    "19-5": "Shows whether the Constant event property is applicable or not.",
    "20-5": "The title of the notification",
    "21-5": "Message of the notification.",
    "22-3": "",
    "23-3": "",
    "24-3": "",
    "22-5": "Media type such as, Single or Carousel for iOS push notifications",
    "23-5": "Image URL  for iOS push notifications",
    "24-5": "iOS sound or the file URL if custom.",
    "28-5": "Shows whether the content is mutable. The values are Yes/No.",
    "30-3": "",
    "30-5": "Image URL for Android push notifications.",
    "32-5": "Large icon for Android push notifications.",
    "35-5": "The values are:\n\n* NA \n* Default OS sound\n* file URL,  if the file is custom",
    "42-3": "",
    "46-3": "",
    "57-5": "Applicable for Day-wise reports only. Displays the run date.",
    "58-5": "Displays the total count for the sent users. Shows as N/A for channels that are not supported, such as In-app.",
    "61-5": "Total events. Total devices (if 'Send to all' is applied)",
    "62-5": "Total events. Total devices (in case of 'Send to all' is applied)",
    "63-5": "Total events. Total devices (in case of 'Send to all' is applied)",
    "66-5": "Total converting users / Total sent users.",
    "25-5": "Badge count on IOS notification",
    "26-5": "Category for iOS push notifications (if applicable).",
    "27-5": "Deep link for iOS push notifications.",
    "29-5": "Subtitle of the Android push notifications.",
    "31-5": "Summary text for Android push notifications.",
    "33-5": "Small app icon for Android push notifications.",
    "34-5": "Deep link for Android push notifications.",
    "36-5": "Shows the priority of display in tray of android device",
    "37-5": "Server priority for Android push notifications",
    "38-5": "Shows whether the notification is collapsible or not",
    "39-5": "Communication channel, for which the user consent is received.",
    "40-5": "Badge ID for Android push notifications.",
    "41-5": "Badge count Android push notifications.",
    "42-5": "Applicable only for push. Sent to app inbox as well or not.",
    "43-5": "Time for the notification to live in the user device.",
    "44-5": "The service provider.",
    "45-5": "Start date of the campaign.",
    "46-5": "Displays the start time of the campaign. Displays the time value if the campaign is set to best time.",
    "47-5": "The conversion is tracked for this event in the campaign.",
    "48-5": "Time period within which conversion is tracked for the campaign.",
    "49-5": "The URL of the campaign to access it on Clevertap dashboard.",
    "50-5": "Current status of the campaign.",
    "51-5": "The creator of the campaign.",
    "52-5": "Time of creating the campaign.",
    "53-5": "The Labels / tags used to identify and organize campaigns.",
    "54-5": "Shows whether the campaign was amplified by sending it to inbox as well or not.",
    "55-5": "If push amplification is applied or not.",
    "56-5": "Priority of web notifications. It can be High, Medium or low.",
    "59-5": "Displays the total count for the users who viewed the notification.",
    "60-5": "Displays the total count for the users who clicked the notification.",
    "64-5": "Errors",
    "65-5": "Total converting users ( as per funnel, including clicked step)",
    "67-5": "Revenue as per the revenue property related to Total conversions.",
    "68-5": "Total number of users in control group.",
    "14-5": "Number of maximum messages sent per day for the campaign.",
    "15-5": "Number of maximum messages sent overall for the campaign.",
    "16-5": "Estimated qualification of users.",
    "69-5": "Total number of control group users converting.",
    "70-5": "Total number of control group users converting / Total number of users in control group.",
    "71-5": "Revenue as per revenue property related to conversion.",
    "72-5": "Unique users who were sent notification",
    "73-5": "Unique users who viewed the notifications within the set conversion time.",
    "74-5": "Unique users who clicked the notifications within set conversion time.",
    "75-5": "Unique users who converted  within the set conversion time.",
    "76-5": "Revenue as per the revenue property related to conversion.",
    "77-5": "Users who were sent a message and they converted. Referred as influenced conversions on the dashboard.",
    "78-5": "Influenced conversion (above) / Total sent users",
    "79-5": "Revenue as per the revenue property related to conversion.",
    "80-5": "Total number of system control group users converting.",
    "81-5": "Total number of system control group users converting / Total number of users in system control group.",
    "82-5": "Revenue as per the revenue property related to conversion.",
    "83-5": "Total number of campaign control group users converting",
    "84-5": "Total number of campaign control group users converting / Total number of users in campaign control group.",
    "85-5": "Revenue as per the revenue property related to conversion",
    "86-5": "Total number of custom control group users converting.",
    "87-5": "Total number of custom control group users converting / Total number of users in custom control group.",
    "88-5": "Revenue as per the revenue property related to conversion.",
    "89-5": "Name of the custom control group.",
    "90-5": "Total number of users in system control group.",
    "91-5": "Total number of users in custom control group.",
    "92-5": "Total number of users in campaign control group.",
    "93-5": "Campaign error description.",
    "94-5": "Campaign error description.",
    "95-5": "Campaign error description.",
    "96-5": "Campaign error description.",
    "97-5": "Campaign error description.",
    "98-5": "Campaign error description.",
    "99-5": "Campaign error description.",
    "100-5": "Campaign error description.",
    "101-5": "Campaign error description.",
    "102-5": "Campaign error description.",
    "103-5": "Campaign error description.",
    "104-5": "Campaign error description.",
    "105-5": "Campaign error description.",
    "106-5": "Campaign error description.",
    "107-5": "Campaign error description.",
    "108-5": "Campaign error description.",
    "109-5": "Campaign error description.",
    "110-5": "Campaign error description.",
    "111-5": "Campaign error description.",
    "112-5": "Campaign error description.",
    "113-5": "Campaign error description.",
    "114-5": "Campaign error description.",
    "115-5": "Campaign error description.",
    "116-5": "Campaign error description.",
    "117-5": "Campaign error description.",
    "118-5": "Campaign error description.",
    "119-5": "Campaign error description.",
    "120-5": "Campaign error description.",
    "121-5": "Campaign error description.",
    "122-5": "Campaign error description.",
    "123-5": "Campaign error description.",
    "124-5": "Campaign error description.",
    "125-5": "Campaign error description.",
    "126-5": "Campaign error description.",
    "127-5": "Campaign error description.",
    "128-5": "Campaign error description.",
    "129-5": "Campaign error description."
  },
  "cols": 6,
  "rows": 130
}
[/block]