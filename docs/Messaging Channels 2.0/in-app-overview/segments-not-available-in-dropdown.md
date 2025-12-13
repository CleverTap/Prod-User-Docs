---
title: Segments Not Available in Dropdown
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
## Overview

The selection of different segments such as Custom list segment and Past Behaviour segments is not available in the in-app notification campaigns because In-app is a live triggering action campaign which requires the user to do the qualifying event at the present time to enter into the campaign and receive the in-app notification. 

Easter Egg : This can be solved via Journeys. By using the entry for the engagement node as the required segment

![1648](https://files.readme.io/ec8ee47-1_Journeys.png "1 Journeys.png")

![1610](https://files.readme.io/7f60601-2_Journeys.png "2 Journeys.png")

# Use Case

Send in app notification when the user launches the app starting there are new arrivals. Navigation button can consist of a deep link to the page of the new arrivals.

![900](https://files.readme.io/568e1bf-3_Use_case.png "3 Use case.png")

# FAQs

## Why does In-app not work on API events?

The In-app should be triggered only on the SDK events. In-apps require the user to be present on the application, hence the in-app campaigns would not work on an event which is triggered via API. Additionally, events from API may not be in real-time and hence the trigger will not work.

## Can there be multiple in-app campaigns running on the same triggering event?  

 There should not be more than 1 in-app campaign on the same triggering event, as it creates a race condition between the campaigns and then any random campaign will be sent to the user.

## Is it possible to send a GIF in an in-app message?

We do support GIF within the interstitial in-apps for users whose CleverTap SDK version is above 3.3.0 and you can send the Gif's in the In-App campaigns by writing a custom HTML as well.\
Please refer to the below document for aspect Ratio and Image Size Guide.\
[https://docs.clevertap.com/docs/inapp-campaigns#section-template-aspect-ratio-and-image-size-guide](https://docs.clevertap.com/docs/inapp-campaigns#section-template-aspect-ratio-and-image-size-guide)

## What are the text and image specifications for in-app campaigns in each template?

Text limit:\
Selected template - Header: Title [22 Characters], Message [75 Characters]\
Selected template - Half Interstitial: Title [25 Characters], Message [100 Characters]\
Selected template - Interstitial: Title [20 Characters], Message [75 Characters]\
Selected template - Header: Title [30 Characters], Message [128 Characters]\
Selected template - Header: Title [22 Characters], Message [75 Characters]

Image specifications: [https://docs.clevertap.com/docs/inapp-campaigns#section-template-aspect-ratio-and-image-size-guide](https://docs.clevertap.com/docs/inapp-campaigns#section-template-aspect-ratio-and-image-size-guide)
