---
title: Funnels
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
Funnels show you how users progress through defined paths in your app, and pinpoint where they drop-off between steps. Funnels are defined as a series of events that a user performs in a particular order.

Common examples include a user onboarding flow (where a user progresses from the initial launching of the app through such activities as registration, profile completion and orientation), or a purchase flow (where a user progresses through a shopping cart experience through to a purchase event).

# Creating a Funnel

To create a funnel, select the desired events in the desired order. You can create up to an 8-step funnel. Select desired event properties for each event to further constrain the analysis to just those users who performed that event/property combination.

<Image title="Funnel OR.png" alt={1343} className="border" border={true} src="https://files.readme.io/f9cd9b0-Funnel_OR.png" />

## Setting Conversion Window

Funnels are calculated based on a specified conversion window (set to 5 days by default). The conversion window is the total elapsed time for the user to complete all the steps in the funnel (i.e. to convert). Shorter windows generally result in fewer users completing the funnel steps whereas larger windows result in more user converting.

<Image title="image2.png" alt={1546} className="border" border={true} src="https://files.readme.io/08ea7eb-image2.png" />

## Advanced Filtering

Advanced filters allow you to restrict your analysis to a specific segment of users. Create a segment based on any combination of past behaviors in combination with any set of user properties. 

> 👍 Advanced filters is a general feature available for all analytics features and most campaigns. Read more in the [Segmentation guide](doc:segments).

# Reading Funnel Charts

Funnel charts let you quickly determine how many users progress through each of the funnel steps. 

The default view shows cumulative conversions per step for the selected time range and can be viewed as either an absolute count of users completing each step or as a percentage.

By definition all users (100%) complete the first step in any funnel. In the example below, for the first step, Product Viewed, 157,858 users complete this step. Of these users, 103,094 go on the complete the Added to Cart step with 30,704 users going on to complete the final Charged step in the funnel.

<Image title="image8.png" alt={1999} className="border" border={true} src="https://files.readme.io/ff2abce-image8.png" />

## Conversions over Time

For each funnel, CleverTap calculates and trends the time it takes for users to progress from one step to another and shows these trends in both a cumulative and absolute graph. 

Conversion time helps you understand how long it takes the majority of your users to progress between steps in your funnel. This in turn can be used as a basis for sending engagement [campaigns](doc:intro-to-campaigns) timed to reach users who DO NOT convert within the time the majority of your users convert. 

Depending the nature of the app and conversion flow, users may progress through funnel steps measured in hours or minutes or measured in days, weeks, or even months.

For a funnel where users progress between steps rapidly, set the Conversion Time to an appropriate time (8 hours or less for example) to see the specific time when the majority of users convert. In the example below, Conversion Time is set to 1 hour. From the graph we see that 80% of users progress through the funnel within 14 minutes.

<Image title="image5.png" alt={1999} className="border" border={true} src="https://files.readme.io/c7cf6b2-image5.png" />

The absolute trend graph shows you the spike in conversions within the first minute where 44% of users convert.

<Image title="image6.png" alt={1999} className="border" border={true} src="https://files.readme.io/296c6e0-image6.png" />

# Funnel Comparisons

You can quickly split a funnel by any event property associated with the event of the first step of the funnel, or by profile properties for sessions or geographies or technographics. This allows you to quickly compare your conversion flows across product categories, geographies, devices, and more.

![1999](https://files.readme.io/7e0045e-image4.png "image4.png")

## Daily Trend View

In the Daily Trend view, completion of each step is calculated for each day in the selected time range and trended. The Daily Trend view lets you pinpoint spikes in conversions on a particular day as well as to see if conversions are trending up or down over time. Trends can be viewed as either an absolute count of users or a percentage.

Note that in the Daily Trend view, on any particular day, the users converting for each step are independent of one another. For example, on September 4th, 59,474 users complete the Product Viewed Step and 47,794 users completed the Added to Cart step. 

Keep in mind that the users that complete Added to Cart on Sept 4th are not necessarily a subset of the users that completed the Product Viewed step on that day. Some of these users who completed Added to Cart on September 4th may have completed the Product Viewed step the prior day, week, etc.

<Image title="image1.png" alt={1999} className="border" border={true} src="https://files.readme.io/80237b3-image1.png" />

# Funnel Computation Methods

## Default Method

By default funnels will count all users who perform all the specified steps, in order, regardless of whether they “loop-back” to an earlier step or move forward to a later step in the funnel. 

For example, say our funnel steps are defined as:  

* Funnel Steps: Step A → Step B → Step C → Step D. 

Let’s analyze whether different users are counted as converting depending on the order in which each progress through the funnel steps.

* User 1: Step A → Step B → Step C → Step D
* User 2: Step A  → Step C → Step D
* User 3: Step A → Step C → Step B → Step D
* User 4:  Step A → Step B → Step A → Step C → Step D

User 1 is counted since she progresses through the funnel steps in order.\
User 2 is not counted since he did not perform Step B.\
User 3 is not counted since she completed the steps out of order.\
User 4 is counted since she completed the steps in order, even though she “looped back” and performed Step A twice.

## Strict Ordering Method

By checking “Enforce Strict Order”, users will only be counted if they complete the funnel steps in exactly the specified order without performing another one of the funnel steps out of order. 

Let's consider the same example as above where the funnel steps defined are:  

* Funnel Steps: Step A → Step B → Step C → Step D. 

If we were to analyze the below users -  

* User 1: Step A → Step B → Step C → Step D
* User 2: Step A  → Step C → Step D
* User 3: Step A → Step C → Step B → Step D
* User 4:  Step A → Step B → Step A → Step C → Step D

Here only, user 1 will be counted as converting as the strict order restricts any deviation from the specified steps in the funnel. The other users ie, 2,3 & 4 are breaking the strict ordering & hence do not qualify.

<Image title="image3.png" alt={1650} className="border" border={true} src="https://files.readme.io/a850a6e-image3.png" />

# Bookmarks

You can bookmark any funnel, cohort, or event query and save it to quickly retrieve later. Bookmarks are specific to each logged in user. No other dashboard users will see the bookmarks you save. 

Bookmarks are convenient for recalling a specific analysis that you want to see frequently. For example, you can bookmark you important conversion funnels and view them each day or week to see how they are changing over time.

# Actionable Funnels

After you build a funnel, you can use the Actionable Funnels feature to save a segment of users from the funnel or create a campaign targeting that segment. 

### Example

You can create a segment for either users that did or did not complete an event at a specific stage of a funnel.

For example, let's create a new funnel that measures the progression of users who launch your app, add an item to their cart, and then purchase an item. 

Let's create a segment for just the users who launched your app, added an item to their cart, but then did not purchase an item. We can do this by clicking the gray area in the third bar, which represents the users who dropped off and did not complete the charged event.

<Image title="actionable-funnel-1.png" alt={1111} className="border" border={true} src="https://files.readme.io/6e87501-actionable-funnel-1.png" />

<Image title="actionable-funnel-2.png" alt={1110} className="border" border={true} src="https://files.readme.io/01d142e-actionable-funnel-2.png" />

Alternatively, instead of targeting users that dropped off in the last stage of the funnel, we can create a segment or campaign targeting that segment for users who purchased an item.

<Image title="actionable-funnels-3.png" alt={1108} className="border" border={true} src="https://files.readme.io/3013112-actionable-funnels-3.png" />
