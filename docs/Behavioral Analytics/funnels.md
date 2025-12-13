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

<Image title="Analytics_Funnels_Create.png" alt={1187} className="border" border={true} src="https://files.readme.io/505951f-Analytics_Funnels_Create.png" />

> 📘 Note
>
> You can drag and drop to re-arrange the steps in a funnel.

<Image title="Analytics_Funnels_steps_rearrange.gif" alt={920} className="border" width="smart" border={true} src="https://files.readme.io/d0dd43c-Analytics_Funnels_steps_rearrange.gif" />

## Setting Conversion Window

Funnels are calculated based on a specified conversion window (set to 5 days by default). The conversion window is the total elapsed time for the user to complete all the steps in the funnel (i.e. to convert). Shorter windows generally result in fewer users completing the funnel steps whereas larger windows result in more user converting.

<Image title="Analytics_Funnels_Conversion_window.png" alt={888} className="border" border={true} src="https://files.readme.io/c1e68ec-Analytics_Funnels_Conversion_window.png" />

## Compare by segments

You can choose to compare your conversion across different segments. For example, compare the funnel for App Launched -> Product Viewed -> Charged  across the "All Users" segment and the “Frequent Buyers" segment. The differences in the conversion trends could reveal a difference in the behavior of your users in each segment and hence result in an insight that could be invaluable. 

To compare conversion across segments:

1. Go to Analytics>Funnels.
2. Select the steps to analyze and view the conversion funnel.
3. Select the "Compare to another segment" box. Select a segment from the list or create an adhoc segment. For more information on segments, see [Segments](doc:segments) ].
4. Click View Funnel.

<Image title="Analytics_Funnels_Compare_Segments_Search.png" alt={1163} className="border" width="100%" border={true} src="https://files.readme.io/012fee4-Analytics_Funnels_Compare_Segments_Search.png" />

The results are displayed.

<Image title="Analytics_Funnels_Compare_Segments_Search_Results.png" alt={1155} className="border" width="100%" border={true} src="https://files.readme.io/eb0e3a1-Analytics_Funnels_Compare_Segments_Search_Results.png" />

## Advanced Filtering

Advanced filters allow you to restrict your analysis to a specific segment of users. Create a segment based on any combination of past behaviors in combination with any set of user properties. 

> 👍 Advanced filters is a general feature available for all analytics features and most campaigns. Read more in the [Segmentation guide](doc:segments).

# Reading Funnel Charts

Funnel charts let you quickly determine how many users progress through each of the funnel steps. 

The default view shows cumulative conversions per step for the selected time range and can be viewed as either an absolute count of users completing each step or as a percentage.

By definition all users (100%) complete the first step in any funnel. In the example below, for the first step, Product Viewed, 157,858 users complete this step. Of these users, 103,094 go on the complete the Added to Cart step with 30,704 users going on to complete the final Charged step in the funnel.

<Image title="image8.png" alt={1999} className="border" border={true} src="https://files.readme.io/ff2abce-image8.png" />

## Breakdown by property

You can quickly breakdown a funnel by profile properties for sessions or geographies or technographics or by any event property associated with any event. This allows you to quickly compare your conversion flows across product categories, geographies, devices, and more. 

To breakdown by property:

1. Click Analytics > Funnel
2. Add Funnel steps and click View Funnel
3. Select the property and its value to breakdown the funnel 

<Image title="Analytics_Funnels_breakdown_by_profile_property.png" alt={1208} width="100%" border={true} src="https://files.readme.io/3b40dbd-Analytics_Funnels_breakdown_by_profile_property.png">
  Breakdown by User Property
</Image>

<Image title="Analytics_Funnels_breakdown_by_event_property.png" alt={1179} border={true} src="https://files.readme.io/56000b3-Analytics_Funnels_breakdown_by_event_property.png">
  Breakdown by Event Property
</Image>

## Hold Property Constant

You can define conversion based on event property. This will help you determine if the conversion was done for the intended item or not. 

You expect the user to view a shirt, add this shirt to cart, and then purchase it. Here, product name is your event property and the property values are (Shirt, Dress, Trousers, Jackets).  If the user purchases anything else,  you do not wish to consider it as conversion.\
Now, the user views the shirt, adds the shirt to cart, but purchases a trouser. You still have a sale but this is not the intended analysis. If the user purchases trousers, then this must be considered as a drop-off. To do this, you can hold the event property (product name) constant and consider it a conversion only if the user purchases a shirt.

<Image title="Analytics_Funnels_hold_property.png" alt={1174} className="border" border={true} src="https://files.readme.io/cc17fa1-Analytics_Funnels_hold_property.png" />

> 📘 Property Considerations
>
> * Only the top 20 event properties are considered. 
> * You can breakdown a funnel by an event property and also hold this event property as constant. However, it must be the same event property in this case. 
> * Creating a campaign or segment is not supported for this funnel type. 

## Conversions over Time

For each funnel, CleverTap calculates and trends the time it takes for users to progress from one step to another and shows these trends in both a cumulative and absolute graph. 

Conversion time helps you understand how long it takes the majority of your users to progress between steps in your funnel. This in turn can be used as a basis for sending engagement [campaigns](doc:intro-to-campaigns) timed to reach users who DO NOT convert within the time the majority of your users convert. 

Depending the nature of the app and conversion flow, users may progress through funnel steps measured in hours or minutes or measured in days, weeks, or even months.

For a funnel where users progress between steps rapidly, set the Conversion Time to an appropriate time (8 hours or less for example) to see the specific time when the majority of users convert. In the example below, Conversion Time is set to 1 hour. From the graph we see that 80% of users progress through the funnel within 14 minutes.

<Image title="image5.png" alt={1999} className="border" border={true} src="https://files.readme.io/c7cf6b2-image5.png" />

The absolute trend graph shows you the spike in conversions within the first minute where 44% of users convert.

<Image title="image6.png" alt={1999} className="border" border={true} src="https://files.readme.io/296c6e0-image6.png" />

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

# Table View

You can also view the funnel information in a table. 

<Image title="Analytics_Funnels_Table_view.png" alt={1186} className="border" width="100%" border={true} src="https://files.readme.io/80345c6-Analytics_Funnels_Table_view.png" />

Every categorization (split by user or event property) in the funnel is a row in the table. You will see the following information in each row:

* Overall % conversion (first step to last step) 
* Conversion % from one step to the next
* Median time for conversion to the next step

# Frequency Chart

The Frequency Chart displays the frequency of a user action from the current step to the next. For example, the number of times a user viewed a shirt before purchasing it. You can select the funnel step as follows:

1. App Launched
2. Product Viewed
3. Charged

The funnel appears. 

<Image title="Analytics_Funnels_Frequency.png" alt={1201} className="border" border={true} src="https://files.readme.io/4b27769-Analytics_Funnels_Frequency.png" />

Click the Frequency tab. Select the step for your analysis, Product viewed in our example. It will show you the frequency of users that viewed the product before purchasing it. We see in the example, that  19.63 % of the users viewed the product 2 times before finally making a purchase. So the insight maybe that marketing effort needs to be towards reducing the number of product views or maybe the user needs more information in the first product view before making a purchase. 

> 📘 Frequency Chart Considerations
>
> * Frequency chart is available only from the second funnel step.
> * Creating a campaign or segment is not supported for this funnel type. 

# Bookmarks

You can bookmark any funnel, cohort, or event query and save it to quickly retrieve later. Bookmarks are specific to each logged in user. No other dashboard users will see the bookmarks you save. 

Bookmarks are convenient for recalling a specific analysis that you want to see frequently. For example, you can bookmark you important conversion funnels and view them each day or week to see how they are changing over time.

# Actionable Funnels

After you build a funnel, you can use the Actionable Funnels feature to save a segment of users from the funnel or create a campaign targeting that segment. 

### Example

You can create a segment for either users that did or did not complete an event at a specific stage of a funnel.

For example, let's create a new funnel that measures the progression of users who launch your app, add an item to their cart, and then purchase an item. 

Let's create a segment for just the users who launched your app, added an item to their cart, but then did not purchase an item. We can do this by clicking the gray area in the third bar, which represents the users who dropped off and did not complete the charged event.

<Image title="actionable-funnel-1.png" alt={1111} border={true} src="https://files.readme.io/6e87501-actionable-funnel-1.png">
  Gray dropoff area
</Image>

<Image title="actionable-funnel-2.png" alt={1110} border={true} src="https://files.readme.io/01d142e-actionable-funnel-2.png">
  Create Segment/Campaign for dropoffs
</Image>

Alternatively, instead of targeting users that dropped off in the last stage of the funnel, we can create a segment or campaign targeting that segment for users who purchased an item.

<Image title="actionable-funnels-3.png" alt={1108} border={true} src="https://files.readme.io/3013112-actionable-funnels-3.png">
  Create Segment/Campaign for converted users
</Image>
