---
title: Platform Features
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
DOCS NOTE: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE IS UNPUBLISHED (OR DELETED) AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES: [https://docs.clevertap.com/docs/getting-started](https://docs.clevertap.com/docs/getting-started)

## Overview

This section covers the platform features including analytics, engagement, and other core concepts.

# Features

The CleverTap platform has five main features: 

* The CleverTap dashboard provides the functionality to [segment](doc:segments) users based on their actions and profile properties, run [targeted campaigns](doc:intro-to-campaigns) to these segments, and [analyze](doc:intro-to-reports)  each campaign’s performance. 
* [SDKs](https://developer.clevertap.com/docs/clevertap-sdks) track users’ actions within mobile apps and websites. CleverTap's SDKs also provide the ability to personalize apps by giving customers access to user profile data.
* [APIs](https://developer.clevertap.com/docs/api-overview) push user profile or event data from any source to CleverTap. Our APIs also export user data from CleverTap for analysis in BI tools and enrich customer information in CRMs.
* Integrations with communication platforms such as [SendGrid](doc:sendgrid) and [Twilio](doc:twilio), attributions providers like [Branch](doc:branch) and [Tune](doc:tune), and remarketing platforms, such as [Facebook Audience Network](doc:facebook-audience-network-1).
* [Webhooks](doc:webhooks) trigger workflows in backend systems as soon as qualifying events occur.

## Analytics 

The analytics features provide the ability for marketers and growth teams to analyze user data coming from an app or a website. Businesses can gather meaningful and actional insights by understanding customers' behaviors, so whether the end goal is to acquire and grow a user base or retain existing users, the CleverTap analytics features can help achieve these goals. 

Teams are empowered with various types of data and can understand what happened in a user's lifecycle, the why, and which actions steps to take to improve their marketing strategies. 

The CleverTap dashboard includes the following analytics features:

* [Boards](https://docs.clevertap.com/docs/simple-reports)
* [Events](https://docs.clevertap.com/docs/events-analytics)
* [Funnels](https://docs.clevertap.com/docs/funnels)
* [Cohorts](https://docs.clevertap.com/docs/cohorts)
* [Trends](https://docs.clevertap.com/docs/trends)
* [Pivots](https://docs.clevertap.com/docs/pivots)
* [Flows](https://docs.clevertap.com/docs/flows)
* [Real Impact](https://docs.clevertap.com/docs/real_impact)
* [Session Analytics](https://docs.clevertap.com/docs/session-analytics)

## Engagement

The engagement features provide the ability to send timely and contextual messages to users in real-time. Whether an engagement strategy involves an entire customer case or a only a segment of users, effective engagement leads to more user acquisition and retention, and turn regular users into loyal users. 

The CleverTap dashboard includes the following engagement features:

* [Campaigns](https://docs.clevertap.com/docs/overview)
* [Journeys](https://docs.clevertap.com/docs/journeys)
* [Bulletins](https://docs.clevertap.com/docs/bulletins)
* [Conversations](https://docs.clevertap.com/docs/conversations)

# Core Concepts

Users, events, segments, campaigns, and reports are the basic building blocks for using CleverTap, so it is important to understand each of these concepts.

## Users

After [integrating the CleverTap SDK](https://developer.clevertap.com/docs), a [user profile](doc:user-profiles) is created for each person who launches the app or visits your website. The CleverTap user profile has a set of default fields, such as device and location. You can also extend the default user profile data model by adding custom fields specific to their business.

## Events

The CleverTap SDK tracks the actions users perform in your app or website, such as a user viewing a product, listening to a song, or making a purchase. [Events](doc:events) are associated with a user profile.

## Segments

CleverTap provides the ability for users to create segments which are a group of users whose actions or user profile properties match a set of criteria you have defined. Once a user has created a segment, they can target them with a campaign or create a report to analyze them. 

## Campaigns

CleverTap [campaigns](doc:intro-to-campaigns) communicate with your users at scale. CleverTap offers 16 different messaging channels to reach your users on the optimal channel and also, engage them with users in an effective manner via a geofencing feature and the [Product Experiences](https://docs.clevertap.com/docs/product-experiences) feature.

## Reports

CleverTap provides the ability to build [reports](doc:intro-to-reports) to understand the effectiveness of campaigns on your users. You can use these reports to analyze your user engagement and guide product decisions.
