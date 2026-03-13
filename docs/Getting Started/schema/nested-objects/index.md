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

* Reduce the number of separate properties in your account
* Keep related data in one place, making it easier to maintain
* Build more scalable segmentation, especially when tracking repeating entities such as subscriptions, policies, cart items, or user preferences
* Enable more precise targeting and personalization based on structured data

## References

* To learn how to use nested objects within user properties, refer to [Nested Objects in User Properties](doc:nested-objects-in-user-properties).
* To understand how to implement nested objects in custom event properties, refer to [Nested Objects in Custom Event Properties](doc:nested-objects-in-custom-event-properties).
* To view SDK-specific implementation details and platform limits for nested objects, refer to [Ingesting Nested Objects using CleverTap SDKs](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-sdks).
* To learn how to send nested objects using the CleverTap API, refer to [Ingesting Nested Objects using CleverTap APIs](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis).

# Advantages

Using nested objects in CleverTap provides the following advantages:

* _Model real-world entities without breaking them into multiple fields_: Store structured data as it exists in your business system.

* _Target users more granularly_: Create segments based on nested attributes.

* _Reduce engineering effort_: Send structured JSON payloads directly through CleverTap without flattening.

# Using Nested Objects

Use nested objects when storing related attributes that belong together logically.

Common examples include the following:

* **User Properties**
  * Profile information
  * Subscriptions
  * Insurance policies
* **Custom Event Properties**
  * Shopping cart content
  * Product line items
  * Transaction details

# Best Practices

Follow these practices to maintain data quality:

* Use consistent schema definitions across integrations
* Send only valid objects
* Monitor payload size and array length
* Use clear attribute names
* Avoid frequent schema changes after implementation
* Avoid deeply nested structures

# FAQs

### Can I use Nested Objects in SDK, CSV, or SFTP uploads?

Nested Objects are supported through the [REST API](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis) and [SDK](https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-sdks). Nested Objects are not supported through CSV or SFTP uploads.

### Can I query deeply nested fields in segmentation?

Yes, you can query up to three levels in supported segmentation workflows.

### What happens if I exceed the payload size or nesting limits?

CleverTap drops extra elements or returns an error if the payload exceeds size or nesting limits.

### Are Nested Objects included in exports?

No. Nested Objects are not included in API-based exports.

### Does this feature affect performance?

Queries on Nested Objects may take longer when segmentation includes multiple nested filters or when nested arrays contain many elements.
