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

> 📘 Supported Partners for Export Status
>
> Currently, we provide events export status for Amazon S3, Microsoft Azure, and Google Cloud Platform (GCP) partners only.

This document further explains the prerequisites, how to enable and disable export status alerts, and track and monitor them.

# Prerequisite

Ensure you integrate with the preferred technology partners:

* [Amazon S3](https://docs.clevertap.com/docs/aws-s3-export)
* [Google Cloud Platform (GCP)](https://docs.clevertap.com/docs/data-export-to-gcp)
* [Microsoft Azure](doc:microsoft-azure)

# Setup

This procedure involves the following major steps:

1. [Set up a Webhook](https://docs.clevertap.com/docs/setup-webhooks)
2. [Enable Status Alerts for Exports on CleverTap Dashboard](doc:status-alerts-for-exports#enable-status-alerts-for-exports)  
   OR
3. [Add or Modify the Webhook](doc:status-alerts-for-exports#add-or-modify-the-webhook)

## Enable Status Alerts for Exports

To enable status alerts for exports:

1. On the CleverTap dashboard, go to _Settings_ > _Partners_ > _Exports center_.

<Image align="center" alt="Exports center" border={true} caption="Exports center" src="https://files.readme.io/fa86e8d47bcd6a79e7e231bf6fd4833202cc60b759573e456f07a8aa63ba557b-image.png" />

2. Click the **Manage Status Alerts** button in the top right corner. The **Manage Status Alerts** window appears.

<Image align="center" border={true} width="90% " src="https://files.readme.io/8037095-image.png" className="border" />

2. Toggle on the **Enable the status to get notified about exports** switch to enable the status alerts.
3. Click **Save**.

> 📘 Note
>
> Once enabled, the export status tracking is applied to both existing and new export creations.

## Disable Status Alerts for Exports

To disable status alerts for exports:

1. Toggle off the **Enable the status to get notified about exports** switch.
2. Click **Save**.

## Add or Modify the Webhook

If required, edit the Webhook as follows:

1. On the **Exports** page, Click the **Manage Status Alerts** button in the top right corner. The **Manage Status Alerts** window appears.
2. On the **Enable export status alerts** pane, you can either create a new URL or use the existing one.

* To use an existing Webhook URL, select one of the preferred Webhook URLs from the **Webhook name** drop-down list.
* If required, to create a new Webhook URL, click the **Add webhook** link.  
  For more information about creating Webhook URLs, refer to the [Webhooks](https://docs.clevertap.com/docs/setup-webhooks) documentation. Once you create a new Webhook, click the **Refresh** icon for the new Webhook to appear here.

3. Click **Save**.

> 📘 Note
>
> We only support a POST Webhook.

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
        Status of the export process. For example, Initiated or Completed.

        <li>**One-time**: a one-time export is initiated and completed just once.</li><li>**Recurring**: a recurring export is initiated and completed repeatedly at set intervals or schedules.</li>
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
