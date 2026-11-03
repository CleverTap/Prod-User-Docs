---
title: Personalize Message
excerpt: >-
  Learn how to personalize webhook message variable values in CleverTap
  campaigns.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

You can personalize the value of each variable in the _Message Payload_ section of the webhook campaign editor for every user, based on their profile properties, event properties, or data from external sources. Personalization is applied per variable field using the inline property picker or Liquid tags, and advanced sources such as Linked Content, Recommendations, and Catalog can be configured to make additional data available at send time.

For more information on user profile properties and events, refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [Events](https://docs.clevertap.com/docs/events).

This document covers the following:

- [Profile and Event Personalization](#profile-and-event-personalization)
- [Liquid Tags](#liquid-tags)
- [Linked Content](#linked-content)
- [Recommendations](#recommendations)
- [Catalog](#catalog)

## Profile and Event Personalization

Each variable value field in the _Message Payload_ section supports inline personalization using the property picker.

To personalize a variable value using a profile or event property:

1. Click **@** in the variable value field you want to personalize. The property picker opens.

   {/* Screenshot: @ property picker open in a variable value field showing categories on the left and properties on the right */}

2. Select a category from the left panel:

   | Category          | Description                                                                                             |
   | ----------------- | ------------------------------------------------------------------------------------------------------- |
   | Profile           | User profile properties such as name, email, phone, and any custom properties you have defined          |
   | Event             | Properties from the qualifying event that triggered the campaign, applicable to Live Behavior campaigns |
   | Linked Content    | Properties mapped from an external API configured under Set up Personalization                          |
   | Catalog Send-Time | Fields from a catalog configured under Set up Personalization                                           |
   | Recommendations   | Recommendation model outputs configured under Set up Personalization                                    |
   | Conditional tags  | Pre-defined contextual variables such as day of week and time of day                                    |
   | Campaign          | Campaign-level identifiers such as Campaign ID                                                          |

3. Select the property from the right panel. CleverTap inserts it into the value field as a Liquid tag, for example `{{ Profile.name | default: "" }}`. The `default` value is sent to users for whom the property is not available on their profile.

You can also type `@` directly into a variable value field to invoke the property picker inline.

## Liquid Tags

Liquid tags give you fine-grained control over variable values by letting you define conditional logic and dynamic formatting.

To insert a Liquid tag, click {[]} in the variable value field. For full syntax, examples, and supported operators, refer to [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags).

Liquid tags are useful for cases such as:

- Displaying different values based on a user property, for example a greeting in the user's preferred language.
- Providing fallback text when a property value is missing.
- Formatting dates, numbers, or strings before they are inserted into the payload.

Webhooks support nested personalization, which lets you reference structured objects such as order details, subscription data, or travel bookings stored in profile or event properties. When using nested personalization, use **Preview & Test** to validate your message before publishing the campaign. For more information, refer to [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags).

<Callout icon="🚧" theme="warn">
  ### Syntax Validation

  CleverTap validates Liquid tag syntax when you click **Done** in the campaign editor. If the syntax is invalid, an error displays and the campaign cannot proceed until the issue is resolved. Use **Preview & Test** to catch errors before clicking **Done**.
</Callout>

## Linked Content

Linked Content lets you personalize variable values with real-time data from an external API called at send time. For example, you can pull in a user's current account balance, a live product price, or weather data for the user's location.

To use Linked Content:

1. In the campaign editor, click **Set up Personalization** in the top bar.
2. Under the _Linked Content_ tab, select the API from which you want to fetch data. Mapped properties from that API are pre-populated.
3. Click **Apply**.
4. In the variable value field, click **@** and select **Linked Content** from the category list to insert a mapped property.

For more information on setting up and managing Linked Content APIs, refer to [Linked Content](https://docs.clevertap.com/docs/linked-content).

## Recommendations

Recommendations let you surface personalized content for each user, such as products, articles, or offers based on their behavior and affinity, directly in a variable value field.

To use Recommendations:

1. In the campaign editor, click **Set up Personalization** in the top bar.
2. Under the _Recommendations_ tab, configure the recommendation model.
3. Click **Apply**.
4. In the variable value field, click **@** and select **Recommendations** from the category list to insert a recommendation property.

For more information on creating and managing recommendation models, refer to [Recommendations](https://docs.clevertap.com/docs/recommendations).

## Catalog

Catalog Send-Time Personalization lets you pull dynamic product or inventory data into variable values at the time of send, so the values reflect current information rather than values fixed at campaign creation.

To use Catalog Send-Time Personalization:

1. In the campaign editor, click **Set up Personalization** in the top bar.
2. Under the _Catalog_ tab, configure the catalog and the fields you want to use.
3. Click **Apply**.
4. In the variable value field, click **@** and select **Catalog Send-Time** from the category list to insert a catalog field.

For more information on uploading and managing catalogs, refer to [Catalogs](https://docs.clevertap.com/docs/catalog).
