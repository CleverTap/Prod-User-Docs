---
title: Composite Events
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
You can combine multiple events to create a composite event. You can then use this event as a single event on the dashboard and even analyze it in reports. 

For example,  the “Video played” and “Song played” events can be combined into a single event called, “Content consumed.”

In another example, you may group “Item purchased" and "Subscription created” into a new composite event called “Money spent”.


#Create a composite event

1. Go to Settings > Schema > Composite events. The composite events page appears. 
2. Click the Add composite event button. 
3. Name your event and select the events that you want to group together. In our example, we name the event as Holiday booked. 
4. Select the events and filter by properties, if required. In our example, we filter the Hotel booked event by the event property category, which is 3 stars and flight booked event by the event property Economy.  
5. You can add any additional events if required or save the new composite event. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ff9b8e-Events_Composite_Create.png",
        "Events_Composite_Create.png",
        613,
        508,
        "#f7f7f9"
      ],
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "* You can combine existing events into a new composite event. \n* This event does not add to the DRP storage limit. \n* This event adds to the global event limit.\n* You can have a maximum of 20 underlying events.",
  "title": "Considerations"
}
[/block]
#Delete composite event 
Click the ellipsis and click the delete icon to delete the composite event. 
<<sunil to add screenshot>>

#Create a composite event property

Now that you have created a composite event, you can a composite property using the properties of the underlying events. You can create a composite event property by grouping together two or more underlying event properties. After they are grouped together, they will behave as a single event property.  For example, we create an event property called Booking revenue that groups the underlying properties such as Flight booked amount (from flight booked event) and Hotel booked amount (from the hotel booked event). When you analyze the Booking revenue property, it will function as a single event property. 

You can add composite event properties from the composite events page. To add a composite event property:

1. Click Add property link for the required composite event from the list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c6d5fd2-Events_Composite_Add_Property_list.png",
        "Events_Composite_Add_Property_list.png",
        1179,
        647,
        "#f6f7f7"
      ]
    }
  ]
}
[/block]
2. Click the Property button on the top and select Add composite property.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ec7b45-Events_Composite_Add_Property_compsite_and_single.png",
        "Events_Composite_Add_Property_compsite_and_single.png",
        1178,
        364,
        "#f6f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
3. Select the properties to be added from the underlying events.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5837078-Events_Composite_Add_composite_properties.png",
        "Events_Composite_Add_composite_properties.png",
        593,
        404,
        "#f6f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
4. Click Save. 

You can now start using this composite property instead of two separate underlying properties. 

<<SUNIL to add a screenshot of a trend for booking event property >>
#Add an individual event property 

Add an individual event property for an underlying event and use it as a composite event property.

After you create a Composite event, you may not need all the underlying properties from each underlying event. You can add a property that belongs to any of the underlying events as an individual property to the Composite event. The composite event behaves as a single event and this individual property behaves as its underlying property. Therefore, you can stop referencing the underlying event just to analyze a specific property. 

For example, you wish to analyze an event called "Flight Class" from the flight booked event. You can add this event to the main composite event "Travel Bookings" and use it as if it is an underlying property of this event.  You do not need to use the "Flight Booked" event because the new composite property offers you a better view of your events. 

You can add event properties from the composite events page. To add a composite event property:

1. Click Add property link for the required composite event from the list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/73bae29-Events_Composite_Create.png",
        "Events_Composite_Create.png",
        613,
        508,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
2. Click the Property button on the top and select Add property.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4607f7d-Events_Composite_Add_Property_Single.png",
        "Events_Composite_Add_Property_Single.png",
        1180,
        346,
        "#f5f8f9"
      ],
      "border": true,
      "sizing": "smart"
    }
  ]
}
[/block]
3. Select the property to be added from the underlying event.  <<SUNIL to change this image>>
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe549ac-Events_Composite_Create_single_property.png",
        "Events_Composite_Create_single_property.png",
        615,
        510,
        "#f7f7fa"
      ],
      "border": true,
      "sizing": "smart"
    }
  ]
}
[/block]
4. Click Save. 

You have now clubbed the underlying properties together. 


#Dashboard availability 
I will give you. Need to look at user stories.

<<Shruti to provide>>

# Exceptions
I will give you. Need to look at user stories.

<<Shruti to provide>>