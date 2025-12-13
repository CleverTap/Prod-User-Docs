---
title: Composite Events
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
## Overview

Composite events provide you the ability to combine multiple events together. A composite event can be used as a single event on the dashboard which can be analyzed in reports later.  

> 👍 Composite Events Examples
>
> Some examples include:
>
> * The *Video played* and *Song played* events can be combined into a single event called *Content consumed*.
> * You may group *Item purchased* and *Subscription created* into a new composite event called *Money spent*.

# Create a Composite Event

To create a composite event, perform the following steps:

1. Navigate to *Settings* > *Schema* > *Composite Events*. The *Composite Events* page displays. 
2. Click the **Add composite event** button. 
3. Name your event and select the events that you want to group together. In our example, we name the event as *Travel Bookings*. 
4. Select the events and filter by properties, if required. In our example, we filter the *Hotel Booked* event by the event property *Rating* which is 3 stars and flight booked event by the event property *Class* (*Economy*).  

> 📘 Additional Events
>
> You can add any additional events (if required) or save the new composite event.

<Image title="Events_Composite_Create.png" alt={619} className="border" width="80%" border={true} src="https://files.readme.io/06128bd-Events_Composite_Create.png" />

> 📘 Considerations
>
> Consider the following:
>
> * You can combine existing events into a new composite event. 
> * This event does not add to the event storage limit. 
> * This event adds to the global event limit.
> * You can have a maximum of 20 underlying events in a composite event.

# Delete a Composite Event 

To delete a composite event, perform the following steps:

1. Click the ellipsis.
2. Click the **Delete** icon to delete the composite event. 

<Image title="1 Delete composite event.png" alt={1401} className="border" border={true} src="https://files.readme.io/ee75996-1_Delete_composite_event.png" />

# Create a Composite Event Property

Now that you have created a composite event, you can create a composite property using the properties of the underlying events. You can create a composite event property by grouping together two or more underlying event properties. After they are grouped together, they behave as a single event property. 

For example, we create an event property called *Booking* revenue that groups the underlying properties such as *Flight* booked amount (from flight booked event) and *Hotel* booked amount (from the hotel booked event). When you analyze the *Booking* revenue property, it will function as a single event property. 

You can add composite event properties from the *Composite Events* page. 

To add a composite event property, perform the following steps:

1. Click the **Add property** link for the required composite event from the list. 

![1401](https://files.readme.io/21d4852-2_Add_property.png "2 Add property.png")

2. Click the **Property** button and select *Add composite property*.

<Image title="Events_Composite_Add_Property_compsite_and_single.png" alt={1178} className="border" border={true} src="https://files.readme.io/2ec7b45-Events_Composite_Add_Property_compsite_and_single.png" />

3. Select the properties to be added from the underlying events.

<Image title="Events_Composite_Add_composite_properties.png" alt={593} className="border" border={true} src="https://files.readme.io/5837078-Events_Composite_Add_composite_properties.png" />

4. Click **Save**. 

You can now start using this composite property instead of two separate underlying properties. For example, you can view a trend of the *Booking Revenue* property in the [Trends](https://docs.clevertap.com/v1.5/docs/trends#section-view-a-trend) report. 

<Image title="Events_Composite_Trend.png" alt={1172} className="border" border={true} src="https://files.readme.io/cfea8e2-Events_Composite_Trend.png" />

# Add an Individual Event Property 

You can choose to add any of the properties that belong to any of the underlying events as an individual property to the composite event. 

The composite event behaves as a single event and this individual property behaves as its underlying property. Therefore, you can stop referencing the underlying event just to analyze a specific property. 

For example, if you want to analyze an event called *Flight Class* from the flight booked event, you can add this event to the main composite event *Travel Bookings*, then use it as if it is an underlying property of this event. You do not need to use the Flight Booked event because the new composite property offers you a better view of your events. 

You can add event properties from the *Composite Events* page. 

To add a composite event property, perform the following steps:

1. Click the **Add property** link for the required composite event from the list. 

<Image title="Events_Composite_Create.png" alt={613} className="border" border={true} src="https://files.readme.io/73bae29-Events_Composite_Create.png" />

2. Click the **Property** button on the top and select *Add property*.

<Image title="Events_Composite_Add_Property_Single.png" alt={1180} className="border" width="smart" border={true} src="https://files.readme.io/4607f7d-Events_Composite_Add_Property_Single.png" />

3. Select the property to be added from the underlying event.  

<Image title="Events_Composite_Add_single_property.png" alt={517} className="border" width="smart" border={true} src="https://files.readme.io/eba39db-Events_Composite_Add_single_property.png" />

4. Click **Save**. 

You have now grouped the underlying properties together. 

> 🚧 Composite Events Limitations
>
> Composite events are available but cannot be split by their event properties in pivots, trends, and funnels . Composite events are not available for flows, trigger events in campaigns, mapped events in catalogs, recommendations, and bulletins.
