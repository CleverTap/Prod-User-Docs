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
You can create a recommendation by choosing a catalog and defining the required configurations based on which our recommendation engine will churn out results. 
These recommendations will be served up to users automatically when you create a campaign using the recommendation.

To create new recommendations, go to Recommendations under the Engage section on the dashboard.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e67a8d2-Recommendations_Menu_Item.png",
        "Recommendations_Menu Item.png",
        168,
        421,
        "#44455f"
      ],
      "border": true
    }
  ]
}
[/block]
# Step 1 Create a Recommendation
Click on "+ Recommendation" on the top-right of the Recommendation menu to generate a new recommendation.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3205de3-New_Recommendation.png",
        "New Recommendation.png",
        973,
        257,
        "#f1f6f5"
      ],
      "border": true
    }
  ]
}
[/block]
#Step 2 Select a Catalog
Select a catalog on which to generate recommendations. Here, you will be able to access the catalogs for which you have mapped events.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/789138e-Select_Catalog.png",
        "Select Catalog.png",
        950,
        342,
        "#f6f7fb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Unmapped catalog",
  "body": "Unmapped catalogs will not be available for generating recommendations"
}
[/block]
#Step 3 Select an Event
This is the event on which CleverTap will consider similar items.

Example  
**My ecommerce App**
1. In case of an e-commerce application, you may wish to trigger a recommendation as soon as a user adds a Nike shoe to cart. 
* In this scenario, you can recommend other shoes to the user 
* This can be either based on the shoes that (s)he may have 'viewed' together', 'searched' together, etc. in the last 30 days
 * In this case the event you should choose is "viewed" together or "searched" together
**My OTT App**
2. In case of a video streaming application, you may wish to trigger a recommendation once a user completes watching a trailer of a fantasy TV series. 
 * In this scenario, you can recommend other shows that have been "Watched" together with fantasy TV shows in the last 10 days. 
 * In this case, the event you should choose is "Watched" together.

Select the event on which to generate recommendations. Here, you will be able to access the events that have been mapped to the chosen catalog. 

Next, you select the relevant timeframe for which you want to generate the recommendations. E.g. Create recommendations for items which have been **viewed together** in the **last 10 days** 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f87cda-Recco_mapped_event.png",
        "Recco mapped event.png",
        947,
        333,
        "#f5f7fa"
      ],
      "border": true
    }
  ]
}
[/block]
#Step 4 Filter recommendations
You can filter the items that are served up to include only certain items. 
E.g. in case of a video streaming platform, you could choose to recommend only English videos. Similarly, you could also choose to serve up only promoted content or high margin content.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b30c843-Reco_Include_criteria.png",
        "Reco_Include criteria.png",
        944,
        458,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]
You could also choose to exclude certain items. E.g. in case of a video streaming platform, you could choose to exclude "A rated" content from recommendations.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e663e4-Reco_Exclude_criteria.png",
        "Reco_Exclude criteria.png",
        944,
        458,
        "#f9f9fb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "It takes up to 24 hours for the CleverTap Data Science Engine to publish the recommendations from the time the recommendation is generated",
  "title": "Note"
}
[/block]