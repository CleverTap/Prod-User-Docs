---
title: Status Alerts for Exports
excerpt: Understand how to monitor and track statuses for exports.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

CleverTap allows you to export data to third-party partners, such as Amazon Web Services (AWS), Google Cloud Platform (GCP), etc. You have the flexibility to choose between one-time data exports and recurring exports. Keeping track of export status is crucial, especially for recurring exports, as they are scheduled to run at regular intervals.

This feature allows you to monitor the status of your data exports via Webhook on your preferred systems. It provides alerts when an export is initiated or completed successfully. Status tracking allows for keeping track of your recurring exports and taking necessary decisions whenever required.

<Callout icon="📘" theme="info">
  ### Supported Partners for Export Status

  Currently, we provide events export status for Amazon S3 and Google Cloud Platform (GCP) partners only.
</Callout>

This document further explains the prerequisites, how to enable and disable export status alerts, and track and monitor them.

# Prerequisite

Ensure you integrate with the preferred technology partners:

* [Amazon S3](https://docs.clevertap.com/docs/aws-s3-configuration)
* [Google Cloud Platform (GCP)](https://docs.clevertap.com/docs/gcp-configuration)
* [Microsoft Azure](https://staging.docs.user.clevertap.net/docs/microsoft-azure-export)

# Setup

This procedure involves the following major steps:

1. [Set up a Webhook](https://docs.clevertap.com/docs/setup-webhooks)
2. [Enable Status Alerts for Exports on CleverTap Dashboard](https://staging.docs.user.clevertap.net/docs/status-alerts-for-exports#enable-status-alerts-for-exports)<br />OR
3. [Add or Modify the Webhook](https://staging.docs.user.clevertap.net/docs/status-alerts-for-exports#modify-the-webhook)

## Enable Status Alerts for Exports

To enable status alerts for exports:

1. On the CleverTap dashboard, go to _Settings_ > _Partners_ > _Exports_.


<Image src="https://files.readme.io/805c5d9-image.png" align="center" width="90% " border={true} />


2. Click the **Manage Status Alerts** button in the top right corner. The **Manage Status Alerts** window appears.


<Image src="https://files.readme.io/8037095-image.png" align="center" width="90% " border={true} />


2. Toggle on the **Enable the status to get notified about exports** switch to enable the status alerts.
3. Click **Save**.

<Callout icon="📘" theme="info">
  ### Note

  Once enabled, the export status tracking is applied to both existing and new export creations.
</Callout>

## Disable Status Alerts for Exports

To disable status alerts for exports:

1. Toggle off the **Enable the status to get notified about exports** switch.
2. Click **Save**.

## Add or Modify the Webhook

If required, edit the Webhook as follows:

1. On the **Exports** page, Click the **Manage Status Alerts** button in the top right corner. The **Manage Status Alerts** window appears.
2. On the **Enable export status alerts** pane, you can either create a new URL or use the existing one.

* To use an existing Webhook URL, select one of the preferred Webhook URLs from the **Webhook name** drop-down list.
* If required, to create a new Webhook URL, click the **Add webhook** link.<br />For more information about creating Webhook URLs, refer to the [Webhooks](https://docs.clevertap.com/docs/setup-webhooks) documentation. Once you create a new Webhook, click the **Refresh** icon for the new Webhook to appear here.

3. Click **Save**.

<Callout icon="📘" theme="info">
  ### Note

  We only support a POST Webhook.
</Callout>

## Sample Payload for Export Status

The JSON payload configured on the Webhook URL will be pushed to the user once the export begins or ends. The following is a sample JSON payload showing the export status received via the Webhook URL.

```json Sample Payload
{
"Export Request Id": 1690283492,
"Partner": "Google Cloud Storage",
"Type": "Events",
"Status": "Completed",
"Frequency": "One Time",
"Date and Time": "25/07/2023 4:50:52 PM"
}
```

The JSON payload contains the following parameters:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Parameters
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `Export Request Id`
      </td>

      <td>
        Unique identifier of the export request. For example, 1690283492.
      </td>
    </tr>

    <tr>
      <td>
        `Partner`
      </td>

      <td>
        Name of the export partner. An example is Google Cloud Platform (GCP).
      </td>
    </tr>

    <tr>
      <td>
        `Type`
      </td>

      <td>
        Type of export. For example, events.
      </td>
    </tr>

    <tr>
      <td>
        `Status`
      </td>

      <td>
        Status of the export process. For example, Initiated, Completed, or Awaiting Next Run.

        <li>**One-time**: a one-time export is initiated and completed just once.</li><li>**Recurring**: a recurring export is initiated and completed repeatedly at set intervals or schedules. Between two scheduled runs, a recurring export shows **Awaiting Next Run**, this means the export last succeeded and is waiting for its next scheduled run. This is distinct from **Pending**, which means the export has not run yet at all.</li>
      </td>
    </tr>

    <tr>
      <td>
        `Frequency`
      </td>

      <td>
        Interval at which the export operation occurs. For example, these intervals can be every 4, 8, 12, or 24 hours.
      </td>
    </tr>

    <tr>
      <td>
        `Date and Time`
      </td>

      <td>
        Date and time when the export operation is initiated or completed.
      </td>
    </tr>
  </tbody>
</Table>
