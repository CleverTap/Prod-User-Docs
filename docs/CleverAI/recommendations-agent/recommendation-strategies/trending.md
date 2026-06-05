---
title: Trending
excerpt: >-
  Learn how Trending recommendations surface recently surging items to keep
  experiences current and relevant.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Trending recommendations surface the items with the fastest-growing engagement within a defined time window. Unlike popularity-based strategies that rank by total interactions, Trending applies time-decay weighting, giving greater weight to recent interactions and gradually reducing the impact of older activity, so the results reflect what is gaining momentum right now, not what has been consistently popular over time.

Because trending recommendations are based on aggregated user behavior, they work for all users without requiring individual user history.

# Use Cases

Trending recommendations work best in contexts where recency and momentum matter, as follows:

* **Homepage and discovery surfaces**: Surfaces items gaining traction in real time, keeping the experience fresh for returning users. For example, a fashion platform displaying the fastest-rising products on its homepage.
* **Promotional email campaigns**: Highlights emerging items before they peak, creating a sense of discovery. For example, a weekly digest email surfacing the fastest-rising products in a category.
* **Low-signal Sessions**: Reliable in early-stage user journeys where behavioral data is sparse, such as during onboarding.
* **Reliable fallback slot**: A dependable default when a primary strategy cannot return sufficient results within a category.

# Strategy Logic

Trending recommendations identify items whose engagement is increasing rapidly within a defined time window.

During setup, you select the interaction event that represents engagement and configure the lookback period used to evaluate growth.

At serving time, each interaction within the lookback window is weighted by how recently it occurred — recent interactions count more than older ones. Items are ranked by their total weighted score, so items gaining momentum today rank above items that peaked earlier in the window.

Common interaction events include:

| Industry  | Event                                   |
| :-------- | :-------------------------------------- |
| ECommerce | Product Viewed, Charged, Added to Cart  |
| OTT       | Video Watched                           |

# Required Inputs

The following inputs are required:

| Input             | Description                                                                                        |
| :---------------- | :------------------------------------------------------------------------------------------------- |
| Interaction event | The user action used to measure engagement and identify trending items.                            |
| Lookback period   | The time window over which interactions are evaluated and weighted.                                |
| Mapping           | Connects the event property containing the item identifier to the identity column of your catalog. |

# Optional Inputs

The following inputs are optional:

| Input                  | Description                                                                                                                                                                                                                                                                                                                                                 |
| :--------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Consideration Criteria | Narrows which interactions count toward the trending score. For example, filter by gender or subscription plan.                                                                                                                                                                                                                                             |
| Fallback Strategy      | Fills remaining slots if the trending results return fewer items than requested. Configured when adding the strategy to a campaign, not during strategy setup. Fallback items are deduplicated against trending results before being returned. If no fallback is configured and trending returns insufficient results, the default values will be returned. |

# Create Trending Strategy

This section helps you set up a strategy that surfaces items gaining the most momentum within a defined time window.

## Prerequisites

Before you begin, check if the following are in place:

* A catalog is uploaded and active.
* At least one interaction event is being tracked, such as Product Viewed, Added to Cart, or Charged.
* The tracked event references the same item ID as the catalog identity column. If they do not match, interactions cannot be attributed to catalog items.

## Set Up Trending Recommendation

This section walks you through the steps to create a Trending strategy. Let us take an example: an ecommerce platform wants to surface the fastest-rising products in its catalog based on product views over the last 7 days.

1. [Select Strategy Type](doc:trending#select-strategy-type)
2. [Select Catalog](doc:trending#select-catalog)
3. [Define Consideration Criteria](doc:trending#define-consideration-criteria)
4. [Map Catalog Column to Event Property](doc:trending#map-catalog-column-to-event-property)
5. [Enter Basic Details](doc:trending#enter-basic-details)

### Select Strategy Type

Select _Trending_ from the list of strategy types.

<Image align="center" border={true} caption="Select Trending Strategy Type" src="https://files.readme.io/cb4bcf89684514c115597ceee6238eb508d962f9fb1d76e4acdaddc4f5fe9647-Select_Trending_Strategy_Type.png" />

### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the Content Catalog containing your streaming library.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/fe2f7e74fb8653f449e8891d0b9dce92f083ad65df662665dcad4cb908b53612-Select_Catalog_OTT.png" />

### Define Consideration Criteria

Pick the single event that defines engagement. This determines what gets counted toward the trending score.

| Event             | What it measures                              |
| :---------------- | :-------------------------------------------- |
| Video Watched     | Titles gaining the most views                 |
| Any custom event  | Whatever signal matters most to your use case |

For example, select Video Watched as the interaction event and set the lookback period to Last 7 days. This tells the system to evaluate play activity from the past seven days, with recent plays weighted more heavily than older ones.

You can click **Add Rule** to apply property filters that narrow which interactions count. For example, filtering Video Played by `Device = Web` counts only plays from web users when identifying trending titles.

<Image align="center" border={true} caption="Define Consideration Criteria" src="https://files.readme.io/d9b0bb4028b09a4335f5e2f560598e3153f204ad658aec31a0660857587cbdfa-Consideration_Criteria_for_Trending.png" />

### Map Catalog Column to Event Property

Map the event property containing the item identifier to the identity column of your catalog. This tells the system which catalog item each interaction belongs to. For example, map the catalog identity column to the `Content ID` event property of the Video Watched event.

<Image align="center" border={true} caption="Map Catalog Column to Event Property" src="https://files.readme.io/213c91632995a06f25d17d801ddf7cdfe200f8a80becc308c282dadb068d1818-Map_Catalog_Column_to_Event_Property_OTT.png" />

<Callout icon="📘" theme="info">
  #### Note

  If this mapping is incorrect or missing, the system cannot match user interactions to catalog items, and the strategy will return no results.
</Callout>

### Enter Basic Details

After setting up the Catalog and Criteria tab, click **Next** to enter the following basic details:

<Image align="center" border={true} caption="Enter Basic Details" src="https://files.readme.io/dfb08ed64f8e165ca6f91d5779f5dfb0075977c95b6ce7d84f20b494bc516fbb-Enter_Basic_Details_OTT.png" />

| Field       | Details                                                                                                                                          |
| :---------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case and time window. For example, Fastest Rising Titles Last 7 Days.    |
| Description | An optional description for your strategy.                                                                                                       |

After adding these details, click **Save**. Once the strategy is saved and interaction events are evaluated, the strategy becomes Active and can be used for campaign personalization.

In this case, the strategy surfaces titles whose view counts have grown the fastest over the past seven days. Recent plays are weighted more heavily than older ones, so a title that spiked in views today ranks above one that peaked earlier in the week. Because no individual user history is required, the ranked list is consistent across all users, making it suitable for a homepage discovery section or a weekly trending email campaign.

# Personalize Campaign Using Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click Personalize to open the Personalize Setup panel, then select the Recommendations tab.

Configure the following:

<Image align="center" border={true} caption="Personalize Campaign Using Trending Recommendation" src="https://files.readme.io/e1ceb7353f243e6dc86f42228e96333e970dc62d54f4c5f8eaecabaacd1343d6-Fastest_Rising_Titles_Last_7_Days_OTT.png" />

## Strategy

Select the primary strategy to use for recommendations. For example, select Fastest Rising Titles Last 7 Days to surface trending titles for users browsing the platform.

Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against trending results before being returned.

## Only Include Items

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes, or Event-Based Rules to filter based on user behavior. For example, adding a catalog-based rule `Genre = Action/Thriller` ensures only Drama titles are recommended.

## Exclude Items

Define rules to explicitly remove certain catalog items from recommendations. For example, exclude titles whose `Language = Hindi`

## Item Configuration

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to 3 and select `Name`, `ImageUrl`, and `Content_url` as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, and trailer link. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### What is the difference between Trending and Popular recommendations?

Popular highlights items with consistently high engagement over a time period. Trending highlights items whose engagement is growing the fastest right now — an item does not need to be popular overall to appear in Trending results.

### Are Trending recommendations personalized?

No. Trending recommendations reflect aggregated user activity and are not user-specific. The same ranked list is returned for all users.

### How is the Trending score calculated?

Each interaction within the lookback window is weighted by how recently it occurred — recent interactions count more than older ones. Items are ranked by their total weighted score, so items gaining momentum today rank above items that peaked earlier in the window.

### What happens if there are not enough trending items?

The strategy falls back to a separately configured fallback strategy. Fallback items are deduplicated against the trending results before being returned. If no fallback is configured, the remaining recommendation slots will be empty.

### When should I use Trending recommendations?

Use this strategy when you want to highlight items gaining momentum and keep discovery surfaces fresh. It works well for homepages, daily push notifications, and time-sensitive campaigns where recency matters more than sustained popularity.
