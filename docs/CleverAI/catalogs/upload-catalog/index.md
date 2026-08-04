---
title: Upload Catalog
excerpt: >-
  Learn how to upload and manage catalogs and feeds in CleverTap to upload,
  sync, and structure product data for personalization, recommendations, and
  engagement.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Uploading a catalog is the first step to bringing product or content data into CleverTap. A catalog acts as a container for items that can later be used across personalization, recommendations, and engagement use cases.

Once uploaded, catalogs are populated and updated using one or more feeds. Each feed is processed independently, so updates from one feed apply only to the fields it manages without affecting data from other feeds. For example, you might use one feed to upload an initial set of products and another feed to keep pricing or availability updated over time.

Catalogs can be uploaded as either Product or Product Location catalogs. Select the catalog type based on the kind of items you want to store. Product catalogs store item-level details such as name, price, and category, while Product Location catalogs store product availability and attributes specific to a location, such as store, region, or warehouse.

Once a catalog is uploaded, its type cannot be changed.

# Upload Catalog

To upload a catalog, perform the following steps:

1. Go to _Settings_ > _Catalogs_ and click **Add Catalog**.
2. Enter the required details.


<Image src="https://files.readme.io/9c3156b684f45804189d17cf7a905956474200cc9b2d1425f4e4614288418ee2-image.png" align="center" caption="Upload Catalog" border={true} />


| Field        | Description                                                                                                                                                                                                     |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog Name | Enter a name to uniquely identify the catalog.                                                                                                                                                                  |
| Description  | Add context about the catalog.                                                                                                                                                                                  |
| Upload Type  | Select how your catalog data is sourced. You can upload a CSV/XML file, fetch data from a URL, or sync from an external source. For more information, refer to [Upload Types](doc:upload-catalog#upload-types). |

After a file is uploaded, the system validates the catalog. Once validation is successful, the file preview section displays a few rows of catalog data, including column headers, so you can preview the data before proceeding. This helps ensure the catalog content is correct before upload.

3. [Map data type with Catalog columns](doc:upload-catalog#map-data-type-with-catalog-columns).
4. Create a Feed to populate data in your catalog.

Click **Upload** to upload the catalog. Once the Catalog is uploaded, it becomes available immediately.

<Callout icon="📘" theme="info">
  #### Catalog Constraints

  A catalog supports the following:

  - A maximum of 200 columns in total
  - 3 fixed columns: Product ID, Name, and Image URL
  - Up to 197 custom attribute columns, defined during catalog creation Columns cannot be added or removed after the catalog is saved.

  Your account supports up to 5 catalogs and a combined total of 15M rows across all catalogs. Both limits apply: you cannot create a new catalog once you reach 5, and you cannot upload more rows to any catalog once your combined row count reaches 15M, whichever comes first.
</Callout>

# Upload Types

Upload Type defines how catalog data is imported into CleverTap. You can upload a file, fetch data from a URL, or sync data from an external source.

## Catalog Upload

Use this option to upload catalog data in bulk from a CSV file on your system. The uploaded file is displayed in a tabular preview, and you can replace it if required before proceeding.

This option is ideal for one-time or bulk uploads.

The following image shows the _Catalog upload_ tab:


<Image src="https://files.readme.io/72162109cee08cbca11c37f059d9e1d2b4109929d6e84397da4d182ce363a4f9-image.png" align="center" caption="Catalog Upload" border={true} />


## API/URL

Select the _API/URL_ tab to source catalog data from an external endpoint rather than uploading a file manually.

Enter a source _URL_ to fetch catalog data, for example, to automatically pull product updates such as pricing and availability from your backend system at regular intervals.

<Callout icon="📘" theme="info">
  #### Note

  The source URL must be publicly accessible. CleverTap fetches data directly from the URL without any authorization headers or credentials. Password-protected or authenticated URLs are not supported.
</Callout>

Click **Fetch Catalogs** to retrieve the data and display a preview of catalog rows and columns. Specify how often CleverTap must re-fetch data from the URL. Enter a _Sync Frequency_ value and select the unit: Minute(s), Hour(s), or Day(s). For example, "Every 1 Hour(s)" pulls fresh catalog data once per hour.

The following image shows the _API/URL_ tab:


<Image src="https://files.readme.io/a2dd3f47b2bfea17f8f0686f73f94c0314a509e1463e5e2d96484fcf23845858-image.png" align="center" caption="Catalog Upload via API or URL" border={true} />


You can preview the first few rows of the data before validating the input.

## Google Sync

When _Google sync_ is selected, you can provide the _Source Url_, fetch the Catalog, and define a sync frequency using minutes, hours, or days.

Before fetching the catalog, configure the following fields in the table:

| Field          | Description                                                                                           |
| -------------- | ----------------------------------------------------------------------------------------------------- |
| Source Url     | Enter the Google-hosted feed URL from which catalog data is fetched.                                  |
| Sync Frequency | Define how often the catalog is refreshed. You can configure the interval in minutes, hours, or days. |

Click **Fetch Catalog** to retrieve catalog data from the configured source. This option supports ongoing synchronization of catalog data. Only links to XML files are allowed for Google Sync. For more information, refer to [Google Merchant Center](https://business.google.com/in/merchant-center/).

The following image shows the Catalog upload via _Google sync_:


<Image src="https://files.readme.io/e88c50d8431e980f1b79fdb07c65161c2dedca2a0dd14a5d07a159f98a9d7e0d-image.png" align="center" caption="Catalog Upload via Google Sync" border={true} />


<Callout icon="📘" theme="info">
  #### Sync Frequency

  CleverTap fetches your catalog from the source URL at the interval you set. It does not store a static copy, so the Sync Frequency you choose directly affects how current your catalog data is. Set a shorter interval, such as every hour, if your source updates frequently, for example during flash sales or when stock levels change in real time. Set a longer interval, such as once a day, if your catalog is relatively stable and only updated periodically. This also reduces unnecessary load on your data source.<br />Enter a value between 1–59 for minutes, 1–23 for hours, or any positive number for days.

  As a best practice, match the sync frequency to how often your source data actually changes.
</Callout>

## Map Data Type with Catalog Columns

After uploading and validating a catalog file, CleverTap automatically reads the data and provides a first-level mapping for each column. Mapping is available for all columns. Review the suggested mappings and update them if needed before saving, as mappings cannot be edited once saved. Correct mappings ensure the catalog data is structured correctly before proceeding.

<Callout icon="📘" theme="info">
  #### Catalog Column Limits

  A catalog supports a maximum of 200 columns in total:

  - 3 fixed columns: Product ID, Name, and Image URL
  - Up to 197 custom attribute columns,defined during catalog creation

  Columns cannot be added or removed after the catalog is saved.
</Callout>

The following image shows the _Mapping data type_ section:


<Image src="https://files.readme.io/327e5a0f27fe737f30eee6ce99f29d91d339ad12b298ba1cd7a45d734fefda02-image.png" align="center" caption="Map Data Type" border={true} />


<br />
