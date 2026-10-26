---
title: Personalize Message
excerpt: ''
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

You can personalize the message for every user based on specific user identity, user property, event property, or campaign ID values. For more information on user profile properties and events (dynamic replacements), refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [Events](https://docs.clevertap.com/docs/events#event-properties).

# Inline Personalization

To invoke the personalization menu, type the _@_ or the \_\{\{\}\}\_symbol in the title or the text fields while creating a message.

You can also add dynamic replacements in the title and body. Notice a preview as displayed below.


<Image src="https://files.readme.io/006da83-Inline_Personalization.png" alt="1095" align="center" caption="Personalize Messages using Dynamic Text" border={true} />


In addition to the title and body, you can personalize many other things, such as media URLs, deep links, or button text. An _@_ icon in a box indicates that it can be personalized.

<br />


<Image src="https://files.readme.io/51be44068b21589f9266a8903e0b16c705c707e0a83018d193bc2377cc255255-Personaliza_Media_URL.png" alt="748" align="center" caption="Add Media URLs, Deep Links or Button Text" border={true} />


# Identity Personalization

Identity personalization in CleverTap enables you to tailor user experiences and messaging based on individual user identities, such as email ID, identity, and phone number. For example, if you are a streaming platform and you want to send a campaign offering a 50% discount on the first-month subscription to users who have registered with a mobile number but have not subscribed to premium content. In this case, you can use identity personalization as follows:


<Image src="https://files.readme.io/699d610-Identity_Personalization_Example.png" alt="Identity Personalization Example" align="center" caption="Identity Personalization Example" border={true} />


You can also target a segment through a multi-channel marketing approach. This strategy involves utilizing various channels, such as email and personalized landing pages. For a personalized experience, email communications can include details such as the user’s name. Users can also be directed to personalized URLs (\<[https://demoapp.com/\{\{Profile.Identity](https://demoapp.com/\{\{Profile.Identity) | default: "Default User"\}\}>) to further engage them with the campaign. The microsites associated with these URLs can mirror the email content and serve as redirection links across different channels, such as Push Notification and WhatsApp, to maintain a consistent, personal experience for the audience.


<Image src="https://files.readme.io/04c801c-Identity_Personalization_Example_-_Email.png" alt="Identity Personalization Using Personalized URLs" align="center" caption="Identity Personalization Using Personalized URL" border={true} />


<Callout icon="📘" theme="info">
  #### Key Points to Remember

  In the cases where mulitple identities are present, the most recent identity value is used and the notification is sent with those values.
</Callout>

When crafting any campaign message, you can leverage identity personalization by typing @ or the \{\{\}\} symbol in the title or text fields (refer to the following images).


<Image src="https://files.readme.io/ad0cf22d11b905aa6f1baeb47e9516e1cec82151a5a97b561acbe13e56462b1d-Identity_Personalization_Using_Personalization.png" alt="Identity Personalization Using @Personalization" align="center" width="75% " caption="Identity Personalization Using @Personalization" border={true} />



<Image src="https://files.readme.io/201345db3e709ee65faf25b8c365870e9979e641dd12e21dc5fcd87fb04aea42-Identity_Personalization_Using_Liquid_Tags.png" alt="Identity Personalization Using Liquid Tags" align="center" width="75% " caption="Identity Personalization Using Liquid Tags" border={true} />


<Callout icon="📘" theme="info">
  #### Key Points to Remember

  In the cases where multiple identities are present, the most recent identity value is used and the notification is with that value.
</Callout>

# Liquid Tags

Click the ![Personalization](https://files.readme.io/b852e7f-Personalization_setting.png) icon in the editor to open personalization options.

Liquid tags offer great flexibility while composing personalized messages. Liquid tags allow you to add logic using a scripting language, which you can use to change the look and feel of your message. Following is an example to send personalized coupon codes based on the type of membership:


<Image src="https://files.readme.io/ed642bf-campaigns_liquid_tags_common_example.png" alt="1357" align="center" caption="Personalized Messages using Liquid Tags" border={true} />


Each notification is personalized to the receiver.

```html Output - Liquid
Hello John!

Here is a special coupon for you: Gold4All
```

For more information on using tags, refer to [Liquid Tags](doc:liquid-tags).

<Callout icon="📘" theme="info">
  #### Personalize Date Property

  When customizing event or profile properties that involve dates, we transform them into different formats for liquid tags and @ personalization.

  For instance:

  - For Liquid Tags personalization, CleverTap transforms the expression \{\{ Event\["Primary Traveler DOB"] | default: "Default" \}\}\ into "2023-05-29 15:55:00" to display both the date and time.
  - For @ Personalization, CleverTap transforms the expression into @Charged - Date | default: "Default" \}\} into "May 29, 2023" to display only the date.
</Callout>

## Liquid Personalization with Nested Objects

You can use nested profile and event properties with Liquid tags to personalize messages using structured data stored within user profiles or events. Nested Object personalization is supported up to three levels.

This allows you to reference specific attributes within complex data structures without restructuring or duplicating data, keeping your campaigns precise, scalable, and highly relevant.

For example, if your user profile stores subscription details inside a `subscription` object, you can dynamically insert it into your message:
`{{ Profile.subscription.planName | default: "your plan" }}`

**Sample Campaign**:

```Text Campaign Message
“Enjoy exclusive benefits with your {{ Profile.subscription.planName | default: 'current' }} plan.”
```

In this case, the message dynamically inserts the user’s exact plan name, making the communication more contextual and personalized. If the value is unavailable, the fallback value (in this case, `current`) ensures the message still reads naturally.

For more information on prerequisites, syntax, and validation, refer to [Liquid Personalization with Nested Objects](doc:liquid-tags#liquid-personalization-with-nested-objects).

# Event Personalization by Campaign Type

Event property personalization (via `@` tags, `{{ }}`) is not available uniformly across all campaign types. Support depends on the trigger type, delay configuration, and whether Constant Event Property is enabled. Refer to the following table to learn more:

| Campaign Type | Single occurrence, delay ≤ 24 hours     | Multiple occurrences, delay ≤ 24 hours            | Single occurrence, delay > 24 hours                                                                                                                                                                  | Multiple occurrences, delay > 24 hours                                                                                                                                                           |
| ------------- | --------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Action**    | Live trigger with event personalization | Live trigger with event personalization per event | Works as PBS. Starts on Publish with trigger event personalization                                                                                                                                   | Works as PBS. Starts on Publish; triggered per event with event personalization                                                                                                                  |
| **Date Time** | Live trigger with event personalization | Live trigger with event personalization per event | Works as PBS with trigger event personalization                                                                                                                                                      | Works as PBS; triggered per event with event personalization                                                                                                                                     |
| **Inaction**  | Live trigger with event personalization | Live trigger with event personalization per event | Works as PBS. On Publish, checks messages for the last X minutes/days and sends with trigger. **Exception**: Constant Event Property campaigns remain on the old flow with no event personalization. | Works as PBS. On Publish, checks the actual delay and sends; multiple messages triggered per event occurrence with event personalization. To limit sends, use Limits under Delivery Preferences. |

Inaction campaigns with a delay greater than 24 hours are the same as live campaign types for all occurrence configurations.

# Linked Content

Linked content provides the ability to personalize emails with rich and contextual data available outside of the CleverTap platform. With linked content, you can send messages with send-time personalization.

For example, you deliver food across different geographies, and you want to personalize offers to each user based on the weather and location. The location can come from CleverTap personalization, and the weather information can come from an API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

```liquid
Hi {{ Profile.name | default:"there!" }},

{% if Linked.cityBasedWeather.temp > 30 %}
It is a bright sunny day in {{ Profile.location | default:"your city" }}. How about a barbeque today?

Use the coupon code (BARBQ).
These are the top 5 restaurants near you:
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}


{% elsif Linked.cityBasedWeather.temp < 10 %}
It is indeed cold today in {{ Profile.location | default:"your city" }}!! 
Time for some hot pizza!
                                         
Use the coupon code (PIZZA). These are the top 5 restaurants near you:
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
                                          
{% else %}
                                          
It has  been a while in {{ Profile.location | default:"your city" }}. 
Order something exotic!
                                          
Use the coupon code (EXOTIC).These are the top 5 restaurants near you:           {% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
                                          
{% endif %}
```

For more information, refer to [Linked Content](https://docs.clevertap.com/docs/linked-content#write-linked-content).

# Recommendations

Click the ![Personlization](https://files.readme.io/b852e7f-Personalization_setting.png) icon in the editor to open personalization options.

After you have uploaded a catalog, you can display personalized recommendations to your customers. For example, you can display a sliding carousel based on their personal likes! For more information on recommendations, see [Recommendations](doc:recommendations).


<Image src="https://files.readme.io/6264702-Recommendation_Sample.png" alt="1752" align="center" caption="Create Personalized Recommendations" border={true} />


# Catalog

Click the ![Personlization](https://files.readme.io/b852e7f-Personalization_setting.png) icon in the editor to open personalization options.  Select a catalog from the list.

A _Catalog_ provides the ability to personalize campaigns with dynamic information in messages from product prices to inventory levels. You can create a new product catalog by uploading a file that contains one row for each item in your product catalog. A _Catalog_ can be uploaded directly on the CleverTap dashboard via a CSV file that is generated by your inventory management system. For more information on _Catalogs_, see [Catalogs](doc:catalog).


<Image src="https://files.readme.io/5077276-catalog_sample.png" alt="1560" align="center" caption="Create a Catalog" border={true} />


# Campaign ID Personalization

To invoke the personalization menu, type the _@_ or the _\{\{\}\}_ symbol in the title, message, and Deep link/Open URL fields when creating a message.

Campaign ID Personalization allows you to customize and personalize your marketing campaigns based on specific campaign IDs. For example, you can send a follow-up email with personalized recommendations related to the products or services featured in the user's previous campaign interaction.

For more information, refer to [Campaign ID Personalization](doc:campaign-id-personalization).

# Constant event property

Constant Event Property allows you to engage the user on multiple actions and inactions. For example, person A added to cart a white coat and person B added to cart a pair of blue jeans, but they both did not purchase the items.

You can either create a campaign for each product that was added to the cart or you can use a _constant event property_ to personalize the campaign to each user that did not purchase the item.

For example, you can map the _prod_name_ property of the _charged_ event to the _product_name_ property of the _added to cart_ event. You can then hold this property constant across both events. Based on this property, you can now personalize the message received by each user.


<Image src="https://files.readme.io/790bd5c-Constant_property_sample.png" alt="1374" align="center" caption="Constant Event Property" border={true} />


For more information on using a constant event property, see [Constant Event Property](doc:constant-property).

#