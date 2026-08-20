---
title: Trending in Category
excerpt: >-
  Learn how to surface rapidly rising items within a specific category based on
  recent engagement growth.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Trending in Category recommendations surface the items whose engagement is growing the fastest within a specific category. Unlike trending strategies that evaluate momentum across the entire catalog, Trending in Category applies time-decay weighting scoped to a category, giving greater weight to recent interactions and gradually reducing the impact of older activity, so the results reflect what is gaining momentum within that category right now.

Because Trending in Category recommendations are based on aggregated user behavior scoped to a category, they work for all users without requiring individual user history. The category is not fixed when you create the strategy. At serve time, it is resolved from a constant value, a user property, or a triggering event property. This means the same strategy can serve different categories without reconfiguration.

# Use Cases

Trending in Category recommendations work best when category-scoped, momentum-driven recommendations are needed, as follows:

- **Category pages and discovery surfaces**: Surfaces items gaining traction within a defined catalog subset. For example, an OTT platform displaying the fastest-rising titles on its Drama genre page.
- **Promotional campaigns**: Highlights emerging items within a category before they peak. For example, a category-specific email surfacing the fastest-rising products in the Electronics category.
- **Flash sales and time-sensitive offers**: Drives urgency around items with a sharp spike in category-level activity. For example, a push notification to users who have browsed the Footwear category, highlighting items that have seen a sharp spike in engagement over the past 24 hours.
- **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results within a category.

# Strategy Logic

Trending in Category recommendations identify items whose engagement is increasing rapidly within a specific category and a defined time window.

During setup, you select the interaction event that represents engagement and configure the catalog columns that determine how category groupings are identified.

At serving time, items are retrieved within the requested category and ranked by how quickly their engagement is growing; recent interactions are weighted more heavily than older ones. Items that have recently gained momentum score higher than those with historically high engagement that have plateaued. The category scope is provided when the recommendation is requested, so the same strategy can serve multiple categories without separate configurations. For example, a single Trending in Category strategy built on a streaming catalog can return the fastest-rising titles across premium and non-premium content for one campaign and across premium content for another.

Common interaction events include:

| Industry  | Event                                  |
| :-------- | :------------------------------------- |
| ECommerce | Product Viewed, Charged, Added to Cart |
| OTT       | VideoWatched                           |

# Required Inputs

The following inputs are required:

| Input              | Description                                                                                                                                                                                                    |
| :----------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Interaction event  | The user action used to measure engagement and identify trending items within the category.                                                                                                                    |
| Category           | The category to scope results to. Not configured during strategy creation, provided dynamically when the recommendation is requested. The same strategy can serve multiple categories without reconfiguration. |
| Mapping            | Connects the event property containing the item identifier to the identity column of your catalog.                                                                                                             |
| Time window        | Period over which interactions are evaluated and weighted. If not set, all available historical data for the selected event is used.                                                                           |
| Interaction filter | Narrows which interactions count toward the trending score. For example, filter by device type or subscription plan.                                                                                           |

# Create Trending in Category Strategy

This section helps you set up a strategy to surface the fastest-rising items in a specific category from your catalog.

## Prerequisites

Before you begin, check if the following are in place:

- A catalog is uploaded and active.
- At least one interaction event is being tracked, such as VideoWatched, Product Viewed, or Charged.
- The tracked event references the same item ID as the catalog identity column. If they do not match, interactions cannot be attributed to catalog items.
- The catalog contains at least one column suitable for category grouping that has a limited number of distinct values. Columns with a high number of unique values are not supported.

## Set Up Trending in Category Recommendation

This section walks you through the steps to create a Trending in Category strategy. Let us take an example: an OTT platform wants to surface the fastest-rising titles among premium content, based on video watches over the last seven days.

To create a Trending in Category strategy, perform the following steps:

1. [Select Strategy Type](doc:trending-in-category#select-strategy-type)
2. [Select Catalog](doc:trending-in-category#select-catalog)
3. [Define Consideration Criteria](doc:trending-in-category#define-consideration-criteria)
4. [Define Catalog Columns for Category Grouping](doc:trending-in-category#define-catalog-columns-for-category-grouping)
5. [Map Catalog Column to Event Property](doc:trending-in-category#map-catalog-column-to-event-property)
6. [Enter Basic Details](doc:trending-in-category#enter-basic-details)

### Select Strategy Type

Select _Trending in Category_ from the list of strategy types.


<Image src="https://files.readme.io/baef1f0e6233f08a8d1e9a6736fd49df5dbff10c221daa95c3e3bda9a3d47a9b-Select_Trending_in_Category_Recommendation.png" align="center" caption="Select Strategy" border={true} />


### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the OTT catalog containing your streaming library.


<Image src="https://files.readme.io/7b4c6480d418a45d79474ddae67a74d27388472a55c4f11b6d3c46c980f77fcb-Select_Catalog_for_Trending_in_Category_Recomm.png" align="center" caption="Select Catalog" border={true} />


### Define Consideration Criteria

Pick the single event that defines engagement within the category. This determines what gets counted toward the trending score.

| Event            | What it measures                                    |
| :--------------- | :-------------------------------------------------- |
| VideoWatched     | Titles gaining the most watches within the category |
| Any custom event | Whatever signal matters most to your use case       |

For example, select `VideoWatched` as the interaction event and set the lookback period to Last 7 days. This tells the system to evaluate watch activity from the past seven days, with recent watches weighted more heavily than older ones.


<Image src="https://files.readme.io/fdb32c44360d0ee06c0517eea3e550a7e1143fb6536dfb8c7e7002c8965ded71-Select_Catalog_for_Trending_in_Category_Recomm.png" align="center" caption="Select Catalog" border={true} />


You can click **+ Filter** to apply property filters that narrow which interactions count. For example, filtering _VideoWatched_ by `Device = Web` counts only watches from web users when identifying trending titles within the category.

### Define Catalog Columns for Category Grouping

Select up to three catalog columns that define how category groupings are identified. Items are grouped by the distinct values in these columns, and the requested category value at serve time determines which group is returned.

For example, if the catalog column is `Is Premium` with values `true` and `false`, selecting `Is Premium` lets you retrieve the fastest-rising titles for premium or non-premium content independently using the same strategy.


<Image src="https://files.readme.io/57945237d9b8459eb2e9acdf1191ff539ae1e09dc3e0927d345aa2613e8f10b6-Define_Catalog_Columns_for_Category_Grouping_-_Trending_in_Category.png" align="center" caption="Define Catalog Column Representing Category for Grouping" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  Select catalog columns that have a limited number of distinct values. Columns with a high number of unique values are not supported for category grouping.

  The values in these columns are also used when configuring the category scope in your campaign; ensure the corresponding user profile attribute or constant value you plan to use matches the values in the catalog column exactly.
</Callout>

### Map Catalog Column to Event Property

The catalog column you select must be the column designated as the unique item identifier when setting up the catalog. This is the column the engine uses to match the event to the correct catalog item.&#x20;

For example, map the catalog identity column to the `Content ID` event property of the _VideoWatched_ event.


<Image src="https://files.readme.io/cc4ca1b19cd7b7c07f0fe9a111afeafaafb9157d02423bee2951621d573b9e9e-Map_Catalog_Column_to_Event_Property.png" align="center" caption="Map Catalog Column to Event Property" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  Ensure the mapping is correctly configured. A missing mapping means the engine has no interaction data to compute trending scores within the category, and the strategy returns no results. An incorrect mapping, for example, selecting a column that does not uniquely identify items; the strategy saves successfully but returns incorrect or empty results at delivery time.
</Callout>

### Enter Basic Details

After setting up the _Catalog & Criteria_ tab, click **Next** to enter the following basic details:

| Field       | Details                                                                                                                                                                             |
| :---------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case and time window. For example, Trending Premium Titles Last 7 Days or Fastest Rising Non-Premium Shows. |
| Description | An optional description for your strategy.                                                                                                                                          |

After adding these details, click **Save**. Once the strategy is saved and interaction events are evaluated, the strategy becomes Active and can be used for campaign personalization.

In this case, the strategy surfaces premium titles whose watch counts have grown the fastest over the past seven days. Recent watches are weighted more heavily than older ones, so a title gaining momentum today ranks above one that peaked earlier in the week. Because no individual user history is required, the ranked list is consistent across all users browsing the same content tier, making it suitable for a premium landing page or a category-based push notification.

# Personalize Campaign Using Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Personalize Setup_ panel, then select the _Recommendations_ tab.

Configure the following:


<Image src="https://files.readme.io/2e229baa644ae83261824f1b87ec921c414255c6621a262a6a9b84b5f5a6927b-Personalize_Campaigns_Using_Trending_in_Category_Recommendations.png" align="center" caption="Personalize Campaign Using Trending in Category" border={true} />


## Strategy

Select the primary strategy to use for recommendations. For example, select _Trending Premium Titles Last 7 Days_ to surface the fastest-rising titles among premium content.

When you select a Trending in Category strategy, the setup panel displays a Define field for each catalog column you configured for category grouping during strategy setup. These fields let you specify how the category value is determined at serve time for each dimension.

For each catalog column, choose one of the following:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        When to use
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Profile Property
      </td>

      <td>
        The category value is read dynamically from the user's profile at serving time. Different users receive recommendations scoped to their own category.
      </td>

      <td>
        Map `is_premium` to the user's Customer Type profile attribute. Each user sees trending titles scoped to the Customer Type value on their profile.
      </td>
    </tr>

    <tr>
      <td>
        Constant Property
      </td>

      <td>
        The category value is fixed for the entire campaign. All users receive recommendations scoped to the same category.
      </td>

      <td>
        Set `is_premium` to true so all users see trending premium titles, or false for non-premium titles.
      </td>
    </tr>

    <tr>
      <td>
        Event Property
      </td>

      <td>
        - Resolves the item from a property on the triggering event.&#x20;

        * Available for Live campaigns only.&#x20;
      </td>

      <td>
        Map to `Content ID` from the VideoWatched event
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  #### Note

  When using Profile Property, the values in the selected user profile attribute must match those in the catalog column. For example, if the `Is Premium` catalog column has values `true` and `false`, the mapped profile attribute must return one of those values for each user. If the values do not match, the system cannot scope results correctly and may return no items.
</Callout>

Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against trending results before being returned. For example, set _Trending Titles_ as the fallback so users always see trending content, even if there are insufficient results for their category scope.

## Inclusion Criteria

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes or Event-Based Rules to filter by user behavior. For example, adding a catalog-based rule `Genre = Action/Thriller` ensures only Action and Thriller titles are recommended.

## Exclusion Criteria

Define rules to explicitly remove certain catalog items from recommendations. For example, adding a catalog-based rule `Language = Hindi` excludes Hindi-language titles from the recommendation output.

## Final Outcome

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `content_url`, and `ImageUrl` as the Item Attributes to Recommend, so the campaign can render each title with its name, content link, and thumbnail. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### Are Trending in Category recommendations personalized?

Yes. You can use user or event personalization while passing the category scope and get the corresponding trending items.

### How is this different from Trending recommendations?

Trending in Category is limited to a specific category, while Trending considers engagement growth across the broader catalog.

### What determines ranking?

Items are ranked based on how quickly their engagement is growing within the selected category.

### When should I use Trending in Category recommendations?

Use this strategy when you want to highlight emerging items within a specific category context.