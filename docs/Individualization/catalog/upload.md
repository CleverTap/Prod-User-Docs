---
title: Upload Catalogs
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
DOCS NOTE: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE IS UNPUBLISHED (OR DELETED) AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES\
[https://docs.clevertap.com/docs/catalog#section-download-a-sample-catalog](https://docs.clevertap.com/docs/catalog#section-download-a-sample-catalog)\
[https://docs.clevertap.com/docs/catalog#section-create-a-new-catalog](https://docs.clevertap.com/docs/catalog#section-create-a-new-catalog)\
[https://docs.clevertap.com/docs/catalog#section-map-catalog-columns](https://docs.clevertap.com/docs/catalog#section-map-catalog-columns)

## Overview

This section covers how to prepare a catalog, then upload it in two ways into CleverTap:

* Dashboard Upload - Manual
* API Upload - Automation

# Prepare a Catalog

Before you can upload a catalog, you must prepare the catalog with a specific structure using one of the two following methods. 

Also, note that the file samples through our dashboard can help you get started in creating your own catalog.

> 📘 Upload Limits
>
> You can only have up to:  
>
> * 10,000 rows via the dashboard.
> * 1 million rows via API.
>
> For more information, refer to [Catalog API Endpoints](https://developer.clevertap.com/docs/catalog-api-endpoints).

> 🚧 Maximums and General Considerations
>
> Some things to keep in mind:
>
> * The catalog file must be in a CSV format.
> * You can add a maximum of 20 columns in a catalog.

## Product Catalog

To prepare a product catalog, perform the following steps:

1. Create a CSV file.
2. Ensure the file has the first row as headers.
3. Enter the following columns to be used in the catalog mapping with events:

* Mandatory: *Identity* to identify the products.
* Mandatory: *Names* to represent all the product names of all the products. 
* Mandatory: *ImageURL* to points to the product image URLs.
* Optional: Any other columns required for personalization or catalog data ingestion. For more information, refer to [Catalog Data Ingestion](https://docs.clevertap.com/docs/catalog-data-ingestion).

4. Fill out your CSV file with all the product details for each of the columns.

> 🚧 Maximums for a Product Catalog
>
> Some things to keep in mind for a product catalog:
>
> * You can upload a maximum of five catalogs.
> * Each catalog can have up to 5 million rows.

Below is a product catalog sample:

![710](https://files.readme.io/612e218-2a_Sample_Product_Catalog.png "2a Sample Product Catalog.png")

## Product Location Catalog

To prepare a product location catalog, perform the following steps:

1. Create a CSV file.
2. Ensure the file has the first row as headers.
3. Enter the following columns to be used in the catalog mapping with user profiles:

* Mandatory: *Identity* to identify the products and is used for the catalog mapping with events.
* Mandatory: *Latitude* to represent the latitude of the product store location.
* Mandatory: *Longitude* to represent the longitude of the product store location.

4. Fill out your CSV file with all the product details for each of the columns.

> 🚧 Maximums for a Product Location Catalog
>
> Some things to keep in mind for a product location catalog:
>
> * You can upload a maximum of five catalogs.
> * Each catalog can have up to 1 million rows.

In a product location catalog, the identity represents a location ID. Below is a product location catalog sample:

![355](https://files.readme.io/4a97c07-2b_Sample_Product_Location_Catalog.png "2b Sample Product Location Catalog.png")

# Upload a Catalog from the Dashboard

To upload a catalog from the dashboard, perform the following steps:

1. Navigate to *Settings* > *Catalogs*. 
2. Click **+ Catalog**.
3. Select *Product* or *Product Location*.

![1402](https://files.readme.io/372dc5b-1_Plus_Catalog.png "1 Plus Catalog.png")

4. Click **Browse** to search and upload a new catalog. The catalog file must be in a CSV format.

<Image title="2 Browse for product location catalog upload.png" alt={1412} className="border" border={true} src="https://files.readme.io/4d83bda-2_Browse_for_product_location_catalog_upload.png" />

3. Once the catalog preview displays, enter a catalog name.
4. Click **Upload**.

<Image title="3 Enter catalog name.png" alt={790} className="border" border={true} src="https://files.readme.io/9925d36-3_Enter_catalog_name.png" />

5. Click **Save Catalog**. 

<Image title="4 Save catalog.png" alt={1408} width="smart" src="https://files.readme.io/8e5ba1a-4_Save_catalog.png" />

Your new catalog is now displayed on the catalog page.  

![1395](https://files.readme.io/860f896-5_New_catalog_displayed_-_success.png "5 New catalog displayed - success.png")

# Upload a Catalog via API

To upload a catalog via API, perform the following steps:

1. [Create a pre-signed URL via API](https://developer.clevertap.com/docs/catalog-api-endpoints#section-create-a-pre-signed-url).
2. [Upload the catalog to CleverTap servers via the Presigned URL](https://developer.clevertap.com/docs/catalog-api-endpoints#section-upload-a-catalog-file).
3. [Mark the completion of the upload via an API request](https://developer.clevertap.com/docs/catalog-api-endpoints#section-indicate-the-completion-of-a-catalog-upload).

For more information, refer to [Catalog API Endpoints](https://developer.clevertap.com/docs/catalog-api-endpoints).

> 📘 Confirmation Email
>
> Once the catalog is uploaded, a validation is performed to ensure all mandatory columns are present. Once the upload is successful, the catalog uploader receives an email confirmation.

# Map Catalog Columns

After uploading the catalog, you must map the catalog column with the associated event and property on CleverTap (i.e., map the *Name* field of the catalog to the event property *Product Name* of the event *Product Viewed*).

1. Navigate to *Settings* > *Catalogs* and select the uploaded catalog. 
2. From the map catalog section, select the catalog columns to map. 

Below is a product location catalog mapping sample where the identity column from the catalog needs to be mapped to any other column in any product catalog:

> 📘 Required Location Column in a Product Catalog
>
> A product catalog must have a specific field stating the item location to map to the identity column in a product location catalog. Also, there can be multiple mappings that can be done with the same product location catalog.

![1409](https://files.readme.io/caf2236-1a_Select_the_catalog_columns_to_map_for_product_location_catalog.png "1a Select the catalog columns to map for product location catalog.png")

Below is a product catalog mapping sample:

> 📘 Product Catalog Considerations
>
> Some things to consider:
>
> * You can map more than one column of the catalog to a CleverTap event property.
> * A mapped event property can only belong to the same event.

<Image title="1b Select the catalog columns to map for product catalog.png" alt={1406} className="border" border={true} src="https://files.readme.io/5fc9faf-1b_Select_the_catalog_columns_to_map_for_product_catalog.png" />

3. Once the mapping is complete, click **Save Catalog**.
