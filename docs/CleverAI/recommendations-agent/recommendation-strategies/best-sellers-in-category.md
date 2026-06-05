---
title: ' Best Sellers in Category'
excerpt: >-
  Learn how to recommend top-selling products or content within specific
  categories based on sales performance and popularity.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Best Sellers in Category recommendations surface the most-purchased items in a specific category from your catalog, based on aggregated purchase data over a selected time period. Unlike Best Sellers, which ranks items across the entire catalog, Best Sellers in Category scopes the ranking to a defined category — so a best-selling sofa ranks above a best-selling lamp even if the lamp has higher catalog-wide purchase volume.

Because they rely on aggregated purchase data rather than individual user history, Best Sellers in Category work for all users and deliver contextually relevant results without requiring personal data.

# Use Cases

Best Sellers in Category recommendations work best when category-scoped, purchase-driven discovery is needed, as follows:

* **Category pages and promotional email campaigns**: Highlights top-performing products within a specific category. For example, a category-specific email featuring the top-selling items in the Skincare category helps subscribers shop with confidence.
* **Push notifications**: Re-engages users with category-relevant best sellers. For example, a push notification to users who have browsed the Home Appliances category, highlighting the most purchased items in that category over the past week.
* **SMS campaigns**: Drives category-specific conversions through social proof. For example, an SMS to opt-in users featuring the three best-selling products in the Footwear category ahead of a weekend promotion.
* **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results within a category.

# Strategy

Best Sellers in Category recommendations rank items based on total purchase activity within a defined category scope over a specified time window.

During setup, you select the purchase event that defines what counts as a sale and configure the catalog columns that determine how category groupings are identified.

At serving time, items are retrieved within the requested category and ranked from highest to lowest by total purchase frequency within the configured window. The category scope is provided when the recommendation is requested, so the same strategy can serve multiple categories without separate configurations. For example, a single Best Sellers in Category strategy can return the most purchased items in Furniture for one campaign and in Lighting for another.

Common interaction events include:

| Industry       | Event                  |
| :------------- | :--------------------- |
| ECommerce      | Charged, Order Placed  |
| Food & Grocery | Order Placed           |
| OTT            | Subscription Purchased |

# Required Inputs

The following inputs are required:

| Input          | Description                                                                                                                                                                                                                                            |
| :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Purchase event | The user action used to count and rank items by purchase frequency within the category.                                                                                                                                                                |
| Category       | Scopes results to a specific category at serve time. Not configured during strategy creation — the category value is dynamically passed when the recommendation is requested. The same strategy can serve multiple categories without reconfiguration. |
| Mapping        | Connects the event property containing the item identifier to the identity column of your catalog.                                                                                                                                                     |

# Optional Inputs

The following inputs are optional:

| Input                  | Description                                                                                                                                                                                                                                                                                                                                   |
| :--------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Time window            | Period over which purchases are counted. If not set, all available historical data for the selected event is used.                                                                                                                                                                                                                            |
| Consideration Criteria | Narrows which purchases count toward ranking. For example, filter by membership tier or region.                                                                                                                                                                                                                                               |
| Fallback Strategy      | Activates when the primary strategy returns fewer items than requested for the given category, including when the category returns zero results. Fallback items are deduplicated against the best seller results before being returned. If no fallback is configured and the category has insufficient data, the default values are returned. |

# Create Best Sellers in Category Strategy

This section helps you set up a strategy that surfaces the most-purchased items in a specific category from your catalog.

## Prerequisites

Before you begin, check if the following are in place:

* A catalog is uploaded and active.
* At least one purchase event is being tracked, such as `Order Placed` or `Charged`.
* The tracked event references the same item ID as the catalog identity column. If they do not match, purchases cannot be attributed to catalog items.
* The catalog contains at least one column suitable for category grouping, with a limited number of distinct values. Columns with a high number of unique values are not supported.

## Set Up Best Sellers in Category Recommendation

This section walks you through the steps to create a Best Sellers in Category strategy. Let us take an example: an apparel retailer wants to surface the most purchased items in the Apparel category over the last 30 days.

1. [Select Strategy Type](doc:best-sellers-in-category#select-strategy-type)
2. [Select Catalog](doc:best-sellers-in-category#select-catalog)
3. [ Define Consideration Criteria](doc:best-sellers-in-category#define-consideration-criteria)
4. [Define Catalog Columns for Category Grouping](doc:best-sellers-in-category#define-catalog-columns-for-category-grouping)
5. [Map Catalog Column to Event Property](doc:best-sellers-in-category#map-catalog-column-to-event-property)
6. [Enter Basic Details](doc:best-sellers-in-category#enter-basic-details)

### Select Strategy Type

Select _Best Sellers in Category_ as the strategy type.

<Image align="center" border={true} caption="Select Strategy Type" src="https://files.readme.io/44b2597f043021febe531b16a4958ae7fe9a88656671a43f913af524ce5caac3-Select_Best_Sellers_in_Category.png" />

### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the catalog containing your apparel inventory.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/e1b24099b12a16b09d9361523c7794208b16235f67312a5d497ac8dfe2ceb88b-Select_Catalog_for_Best_Sellers_in_Category.png" />

### Define Consideration Criteria

Pick the single event that defines a purchase within the category. This determines what gets counted toward the ranking.

| Event            | What it measures                                                                        |
| :--------------- | :-------------------------------------------------------------------------------------- |
| Charged          | Items most frequently purchased within the category (standard CleverTap purchase event) |
| Any custom event | Whatever signal matters most to your use case                                           |

For example, select Charged as the purchase event and set the lookback period to Last 30 days. This tells the system to count purchases from the past 30 days when ranking items within each category.

<Image align="center" border={true} caption="Define Consideration Criteria" src="https://files.readme.io/43aa3eecff2e503a6f1d320d2358e0a311ea04fea2698010a5b46b07f8a159fe-Define_Consideration_Criteria.png" />

You can click **Add Rule** to apply property filters that narrow which purchases count. For example, filtering Charged by `Gender = Female` counts only purchases from female users when identifying best sellers within a category.

### Define Catalog Columns for Category Grouping

Select the catalog column that defines how category groupings are identified. Items are grouped by the distinct values in this column, and the requested category value at serve time determines which group is returned.

For example, select _Best by Category_ to group items by their category values. This allows you to retrieve the most-purchased items in the Apparel category or any other category, independently, using the same strategy.

<Image align="center" border={true} caption="Define Catalog Column for Category Group" src="https://files.readme.io/f8a4842e39371d70725fcf7cd1c843aaa983a34fbaef62979cdf4dc7a6b3dd1d-Select_Catalog_Columns_Representing_Category.png" />

<Callout icon="📘" theme="info">
  #### Note

  Select catalog columns that have a limited number of distinct values. Columns with a high number of unique values are not supported for category grouping. Refer to the platform limits for the maximum number of unique values allowed per column.
</Callout>

### Map Catalog Column to Event Property

Map the event property containing the item identifier to the identity column of your catalog. This tells the system which catalog item each purchase belongs to. For example, map the catalog identity column to the `Product ID` event property of the `Charged` event..

<Image align="center" border={true} caption="Map Catalog Column to Event Property" src="https://files.readme.io/6f2d619cf064c172bb8c8b79a327cd5e18b2bbfff0ef0d068a12be5d0c777d3b-Map_Catalog_and_Event_Property_for_Best_Sellers_in_Category.png" />

<Callout icon="📘" theme="info">
  #### Note

  If this mapping is incorrect or missing, the system cannot match purchases to catalog items, and the strategy will return no results.
</Callout>

### Enter Basic Details

After setting up the Catalog and Criteria tab, click **Next** to enter the following basic details:.

<Image align="center" border={true} caption="Enter Basic Details" src="https://files.readme.io/20f7e7c81626945d613b00197ff15177d7c278678ef806c2f152f23ea9637188-Enter_Basic_Details_for_Best_Sellers_in_Category.png" />

| Field       | Details                                                                                                                                           |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case and time window. For example, Best Selling in Category Last 30 Days. |
| Description | An optional description for your strategy.                                                                                                        |

After adding these details, click _Save_. Once the strategy is saved and purchase events are evaluated, the strategy becomes _Active_ and can be used for campaign personalization.

In this case, the strategy surfaces the most-purchased items in the Apparel category over the past 30 days. Because no individual user history is required, the ranked list is consistent across all users browsing the same category, making it suitable for a category landing page, a category-specific push notification, or an SMS campaign driving category-level conversions.

# Personalize Campaign Using Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Personalize Setup_ panel, then select the _Recommendations_ tab.

Configure the following:

<Image align="center" border={true} caption="Personalize Campaign Using Recommendation" src="https://files.readme.io/ea8a35793e4d5dec3b7aa3f7835a878be3b9dd97de6a7255bb4e3a750f5aa254-Personalize_Campaign_Using_Best_Sellers_in_Category.png" />

## Strategy

Select the primary strategy to use for recommendations. For example, select Best Selling Apparel Last 30 Days to surface the most purchased apparel items for users browsing the category page.

After selecting the strategy, configure how the Category scope is passed at serve time:

| Option           | Description                                                                                                                                                                                                                                                               |
| :--------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Constant Value   | Returns the best sellers from the same category for all users. For example, setting `Category = Apparel` always surfaces the most purchased apparel items, regardless of who receives the recommendation.                                                                 |
| Profile Property | Returns the best-selling items in a category based on each user's profile attributes. For example, mapping to Preferred Category surfaces the most-purchased items in the category for each user's profile, making the recommendation contextually relevant to each user. |

Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against the best seller results before being returned.

## Only Include Items

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes, or Event-Based Rules to filter based on user behavior. For example, adding a catalog-based rule `Gender = Female` ensures only women's products appear in the recommendation block.

## Exclude Items

Define rules to explicitly remove certain catalog items from recommendations. For example, adding a catalog-based rule `Brand = Wrangler` ensures Wrangler-branded products do not appear in the recommendation output.

## Item Configuration

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, `Brand`, `Category`, and `Price` as the Item Attributes to Recommend, so the campaign can render each product with its name, thumbnail, brand, category, and price. Once configured, click Apply to save the personalization setup for the campaign.

# FAQs

### What is the difference between Best Sellers in Category and Best Sellers recommendations?

Best Sellers ranks items across the entire catalog. Best Sellers in Category scopes the ranking to a specific category, returning the most purchased items within that group. Use Best Sellers for catalog-wide purchase leaders and Best Sellers in Category when the context is already scoped to a product category.

### Are Best Sellers in Category recommendations personalized?

No. Best Sellers in Category recommendations reflect aggregated purchase data within a category and are not user-specific. The same ranked list is returned for all users requesting the same category. However, because the category scope is passed dynamically at serve time, you can use user attributes, such as a preferred category, to determine which category to request, making the experience feel contextually relevant.

### How is the Best Sellers in Category score calculated?

Items are ranked by total purchase frequency within the requested category and configured time window. The most purchased item in that category appears first. All purchases within the window count equally; no time-decay weighting is applied.

### What happens if there are not enough best-selling items in a category?

The strategy falls back to a separately configured fallback strategy. Fallback items are deduplicated against the best seller results before being returned. If no fallback is configured, the default value is returned.

### When should I use Best Sellers in Category recommendations?

Use this strategy when you want to highlight top-performing items within a specific category context, for example, on category landing pages, in department-specific campaigns, or as a social proof layer for category-based promotions.
