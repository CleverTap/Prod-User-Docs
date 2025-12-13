---
title: Creating a Recommendation
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
You can create a recommendation by choosing a catalog and defining the required configurations based on which our recommendation engine will churn out results.\
These recommendations will be served up to users automatically when you create a campaign using the recommendation.

To create new recommendations, go to Recommendations under the Engage section on the dashboard.

<Image title="Recommendations_Menu Item.png" alt={168} className="border" border={true} src="https://files.readme.io/e67a8d2-Recommendations_Menu_Item.png" />

# Step 1 Create a Recommendation

Click on "+ Recommendation" on the top-right of the Recommendation menu to generate a new recommendation.

<Image title="New Recommendation.png" alt={973} className="border" border={true} src="https://files.readme.io/3205de3-New_Recommendation.png" />

# Step 2 Select a Catalog

Select a catalog on which to generate recommendations. Here, you will be able to access the catalogs for which you have mapped events.

<Image title="Select Catalog.png" alt={950} className="border" border={true} src="https://files.readme.io/789138e-Select_Catalog.png" />

> 📘 Unmapped catalog
>
> Unmapped catalogs will not be available for generating recommendations

# Step 3 Select an Event

This is the event on which CleverTap will consider similar items.

Example\
**My ecommerce App**

1. In case of an e-commerce application, you may wish to trigger a recommendation as soon as a user adds a Nike shoe to cart. 

* In this scenario, you can recommend other shoes to the user 
* This can be either based on the shoes that (s)he may have 'viewed' together', 'searched' together, etc. in the last 30 days
* In this case the event you should choose is "viewed" together or "searched" together\
  **My OTT App**

2. In case of a video streaming application, you may wish to trigger a recommendation once a user completes watching a trailer of a fantasy TV series. 

* In this scenario, you can recommend other shows that have been "Watched" together with fantasy TV shows in the last 10 days. 
* In this case, the event you should choose is "Watched" together.

Select the event on which to generate recommendations. Here, you will be able to access the events that have been mapped to the chosen catalog. 

Next, you select the relevant timeframe for which you want to generate the recommendations. E.g. Create recommendations for items which have been **viewed together** in the **last 10 days** 

<Image title="Recco mapped event.png" alt={947} className="border" border={true} src="https://files.readme.io/7f87cda-Recco_mapped_event.png" />

# Step 4 Filter recommendations

You can filter the items that are served up to include only certain items.\
E.g. in case of a video streaming platform, you could choose to recommend only English videos. Similarly, you could also choose to serve up only promoted content or high margin content.

![944](https://files.readme.io/b30c843-Reco_Include_criteria.png "Reco_Include criteria.png")

You could also choose to exclude certain items. E.g. in case of a video streaming platform, you could choose to exclude "A rated" content from recommendations.

![944](https://files.readme.io/5e663e4-Reco_Exclude_criteria.png "Reco_Exclude criteria.png")

> 📘 Note
>
> It takes up to 24 hours for the CleverTap Data Science Engine to publish the recommendations from the time the recommendation is generated
