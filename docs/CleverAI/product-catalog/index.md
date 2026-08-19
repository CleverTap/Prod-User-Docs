---
title: Product Catalog
excerpt: >-
  Learn how CleverTap’s Catalog enriches incomplete product catalogs with AI to
  power personalized experiences and recommendations.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Product Catalog in CleverTap enables customers to [upload](doc:upload-catalog) and [manage](doc:create-product#manage-catalog-products) product data that powers personalization and recommendations.

However, uploaded catalogs are often incomplete and lack category-specific attributes such as color, size or length, material, capacity, and other relevant metadata. These gaps limit the ability to deliver true 1:1 personalization and reduce the effectiveness of product recommendations, including scenarios with sparse behavioral or catalog data.

For example, consider an e-commerce catalog item uploaded with the following data:

- _Title_: Men’s Running Shoes
- _Description_: Lightweight shoes designed for daily runs
- _Image_: Product image showing a blue running shoe

The catalog item does not explicitly include structured attributes such as color, shoe type, gender, or usage.

<Callout icon="📘" theme="info">
  ### Availability

  Product Catalog is available in Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

# Use Cases

Here are some of the industry-specific personalization and recommendation use cases that Catalogs feature enables by filling missing attributes, standardizing catalog data, and adapting content for relevance and scale.

<Tabs>
  <Tab title="Ecommerce">
    E-commerce catalogs often lack structured attributes needed for accurate filtering, targeting, and similarity matching. The Catalog feature automatically derives attributes such as brand, color, length, and gender from product text and images.

    This enables use cases such as:

    - Personalized product recommendations based on user preferences (for example, color or style affinity).
    - Improved product discovery through attribute-based filtering.
    - Adapted product images and descriptions optimized for different engagement channels and user personas
  </Tab>

  <Tab title="FinTech">
    Financial product catalogs may not explicitly classify offerings by risk or suitability. This feature helps derive and standardize attributes such as risk category.

    This enables:

    - Personalized product recommendations aligned to a user’s risk profile.
    - Targeted campaigns for low-risk or high-risk financial products.
    - Better compliance-aware segmentation and messaging.
  </Tab>

  <Tab title="Food and Delivery">
    Food catalogs often lack consistent classification across cuisines, meal types, or dietary preferences. This feature identifies attributes such as cuisine, meal type, and dish category.

    This enables:

    - Personalized meal and restaurant recommendations based on user preferences.
    - Improved discovery for new or less-ordered items.
    - Adapted images and descriptions optimized for different channels and regions
  </Tab>

  <Tab title="Gaming">
    Gaming catalogs may not explicitly tag games by genre, audience, or age segment. This feature extracts attributes such as game type, age segment, and gender relevance.

    This enables:

    - Personalized game recommendations and promotions.
    - Audience-specific onboarding and engagement journeys.
    - Discovery of similar games based on enriched attributes.
  </Tab>

  <Tab title="Subscription">
    Subscription-based platforms often struggle to tag content consistently at scale. This feature derives attributes such as article type, age segment, and audience relevance.

    This enables:

    - Personalized content recommendations.
    - Audience-specific newsletters and campaigns.
    - Better discovery of relevant content across the catalog.
  </Tab>
</Tabs>

## Product Catalogs Listing

The _Product Catalogs_ listing page displays every catalog in the account. Each catalog appears as a row showing its name and system-generated ID, the number of items it contains, its status, how many live engagements use it, and who last updated it and when. This view provides a central place to monitor and manage catalogs and quickly understand their current state.

Use the search bar to find a specific catalog, and scroll through the list to review multiple catalogs. The **Add Catalog** button lets you create a new catalog. A system-generated ID is assigned to each catalog when it is created.

The following image shows the _Catalog listing_ page:


<Image src="https://files.readme.io/148c7aa21f021947947ce82b751c70eb0f92328cc7411741f21a83232ac41e50-image.png" align="center" caption="Product Catalog Listing" border={true} />


## Filters on Catalogs Listing

The Filters panel helps narrow down the catalogs displayed in the list.

<Table>
  <thead>
    <tr>
      <th>
        Filter
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Time period
      </td>

      <td>
        Restrict to catalogs created within a date range. Choose a preset, such as All Time, or set a custom range.
      </td>
    </tr>

    <tr>
      <td>
        Created by
      </td>

      <td>
        Show catalogs created by specific users, selected by email ID.
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        Filter by catalog status:

        - ACTIVE- Successfully created or synced, available for use in campaigns.

        - INACTIVE - Disabled, data feed unreachable/failed, or no product entries. Cannot be used in live campaigns until the issue is resolved.
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  ### Note

  A newly created catalog is INACTIVE. A catalog becomes ACTIVE only after an upload completes successfully. If a catalog you just created does not appear in a campaign's catalog picker, check its status here and review its Feeds tab for a failed upload.

  Filters make it easier to locate specific catalogs, especially when managing a large number of entries.
</Callout>

The following image shows the available _Filters_ for Product Catalog Listing:


<Image src="https://files.readme.io/6dc0b51147b16453e6e1dd7c719ae75691e704975c6c2c216f436e83e126e37e-image.png" align="center" caption="Filters on Product Catalog Listing" border={true} />


## Edit Columns

The Edit Columns panel allows you to control how the catalogs table is displayed. You can select which columns appear in the table and reorder them using drag handles.

Name always appears and cannot be hidden. The following columns can be shown, hidden, or reordered: Items, Status, Active Engagements, Updated by, Updated on, and Last Updated on. Customizing columns helps you focus on the information that matters most to your workflow.

The following image shows the _Edit Columns_ panel to show or hide the column in Catalog Listing:


<Image src="https://files.readme.io/041b7272f0ad0f93dc3ff07712ab6dc50f1bd04d482894f251934435cf04804d-image.png" align="center" caption="Edit Columns" border={true} />


## Delete a Catalog

To delete a catalog, open it and use the delete action. Deleting a catalog:

- Sets its status to DELETED and removes it from the Product Catalog listing page, but it can be seen if the deleted filter.
- Disables any recurring sync on it, so no further scheduled feed runs are created.
- Releases its name, so you can create a new catalog with the same name afterward.

<Callout icon="📘" theme="warn">
  ### Deletion is blocked while live engagements use the catalog

  If any live campaign or journey references the catalog, the delete is refused and CleverTap lists the blocking engagements. Stop those engagements, or remove the catalog block from them, then retry. The Active Engagements column on the listing page tells you in advance which catalogs are in use.
</Callout>
