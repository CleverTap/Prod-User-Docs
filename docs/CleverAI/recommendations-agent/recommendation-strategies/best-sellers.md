---
title: Best Sellers
excerpt: >-
  Learn how to recommend top-performing products or content based on overall
  sales and popularity trends.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Best Sellers recommendations surface items with the highest purchase activity from your catalog over a selected time period. Unlike engagement-based strategies such as Popular or Trending, Best Sellers rank items by purchase frequency, making them a reliable indicator of what users are actually buying, not just browsing.

Because Best Sellers rely on aggregated purchase data rather than individual user history, they work for all users, including first-time visitors with no behavioral data.

# Use Cases

Best Sellers recommendations work best when purchase-driven discovery is needed, as follows:

- **Promotional campaigns**: Highlights products with proven purchase performance. For example, a monthly newsletter featuring the top 10 most-purchased products across the catalog helps subscribers shop with confidence.
- **Push notifications**: Re-engages lapsed users with high-converting items. For example, a push notification highlighting the best-selling products from the past week, prompting users to return and make a purchase. •
- **SMS campaigns**: Drive conversions through social proof before a sale. For example, an SMS to opt-in users featuring the three most purchased items in the catalog before a seasonal event.
- **Homepage and discovery surfaces**: Surfaces consistently purchased items to new or anonymous users who have no browsing history.
- **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results.

# Strategy Logic

Best Sellers recommendations rank items based on total purchase activity over a configured time window.

During setup, you select the consideration criteria (purchase event) that defines what counts as a sale and configure the time window over which purchases are counted.

At serving time, items are ranked from highest to lowest by total purchase frequency within the configured window. Because the ranking is based on catalog-wide aggregated purchase data, the output is consistent across all users in the same context.

Common interaction events include:

| Industry       | Event                  |
| :------------- | :--------------------- |
| ECommerce      | Charged, Order Placed  |
| Food & Grocery | Order Placed           |
| OTT            | Subscription Purchased |

# Required Inputs

The following inputs are required:

| Input                  | Description                                                                                                        |
| :--------------------- | :----------------------------------------------------------------------------------------------------------------- |
| Consideration Criteria | The user action used to count and rank items by purchase frequency.                                                |
| Mapping                | Connects the event property containing the item identifier to the identity column of your catalog.                 |
| Time window            | Period over which purchases are counted. If not set, all available historical data for the selected event is used. |
| Consideration Criteria | Narrows which purchases count toward ranking.                                                                      |

# Create Best Sellers Strategy

This section helps you set up a strategy to surface the most-purchased items from your catalog.

## Prerequisites

Before you begin, check if the following are in place:

- A catalog is uploaded and active.
- At least one purchase event is being tracked, such as `Order Placed` or `Charged`.
- The tracked event references the same item ID as the catalog identity column. If they do not match, purchases cannot be attributed to catalog items.

## Set Up Best Sellers Recommendation

This section walks you through the steps to create a Best Sellers strategy. Let us take an example: a food and grocery platform wants to surface the most purchased products across its catalog over the last 30 days.

1. [Select Strategy Type](doc:best-sellers#select-strategy-type)
2. [Select Catalog](doc:best-sellers#select-catalog)
3. [Define Consideration Criteria](doc:best-sellers#define-consideration-criteria)
4. [Map Catalog Column to Event Property](doc:best-sellers#map-catalog-column-to-event-property)
5. [Enter Basic Details](doc:best-sellers#enter-basic-details)

### Select Strategy Type

Select _Best Sellers_ from the list of strategy types.


<Image src="https://files.readme.io/3f73071be3ba7e8dc2ec2b9de655d0ca1a5ac5a7e0fb95c584dbe24ce878d2d8-Select_Best_Sellers_Recommendation.png" align="center" caption="Select Strategy Type" border={true} />


### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the catalog containing your apparel inventory.


<Image src="https://files.readme.io/d483c8bc62fc1319dddd3be300b27591ce9df6ebd36fd91af3960a7d670a3881-Select_Catalog_for_Best_Sellers_Srategy.png" align="center" caption="Select Catalog" border={true} />


### Define Consideration Criteria

Pick the single event that defines a purchase. This determines what gets counted toward the ranking.

| Event            | What it measures                                                    |
| :--------------- | :------------------------------------------------------------------ |
| Charged          | Items most frequently purchased (standard CleverTap purchase event) |
| Any custom event | Whatever signal matters most to your use case                       |

For example, select `Charged` as the purchase event and set the lookback period to Last 30 days. This tells the system to count purchases from the past 30 days when ranking items.


<Image src="https://files.readme.io/00c24a78c3ea319de53a694a773273147b52b9cb2778fb6aa9606296d12580fd-Define_Consideration_Criteria_-_Best_Sellers.png" align="center" caption="Define Consideration Criteria" border={true} />


You can click **Add Rule** to apply property filters that narrow which purchases count. For example, filtering _Charged_ by `Gender = Female` counts only purchases from female users when identifying best sellers.

### Map Catalog Column to Event Property

The catalog column you select must be the column designated as the unique item identifier when setting up the catalog. This is the column the engine uses to match the event to the correct catalog item.&#x20;

For example, map the catalog identity column to the `Product ID` event property of the _Charged_ event.


<Image src="https://files.readme.io/c57a074ad8107d17e8ab14caccbb89faa957c6879fd202b02e3fc6076522daae-Map_Catalog_Column_to_Event_Property_-_Best_Sellers.png" align="center" caption="Map Catalog Column to Event Property" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  Ensure the mapping is correctly configured. A missing mapping means the engine has no interaction data to compute trending scores against, and the strategy returns no results. An incorrect mapping, for example, selecting a column that does not uniquely identify items; the strategy saves successfully but returns incorrect or empty results at delivery time.
</Callout>

### Enter Basic Details

After setting up the _Catalog & Criteria_ tab, click **Next** to enter the following basic details:


<Image src="https://files.readme.io/afa735875f5cb4ae8ad2eb2ba54983bea6c9419c70b5b1c3a4c58374dad451e4-Enter_Basic_Details_for_Best_Sellers.png" align="center" caption="Enter Basic Details" border={true} />


| Field       | Details                                                                                                                                          |
| :---------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case and time window. For example, Best Seller Products in Last 30 Days. |
| Description | An optional description for your strategy.                                                                                                       |

After adding these details, click **Save**. Once the strategy is saved and purchase events are evaluated, the strategy becomes Active and can be used for campaign personalization.

In this case, the strategy surfaces the most-purchased products over the past 30 days. Because no individual user history is required, the ranked list is consistent across all users, making it suitable for a homepage best-sellers section, a monthly promotional email, or an SMS campaign driving conversions through social proof.

# Personalize Campaign Using Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Set up Personalization_ panel, then select the _Recommendations_ tab.

Configure the following:


<Image src="https://files.readme.io/009f0004044da7edc575dd1ac779d26ef39297d301ca76850e88f6a440f13e43-Personalize_Using_Best_Sellers_Recommendations.png" align="center" caption="Personalize Campaign Using Recommendation" border={true} />


## Strategy

Select the primary strategy to use for recommendations. For example, select Best Seller Products in the Last 30 Days to surface the most-purchased products across the catalog for all users.

Optionally, enable _Fallback Strategy_ to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated from the best-seller results before being returned.

For example, set _Trending Products_ as a fallback so recommendation slots remain filled even when Best Sellers returns fewer items than requested.

## Inclusion Criteria

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes or Event-Based Rules to filter by user behavior. For example, adding a catalog-based rule `Category = Tops` ensures only tops appear in the recommendation block.

## Exclusion Criteria

Define rules to explicitly remove certain catalog items from recommendations. For example, adding a catalog-based rule `Brand = Wrangler` ensures Wrangler-branded products do not appear in the recommendation output.

## Final Outcome

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, `Brand, Category`, and `Price` as the Item Attributes to Recommend, so the campaign can render each product with its name, thumbnail, brand, category, and price. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### Are Best Sellers recommendations personalized?

No, these recommendations are based on aggregated purchase data and apply to all users.

### How is this different from Popular recommendations?

Best Sellers are based on purchases, while Popular recommendations can be based on other engagement events such as views or add-to-cart actions.

### What determines ranking?

Ranking is based on the total number of purchases within the selected time window.

### When should I use Best Sellers recommendations?

Use this strategy when you want to promote products with strong purchase performance.

<br />
