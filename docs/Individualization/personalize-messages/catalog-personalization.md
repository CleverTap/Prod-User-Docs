---
title: Catalog Send-Time Personalization
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

Catalog send-time personalization provides the ability to personalize messages with external data pulled from an uploaded catalog at the time a campaign is sent. Automatically include dynamic information directly in a message such as product price, product category, available inventory levels, and more. 

> 👍 E-commerce App Example
>
> A user adds a laptop to the cart, then exits. By providing additional details in the engagement message such as the image, size, latest price, and specifications of the laptop, the user can be nudged to purchase the item. Using catalog send-time personalization helps keep users engaged in a meaningful way.

After you have uploaded the catalog, you can start using it in a campaign. For more information, refer to [Catalog](https://docs.clevertap.com/docs/catalog).

# Event Property

Follow the steps below to personalize a catalog by event property:

1. Create a [campaign](doc:intro-to-campaigns).

2. Click the **Personalization Setup** link to select a catalog. Once the personalization setup window displays, you can map the required catalog columns to event properties and user properties. 

<Image title="Catalog_personalization_setup_new.png" alt={1387} className="border" border={true} src="https://files.readme.io/0fddae4-Catalog_personalization_setup_new.png" />

3. Click the **Catalog Send-Time** tab and select the required catalog from the list. 

<Image title="Catalog_personalization_select_catalog_new.png" alt={727} width="80%" src="https://files.readme.io/ec5d255-Catalog_personalization_select_catalog_new.png" />

4. Select the event. You can personalize your message based on the property values of this event. 

<Image title="catalog_personalization_select_event.png" alt={719} className="border" width="80%" border={true} src="https://files.readme.io/f852b40-catalog_personalization_select_event.png" />

> 📘 Recent Occurrence
>
> The most recent occurrence of the event is used to select the relevant item from the catalog. If the campaign is a triggered campaign, then the event that triggered the campaign is considered.

5. Select the event property to map to the catalog column. This mapping is important to identify the catalog column that matches the event property. For example, we map *Product Name*, such as a laptop (from the *Viewed* event) to the *Name* column in the catalog. 

Repeat this step to map more properties. 

> 📘 Map Multiple Properties
>
> If required, map multiple properties. Every addition to the mapping is treated as an *and* condition. For example, map the name, the color, and the brand to personalize the message for the user.

<Image title="catalog_personalization_select_catalog_property.png" alt={719} className="border" width="80%" border={true} src="https://files.readme.io/08aa75d-catalog_personalization_select_catalog_property.png" />

6. Click **Save** to set up the personalization. 

7. Use [liquid tags](doc:liquid-tags) to create a personalized message for your target audience. 

In this example, the syntaxes for using different catalog columns are shown below:

```liquid Liquid Tag
{{ Catalog.["Sample Catalog"].Name | default: "Laptop" }}
{{ Catalog.["Sample Catalog"].Amount | default: "0" }}
```

![1173](https://files.readme.io/3069384-catalog_personalization_liquid_message.png "catalog_personalization_liquid_message.png")

You can now use the latest amount for the last added to cart item, such as the laptop. 

# User Property 

Follow the steps below to personalize a catalog by user property:

1. Create a [campaign](doc:intro-to-campaigns).
2. Click the **Personalization Setup** link to select a catalog. Once the personalization setup window displays, you can map the required catalog columns to event properties and user properties. 

<Image title="Catalog_personalization_setup_new.png" alt={1387} className="border" border={true} src="https://files.readme.io/b776884-Catalog_personalization_setup_new.png" />

3. Click the **Catalog Send-Time** tab and select the required catalog from the list. 

<Image title="Catalog_personalization_select_catalog_new.png" alt={727} width="80%" src="https://files.readme.io/792a568-Catalog_personalization_select_catalog_new.png" />

4. Select the user property to map to the catalog column. For example, you can recommend the top restaurant in New York with rich details about the restaurant from the catalog to a user with the user property *City* set as New York. 

> 📘 Note
>
> If required, map multiple properties. Every addition to the mapping is treated as an *and* condition. For example, map the city, the top-rated restaurants, and the Chinese restaurants to personalize the message for the user.

<Image title="catalog_personalization_map_user_property.png" alt={727} className="border" width="80%" border={true} src="https://files.readme.io/c2cea0e-catalog_personalization_map_user_property.png" />

5. Click **Save** to set up the personalization. 
6. Use [liquid tags](doc:liquid-tags) to create a personalized message for your target audience. 

In this example, the syntax for using a catalog column is shown below:

```liquid Liquid Tag
{{ Catalog.Sample_Catalog.["City Restaurants"] | default:"New York Top Restaurant" }}
```

![1081](https://files.readme.io/cc955ed-catalog_personalization_liquid_message_User_property.png "catalog_personalization_liquid_message_User_property.png")

> 📘 Map Multiple Properties
>
> Create personalization by combining catalog send-time personalization with [constant event property](https://docs.clevertap.com/docs/constant-property#section-advanced-constant-property-with-catalog-personalization).

# Video Tutorial

For further information, you can watch the following video on catalog send-time personalization:

<Embed url="https://www.youtube.com/watch?v=TVltd1_rpG4&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=5" title="Product Demo: Send-Time Personalization" favicon="https://www.youtube.com/s/desktop/404f9720/img/favicon.ico" image="http://i.ytimg.com/vi/TVltd1_rpG4/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=TVltd1_rpG4&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=5" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FTVltd1_rpG4%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DTVltd1_rpG4%26image%3Dhttp%253A%252F%252Fi.ytimg.com%252Fvi%252FTVltd1_rpG4%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
