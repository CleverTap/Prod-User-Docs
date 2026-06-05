---
title: More Like This
excerpt: >-
  Learn how to recommend products or content that closely match a user’s
  interests based on similar items.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

More Like This recommendations surface products with similar attributes to a selected item. These attributes are derived from catalog data and can include category, price range, brand, or other product characteristics. The catalog must include a product description field to improve recommendation quality.

# Advantages

* Helps users discover similar or alternative products
* Supports comparison shopping with relevant options
* Leverages catalog attributes to maintain contextual relevance
* Provides fallback discovery when a specific product is unavailable

# Use Cases

Use More Like This recommendations in the following scenarios:

* **Promotional email campaigns:**  
  For example, a browse abandonment email that surfaces products with attributes similar to those a user recently viewed, helping them discover alternatives they may not have considered.

* **Push notifications:**  
  For example, a push notification is sent when a product a user viewed goes out of stock, surfacing similar alternatives based on catalog attributes to keep them engaged.

* **SMS campaigns:**  
  For example, an SMS to lapsed users featuring products in a category, brand, or price range similar to items they previously viewed, prompting them to return and explore.

# Strategy Logic

More Like This uses an AI-powered content-based recommendation algorithm that generates semantic product embeddings from catalog attributes and product images. The system identifies genuinely similar items based on a product's nature, content, metadata, and visual characteristics, rather than relying solely on user behavior or co-interaction patterns. This enables high-quality recommendations even for new or low-interaction products, helping solve the cold-start problem common in collaborative filtering systems.

# Required Inputs (any one)

The following inputs are required:

* Product ID, the source product to find similar items

(OR)

* user ID, which uses the user's recent interaction history to identify source products

## Optional Inputs

The following inputs are optional:

* Additional catalog attributes, such as category, brand, price, and description, improve embedding quality
* Time window controls recency decay when user history is used
* Fallback strategy fills remaining slots if insufficient results are returned

# Items and Attributes

The key items and attributes are as follows:

* Uses catalog attributes and product images to generate semantic embeddings
* Description, category, brand, and price are optional, but they improve the similarity quality
* Does not require user interaction; can work from a single product ID
* Effective for new catalog items with no behavioral data (cold-start)

# Create More Like This Strategy

To create a More Like This strategy, follow the steps:

1. [Select Strategy Type]()
2. [Select Catalog]()
3. [Define an Interaction Event]()
4. [Set a Mapping (Required)]()
5. [Save]()

## Select Strategy Type

Select _More Like This_ as the strategy type.

## Select the Catalog

Select the catalog that contains the items you want to recommend.

## Define an Interaction Event (Required for User-Based Recommendations)

Select the user action used to capture browsing or purchase activity, for example, `Product Viewed`. This event is required when recommendations are based on the user's recent interaction history. If you intend to base recommendations on a specific product ID instead, this step is not required, as the product ID is passed directly at invocation time.

Specify the time window in which interaction events are evaluated. Only events that occur within this window are counted toward the recommendation output.

Interaction event filters are supported. For example, you can configure `Product Viewed` where device type is Mobile to surface similar products for mobile users.

## Set a Mapping (Required)

Map the interaction event properties to the corresponding catalog item attributes so the system can associate user actions with catalog items.

## Save

Save the strategy configuration. Once saved, catalog attributes are evaluated, and when similar items are identified, the strategy becomes Active and can be used for campaign personalization.

# Personalize

More Like This recommendations can be personalized if a user ID is provided. In that case, the user's recent interaction history is used to identify source products, with recency as the weighing factor. If no user history is available, a specific product ID must be provided in the request to anchor the similarity search.

When you invoke a More Like This recommendation as part of an engagement, you can pass a user ID or a specific product ID to control which item or user history anchors the similarity search.

## Fallback Strategy

If the system cannot generate sufficient recommendations from attribute similarity, it falls back to a configurable fallback strategy set at setup time. If neither user ID nor product ID is provided, the system automatically falls back to the configured fallback strategy. Configure the fallback when adding this strategy to a campaign, not during strategy setup.

# Example

The following example shows how a More Like This strategy is configured for a furniture retailer that wants to surface similar products based on catalog attributes.

## Furniture - Products Similar to a Viewed Item

| Setting           | Value            |
| ----------------- | ---------------- |
| Strategy type     | More Like This   |
| Interaction event | `Product Viewed` |
| Time window       | Last 7 days      |

**Result:** The strategy surfaces products that are semantically similar to a product the user has recently viewed, based on catalog attributes such as category, brand, price, and product description. For example, a user who viewed a mid-century modern dining table is shown similar tables with comparable style, material, and price range. This setup is suitable for a browse abandonment email, an out-of-stock push notification, or a printed mailer featuring similar alternatives.

# FAQs

### Are More Like This recommendations personalized?

Results depend on how the strategy is invoked. When based on a specific product, the results are the same for all users viewing that item. When based on a user's browsing history, results are personalized per user.

### What attributes are used to determine similarity?

All available catalog attributes for a product are used to determine similarity, including product title, category, brand, price, tags, and other metadata. The product description is of utmost importance because it provides the richest context for the item's features, use cases, and characteristics.

### What is the difference between using a product ID and a user ID?

When a product ID is provided, the strategy finds items similar to that specific product. Results are the same for every user who encounters that product. When a user ID is provided, the strategy uses the user's recent browsing history to identify source products, and the results are personalized for each user.

### Can I use both a product ID and a user ID together?

If a user ID is provided, the system uses the user's browsing history to determine the source product. A product ID can serve as a fallback if no browsing history is available.

### Does More Like This work for newly added catalog items?

Yes. Because similarity is computed from catalog attributes and content embeddings rather than interaction counts, new catalog items can appear in recommendations immediately after they are added, without requiring any purchase or view history. This makes More Like This effective for surfacing newly launched products alongside established ones.

### What happens if neither a product ID nor a user ID is available?

The system falls back to the configured fallback strategy. No recommendations are served without at least one of these inputs.

### Why is the description field important?

The description provides additional context, improving similarity matching between products.

### When should I use More Like This recommendations?

Use this strategy when you want to show similar or alternative items based on product attributes.
