---
title: Constant Event Property_Campaign_redesign_WIP
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

A *Constant Property* is an event property that can be tracked across multiple events. Segmentation is done if multiple events are done with the same value of the event property held constant. This feature enables a Marketer to create a single Campaign for all the values of the property held constant instead of individual campaigns for each value of the property.

## Example #1 - Single item engagement

As a growth marketer for an E-Commerce app, you want to segment out an audience that has Viewed a product in the past but not bought that exact same product. A straightforward segmentation would be to qualify people based on each product - Users who did Product Viewed Event where Product Name = Red Shoes in the last 30 days and Users who did not do Charged Event where Product Name = Red Shoes in the last 30 days. This would need to be repeated for all the items that the E-Commerce app has available.

"Constant Property" feature allows a single segmentation where you can mark the property "Product Name" to be kept constant and the system will fire the same query for all the values of the Product Name and qualify those users accordingly. The "Constant Property" value will be available as a Personalisation key inside the Message body. 

If User A has Viewed "Jenny red shoes" and not Purchased that exact product then would get an engagement as -\
Hello A\
You have added **Jenny red shoes** to your cart. How about a discount code Cashback20 to help you save more?

If User B has Viewed "Wonderland yellow jacket" and not Purchased that exact product then would get an engagement as -\
Hello B\
You have added  **Wonderland yellow jacket** to your cart. How about a discount code Cashback20 to help you save more?

## Example #2 - Summary engagement

As a growth marketer for the E-Commerce app, you may want to send a summary of Weekly Expenses and Savings on the transactions the User has done on the application. This can nudge the users to continue seeing value in purchasing from your E-Commerce platform.

The following are some sample engagement messages where John spent $100 over the last 1 week and saved $20 by using various coupons. Mary spent $120 over the last 1 week and saved $40 by using various coupons. You can send out a notification that says something like the following:

```text Message for John
Hello John!

The weekend sale is here! You have been able to save $20!! from your purchases worth $100 over the last week. Shop more on the weekend and choose from exciting products with more than 20% OFF!!
```
```text Message for Mary
Hello John!

The weekend sale is here! You have been able to save $40!! from your purchases worth $120 over the last week. Shop more on the weekend and choose from exciting products with more than 20% OFF!!
```

# Hold Event Property Constant

You can hold a property constant in an inaction campaign or a Past behavior type campaign. The Constant Event Property is currently supported for Push, Email, SMS, and Webhook campaigns.

## Alias Event Property 

In the cases where the same event property is called by different names for different events, you can create an Alias property that will hold all the properties from different events.  This Alias property can then be used across campaigns and analytics. 

For example, the event *Purchased* has an event property that holds the product id of the item called *product\_id*. However, the event *Added to cart* has an event property called *Product ID* that holds the same value. You can create an *Alias Event property* called *Product ID* that holds the event property *product\_id* and *Product ID*.\
This message can be achieved by holding an event property constant across [ Past Behavior Segments](doc:create-past-behavior-segments-1).

1. Navigate to *Settings* > *Schema* > *Events* > *Alias event property.*
2. Click the **+Alias Event Property** button. The *Create Alias Event Property* window displays.

MAYBE ADD IMAGE BELOW with 1 Alias event property dashboard - IMAGE FROM STAGING DASHBOARD HAS TYPOS\
DK>> INCLUDE FROM BETA DASHBOARD

3. Enter the name for the *Alias event property*.  
4. Click the **+ Event property** link to map current events and their properties to the new alias.

<Image title="Constant_Alias_create.png" alt={1195} className="border" border={true} src="https://files.readme.io/9115d0e-Constant_Alias_create.png" />

You can now use this *Alias event property* in all campaigns within the Constant Property option.

## Inaction Campaign

You want to engage all the users who dropped off after adding a product to the cart. The event property across these events is *Product Name*. The value of this event property can be anything from Jenny's red shoes, running shoes, a Wonderland yellow jacket, a baseball bat, and so on.

You can define the conditions for the target audience and then select the constant event property.

To create a campaign, perform the following steps:

1. From the dashboard, navigate to *Campaigns*.
2. Click **+ Campaign**.  
3. Select a messaging channel.  

{user["CHANGE SCREENSHOT TO ONE WITH BETTER NAMES"]}

![1578](https://files.readme.io/9e0e992-1_Plus_Campaign.png "1_Plus_Campaign.png")

4. Under the *Start here* section, select the qualification criteria as *Live Behavior*. 

@PM: OUR EXISTING DOC USED TO SAY 'LIVE SEGMENT'. PLEASE CONFIRM IF STEP 4 AND THIS SCREENSHOT WORKS OR NOT. (I COULDN'T FIGURE OUT HOW TO MAKE IT WORK WITH THE 'LIVE BEHAVIOR' SELECTION

DK>> Under WHO, select segment and use Inaction within time.

5. Click **Done**.

{user["CHANGE BELOW SCREENSHOT"]}

![1575](https://files.readme.io/db547ee-2_Past_Behavior_copy.png "2 Past Behavior copy.png")

6. Under the *Who* section, select events and properties, as required.
7. Select the *Constant event property* checkbox, then select *Product name*.

@PM: IS THE SCREENSHOT BELOW CORRECT?\
DK>> NO, CHOOSE LIVE USER OPTION AND THEN CHOOSE INACTION WITHIN TIME IN WHO UNDER FIND USERS FROM OPTION

8. Click **Done** and personalize the message using [Liquid Tags](doc:liquid-tags) under the *What* section.

<Image title="3 Constant Event Property.png" alt={1574} className="border" width="80%" border={true} src="https://files.readme.io/5c05e3a-3_Constant_Event_Property.png" />

\<\<THIS SHOULD BE IN CONTINUATION OF THE ABOVE, WE HAVE SHOW WHO AND WHEN THIS NEEDS TO UNDER THE WHAT SECTION WITH SCREENSHOT.>>

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

## Past Behavior Campaigns

\<\<CHANGED THE EXAMPLE HERE, REITERATE THE PREVIOUS EXAMPLE>>

Let's take the earlier [OTT example](https://docs.clevertap.com/docs/constant-property#section-sending-a-summary). You can define the conditions for the target audience and then select the constant event property.

To create a campaign, perform the following steps:

1. From the dashboard, navigate to *Campaigns*.
2. Click **+ Campaign**.  
3. Select a messaging channel.  

![1578](https://files.readme.io/976b4ed-1_Plus_Campaign_copy.png "1_Plus_Campaign copy.png")

4. Under the *Start here* section, select the qualification criteria as *Past behavior/Custom list*. 
5. Click **Done**.

![1575](https://files.readme.io/6777ed7-2_Past_Behavior_copy.png "2 Past Behavior copy.png")

6. Under the *Who* section, select events and properties, as required.
7. Select the *Constant event property* checkbox, then select *Product name*.

@PM: IS THE SCREENSHOT BELOW CORRECT?\
DK>> YES

8. Click **Done** and personalize the message using [Liquid Tags](doc:liquid-tags) under the *What* section.

![1574](https://files.readme.io/e1624c2-3_Constant_Event_Property.png "3 Constant Event Property.png")

{user["SHOW WHAT PAGE COMPLETELY."]}\
For example, you can send the campaign with a list of shows that the user is still watching.

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

# Stats

The stats page for Campaigns where the "Constant Property" feature is used, shows comprehensive details as follows:

* Event count for each value of the constant event property (Top 10 or Bottom 10)
* User count for each value of the constant event property for notification sent, viewed, clicked, converted and in control group

You can change the conversion event and map the conversion event's property to the constant event property and also track conversion for the same value of event property. 

<Image title="Constant_property_PBS_Stats.png" alt={1134} className="border" border={true} src="https://files.readme.io/75de59b-Constant_property_PBS_Stats.png" />

## Conversion Event

The conversion event helps you to track conversion. To track revenue, set the user conversion event from the campaign setup. 

* Mapping constant property with conversion event property allows you to view conversion rate for specific property values
* You can view metrics for any conversion event and track conversion rate when any item is purchased or track the conversion rate for a specific item that is added to cart.

<Image title="Constant_property_conversion_event.png" alt={1162} className="border" border={true} src="https://files.readme.io/378af2e-Constant_property_conversion_event.png" />

# Advanced - Constant Property with Catalog Personalization

You can combine [catalog personalization](doc:catalog-personalization) with constant event property to unleash the full power of campaign personalization. 

For example, you can hold an event property (Product ID) constant and also add to it the rating and cost present in a catalog via catalog personalization.

![809](https://files.readme.io/50a187b-Constant_property_with_Catalog_Personalization.png "Constant_property_with_Catalog_Personalization.png")

First, you must map the constant event property to the catalog. To do so, perform the following steps:

1. From the dashboard, navigate to *Campaigns*.
2. Click **+ Campaign**.  
3. Select a messaging channel.  

![1578](https://files.readme.io/772970c-0_Plus_Campaign.png "0 Plus_Campaign.png")

4. Under the *What* section, select a message type.
5. Click **Go To Editor**.

![1574](https://files.readme.io/35914a0-1_Go_to_Editor.png "1 Go to Editor.png")

6. Click **Personalization**.

![1668](https://files.readme.io/7298b1c-2_Personalization.png "2 Personalization.png")

7. Under *Catalog*, select a catalog.
8. Select events and properties, as required.
9. Click **Apply**.

![994](https://files.readme.io/907964c-3_Personalization_Setup.png "3 Personalization Setup.png")

10. Enter any mandatory content for your message.
11. Click **Done**.

![1666](https://files.readme.io/7384852-4_Fill_out_content.png "4 Fill out content.png")

12. Under the *Who* section, select events and properties, as required.
13. Select the *Constant event property* checkbox, then select *Product name*.

@PM: IS THE SCREENSHOT BELOW CORRECT? THE EXISTING DOC HAD A STEP 'Map the constant event property to the column. This will be used for fetching values from the catalog.' AND I COULDN'T FIGURE OUT THIS STEP IN THE NEW DASHBOARD.\
DK>> ONCE YOU SELECT THE CATALOG YOU WILL GET THE OPTION TO MAP THE PROPERTIES

14. Click **Done**.

![1598](https://files.readme.io/4970fdc-5_Constant_Event_Property.png "5 Constant Event Property.png")

## Past behavior Campaign Personalization

For Past behavior Campaigns, you can use the following liquid script. In this example, the item is the index used for looping over the list of items for a user. *Rating* and *Amount* are the column names from which we are fetching additional values that can be used in the message. 

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

## Inaction Campaigns Personalization

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
