---
title: Platform Considerations
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
# Operating System (OS)

The CleverTap SDK supports the following OS:

* Android 4.0 (Ice Cream Sandwich) and above 
* iOS 8.0 and above

# Users

## User profiles

### General

* A User Profile can have a maximum number of 256 custom attribute keys.
* User Profile attribute keys must be of type String and attribute values can be scalar values, i.e. String, Boolean, Integer, Float or a Date object or multi-values (returned as a JSONArray or NSArray/Array).
* Attribute key names are limited to 120 characters in length. 
* Scalar attribute values are limited to 512 characters in length. It means that the key values can have a maximum length of 512 characters. For example, the name of the product, such as **red shoe**.

### Multi-value Properties

* Multi-values property must have unique values for the corresponding attribute key. For example, The attribute key 'Shirt Color' can have the following unique values. 
  1. Red Shirt
  2. Blue Shirt
  3. Green Shirt
* Multi-value property values must be Strings and are limited to 100 items. Excess items will be removed on a FIFO (first-in, first-out) basis. For example, the key 'Shirt Type'  can have the following values:

1. Shirt 1
2. Shirt 2 
3. Shirt 3…upto
4. Shirt 100

* Multi-value property values are limited to 512 characters in length.
* When setting a multi-value property, any existing value is overwritten.
* When adding items to a multi-value property via an API, the API looks for a match. If the property does not exist, a new property with the specified name is created.  If the property is a single value property with a scalar value, the property is promoted to a multi-value property. The current property value is then converted to a string and the new values are added to the values list. For example, the profile for John has the Language property with property value as “English”. You pass new values such as "Spanish" and "German" to the Language property. Now, the Language property will include all values, that is, English, Spanish, and German.
* When removing items from a multi-value property via an API, it checks if the property contains a scalar value. If the property contains a scalar value, it is promoted from a single value property to a multi-value property before the value is removed. If the multi-value property becomes empty after removing the values, then the property is also removed (for the specified profile). For example, the profile for Jane has the Language property with property value as “English”. You remove English from the Language property. Now, the Language property is removed from Jane’s profile.

### Prohibited Characters

The following characters are prohibited in key names:\
percent (%), greater than sign (>), less than sign (\<), exclamation point (!), pipe (|), ampersand (&), dot(.), colon( : ), semi-colon(;), dollar sign($), single quote('), double quote("), backslash( \\ ), and hash(#).

For example, you cannot have a key named “$erialNo>Fifty”.

## Upload User Profiles API

* Calls to the Upload User Profiles API endpoint are synchronous. We recommend making individual calls, waiting for our response, and then make another request. 
* Concurrent requests to the Upload User Profiles API are limited to 15 per account. Requests that exceed the limit will return a 429 HTTP response code.

# Events

## General Constraints

* The maximum number of User Event types per app is 512. While the number may appear limited at first, you can use it with properties and record substantial User Event data. The volume of events submitted per account across those User Event types is practically unlimited.
* For each User Event that is recorded, the maximum number of Event Properties is limited to 256.
* The *Charged* Event supports up to 256 Items values.
* Event property keys must be of type String and property values must be Scalar values, that is, String, Boolean, Integer, Float, or a Date object.
* Prohibited characters for Event names are: percent (%), greater than sign (>), less than sign (\<), exclamation point (!), pipe (|), ampersand (&), dot(.), colon( : ), semi-colon(;), dollar sign($), single quote('), double quote("), and backslash( \\ ).
* User Event keys are limited to 120 characters in length.
* User Event property values are limited to 512 characters in length.
* Event names that differ only by spaces are not considered unique. For instance, `Event Name` and `EventName` are treated as the same event. To avoid this conflict, use separators such as underscores (\_) or hyphens (-). For example, use `Event_Name` or `Event-Name` instead of `EventName`.
* Event names are not case-sensitive, meaning that variations such as `SignUp`, `signup`, and `SIGNUP` are considered as the same event. If a previously discarded event name is reused with a different capitalization, it will still be rejected. To prevent this issue, it is recommended to create a distinct name by adding a character such as an underscore (\_) or a dash (-). For example, instead of using `SignUp`, you could use `SignUp_New`.

## Upload Events API

* Notification Sent, Notification Viewed, Notification Clicked, Notification Delivered, Notification Replied, UTM Visited, App Launched, App Uninstalled, App Version Changed, and Stayed, Reply Sent, Experiment Rendered, Reachable By, Identity Reset, Identity Set, and Identity Error are system event names that are available by default and used across the system. These are reserved event names that cannot be used for custom events.
* Avoid using event property names similar to system event properties. This affects the eligibility for trigger campaigns using the same event property. For instance, *device\_type* is already a system event property used to monitor device-related data. Therefore, use more generic names for custom event properties to avoid potential conflicts with system properties.
* Prohibited characters in event and property names include percent (%), greater than sign (>), less than sign (\<), exclamation point (!), pipe (|), ampersand (&), dot(.),colon( : ), semi-colon(;), dollar sign($), single quote('), double quote("), and backslash( \\ ).
* Calls to the  Upload Events API endpoint are synchronous. We recommend making individual calls, waiting for our response, and then make another request.
* Concurrent requests to the Upload Events API are limited to 15 per account. Requests that exceed the limit will return a 429 HTTP response code.

# Channel-Specific Timeouts and Retries

CleverTap provides multiple engagement channels such as Mobile Push Notifications, SMS, WhatsApp, Email, Webhooks, and more. These channels allow you to collect data or send engagements via your Business Service Providers (BSPs).

When you integrate your BSP's API endpoint with our system, you might expect answers to the following questions:

* What throughput should you expect?
* What is the expected response window?
* How often does CleverTap retry if it receives an error from your service provider's API endpoint?
* What are the various types of errors?

CleverTap offers native integrations with various third-party service providers (BSPs) that operate on different communication channels, such as GupShup (for Email and WhatsApp), Nexmo (for WhatsApp), Sendgrid (for Email), and so on. Each BSP has unique configuration settings for batch processing and timeouts tailored to their specific processing capabilities.

## Best Practices to Follow

For a seamless experience, we recommend you follow the below-mentioned best practices:

* Consider a scenario where your BSP's API experiences a temporary surge in traffic, leading to delayed responses or potential errors. In this case, implementing queuing logic can ensure a smoother process. You enable data processing on your terms by providing CleverTap with an HTTP response code 200 using the POST method. This mitigates the impact of potential fluctuations.
* CleverTap diligently respects HTTP codes and categorizing. For example, HTTP codes that lie in the range of 3xx, 4xx, and 5xx are marked as errors. For more information, refer to [API Errors](https://developer.clevertap.com/docs/api-errors).
* When CleverTap receives an error response due to a temporary technical issue from your service provider, it is important to follow CleverTap's specified [Timeout and Retry Limits](doc:platform-considerations#timeouts-and-retries). Adhering to these limits ensures that necessary retries are performed, ultimately improving the integration reliability.

## Timeouts and Retries

To understand the implemented timeouts and retries that CleverTap respects, refer to the following terms:

* **Channel**: The name of the messaging channel.
* **Timeout (ConnectionRequest)**: The configured API cannot respond within the expected time window.
* **Retry Limits**: The number of times the CleverTap server retries.

For more information about timeouts and retries for each channel, refer to the following:

* [Push Notifications](doc:troubleshooting-faqs-push-notifications#q-what-are-the-timeouts-and-retry-times-for-push-notifications)
* [Web Push](doc:web-push-stats#what-are-the-timeouts-and-retry-limits-for-web-push-notifications)
* [SMS](doc:sms-faqs#q-what-are-the-timeouts-and-retry-times-for-sms)
* [Email](doc:troubleshooting-email#q-what-are-the-timeouts-and-retry-times-for-email)
* [WhatsApp](doc:faqs-1#q-what-are-the-timeouts-and-retry-times-for-whatsapp)
* [Webhook](doc:webhooks-overview#q-what-are-the-timeouts-and-retry-times-for-webhook)
