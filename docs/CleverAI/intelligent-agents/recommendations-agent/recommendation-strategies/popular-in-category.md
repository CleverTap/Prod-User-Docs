---
title: Popular in Category
excerpt: >-
  Learn how Popular in Category recommendations surface the most engaged-with
  items within a specific category using aggregated user interactions.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Popular in Category surfaces the most engaged-with items within the category most relevant to each user, based on aggregated interaction data over a selected time window. The category is resolved at serving time from a user property or an event property, so each user sees trending items in their own context, without requiring personalized behavioral history.

# Use Cases

Popular in Category recommendations work best when category-scoped, data-light recommendations are needed, as follows:

- **Category pages and discovery surfaces**: Surfaces consistently high-performing items within a defined catalog subset. For example, a streaming platform displaying the most-watched titles on its Drama genre page.

- **Promotional campaigns**: Drives engagement by highlighting top items in a category relevant to the campaign context. For example, a weekly digest email featuring the most-viewed items in the Sports gear category over the past seven days surfaced to users who have a `Product Viewed` event with category = `Sports`.

- **Flash sales and time-sensitive offers**: Reinforces urgency with category-specific social proof. For example, an SMS campaign featuring the top three most-interacted products in the Electronics category during a sale window.

- **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results within a category.

# Strategy Logic

Popular in Category recommendations rank items by aggregating user interactions within a defined category scope over a specified time window.

During setup, you select the interaction event that defines engagement and configure the catalog columns that determine how category groupings are identified.

At serving time, items are retrieved within the requested category and ranked by total cumulative interaction volume, with the most interacted items appearing first. The category scope is provided when the recommendation is requested, so the same strategy can serve multiple categories without separate configurations. For example, a single Popular in Category strategy built on a streaming catalog can return the most-watched titles in Drama for one campaign and in Action for another.

Common interaction events include:

| Industry  | Event                                  |
| :-------- | :------------------------------------- |
| ECommerce | Product Viewed, Charged, Added to Cart |
| OTT       | Video Watched                          |

# Required Inputs

The following inputs are required:

| Input                  | Description                                                                                                                                                                                                                                        |
| :--------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Interaction event      | The user action used to count and rank items within the category.                                                                                                                                                                                  |
| Category               | The category is not fixed when you create the strategy. At serve time, it is resolved from a constant value, a user property, or a triggering event property. This means the same strategy can serve different categories without reconfiguration. |
| Mapping                | Connects the event property containing the item identifier to the identity column of your catalog.                                                                                                                                                 |
| Time window            | Period over which interactions are counted. If not set, all available historical data for the selected event is used.                                                                                                                              |
| Consideration Criteria | Narrows which interactions count toward ranking.                                                                                                                                                                                                   |

# Create Popular in Category Strategy

This section helps you set up a strategy to surface the most-interacted-with items in a specific category from your catalog.

## Prerequisites

Before you begin, check if the following are in place:

- A catalog is uploaded and active.
- At least one interaction event is being tracked, such as \`Video Watched.
- The tracked event references the same item ID as the catalog identity column. If they do not match, interactions cannot be attributed to catalog items.
- The catalog contains at least one column suitable for category grouping, with a limited number of distinct values. Columns with a high number of unique values are not supported.

## Set Up Popular in Category Recommendation

This section walks you through the steps to create a Popular in Category strategy. Let us take an example: an OTT platform wants to recommend the most-watched titles in the Drama genre over the last 30 days to users browsing the genre page.

Go to _Recommendations_ in the CleverTap dashboard, click **Create Strategy**, and perform the following steps:

1. [Select Strategy Type](doc:popular-in-category#select-strategy-type)
2. [Select Catalog](doc:popular-in-category#select-catalog)
3. [Define Consideration Criteria](doc:popular-in-category#define-consideration-criteria)
4. [Define Catalog Columns for Category Grouping](doc:popular-in-category#define-catalog-columns-for-category-grouping)
5. [Map Catalog Column to Event Property](doc:popular-in-category#map-catalog-column-to-event-property)
6. [Enter Basic Details](doc:popular-in-category#enter-basic-details)

### Select Strategy Type

Select _Popular in Category_ from the list of strategy types.


<Image src="https://files.readme.io/13628ec8fb6dbc636a958d5cf15dc8655eaa7fa88a39925b5a101caf3b96ab3c-Select_Popular_in_Category.png" align="center" caption="Select Popular in Category Strategy Type" border={true} />


### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the Content Catalog containing your streaming library.


<Image src="https://files.readme.io/0a203503703b0ed5f40ccbeea814d272eb98cc3ef31b91fd467d9f8fd244f7ee-Select_Catalog_for_the_Popular_in_Category.png" align="center" caption="Select Catalog" border={true} />


### Define Consideration Criteria

Pick the single event that defines popularity within the category. This determines what gets counted.

| Event         | What it measures                        |
| :------------ | :-------------------------------------- |
| Video Watched | Titles most watched within the category |

For example, select _OTTvideoview_ as the interaction event and set the lookback period to _Last 15 days_. This tells the system to count view activity from the past 15 days to determine which titles are most popular within each genre.&#x20;


<Image src="https://files.readme.io/dd7f25f992d81aed4048f9440ab7056fb1105cb73b93fd0fc98f7701daca7225-Consideration_Criteria_-_Popular_in_Category.png" align="center" caption="Define Consideration Criteria" border={true} />


Select the period over which interactions are counted.

You can click **+ Filter** to apply property filters that narrow which interactions count. For example, filtering the event by `Subscription Plan = Premium` counts only views from premium subscribers within the category.

### Define Catalog Columns for Category Grouping

Select up to three catalog columns that define how category groupings are identified. Items are grouped by the distinct values in these columns, and the requested category value at serve time determines which group is returned.

For example, if the catalog column is `Genre` with values `Drama`, `Action`, and `Comedy`, selecting `Genre` allows you to retrieve the most-watched titles in Drama or Action independently using the same strategy.


<Image src="https://files.readme.io/6c8984190967ada862b0215589c0f918e1b9aaebf35b7125ff9f3f05c5b902fc-Select_Categoru_for_Popular_in_Category.png" align="center" caption="Define Catalog Column Representing Category Grouping" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  Select catalog columns that have a limited number of distinct values. Columns with a high number of unique values are not supported for category grouping.
</Callout>

### Map Catalog Column to Event Property

The catalog column you select must be the column designated as the unique item identifier when setting up the catalog. This is the column the engine uses to match the event to the correct catalog item.

In this case, the catalog column will be mapped to the `Content ID` event property of the `OTTvideoview` event.


<Image src="https://files.readme.io/3068ee886070c420ca9bf80dcc076a9989e436ffa109dac741c9835ce73dba7d-Map_Catalog_Column_to_Event_Property_for_Popular_in_Category.png" align="center" caption="Map Catalog Column to Event Property" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  Ensure the mapping is correctly configured. A missing mapping means the engine has no data to rank items against, and the strategy returns no results. An incorrect mapping, for example, selecting a column that does not uniquely identify items; the strategy saves successfully but returns incorrect or empty results at delivery time.
</Callout>

### Enter Basic Details

After setting up the _Catalog & Criteria_ tab, click **Next** to enter the following basic details:


<Image src="https://files.readme.io/72af28659596e7025a06f651242b0d8927bec7d4113796905f7c2ed6169d6703-Enter_Basic_Details_for_Popular_in_Category.png" align="center" caption="Enter Basic Details" border={true} />


| Field       | Details                                                                                                                                                             |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case, catalog, and logic. For example, Popular content in Last 15 Days or Top Action Shows. |
| Description | An optional description for your strategy.                                                                                                                          |

After adding these details, click **Save**. Once the strategy is saved, interaction events are evaluated, and popular titles within each genre are determined, the strategy becomes Active and can be used for campaign personalization.

In this case, the strategy surfaces the most-watched Drama titles from the past 15 days. Because no individual user history is required, the ranked list is consistent across all users browsing the same genre, making it suitable for a genre page or a category-based push notification.

# Personalize

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Set up Personalization_ panel, then select the _Recommendations_ tab.

Configure the following:


<Image src="https://files.readme.io/016b6cf841e151b296f927885eaacad4450b1422b3b963a04a7be90f7ac24a18-Personalization_Setup_-_Popular_in_Category.png" align="center" caption="Personalize Campaign Using Recommendation" border={true} />


## Strategy

Select the primary strategy to use for recommendations. For example, select Popular content Last 15 Days to surface the most-watched Drama titles for users browsing the genre page.

After selecting the strategy, configure how the Category scope is passed at serve time:&#x20;

| Option         | Description                                                                                                                                                                                                                                           |
| :------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Constant Value | Returns popular items from the same category for all users. For example, setting `Genre = Drama` always surfaces the most-watched Drama titles, regardless of who receives the recommendation.                                                        |
| User Property  | Returns popular items from a category based on each user's profile attribute. For example, mapping to `Preferred Genre` surfaces the most-watched titles in that genre for each user, making recommendations contextually relevant to each user.      |
| Event Property | Returns popular items from the category resolved from the triggering event. Available for Live campaigns only. For example, mapping to `category` from a `Product Viewed` event surfaces the most popular items in the category the user just viewed. |

Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against popular results before being returned.

## Inclusion Criteria

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes or Event-Based Rules to filter by user behavior.

## Exclusion Criteria

Define rules to explicitly remove certain catalog items from recommendations. For example, adding a catalog-based rule `Language = Hindi` ensures Hindi-language titles are not recommended.

## Final Outcome

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, and so on as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, and trailer link. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### What is the difference between Popular in Category and Popular recommendations?

Popular ranks items across the entire catalog. Popular in Category scopes results to a specific category, returning the most-interacted items within that group. Use Popular for catalog-wide discovery and Popular in Category when the context is already scoped to a genre, department, or product type.

### Are Popular in Category recommendations personalized?

No. Popular in Category recommendations reflect aggregated user activity within a category and are not user-specific. The same ranked list is returned for all users requesting the same category. However, because the category scope is passed dynamically at serve time, you can use user attributes, such as a preferred genre, to determine which category to request, making the experience feel contextually relevant.

### How is the Popular in Category score calculated?

Items are ranked by total cumulative interaction volume within the requested category and configured time window. The most interacted-with items appear first. All interactions within the window count equally; no time-decay weighting is applied.

### What happens if there are not enough items in a category?&#x20;

If the primary Popular in Category strategy returns fewer items than requested, the configured Fallback Strategy fills the remaining slots. Fallback items are deduplicated against the primary results, so you will not see the same title recommended twice.

The fallback dropdown only shows strategies that meet all the following requirements:

- Must be a Popular or Trending strategy
- Must use the same catalog as the primary strategy
- Must not itself be category-scoped

If you have not yet created a plain Popular/Trending strategy in the same catalog, the Add Strategy option remains empty even after selecting _Fallback Strategy_.

### When should I use Popular in Category recommendations?

Use this strategy when you want to highlight high-performing items within a specific category context, for example, on genre pages, category landing pages, or campaigns scoped to a product type or content genre.