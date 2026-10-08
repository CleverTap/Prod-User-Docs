---
title: Analytics Alerts
excerpt: >-
  Learn how to set up continuous metric monitoring and receive instant
  notifications when anomalies or threshold breaches occur in your analytics
  data.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: noindex
---
# Overview

Alerts in Analytics is a continuous monitoring feature in CleverTap that notifies you when a metric on a trendline behaves unexpectedly. Instead of checking dashboards manually, you set up an alert once, and CleverTap evaluates the metric on the specified conditions on an hourly, daily, weekly, or monthly basis and notifies you when a condition is met.

This feature is available on Trends charts and supports the following metrics:

- Total Events
- Unique Users

## Alert Types

You can choose between two alert types:

- **Anomaly alerts**: Triggered when the metric deviates from its expected range, as determined by CleverTap's seasonality-aware detection model.
- **Threshold alerts**: Triggered when the metric crosses a fixed value or changes by a defined percentage relative to the same period last week.

When an alert is triggered, CleverTap delivers notifications based on the selected delivery options, such as a Dashboard Notification, Email, or a Slack channel.

# Alerts Evaluation Process

When you create an alert, CleverTap saves the event, filters, and metric you are monitoring as the alert's query. CleverTap then runs this query automatically at the schedule you set.

Each time CleverTap evaluates the alert, it does the following:

- Fetches the latest metric data for the monitored event and segment.
- Runs the detection logic (anomaly or threshold) against the latest data.
- Triggers a notification if the condition is met and delivers it to your chosen notification channels.

<Callout icon="💡" theme="default">
  ### Tip

  Choose the alert type that suits your metric. Use _anomaly alerts_ for metrics that change frequently and unpredictably. Use _threshold alerts_ when you have a specific value or percentage change in mind that you always want to know about.
</Callout>

# Prerequisites

Before you create an alert, make sure you meet the following requirements:

- You have access to the CleverTap Analytics module.
- You have a Trends chart configured with at least one supported metric (Event count or Unique users).
- To send alerts to Slack, a user with admin access must first connect your project to Slack. For more information, refer to [Connect Slack](doc:alerts#connect-slack).

# Create an Alert

You can create an alert directly from a Trends chart. ​

To create an alert:

1. Go to _Analytics_ > _Trends Beta_ and view a Trends analysis.
2. Hover over a data point on the trendline you want to monitor, then click the + icon to view the selection options.
3. Click **Create alert**.


<Image src="https://files.readme.io/c6e328875aa68607e42a14a7a4c38e53c7eebdf4495322157d7a0a3f47fe6749-image.png" align="center" caption="Create Alert from a Trendline Data Point" border={true} />


The **Create Alert** window opens, which follows the following two-step process:

1. [Criteria](doc:alerts#criteria)
2. [Delivery Options](doc:alerts#delivery-options)

## Criteria

The **Criteria** step lets you name the alert and define the condition that triggers it. This step lets you define what to monitor and how to detect a condition.


<Image src="https://files.readme.io/1dd0255d9fe3a48f9e0b85cf16983288a1cb999f541cce691a9497448b5a85cc-image.png" align="center" caption="Define Alert Criteria" border={true} />


The following fields appear in this step:

<Table>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Name
      </td>

      <td>
        A label for the alert. Choose a name that clearly describes what is being monitored. For example, _the charged event drop for weekdays_.
      </td>
    </tr>

    <tr>
      <td>
        Event trigger
      </td>

      <td>
        The event and filter conditions that are being monitored. This field is pre-populated from the trendline you selected on the Trends chart and cannot be edited in the window. For example, if you selected a data point on a _Charged_ event trendline filtered by _Count greater than or equal to 1_, those details appear here automatically.
      </td>
    </tr>

    <tr>
      <td>
        Alert trigger
      </td>

      <td>
        The type of detection to apply. You can select the following two Alert trigger types:

        - **Anomaly**: Triggers when the metric deviates from its statistically expected range. Choose Anomaly when you want open-ended monitoring, meaning you do not need to know in advance what value constitutes a problem. CleverTap uses historical data and seasonal patterns to calculate an expected range for the metric, including a margin of error, and triggers the alert when the metric falls outside that range.

          For example,**&#x20;**&#x79;our _App Launch_ event typically records between 80,000 and 100,000 app launches on weekdays. On a Tuesday, app launches drop to 42,000. CleverTap recognizes this falls outside the expected range and triggers the alert.
        - **Threshold**: Triggers when the metric crosses a fixed value or percentage change. Choose Threshold when you have a specific value or percentage change in mind that you always want to know about. The alert triggers when the metric crosses the threshold value or percentage you define.

          For example, you want to know whenever your _Charged_ event total drops more than 20% compared to the same weekday last week. You set the condition to _Decreases by (%)_ and the value to _20_. If the previous Tuesday's total was 5,000 and the current Tuesday's total is 3,800 (a 24% decrease), the alert triggers. If the total for Tuesday is 4,200 (a 16% decrease), no alert is triggered.
      </td>
    </tr>

    <tr>
      <td>
        Scan mode _(Anomaly only)_
      </td>

      <td>
        The detection mode that CleverTap applies. It determines how much historical data CleverTap uses to build the expected value baseline. Choose the mode based on how stable or seasonal your metric is.

        For more information, refer to [Scan Mode](doc:anomaly-detection#scan-mode).
      </td>
    </tr>

    <tr>
      <td>
        Confidence interval _(Anomaly only)_
      </td>

      <td>
        The certainty level CleverTap uses to define the expected range, such as 99%, 95%, or 90%. A higher percentage widens the expected range, so fewer deviations trigger the alert.

        For more information, refer to [Confidence Interval](doc:anomaly-detection#confidence-interval).
      </td>
    </tr>

    <tr>
      <td>
        Alert for (Anomaly only)
      </td>

      <td>
        Controls which direction of deviation triggers the alert. The following options are available:

        - **Spike**: Triggers an alert only when the metric exceeds the upper bound of the expected range.
        - **Drop**: Triggers an alert only when the metric falls below the lower bound of the expected range.
        - **Both**: Triggers an alert on both upward and downward deviations.

        Use these options to reduce noise when you only care about one type of movement in your metric. For example,**&#x20;**&#x69;&#x66;**&#x20;**&#x79;ou monitor a _Payment Failed_ event and only care about spikes in failure&#x73;_, but&#x20;_&#x61; drop in failures is not a problem. Set an alert for _Spike_ so that naturally quieter periods do not generate false alerts.
      </td>
    </tr>

    <tr>
      <td>
        Trigger condition _(Threshold only)_
      </td>

      <td>
        The condition that must be met to trigger the alert. The following options are available:

        - **Above**: Triggers when the metric value exceeds the threshold.
        - **Below**: Triggers when the metric value drops below the threshold.
        - **Increases by (%)**: Triggers when the metric increases by at least X% compared to the same period last week.
        - **Decreases by (%)**: Triggers when the metric decreases by at least X% compared to the same period last week.
      </td>
    </tr>

    <tr>
      <td>
        Threshold value _(Threshold only)_
      </td>

      <td>
        The numeric value used in the trigger condition. Enter an absolute number for _Above_ o&#x72;_&#x20;Below_, or a percentage for _Increases by (%)_ or _Decreases by (%)_.
      </td>
    </tr>
  </tbody>
</Table>

After configuring the criteria, click **Next** to proceed to [Delivery Options](doc:alerts#delivery-options).

## Delivery Options

The Delivery Options step lets you configure how often CleverTap evaluates the alert and where to send the notifications.


<Image src="https://files.readme.io/fdc19d024c6f20774e1c638a68ab0336f2cac53bcc9a5346526c44b63ffc5f4c-image.png" align="center" caption="Set Up Delivery Options for Alerts" border={true} />


The following fields appear in this step:

<Table>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Alert frequency
      </td>

      <td>
        Determines how often CleverTap checks whether the alert condition is met. The following options are available:

        - **Hourly**: Evaluates once per hour, approximately 20 minutes after each hour closes.
        - **Daily**: Evaluates once per day at approximately 6:00 AM in your account's timezone.
        - **Weekly**: Evaluates once per week at approximately 6:00 AM on the first day of the new week in your account's timezone.
        - **Monthly**: Evaluates once per month at approximately 6:00 AM on the first day of the new month in your account's timezone.
      </td>
    </tr>

    <tr>
      <td>
        Delivery destination
      </td>

      <td>
        Defines where to send notifications. For example, Dashboard, Email, or Slack (You can also multi-select Slack channels).
      </td>
    </tr>

    <tr>
      <td>
        Email recipients
      </td>

      <td>
        The email addresses to notify. You are added automatically as a recipient.
      </td>
    </tr>

    <tr>
      <td>
        Slack channels _(if Slack is connected)_
      </td>

      <td>
        The Slack channel that receives the alert. Select from the available channels that the CleverTap bot has been invited to join. Slack delivery requires a one-time project-level Slack connection by an admin. If Slack is not connected, a **Connect Slack** button appears instead of the channel picker.
      </td>
    </tr>
  </tbody>
</Table>

After configuring delivery options, click **Create** to save the alert.

<Callout icon="💡" theme="default">
  ### **Note**

  The 20-minute delay applies to hourly alerts only. It allows event data to fully settle before evaluation runs. For example, if you set an hourly alert with an evaluation window of 3:00 to 4:00 PM, CleverTap evaluates the metric at approximately 4:20 PM once that hour is fully closed.

  For all alert frequencies (hourly, daily, weekly, and monthly), CleverTap only evaluates complete, closed periods. It never evaluates a partial period. This is important when interpreting a metric value of 0. A value of 0 in a completed, evaluated period means no events occurred. It does not mean data has not arrived yet, because CleverTap waits for the period to close before running any evaluation.
</Callout>

# Manage Alerts

You can view, edit, pause, resume, and delete all alerts in your project from the **Manage Alerts** page.

To access Manage Alerts, go to _Settings_ > _Alerts_.


<Image src="https://files.readme.io/3ad8e36ba913f002df2406ce536d7b86e5e20dbbb04f90b55f9462b55a37b96e-image.png" align="center" caption="View Alerts on Manage Alerts" border={true} />


The Manage Alerts page shows a table with the following columns:

<Table>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Name
      </td>

      <td>
        The name you specified for the alert.
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        The current status of the alert. The following alert statuses are available:

        - **ACTIVE**:**&#x20;**&#x54;he alert is running and will evaluate at its next scheduled time.
        - **PAUSED**: The alert is not evaluating. Its configuration is preserved. You can resume it at any time.
        - **FAILING**: CleverTap was unable to evaluate the alert's condition successfully three or more consecutive times. You are notified by email when this happens.
      </td>
    </tr>

    <tr>
      <td>
        Alert trigger
      </td>

      <td>
        Whether the alert uses Anomaly or Threshold detection.
      </td>
    </tr>

    <tr>
      <td>
        Created By
      </td>

      <td>
        The email address of the person who created the alert.
      </td>
    </tr>

    <tr>
      <td>
        Created On
      </td>

      <td>
        The date the alert was created.
      </td>
    </tr>
  </tbody>
</Table>

## Edit

To edit an alert's criteria or delivery options:

1. On the Manage Alerts page, hover over the alert you want to edit.
2. Click the edit icon.
3. The _Edit alert_ window opens with your existing settings pre-filled.
4. Update the fields you want to edit.
5. Click **Save changes** to confirm.


<Image src="https://files.readme.io/92e4840eb85e2b4ed4736741cc7fb2ecb5e0940221ad12f57b19521fe1792c15-2026-07-27_18-13-05_1.gif" align="center" caption="Editing an Active Alert" border={true} />


## Pause

Pausing an alert temporarily stops it from evaluating. The alert configuration is preserved, and you can resume it later. Use this when you want to stop receiving alerts during a known period of unusual activity, such as a major product launch or a marketing campaign, without losing the alert configuration.

To pause an alert:

1. On the Manage Alerts page, hover over the alert you want to pause.
2. Click the ellipsis icon.
3. Click **Pause** from the list.
4. Click **Pause** to confirm.


<Image src="https://files.readme.io/84aa84dc8f2f5f59f587bfbd41da98c7a4e4b7f5381d8df36071ecab83692ce6-2026-07-27_18-11-47_1.gif" align="center" caption="Pausing an Active Alert" border={true} />


To resume a paused alert, follow the same steps and click **Resume** in the ellipsis menu.

## Delete

Deleting an alert permanently removes it and its notification settings. This action cannot be undone.

To delete an alert:

1. On the Manage Alerts page, hover over the alert you want to delete.
2. Click the ellipsis icon.
3. Click **Delete** from the list.
4. Click **Delete** to confirm.


<Image src="https://files.readme.io/705199421e05735aab327fda0954319d036c26eb2c7677ca5f4b6f272543f5f6-2026-07-27_18-12-08_1.gif" align="center" caption="Deleting an Active Alert" border={true} />


# Connect Slack

Connecting Slack allows any alert in your project to deliver notifications to a Slack channel. This is a one-time, project-level setup that requires admin access.

## Prerequisites for Slack Connection

- You must have admin access to your CleverTap project.
- You must have permission to install apps in your Slack workspace.

## Connect Your Slack Workspace

To connect Slack:

1. Open the _Delivery Options_ step from the _Create Alert_ window.
2. Click **Connect Slack**. You are redirected to Slack's authorization page to grant CleverTap the requested permissions.
3. Select or enter the name of your Slack workspace.
4. Click **Submit Request**.


<Image src="https://files.readme.io/a79146cc3627edb84c7d84c3c82f8afcff2d17e205e902fde0e611b78d363884-image.png" align="center" border={true} />


Once connected, any alert in your project can route notifications to any Slack channel to which the CleverTap bot has been invited.

# Project Limits

The following limits apply to Alerts:

| Limit                             | Value                              |
| --------------------------------- | ---------------------------------- |
| Active alerts per project         | 10                                 |
| Supported metrics                 | Total Events and Unique users only |
| Alert types                       | Anomaly and Threshold              |
| Threshold percent-change baseline | Same period last week only         |

<Callout icon="💡" theme="default">
  ### **Note**

  When you reach the 10-alert limit, the **Create alert** option is disabled. To create a new alert, go to **Manage Alerts** and delete or pause any active alerts first. Paused alerts do not count toward the 10-alert limit. Only alerts with **ACTIVE** status count against the project limit.
</Callout>

# FAQs

Find answers to the following common questions about Alerts in Analytics.

### What does the alert frequency control?

The alert frequency determines how often CleverTap evaluates the alert. Hourly evaluations check the metric every hour, daily evaluations check once per day, and so on. Choose a frequency that matches how quickly you need to respond to a change in the metric.

### What is the baseline for percentage-change threshold alerts?

The baseline is always the same period from the previous week. For example, if your alert evaluates on a Wednesday, CleverTap compares Wednesday's value to the previous Wednesday's value. This applies regardless of whether your alert frequency is set to Hourly, Daily, Weekly, or Monthly. The comparison always looks back to the equivalent period one week prior. Comparison with any other period, such as the previous day or month, is not supported. This keeps comparisons consistent with the weekly seasonality patterns common in most product metrics.

### Can I receive alerts on multiple channels at once?

Yes. You can select any combination of Dashboard, Email, and Slack as delivery destinations for each alert.

### What happens to Slack alerts if I disconnect Slack?

Slack delivery is paused on all existing alerts. Dashboard and email notifications for those alerts continue to trigger.

### Why is my alert showing as _FAILING_?

An alert enters **FAILING** status when CleverTap is unable to evaluate the alert's condition successfully three or more consecutive times. This can happen due to a temporary system error. You receive an email notification when this happens. If the alert continues to fail, contact [CleverTap Support](https://help.clevertap.com/en-US/clevertapsupport/tickets/create).

### I set an anomaly alert, but it is not triggering even though I can see a clear drop on my chart. Why?

The anomaly algorithm may not have flagged the drop if it falls within the expected range. Try editing the alert and lowering the Confidence Interval to 90%. This narrows the expected range and makes the alert more sensitive. For more information, refer to [Confidence Interval](doc:anomaly-detection#confidence-interval).

### Can I edit a monitored event or metric after creating an alert?

No. The event, filters, and metric are saved when the alert is created and cannot be changed afterward. To monitor a different event or metric, delete the existing alert and create a new one.

<br />
