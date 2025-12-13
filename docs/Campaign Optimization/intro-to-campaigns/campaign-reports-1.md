---
title: Campaign Reports_WIP
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
You can view comprehensive reports for all campaigns you send out of CleverTap. You can use these reports to analyze campaign performance, compare performance across campaigns, and understand engagement trends.

Campaign reports allow monitoring campaign performance at a glance. You can mail either a summary report of all campaigns sent out in a particular date range or even split it by day. This report includes metrics, such as campaign deliveries, engagements, conversions, and errors. To optimize dashboard performance, the data in the report is cached and you could receive data that has been generated up to 4 hours earlier. Also, it’s possible that the report is sent to you within 6 hours depending on the other activities happening at the time of requesting the report.

# Generate Reports

You can view the campaigns from the campaigns list page. Follow the steps to view a report:

1. Click Campaigns from the main menu. The Campaign List page appears.
2. Select the campaigns for the report or select the filter criteria.
3. Click the Email Report icon or Subscribe to Reports icon. The Campaign Summary Emails pane appears.

![1068](https://files.readme.io/be30a03-Campaigns_Report_Main.png "Campaigns_Report_Main.png")

3. Setup the campaign report. Select the report criteria. 

<Image title="Campaigns_Report_Setup_tab.png" alt={564} className="border" width="80%" border={true} src="https://files.readme.io/7092227-Campaigns_Report_Setup_tab.png" />

* Create a report for  - Select a report for the following:
* Selected Campaigns - Generates reports only for the campaigns selected from the list. 
* All campaigns with filters applied - Generates report for all the campaigns displayed after applying filters on the campaigns list page. 
* Data to include - Determine what data to include in the report. 
* Campaign Overview - Provides an overview of all the campaigns in the report. 
* Campaign stats - Provides important stats for the selected campaigns such as 
* Campaign detailed stats - Shows all campaign-related stats, such as total campaigns sent, the total number of devices, and so on. 
* Campaign errors - Displays all the campaign errors. 
* Split all data by - Split data by the required parameters.
* Day - Shows reports by each day. 
* OS - Shows reports by OS, that is Android and iOS.
* Variant type - Shows report by the variant type for AB test campaigns.
* Frequency - Displays report based on the selected frequency. 
* One-time - Sends report only once. 
* Recurring - Sends recurring reports on the selected days or dates. 

4. You can have a one-time report or a recurring report and subscribe to it, based on the selected frequency.\
   For a report subscription, you are redirected to the Subscribe tab.  The report is emailed to you on the selected days.

This report summarizes data on all campaigns that were sent out the previous week in CleverTap.

# Subscribe Reports

You may want to subscribe to a report in various scenarios. For example, select and subscribe to 4 campaigns on a monthly recurrence, or only subscribe to push campaigns that you created with a label for a monthly/daily recurrence.

To view your existing subscriptions, click the Subscribe to Reports link from the Campaigns list page. The subscriptions are displayed on the Subscriptions tab. 

To create new report subscriptions, follow the steps:

1. Select the required campaigns from the Campaigns list page. 

![1065](https://files.readme.io/ad91c14-Campaigns_Report_subscribe_link.png "Campaigns_Report_subscribe_link.png")

2. Click the Subscribe to Reports link from the campaigns list page. The Campaign Summary Emails page appears. 
3. From the setup tab, select the required options and click Send Report. 
4. Your existing subscription to reports is displayed on the Subscribe tab.  

![561](https://files.readme.io/c1340f7-Campaigns_Report_subscribe_tab.png "Campaigns_Report_subscribe_tab.png")

# Edit/Delete Reports

The existing schedule for the reports is displayed on the Subscribe tab. 

1. To edit or delete a subscription to a report,  click **Subscribe to Reports** on the campaign list page. The Campaign Summary Emails pane appears.
2. Click the ellipsis icon to edit or delete a report subscription.

![1070](https://files.readme.io/d9e23ef-Campaigns_Report_subscribe_delete_edit.gif "Campaigns_Report_subscribe_delete_edit.gif")

# Reports API

You can use the [Get Campaign Report API](https://developer.clevertap.com/docs/get-campaign-report-api) to programmatically generate campaign reports for your consumption.

# Campaign Report Data 

The following table provides all columns that will be part of the report, based on the selected data group. For example, the first column Campaign ID will be part of each report, irrespective of the data group. However, the campaign name will appear as a column in your report, only if you select 'Campaign overview' while requesting the report.

<Table align={["left","left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Report Column
      </th>

      <th>
        Campaign overview
      </th>

      <th>
        Campaign stats
      </th>

      <th>
        Campaign detailed stats
      </th>

      <th>
        Campaign errors
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
        The channel such as Email, Mobile Push, and so on that is used for the campaign.
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
        The campaign delivery such as Action, Inaction, One time, and so on.
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
        DND / set campaign frequency
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
        timezone
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
        cutoff
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
        fcap (global campaign limits)
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
        throttle
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
        Safety check limit
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
        Campaign per day limit
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
        Campaign overall limit
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
        estimated reach
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
        WHO query
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
        Constant event property
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
        Shows whether the Constant event property is applicable or not.
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
        The title of the notification
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
        iOS Rich Media type
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
        Media type such as, Single or Carousel for iOS push notifications
      </td>
    </tr>

    <tr>
      <td>
        IOS Rich media URL
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
        Image URL  for iOS push notifications
      </td>
    </tr>

    <tr>
      <td>
        IOS sound file
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
        IOS Badge Count
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
        Badge count on IOS notification
      </td>
    </tr>

    <tr>
      <td>
        IOS Category
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
        IOS Deep link / External URL
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
        IOS Mutable content
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
        Android large Icon URL
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
        Android Small App Icon colour
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
        Android Deep link / External URL
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
        * file URL,  if the file is custom
      </td>
    </tr>

    <tr>
      <td>
        Android Notification tray priority
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
        Shows the priority of display in tray of android device
      </td>
    </tr>

    <tr>
      <td>
        Android Notification delivery priority
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
        Server priority for Android push notifications
      </td>
    </tr>

    <tr>
      <td>
        Collapse notification
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
        Shows whether the notification is collapsible or not
      </td>
    </tr>

    <tr>
      <td>
        Notification channels
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
        Send to App Inbox as well
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
        Time to live
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
        SMS/ Email/ WA service provider
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
        Created time
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
        Priority of web notifications. It can be High, Medium or low.
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
        Applicable for Day-wise reports only. Displays the run date.
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
        Displays the total count for the sent users. Shows as N/A for channels that are not supported, such as In-app.
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
        Total events. Total devices (if 'Send to all' is applied)
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
        Total events. Total devices (in case of 'Send to all' is applied)
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
        Total events. Total devices (in case of 'Send to all' is applied)
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
        Errors
      </td>
    </tr>

    <tr>
      <td>
        Click through conversions
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
        Total converting users ( as per funnel, including clicked step)
      </td>
    </tr>

    <tr>
      <td>
        Click through conversions %
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
        Click through conversion revenue
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
        Total control group count
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
        Total control group conversions
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
        Total control group conversions %
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
        Total control group revenue
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
        Unique users who were sent notification
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
        View through Conversions
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
        View through Conversions %
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
        Influenced conversion (above) / Total sent users
      </td>
    </tr>

    <tr>
      <td>
        View through conversions Revenue
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
        Total number of campaign control group users converting
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
        Revenue as per the revenue property related to conversion
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
        Custom Control Group count
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
        Campaign Control Group count
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
        Invalid FCM key
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
        App uninstalled(Android)
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
        Invalid APNS certificate
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
        APNS error
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
        APNS Format error
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
        App Uninstalled(iOS)
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
        Invalid token - FCM
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
        Unknown error - FCM
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
        Dispatch error
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
        Internal error due to amplification
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
        Global frequency cap exceeded
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
        Campaign frequency cap exceeded
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
        Campaign limit reached for day
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
        Campaign limit reach for run
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
        Profile not reachable
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
        Campaign stopped
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
        Duplicate profile for channel
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
        APNS bad topic error
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
        APNS disallowed topic
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
        APNS bad device token
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
        APNS device token and topic mismatch
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
        APNS inactive device token for topic
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
        APNS wrong environment certificate
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
        APNS bad certificate
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
        APNS idle timeout
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
        APNS missing certificate topic
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
        FCM payload too large
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
        User not reachable
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
        User not qualified
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
        Notification during campaign DND
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
        Campaign cut-off time reached
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
