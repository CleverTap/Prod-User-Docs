---
title: BigQuery Export
excerpt: Data Warehousing and Analytics Platform
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

[BigQuery](https://cloud.google.com/bigquery) is Google's cloud-based data warehousing and analytics platform. It enables users to store and analyze large amounts of data quickly and in a cost-effective manner. BigQuery integrates with several other Google Cloud Services (GCS). It supports various data sources, including CSV, JSON, Avro, Parquet, and ORC.

CleverTap integration with BigQuery through GCS allows you to export your CleverTap data to BigQuery for further analysis and reporting. This document describes how to integrate and analyze your CleverTap data in BigQuery.

<Callout icon="📘" theme="info">
  #### Note

  For any issues or questions related to the integration, you can reach out to the CleverTap Support Team for assistance.
</Callout>

# Key Benefits

Integrating BigQuery with CleverTap empowers businesses to unlock the full potential of their customer data, enabling advanced analytics, improved decision-making, personalized engagements, and scalable data processing.

Here are some of the key benefits of this integration:

* **Data Centralization:** You can centralize your customer data in one location. This allows for comprehensive analysis and reporting, as well as the ability to combine data from various sources for a holistic view of customer interactions.
* **Enhanced Data Insights:** By combining CleverTap's user engagement data with BigQuery's robust analytics capabilities, you gain deeper insights into user behavior, preferences, and interactions. This enables you to understand your customers better and make informed decisions based on comprehensive data.
* **Real-time Data Access:** Allows you to access real-time user data in BigQuery's data warehouse. This instant data availability empowers you to perform dynamic and up-to-the-minute analysis. It drives faster reactions to changing customer trends.
* **Scalability and Performance:** Integrating with CleverTap allows you to process and analyze vast amounts of customer data rapidly, ensuring high performance and scalability as your data volume grows. BigQuery's ability to handle large datasets without compromising performance ensures you can keep up with increasing user demands.
* **Scheduled Data Streaming:** You can schedule regular data exports from CleverTap to BigQuery and eliminate the need for manual data exports. This allows you to automate the CleverTap data transfer to BigQuery at recurring intervals, typically every 4 hours. While real-time streaming is not possible due to the minimum 4-hour delay between exports, this approach still provides a timely and efficient way to synchronize your CleverTap data with BigQuery. Scheduled data streaming ensures access to up-to-date customer data for analysis and decision-making.
* **Enhanced Segmentation and Targeting:** You can perform advanced segmentation and targeting of your CleverTap audience with this integration. This enables you to create highly personalized and targeted campaigns based on CleverTap's behavioral and demographic data. This precision targeting enhances the effectiveness of your marketing campaigns.
* **Predictive Analytics:** By leveraging CleverTap's behavioral analytics with BigQuery's data processing capabilities, you can implement predictive models to anticipate customer behavior. This empowers you to take proactive measures and optimize user experiences.
* **Customized Reporting and Visualization:** With CleverTap and BigQuery working together, by integrating CleverTap with BigQuery, you can create custom reports and visualizations using the data visualization tools of your choice. This allows for tailored reporting and visualization based on your specific business requirements and provides flexibility in data presentation.
* **Data Security and Reliability:** CleverTap and BigQuery are designed with security and reliability in mind. The integration ensures that your data is protected and readily available whenever needed, giving you peace of mind about data management.

# Prerequisites for Integration

Before you begin the integration, ensure that you have the following:

* A CleverTap account with the required access to create an export from CleverTap.
* A GCS project with a Service Account and the necessary permissions to access BigQuery, Cloud Storage, and Cloud Functions.
* Integrated Google Cloud with CleverTap. For more information, refer to [Integrated Google Cloud with CleverTap](doc:data-export-to-gcp#integrate-gcp-with-clevertap).
* An [IAM user](https://cloud.google.com/storage/docs/access-control/iam-roles) with the necessary permissions to access BigQuery and Cloud Storage.

# Export from CleverTap to BigQuery

To perform the export from CleverTap to BigQuery:

1. [Set Up CleverTap Export](doc:bigquery#set-up-clevertap-export)
2. [Store the Data in BigQuery](doc:bigquery#store-the-data-in-bigquery)
3. [Verify the Incoming Data](doc:bigquery#verify-the-incoming-data)
4. [Set Up a Recurring Data Transfer Service](doc:bigquery#set-up-a-recurring-data-transfer-service)

## Set Up CleverTap Export

Create a CleverTap export file that exports your data to a Google Cloud Storage (GCS) bucket in a specified format such as JSON, XML, CSV, or Parquet. Configure the export profile to run at a specific interval, for example, every 4 hours. The below image shows the _Notification Sent_ event export.

<Image align="center" alt="Export the Notification Sent Data to Google Cloud" border={true} caption="Export the Notification Sent Data to Google Cloud" src="https://files.readme.io/ec2fbcb-image.png" />

> 📘 Establish Connection
>
> Ensure that the CleverTap export file is configured to a designated GCS bucket. This is required to establish a connection between CleverTap and GCS.

After the export is completed, it appears on the _Exports_ page.

<Image align="center" alt="View Exported Data on the CleverTap Dashboard" border={true} caption="View Exported Data on the CleverTap Dashboard" src="https://files.readme.io/bedb618612a0258fe59958d195d557fe7b6cc6b7b1702a99e25db6385726f183-image.png" />

### View Exported Data in GCS Bucket

To view the exported data in the GCS bucket, enter the Export ID in the filter option as shown below:

<Image align="center" alt="View Exported Data in GCS Bucket" border={true} caption="View Exported Data in GCS Bucket" src="https://files.readme.io/95a4c4d-Notification_Sent.png" />

To find the Export ID, check the _Export details_ column on the _Export_ page.

## Store the Data in BigQuery

Suppose you have an e-commerce website, and you want to store and analyze your CleverTap data of _Notification Sent_ events using BigQuery. To achieve this use case, you need to create the following:

* [Datasets](doc:bigquery#datasets)
* [Tables](doc:bigquery#tables)

### Datasets

To store the data in BigQuery, you must first create a [dataset](https://cloud.google.com/bigquery/docs/datasets-intro). Consider a dataset as a folder containing tables, views, and other BigQuery objects. For our use case, let's create a dataset called _CleverTap_Data_. This dataset will act as a container to organize and manage all the tables and information related to CleverTap data.

To create a dataset in BigQuery:

1. Open the Google Cloud Console at [console.cloud.google.com](https://console.cloud.google.com/).
2. Select your project or create a new project if required.
3. From the navigation menu on the left, click **BigQuery** to access the BigQuery Console.
4. Choose a Project. If you have multiple projects, ensure you select the correct project where you want to create the dataset.
5. Click the![](https://files.readme.io/b927780-Ellipsis_Bigquery_1.png) icon from your project name and click **Create dataset** from the context menu.
6. In the _Create Dataset_ dialog box, enter a unique name for your dataset. Choose a name that conveys the purpose or content of the data you will store within it.
7. Select the location for your dataset. It determines the geographical region where the data will be physically stored. Choose a location that aligns with your data residency requirements.
8. Click **Create dataset**.

<Image align="center" alt="Create a Dataset" border={true} caption="Create a Dataset" src="https://files.readme.io/800803e-Create_Dataset_CleverTap_Data.gif" />

For more information, refer to [Create Datasets](https://cloud.google.com/bigquery/docs/datasets).

### Tables

Let us consider [tables](https://cloud.google.com/bigquery/docs/tables-intro) as spreadsheets within the _CleverTap_Data_ dataset. Each table consists of columns (similar to columns in a spreadsheet) that define the specific data fields you want to capture. For example, the _user_id_, _event_name_, _campaign_name_ and _campaign_id_.

Once you have created a dataset in BigQuery, you can create tables within that dataset to store your data. Creating tables in BigQuery enables you to structure and store your data for efficient analysis and querying. By defining the table schema and optionally loading data, you can effectively organize your datasets and leverage the power of BigQuery for data analytics and exploration.

By creating these tables within the _CleverTap_Data_ dataset, you can easily organize and analyze your customer data. You can run queries to extract insights, perform calculations, and generate reports based on the information stored in these tables.

To create a table in BigQuery:

1. Locate and click the dataset name where you want to create the table in the BigQuery console. The dataset will expand to display its contents.
2. Click the **Create table** button or the ellipsis icon![](https://files.readme.io/d7ba75b-Ellipsis_Bigquery_1.png)on dataset name and click **Create table** from the context menu. This will open the table creation form.
3. Configure the below Table Settings:
   1. From _Source_, select **Google Cloud Service** in the _Create table form_ field.
   2. Browse your GCS bucket and choose the _Notification Sent_ file to transfer its data.
   3. Select **CSV** in the _File format_ option.
   4. From _Destination_, select the _Project_ and _Dataset_ where you want to transfer the data.
   5. Provide a unique name for your table in the _Table_ field. We recommend you choose a descriptive name that reflects the purpose or content of the table. This helps you to identify the event data that you will transfer to the table. For this example, enter the table name as **Notification Sent**, which means that every event export file with the name _Notification Sent_ will append to this table.
   6. Select the _Table type_ as **Native table** to store data from your Google Cloud Storage bucket.
4. Click **Create table**.

<Image align="center" alt="Create a Table" border={true} caption="Create a Table" src="https://files.readme.io/8a0de62-Create_Table.gif" />

Once the table is created, you can view and manage it within the dataset. The table will be listed along with any other existing tables in the dataset. From the table view, you can perform operations such as running queries, modifying the table schema, setting access controls, and managing table properties. You can also configure table-specific settings, such as expiration policies, which automatically delete the table or its partitions after a specific time period. For more information, refer to [Create Tables](https://cloud.google.com/bigquery/docs/tables).

> 📘 Note
>
> In the above use case, the dataset _CleverTap_Data_ acts as a container or folder, while the table _Notification Sent_ acts as individual tables, each storing specific types of information related to customer data.

## Verify the Incoming Data

Before you configure the Data Transfer, you need to verify if your data has been correctly loaded and that the schema is in place. To verify the incoming data:

1. Navigate to the _Explorer_ dashboard.
2. Click the table in the sidebar. The _SCHEMA_ page opens:

<Image align="center" alt="View Schema" border={true} caption="View Schema" src="https://files.readme.io/3a15bfa-Schema.png" />

3. Click the **PREVIEW** tab to verify the incoming data.

<Image align="center" alt="Preview the Incoming Data" border={true} caption="Preview the Incoming Data" src="https://files.readme.io/396ef38-Preview.png" />

## Set Up a Recurring Data Transfer Service

Finally, set up a recurring data transfer service to move the exported data from GCS to BigQuery. The Data Transfer setup transfers the data from GCS to BigQuery. Create a [Cloud Storage Transfer](https://cloud.google.com/bigquery/docs/cloud-storage-transfer) from BigQuery that triggers a data transfer pipeline at the same interval as the export file. For example,  every 4 hours).

To set up a recurring data transfer service:

1. Navigate to _BigQuery_ > _Data Transfer_ from the Google Cloud console.
2. Click **Create Transfer**.
3. On the _Create Transfer_ page:

* In the _Source type_ section, from _Source_ drop-down, select _Google Cloud Storage_.

<Image align="center" alt="Source Type" border={true} caption="Source Type" src="https://files.readme.io/588d34e-Source_Type_Bigquery.png" />

* In the _Transfer config name_ field, from the _Display name_, enter a name for the transfer, such as _Notification_Sent_Data_. The transfer name can be any value that allows you to easily identify the transfer if you need to modify it later.

<Image align="center" alt="Transfer Config Name" border={true} caption="Transfer Config Name" src="https://files.readme.io/a2626c1-Transfer_config_name.png" />

* In the _Schedule options_ section, set the _Repeat frequencies_ for the schedule. You may either choose the default value as **Start now** to schedule the export immediately or click **Start at a set time** to schedule the export at a later time.

<Image align="center" alt="Schedule Options" border={true} caption="Schedule Options" src="https://files.readme.io/62a5084-Schedule_Options.png" />

* In the _Destination settings_ section, from the _Destination dataset_ drop-down, choose the dataset you created to store your data.

<Image align="center" alt="Destination Settings" border={true} caption="Destination Settings" src="https://files.readme.io/1da5024-Dataset_Name.png" />

* In the _Data source details_ section:
  * In the _Destination table_ field, enter the table name you created to store the data in BigQuery.
  * In the _Cloud Storage URI_ field, browse the _Notification_Sent_ event from the bucket.
    > 📘 Naming Convention
    >
    > When using the Cloud Storage URI to browse for event data, include an asterisk (*) before and after the event name as shown in the image below. This allows the event export table to continuously update with fresh event data.
  * From the _Write preference_ drop-down, select _APPEND_, to append new data to your existing destination table. The default value for _Write preference_ is _APPEND_.
  * Check the _Delete source files after transfer_ option to delete the source files from the GCS bucket after they are transferred to the BigQuery table. This helps to optimize the cloud storage cost.
  * From the _File format_ drop-down, select the data format you selected while exporting the data from the CleverTap dashboard. We recommend you select the file format as CSV.

<Image align="center" alt="Data Source Details" border={true} caption="Data Source Details" src="https://files.readme.io/2084205-Data_Source_Details.png" />

* In the _Header rows to skip_ field, we suggest entering at least one row corresponding to the table titles. This ensures that the space for table titles is preserved when transferring the data to the table.

<Image align="center" alt="Header Rows to Skip" border={true} caption="Header Rows to Skip" src="https://files.readme.io/ad59ab4-Header_Rows_to_Skip.png" />

4. Click **Save**.

# Analyze CleverTap Data in BigQuery

Once the data is exported to BigQuery, you can use SQL queries to analyze your CleverTap data in the BigQuery console or through other BigQuery-compatible tools. For example, you can:

* Count the number of user events or actions within a specific time period.
* Identify user segments based on their activity patterns.
* Calculate user engagement metrics such as retention rates, churn rates, or conversion rates.
* Perform cohort analysis to understand user behavior over time.
* Combine CleverTap data with other datasets in BigQuery for deeper analysis and correlation.

By exporting and analyzing your CleverTap data in BigQuery, you can unlock powerful analytics capabilities and gain valuable insights into your user engagement and retention strategies.
