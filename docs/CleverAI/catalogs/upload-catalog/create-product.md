---
title: Create Product
excerpt: Learn about creating and managing catalog products using APIs and data feeds.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Creating a product allows you to add individual items to a catalog. Products represent the core entities within a catalog and include attributes such as name, ID, image URL, and additional custom attributes.

Products are created and managed programmatically using APIs or ingested through feeds. [Create Product APIs](https://developer.clevertap.com/docs/create-single-product-api) are typically used for real-time or controlled product creation, while [feeds](doc:create-feed) are used for bulk uploads and periodic updates.

# Create Product

Products cannot be created directly from the dashboard. To add products to a catalog, you must use the [Create Product API](https://developer.clevertap.com/docs/create-single-product-api) or upload data through feeds.

## System Fields

System fields are enforced by the API. The following table describes the fields validated during product creation:

| Field     | Description                        | Constraints                                                      |
| --------- | :--------------------------------- | ---------------------------------------------------------------- |
| Identity  | Unique identifier for the product. | Required. Max 500 characters. Must be unique within the catalog. |
| Name      | Name of the product.               | Required. 1–1,000 characters.                                    |
| Image URL | Link to the product image.         | Required for single product creation. Max 2,000 characters.      |

<Callout icon="📘" theme="info">
  #### Note

  For bulk product creation, up to 100 products can be included in a single request.
</Callout>

## Attributes

In addition to system fields, products support a flexible `attributes` object that stores additional key-value pairs based on your catalog schema.

The following are common conventions used in the `attributes` object:

| Attribute         | Description                                             |
| ----------------- | ------------------------------------------------------- |
| price             | Price of the product.                                   |
| description       | Details about the product.                              |
| category          | The category the product belongs to.                    |
| Custom attributes | Any additional attributes based on your catalog schema. |

For more information on the request format, authentication, and the full list of supported fields, refer to [Create Product API]().

## Guidelines

The following guidelines apply to product creation and catalog management in CleverTap:

* Each product must have a unique identity within the catalog.
* Users can create products only through APIs or feeds, not from the dashboard.
* Missing or invalid system fields result in validation errors during ingestion.
* Attributes such as price, description, and category are conventions stored in the `attributes` object. The API does not validate or reject a product that omits these values.
* When creating products via the API in bulk, a maximum of 100 products can be included per request.
* Each bulk request must not exceed 500 KB in total payload size.
* Use feeds for bulk uploads and APIs for real-time or incremental updates.

# Manage Catalog Products

The _Product_ tab displays all products within a selected catalog. It provides tools for searching, filtering, and inspecting individual catalog items.

## Product List

The product list displays all catalog items in a paginated table.

The following table describes each column:

| Column       | Description                                        |
| ------------ | -------------------------------------------------- |
| Product Name | The name of the product as defined in the catalog. |
| ID           | The unique identifier assigned to the product.     |
| Image URL    | The URL of the product image.                      |

### Download Catalog

Click **Download Catalog** to export all active products in the catalog as a CSV file. The export runs in the background and may take a few minutes.

The **Download** button reflects the current export state as shown in the following table:

| Button state      | Description                  |
| ----------------- | ---------------------------- |
| Download Catalog  | Click to start a new export. |
| In Progress       | Export is being generated.   |
| Ready to download | Click to download the file.  |

When the export is complete, you receive an email notification. Click the **Ready to Download** button to get the exported CSV file.

## Product Details

Selecting a product from the list opens the _Product Detail_ panel on the right. The panel displays the product name, product image, and two subsections: _Details_ and _Properties_.

To collapse the panel, click the arrow at the top.

### Details

The _Details_ subsection shows system-level metadata for the selected product.

| Field      | Description                                                 |
| ---------- | ----------------------------------------------------------- |
| updated_at | The timestamp indicates when the product was last updated.  |
| created_at | The timestamp indicates when the product was first created. |

<Callout icon="📘" theme="info">
  #### Note

  Timestamps are displayed in Unix epoch format.
</Callout>

### Properties

The _Properties_ subsection shows the custom attributes stored in the `attributes` object for the selected product. The fields displayed here vary depending on the catalog's schema.

The following image shows the Product Details:

<Image align="center" border={true} caption="Product Details" src="https://files.readme.io/972e183c990e86546600a14d8872c678a8fe5052b9f50177b36d307addbd5b93-image.png" />
