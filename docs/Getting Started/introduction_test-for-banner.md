---
title: Introduction_test for banner
excerpt: >-
  <a href="https://clevertap.com/live-product-demo/"><img
  src="https://files.readme.io/6df4aa6-Demo_CTA_for_Docs.png" width="125%" ></a>
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[![](https://files.readme.io/6df4aa6-Demo_CTA_for_Docs.png)](https://clevertap.com/live-product-demo/)

CleverTap enables you to integrate app analytics and marketing, and our platform helps you increase user engagement in three ways: 
  * Track actions users are taking in your app to analyze how people use your product. 
  * [Segment](doc:segments) users based on their actions and run targeted [campaigns](doc:intro-to-campaigns) to these segments. 
  * [Analyze](doc:intro-to-reports) each of your campaigns to understand their effect on user engagement and your business metrics.

# Platform Features

The CleverTap platform has five parts: 

* CleverTap's dashboard where you can [segment](doc:segments) your users based on their actions and profile properties, run [targeted campaigns](doc:intro-to-campaigns) to these segments, and [analyze](doc:intro-to-reports) each campaign’s performance. 
* [SDKs](https://developer.clevertap.com/docs/clevertap-sdks) that let you track users’ actions within your mobile apps and websites. Our SDKs also enable you to personalize your app by giving you access to user profile data.
* [APIs](https://developer.clevertap.com/docs/api-overview) that let you push user profile or event data from any source to CleverTap. Our APIs also enable you to export your data from CleverTap for analysis in BI tools and enrich customer information in CRMs.
* Integrations with communication platforms such as [SendGrid](doc:sendgrid) and [Twilio](doc:twilio), attributions providers like [Branch](doc:branch) and [Tune](doc:tune), and remarketing platforms such as [Facebook Audience Network](doc:facebook-audience-network).
* [Webhooks](doc:webhooks) that let you trigger workflows in your backend systems as soon as qualifying events occur.

# Core Concepts

Users, events, segments, campaigns, and reports are central to CleverTap, so it is important to understand each role. 

* **Users:** After you [integrate the CleverTap SDK](https://developer.clevertap.com/docs), a [user profile](doc:user-profiles) is created for each person who launches your app or visits your website. The CleverTap user profile has a set of default fields such as device and location. You can also extend the default user profile data model by adding custom fields that are specific to your business.
* **Events:** The CleverTap SDK lets you track the actions users perform in your app or website such as a user viewing a product, listening to a song, or making a purchase. [Events](doc:events) are associated with a user profile.
* **Segments:** CleverTap enables you to create segments, which are a group of users whose actions or user profile properties match a set of criteria you’ve defined. Once you’ve created a segment, you can target them with a campaign or create a report to analyze them. 
* **Campaigns:** CleverTap [campaigns](doc:intro-to-campaigns) enable you to communicate with your users at scale. CleverTap offers 13 different messaging channels to reach your users on the optimal channel.
* **Reports:** CleverTap enables you to build [reports](doc:reports-1) to understand the impact of your campaigns on your users. You can use these reports to analyze your user engagement and guide product decisions.

# Example Use Case

The following is an example of how a CleverTap customer in the retail industry is using our platform to increase sales:

When a person launches the company’s app for the first time, we automatically create a CleverTap [user profile](doc:user-profiles) for the person with our SDK. As the person navigates through product pages in the app, we log these actions as [events](doc:events) associated with the user’s profile. 

The user’s interaction with the company extends beyond the app though. To complete a purchase, the user contacts the company’s call center, and the company adds this purchase event to the user’s profile with our [server-side API](https://developer.clevertap.com/docs/api-overview). 

Now, the marketer at the company wants to rewards its most loyal users and incentivize them to buy more. Through CleverTap’s dashboard, the marketer can [create a campaign](doc:intro-to-campaigns) to show an [in-app notification](doc:in-app) to users who recently made a purchase above a certain price. Next time the user launches the app, they will see a personalized message thanking them for buying that specific product and a discount code for their next purchase. 

To close this loop, the marketer can create a [report](doc:intro-to-reports) in the CleverTap dashboard to measure the impact of that campaign in terms of both user engagement and product sales. 

# Getting Started

The best place to get started with CleverTap is our **[quickstart guide](doc:quickstart-guide)**, which shows you how to create a segment, build a campaign, and run a report in ten minutes.

** [Quickstart Guide](doc:quickstart-guide) **