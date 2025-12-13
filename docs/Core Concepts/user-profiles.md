---
title: User Profiles
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
# Overview

After you integrate our SDK, we will create a user profile for each person who launches your app or visits your website.

<Image title="a11895e-up1.png" alt={1246} className="border" border={true} src="https://files.readme.io/6192e0c-a11895e-up1.png" />

A CleverTap user profile has a set of default fields, such as email, phone number, and language. You can also extend the default user profile by adding custom fields that are specific to your business. 

For example, if you offer a subscription service in your app, you can create a custom profile field to track what type of plan the user purchased. 

<Image title="up2.png" alt={577} className="border" border={true} src="https://files.readme.io/cc82315-up2.png" />

The benefit of adding more information to a CleverTap user profile is the ability to create a user segment for people that have a specific profile property you define, and then build a campaign to engage with that segment. The second benefit of adding more information to a CleverTap user profile is the ability to personalize your campaign messaging with information. The third benefit is to [personalize your app](https://developer.clevertap.com/docs/app-personalization) based on information from that person's CleverTap user profile.

# User Profile Data Model

A CleverTap user profile consists of three things:

* Identifiers: Each user profile is given a unique CleverTap id. You can also add other identifiers to recognize the user including email, phone number, Facebook ID, Google Plus ID, or your own custom identifier.
* Properties: This is information stored about the user. For example, this might include age, gender, device, and location. You can also extend the default user profile by adding custom fields that are specific to your business. 
* Events: This is a log of actions taken by a user in your app. For example, this might include a product viewed, a video watched, or an item added to cart.

## User Profile Types

The CleverTap user profile type changes automatically depending on the information set in them. A user profile can only belong to one type.

**Anonymous**\
Anonymous profiles do not yet contain uniquely identifiable information about the user.

**Addressable**\
Addressable user profiles are reachable either via email or push-notifications.

**Customer**\
When you record a purchase via the Charged event, that user will be marked as a Customer.

# Updating a User Profile

There are two ways to update a user profile

* Add information to a user profile [through our SDKs](https://developer.clevertap.com/docs/clevertap-sdks).
* Add information to a user profile through our [server-side APIs](https://developer.clevertap.com/docs/user-profile-object).

# System User Properties

System user properties are user properties that are derived from the user information that is received from your application after you integrate our SDK. 

\*\*Age:  If the `birthday` or `DOB`is available as a profile property, CleverTap automatically calculates the age for the user profile. 

<Image title="Test_user_Segments.png" alt={1188} className="border" border={true} src="https://files.readme.io/722dc07-Test_user_Segments.png" />

You can now create and target segments based on user age, such as 'All users between 25 to 30 years'.

![1934](https://files.readme.io/63927fe-Screenshot_2019-10-22_at_6.26.26_PM.png "Screenshot 2019-10-22 at 6.26.26 PM.png")

# Find People

To look at a specific user's profile in the CleverTap dashboard, you can go to the Segment tab and then click on Find People. In the By Identity box, you can search for a user by an identifier, such as email, phone number, or a custom identifier you define.

<Image title="2f1d58a-find1.png" alt={1239} className="border" border={true} src="https://files.readme.io/ba68922-2f1d58a-find1.png" />

On the Find People page, you can also search for users that match a specific set of criteria. This criteria can include actions taken, actions not taken, and profile properties.

<Image title="ef00a21-find2.png" alt={921} className="border" border={true} src="https://files.readme.io/e5e9046-ef00a21-find2.png" />
