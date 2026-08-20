---
title: More Like These
excerpt: >-
  Learn how to recommend products or content that closely match a user’s
  interests based on similar items.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

More Like These recommendations surface catalog items most similar to a specific item, based on content similarity computed from catalog attributes and product images. Unlike user-based strategies, such as Based on What You Viewed, More Like These does not require any user interaction history; it takes a catalog item as the reference point and returns the most similar items from the catalog.

Because recommendations are item-based rather than user-based, they work for all users regardless of interaction history, making this strategy suitable for any context where a specific item is already in focus, such as a product detail page.

<Callout icon="📘" theme="info">
  #### Note

  Similarity is computed from the catalog attributes and product images you select when configuring the strategy. Including a description for each catalog item is strongly recommended, as it serves as an additional signal for the model. This is especially important for catalogs where images are less distinctive, such as streaming or OTT content.
</Callout>

# Use Cases

More Titles Like This recommendations work best when item-context recommendations are needed, as follows:

- **Title detail pages**: Surfaces similar titles on the page of a title a user is currently viewing. For example, a "More Like These" section below a documentary the user is watching, recommending other titles with similar themes, genre, or tags.
- **Post-viewing recommendations**: Drives continued engagement after a session ends. For example, recommending titles similar to the last show a user completed watching.
- **Email and push campaigns**: Anchors recommendations to a specific title. For example, an email campaign featuring titles similar to a recently released documentary to drive discovery of related content.
- **Reliable fallback for personalized strategies**: Provides relevant item-level recommendations when user history is unavailable.

# Strategy Logic

More Like These recommendations surface catalog items most similar to a selected item, based on the attributes and images configured in your catalog.

At the time of strategy creation, no interaction events or user data are configured; only the catalog is selected. The system uses pre-computed product embeddings to measure similarity between catalog items.

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

# Create More Like These Strategy

This section helps you set up a strategy that surfaces catalog items similar to a specified seed title.

## Prerequisites

Before you begin, check if the following are in place:

- A catalog is uploaded and active.
- The catalog contains sufficient items for similarity computation.

## Set Up More Titles Like This Recommendation

This section walks you through the steps to create a More Titles Like This strategy. Let us take an example: an OTT platform wants to recommend titles similar to whichever title a user is currently viewing.

1. [Select Strategy Type](doc:more-like-this#select-strategy-type)
2. [Select Catalog](doc:more-like-this#select-catalog)
3. [Enter Basic Details](doc:more-like-this#enter-basic-details)

### Select Strategy Type

Select _Content Recommendation Strategy_ from the list of strategy types.


<Image src="https://files.readme.io/aef148bb6b561c88f4b66e08817f83754fee0c89fd9728228b3f6d74ced0207e-Select_More_Like_These_.png" align="center" caption="Select Strategy Type" border={true} />


### Select Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the catalog containing your streaming library.

Unlike engagement-based strategies, More Like These does not require an interaction event. Similarity is computed entirely from your catalog data, the attributes, and images you select in the next step.


<Image src="https://files.readme.io/9d0be4c436e835077b3ddbe93497782619efef608fe0c76b0c69c48546816926-Select_Catalog_for_More_Like_This.png" align="center" caption="Select Catalog" border={true} />


### Enter Basic Details

After selecting the catalog, click **Next** to enter the following basic details:


<Image src="https://files.readme.io/a5316fbeaacd42c1d8f1e3e7207465a83121637313108e2e2a5569fa597c2736-Enter_Basic_Details_for_More_LIke_this.png" align="center" caption="Enter Basic Details" border={true} />


# Personalize Campaign Using More Like These Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the Set up _Personalization_ panel, then select the _Recommendations_ tab.

Configure the following:


<Image src="https://files.readme.io/63aacfe5b1ab7ddd1254b4145da4eff1ea6632c12dfd7e3fa00e08d87eb44ce6-Personalize_Using_More_Like_These.png" align="center" caption="Personalize Campaign Using More LIke These Strategy" border={true} />


## Strategy

Select the primary strategy to use for recommendations. For example, select _More Titles Like This_ to surface titles similar to a specific seed title.

After selecting the strategy, configure how the reference title is resolved at serve time:

<Table align={["left","left",null]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        Description
      </th>

      <th>

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        User Property
      </td>

      <td>
        Returns titles similar to a seed item resolved from each user's profile attribute.
      </td>

      <td>
        Map  `Content ID` so that the strategy uses the content stored on each user's profile as the reference at serve time.
      </td>
    </tr>

    <tr>
      <td>
        Constant Property
      </td>

      <td>
        Returns titles similar to the same fixed seed item for all users. Enter a specific content identity so that the strategy always surfaces titles similar to that title, regardless of who receives the recommendation.
      </td>

      <td>
        Select _User property_ and map it  to `Content ID` so the strategy
        uses the content stored on each user's profile as the reference at serve time.
      </td>
    </tr>

    <tr>
      <td>
        Event Property
      </td>

      <td>
        - Resolves the item from a property on the triggering event.

        * Available for Live campaigns only.
      </td>

      <td>
        Map to `Content ID` from the VideoWatched event so that the strategy surfaces titles similar to what the user viewed.
      </td>
    </tr>
  </tbody>
</Table>

For our use case, select _Profile Property_ and map it to `Content ID` so that the system uses the content identity stored on each user's profile as the reference at serve time.

Optionally, enable _Fallback Strategy_ to specify one or more fallback strategies that activate when the primary strategy cannot return enough items, for example, when no Content ID is set on a user's profile. Fallback strategies are evaluated in order of priority, with the last fallback used only if all preceding strategies return insufficient results. Fallback items are deduplicated against results before being returned.

For example, set _Popular Titles_ as a fallback so recommendation slots remain filled when no reference identity is available.

## Inclusion Criteria

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes or Event-Based Rules to filter by user behavior. For example, adding a catalog-based rule `Language = Hindi` ensures only Hindi-language titles appear in the recommendation output.

## Exclusion Criteria

Define rules to explicitly remove certain catalog items from recommendations. For example, adding an event-based rule to exclude titles that a user has `Already Watched` ensures previously viewed content does not reappear in recommendations.

## Final Outcome

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, `content_type`, and `content_url` as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, content type, and content link. Once configured, click **Apply** to save the personalization setup for the campaign.

# FAQs

### What makes More Like These different from Based on What You Viewed?

Based on What You Viewed personalizes recommendations using each user's viewing history, surfacing titles similar to what a user has recently watched. The More Like These strategy takes a single title as the reference and returns the most similar titles to that item, regardless of who is viewing. Use Based on What You Viewed for personalized discovery; use _More Like These_ when recommendations should be anchored to a specific title in context.&#x20;

### Does More Like These require user interaction history?

No. More Like These is item-based, not user-based. It requires only the identity of a seed item at serve time and returns similar items from the catalog using content similarity. No user interaction data is needed.

### How are items selected for More Like These recommendations?

The strategy uses product embeddings to measure content similarity between catalog items. At serve time, the system takes the seed item's identity, queries the catalog for items with the highest vector similarity to that seed, and returns the top-ranked results.

### What happens if there are not enough similar items?

If the primary strategy returns fewer items than requested, the configured Fallback Strategy fills the remaining slots. Fallback items are deduplicated against the primary results, so you will not see the same title recommended twice.

The fallback dropdown only shows strategies that meet all the following requirements:

- Must be a Popular or Trending strategy
- Must use the same catalog as the primary strategy
- Must not itself be category-scoped

If you have not yet created a plain Popular/Trending strategy in the same catalog, the Add Strategy option remains empty even after selecting _Fallback Strategy_.

### When should I use More Like These recommendations?

Use this strategy when recommendations should be anchored to a specific item rather than to a user's history, for example, on title detail pages, in post-viewing follow-up campaigns, or in any context where a specific title is already in focus, and you want to surface similar content.