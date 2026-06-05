---
title: Popular
excerpt: >-
  Learn how Popular recommendations show consistently high performing items of
  the catalog using aggregated engagement to drive reliable discovery.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Popular recommendations surface consistently high-performing items from your catalog based on aggregated user interaction data over a selected time period. Because they rely on group behavior rather than individual history, they work for all users, including first-time visitors with no behavioral data.

The same catalog can produce different results depending on which interaction event is selected. For example, you can use `Product Viewed` for _popular_ or _Charged_ for Best Sellers.

# Use Cases

Popular recommendations work best when broad, data-light recommendations are needed, as follows:

* **New or anonymous users**: No browsing or purchase history is required, making this suitable for first-time visitors. For example, a homepage banner or app landing screen for users with no prior activity.
* **Broad discovery experiences**: Surfaces consistently high-performing items across the catalog. For example, an ecommerce platform displaying the most-viewed products on its homepage or category pages.
* **Low-signal sessions**: Reliable in early-stage user journeys where behavioral data is sparse. For example, during onboarding flows where personalized recommendations are not yet possible.
* **Promotional campaigns**: Drives engagement by highlighting top-performing items across the catalog. For example, a weekly email to new users featuring the most-viewed products over the past seven days.
* **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results.

# Strategy Logic

Popular recommendations rank items by aggregating user interactions over a specified time window and ordering them by total interaction volume.

During setup, you select the consideration criteria (interaction event) that defines popularity and configure the time window over which interactions are counted.

At serving time, items are ranked by total cumulative interaction volume within the configured window, with the most interacted items appearing first. Because the ranking is based on catalog-wide aggregated data, the output is consistent across all users in the same context.

Common interaction events include:

| Industry  | Event                                  |
| :-------- | :------------------------------------- |
| ECommerce | Product Viewed, Charged, Added to Cart |
| OTT       | OTTvideoview                           |

# Required Inputs

The following inputs are required:

| Input                  | Description                                                                                        |
| :--------------------- | :------------------------------------------------------------------------------------------------- |
| Consideration Criteria | The user action used to count and rank items.                                                      |
| Mapping                | Connects the event property containing the item identifier to the identity column of your catalog. |

# Optional Inputs

The following input is optional:

| Input              | Description                                                                                                                                                                           |
| :----------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Time window        | Period over which interactions are counted. If not set, all available historical data for the selected event is used.                                                                 |
| Interaction filter | Narrows which interactions count toward ranking. For example, filter by _Gender_ or _Device_ type.                                                                                    |
| Fallback strategy  | Fills remaining slots if the strategy returns fewer items than requested. If no fallback is configured and Popular returns insufficient results, the default values will be returned. |

# Create Popular Strategy

This section helps you to set up a strategy that surfaces the most interacted-with items across your catalog.

## Prerequisites

Before you begin, check if the following are in place:

* A catalog is uploaded and active.
* At least one interaction event is being tracked, such as `OTTvideoview`.
* The tracked event references the same item ID as the catalog identity column. If they do not match, interactions cannot be attributed to catalog items.

## Set Up Popular Recommendation

This section walks you through the steps to create a Popular strategy. Let us take an example: an ecommerce brand wants to recommend the most-viewed products over the last 30 days to new users.

Go to _Recommendations_ in the CleverTap dashboard, click **Create Strategy**, and perform the following steps:

1. [Select Strategy Type](doc:popular#select-strategy-type)
2. [Select Catalog](doc:popular#select-catalog)
3. [Configure Consideration Criteria](doc:popular#configure-consideration-criteria)
4. [Map Catalog Column to Event Property](doc:popular#map-catalog-column-to-event-property)
5. [Enter Basic Details](doc:popular#enter-basic-details)

### Select Strategy Type

Choose _Popular_ from the list of strategy types.

<Image align="center" border={true} caption="Select Strategy Type" src="https://files.readme.io/f8adf79dfffd263d30dbbb49dd9f64538ab4b2521e9ab8125f263ad14e022e58-Select_Strategy_Type.png" />

### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the OTTCatalogdevTV catalog containing your streaming library.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/e067453d05490315e902eccda184e8a92dc5542bb4f8b4546e5290f9dfb5fb75-Select_Catalog_for_Popular.png" />

### Configure Consideration Criteria

Pick the single event that defines popularity. This determines what gets counted.

| Event            | What it measures                              |
| :--------------- | :-------------------------------------------- |
| OTTvideoview     | Titles most watched                           |
| Any custom event | Whatever signal matters most to your use case |

For example, select OTTvideoview as the interaction event and set the lookback period to Last 30 days. This tells the system to count view activity from the past 30 days to determine which titles are most popular.

You can click **Add Rule** to apply property filters that narrow which interactions count. For example, filtering OTTvideoview by `Device = Web` counts only views from web users when identifying popular titles.

<Image align="center" border={true} caption="Select Consideration Criteria" src="https://files.readme.io/7b059ee5b18cef5a48e8f578b0d98190bdf6ac541974e924341f23b92ab61f50-Select_Consideration_Criteria_for_Popular.png" />

### Map Catalog Column to Event Property

Map the event property containing the item identifier to the identity column of your catalog. This tells the system which catalog item each interaction belongs to.

For example, map the catalog identity column to the `Content ID` event property of the OTTvideoview event.

<Image align="center" border={true} caption="Map Catalog Column to Event Property" src="https://files.readme.io/d048aec859982719ee742d4f849bf1080eaa6556ae429a779820801eefebd50d-Map_Catalog_Column_to_Event_Property_for_Popular.png" />

<Callout icon="📘" theme="info">
  #### Note

  If this mapping is incorrect or missing, the system cannot match user interactions to catalog items, and the strategy will return no results.
</Callout>

### Enter Basic Details

After setting up the Catalog and Criteria tab, click **Next** to enter the following basic details:

<Image align="center" border={true} caption="Enter Basic Details for your Strategy" src="https://files.readme.io/4e861676bad455ffb95c92fc4a990085a3c96f986778267ad57188c975fbbe85-Enter_Basic_Details_for_Popular.png" />

| Field       | Details                                                                                                                                      |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case and time window. For example, Most Watched Titles Last 30 Days. |
| Description | An optional description for your strategy.                                                                                                   |

After adding these details, click **Save**. Once the strategy is saved, interaction events are evaluated, and when the popular items are determined, the strategy becomes _Active_ and can be used for personalization in the campaigns.

In this case, the strategy surfaces the most-watched titles from the past 30 days. Because no user history is required, the ranked list is consistent across all users, making it suitable for a homepage discovery section or a weekly trending email campaign.

# Personalize Campaign Using Popular Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Personalize Setup_ panel, then select the Recommendations tab.

Configure the following:

<Image align="center" border={true} caption="Personalize Campaign Using Popular Recommendation" src="https://files.readme.io/40ab58a0f619d2f019da562bd574ba3436c0b41c37401b53594341cdd6e6b6b0-Personalize_Campaign_using_Popular_Recommendation.png" />

## Strategy

Select the primary strategy to use for recommendations. For example, select Most Watched Titles Last 30 Days to surface the most-watched titles for users browsing the platform. [8:24 AM]Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against popular results before being returned.

For example, set Trending Shows as a fallback so recommendation slots remain filled even when Popular returns fewer items than requested.

## Only Include Items

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes, or Event-Based Rules to filter based on user behavior. For example, adding a catalog-based rule `Language = Hindi` ensures only Hindi titles are recommended.

## Exclude Items

Define rules to explicitly remove certain catalog items from recommendations. For example, adding a catalog-based rule `Rating = 18+` ensures age-restricted titles do not appear in the recommendation output.

## Item Configuration

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, `genre`, and `content_url` as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, genre, and content link. Once configured, click **Apply** to save the personalization setup for the campaign.

Once the recommendation personalization is set, use Liquid Script to reference the recommendation output in your Title and Message fields.

# FAQs

### What is the difference between Popular and Trending recommendations?

Popular highlights items with consistently high engagement over the selected time window. Trending highlights items with rapidly increasing engagement, regardless of absolute volume. Use Popular for proven, stable performers. Use Trending to surface what is gaining momentum right now.

### Are Popular recommendations personalized?

No. Popular recommendations reflect aggregated user activity and are not user-specific. The same ranked list is returned for all users.

### How is the Popular score calculated?

Items are ranked by total cumulative interaction volume within the configured time window. The most interacted-with items appear first. Unlike Trending, no time-decay weighting is applied; all interactions within the window count equally.

### What happens if there are not enough popular items?

The strategy falls back to a separately configured fallback strategy. Fallback items are deduplicated against the popular results before being returned. If no fallback is configured, the default values are returned.

### When should I use Popular recommendations?

Use this strategy when you want to highlight proven, consistently high-performing items. It works well for homepages, onboarding flows, and campaigns targeting new or anonymous users where individual behavioral data is not yet available.
