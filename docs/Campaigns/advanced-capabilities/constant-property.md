---
title: Constant Event Property
excerpt: Design campaigns based on a constant property across events.
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

A _Constant Property_ is an event property that can be tracked across multiple events. Segmentation is done if multiple events are done with the same value of the event property held constant. This feature enables a marketer to create a single Campaign for all the values of the property held constant instead of individual campaigns for each value of the property.

## Example #1 - Single Item Engagement

As a growth marketer for an E-Commerce app, you want to segment out an audience that has Viewed a product in the past but not bought that exact product. A straightforward segmentation would be to qualify people based on each product - Users who did Product Viewed Event where Product Name = Red Shoes in the last 30 days and Users who did not do Charged Event where Product Name = Red Shoes in the last 30 days. This would need to be repeated for all the items the E-Commerce app has available.

The "Constant Property" feature allows a single segmentation where you can mark the property "Product Name" to be kept constant, and the system will fire the same query for all the values of the Product Name and qualify those users accordingly. The "Constant Property" value will be available as a Personalisation key inside the Message body.

If User A has Viewed "Jenny red shoes" and not Purchased that exact product, then they would get an engagement as -<br />Hello A<br />You have added **Jenny's red shoes** to your cart. How about a discount code, Cashback20, to help you save more?

If User B has Viewed "Wonderland yellow jacket" and not Purchased that exact product, then would get an engagement as -<br />Hello B<br />You have added a **Wonderland yellow jacket** to your cart. How about a discount code, Cashback20, to help you save more?

## Example #2 - Summary Engagement

As a growth marketer for the E-Commerce app, you may want to send a summary of Weekly Expenses and Savings on the User's transactions on the application. This can nudge the users to continue seeing value in purchasing from your E-Commerce platform.

The following are some sample engagement messages where John spent $100 over the last week and saved $20 using various coupons. Mary spent $120 the previous week and saved $40 using multiple coupons. You can send out a notification that says something like the following:

```text Message for John
Hello John!

The weekend sale is here! You have been able to save $20!! from your purchases worth $100 over the last week. Shop more on the weekend and choose from exciting products with more than 20% OFF!!
```
```text Message for Mary
Hello Mary!

The weekend sale is here! You have been able to save $40!! from your purchases worth $120 over the last week. Shop more on the weekend and choose from exciting products with more than 20% OFF!!
```

# Example #3 - Category-Level Engagement

As a growth marketer for an e-commerce app, you want to engage users who viewed a product category, such as Shoes, but did not purchase any products in that category. Creating a separate segment for each product category is not practical. The Constant Event Property feature handles this with a single segment. Mark the product_type property as constant, and CleverTap evaluates the same category value across the `Product Viewed` and `Charged` events.

The segment logic is as follows:

- User performed `Product Viewed`
- User did not perform `Charged`
- `product_type` from `Product Viewed` is held constant for comparison

If User A viewed product type = Shoes and did not purchase any item with product type = Shoes, the user qualifies for the segment. The campaign can then personalize the message using the constant property value.

<Callout icon="📘" theme="info">
  ### Note

  This use case uses a category-level property (product_type) rather than an item-level property (product_name). Use this approach when you want to engage users based on broad interest in a category rather than a specific product.
</Callout>

# Limitations

The Constant Event Property feature supports the Live Behavior (inaction) campaign types.

The following use cases are not supported natively:

Filtering users who performed an event with the same property value more than a specified number of times within a given time window. For example, users who viewed the same product type more than 3 times in the last 24 hours. Triggering a campaign on the nth occurrence of an event for the same property value.

# Hold Event Property Constant

You can hold a property constant in an inaction campaign. Currently, the Constant Event Property supports Push, Email, SMS, and Webhook campaigns.

## Alias Event Property

If different names call the same event property for various events, you can create an Alias property that will hold all the properties from other events.  You can then use this across campaigns and analytics.

For example, the event _Purchased_ has an event property that holds the product id of the item called _product_id_. However, the event _Added to carthas an event property called Product ID_ that holds the same value. You can create an _Alias Event property_ called _Product ID_ containing the event property _product_id_ and _Product ID_.

1. Navigate to _Settings_ > _Schema_ > _Events_ > _Alias event property._
2. Click the **+Alias Event Property** button. The _Create Alias Event Property_ window displays.
3. Enter the name for the _Alias event property_.
4. Click the **+ Event property** link to map current events and their properties to the new alias.


<Image src="https://files.readme.io/30998fe-Alias_Event_property.png" alt="447" align="center" border={true} />


You can now use this _Alias event property_ in all campaigns within the Constant Property option.

## Inaction Campaign

You want to engage all the users who dropped off after adding a product to the cart. The event property across these events is _Product Name_. The value of this event property can be anything from Jenny's red shoes, running shoes, a Wonderland yellow jacket, a baseball bat, and so on.

You can define the conditions for the target audience and then select the constant event property.

To create a campaign:

1. From the dashboard, navigate to _Campaigns_.
2. Click **Create Campaign**.


<Image src="https://files.readme.io/58eeb9b6ee30089676ad4a77aec7694fb79a1a86067a93f743aaca4f779b5b15-image.png" align="center" caption="Create Campaign" border={true} />


3. Select a messaging channel.

4) Under the _Start here_ section, select the qualification criteria as _Live Behavior_.
5) Click **Done**.


<Image src="https://files.readme.io/a82b66d-StartHere_LiveBehavior.png" alt="659" align="center" border={true} />


6. Under the _Who_ section, select events, and properties, as required.
7. Select the _Constant event property_ checkbox, then select _Product name_.
8. Click **Done** and personalize the message using [Liquid Tags](doc:liquid-tags) under the _What_ section.


<Image src="https://files.readme.io/bb4eb58f1a46f7a5daa9cb56b293936cffc2a9bd537e3d2cca45b4e551d4e63e-image.png" align="center" caption="Who Section" border={true} />


For example, you can send the campaign with the item name that the user who added an item to the cart but did not purchase.

```liquid
Hurrah.. ! 
Complete your purchase of {{ ConstantEventProperty | default:"this item" }} with 15% off on using code GRT572E.
```

Following is a sample message the user gets:

```text
Hurrah.. ! 
Complete your purchase of Jenny red shoes with 15% off on using code GRT572E.
```

We hold the property, such as _Products,_ across all events. The _Product property_ value can be anything, such as Jenny red shoes, Cool Ice blue goggles, or George High white hat. The Constant Event Property holds the value of the product.

<Callout icon="📘" theme="info">
  ### Note

  If the campaign uses Constant Event Property personalization with a delay greater than 24 hours, default values are sent.
</Callout>

# Stats

The stats page for Campaigns, where the _Constant Property_ feature is used, shows comprehensive details as follows:

- Event count for each value of the constant event property (Top 10 or Bottom 10)
- User counts for each value of the constant event property for notification sent, viewed, clicked, converted, and in the control group.

You can change the conversion event, map its property to the constant event property, and track conversions for the same event property value.

## Conversion Event

The conversion event helps you track conversions. To track revenue, set the user conversion event from the campaign setup.

- Mapping a constant property with a conversion event property allows you to view the conversion rate for specific property values.
- You can view metrics for any conversion event and track the conversion rate when any item is purchased, or track the conversion rate for a specific item that is added to the cart.


<Image src="https://files.readme.io/378af2e-Constant_property_conversion_event.png" alt="1162" align="center" border={true} />


# Advanced - Constant Property with Catalog Personalization

You can combine [catalog personalization](doc:catalog-send-time-personalization) with constant event property to unleash the full power of campaign personalization.

For example, you can hold an event property (Product ID) constant and also add to it the rating and cost present in a catalog via catalog personalization.


<Image src="https://files.readme.io/50a187b-Constant_property_with_Catalog_Personalization.png" alt="809" align="center" border={true} />


First, you must map the constant event property to the catalog. To do so, perform the following steps:

1. From the dashboard, navigate to _Campaigns_.
2. Click **+ Campaign**.
3. Select a messaging channel.
4. Under the _What_ section, select a message type.
5. Click **Go To Editor**.


<Image src="https://files.readme.io/35914a0-1_Go_to_Editor.png" alt="1574" align="center" border={true} />


6. Click **Personalization**.


<Image src="https://files.readme.io/7298b1c-2_Personalization.png" alt="1668" align="center" border={true} />


7. Under _Catalog_, select a catalog.
8. Select the required events and properties.
9. Click **Apply**.


<Image src="https://files.readme.io/907964c-3_Personalization_Setup.png" alt="994" align="center" border={true} />


10. Enter any mandatory content for your message.
11. Click **Done**.


<Image src="https://files.readme.io/7384852-4_Fill_out_content.png" alt="1666" align="center" border={true} />


12. Under the _Who_ section, select the required events and properties.
13. Select the _Constant event property_ checkbox, then select _Product name_.
14. Click **Done**.


<Image src="https://files.readme.io/4970fdc-5_Constant_Event_Property.png" alt="1598" align="center" border={true} />


## Inaction Campaigns Personalization

For inaction campaigns, you can use the following liquid script to use a particular column from the selected catalog in the message.

```liquid
Hurrah.. ! 
Complete your purchase of {{ ConstantEventProperty | default:"this item" }}, with 15% off on using code GRT572E.

{{ ConstantEventProperty | default:"this item" }} is rated {{ Catalog["Amount Catalog"].Rating | default:"3" }}-star and is currently priced at {{ Catalog["Amount Catalog"].Amount | default:"$99" }}.
```

A user receives a message like:

```text
Hurrah.. ! 
Complete your purchase of Nautical White T-shirt, with 15% off on using code GRT572E.

Nautical White T-shirt is rated 4-star and is currently priced at $69.
```

```text

Nautical White T-shirt is rated 4-star and is currently priced at $69.
```
