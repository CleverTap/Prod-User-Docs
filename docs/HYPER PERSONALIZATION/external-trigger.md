---
title: External Trigger
excerpt: Learn how to create a External Trigger campaign using the CleverTap dashboard.
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

External Trigger campaigns are a feature that allows you to trigger the campaign delivery based on API calls or external events. These campaigns are particularly well-suited for advanced scenarios, where the marketer creates the campaign content within the CleverTap dashboard, and the content delivery is triggered from your servers and systems. The API request used to trigger the message can include supplementary data that can be dynamically inserted into the message.

<Callout icon="📘" theme="info">
  ### **Public Beta**

  This feature is released in Public Beta. Contact your Customer Success Manager to know more about this feature.
</Callout>

# Key Benefits

CleverTap's External Trigger feature can be a powerful tool for various applications across domains. The following are some of the use cases where different businesses can use this feature to provide real-time communication and automation capabilities:

- **Subscription Purchases or Upgrade Alerts**<br />When a user purchases or upgrades their subscription plan, an external trigger can automatically send confirmation emails to the user.

- **Fitness Milestones Achieved**<br />When a user reaches a significant milestone, such as recording 15k steps daily, an external trigger can send them a congratulatory notification or email. These notifications are positive reinforcement that celebrates user achievements, motivating them to maintain their fitness routines and engage more with the app.

- **Order Confirmation**: Whenever an order is placed, an e-commerce platform makes an API call to the notification service, passing along the necessary information such as the product ID, product name, pricing details, and so on.

Businesses and applications can engage users effectively and ensure users receive timely updates and notifications based on specific events or conditions. Also, it significantly improves user satisfaction and overall user engagement in various domains.

# Create an External Trigger Campaign

To create a new External Trigger campaign:

1. From the dashboard, select _Campaigns_.
2. Click + Campaign.
3. Select the messaging channel from the Messaging Channels list. This feature is currently available for the _Push Notifications_, _Email_, _Webhook_, and _App Inbox_ messaging channels.


<Image src="https://files.readme.io/a0f8ec12123bf8c5c3bb504a096c54b76083a69034625df3dd9d6b6a20f1ac8a-Select_a_Campaign_from_Campaign.png" alt="Select Messaging Channel" align="center" border={true} />


The campaign page displays.


<Image src="https://files.readme.io/2a7f09a-image.png" alt=" Create Campaign" align="center" width="90% " border={true} />


4. Define all the sections and publish the campaign.
5. [Trigger campaign via API](https://developer.clevertap.com/docs/external-trigger-api).

## Start Campaign Setup

The _Start here_ section displays the setup information. Before moving ahead, ensure that the required platforms are integrated and ready for campaigns.

This section has the following parts:

#### Qualification Criteria

Setting up an External Trigger campaign takes a few steps. After selecting the messaging channel, select _External Trigger_ from the _Qualification Criteria_ section.


<Image src="https://files.readme.io/3b8c83e-image.png" alt="Set Up External Trigger Campaign" align="center" border={true} />


#### Set a Goal

Setting a goal is optional. It allows you to measure your campaign effectively. You can define your conversion goal further by selecting the Event and Conversion time.

The campaign goal can be as generic or as specific as you want. It can answer questions such as "How many users were influenced to purchase an X amount?" or "How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ".


<Image src="https://files.readme.io/d248ab8-image.png" alt="Set a Goal" align="center" border={true} />


## Define the Audience

### Target Segment

External Trigger campaigns are triggered against the user ID. However, marketers can further filter the segment based on past behavior and user properties.


<Image src="https://files.readme.io/9d48b71-image.png" alt="Define Target Segment - Who" align="center" width="85% " border={true} />


For example, an e-commerce portal wants to send an order confirmation to the buyer with all the product details. In this case, the users qualify as soon as they purchase, and the External Trigger campaign is sent to the user. Though the trigger remains the same, you can further narrow your target audience by selecting the _Filter on past behavior and user properties_ option. For example, you want to send an order summary and a discount code to your _Gold_ members. Here, you are filtering your target audience with the user property `Customer Type` = Gold.

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups).


<Image src="https://files.readme.io/25a2953-image.png" align="center" width="75% " border={true} />


### Targeting Cap

You can limit the number of users receiving the message.

A relevant use case is a limited offer where you want to distribute a fixed number of coupon codes. If the total reach for your campaign exceeds the number of coupon codes you can distribute, then you can limit the number of users who will receive the message to precisely the number of coupons you want to distribute.

<Callout icon="📘" theme="info">
  ### Campaign Limit

  Ensure that you set up a limit of 100 or more, regardless of the qualified user segment size. If the limit specified is less than 100, an error occurs.
</Callout>


<Image src="https://files.readme.io/62861db-image.png" alt="Target Cap in Campaign" align="center" width="80% " border={true} />


## Define the Message

Consider the same example where the e-commerce portal wants to send the summary of the order placed to the buyer. The summary message can include the following supplementary data:

- Product Name
- Product ID
- Product Image
- Pricing Details like Cost of the product, Transaction Fee, Processing Fee, Shipping Fee, etc

You can do so from the Editor of the respective messaging channel. CleverTap has a messaging object called `ExternalTrigger` that allows you to define the keys for personalization. The API call processes the user attributes object and dynamically fetches the values for keys from the incoming API payload before sending a campaign to the user.

Use Liquid Tags to include all the required parameters in your message body. The following are the sample campaigns to send order summary, including the details mentioned above:

- **Example 1: Without Conditional Tags**


<Image src="https://files.readme.io/6f6bdbc-Sending_Order_Confirmation_-_Without_Conditional_Tags.png" alt="Email Campaign for Sending Order Confirmation - Without Conditional Tags" align="center" border={true} />


You can copy the above message body from the following block:

```json Message Body
Hey {{ Profile.name | default: "User" }}

Thank you for shopping with us!

    Name: {{ ExternalTrigger.Name | default: "defaultName" }}
    Price: {{ ExternalTrigger.Price | default: "defaultPrice" }}
    ImageUrl: {{ ExternalTrigger.ImageUrl | default: "defaultImageUrl" }}

```

- **Example 2: With Conditional Tags**


<Image src="https://files.readme.io/577aed5-Sending_Order_Confirmation_-_With_Conditional_Tags.png" alt="Email Campaign for Sending Order Confirmation to Buyers" align="center" border={true} />


You can copy the above message body from the following block:

```json Message Body
Hey {{ Profile.name | default: "User" }}

Thank you for shopping with us!
{% for product in ExternalTrigger.productDetails %}
Name: {{ product.productName | default: "defaultProductName"}}
productID: {{product.productID | default: "defaultProductId"}}
imageURL: {{product.imageURL | default: "defaultImageUrl"}}
{% for pricingDetail in product.pricingDetails %}
{{ pricingDetail.name | default : "defaultPriceName"}} : {{ pricingDetail.value | default : "defaultPriceValue"}} 
 {% endfor %}
{% endfor %}
```

## Define the Campaign Schedule

### Date and time

You can set up the _When_ section to schedule the campaign start and end using the options below:

- Start date and time
- End date and time

### Delivery preferences

You can apply global campaign limits to determine how many push notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the _Don’t apply global campaign limits to this campaign_ checkbox.

You can also click the _Advanced_ checkbox to specify _Do Not Disturb_ (DND) hours during which notifications from this push campaign are prevented from going out, either by discarding them or delaying delivery after DND hours, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).


<Image src="https://files.readme.io/60373b1-PBS_Delivery_Preferences.png" alt="2214" align="center" border={true} />


## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:

1. Click **Continue** to view your campaign summary. The _Overview_ page displays.
2. View your campaign summary, then click **Publish Campaign**. You must have a Campaign ID, created when you publish the campaign, to send messages with the endpoint.


<Image src="https://files.readme.io/ee83fe1-image.png" alt="Publish Campaign" align="center" width="90% " border={true} />
