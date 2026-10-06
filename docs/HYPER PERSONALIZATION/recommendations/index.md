---
title: Recommendations
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The recommendations feature is key in helping marketers engage and retain their customer base as it provides the capability to create personalized content for each user based on their unique historical data.

Using recommendations in campaigns and journeys will boost overall engagement throughout the user’s lifecycle across multiple channels such as, in-apps, batch campaigns, or push notifications. Powered by a scalable architecture, this feature can cater to the millions of users you are trying to reach.

<Callout icon="📘" theme="info">
  #### Availability

  Recommendations feature is available only on the _Cutting Edge_ plan.&#x20;

  The new and enhanced [Recommendations](doc:recommendations-agent) feature is available only on the _Ultimate_ plan. To access this feature, contact your Customer Success Manager.
</Callout>

# How it Works

The following demonstrates how recommendations work:

- Once a catalog is uploaded into CleverTap, after 24 hours, the relationships among catalog items are used to form the basis of generating recommendations for a particular event. The catalog can also pick items to serve up recommendations.

- Then, you can create a recommendation by defining certain rules that indicate which catalog you want to use, the catalog value, the event on the basis of which recommendation is to be generated, the lookback window, and any specific filtering criteria.

- While building a campaign or journey, use recommendations to personalize each interaction with each one of your users to create a delightful experience.

- Once the recommendation is built into a campaign or journey, your users will receive personalized recommendations based on their past history of interaction with other products.

- **Triggered Campaigns**<br />In the case of triggered campaigns, if the user performs the event defined for the last action under recommendations in the last 60 days and also performs the qualifying event, they will receive the campaigns.

  **Example**<br />Consider the example where the Charged event is the event defined for the last action under recommendations, and Added to cart is the qualifying event.

  - **Scenario 1: Receive the Campaign**<br />If the user performs Charged event on the same day at 6 p.m., they will receive the campaign as soon as they perform the Added to cart event next.
  - **Scenario 2: Did not Receive the Campaign**<br />If the user has not performed the Charged event in the last 60 days and performs the Added to cart event on a certain date at 4 p.m., they will not receive the campaign.

- **PBS Campaigns**<br />In the case of Past Behavior Segment (PBS) campaigns, if the user performs the qualifying event and has also performed the event defined for the last action performed under recommendations in the last 60 days, they will receive the campaign.

  **Example**<br />Consider the example where Charged event is the event defined for the last action under recommendations, and the Product Viewed in the last 30 days is the segment definition. If 100 users qualify for the segment definition and only 80 users have performed the Charged event in the last 60 days, only 80 users will receive the campaign along with recommendations.

# Examples

Below are some examples showing how recommendations can be used:

1. John receives relevant and timely recommendations to purchase soccer merchandise as he recently added a pair of soccer shoes to his shopping cart. His list of recommendations would be based upon what other people interested in purchasing soccer shoes have been doing around this time of the year.

2. Jane has just watched _Game of Thrones_. Next, she receives an instant, in-app recommendation that suggests her to watch similar English drama series and other titles that are often viewed by viewers who also watch _Game of Thrones_. These recommendations are also sensitive to recent trends and patterns.
