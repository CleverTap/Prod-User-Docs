---
title: Nested Objects
excerpt: >-
  Learn how to view and use Nested Objects in CleverTap to model complex user
  and custom event properties to build precise segments.
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

Nested Objects allow you to group related information in a clean, structured way instead of spreading it across many separate properties. This keeps your data organized, easier to manage, and simpler to understand.

With Nested Objects, you can send rich, structured [user](doc:nested-objects-in-user-properties) and [event](doc:nested-objects-in-custom-event-properties) properties to CleverTap in JSON format. Instead of creating multiple flat properties for related information, you bundle them into a single logical structure.

This approach helps you do the following:

- Reduce the number of separate properties in your account.
- Keep related data in one place to make it easier to maintain.
- Build more scalable segmentation, especially when tracking repeating entities such as subscriptions, policies, cart items, or user preferences.
- Enable more precise targeting and personalization based on structured data.

# Advantages

Using nested objects in CleverTap provides the following advantages:

- _Model real-world entities without breaking them into multiple fields_: Store structured data as it exists in your business system.

- _Target users more granularly_: Create segments based on nested attributes.

- _Reduce engineering effort_: Send structured JSON payloads directly through CleverTap without flattening.

# About Nested Objects

Use nested objects when storing related attributes that logically belong together.

Common examples include the following:

- **User Properties**
  - Profile information
  - Subscriptions
  - Insurance policies and more
- **Custom Event Properties**
  - Shopping cart content
  - Product line items
  - Transaction details and so on

## Nesting Depth and Limits

CleverTap supports up to 3 levels of nesting. The root key is Level 0. Each nested object or array inside the root adds one level of depth.

**User Properties**

The following example shows nesting depth for a user property:

```json
{
  "InsuranceDetails": {
    "Policy": [
      {
        "PolicyID": "POL123",
        "Beneficiary": [
          {
            "Name": "John Doe"
          }
        ]
      }
    ]
  }
}
```

The table below describes the nesting depth for each key in the example above:

| Level | Key                                                          |
| ----- | ------------------------------------------------------------ |
| 0     | `InsuranceDetails`  (Root)                                   |
| 1     | `Policy`                                                     |
| 2     | `Beneficiary`                                                |
| 3     | `Name` inside `Beneficiary`  (Terminal; cannot nest further) |

<br />**Event Properties**

The following example shows nesting depth for an event property:

```json
{
  "Courses_In_Cart": [
    {
      "Id": 10,
      "Courses": [
        {
          "Name": "B.Tech CSE",
          "Sub_Courses": [
            {
              "Name": "Data Structures"
            }
          ]
        }
      ]
    }
  ]
}
```

The table below describes the nesting depth for each key in the example above:

| Level | Key                                                        |
| ----- | ---------------------------------------------------------- |
| 0     | `Courses_In_Cart`(Root)<br />                              |
| 1     | `Courses`                                                  |
| 2     | `Name`, `Sub_Courses`                                      |
| 3     | `Name` inside `Sub_Courses`(Terminal; cannot nest further) |

> 📘 Note
>
> At each level (1, 2, and 3), a maximum of 5 keys can be objects or arrays. The remaining keys must be primitive values such as strings, numbers, or booleans.&#x20;

# Best Practices

Follow these practices to maintain data quality:

- Use consistent schema definitions across integrations
- Send only valid objects
- Monitor payload size and array length
- Use clear attribute names
- Avoid frequent schema changes after implementation
- Avoid deeply nested structures

## References

- To learn how to use nested objects within user properties, refer to [Nested Objects in User Properties](doc:nested-objects-in-user-properties).
- To understand how to implement nested objects in custom event properties, refer to [Nested Objects in Custom Event Properties](doc:nested-objects-in-custom-event-properties).
- To view SDK-specific implementation details and platform limits for nested objects, refer to [Ingesting Nested Objects using CleverTap SDKs](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-sdks).
- To learn how to send nested objects using the CleverTap API, refer to [Ingesting Nested Objects using CleverTap APIs](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis).

# FAQs

### Can I use Nested Objects in SDK, CSV, or SFTP uploads?

Nested Objects are supported through the [REST API](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis) and [SDK](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-sdks). Nested Objects are not supported through CSV or SFTP uploads.

### Can I query deeply nested fields in segmentation?

Yes, you can query up to three levels in supported segmentation workflows.

### What happens if I exceed the payload size or nesting limits?

CleverTap drops extra elements or returns an error if a payload exceeds the size or maximum nesting limits.

### Are Nested Objects included in exports?

No. Nested Objects are not included in API-based exports.

### Does this feature affect performance?

Queries on Nested Objects may take longer when segmentation conditions include multiple nested filters or when nested arrays contain many elements. To maintain performance, avoid using large arrays in frequently queried fields and limit segmentation rules to essential nested attributes.

#

<br />
