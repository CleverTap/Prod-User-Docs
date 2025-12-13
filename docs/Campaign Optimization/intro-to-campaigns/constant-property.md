---
title: Constant Event Property
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
A *Constant Property* is an event property that can be tracked across multiple events. Qualification is done if the two (or multiple events) are done with the same value of the event property held constant. 
A user is qualified if the events that are performed have a constant event property.  If there is no common property across events, then you can map different properties by using a common alias. The following examples demonstrate scenarios where you intend to nudge the users who drop-off or send a summary of products.

##Usage Scenarios

Consider an e-commerce app. You want to send personalized notifications to all customers that add an item to cart but do not purchase it. For example, user A adds a pair of red shoes to cart, while user B adds a yellow jacket to the cart. These users do not make any purchases. The Jenny red rhoes and Yellow Jacket are the values of the event property, say  Product Name.

In this example, one must create two separate campaigns for each value (Jenny red shoes and Puma yellow jacket) of the Product Name event property. Now imagine creating a campaign for each event performed by the user. 

A product catalog can have hundreds or even thousands of items.  Creating and monitoring campaigns for thousands of items for multiple events is impossible. However, you can achieve this using the constant event property in a single campaign. 

Following is a sample engagement message for user A:
Hello A
You have added **Jenny red shoes** to your cart. How about a discount code SA23jk to help you save more?

Following is a sample engagement message for user B from the same campaign:
Hello B
You have added  **Puma yellow jacket** to your cart. How about a discount code SA23jk to help you save more?

## Send a Summary

You can also send a summary of events for each product to the user. An OTT app may want to send a summary of all the videos that the users have started watching during the past week. They can nudge the users to continue watching these videos over the weekend. 

The following are some sample engagement messages for OTT users. John started watching but did not complete these shows - *Funny Cats*, *Dogs eat makeup* and *Fast Cars*. Mary started watching but did not complete the following shows - *Fury in Fur *and *Forest travels*. You can send out a notification that says something like the following:

[block:code]
{
  "codes": [
    {
      "code": "Hello John!\n\nThe weekend is here! How about you finish watching these episodes from the past week?\n\n  * Funny Cats \n  * Dogs eat makeup \n  * Fast cars",
      "language": "text",
      "name": "Message for John"
    },
    {
      "code": "Hello Mary!\n\nThe weekend is here! How about you finish watching these episodes from the past week?\n\n  * Fury in Fur\n  * Forest travels \n",
      "language": "text",
      "name": "Message for Mary"
    }
  ]
}
[/block]
#Hold event property constant

You can hold a property constant in an inaction campaign or a one-time campaign. The Constant Event Property is currently supported for Push, Email, SMS, and Webhook campaigns.

##Alias event property 

You can hold a current common property across events as a Constant Event Property. However, there may be cases where the same event property is called by different names for different events. In this case, you can create an alias event that will hold all the properties from different events.  This Alias event can then be used across campaigns and analytics. 

For example, the event *Purchased* has an event property that holds the price of the item called *price*. However, the event *Added to cart *has an event property called *selling price* that holds the same value. You can create an* Alias Event property* called *Product price* that holds the event property *selling price* and *price*. 
This message can be achieved by holding an event property constant across [ Past Behavior Segments](doc:create-past-behavior-segments-1).


1. Navigate to *Settings* > *Events* > *Alias event property.*
2. Click the **+Alias Event Property** button. The *Create Alias Event Property* window displays:
3. Enter the name for the *Alias event property*.  
4. Click the **+ Event property** link to map current events and their properties to the new alias.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9115d0e-Constant_Alias_create.png",
        "Constant_Alias_create.png",
        1195,
        702,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]
You can now use this *Alias event property* in all campaigns. 

##Inaction Campaign

You want to engage all the users who dropped off after adding a product to cart. The event property across these events is *Product Name*. The value of this event property can be anything from Jenny red shoes, running shoes, a Puma yellow jacket, a baseball bat, and so on.

Create a campaign. You can define the conditions for the target audience and then select the constant event property.
Follow the steps to create a campaign. 
1. Click the **+Campaign **button from the Campaigns dashboard.  
2. Select the *channel*.  
3. Select the *Campaign type*, that is, live segment campaign. 
4. Select the *Constant event property*, that is, Product Name.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58c94af-Constant_property_Campaign_who_Live_Inaction.png",
        "Constant_property_Campaign_who_Live_Inaction.png",
        1074,
        1156,
        "#f9f9fa"
      ],
      "border": true,
      "sizing": "80",
      "caption": "PBS Segment"
    }
  ]
}
[/block]
5. Click **Continue** and personalize message using [Liquid Tags](doc:liquid-tags) ]. 

For example, you can send the campaign with the item name that the user who added an item to the cart but did not purchase.
[block:code]
{
  "codes": [
    {
      "code": "Hurrah.. ! \nComplete your purchase of {{ ConstantEventProperty | default:\"this item\" }} with 15% off on using code GRT572E.",
      "language": "liquid"
    }
  ]
}
[/block]
Following is a sample message that is received by your user:
[block:code]
{
  "codes": [
    {
      "code": "Hurrah.. ! \nComplete your purchase of Jenny red shoes with 15% off on using code GRT572E.",
      "language": "text"
    }
  ]
}
[/block]
We hold the property such as *Products* across all the events. The *Product property *value can be anything, such as Jenny red shoes, Cool Ice blue goggles, or George High white hat. The Constant Event Property holds the value of the product.  


##One time campaigns (using Past Behavior Segments)

Let's take the earlier [OTT example](https://docs.clevertap.com/docs/constant-property#section-sending-a-summary).

Create a campaign. You can define the conditions for the target audience and then select the constant event property.
Follow the steps to create a campaign. 
1. Click the +Campaign button from the Campaigns dashboard.  
2. Select the channel.  
3. Select the Campaign type, that is, past behavior (PBS).
4. Select the Constant event property that displays the show name, that is Product Name

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47ef857-Constant_property_Campaign_who_PBS.png",
        "Constant_property_Campaign_who_PBS.png",
        1046,
        1932,
        "#fafaf9"
      ],
      "border": true,
      "sizing": "80",
      "caption": "PBS Segment"
    }
  ]
}
[/block]
5. Click Continue and personalize message using [Liquid Tags](doc:liquid-tags) ]. For example, you can send the campaign with a list of shows that the user is still watching.
[block:code]
{
  "codes": [
    {
      "code": "Hello {{ Profile.name | default:\"there\" }}\n\nThe weekend is here! How about you finish watching these episodes from the past week?\n\n{% for index in ConstantEventProperty %}\n\n{{ index | default:\"Failed\" }}\n\n{% endfor %}",
      "language": "liquid"
    }
  ]
}
[/block]
Following is a sample message that is received by your user:
[block:code]
{
  "codes": [
    {
      "code": "Hello John\n\nThe weekend is here! How about you finish watching these episodes from the past week?\n\n  * Funny Cats \n  * Dogs eat makeup \n  * Fast cars",
      "language": "text"
    }
  ]
}
[/block]
You can additionally use 'limit' in the For loop above to define the upper limit of the number of items in your message. For example, if you do not want the number of shows to be more than three, you can use the following:
[block:code]
{
  "codes": [
    {
      "code": "{% for index in ConstantEventProperty limit:3 %}",
      "language": "liquid",
      "name": "Limit"
    }
  ]
}
[/block]
This will restrict the maximum number of values in constant event property per user to 3. For users having lesser values, say 2, they will get the message with only 2 show names. To know more about limits, see [Limit in Liquid Tags](doc:https://docs.clevertap.com/docs/liquid-tags#section-limit). By default, the limit is 5 (even if `limit` tag is not used)

You can also refer to a value at a particular order by referencing the index of that value in the array. For example, a user added to cart but did not purchase Red shoes, yellow jacket, and Blue T-shirt. You can target users for specifically the second item from the bottom that they added to cart. It can be achieved using the following script. The last item is index 0, second last index 1, and so on.
[block:code]
{
  "codes": [
    {
      "code": "Second last item - {{ ConstantEventProperty[1] | default:\"index default\" }}",
      "language": "liquid",
      "name": "Specific item in the list"
    }
  ]
}
[/block]
#Conversion Event

The conversion event helps you to track conversion. To track revenue, set the user conversion event from the campaign setup. 

  * Mapping constant property with conversion event property allows you to view conversion rate for specific property values
  * You can view metrics for any conversion event and track conversion rate when any item is purchased OR track the conversion rate for a specific item that is added to cart.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/378af2e-Constant_property_conversion_event.png",
        "Constant_property_conversion_event.png",
        1162,
        665,
        "#f8f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
#Stats

Open the campaign and click the Constant Property stats tab to view the campaign reports. The campaign report comprises the following:

  * Event count for each value of the constant event property (Top 10 or Bottom 10)
  * User count for each value of the constant event property for notification sent, viewed, clicked, converted and in control group

You can change the conversion event and map the conversion event's property to the constant event property and also track conversion for the same value of event property. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75de59b-Constant_property_PBS_Stats.png",
        "Constant_property_PBS_Stats.png",
        1134,
        1130,
        "#f5f2f4"
      ],
      "border": true
    }
  ]
}
[/block]
#Advanced - Constant Property with Catalog Personalization

You can combine [Catalog Personalization](doc:catalog-personalization) ] with Constant event property to unleash the full power of campaign personalization. 

For example, you can hold an event property (Jenny Shoes) constant and also add to it the rating and cost present in a catalog via catalog personalization.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/50a187b-Constant_property_with_Catalog_Personalization.png",
        "Constant_property_with_Catalog_Personalization.png",
        809,
        486,
        "#dddbe0"
      ]
    }
  ]
}
[/block]
You must first map the constant event property to the catalog. 

1. Click personalization setup > send-time catalog

2. Select the required catalog 
3. Map the constant event property to the column. This will be used  for fetching values from the catalog
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/14eb294-Constant_property_Catalog_Personalization.png",
        "Constant_property_Catalog_Personalization.png",
        725,
        507,
        "#f6f6f8"
      ],
      "border": true
    }
  ]
}
[/block]
## One-time campaigns personalization
For one-time campaigns using Past behavior segments, you can use the following liquid script. In this example, the item is the index used for looping over the list of items for a user. *Rating* and *Amount* are the column names from which we are fetching additional values that can be used in the message. 
[block:code]
{
  "codes": [
    {
      "code": "Hello {{ Profile.name | default:\"there\" }},\n\nHere is another reason to complete purchase items added to your cart. Use Coupon FRT456P to get 15% discount on -\n{% for item in Catalog[\"Amount Catalog\"] %}\n\n {{item.Name | default: \"jhsfk\"}}, rated at {{item.Rating | default: \"3\"}}-star and currently priced at ${{item.Amount | default: \"79999\"}} \n\n{% endfor %}\n\nEnjoy.. !!",
      "language": "liquid",
      "name": "Constant event property with catalog personalisation"
    }
  ]
}
[/block]
The sample message an end user will receive will be like the following:
[block:code]
{
  "codes": [
    {
      "code": "Hello John,\n\nHere is another reason to complete purchase items added to your cart. Use Coupon FRT456P to get 15% discount on -\nJenny red shoes, rated at 4-star and currently priced at $129\nRocket umbrella, rated at 5-star and currently priced at $49\nCrosil watch, rated at 5-star and currently priced at $299\n\nEnjoy.. !!",
      "language": "liquid"
    }
  ]
}
[/block]

##Inaction campaigns personalization
For inaction campaigns using Past behavior segments, you can use the following liquid script to use a particular column from the selected catalog in the message. 
[block:code]
{
  "codes": [
    {
      "code": "Hurrah.. ! \nComplete your purchase of {{ ConstantEventProperty | default:\"this item\" }}, with 15% off on using code GRT572E.\n\n{{ ConstantEventProperty | default:\"this item\" }} is rated {{ Catalog[\"Amount Catalog\"].Rating | default:\"3\" }}-star and is currently priced at {{ Catalog[\"Amount Catalog\"].Amount | default:\"$99\" }}.",
      "language": "liquid"
    }
  ]
}
[/block]
The sample message an end user will receive will be something like the following:
[block:code]
{
  "codes": [
    {
      "code": "Hurrah.. ! \nComplete your purchase of Nautical White T-shirt, with 15% off on using code GRT572E.\n\nNautical White T-shirt is rated 4-star and is currently priced at $69.",
      "language": "text"
    }
  ]
}
[/block]