---
title: Journeys Clone
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
Timely and relevant communication is a great way to build meaningful relationships with your users and provide a great experience across the customer lifecycle. CleverTap Journeys is a visual campaign builder that allows you to engage your customers across various devices and channels. After you set up Journeys, the user will get automatic communication and suggestions at the most favorable times and you can see and measure the considerable boost in your conversions. 

You can create user journeys that start from qualifying users to engage them using various channels and conclude with the users performing the desired action. You can drag and drop elements to create a Journey. A Journey starts with a user segment and ends with a target. 

# Overview

Journeys are ideal for engaging users across the lifecycle of your app and provide them with a great experience. 

To list a few sample use cases:

* Build User Onboarding Journeys that engage users over several days or weeks and on different channels as you educate them about your service.
* Build Promotional Journeys to entice your users to transact at different points of time.
* Long-running re-engagement campaigns to pull users back to your app if they begin to slip away.

You can create a single journey or multiple journeys to create the best experience for your users. For example, when users install your app for the first time, you can:

* Build User Onboarding Journeys that engage the users over several days or weeks using various channels such as Push, SMS, Web, and so on. You encourage them to use and explore your app and become power users.
* When they are comfortable with using your app, you build Promotional Journeys to entice your users to transact at different points of time and start generating revenue. 
* If you notice that some of the users are starting to slip away then you run re-engagement campaigns to pull users back to the app.

# Concepts

You will need to know some key terms to understand the Journey stats.

* **Node:** Segment Node, Engagement Node, Operator Node **TBD**
* **Goal:**  **TBD**
* **Entry:** All users who have entered the Journey (first node).
* **Goal Met:** If a goal is set in the Journey builder, these are all users who met the goal. 
* **Journey Timeout:** If a Journey timeout is set in the Journey builder (entry criteria), these are all the users who timed out.
* **Node Timeout:**  This is the time duration set for the node, after which the users will move on to the next node via Node timeout connector.
* **Completed:** If a goal is not set in the Journey builder, these are all the users who successfully reached the last node of the Journey.

> 👍
>
> Journeys are only available to customers who are on the [Essentials plan](https://clevertap.com/pricing/).

# Advanced Topics

## Past Behavior Segments & Journey Qualification

* If your entry criteria is a Past Behavior segment, users will be qualified for your journey at the start time specified.
* If you have added a Past Behavior segment along your journey that segment will be evaluated once a day at 12:00 am (in the timezone of your account).
* If you have added a Past Behavior segment as a goal that segment will be evaluated once a day at 12:00 am (in the timezone of your account).
