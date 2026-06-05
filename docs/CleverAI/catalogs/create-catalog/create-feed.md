---
title: Create Feed
excerpt: >-
  Learn how to configure data sources that upload and update products in a
  catalog.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

A feed represents a source of data that supplies products or updates to a catalog. While a catalog acts as a container for all items, feeds define how and from where that data is added or updated.

A catalog can have multiple feeds, each responsible for different types of data updates.

For example, consider an e-commerce product catalog:

* You upload your full product list, including IDs, names, categories, and images, using a CSV file.
* Later, you update pricing and availability daily from your backend system.

In this case:

* The initial CSV upload is one feed.
* The daily price and availability sync is another feed.

Both feeds update the same catalog but serve different purposes.

<Callout icon="📘" theme="info">
  #### Note

  Multiple one-time file upload feeds can be connected to a single catalog. However, recurring sync feeds (API/URL and Google Sync) are limited to one active configuration per catalog at a time.
</Callout>

# Create Feed

Click **Create Feed** to configure a new feed for the selected catalog.

The following table describes the fields available when creating a feed:

| Field         | Description                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------- |
| Upload Type   | Select how the feed data is sourced. Supported options are CSV/XML/JSON file upload, API/URL, or Google Sync. |
| File / Source | Provide the required input based on the selected upload type, such as a file, URL, or sync configuration.     |

For API/URL and Google Sync feeds, the following additional fields are required.

| Field          | Description                                                                                                                    |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Source URL     | The URL from which CleverTap fetches the catalog data.                                                                         |
| Sync Frequency | The interval at which CleverTap re-fetches data from the source URL. Set a value and select the unit: minutes, hours, or days. |

For further details on configuring upload types, refer to [Create Catalog](doc:create-catalog).

After entering the required details, select **Save** to add the feed to the catalog.

Each feed updates only the attributes it contains. When multiple feeds are connected to the same catalog:

* Each feed operates independently.
* Updates from one feed do not overwrite unrelated fields from another.
* The most recent successful update determines the value of overlapping attributes.

This allows you to do the following:

* Separate initial data ingestion from ongoing updates.
* Maintain multiple data sources for the same catalog.
* Update specific attributes without re-uploading the entire dataset.

## Feed Status

Each feed displays a status that indicates its current state.

The following table describes each status:

| Status          | Description                                                                                                     |
| --------------- | --------------------------------------------------------------------------------------------------------------- |
| Pending         | The feed has been created and is queued for processing.                                                         |
| Running         | The feed is currently processing and updating catalog data.                                                     |
| Completed       | The feed was processed successfully and updated the catalog.                                                    |
| Failed          | The feed processing failed due to validation or upload errors.                                                  |
| Partial Success | The feed processed successfully for some records but failed for others. Review logs to identify failed entries. |

The following image shows the _Create Feed_ page:

<Image align="center" border={true} caption="Create Feed" src="https://files.readme.io/813085df7901b79f10b4c73c7cd8fbd0c6ad5a5630f58e023293c136ba088a31-image.png" />

## Guidelines

The following guidelines apply to creating and managing feeds at CleverTap:

* Multiple one-time file upload feeds can be connected to a single catalog.
* Recurring sync feeds (API/URL and Google Sync) are limited to one configuration per catalog.
* Each feed updates only the fields it contains.
* Feed failures do not impact other feeds linked to the same catalog.
* Review feed logs to troubleshoot errors or partial updates.
* Use the appropriate upload type based on your data source and update frequency.

# Manage Feed Logs

Monitor feed activity from the _Feed_ tab. The _Feed_ tab shows all feeds associated with the selected catalog. Each feed entry includes the details such as feed name, number of products, upload type, status, uploaded by, and last updated.

The following image shows the Feed details:

<Image align="center" border={true} caption="Feed Details" src="https://files.readme.io/a9927ab27ab36c718c7271797849e1638987a5ebf97bd88199cb6b818c09ff6b-image.png" />

You can search feeds, apply filters, or click **Create Feed** to add a new feed. This view helps track how catalog data is being sourced and updated.

## Filter Feed Logs

Apply filters to track feed performance and identify issues. Update or add new feeds as your data requirements evolve. Filters in the Feed Logs view allow you to narrow feeds by the following criteria.

| Filter      | Description                                                                                |
| ----------- | ------------------------------------------------------------------------------------------ |
| Time Period | Narrow feeds by a specific date range based on when they were created or processed.        |
| Status      | Filter feeds by processing state: pending, running, completed, failed, or partial success. |
| Created By  | View feeds created by a specific user.                                                     |

The following image shows the filters for Feed Logs:

<Image align="center" border={true} caption="Filters on Feed Logs" src="https://files.readme.io/56cb5cafc861370f4bfe33f054cce052d39a806f1a15dcb517ef2a735dfbc693-image.png" />

## Edit Columns

The Edit Columns option allows you to customize the Feed tab by choosing which columns to display and in what order. This makes it easier to focus on the most relevant information based on your workflow.

<Image align="center" border={true} caption="Edit Columns" src="https://files.readme.io/1c0c02290794e510f17cc46f77527614a1cf0386a71ac6c3f50093143ffb0c07-image.png" />
