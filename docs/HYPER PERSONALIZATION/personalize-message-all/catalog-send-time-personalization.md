---
title: Catalog Send-Time Personalization
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

Catalog send-time personalization allows messages to be personalized with external data pulled from an uploaded catalog when a campaign is sent. Automatically include dynamic information available in the catalog directly in a message, such as product price, product category, available inventory levels, and more.

> 👍 E-commerce App Example
>
> A user adds a laptop to the cart, then exits. By providing additional details in the engagement message such as the image, size, latest price, and specifications of the laptop, the user can be nudged to purchase the item. Using catalog send-time personalization helps keep users engaged in a meaningful way.

After you have uploaded the catalog, you can start using it in a campaign. For more information, refer to [Catalog](https://docs.clevertap.com/docs/catalog).

# Event Property

Follow the steps below to personalize a catalog by event property:

1. Create a [campaign](doc:intro-to-campaigns).

2. Click the **Personalization** link to select a catalog. Once the personalization setup window displays, you can map the required catalog columns to event properties and user properties.

<Image align="center" border={true} caption="Personalize Setup" src="https://files.readme.io/09120c799ef7c0279246565b3d4c1f0d08f397adfde2d607c94712d5898cb45f-image.png" />

3. Click the **Catalog** tab and select the required catalog from the list.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/0f71cd8d16dd6b0cca550839ae50747d9bffa2b2578cb0db943835120776603a-image.png" />

4. Select the event. You can personalize your message based on the event's property values.

<Image align="center" border={true} caption="Map Event to the Catalog Columns" src="https://files.readme.io/ff08127b407a754a7539394ea8fa800e3d61b31f88d86ddb0f0bad6609265733-image.png" />

> 📘 Recent Occurrence
>
> The most recent occurrence of the event is used to select the relevant item from the catalog. If the campaign is a triggered campaign, then the event that triggered the campaign is considered.

5. Select the event property to map to the catalog column. This mapping is important to identify the catalog column that matches the event property. For example, we map _Product Name_, such as a laptop (from the _Viewed_ event), to the _Name_ column in the catalog.

Repeat this step to map more properties.

> 📘 Note
>
> * If required, map multiple properties. Every addition to the mapping is treated as an _and_ condition. For example, map the name, the color, and the brand to personalize the message for the user.
> * Catalog mapping is not supported for array-type items in Charged events.

6. Click **Save** to set up the personalization.

7. Use [liquid tags](doc:liquid-tags) to create a personalized message for your target audience.

In this example, the syntax for using different catalog columns is shown below:

```liquid Liquid Tag
{{ Catalog.["Sample Catalog"].Name | default: "Laptop" }}
{{ Catalog.["Sample Catalog"].Amount | default: "0" }}
```

<Image align="center" border={true} caption="Create Message using Liquid Tags" src="https://files.readme.io/ed694c0c0a2c2bdc9656c823b6240c14e02056936ddf94addac23ef00aeb4455-image.png" />

You can now use the latest amount for the last item added to the cart, such as the laptop.

# User Property

Follow the steps below to personalize a catalog by user property:

1. Create a [campaign](doc:intro-to-campaigns).
2. Click the **Personalization** link to select a catalog. After the personalization setup window displays, you can map the required catalog columns to event properties and user properties.

<Image align="center" border={true} caption="Personalize Setup" src="https://files.readme.io/09120c799ef7c0279246565b3d4c1f0d08f397adfde2d607c94712d5898cb45f-image.png" />

3. Click the **Catalog** tab and select the required catalog from the list.

<Image align="center" border={true} caption="Select Catalog" src="https://files.readme.io/bbd1ad4de67c02a969ccf6a0d6ea9924f1ebcaf1cd7155ac00e04044b49a380e-image.png" />

4. Select the user property to map to the catalog column. For example, you can recommend the top restaurant in New York with rich details about the restaurant from the catalog to a user with the user property _City_ set as New York.

> 📘 Note
>
> If required, map multiple properties. Every addition to the mapping is treated as an _and_ condition. For example, map the city, the top-rated restaurants, and the Chinese restaurants to personalize the message for the user.

<Image align="center" border={true} caption="Map Catalog Column to Profile Property" src="https://files.readme.io/f8c56252142ca44fea14ecf2a8a821b8f406452fafebf4ad8a5fae8a014a25f3-image.png" />

5. Click **Apply** to set up the personalization.
6. Use [liquid tags](doc:liquid-tags) to create a personalized message for your target audience.

In this example, the syntax for using a catalog column is shown below:

```liquid Liquid Tag
{{ Catalog.Sample_Catalog.["City Restaurants"] | default:"New York Top Restaurant" }}
```

<Image align="center" border={true} caption="Create Message using Liquid Tags" src="https://files.readme.io/c8ef0cb252e62f5e798b47dae22fe4fa0cfcd9facee32c32cdd655db41808e69-image.png" />

> 📘 Map Multiple Properties
>
> Create personalization by combining catalog send-time personalization with [constant event property](https://docs.clevertap.com/docs/constant-property#section-advanced-constant-property-with-catalog-personalization).

<br />
