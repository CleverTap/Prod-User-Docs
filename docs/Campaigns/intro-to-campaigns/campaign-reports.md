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
# Overview

Comprehensive reports are viewable for all campaigns you send out of CleverTap. You can use these reports to analyze campaign performance, compare performance across campaigns, and understand engagement trends.

Campaign reports provide the capability to monitor a campaign's performance at a glance. You can email a summary report of all campaigns sent out in a particular date range or split it by day. This report includes metrics, such as campaign deliveries, engagements, conversions, and errors. To optimize dashboard performance, the data in the report is cached and you can receive data that has been generated up to four hours earlier. Also, it is possible that the report is sent to you within six hours depending on the other activities happening at the time of requesting the report.

# Generate Reports

You can view the campaigns from the campaigns list page. To view a report, perform the following steps:

1. From the dashboard, navigate to *Campaigns*.
2. Select the campaigns for the report or select using the filter criteria.
3. Click the email icon or the *Subscribe to Reports* icon. Then, the *Campaign Summary Emails* screen displays.

![1577](https://files.readme.io/390e1ce-Campaign_report_1.png "Campaign report 1.png")

4. Set up the campaign report. Select the report criteria. 

<Image title="Campaigns_Report_Setup_tab.png" alt={564} className="border" width="80%" border={true} src="https://files.readme.io/7092227-Campaigns_Report_Setup_tab.png" />

* Create a report for - Select a report for the following:
* Selected campaigns: Generates reports only for the campaigns selected from the list. 
* All campaigns with filters applied: Generates report for all the campaigns displayed after applying filters on the campaigns list page. 
* Data to include - Determine what data to include in the report:
* Campaign overview: Provides an overview of all the campaigns in the report. 
* Campaign stats: Provides important stats for the selected campaigns.
* Campaign detailed stats: Shows all campaign-related stats, such as total campaigns sent, the total number of devices, and so on. 
* Campaign errors: Displays all the campaign errors. 
* Split all data by - Split data by the required parameters:
* Day: Shows reports by each day. 
* OS: Shows reports by OS, that is Android and iOS.
* Variant type: Shows report by the variant type for AB test campaigns.
* Split all data by - Split data by the required parameters:
* Frequency: Displays report based on the selected frequency. 
* One-time: Sends report only once. 
* Recurring: Sends recurring reports on the selected days or dates. 

You can have a one-time report or a recurring report and subscribe to it based on the selected frequency. 

For a report subscription, you are redirected to the *Subscribe* tab.  The report is emailed to you on the selected days.

This report summarizes data on all campaigns that were sent out the previous week in CleverTap.

# Subscribe to Reports

You may want to subscribe to a report in various scenarios. For example, select and subscribe to four campaigns on a monthly recurrence, or only subscribe to push campaigns that you created with a label for a monthly/daily recurrence.

To view your existing subscriptions, click the **Subscribe to Reports** link from the *Campaigns* list page. The subscriptions are displayed on the *Subscriptions* tab. 

To create new report subscriptions, perform the following steps:

1. Select the required campaigns from the *Campaigns* list page. 

![1577](https://files.readme.io/184feee-Campaign_report_1.png "Campaign report 1.png")

2. Click the **Subscribe to Reports** link from the campaigns list page. The *Campaign Summary Emails* screen displays. 
3. From the setup tab, select the required options and click **Send Report**. 
4. Your existing subscription to reports is displayed on the *Subscriptions* tab.  

![561](https://files.readme.io/c1340f7-Campaigns_Report_subscribe_tab.png "Campaigns_Report_subscribe_tab.png")

# Edit or Delete Reports

The existing schedule for the reports is displayed on the *Subscriptions* tab. 

1. To edit or delete a subscription to a report,  click **Subscribe to Reports** on the campaign list page. The *Campaign Summary Emails* screen displays.
2. Click the vertical ellipsis. 

![567](https://files.readme.io/3a97128-Campaign_report_2.png "Campaign report 2.png")

3. Click **Edit** or **Delete** to make changes to a report subscription.

![568](https://files.readme.io/90ad733-Campaign_report_3.png "Campaign report 3.png")

# Reports API

You can [get the campaign report API](https://developer.clevertap.com/docs/get-campaign-report-api) to programmatically generate campaign reports for your consumption.

# Campaign Report Data 

The following table provides all columns part of the report based on the selected data group. For example, the first column Campaign ID will be part of each report, irrespective of the data group. However, the campaign name will display as a column in your report, only if you select *Campaign overview* while requesting the report.

<Table align={["left","left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Report Column
      </th>

      <th>
        Campaign Overview
      </th>

      <th>
        Campaign Stats
      </th>

      <th>
        Campaign Detailed stats
      </th>

      <th>
        Campaign Errors
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Campaign ID
      </td>

      <td>
        Yes
      </td>

      <td>
        Yes
      </td>

      <td>
        Yes
      </td>

      <td>
        Yes
      </td>

      <td>
        The unique ID for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Name
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The name provided for the campaign during its creation.
      </td>
    </tr>

    <tr>
      <td>
        Channel
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The channel such as email, mobile push, that is used for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Delivery
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The campaign delivery such as action, inaction, one time, and so on.
      </td>
    </tr>

    <tr>
      <td>
        Type
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The type of campaign such as single message, message on user property, or A/B test.
      </td>
    </tr>

    <tr>
      <td>
        Variant
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The message variant. Applicable only to A/B test messages and message on user property.
      </td>
    </tr>

    <tr>
      <td>
        OS
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The device operating system, such as iOS and Android.
      </td>
    </tr>

    <tr>
      <td>
        Device
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Devices such as mobile, TV, or a Tablet.
      </td>
    </tr>

    <tr>
      <td>
        DND / Set Campaign Frequency
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        DND or campaign frequency setting configured at the time of campaign creation.
      </td>
    </tr>

    <tr>
      <td>
        Timezone
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Configuration for the delivery in the user timezone.
      </td>
    </tr>

    <tr>
      <td>
        Cutoff
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Configuration of the cutoff period after which the campaign is not delivered.
      </td>
    </tr>

    <tr>
      <td>
        FCAP (global campaign limits)
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Configuration for the  maximum number of messages that a user can receive in a day.
      </td>
    </tr>

    <tr>
      <td>
        Throttle
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Configuration for the  throttle limits applied to the campaigns.
      </td>
    </tr>

    <tr>
      <td>
        Safety Check Limit
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The campaign is not sent to any user if the number of qualified users exceed the limit.
      </td>
    </tr>

    <tr>
      <td>
        Campaign per Day Limit
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Number of maximum messages sent per day for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Overall Limit
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Number of maximum messages sent overall for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Estimated Reach
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Estimated qualification of users.
      </td>
    </tr>

    <tr>
      <td>
        Reach (Send to all / last active)
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Send to all devices or the last active device.
      </td>
    </tr>

    <tr>
      <td>
        Who Query
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The who query defined in the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Constant Event Property
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Shows whether the constant event property is applicable or not.
      </td>
    </tr>

    <tr>
      <td>
        Title
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The title of the notification.
      </td>
    </tr>

    <tr>
      <td>
        Message
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Message of the notification.
      </td>
    </tr>

    <tr>
      <td>
        iOS Rich Media Type
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Media type such as, single or carousel for iOS push notifications.
      </td>
    </tr>

    <tr>
      <td>
        iOS Rich Media URL
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Image URL for iOS push notifications.
      </td>
    </tr>

    <tr>
      <td>
        iOS Sound File
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        iOS sound or the file URL if custom.
      </td>
    </tr>

    <tr>
      <td>
        iOS Badge Count
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Badge count on iOS notification.
      </td>
    </tr>

    <tr>
      <td>
        iOS Category
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Category for iOS push notifications (if applicable).
      </td>
    </tr>

    <tr>
      <td>
        iOS Deep Link / External URL
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Deep link for iOS push notifications.
      </td>
    </tr>

    <tr>
      <td>
        iOS Mutable Content
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Shows whether the content is mutable. The values are Yes/No.
      </td>
    </tr>

    <tr>
      <td>
        Android Subtitle
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Subtitle of the Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Android Image URL
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Image URL for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Android Summary
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Summary text for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Android Large Icon URL
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Large icon for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Android Small App Icon Color
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Small app icon for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Android Deep Link / External URL
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Deep link for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Android Sound File
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The values are:

        * NA 
        * Default OS sound
        * file URL, if the file is custom
      </td>
    </tr>

    <tr>
      <td>
        Android Notification Tray Priority
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Shows the priority of display in tray of android device.
      </td>
    </tr>

    <tr>
      <td>
        Android Notification Delivery Priority
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Server priority for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Collapse Notification
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Shows whether the notification is collapsible or not.
      </td>
    </tr>

    <tr>
      <td>
        Notification Channels
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Communication channel, for which the user consent is received.
      </td>
    </tr>

    <tr>
      <td>
        Badge ID
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Badge ID for Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Badge Icon
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Badge count Android push notifications.
      </td>
    </tr>

    <tr>
      <td>
        Send to App Inbox as Well
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Applicable only for push. Sent to app inbox as well or not.
      </td>
    </tr>

    <tr>
      <td>
        Time to Live
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Time for the notification to live in the user device.
      </td>
    </tr>

    <tr>
      <td>
        SMS / Email / WA Service Provider
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The service provider.
      </td>
    </tr>

    <tr>
      <td>
        Start Date
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Start date of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Start Time
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Displays the start time of the campaign. Displays the time value if the campaign is set to best time.
      </td>
    </tr>

    <tr>
      <td>
        Conversion Event
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The conversion is tracked for this event in the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Conversion Time (in minutes)
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Time period within which conversion is tracked for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Campaign URL
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The URL of the campaign to access it on Clevertap dashboard.
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Current status of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Created By
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The creator of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Created Time
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Time of creating the campaign.
      </td>
    </tr>

    <tr>
      <td>
        Labels
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        The Labels / tags used to identify and organize campaigns.
      </td>
    </tr>

    <tr>
      <td>
        AmplifiedByInbox
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Shows whether the campaign was amplified by sending it to inbox as well or not.
      </td>
    </tr>

    <tr>
      <td>
        AmplifiedByPush
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        If push amplification is applied or not.
      </td>
    </tr>

    <tr>
      <td>
        Web Priority
      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Priority of web notifications. It can be high, medium, or low.
      </td>
    </tr>

    <tr>
      <td>
        Run Date
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Applicable for day-wise reports only. Displays the run date.
      </td>
    </tr>

    <tr>
      <td>
        Total Sent (users)
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Displays the total count for the sent users. Shows as N/A for channels that are not supported, such as in-app.
      </td>
    </tr>

    <tr>
      <td>
        Total Viewed (users)
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Displays the total count for the users who viewed the notification.
      </td>
    </tr>

    <tr>
      <td>
        Total Clicked (users)
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Displays the total count for the users who clicked the notification.
      </td>
    </tr>

    <tr>
      <td>
        Total Sent (events)
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total events. Total devices (if *Send to all* is applied).
      </td>
    </tr>

    <tr>
      <td>
        Total Viewed (events)
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total events. Total devices (in case of *Send to all* is applied).
      </td>
    </tr>

    <tr>
      <td>
        Total Clicked (events)
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total events. Total devices (in case of *Send to all* is applied).
      </td>
    </tr>

    <tr>
      <td>
        Errors
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Errors.
      </td>
    </tr>

    <tr>
      <td>
        Click Through Conversions
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total converting users (as per funnel, including clicked step).
      </td>
    </tr>

    <tr>
      <td>
        Click Through Conversions %
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total converting users / Total sent users.
      </td>
    </tr>

    <tr>
      <td>
        Click Through Conversion Revenue
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Revenue as per the revenue property related to Total conversions.
      </td>
    </tr>

    <tr>
      <td>
        Total Control Group Count
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total number of users in control group.
      </td>
    </tr>

    <tr>
      <td>
        Total Control Group Conversions
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total number of control group users converting.
      </td>
    </tr>

    <tr>
      <td>
        Total Control Group Conversions %
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Total number of control group users converting / Total number of users in control group.
      </td>
    </tr>

    <tr>
      <td>
        Total Control Group Revenue
      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Revenue as per revenue property related to conversion.
      </td>
    </tr>

    <tr>
      <td>
        Unique Sent (users)
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Unique users who were sent notification.
      </td>
    </tr>

    <tr>
      <td>
        Unique Viewed Within Conversion Time
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Unique users who viewed the notifications within the set conversion time.
      </td>
    </tr>

    <tr>
      <td>
        Unique Clicked Within Conversion Time
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Unique users who clicked the notifications within set conversion time.
      </td>
    </tr>

    <tr>
      <td>
        Unique Converted Within Conversion Time
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Unique users who converted  within the set conversion time.
      </td>
    </tr>

    <tr>
      <td>
        Revenue Within Conversion Time
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Revenue as per the revenue property related to conversion.
      </td>
    </tr>

    <tr>
      <td>
        View Through Conversions
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Users who were sent a message and they converted. Referred as influenced conversions on the dashboard.
      </td>
    </tr>

    <tr>
      <td>
        View Through Conversions %
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Influenced conversion (above) / Total sent users.
      </td>
    </tr>

    <tr>
      <td>
        View Through Conversions Revenue
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Revenue as per the revenue property related to conversion.
      </td>
    </tr>

    <tr>
      <td>
        System Control Group Conversions
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of system control group users converting.
      </td>
    </tr>

    <tr>
      <td>
        System Control Group Conversions %
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of system control group users converting / Total number of users in system control group.
      </td>
    </tr>

    <tr>
      <td>
        System Control Group Revenue
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Revenue as per the revenue property related to conversion.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Control Group Conversions
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of campaign control group users converting.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Control Group Conversions %
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of campaign control group users converting / Total number of users in campaign control group.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Control Group Revenue
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Revenue as per the revenue property related to conversion.
      </td>
    </tr>

    <tr>
      <td>
        Custom Control Group Conversions
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of custom control group users converting.
      </td>
    </tr>

    <tr>
      <td>
        Custom Control Group Conversions %
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of custom control group users converting / Total number of users in custom control group.
      </td>
    </tr>

    <tr>
      <td>
        Custom Control Group Revenue
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Revenue as per the revenue property related to conversion.
      </td>
    </tr>

    <tr>
      <td>
        Custom Control Group Name
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Name of the custom control group.
      </td>
    </tr>

    <tr>
      <td>
        System Control Group Count
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of users in system control group.
      </td>
    </tr>

    <tr>
      <td>
        Custom Control Group Count
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of users in custom control group.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Control Group Count
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>

      </td>

      <td>
        Total number of users in campaign control group.
      </td>
    </tr>

    <tr>
      <td>
        Invalid FCM Key
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        App Uninstalled (Android)
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Wrong FCM API key
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Invalid APNS Certificate
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Error
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Format Error
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Account Temporarily Blacklisted
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        App Uninstalled (iOS)
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Invalid Profiles
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Duplicate APNS Token
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Invalid Token - FCM
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Unknown Error - FCM
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Dispatch Error
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Internal Error Due to Amplification
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Global Frequency Cap Exceeded
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Frequency Cap Exceeded
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Limit Reached for Day
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Limit Reached for Run
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Profile Not Reachable
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Stopped
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        User DND
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Duplicate Profile for Channel
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Bad Topic Error
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Disallowed Topic
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Bad Device Token
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Device Token and Topic Mismatch
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Inactive Device Token for Topic
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Wrong Environment Certificate
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Bad Certificate
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Idle Timeout
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Missing Certificate Topic
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        APNS Bad Priority
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        FCM Payload Too Large
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        User Not Reachable
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        User Not Qualified
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Notification during Campaign DND
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Cut-off Time Reached
      </td>

      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Yes
      </td>

      <td>
        Campaign error description.
      </td>
    </tr>
  </tbody>
</Table>
