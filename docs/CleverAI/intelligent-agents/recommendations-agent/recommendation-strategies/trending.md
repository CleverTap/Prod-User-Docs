---
title: Trending
excerpt: >-
  Learn how Trending recommendations surface recently surging items to keep
  experiences current and relevant.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Trending recommendations surface the items with the fastest-growing engagement within a defined time window. Unlike popularity-based strategies that rank by total interactions, Trending applies time-decay weighting, giving greater weight to recent interactions and reducing the impact of older activity. This means results reflect what is gaining momentum right now, not what has been consistently popular over time.

Because trending recommendations are based on aggregated user behavior, they work for all users without requiring individual user history.

# Use Cases

Trending recommendations work best in contexts where recency and momentum matter, as follows:

- **Homepage and discovery surfaces**: Surfaces items gaining traction in real time, keeping the experience fresh for returning users. For example, a fashion platform displaying the fastest-rising products on its homepage.
- **Promotional email campaigns**: Highlights emerging items before they peak, creating a sense of discovery. For example, a weekly digest email surfacing the fastest-rising products in a category.
- **Low-signal Sessions**: Reliable in early-stage user journeys where behavioral data is sparse, such as during onboarding.
- **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results within a category.

# Strategy Logic

Trending recommendations identify items whose engagement is increasing rapidly within a defined time window.

During setup, you select the interaction event that represents engagement and configure the lookback period for evaluating growth.

At serving time, each interaction within the lookback window is weighted by how recently it occurred — recent interactions count more than older ones. Items are ranked by their total weighted score, so items gaining momentum today rank above items that peaked earlier in the window.

Common interaction events include:

| Industry  | Event                                   |
| :-------- | :-------------------------------------- |
| ECommerce | Product Viewed, Charged, Added to Cart  |
| OTT       | Video Watched                           |

# Required Inputs

The following inputs are required:

| Input                  | Description                                                                                                     |
| :--------------------- | :-------------------------------------------------------------------------------------------------------------- |
| Interaction event      | The user action used to measure engagement and identify trending items.                                         |
| Lookback period        | The time window over which interactions are evaluated and weighted.                                             |
| Mapping                | Connects the event property containing the item identifier to the identity column of your catalog.              |
| Consideration Criteria | Narrows which interactions count toward the trending score. For example, filter by gender or subscription plan. |

# Create Trending Strategy

This section helps you set up a strategy that surfaces items gaining the most momentum within a defined time window.

## Prerequisites

Before you begin, check if the following are in place:

- A catalog is uploaded and active.
- At least one interaction event is being tracked, such as Product Viewed, Added to Cart, or Charged.
- The tracked event references the same item ID as the catalog identity column. If they do not match, interactions cannot be attributed to catalog items.

## Set Up Trending Recommendation

This section walks you through the steps to create a Trending strategy. Let us take an example: an ecommerce platform wants to surface the fastest-rising products in its catalog based on product views over the last 7 days.

1. [Select Strategy Type](doc:trending#select-strategy-type)
2. [Select Catalog](doc:trending#select-catalog)
3. [Define Consideration Criteria](doc:trending#define-consideration-criteria)
4. [Map Catalog Column to Event Property](doc:trending#map-catalog-column-to-event-property)
5. [Enter Basic Details](doc:trending#enter-basic-details)

### Select Strategy Type

Select _Trending_ from the list of strategy types.


<Image src="https://files.readme.io/c4807318896a2f9d0cde610ea6503aab20418f735a6fab036dde29a00df71f7a-Trending_Recommendations.png" align="center" caption="Select Trending Strategy Type" border={true} />


### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the Content Catalog containing your streaming library.


<Image src="https://files.readme.io/fe2f7e74fb8653f449e8891d0b9dce92f083ad65df662665dcad4cb908b53612-Select_Catalog_OTT.png" align="center" caption="Select Catalog" border={true} />


### Define Consideration Criteria

Pick the single event that defines engagement. This determines what gets counted toward the trending score.

| Event             | What it measures                              |
| :---------------- | :-------------------------------------------- |
| Video Watched     | Titles gaining the most views                 |
| Any custom event  | Whatever signal matters most to your use case |

For example, select `Video Watched` as the interaction event and set the lookback period to Last 7 days. This tells the system to evaluate play activity from the past seven days, with recent plays weighted more heavily than older ones.

You can click **+ Filter** to apply property filters that narrow which interactions count. For example, filtering Video Played by `Device = Web` counts only plays from web users when identifying trending titles.


<Image src="https://files.readme.io/04b2ed1f5f3f543ba740087563fee5d8e0655b08ed452c7b73aa5b202d28c74f-Define_Consideration_Criteria_-_Trending.png" align="center" caption="Define Consideration Criteria" border={true} />


### Map Catalog Column to Event Property

The catalog column you select must be the column designated as the unique item identifier when setting up the catalog. This is the column the engine uses to match the event to the correct catalog item.

For example, map the catalog identity column to the `Content ID` event property of the Video Watched event.


<Image src="https://files.readme.io/51f40102e8f2483a812a497ba634128b90eed767835da454db9401c3ad7c04f6-Map_Catalog_Column_to_Event_Property_-_Trending.png" align="center" caption="Map Catalog Column to Event Property" border={true} />


<Callout icon="📘" theme="info">
  #### Note

  Ensure the mapping is correctly configured. A missing mapping means the engine has no interaction data to compute trending scores against, and the strategy returns no results. An incorrect mapping, for example, selecting a column that does not uniquely identify items; the strategy saves successfully but returns incorrect or empty results at delivery time.
</Callout>

### Enter Basic Details

After setting up the _Catalog & Criteria_ tab, click **Next** to enter the following basic details:


<Image src="https://files.readme.io/dfb08ed64f8e165ca6f91d5779f5dfb0075977c95b6ce7d84f20b494bc516fbb-Enter_Basic_Details_OTT.png" align="center" caption="Enter Basic Details" border={true} />


| Field       | Details                                                                                                                                          |
| :---------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case and time window. For example, Fastest Rising Titles Last 7 Days.    |
| Description | An optional description for your strategy.                                                                                                       |

After adding these details, click **Save**. Once the strategy is saved and interaction events are evaluated, the strategy becomes Active and can be used for campaign personalization.

In this case, the strategy surfaces titles whose view counts have grown the fastest over the past seven days. Recent plays are weighted more heavily than older ones, so a title that spiked in views today ranks above one that peaked earlier in the week. Because no individual user history is required, the ranked list is consistent across all users, making it suitable for a homepage discovery section or a weekly trending email campaign.

# Personalize Campaign Using Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Set up Personalization_ panel, then select the Recommendations tab.

Configure the following:


<Image src="https://files.readme.io/a4a05b16ede01074c08d91e4c37fb0adb76cd9c0af974f003c46811b8a7d35af-Personalize_Campaign_Using_Trending_Recommendations.png" align="center" caption="Personalize Campaign Using Trending Recommendation" border={true} />


## Strategy

Select the primary strategy to use for recommendations. For example, select Fastest Rising Titles Last 7 Days to surface trending titles for users browsing the platform.

Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against trending results before being returned.

## Inclusion Criteria

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes, or Event-Based Rules to filter based on user behavior. For example, adding a catalog-based rule `Genre = Action/Thriller` ensures only Drama titles are recommended.

## Exclusion Criteria

Define rules to explicitly remove certain catalog items from recommendations. For example, exclude titles whose `Language = Hindi`

## Final Outcome

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to 3 and select `Name`, `ImageUrl`, and `Content_url` as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, and trailer link. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### What is the difference between Trending and Popular recommendations?

Popular highlights items with consistently high engagement over a time period. Trending highlights items whose engagement is growing the fastest right now — an item does not need to be popular overall to appear in Trending results.

### Are Trending recommendations personalized?

No. Trending recommendations reflect aggregated user activity and are not user-specific. The same ranked list is returned for all users.

### How is the Trending score calculated?

Each interaction within the lookback window is weighted by how recently it occurred — recent interactions count more than older ones. Items are ranked by their total weighted score, so items gaining momentum today rank above items that peaked earlier in the window.

### What happens if there are not enough trending items?

If the primary strategy returns fewer items than requested, the configured Fallback Strategy fills the remaining slots. Fallback items are deduplicated against the primary results, so you will not see the same title recommended twice.

The fallback dropdown only shows strategies that meet all the following requirements:

- Must be a Popular or Trending strategy
- Must use the same catalog as the primary strategy
- Must not itself be category-scoped

If you have not yet created a plain Popular/Trending strategy in the same catalog, the Add Strategy option remains empty even after selecting _Fallback Strategy_.

### When should I use Trending recommendations?

Use this strategy when you want to highlight items gaining momentum and keep discovery surfaces fresh. It works well for homepages, daily push notifications, and time-sensitive campaigns where recency matters more than sustained popularity.