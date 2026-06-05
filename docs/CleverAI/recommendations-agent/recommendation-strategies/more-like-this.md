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

More Titles Like This recommendations surface catalog items most similar to a specific title, based on content similarity computed from product embeddings. Unlike user-based strategies such as Based on What You Viewed or Frequently Bought Together, More Titles Like This does not require any user interaction history — it takes a single catalog item as the seed and returns the items most similar to it.

Because recommendations are item-based rather than user-based, they work for all users regardless of their interaction history, making this strategy suitable for any context where a specific title is already in focus.

# Use Cases

More Titles Like This recommendations work best when item-context recommendations are needed, as follows:

* **Title detail pages**: Surfaces similar titles on the page of a title a user is currently viewing. For example, a "More Like This" section below a documentary the user is watching, recommending other titles with similar themes, genre, or tags.
* **Post-viewing recommendations**: Drives continued engagement after a session ends. For example, recommending titles similar to the last show a user completed watching.
* **Email and push campaigns**: Anchors recommendations to a specific title. For example, an email campaign featuring titles similar to a recently released documentary to drive discovery of related content.
* **Reliable fallback for personalized strategies**: Provides relevant item-level recommendations when user history is unavailable.

# Strategy Logic

More Titles Like This recommendations are computed using a content-based algorithm that identifies catalog items most similar to a specified seed item.

At strategy creation time, no interaction event or user data is configured; only the catalog is selected. The system uses pre-computed product embeddings to measure similarity between catalog items.

At serving time, you provide the identity of the seed item, the specific title the user is currently viewing or the campaign is anchored to. The system queries the catalog using vector similarity to identify and return the items most similar to that seed, ranked by similarity score.

Common use cases by industry:

| Industry  | Seed Item                      | What it surfaces                        |
| :-------- | :----------------------------- | :-------------------------------------- |
| OTT       | Title currently being viewed   | Similar titles by genre, tags, or theme |
| ECommerce | Product currently being viewed | Similar products by attributes          |

# Required Inputs

The following input is required:

| Input   | Description                                                                                                                             |
| :------ | :-------------------------------------------------------------------------------------------------------------------------------------- |
| Catalog | The active catalog from which similar items are retrieved. The system uses the catalog's product embeddings to compute item similarity. |

# Optional Inputs

The following input is optional:

| Input             | Description                                                                                                                                                                                                                                                       |
| :---------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fallback Strategy | Fills recommendation slots if the strategy cannot return enough similar items. Fallback items are deduplicated against results before being returned. If no fallback is configured and insufficient similar items are found, the default values will be returned. |

# Create More Like This Strategy

This section helps you set up a strategy that surfaces catalog items similar to a specified seed title.

## Prerequisites

Before you begin, check if the following are in place:

* A catalog is uploaded and active.
* The catalog contains sufficient items for similarity computation.

## Set Up More Titles Like This Recommendation

This section walks you through the steps to create a More Titles Like This strategy. Let us take an example: an OTT platform wants to recommend titles similar to whichever title a user is currently viewing.

1. [Select Strategy Type](doc:more-like-this#select-strategy-type)
2. [Select Catalog](doc:more-like-this#select-catalog)
3. [Enter Basic Details](doc:more-like-this#enter-basic-details)

### Select Strategy Type

Select _Content Recommendation Strategy_ from the list of strategy types.

<Image align="center" border={true} caption="Select Strategy Type" src="https://files.readme.io/1b3dd664ac5c88726bad68695a01b657273a9a8895138eee29130c554b391460-Select_Algorithm_for_More_lIke_This_.png" />

### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the catalog containing your streaming library.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/9d0be4c436e835077b3ddbe93497782619efef608fe0c76b0c69c48546816926-Select_Catalog_for_More_Like_This.png" />

### Enter Basic Details

After selecting the catalog, click **Next** to enter the following basic details:

<Image align="center" border={true} caption="Enter Basic Details" src="https://files.readme.io/a5316fbeaacd42c1d8f1e3e7207465a83121637313108e2e2a5569fa597c2736-Enter_Basic_Details_for_More_LIke_this.png" />

# Personalize Campaign Using More Titles Like This Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Personalize Setup_ panel, then select the _Recommendations_ tab.

Configure the following:

<Image align="center" border={true} caption="Personalize Campaign Using More LIke This Strategy" src="https://files.readme.io/087b4131a427d0ecad3c4207a06a21d317b1073ee4c565bbb12efb61fbf49224-Perosanalize_Campaign_Using_More_Like_This.png" />

## Strategy

Select the primary strategy to use for recommendations. For example, select _More Titles Like This_ to surface titles similar to a specific seed title.

After selecting the strategy, configure how the seed item identity is passed at serve time:

| Option            | Description                                                                                                                                                                                                                                                      |
| :---------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Profile Property  | Returns titles similar to a seed item resolved from each user's profile attribute. For example, mapping to Content ID surfaces titles most similar to the specific content identity stored on each user's profile, such as the title they are currently viewing. |
| Constant Property | Returns titles similar to the same fixed seed item for all users. For example, entering a specific content identity always surfaces titles similar to that title, regardless of who receives the recommendation.                                                 |

For example, select _Profile Property_ and map it to `Content ID` so the system uses the content identity stored on each user's profile as the seed at serve time.

Optionally, enable Fallback Strategy to specify one or more fallback strategies that activate when the primary strategy cannot return enough items, for example, when no Content ID is set on a user's profile. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against results before being returned.

For example, set _Popular Titles_ as a fallback so recommendation slots remain filled when no seed identity is available.

## Only Include Items

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes, or Event-Based Rules to filter based on user behavior. For example, adding a catalog-based rule `Language = Hindi` ensures only Hindi-language titles appear in the recommendation output.

## Exclude Items

Define rules to explicitly remove certain catalog items from recommendations. For example, adding an event-based rule to exclude titles a user has `Already Watched` ensures previously viewed content does not reappear in recommendations.

## Item Configuration

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, `content_type`, and `content_url` as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, content type, and content link. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### What makes More Like This different from Based on What You Viewed?

Based on What You Viewed personalizes recommendations using each user's individual viewing history, it surfaces titles similar to everything a user has recently watched. More Like This strategy takes a single specific title as the seed and returns the most similar titles to that item, regardless of who is viewing. Use Based on What You Viewed for personalized discovery; use _More Like This_ when recommendations should be anchored to a specific title in context.

### Does More Like This require user interaction history?

No. More Like This is item-based, not user-based. It requires only the identity of a seed item at serve time and returns similar items from the catalog using content similarity. No user interaction data is needed.

### How are items selected for More Like This recommendations?

The strategy uses product embeddings to measure content similarity between catalog items. At serve time, the system takes the seed item's identity, queries the catalog for items with the highest vector similarity to that seed, and returns the top-ranked results.

### What happens if there are not enough similar items?

The strategy falls back to a separately configured fallback strategy. Fallback items are deduplicated against the results before being returned. If no fallback is configured, the default value is returned.

### When should I use More Like This recommendations?

Use this strategy when recommendations should be anchored to a specific item rather than to a user's history, for example, on title detail pages, in post-viewing follow-up campaigns, or in any context where a specific title is already in focus and you want to surface similar content.
