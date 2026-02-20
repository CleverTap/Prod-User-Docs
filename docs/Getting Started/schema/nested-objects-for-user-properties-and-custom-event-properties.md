---
title: Nested Objects for User Properties and Custom Event Properties
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

Nested Objects allow you to group related information together in a clean, structured way, instead of spreading it across many separate properties. This keeps your data organized, easier to manage, and simpler to understand.

With Nested Objects, you can send rich, structured user and event properties to CleverTap in [JSON format](https://staging.docs.dev.clevertap.net/docs/ingesting-nested-objects-via-clevertap-apis). Instead of creating multiple flat properties for related information, you bundle them into a single logical structure.

This approach helps you do the following:

* Reduce the number of separate properties in your account
* Keep related data in one place, making it easier to maintain
* Build more scalable segmentation, especially when tracking repeating entities such as subscriptions, policies, cart items, or user preferences
* Enable more precise targeting and personalization based on structured data

The following example shows how nesting levels are structured inside a user profile payload. Each deeper level represents a field nested inside an object or array under `profileData`.

<Image align="center" border={true} caption="Nested Structure for User Properties (profileData)" src="https://files.readme.io/e3fb37bcf77b4cebef146b217e2e67058e93ac56b46a69c54a622f5243591595-image.png" width="60% " />

**Examples**

* _Nested Objects for user properties_: User profile information, such as subscriptions, insurance policies, preferences, and so on.
* _Nested Objects for custom event properties_: Shopping cart contents, product line items, transaction metadata, and more.

For more information on implementation, including JSON examples, refer to [Ingesting Nested Objects via CleverTap APIs](https://staging.docs.dev.clevertap.net/docs/ingesting-nested-objects-via-clevertap-apis).

> 📘 Public Beta
>
> This feature is released in Public Beta. For more information about this feature, contact your Customer Success Manager or CleverTap Support.

## Advantages

When you use Nested Objects in CleverTap, you have the following advantages:

* _Model real-world entities without breaking them into multiple fields_: Store structured data as it exists in your business system. For example, you can store multiple policies under a single Policies property, instead of creating separate fields such as Policy_1_ID, Policy_2_ID, and so on.

* _Target users more granularly_: Create segments based on nested attributes.

* _Reduce engineering effort_: Send structured JSON payloads directly through CleverTap without flattening.

## Use Cases

Businesses across industries use Nested Objects to personalize engagement:

**Nested Objects for User Properties**

* _BFSI_: Notify customers when key stakeholders, such as policy beneficiaries or account nominees, lack email addresses. For example, segment users whose `Policies.Beneficiaries.Email` field is empty.
* _Media & Entertainment_: Target users based on nested viewing preferences, such as preferred genres, languages, or favorite shows, stored directly in profile metadata. This enables a higher Click-Through Rate (CTR) on recommendations and reduces churn by improving personalization accuracy.

**Nested Objects for Custom Event Properties**

* _Healthcare_: Send medication reminders or follow-up test notifications based on nested appointment details. This helps reduce missed follow-ups and improves patient compliance.
* _Travel & Hospitality_: Trigger personalized follow-ups based on booking preferences such as room type, meal plan, or service requests. This improves guest experience and reduces booking cancellations by confirming preferences proactively.

# Nested Objects for User Properties and Custom Event Properties

You can use Nested Objects in both user properties and custom event properties to store structured JSON without flattening fields.

* _For user properties_, Nested Objects help model complex profile-level attributes such as subscriptions, policies, preferences, beneficiaries, and so on.
* _For custom event properties_, Nested Objects allow you to send structured event-level payloads such as cart details, order line items, transaction metadata, policy updates, booking information, and more.

Nested Objects in custom event properties follow the same structure and validation rules as Nested Objects in user properties. Event properties follow the same schema enforcement rules to ensure consistent ingestion and prevent failures.

**Examples**

You can send Nested Objects through CleverTap ingestion APIs so that structured data becomes available for segmentation, personalization, and campaign targeting.

* Sending a user property with multiple insurance policies and nested beneficiaries
* Sending a user property with nested subscription tiers and device preferences
* Sending an event such as Claim Filed with nested claim details (claim amount, policy ID, document status)
* Sending an event such as Order Confirmation with nested cart details and line items
* Sending an event such as Content Watched with nested viewing metadata (genre, duration watched, language, completion status)

This unified support enables consistent modeling of structured data across both profile and event ingestion.

# Use Nested Objects across Platforms

After ingestion, Nested Object fields are available across CleverTap, including user profiles, segmentation filters, and campaign personalization.

* **Profile Page**: View structured objects stored in a user’s profile. Each nested user property is shown as a dot-separated field under the _User Properties_ tab on the profile. For example, `Courses.EnrolledModules.Instructor.Name`.

* **Segmentation Builder**: Create conditions using nested attributes, such as `Policies.Beneficiaries.Email`. You can combine multiple nested conditions to create granular filters. For example, you can segment users who have at least one policy with an overdue premium or a beneficiary missing contact information.

The following image shows how nested fields appear within profile data and can be used to create filters in the Segmentation Builder:

<Image align="center" alt="Nested Objects in Segment Builder" border={true} caption="Nested Objects for User Properties in Segment Builder" src="https://files.readme.io/c5aeec5eff621d610e90bf75239fe8ef3369a52cff95bf00997f85291cc005d0-image.png" />

The following image shows how nested fields appear for event properties and can be used to create filters in the Segmentation Builder:

<Image align="center" border={true} caption="Nested Objects for Event Properties in Segment Builder" src="https://files.readme.io/8cc3b92e6b20288cae3ad3cd23078c8912244e907c56f3d436ce564300cfaff5-image.png" />

* **Liquid Tags**: Use Liquid Tags to personalize Campaign content using attributes stored inside Nested Objects in user properties and custom event properties. You can reference nested fields directly in Push Notifications, Emails, and In-App messages.

The following image shows the Liquid Tags for Nested Objects in user properties:

<Image align="center" border={true} caption="Liquid Tags for Nested Objects in User Properties" src="https://files.readme.io/a8215156ed3174e8601f9df1404ecb707005e7c106d90107491c3619ab050dc9-image.png" width="70% " />

You can use dot notation in Liquid Tags to reference nested fields inside user properties. This allows you to dynamically personalize campaign content, such as addressing a user’s policy type or beneficiary name.

The following image shows the Liquid Tags for Nested Objects in custom event properties:

<Image align="center" border={true} caption="Liquid Tags for Nested Objects in Custom Event Properties" src="https://files.readme.io/e2be66919030b562f73bb7049534d629b0893bb62fe8c87e167e399977335353-image.png" width="70% " />

In the above example, `{{ Event.courses_in_cart[0].courses[0].name | default: "courses in cart" }}` is used. The message dynamically inserts the name of the first course from the first item inside the `courses_in_cart` array when the event triggers. If the value is unavailable, it falls back to the default text `courses in cart`.

This shows how you can access deeply nested event attributes, including arrays within arrays, to personalize real-time messages triggered by custom events.

> 📘 Dashboard Limitations with Nested User Properties in Segments
>
> You may view this message in some areas of the Dashboard:
>
> "_Nested user property queries aren’t supported yet. Choose a segment without nested properties to proceed._"
>
> Nested user property segments are not yet supported in areas such as Predictions and Bulletins. To continue, use or create a segment with only standard (non-nested) user properties in such areas of the product.

## System Considerations

CleverTap enforces some system limits to maintain performance and stability. The following table lists the limits applied during nested object ingestion to ensure consistent data handling:

| Limit Type                                  | Maximum Value                                                                                                               |
| :------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------- |
| Nesting depth                               | 3 levels                                                                                                                    |
| Payload size                                | 32 KB; Applies to the total size of profileData (profile uploads) or evtData (event uploads), including all nested content. |
| Root-level keys (objects or arrays)         | Maximum 5                                                                                                                   |
| Nested elements inside an array             | Maximum 100                                                                                                                 |
| Nested keys inside an object                | Maximum 100                                                                                                                 |
| Reserved fields for user properties         | `identity`, `email`, and `timestamp` remain flat                                                                            |
| Reserved fields for custom event properties | `Charged.Items`                                                                                                             |

## Best Practices

Follow these practices to maintain data quality:

* Use consistent schema definitions across integrations.
* Send only valid objects; CleverTap drops null or empty objects automatically.
* Monitor object size and array length to stay within system limits.
* Use clear attribute names for easier targeting.
* Avoid changing nested key names frequently after implementation.

# FAQs

### Can I use Nested Objects in SDK, CSV, or SFTP uploads?

Nested Objects are supported through the REST API and SDK. Nested Objects are not supported through CSV or SFTP uploads. For more information, refer to [Ingesting Nested Objects via CleverTap APIs](https://staging.docs.dev.clevertap.net/docs/ingesting-nested-objects-via-clevertap-apis).

### Can I query deeply nested fields in segmentation?

Yes, you can query up to three levels in supported segmentation workflows.

### What happens if I exceed the payload size or nesting limits?

CleverTap drops extra elements or returns an error if a payload exceeds size or maximum nesting limits.

### Are Nested Objects included in exports?

No. Nested Objects are not included in API-based exports.

### Does this feature affect performance?

Queries on Nested Objects may take longer when segmentation conditions include multiple nested filters or when nested arrays contain many elements. To maintain performance, avoid using large arrays in frequently queried fields and limit segmentation rules to essential nested attributes.