---
title: Catalog Stats
excerpt: >-
  Learn how the Stats tab helps you track catalog coverage, recommendation
  reach, and engagement performance across channels.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The Stats tab provides an overview of how items in a catalog are used across recommendations and engagement channels. It helps you understand recommendation reach and engagement performance across channels.

To create a catalog, refer to [Create Catalog](doc:create-catalog).

# Engagement Channel-wise Breakdown

This section shows how catalog-driven messages perform across supported engagement channels. Metrics are calculated based only on messages that include catalog items.

The following table describes each column:

| Column                            | Description                                                                                                                       |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Channel                           | The engagement channel through which catalog-based messages were sent. Supported channels include Email, SMS, WhatsApp, and Push. |
| Total number of Engagements       | The total count of campaigns, journeys, or other messaging touchpoints that used catalog items on that channel.                   |
| Total number of Messages          | The total number of messages sent that included catalog items on that channel.                                                    |
| Total number of items recommended | The total number of catalog items recommended through messages on that channel.                                                   |
| Average Click Through Rate        | The average percentage of sent catalog-based messages that received at least one click.                                           |

The following image shows the _Stats_ page:

<Image align="center" border={true} caption="Catalog Stats" src="https://files.readme.io/d94ad76c796993e17d6315ba2722a3952796c20698fbd6318b13ed4ae3e664e1-2026-06-03_14-11-37_1.gif" />

# Top Recommended

This section lists the most frequently recommended products from the catalog. Use the Search field to find a specific item by name.

The following table describes the default columns in the list.

| Column            | Description                                                          |
| ----------------- | -------------------------------------------------------------------- |
| Item Name         | The name of the recommended product, along with its catalog item ID. |
| Total recommended | The number of times the item has been recommended to users.          |

<Callout icon="📘" theme="info">
  #### Note

  Additional columns such as Description, Price, and Link may appear depending on the attributes defined in your catalog schema. These are not fixed system fields.
</Callout>

# Item Detail

Selecting a row opens the _Item Detail_ panel on the right, which displays information about the selected product. It is organized into two subsections: Details and Properties.

## Details

The _Details_ subsection shows system-level metadata for the selected product.

| Field           | Description                                                     |
| --------------- | --------------------------------------------------------------- |
| Uploaded on     | The date and time when the item was first added to the catalog. |
| Last updated on | The date and time the item was last updated.                    |

## Properties

The _Properties_ subsection shows the attributes defined in your catalog schema for the selected product. The fields displayed here vary depending on the catalog's schema.

| Field      | Description                                                   |
| ---------- | ------------------------------------------------------------- |
| Product Id | The unique identifier assigned to the product in the catalog. |
| Image link | The URL of the product image.                                 |

<Callout icon="📘" theme="info">
  #### Note

  Additional properties such as Category, Stock, Brand, or Price may appear depending on the attributes defined in your catalog schema. These are not fixed system fields.
</Callout>
