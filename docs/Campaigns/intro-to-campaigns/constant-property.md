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
## Overview

A *Constant Property* is an event property that can be tracked across multiple events. Qualification is done if the two (or multiple events) are done with the same value of the event property held constant.\
A user is qualified if the events that are performed have a constant event property.  If there is no common property across events, then you can map different properties by using a common alias. The following examples demonstrate scenarios where you intend to nudge the users who drop-off or send a summary of products.

## Usage Scenarios

Consider an e-commerce app. You want to send personalized notifications to all customers that add an item to cart but do not purchase it. For example, user A adds a pair of red shoes to cart, while user B adds a yellow jacket to the cart. These users do not make any purchases. The Jenny red rhoes and Yellow Jacket are the values of the event property, say  Product Name.

In this example, one must create two separate campaigns for each value (Jenny red shoes and Puma yellow jacket) of the Product Name event property. Now imagine creating a campaign for each event performed by the user. 

A product catalog can have hundreds or even thousands of items.  Creating and monitoring campaigns for thousands of items for multiple events is impossible. However, you can achieve this using the constant event property in a single campaign. 

Following is a sample engagement message for user A:\
Hello A\
You have added **Jenny red shoes** to your cart. How about a discount code SA23jk to help you save more?

Following is a sample engagement message for user B from the same campaign:\
Hello B\
You have added  **Puma yellow jacket** to your cart. How about a discount code SA23jk to help you save more?

## Send a Summary

You can also send a summary of events for each product to the user. An OTT app may want to send a summary of all the videos that the users have started watching during the past week. They can nudge the users to continue watching these videos over the weekend. 

The following are some sample engagement messages for OTT users. John started watching but did not complete these shows - *Funny Cats*, *Dogs eat makeup* and *Fast Cars*. Mary started watching but did not complete the following shows - *Fury in Fur* and *Forest travels*. You can send out a notification that says something like the following:

```text Message for John
Hello John!

The weekend is here! How about you finish watching these episodes from the past week?

  * Funny Cats 
  * Dogs eat makeup 
  * Fast cars
```
```text Message for Mary
Hello Mary!

The weekend is here! How about you finish watching these episodes from the past week?

  * Fury in Fur
  * Forest travels
```

# Hold event property constant

You can hold a property constant in an inaction campaign or a one-time campaign. The Constant Event Property is currently supported for Push, Email, SMS, and Webhook campaigns.

## Alias event property 

You can hold a current common property across events as a Constant Event Property. However, there may be cases where the same event property is called by different names for different events. In this case, you can create an alias event that will hold all the properties from different events.  This Alias event can then be used across campaigns and analytics. 

For example, the event *Purchased* has an event property that holds the price of the item called *price*. However, the event *Added to cart* has an event property called *selling price* that holds the same value. You can create an *Alias Event property* called *Product price* that holds the event property *selling price* and *price*.\
This message can be achieved by holding an event property constant across [ Past Behavior Segments](doc:create-past-behavior-segments-1).

1. Navigate to *Settings* > *Events* > *Alias event property.*
2. Click the **+Alias Event Property** button. The *Create Alias Event Property* window displays:
3. Enter the name for the *Alias event property*.  
4. Click the **+ Event property** link to map current events and their properties to the new alias.

<Image title="Constant_Alias_create.png" alt={1195} className="border" border={true} src="https://files.readme.io/9115d0e-Constant_Alias_create.png" />

You can now use this *Alias event property* in all campaigns. 

## Inaction Campaign

You want to engage all the users who dropped off after adding a product to cart. The event property across these events is *Product Name*. The value of this event property can be anything from Jenny red shoes, running shoes, a Puma yellow jacket, a baseball bat, and so on.

Create a campaign. You can define the conditions for the target audience and then select the constant event property.\
Follow the steps to create a campaign. 

1. Click the **+Campaign** button from the Campaigns dashboard.  
2. Select the *channel*.  
3. Select the *Campaign type*, that is, live segment campaign. 
4. Select the *Constant event property*, that is, Product Name.

<Image title="Constant_property_Campaign_who_Live_Inaction.png" alt={1074} width="80%" border={true} src="https://files.readme.io/58c94af-Constant_property_Campaign_who_Live_Inaction.png">
  PBS Segment
</Image>

5. Click **Continue** and personalize message using [Liquid Tags](doc:liquid-tags). 

For example, you can send the campaign with the item name that the user who added an item to the cart but did not purchase.

```liquid
Hurrah.. ! 
Complete your purchase of {{ ConstantEventProperty | default:"this item" }} with 15% off on using code GRT572E.
```

Following is a sample message that is received by your user:

```text
Hurrah.. ! 
Complete your purchase of Jenny red shoes with 15% off on using code GRT572E.
```

We hold the property such as *Products* across all the events. The *Product property* value can be anything, such as Jenny red shoes, Cool Ice blue goggles, or George High white hat. The Constant Event Property holds the value of the product.  

## One time campaigns (using Past Behavior Segments)

Let's take the earlier [OTT example](https://docs.clevertap.com/docs/constant-property#section-sending-a-summary).

Create a campaign. You can define the conditions for the target audience and then select the constant event property.\
Follow the steps to create a campaign. 

1. Click the +Campaign button from the Campaigns dashboard.  
2. Select the channel.  
3. Select the Campaign type, that is, past behavior (PBS).
4. Select the Constant event property that displays the show name, that is Product Name

<Image title="Constant_property_Campaign_who_PBS.png" alt={1046} width="80%" border={true} src="https://files.readme.io/47ef857-Constant_property_Campaign_who_PBS.png">
  PBS Segment
</Image>

5. Click Continue and personalize message using [Liquid Tags](doc:liquid-tags) ]. For example, you can send the campaign with a list of shows that the user is still watching.

```liquid
Hello {{ Profile.name | default:"there" }}

The weekend is here! How about you finish watching these episodes from the past week?

{% for index in ConstantEventProperty %}

{{ index | default:"Failed" }}

{% endfor %}
```

Following is a sample message that is received by your user:

```text
Hello John

The weekend is here! How about you finish watching these episodes from the past week?

  * Funny Cats 
  * Dogs eat makeup 
  * Fast cars
```

You can additionally use 'limit' in the For loop above to define the upper limit of the number of items in your message. For example, if you do not want the number of shows to be more than three, you can use the following:

```liquid Limit
{% for index in ConstantEventProperty limit:3 %}
```

This will restrict the maximum number of values in constant event property per user to 3. For users having lesser values, say 2, they will get the message with only 2 show names. To know more about limits, see [Limit in Liquid Tags](doc:https://docs.clevertap.com/docs/liquid-tags#section-limit). By default, the limit is 5 (even if `limit` tag is not used)

You can also refer to a value at a particular order by referencing the index of that value in the array. For example, a user added to cart but did not purchase Red shoes, yellow jacket, and Blue T-shirt. You can target users for specifically the second item from the bottom that they added to cart. It can be achieved using the following script. The last item is index 0, second last index 1, and so on.

```liquid Specific item in the list
Second last item - {{ ConstantEventProperty[1] | default:"index default" }}
```

# Conversion Event

The conversion event helps you to track conversion. To track revenue, set the user conversion event from the campaign setup. 

* Mapping constant property with conversion event property allows you to view conversion rate for specific property values
* You can view metrics for any conversion event and track conversion rate when any item is purchased OR track the conversion rate for a specific item that is added to cart.

<Image title="Constant_property_conversion_event.png" alt={1162} className="border" border={true} src="https://files.readme.io/378af2e-Constant_property_conversion_event.png" />

# Stats

Open the campaign and click the Constant Property stats tab to view the campaign reports. The campaign report comprises the following:

* Event count for each value of the constant event property (Top 10 or Bottom 10)
* User count for each value of the constant event property for notification sent, viewed, clicked, converted and in control group

You can change the conversion event and map the conversion event's property to the constant event property and also track conversion for the same value of event property. 

<Image title="Constant_property_PBS_Stats.png" alt={1134} className="border" border={true} src="https://files.readme.io/75de59b-Constant_property_PBS_Stats.png" />

# Advanced - Constant Property with Catalog Personalization

You can combine [Catalog Personalization](doc:catalog-personalization) ] with Constant event property to unleash the full power of campaign personalization. 

For example, you can hold an event property (Jenny Shoes) constant and also add to it the rating and cost present in a catalog via catalog personalization.

![809](https://files.readme.io/50a187b-Constant_property_with_Catalog_Personalization.png "Constant_property_with_Catalog_Personalization.png")

You must first map the constant event property to the catalog. 

1. Click personalization setup > send-time catalog

2. Select the required catalog 

3. Map the constant event property to the column. This will be used  for fetching values from the catalog

<Image title="Constant_property_Catalog_Personalization.png" alt={725} className="border" border={true} src="https://files.readme.io/14eb294-Constant_property_Catalog_Personalization.png" />

## One-time campaigns personalization

For one-time campaigns using Past behavior segments, you can use the following liquid script. In this example, the item is the index used for looping over the list of items for a user. *Rating* and *Amount* are the column names from which we are fetching additional values that can be used in the message. 

```liquid Constant event property with catalog personalisation
Hello {{ Profile.name | default:"there" }},

Here is another reason to complete purchase items added to your cart. Use Coupon FRT456P to get 15% discount on -
{% for item in Catalog["Amount Catalog"] %}

 {{item.Name | default: "jhsfk"}}, rated at {{item.Rating | default: "3"}}-star and currently priced at ${{item.Amount | default: "79999"}} 

{% endfor %}

Enjoy.. !!
```

The sample message an end user will receive will be like the following:

```liquid
Hello John,

Here is another reason to complete purchase items added to your cart. Use Coupon FRT456P to get 15% discount on -
Jenny red shoes, rated at 4-star and currently priced at $129
Rocket umbrella, rated at 5-star and currently priced at $49
Crosil watch, rated at 5-star and currently priced at $299

Enjoy.. !!
```

## Inaction campaigns personalization

For inaction campaigns using Past behavior segments, you can use the following liquid script to use a particular column from the selected catalog in the message. 

```liquid
Hurrah.. ! 
Complete your purchase of {{ ConstantEventProperty | default:"this item" }}, with 15% off on using code GRT572E.

{{ ConstantEventProperty | default:"this item" }} is rated {{ Catalog["Amount Catalog"].Rating | default:"3" }}-star and is currently priced at {{ Catalog["Amount Catalog"].Amount | default:"$99" }}.
```

The sample message an end user will receive will be something like the following:

```text
Hurrah.. ! 
Complete your purchase of Nautical White T-shirt, with 15% off on using code GRT572E.

Nautical White T-shirt is rated 4-star and is currently priced at $69.
```

# Video Tutorial

For further information, you can watch the following video on constant property campaigns:

<Embed url="https://www.youtube.com/watch?v=Ia3-WT67kC8&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=2" title="Product Demo: Constant Property Campaigns" favicon="https://www.youtube.com/s/desktop/1f1401a5/img/favicon.ico" image="https://i.ytimg.com/vi/Ia3-WT67kC8/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=Ia3-WT67kC8&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=2" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FIa3-WT67kC8%253Flist%253DPLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DIa3-WT67kC8%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FIa3-WT67kC8%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
