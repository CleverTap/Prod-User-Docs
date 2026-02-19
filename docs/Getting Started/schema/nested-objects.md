---
title: Nested Objects
excerpt: >-
  Learn how to view and use Nested Objects in CleverTap to model complex user
  data and build precise segments.
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

Nested Objects allow you to represent rich, structured information about your users, such as subscriptions, insurance policies, or shopping carts, without breaking it into multiple flat properties. Instead of managing dozens of separate fields, you can organize the related details inside a single structured user property.

For more information on implementation, including schema definitions and JSON examples, refer to [Ingesting Nested Objects via CleverTap APIs](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis).

> 📘 Public Beta
>
> This feature is released in Public Beta. For more information about this feature, contact your Customer Success Manager or CleverTap Support.

## Advantages

Nested Objects in CleverTap offers the following advantages:

* **Model complex entities naturally:** Store structured data as it exists in your business system.  
  For example: Save multiple insurance policies owned by a single user under one parent user property.

* **Target users more granularly:** Create segments based on nested attributes.  
  For example: Identify users who have at least one expired subscription plan.

* **Reduce engineering effort:** Send structured JSON payloads directly through CleverTap without flattening.  
  For example: Provide order details, such as product name, quantity, and delivery status, as nested JSON objects.

## Use Cases

Businesses across industries use Nested Objects to personalize engagement:

* **BFSI** Notify customers when key stakeholders, such as policy beneficiaries or account nominees, lack email addresses.
* **E-commerce:** Offer discounts to users with a cart containing at least one product in the _Shoes_ category.
* **Telecom:** Remind subscribers about broadband renewals using plan metadata such as plan name, validity, and renewal date.
* **Media & Entertainment:** Personalize recommendations based on nested metadata such as show titles, genres, or episode preferences saved in the user property.

# Manage Nested Objects Across Platforms

You can view and manage Nested Objects anywhere you access profile and event data.

* **Profile Page:** View structured objects stored in a user’s profile. Each nested user property is shown as a dot-separated field under the User Properties tab on the profile.

* **Segmentation Builder:** Create conditions using nested attributes, such as `Policies.Beneficiaries.Email`. You can combine multiple nested conditions to create granular filters, for example, segmenting users with at least one policy where the premium is overdue or the beneficiary lacks contact information.

The Segmentation Builder in the image shows how nested fields appear within profile data and can be used to create filters.

<Image align="center" alt="Nested Objects in Segment Builder" border={true} caption="Nested Objects in Segment Builder" src="https://files.readme.io/c5aeec5eff621d610e90bf75239fe8ef3369a52cff95bf00997f85291cc005d0-image.png" />

> 📘 Dashboard Limitations with Nested Properties Segments
>
> You may see this message in some areas of the Dashboard:
>
> "_Nested user property queries aren’t supported yet. Choose a segment without nested properties to proceed._"
>
> Support for nested user properties has yet to be provided in areas such as Predictions and Bulletins. To continue, use or create a segment with only standard (non-nested) user properties in such Product areas.

## System Considerations

CleverTap enforces some system limits to maintain performance and stability. The following table lists the limits applied during nested object ingestion to ensure consistent data handling:

| Limit Type                   | Maximum Value                             |
| ---------------------------- | ----------------------------------------- |
| Nesting depth                | 3 levels                                  |
| Payload size                 | 128 KB per profile or event               |
| Object or array keys at root | 5                                         |
| Reserved fields              | `identity`, `email`, and `ts` remain flat |

CleverTap drops extra elements or raises an error if a payload exceeds these limits.

## Best Practices

Follow these practices to maintain data quality:

* Use consistent schema definitions across integrations.
* Send only valid objects; CleverTap drops null or empty objects automatically.
* Monitor object size and array length to stay within system limits.
* Start with a test schema before rolling out to production.
* Use clear attribute names for easier targeting.

# FAQs

### Can I use Nested Objects in SDK, CSV, or SFTP uploads?

Nested Objects are supported through the REST API and SDK. Nested Objects are not supported through CSV or SFTP uploads. For more information, refer to [Ingesting Nested Objects via CleverTap APIs](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis).

### Can I query deeply nested fields in segmentation?

Yes, you can query up to three levels in supported segmentation workflows. Some workflows, such as campaign targeting, may not support nested queries.

### What happens if I exceed the payload size or nesting limits?

CleverTap drops extra elements or converts invalid data into strings. Review the error stream for details.

### Are nested objects included in exports?

No. Nested Objects are not exported through API-based data exports.

### Does this feature affect performance?

When used within the defined limits, Nested Objects do not affect overall system performance. However, queries involving large or deeply nested data structures may take slightly longer to process.
