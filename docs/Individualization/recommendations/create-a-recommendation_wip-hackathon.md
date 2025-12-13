---
title: Create a Recommendation_WIP hackathon
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
REVIEW EXISTING LIVE PAGE AND ASSESS WHAT INFO CAN BE INCORPORATED FROM THE HACKATHON COPY.

How to generate recommendations
Setup a Catalog - This step covers uploading the catalog and mapping it to Events which would be used for recommendation creation. The Catalog items are used to  create associations which can be recommended and then used for personalisation within the recommendation content. Follow steps here for uploading a catalog - LINK
Setup a Recommendation - This step is to set up the Recommendation model which will generate the associations of different items present in the Catalogs.
From the dashboard, navigate to Settings > Engage > Recommendations.
Click + Recommendation.
Select the Catalog
Select the Event - This step is used to select the event which will be used for grouping multiple behaviours. Example, Product Viewed, grouping of Users would be done based on the Product Viewed event.
Select the Relevancy Period - This step is used to define the basket range in which items are to be considered as together or within one basket. Example, create recommendations for items which were Viewed together in 10 day buckets.
Filter Catalog items - This step is used to filter out items that are to be included/excluded in the recommendation creation. Example, any item from a restaurant which has a rating of 2.5 or less, should not be used in the recommendation association.

Note: An account can have 5 recommendations at any given point in time.