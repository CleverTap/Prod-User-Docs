---
title: Notify - Logs and Exports
excerpt: >-
  Learn how to track individual message deliveries and export log data for your
  Notify campaigns.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The _Logs_ tab provides a per-message delivery log for a specific Notify campaign, allowing you to trace individual API requests from receipt through final delivery.

The following image shows the _Logs&#x20;_&#x74;ab:


<Image src="https://files.readme.io/753dcbfec326af86413ccb291246388c2112d4758e5b4770b3d6331b886a4432-image.png" align="center" caption="Notify Logs" border={true} />

# Log Table

Each row in the Log table represents a single Notify API request and displays the following information:

| Column          | Description                                                                                                                                                                                       |
| :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Request ID      | The unique identifier for the individual Notify API request.                                                                                                                                      |
| Received At     | The date and time when CleverTap received the API request.                                                                                                                                        |
| Recipient ID    | The email ID of the message recipient.                                                                                                                                                            |
| Status          | The current delivery status of the request.                                                                                                                                                       |
| Time to Deliver | The time taken for successful delivery to the user, measured from when CleverTap received the request. This column is populated only if delivery callbacks are set up correctly for your account. |
| Failure Reason  | The reason the message could not be delivered, if applicable.                                                                                                                                     |

### Message Timeline

Expand any log entry to view the full message Timeline, a step-by-step trace of the message's journey, including the timestamp and stage label at each step.

The following image shows the Message Timeline:


<Image src="https://files.readme.io/1bd814923883d5d311ab62e368054b1b210ee0c801257ad0b3fa5e3a6eef0454-image.png" align="center" caption="Message Timeline" border={true} />


## Delivery Statuses

| Status                    | Description                                                                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Request Delivery Pending  | The request has been processed by CleverTap and sent to the provider. Delivery to the recipient by the service provider is pending.                        |
| Request Delivered         | The message was successfully delivered to the recipient.                                                                                                   |
| Request Processing Failed | The request failed either during CleverTap's internal processing or because the provider's endpoint could not accept the request.                          |
| Request Delivery Failed   | The message was sent to the provider, but could not be delivered to the recipient.                                                                         |
| Delivery Info NA          | Delivery status is unavailable for this request. This occurs when no delivery callback is received from the provider<br />within the expected time window. |

## Filter Logs

Use the _Filters_ panel to narrow results by the following:

- **Status**: Filter by one or more delivery statuses.
- **Time Period**: Select a date range to filter logs by the request received date.

<Callout icon="📘" theme="info">
  ### Log Data Availability

  Log data is available for the last 30 days. To access log data beyond this range, us&#x65;_&#x20;Log Exports_.
</Callout>

# Log Exports

The Notify page has two tabs: _List&#x20;_&#x61;nd _Log export._

- **List**: Displays all your Notify campaigns with their name, Notify ID, channel, status, start date, and creator. Use this tab to view, manage, and filter your campaigns. You can also select one or more campaigns from this tab to create a log export.

- **Log export**: Lets you export delivery log data across your Notify campaigns as a file. You can configure a one-time or recurring export, choose how the file is delivered, select the columns to include, and download the data in CSV or JSON format. Log exports are not limited to a single campaign. You can export data for selected campaigns or all campaigns at once.

To create a new export, go to the _List_ tab, select one or more campaigns, and click the **Export Logs&#x20;**&#x69;con in the action bar.

The following image shows the _Logs&#x20;_&#x74;ab:

<Image src="https://files.readme.io/b01bf0dc16c91506b4f000a5049e06cd2adef182b172fd0eeb6559845713e872-image.png" align="center" caption="Logs Tab" border={true} />


The following image shows the _Log export_ tab:


<Image src="https://files.readme.io/03f168496e347ec64b429119c77d5eca97357355257d6360ba94787f1cbcdee4-image.png" align="center" caption="Log Export Tab" border={true} />


### Create a Log Export

The _Notify Export_ dialog opens in two steps: **Details** and **Attributes**.

#### Details

Configure the following fields in the _Details_ section:

| Field                | Description                                                                                                                                                                                                                                                                                                |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                 | Enter a name for the export.                                                                                                                                                                                                                                                                               |
| Create an export for | Select _All Notify_ to export logs for all your Notify campaigns, or select _Selected Notify_ to export logs only for the campaigns you selected from the List view.                                                                                                                                       |
| Frequency            | Select _One time&#x20;_&#x66;or a single export, or _Recurring_ for a scheduled export that runs automatically on your preferred day.                                                                                                                                                                      |
| Delivery             | Select _Email_ to receive the export file by email, or _Partner Export_ to send it to a cloud storage bucket. If you select _Partner Export_, choose the cloud provider from the dropdown (Amazon S3 or Google Cloud) and select a bucket from the _Select Bucket_ dropdown.                               |
| File format          | Select **CSV** or **JSON&#x20;**&#x61;s the export file format. JSON is only supported for Partner Export (Amazon S3 or Google Cloud).                                                                                                                                                                     |
| File path            | Displayed when **Partner Export** is selected. Shows the storage path where the file is written, in the following format:<br />`<bucketName>/<accountId>/notify_exports/<export_name>.csv.gz`<br />For example: `export-testing-bucket/1656678144/notify_exports/recurring_daily_s3_csv_1788208725.csv.gz` |

<Callout icon="📘" theme="info">
  ### Note

  If the required cloud credentials are not yet configured, a warning message appears prompting you to add credentials. Click **Add Credentials** to go to the credentials configuration page. After adding credentials, click the refresh icon to reload the bucket list.
</Callout>

The following image shows the _Details&#x20;_&#x73;ection of the Log Export:


<Image src="https://files.readme.io/62125f50564371b19cee4da67c6ec53e58cd0b6a1d3178fdc9bb5f6eaae89655-image.png" align="center" caption="Log Export- Details" border={true} />


Click **Next** to proceed to the _Attributes_.

#### Attributes

Th&#x65;**&#xA0;**_Attributes_ section lists all available columns for the export file. All columns are selected by default. Uncheck any columns you do not want to include, or click **Deselect all** to clear all selections and choose only the attributes you need in the log export.

The following columns are available:

| Column         | Description                                                                                                      |
| -------------- | ---------------------------------------------------------------------------------------------------------------- |
| Notify ID      | The unique identifier of the Notify campaign.**&#x20;**&#x54;his is a standard column that cannot be deselected. |
| Request ID     | The unique identifier for the individual API request. This is a standard column that cannot be deselected.       |
| Failure reason | The reason a message could not be delivered, if applicable.                                                      |
| Channel        | The communication channel used for the message, for example, Email or SMS.                                       |
| Time           | The timestamp of the specific message status, for example, when the message was processed or delivered.          |
| Recipient ID   | The email ID or phone number of the message recipient.                                                           |
| Message status | The delivery status of the message.                                                                              |

Click **Create Export** to generate the export. The export is created and appears in the _Log export&#x20;_&#x6C;isting.

The following image shows the _Attributes&#x20;_&#x73;ection of the Log Export:


<Image src="https://files.readme.io/db763e08090c36390f85a0a275e4595681366ce567bb4daf03231bf25c6ca064-image.png" align="center" caption="Log Export- Attributes" border={true} />


The following image shows a sample export file with the selected attributes populated:


<Image src="https://files.readme.io/cd510b8d3cbcf534ac281b2c4e55fe1b8dbe7dfa2b0f31e33e8c33eae25cb447-image.png" align="center" caption="Sample Export" border={true} />


### View and Manage Log Exports

The _Log export_ tab displays all exports created for your Notify campaigns. The following image shows the listing of the Log Exports:<br />


<Image src="https://files.readme.io/dddfaf2089e31c5f1a6d293a063d5e5f02ddb85ce4d8f8cd31f002076f09f0a5-image.png" align="center" caption="Log Export List" border={true} />


Each row in the listing shows the following information:

| Column      | Description                                                                                                                                |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Name        | The name of the export, along with its unique export ID.                                                                                   |
| Format Type | The export file format: CSV or JSON.                                                                                                       |
| Partner     | The cloud storage partner used for delivery, for example,<br />Amazon S3 or Google Cloud. Displays _NA_ when the delivery method is Email. |
| Frequency   | Indicates whether the export is one-time or Recurring.                                                                                     |
| Status      | The current state of the export. Possible values are Running, Awaiting Next Run, Completed, and Stopped.                                   |
| Created by  | The email ID of the user who created the export.                                                                                           |
| Created on  | The date and time when the export was created.                                                                                             |

You can perform the following actions on an export from the listing:

| Action | Description                                                                                                                                 |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Edit   | For recurring exports, you can edit the export name and frequency. The delivery method and other settings cannot be changed after creation. |
| Stop   | Stops a recurring export. Once stopped, all future runs for this export are stopped.                                                        |

You can search for a specific export by name or ID using the search bar. Use the filter icon to narrow results by additional criteria.


<Image src="https://files.readme.io/375cb260ec22431fcd511f5fbdc02a165cc2726b212d3e23d98cb1f6da13f65c-image.png" align="center" caption="Search Log Exports" border={true} />

<br />

<br />

<br />