---
title: Flows
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
[block:callout]
{
  "type": "info",
  "title": "",
  "body": "**Flows** is a part of CleverTap's Discovery Platform and is available for Enterprise accounts"
}
[/block]
# Overview

Flows let you understand all the ways a user navigates through your app. This gives you a broad view of the common paths users take as well as where they get stuck. 

Flows provides you with two modes of analysis :
  * Event Flow: What users did *before* or *after* performing an event
  * Content Flow: What users did *before* or *after* consuming a specific content, product, page, etc.

With Flows you will be able to isolate virtually any user journey beginning, ending, or including specific events completed within a defined conversion timeframe. You can also filter flows by any specific segment of users.

# Event flow setup

To use Events Flow, go to the Analyze tab in the CleverTap Dashboard, select Flows → Event Flows
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2325466-Flows_1.png",
        "Flows 1.png",
        1440,
        539,
        "#dedfe5"
      ],
      "border": true
    }
  ]
}
[/block]
## Analyze Users Actions Before or After an Event

The most common type of analysis is to look at all the different paths users take after they launch your application. However, you can select any event as the starting point of a user Flow. 
[block:callout]
{
  "type": "success",
  "body": "if you wanted insight into what your users did in your app after receiving one of your marketing push campaigns, you can select the CleverTap System Event, “Notification Clicked,” which gets recorded each time a users clicks on a campaign. From there, you’ll see all the events a user performed after clicking on a push notification giving you direct insights as the effectiveness of your marketing activities.",
  "title": "Example: Analyze Marketing Effectiveness"
}
[/block]

[block:callout]
{
  "type": "success",
  "title": "Example: Analyze reasons for Uninstalls",
  "body": "You can analyze what events users perform before they Uninstall your app. This could give you insights like spam campaigns or a specific page view leads to uninstall"
}
[/block]
## Building the Event Flow

### Step 1: Pick Start of Flow
  * Here, you can pick upto 3 events as the start of the flow. 
  * This will allow you to analyze what users did 'after' or 'before' the events you picked

### Step 2: Pick Events to analyze
  * Here, you can pick upto 16 events to be a part of the flow
  * This allows you to pick all events that you want to analyze as a part of the Flow you are building
  ** You can also choose to split an event by its property
  ** For an event split by property, you will be able to view up to 50 properties of the event in the flow
  ** Example: If you are analyzing a conversion flow where 'Product Viewed' is split by property 'category', you will be able to analyze which category of product are your users viewing before converting vs which category your users view after dropping off 

### Step 3: Optional end of flow
  * Here, you can pick up to 3 events to end the flow with
  * This will allow you to end the flow when the said event(s) occur

### Step 4: Look ahead/back window
  * Here, you can pick the time window that do you want your flows analyzed
  * The analysis will contain only users who completed the set of events within that window
  * Shorter conversion times reduces the number of users who will be included in the output

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac86285-screencapture-eu1-dashboard-staging-4-dashboard-clevertap-ZWW-WWW-WWRZ-flows-html-2018-12-26-23_36_09.png",
        "screencapture-eu1-dashboard-staging-4-dashboard-clevertap-ZWW-WWW-WWRZ-flows-html-2018-12-26-23_36_09.png",
        1480,
        1869,
        "#dfe0e6"
      ],
      "border": true
    }
  ]
}
[/block]
## Reading Flow Chart
The output of the flow analysis takes the form of a “sunburst” chart.

Each concentric circle in the chart represents successive steps in the user’s journey. At the center for the chart is the total number of users included in the analysis (in the below example 1.2 million users). 

Each outward “ray” in the sunburst represents a different Flow that users took. Hovering over the concentric circles will highlight and isolate a different “ray” or path through the app as well as tell you how many users this Flow represents. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac9c85d-image2.png",
        "image2.png",
        1928,
        1202,
        "#e0efec"
      ],
      "border": true
    }
  ]
}
[/block]
### Filters
**Interaction Depth** allows you to define the complexity of flows by picking the number of steps upto a maximum of 20 steps

**Collapse Repeated Steps** simplifies the visualization of Flows by collapsing any event that happens multiple times in succession into a single element of the chart. For example, if a user were to perform the same event in rapid succession with no other activity in between (App Launch → App Launch → App Launch) rather than rendering this as 3 successive App Launch events, this option collapses these (visually) into a single instance.

**Filter events** allows you to remove events that you do not want to analyze in the flow. You can add them back by using the same filter

**Hover on step** allows you to see the percentage of users progressing from one step to the next as well as the total elapsed time it takes is conveniently displayed in a table next to the chart.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1beab10-flows2.png",
        "flows2.png",
        1236,
        642,
        "#dae1de"
      ],
      "border": true
    }
  ]
}
[/block]
# Set Up a Content Flow

To use Content Flows, go to the Analyze tab in the CleverTap Dashboard, select Flows -> Content Flows
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3154c2-Flows_1.png",
        "Flows 1.png",
        1440,
        539,
        "#dedfe5"
      ],
      "border": true
    }
  ]
}
[/block]
## Analyze Users Actions Before or After consuming a content, product or page

The most common type of 'after' analysis is to look at all the different videos the users watch after they watch a specific video
The most common type of 'before' analysis is to look at all the different products the users add to cart before they watch a specific product to cart

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3602328-Screenshot_2018-12-26_at_11.25.14_PM.png",
        "Screenshot 2018-12-26 at 11.25.14 PM.png",
        1233,
        733,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
## Content flow setup

### Step 1: Pick Start of Flow
  * Here, you can pick the event and the property value that you want to start the flow with. 
  * This will allow you to analyze what users did 'after' or 'before' the event property value you picked
  * E.g. Event 'Video Watched', Property 'video name', Value 'Star Trek episode 1'

### Step 2: Optional end of flow
  * Here, you can pick the property value you want to end the flow with
  * This will allow you to end the flow when the said value occurs in the flow
  * E.g. End the flow on the first occurrence of 'Doctor Who episode 10'

### Step 4: Look ahead/back window
  * Here, you can pick the time window that do you want your flows analyzed
  * The analysis will contain only users who completed the set of property values within that window
  * Shorter conversion times reduces the number of users who will be included in the output

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19496c9-Screenshot_2018-12-26_at_11.32.47_PM.png",
        "Screenshot 2018-12-26 at 11.32.47 PM.png",
        887,
        641,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Reading 'before' flows",
  "body": "When analyzing what a user did before an event (i.e. show me the event that happened before App Uninstall) the Flow Chart is inverted. In this case the innermost concentric circle is the last step in the user journey.\nThis inverted visualization better highlights the steps that happened immediately immediately before the last event (App Uninstall in this example). Just look at the inner concentric circles to understand the events that are in closest proximity to the ending event."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "Currently in Flows, we sample your data to ensure that results load faster, so you might see a minor difference in counts when you compare these numbers to numbers in the rest of your dashboard. \n\nThis sampling has been optimized for accuracy and your numbers will be directionally correct. Sampling kicks in if the query contains more than 100,000 events, and the sample size is 10%"
}
[/block]