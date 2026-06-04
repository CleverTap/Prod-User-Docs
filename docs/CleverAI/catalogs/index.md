---
title: Catalogs
excerpt: >-
  Learn how CleverTap’s Catalog enriches incomplete product catalogs with AI to
  power personalized experiences and recommendations.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Catalog in CleverTap enables customers to upload and manage product data that powers personalization and recommendations.

However, uploaded catalogs are often incomplete and lack category-specific attributes such as color, size or length, material, capacity, and other relevant metadata. These gaps limit the ability to deliver true 1:1 personalization and reduce the effectiveness of product recommendations, including scenarios with sparse behavioral or catalog data.

For example, consider an e-commerce catalog item uploaded with the following data:

* _Title_: Men’s Running Shoes
* _Description_: Lightweight shoes designed for daily runs
* _Image_: Product image showing a blue running shoe

The catalog item does not explicitly include structured attributes such as color, shoe type, gender, or usage.

# Use Cases

Here are some of the industry-specific personalization and recommendation use cases that Catalogs feature enables by filling missing attributes, standardizing catalog data, and adapting content for relevance and scale.

<Tabs>
  <Tab title="Ecommerce">
    Ecommerce catalogs often lack structured attributes needed for accurate filtering, targeting, and similarity matching. The Catalog feature automatically derives attributes such as brand, color, length, and gender from product text and images.

    This enables use cases such as:

    * Personalized product recommendations based on user preferences (for example, color or style affinity).
    * Improved product discovery through attribute-based filtering.
    * Adapted product images and descriptions optimized for different engagement channels and user personas
  </Tab>

  <Tab title="FinTech">
    Financial product catalogs may not explicitly classify offerings by risk or suitability. This feature helps derive and standardize attributes such as risk category.

    This enables:

    * Personalized product recommendations aligned to a user’s risk profile.
    * Targeted campaigns for low-risk or high-risk financial products.
    * Better compliance-aware segmentation and messaging.
  </Tab>

  <Tab title="Food and Delivery">
    Food catalogs often lack consistent classification across cuisines, meal types, or dietary preferences. This feature identifies attributes such as cuisine, meal type, and dish category.

    This enables:

    * Personalized meal and restaurant recommendations based on user preferences.
    * Improved discovery for new or less-ordered items.
    * Adapted images and descriptions optimized for different channels and regions
  </Tab>

  <Tab title="Gaming">
    Gaming catalogs may not explicitly tag games by genre, audience, or age segment. This feature extracts attributes such as game type, age segment, and gender relevance.

    This enables:

    * Personalized game recommendations and promotions.
    * Audience-specific onboarding and engagement journeys.
    * Discovery of similar games based on enriched attributes.
  </Tab>

  <Tab title="Subscription">
    Subscription-based platforms often struggle to tag content consistently at scale. This feature derives attributes such as article type, age segment, and audience relevance.

    This enables:

    * Personalized content recommendations.
    * Audience-specific newsletters and campaigns.
    * Better discovery of relevant content across the catalog.
  </Tab>
</Tabs>

## Catalogs Listing

The Catalogs listing page displays all catalogs available in the account. Each catalog appears as a row in the table and includes details such as the catalog name and ID, number of items, catalog validation status, uploader, upload date, and last updated date. This view provides a central place to monitor and manage catalogs and quickly understand their current state.

Use the search bar to find a specific catalog, and scroll through the list to review multiple catalogs. The **Add Catalog** button lets you create a new catalog. A system-generated ID is assigned to each catalog when it is created.

The following image shows the _Catalog listing_ page:

<Image align="center" border={true} caption="Catalog Listing" src="https://files.readme.io/b85ade9f52fc8d004d616b3e8a4df335d4cfef34310f32b7a1901a99eed376a8-image.png" />

## Filters on Catalogs Listing

The Filters panel helps narrow down the catalogs displayed in the list. You can filter catalogs based on the following:

* ACTIVE- Successfully created or synced, available for use in campaigns.
* INACTIVE - Disabled, data feed unreachable/failed, or no product entries. Cannot be used in live campaigns until the issue is resolved.

Filters can be saved for reuse or reset when no longer needed. This makes it easier to locate specific catalogs, especially when managing a large number of entries.

The following image shows the available _Filters_ for Catalog Listing:

<Image align="center" border={true} caption="Filters on Catalog Listing" src="https://files.readme.io/c1907af47e0dcc4808e8fd274de4da868b8304713a0756cc43e159fcf0a4d934-image.png" />

## Edit Columns

The Edit Columns panel allows you to control how the catalogs table is displayed. You can select which columns appear in the table and reorder them using drag handles.

The available columns include name, number of items, catalog validation, uploaded by, uploaded on, and last updated on. After making changes, select _Apply Changes_ to save or reset to revert to the previous configuration, or _Cancel_ to exit without saving. Customizing columns helps you focus on the information that matters most to your workflow.

The following image shows the _Edit Columns_ panel to show or hide the column in Catalog Listing:

<Image align="center" border={true} caption="Edit Columns" src="https://files.readme.io/2c3de3406367c98ea4d91aae067a29eb0ebb57645733855e0f45548430f2266b-image.png" />
