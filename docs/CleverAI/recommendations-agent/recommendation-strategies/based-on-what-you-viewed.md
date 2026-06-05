---
title: Based on What You Viewed
excerpt: >-
  Learn how to recommend products or content based on a user’s recent browsing
  and viewing behavior.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Based on What You Viewed recommendations surface personalized content by combining each user's individual viewing history with catalog data using a hybrid recommendation algorithm. Unlike aggregate strategies such as Popular or Trending, which return the same items for all users, Based on What You Viewed recommendations are unique to each user, surfacing titles most relevant to what they have previously watched.

Because recommendations are computed per user, this strategy requires individual interaction data to generate results. Users with insufficient viewing history within the configured time window receive the configured fallback strategy instead.

# Use Cases

Based on What You Viewed recommendations work best when personalized, and behavior-driven recommendations are needed, as follows:

* **Personalized homepage sections**: Surfaces titles relevant to each user's recent viewing activity. For example, a "Based on What You Viewed" section on a streaming platform's homepage recommending titles similar to what a user recently watched.

* **Re-engagement campaigns**: Brings lapsed users back with content relevant to their viewing history. For example, a push notification featuring titles aligned with what a user last watched before becoming inactive.

* **Post-viewing follow-up**: Drives continued engagement after a session ends. For example, an email recommending titles similar to the last show a user watched.

* **Personalized promotional campaigns**: Tailors catalog discovery to individual preferences. For example, a weekly digest email surfacing new releases relevant to a user's viewing behavior.

# Strategy

Based on What You Viewed recommendations are computed per user using a hybrid algorithm that combines each user's individual viewing history with catalog data.

During setup, you select the interaction event that captures user behavior and configure the time window over which viewing activity is evaluated. The system uses this data to identify which titles each user has engaged with and surfaces catalog items most relevant to their individual behavior.

At serving time, recommendations are personalized to each user. Users with no viewing history within the configured time window receive the configured fallback strategy instead.

Common interaction events include:

| Industry  | Event                         |
| :-------- | :---------------------------- |
| OTT       | OTTvideoview                  |
| ECommerce | Product Viewed, Added to Cart |

# Required Inputs

The following inputs are required:

| Input             | Description                                                                                        |
| :---------------- | :------------------------------------------------------------------------------------------------- |
| Interaction event | The user action used to build each user's viewing profile for recommendation.                      |
| Mapping           | Connects the event property containing the item identifier to the identity column of your catalog. |

# Optional Inputs

The following inputs are optional:

| Input                  | Description                                                                                                                                                                                                                                   |
| :--------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Time window            | Period over which viewing activity is evaluated. If not set, all available historical data for the selected event is used.                                                                                                                    |
| Consideration Criteria | Narrows which interactions count toward each user's viewing profile. For example, filter by device type or subscription plan.                                                                                                                 |
| Fallback Strategy      | Fills recommendation slots when a user has insufficient viewing history. Fallback items are deduplicated against results before being returned. If no fallback is configured and no viewing data is available, the default value is returned. |

# Create Based on What You Viewed Strategy

## Prerequisites

Before you begin, check if the following are in place:

* A catalog is uploaded and active. • At least one interaction event is being tracked, such as `OTTvideoview`.
* The tracked event references the same item ID as the catalog identity column. If they do not match, interactions cannot be attributed to catalog items.
* Users have sufficient viewing history to generate personalized results. Configure a fallback strategy for users with limited data.

## Set Up Based on What You Viewed Recommendation

This section walks you through the steps to create a Based on What You Viewed strategy. Let us take an example: an OTT platform wants to recommend titles based on what each user has recently watched over the last 30 days.

1. [Select Strategy Type](doc:based-on-what-you-viewed#select-strategy-type)
2. [Select Catalog](doc:based-on-what-you-viewed#select-the-catalog)
3. [Define Consideration Criteria](doc:based-on-what-you-viewed#define-consideration-criteria)
4. [Map Catalog Column to Event Property](doc:based-on-what-you-viewed#map-catalog-column-to-event-property)
5. [Enter Basic Details](doc:based-on-what-you-viewed#enter-basic-details)

### Select Strategy Type

Select _Hybrid Recommendation Strategy_ from the list of strategy types.

<Image align="center" border={true} caption="Select Strategy Type" src="https://files.readme.io/7bf1154c4f17c913248fcf887dd575eda19789f3493b93b8285c8f0bcc34b1a8-Frequently_Bought_Together.png" />

### Select the Catalog

Select the catalog to use. The catalog must be active and contain the items you want to recommend. For example, select the`OTTCatalogdevTV` catalog containing your streaming library.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/b7a2d7ab9e3dc763abd5f6a7235934957e98cde28b3f3acb478d2a734b450c67-Select_Catalog_for_Based_on_What_You_Viewed.png" />

### Define Consideration Criteria

Pick the single event that captures viewing behavior. This determines which interactions are used to build each user's recommendation profile.

| Event            | What it measures                                         |
| :--------------- | :------------------------------------------------------- |
| OTTvideoview     | Titles each user has watched                             |
| Any custom event | Whatever behavioral signal matters most to your use case |

For example, select OTTvideoview as the interaction event and set the lookback period to Last 30 days. This tells the system to evaluate each user's viewing activity from the past 30 days when generating personalized recommendations.

You can click **Add Rule** to apply property filters that narrow which interactions count.

<Image align="center" border={true} caption="Define Consideration Criteria" src="https://files.readme.io/a3280a44596da4b65217dfd6df517a800781297538edfd65476316394f006fee-Define_Consideration_Criteria_for_Based_on_What_You_Viewed.png" />

### Map Catalog Column to Event Property

Map the event property containing the item identifier to the identity column of your catalog. This tells the system which catalog item each viewing interaction belongs to. For example, map the catalog identity column to the Content ID event property of the OTTvideoview event.

<Image align="center" border={true} caption="Map Catalog Column to Event Property" src="https://files.readme.io/9f59ec5a4265a79000788d178dd320da8d9f10adc0f22702dbb17048955b1f38-Map_Catalog_and_Event_Property_for_Based_on_What_You_Viewed.png" />

## Enter Basic Details

After setting up the Catalog and Criteria tab, click Next to enter the following basic details:

<Image align="center" border={true} caption="Enter Basic Details" src="https://files.readme.io/92206c5df7f3ab1fc2a04a3e1d352a24f7513f9ff19d9e125a40490c5683d2e7-Entrer_Basic_Details_for_Based_on_What_You_Viewed.png" />

| Field       | Details                                                                                                              |
| :---------- | :------------------------------------------------------------------------------------------------------------------- |
| Name        | Name the strategy using a clear, descriptive name that reflects the use case. For example, Based on What You Viewed. |
| Description | An optional description for your strategy.                                                                           |

After adding these details, click Save. Once the strategy is saved and the viewing events are evaluated, the strategy becomes Active and can be used for campaign personalization.

In this case, the strategy surfaces titles based on each user's viewing activity from the past 30 days. Because recommendations are personalized per user, each user receives a unique set of recommendations based on their individual viewing history, making it suitable for a homepage discovery section or a re-engagement push notification.

# Personalize Campaign Using Recommendation

Once the strategy is active, you can use it to personalize recommendations in your campaigns. To configure recommendations within a campaign, click **Personalize** to open the _Personalize Setup_ panel, then select the _Recommendations_ tab.

Configure the following:

<Image align="center" border={true} caption="Personalize Campaign Using Recommendation" src="https://files.readme.io/aded138a15dbec9656639185bcc81f75853057f2e678d1c9dc537d8fd9d69be5-Personalize_Campaign_Using_Based_on_What_You_Viewed.png" />

## Strategy

Based on What You Viewed recommendations are computed per user using a hybrid algorithm that combines each user's individual viewing history with catalog-level product similarity.

During setup, you select the interaction event that captures viewing behavior and configure the time window for evaluating activity. The system applies time-decay weighting to each viewing interaction; recently watched titles influence recommendations more than older ones. Product embeddings are then used to identify catalog items most similar to each user's recently viewed titles.

At serving time, recommendations are personalized to each user. The system retrieves the user's recent viewing history, weights each viewed title by recency, and surfaces catalog items most similar to those titles based on product embeddings. Users with no viewing history within the configured time window receive the configured fallback strategy instead.

## Only Include Items

Define rules to restrict which catalog items are eligible for recommendation. You can add Catalog-Based Rules to filter by catalog attributes, or Event-Based Rules to filter based on user behavior. For example, adding a catalog-based rule Producer = Netflix ensures only Netflix-produced titles are recommended.

## Exclude Items

Define rules to explicitly remove certain catalog items from recommendations. For example, adding an event-based rule to exclude titles a user has already watched ensures previously viewed content does not reappear in recommendations.

## Item Configuration

Specify how many items to recommend and which catalog attributes to return for each item. For example, set Items to Recommend to `3` and select `Name`, `ImageUrl`, `language`, `content_url`, and producer as the Item Attributes to Recommend, so the campaign can render each title with its name, thumbnail, language, content link, and producer. Once configured, click Apply to save the personalization setup for the campaign.

# FAQs

### What makes Based on What You Viewed different from Popular or Trending?

Popular and Trending surface the same items for all users based on aggregate behavior. Based on What You Viewed generates a unique set of recommendations for each user based on their individual viewing history. Use Popular or Trending for catalog-wide discovery; use Based on What You Viewed when recommendations should reflect what each specific user has watched.

### Is the Based on What You Viewed recommendation personalized?

Yes. Recommendations are computed per user using a hybrid algorithm that combines each user's individual viewing history with catalog data. Each user receives a distinct set of recommendations tailored to their behavior.

### How are items selected for Based on What You Viewed recommendations?

The strategy evaluates each user's viewing history within the configured time window and applies time-decay weighting, with recently watched titles count more than older ones. For each viewed title, the system identifies catalog items with the highest product similarity using vector embeddings. Scores are aggregated across all recently viewed titles, and the top-ranked results are returned.

### What happens if a user has no viewing history?

The strategy falls back to a separately configured fallback strategy. Fallback items are deduplicated against the results before being returned. If no fallback is configured, the remaining recommendation slots will be empty.

### When should I use Based on What You Viewed recommendations?

Use this strategy when you want to deliver personalized recommendations based on individual viewing behavior, for example, in homepage discovery sections, re-engagement campaigns, or post-viewing follow-up messages, so each user receives content relevant to their viewing history.
