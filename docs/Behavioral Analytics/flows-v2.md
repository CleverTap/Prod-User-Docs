---
title: Flows 2.0
excerpt: >-
  Understand how to use the new Flows to visualize user actions, uncover
  behavioral patterns, and optimize user journeys for better engagement and
  conversions.
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

Flows provide a powerful way to visualize and analyze user navigation within your app. By tracking user journeys, Flows help identify common pathways, drop-off points, and engagement trends. This enables data-driven decision-making to improve user experience, optimize conversion rates, and refine marketing strategies.

With Flows, you can:

* Analyze user behavior at various touchpoints.
* Identify patterns leading to conversions or drop-offs.
* Optimize user journeys to enhance retention and revenue.

Flows allow you to track specific events within a defined time frame and filter results based on user segments, ensuring tailored insights for better business decisions.

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information about this feature or any queries, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

# View Flows

Ensure you have the necessary permissions to access analytics in the CleverTap dashboard. To set up event flow, you must specify the period for analysis and the duration for which the flows must be generated. For example, an e-commerce app can analyze its users' actions after adding a Nike Shoe to the cart.

To get started with flows:

1. Navigate to the _Analytics_ tab in the CleverTap dashboard.
2. Select _Flows BETA_.

<Image align="center" alt="Event Flows" border={true} caption="Event Flows" src="https://files.readme.io/2f0fea2e7032fbc7796c0c9ba82e71fe292f5d5d6fc48f2c75557672d48480a7-image.png" />

3. Select the event, such as _Added to Cart_. You can filter it by a specific event property, such as _Nike_ shoes. The flow will show all the user paths after this event, such as the user selecting a product category, making a purchase, or simply dropping off.
4. Select the user segment. For example, users who engage with the app a minimum of 4 times in the past week.
5. (Optional) Use _Split by Property_ option to break down the flow results by an event property. Splitting helps you compare how user journeys differ across categories. For example, you can split the _Added to Cart_ event by the brand property to compare how users who add Nike, Adidas, or Puma products move through the purchase journey. Each property value appears as a separate path in the flow visualization.
6. (Optional) Use _Exclude Events_ option to remove specific events from the flow analysis. This helps simplify the flow and focus on the most relevant user actions. For example, you can exclude events such as _App Launched_ or _Notification Viewed_ if they are not meaningful for understanding the purchase journey. Excluding such events prevents them from appearing as intermediate steps in the flow.
7. Define the _Look ahead window_. The look-ahead window is the specified time period after which the subsequent events that follow the main event are recorded. For example, if the look-ahead window is set to 1 day and the selected event is the App launch, then any event after the App Launch within 1 day will be part of the Flow. For more details about the Look Ahead window, refer to the [Look Ahead Window](doc:flows-v2#look-ahead-window).
8. Specify the From and To Date from the right pane. This is the specified time period for the flow.
9. Click **View Analysis**.  The flow for the selected event appears.

# Flow Analysis

The most common type of analysis is to look at all the different paths users take after they launch your application; however, you can select any event as the starting point of a user flow.

The new Flow displays the selected event as the START of the journey. For example, you may want to know what happened after the user added an item to the cart. Here, we expand forward in time to view all the steps. The image shows that after users add an item to their cart, 26.7% view the product compared to 25% who purchase it.

<Image align="center" alt="Flow Steps" border={true} caption="Flow Steps" src="https://files.readme.io/2f0fea2e7032fbc7796c0c9ba82e71fe292f5d5d6fc48f2c75557672d48480a7-image.png" />

Another example is verifying the effectiveness of your marketing push campaigns. You can select the CleverTap system event _Notification Clicked_, which is recorded each time a user clicks on a campaign. From here, you can view all the events a user performs after clicking on a push notification, giving you direct insights into the effectiveness of your marketing activities.

Similarly, you can also analyze App Uninstalls. This will allow you to analyze the types of events users perform before they uninstall your app, giving you insights such as spam campaigns or a specific page view that leads to uninstall.

## Look Ahead Window

The Look-Ahead Window determines how subsequent user actions are visualized after a selected event. It works in combination with the defined time range and the selected event. For example, if you select a date range of 30 days, a look-ahead window of 5 days, and _App Launch_ as the event, CleverTap analyzes all user actions within 5 days. These actions are visualized as steps after each _App Launch_, before starting a new flow.

* A larger look-ahead window analyzes events over a longer period, forming a horizontally long flow path, where events appear sequentially.
* A shorter look-ahead window analyzes only immediate actions, producing a vertically long flow path, where repeated interactions are stacked.

### Example: 7-Day vs. 1-Day Look-Ahead Window

Let us compare a 7-day look-ahead window with a 30-day look-ahead window. Following are the user actions:

| Day | User | Event Flow                                  |
| --- | ---- | ------------------------------------------- |
| 1   | John | App Launched → Product Viewed → Add to Cart |
| 2   | John | App Launched → Product Viewed → Add to Cart |
| 3   | John | App Launched → Purchase                     |

On the first day, John did not buy the product. He launched the app, viewed the product (say shoes), and then added them to the cart. The next day, he launched the app again, viewed the product, and added another product to the cart (say, a shirt). On the third day, he launched the app and completed the purchase. These events are analyzed differently based on the look-ahead window. Based on the look-ahead window, the flow will look different.

#### 7-Day Look-Ahead Window (Horizontally Long)

The flow stops when the look-ahead window expires. Since the look-ahead window spans 7 days, all events within that period are linked in sequence, creating a stretched-out flow path.

| No. of App Launches Considered | Event Flow                                                                                                                  |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| 1                              | App Launched → Product Viewed → Add to Cart → Purchase→ App Launched→ Product Viewed → Add to Cart → App Launched→ Purchase |

#### 1-Day Look-Ahead Window (Vertically Stacked)

The flow stops when the look-ahead window expires. Since the look-ahead window is only 1 day, each app launch is treated separately, creating a more segmented flow for these events.

| No. of App Launches Considered | Event Flow                                                        |
| ------------------------------ | ----------------------------------------------------------------- |
| 3                              | _Step 1_ - App Launched → Product Viewed → Add to Cart → Purchase |
|                                | _Step 2_ - App Launched → Product Viewed → Add to Cart            |
|                                | _Step 3_ - App Launched → Purchase                                |

> 🚧 Flow Considerations
>
> Currently, we only calculate the top 10,000 flows. Events beyond this limit are grouped under _Others_.

## Bookmark a Flow Analysis

You can bookmark any Flow analysis to quickly revisit it later. Bookmarks are user-specific; only the logged-in user can view their saved bookmarks on the CleverTap dashboard.

Bookmarks are especially useful for tracking frequently analyzed user journeys. For example, if you regularly analyze the flow starting from _App Launch_ with a 7-day Look-Ahead Window for high-engagement users, bookmarking it saves time and ensures consistency in analysis.

To bookmark a Flow, perform the following steps

1. Click **Bookmark** in the top-right corner of the dashboard after generating the Flow analysis.
2. Enter a descriptive name to help you easily identify the analysis later.
3. Click **Save**.

You can save up to 50 bookmarks.

> 📘 Note
>
> Bookmarked Flows are accessible only to the user who created them. You can access all your saved bookmarks from the bookmark list under the _Flows_ section.

# FAQ

### What is the longest time period I can use in a Flow?

You can select up to 60 days to be shown in a Flow

### How do I decide the Look-Ahead Window for my app?

The Look-Ahead Window depends on the type of user interactions. Examples:

* A subscription-based app might require a 30-day look-ahead window to track renewal behavior.
* A ride-hailing app might only need a 1-minute look-ahead window to analyze immediate actions such as booking and ride completion.

### Can the Look Ahead Window and the Flow Time period be the same?

No, the Flow Time Period must always be greater than the Look-Ahead Window.

### What is the maximum number of steps in a flow?

CleverTap supports up to 20 steps in a flow. If a user path exceeds 20 steps, only the first 20 steps will be displayed.

### Can I compare multiple flows side by side?

Currently, flows are analyzed individually. However, you can manually compare multiple flow reports by applying the same user segments and settings across different analyses.
