---
title: Setup and Integration (Core)
excerpt: Integrate CleverTap's SDK for user understanding and retention.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Integration

Integrating the CleverTap SDK with your mobile app or website is the first step to understanding and retaining users while igniting growth.

The Core plan is a self-serve model where we provide support for integration via:

* [Documentation](https://docs.clevertap.com/docs?utm_source=C4S\&utm_medium=doc\&utm_campaign=KB): A product documentation entailing CleverTap overview for users, platform features, and core concepts, and developer documentation covering SDK, API, and Development resources to help you get.
* [Integration Videos](https://eu1.dashboard.clevertap.com/R74-ZWR-R44Z/integration-videos?utm_source=C4S\&utm_medium=doc\&utm_campaign=KB): These videos can be accessed from the _Need Help?_ section to help you tackle integration issues.
* [Integration Checklist](https://eu1.dashboard.clevertap.com/R74-ZWR-R44Z/main?utm_source=C4S\&utm_medium=doc\&utm_campaign=KB): Available on your CleverTap dashboard to guide you through onboarding and setup.
* [Support tickets](https://bit.ly/c4sticket?utm_source=C4S\&utm_medium=doc\&utm_campaign=KB): You will be able to raise support tickets, and the support team will revert back over the email. In case you need a specialized onboarding manager, then you would need to upgrade to an Enterprise plan.

The time to integrate depends on the speed and skills of your software developer. It also depends on the number of metrics you want to track and the Mar-Tech stack of your business. We have customers who have integrated CleverTap in a week. It is recommended that you begin with tracking only the most essential metrics for your business.

# [Data Setup](https://docs.clevertap.com/docs/onboarding-setup-data-management?utm_source=C4S\&utm_medium=doc\&utm_id=KB)

Data setup starts with defining the structure for your data, that is, Schema. Once that is defined and all the required SDKs are integrated, the data flows into the CleverTap dashboard. Read on to learn more about Schema and User Profiles.

## [Schema](https://docs.clevertap.com/docs/schema?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB)

Schema is a framework to maintain, organize, and structure your data. It enforces rules to maintain data integrity so that you can avoid data quality issues later. The schema table stores event and user properties in a pre-defined order to preserve data sanity. Let us quickly overview events and user profiles in the upcoming sections.

## [User Profile](https://developer.clevertap.com/docs/concepts-user-profiles?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB)

A CleverTap user profile has a set of default fields, such as email, phone number, and language. You can also extend the default user profile by adding custom fields that are specific to your business.

A CleverTap user profile consists of three parts:

* **Identifiers**: Each user profile is given a unique CleverTap ID. You can also add other identifiers to recognize the user, including email, phone number, Facebook ID, or your own custom identifier. To learn more about how identity works on the CleverTap dashboard, refer to the [User Profiles](https://developer.clevertap.com/docs/concepts-user-profiles?utm_source=C4S\&utm_medium=doc\&utm_id=KB) documentation.
* **Properties**: User profile properties such as age, gender, device, and location. You can also extend the default user profile by adding custom fields that are specific to your business.


<Image src="https://files.readme.io/b58d5ee-image.png" alt="User Properties" align="center" width="400px" border={true} />


* **Events**: This is a log of actions a user takes in your app, such as a product viewed, a video watched, or an item added to the cart.

### [User Profile Types](https://docs.clevertap.com/docs/user-profiles?utm_source=C4S\&utm_medium=doc\&utm_id=KB#user-profile-types)

The CleverTap user profile type changes automatically depending on the information set in them. A user profile can only belong to one type:

* Anonymous/Guest
* Addressable User Profiles
* Customer

#### [Updating User Profile](https://docs.clevertap.com/docs/user-profiles?utm_source=C4S\&utm_medium=doc\&utm_id=KB#user-profile-types)

You can also upload user properties via CSV, API, and SFTP Import. For more information, refer to the following documentation below.

* [Uploading User Profiles via API](https://developer.clevertap.com/docs/upload-user-profiles-api?utm_source=C4S\&utm_medium=doc\&utm_campaign=KB)
* [Importing data via SFTP](https://developer.clevertap.com/docs/imports-via-sftp?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB)
* [CSV Upload](https://docs.clevertap.com/docs/csv-upload?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB)

## [Events](https://developer.clevertap.com/docs/events?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB)

Events track what individual actions users perform in your app or website. Some examples of events include a user launching an app, viewing a product, listening to a song, sharing a photo, making a purchase, or favoriting an item.

An event could be of four types:

* [System Events](https://docs.clevertap.com/docs/schema?utm_source=C4S\&utm_medium=doc\&utm_id=KB#system-events): These are events tracked automatically after you Integrate our SDK. Some events tracked automatically are app install, app launched, notification sent, notification viewed, etc. Check the complete [list of system events](https://developer.clevertap.com/docs/events?utm_source=C4S\&utm_medium=doc\&utm_id=KB#system-events) in CleverTap.
* [Custom Events](https://docs.clevertap.com/docs/schema?utm_source=C4S\&utm_medium=doc\&utm_id=KB#custom-events): These are events you can define, edit, remove, and so on. These are your app events that you can fully control.
* [Conversion Event](https://docs.clevertap.com/docs/schema?utm_source=C4S\&utm_medium=doc\&utm_id=KB#conversion-event): These events help you track conversion. For example, _charged_ event for an e-commerce app or an _order placed_ for a Food-Tech app or website.
* [Qualifying Event](https://docs.clevertap.com/docs/schema?utm_source=C4S\&utm_medium=doc\&utm_id=KB#section-qualifying-event): This event qualifies users as active if they have performed the event at least once in the defined time.
