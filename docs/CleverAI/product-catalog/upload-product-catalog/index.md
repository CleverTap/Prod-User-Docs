---
title: Upload Product Catalog
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

Uploading a product catalog is the first step to bringing product or content data into CleverTap. A product catalog acts as a container for items that can later be used across personalization, recommendations, and engagement use cases.

Once uploaded, catalogs are populated and updated using one or more feeds. Each feed is processed independently, so updates from one feed apply only to the fields it manages and do not affect data from other feeds. For example, you might use one feed to upload an initial set of products and another feed to keep pricing or availability updated over time.

<Callout icon="📘" theme="warn">
  ### **Note**

  Each feed replaces a product's attributes in full.

  When a feed processes a product, it overwrites that product's entire attributes object with the values in the current feed. Any attribute you do not include in the feed is removed from the product, it is not preserved from an earlier feed.

  This means you cannot split a catalog across feeds by field. A _pricing only&#x20;_&#x66;eed that omits color and size will strip color and size from every product it touches.

  Always include every attribute you want to keep in each feed that touches a given product. For more information, refer to [How Multiple Feeds Work]().
</Callout>

Product catalogs store item-level details such as name, price, and category. Once a catalog is uploaded, its type cannot be changed.

# Upload a Product Catalog

To upload a catalog, perform the following steps:

1. Go to _Product Catalog_ and click **Add Catalog**.
2. Enter the required details.


   <Image src="https://files.readme.io/211a695de9baa2eb9124a5aa9f6114f644e08a3bb27ca1bbc2237c22dd60c245-image.png" align="center" caption="Upload Product Catalog" border={true} />


| Field        | Description                                                                                                                                                                                                                                                           |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog Name | Enter a name to uniquely identify the catalog.                                                                                                                                                                                                                        |
| Description  | Add context about the catalog.                                                                                                                                                                                                                                        |
| Upload Type  | Select how your catalog data is sourced. Choose Device storage, URL sync, or Google merchant sync. You can upload a CSV file, fetch data from a URL, or sync from an external source. For more information, refer to [Upload Types](doc:upload-catalog#upload-types). |

After a file is uploaded, the system validates the catalog. Once validation succeeds, the file preview section displays a few rows of catalog data, including column headers, so you can review the data before proceeding. This helps ensure the catalog content is correct before upload.

3. [Map data type with Catalog columns](doc:upload-catalog#map-data-type-with-catalog-columns).
4. Create a Feed to populate _your catalog with data_.

Click **Upload** to upload the catalog. Once the Catalog is uploaded, it becomes available immediately.

<Callout icon="📘" theme="info">
  #### Catalog Constraints

  A catalog supports the following:

  - A maximum of 100 columns in total
  - 3 fixed columns: Identity, Name, and Image URL. Column headers are case-insensitive. You can use any of the following header casing in your CSV file: identity vs Identity vs IDENTITY, name vs Name, and imageurl vs ImageUrl vs Image_URL vs image_url
  - Up to 97 custom attribute columns, defined during catalog creation Columns cannot be added or removed after the catalog is saved.

  Your account supports up to 5 catalogs and a combined total of 15M rows across all catalogs. Both limits apply: you cannot create a new catalog once you reach 5, and you cannot upload more rows to any catalog once your combined row count reaches 15M, whichever comes first.

  Custom attribute names must be at most 50 characters, must start with a letter or underscore, and may contain only letters, numbers, underscores, dashes, spaces, and parentheses.

  identity, name, image_url, and imageurl are reserved and cannot be reused as custom attribute names.

  Attribute names must be unique within a catalog and case-insensitive.
</Callout>

# Upload Types

Upload Type defines how catalog data is imported into CleverTap. You can upload a file, fetch data from a URL, or sync data from an external source.

## Device Storage

Use this option to upload catalog data in bulk from a CSV file on your system. The uploaded file is displayed in a tabular preview, and you can replace it if required before proceeding. The maximum file size is 2048 MB.

This option is ideal for one-time or bulk uploads.

The following image shows the _Device Storage_ tab:


<Image src="https://files.readme.io/77e9487cc95b65b3d042234dfe4fb8980316e34d9dda781271466feceda8696e-image.png" align="center" caption="Upload using Device Storage" border={true} />


## URL Sync

Select the _URL_ _sync_ tab to source catalog data from an external endpoint rather than uploading a file manually.

Enter a source _URL_ to fetch catalog data, for example, to automatically pull product updates such as pricing and availability from your backend system at regular intervals.

<Callout icon="📘" theme="info">
  #### Note

  The source URL must be publicly accessible. CleverTap fetches data directly from the URL without any authorization headers or credentials. Password-protected or authenticated URLs are not supported.
</Callout>

Click **Fetch Catalogs** to retrieve the data and display a preview of catalog rows and columns. Specify how often CleverTap must re-fetch data from the URL. Enter a _Sync Frequency_ value and select the unit: Minute(s), Hour(s), or Day(s). For example, "Every 1 Hour(s)" pulls fresh catalog data once per hour.

The following image shows the _URL sync_ tab:


<Image src="https://files.readme.io/5a6e9951e2e48b00c9e579075f0e14d8a5dbcb1f223ba49e5e71cd02564c6ea5-image.png" align="center" caption="Product Catalog Upload via URL sync" border={true} />


You can preview the first few rows of the data before validating the input.

## Google Sync

When _Google Merchant Sync_ is selected, you can provide the _Source URL_, fetch the Catalog, and define a sync frequency in minutes, hours, or days.

Before fetching the catalog, configure the following fields in the table:

| Field          | Description                                                                                           |
| -------------- | ----------------------------------------------------------------------------------------------------- |
| Source Url     | Enter the Google-hosted feed URL from which catalog data is fetched.                                  |
| Sync Frequency | Define how often the catalog is refreshed. You can configure the interval in minutes, hours, or days. |

Click **Fetch Catalog** to retrieve catalog data from the configured source. This option supports ongoing synchronization of catalog data. Only links to XML files are allowed for Google Sync. For more information, refer to [Google Merchant Center](https://business.google.com/in/merchant-center/).

The following image shows the Catalog upload via _Google sync:_


<Image src="https://files.readme.io/5c9cd390bdf4488746c9c503d8089f27c72c4728a86f6e310df6da8e0db306f6-image.png" align="center" caption="Product Catalog Upload via Google Merchant Sync" border={true} />


<Callout icon="📘" theme="info">
  #### Sync Frequency

  CleverTap fetches your catalog from the source URL at the interval you set. It does not store a static copy, so the Sync Frequency you choose directly affects how current your catalog data is. Set a shorter interval, such as every hour, if your source updates frequently, for example during flash sales or when stock levels change in real time. Set a longer interval, such as once a day, if your catalog is relatively stable and only updated periodically. This also reduces unnecessary load on your data source.<br />Enter a value between 1–59 for minutes, 1–23 for hours, or any positive number for days. The minimum value is 1. There is currently no enforced maximum.

  As a best practice, match the sync frequency to how often your source data actually changes.
</Callout>

## Map Data Type with Catalog Columns

After uploading and validating a catalog file, CleverTap automatically reads the data and provides a first-level mapping for each column. Mapping is available for all columns. Review the suggested mappings and update them if needed before saving, as mappings cannot be edited once saved. Correct mappings ensure the catalog data is structured correctly before proceeding.

The following table lists the data types and the usage examples:

| Data type | Use for                                                                    |
| --------- | -------------------------------------------------------------------------- |
| String    | Text values such as names, categories, or SKUs.                            |
| Number    | Whole numbers.                                                             |
| Float     | Numbers with decimal values, such as prices or ratings.                    |
| Boolean   | Values with exactly two states, such as true/false for stock availability. |
| Array     | Lists of values, such as multiple tags or genres.                          |

<Callout icon="📘" theme="info">
  #### Catalog Column Limits

  A catalog supports a maximum of 100 columns in total:

  - 3 fixed columns: Product ID, Name, and Image URL
  - Up to 97 custom attribute columns,defined during catalog creation

  Columns cannot be added or removed after the catalog is saved.
</Callout>

The following image shows the _Mapping data type_ section:


<Image src="https://files.readme.io/bb0337a2ad9889ba8548c2d29496a53f94e9985b83faa275fa5099af582d5d1b-image.png" align="center" caption="Map Data Type" border={true} />
