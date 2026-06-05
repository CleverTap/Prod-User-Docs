---
title: Catalogs Usage in Campaigns
excerpt: >-
  Learn how to add a catalog to a campaign and reference catalog attributes to
  populate item-specific details in your messages at send time.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

[Catalogs](doc:catalogs) allow you to pull structured product or content data directly into a campaign message, so each user sees item-specific details from your catalog at send time. Instead of hardcoding product names, images, or prices into your template, you reference catalog attributes as variables, and CleverTap resolves them per recipient.

When you add a catalog block to a campaign, every user who receives the message views item details populated from the catalog record you specify, keeping your content accurate and consistent without manual updates.

<Callout icon="📘" theme="info">
  #### How Catalog Data is Resolved at Send Time

  Catalog attributes are not embedded when you build the campaign. At the moment CleverTap sends to each recipient, it looks up the catalog record and substitutes the mapped attributes into your template. If a catalog item is updated after the campaign is scheduled, the latest value is used at send time.
</Callout>

# Use Cases

The following use cases show how different teams use catalog-driven personalization to keep messages accurate and relevant.

## Personalize Transactional and Trigger-Based Messages with live product data

Use catalog attributes to populate item-specific details in triggered messages, such as order confirmations, back-in-stock alerts, or price-drop notifications, without duplicating product data in your campaign template.

The following table lists example use cases by domain:

| Domain        | Use case                                                                                                                                                               |
| :------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| OTT           | Send a "Now Available" notification when a title a user added to their watchlist becomes available, pulling the title name, thumbnail, and deep link from the catalog. |
| E-commerce    | Trigger a price-drop alert that shows the exact product name, updated price, and image sourced directly from the catalog.                                              |
| Travel        | Send a booking confirmation that displays flight details, hotel name, and check-in date pulled from the catalog record tied to the booking.                            |
| Food delivery | Notify users when a previously unavailable item at their favorite restaurant is back, with the dish name, image, and price from the catalog.                           |

## Keep Promotional Content Accurate without Manual Edits

Build campaign templates that reference catalog attributes instead of static copy. When product details change, such as pricing, availability, or descriptions, the campaign reflects the latest values automatically.

The following table lists example use cases by domain:

| Domain        | Use case                                                                                                                                                                     |
| :------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| OTT           | Feature a new release in a weekly digest where the title, synopsis, and thumbnail are all drawn from the catalog, so no template edits are needed when the lineup changes.   |
| E-commerce    | Run a flash-sale email that pulls featured product names and prices from the catalog at send time, eliminating the need to rebuild the campaign each time inventory changes. |
| Travel        | Promote seasonal packages using catalog-sourced destination names, prices, and imagery that update automatically as inventory changes.                                       |
| Food delivery | Send a "Featured this week" push where the dish name and image come from the catalog, so the campaign template stays the same across weeks.                                  |

## Maintain Consistency across Channels

Use the same catalog as the single source of truth for product details across email, push, SMS, and WhatsApp campaigns. A change to a catalog record propagates to every campaign that references it without requiring per-channel edits.

The following table lists example use cases by domain.

| Domain        | Use case                                                                                                                                              |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| OTT           | Reference the same title metadata in both a push notification and a follow-up email without maintaining separate copies of the content.               |
| E-commerce    | Use catalog-sourced product names and images consistently in push, email, and WhatsApp campaigns so users see identical item details across channels. |
| Travel        | Surface the same destination details and pricing in an SMS alert and a follow-up email from a single catalog record.                                  |
| Food delivery | Use one catalog entry for a restaurant's details across a push notification and a promotional email campaign.                                         |

# Prerequisites

Before adding a catalog block to a campaign, confirm the following are in place:

* At least one active catalog with populated product records.
* The catalog includes the attributes you intend to use in the message, such as name, image URL, price, and product URL.
* The engagement campaign has been created and is in draft form.

# Add Catalog to Campaign

Open your campaign and go to the Content Editor. Click **Personalize**, select the _Catalog_ tab, and perform the following steps:

1. [Select catalog](#select-catalog)
2. [Map catalog attributes](#map-catalog-attributes)
3. [Reference catalog data in campaign message](#reference-catalog-data-in-campaign-message)

## Select Catalog

Choose a catalog from the dropdown. The selected catalog is the data source for the campaign. All attribute references in the message template are resolved against records in this catalog.

The following image shows the catalog selection in the _Personalize_ section:

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/e86dacf1662ba16b5c0e95c342af78f0beb340cfefb88d799047c1574cbd170b-image.png" />

Only active catalogs are available for selection. If the catalog you need is not listed, verify its status on the _Catalogs_ page.

## Map Catalog Attributes

Select the catalog attributes you want to use in the message template. Any attribute defined in the catalog schema is available to map.

For example, for an e-commerce campaign, you might map Product Name, Product Image, Price, and Product URL. These variables are available in the Title and Message fields, so each message displays the correct details for the item being promoted.

Once attributes are mapped, use Liquid Script to reference them in your campaign message.

## Reference Catalog Data in Campaign Message

Once the catalog is configured, use Liquid Tags in your _Title_ and _Message_ fields to pull mapped attribute values into the template.

<Image align="center" border={true} caption="Catalog Reference using Liquid Tags" src="https://files.readme.io/a4b02cd130c35aa8e76405e8968e5c1bf5e3adb20f0025ce07957e3182c5ca76-image.png" />

The following example shows how a price-drop alert is resolved in an e-commerce campaign.

A user who previously viewed a product receives a price-drop notification. CleverTap looks up the catalog record for that product and substitutes its attributes into the template.

| Field         | Resolved value                           |
| :------------ | :--------------------------------------- |
| Title         | Running Shoes - Now ₹1,999               |
| Message       | Price just dropped on an item you viewed |
| Image         | Product image from the catalog           |
| Click to view | Deep link to the product page            |

The price and product name are pulled from the catalog record at send time. If the price changes again before the message is delivered, the updated value is used.

# Publish

Use **Preview** to verify the message template structure and confirm that catalog attribute placeholders are correctly mapped and positioned in your content.

Once the template is validated, publish or schedule the campaign. At send time, CleverTap resolves each catalog attribute reference and populates the message with the current values from the catalog record.
