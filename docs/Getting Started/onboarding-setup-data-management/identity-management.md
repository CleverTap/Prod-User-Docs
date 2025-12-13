---
title: Identity Management
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
@DOCS: FELICE WILL PUBLISH LATER ONCE ALL SUB-SECTIONS HAVE BEEN APPROVED. 

## Overview

Identity management is how CleverTap attributes properties and events performed on your application to a specific user. It is the process of defining your users' information on the CleverTap dashboard by providing each user a unique identifier. 

![848](https://files.readme.io/2c7163e-image3.png "image3.png")

# User Identity

A user identity is a primary key that you define in your database to identify your user as unique.

> 👍 User Identity Examples
>
> Some user identity examples include:
>
> * Customer ID
> * Order ID
> * Merchant ID 
> * Phone number
> * Email

CleverTap supports the following types of identity:

* CleverTap ID: CleverTap's own primary key to identify users
* Email ID: [abc@xyz.tld](mailto:abc@xyz.tld)
* Phone number: +&lt;area code&gt;&lt;phone number&gt;
* Identity: Any other unique identifiers such as, orderID, userID, or shopID

![1999](https://files.readme.io/1318579-User_Identity_Profile.png "User_Identity_Profile.png")

## Identify Logged-in Users

Depending on your business, the best practice is to identify your logged-in users by using a primary key that you already use in your database as an identity on CleverTap.

> 👍 Common Use Case Examples with a Primary Key
>
> Each business may want to choose a different primary key as a unique identity, such as:
>
> * An over-the-top (OTT) platform can use an email.
> * A payment gateway can use a phone number.

Creating an internal user ID is also a recommended best practice. A good way to implement identity creation on login is to embed the onUserLogin method provided by the CleverTap SDK.

## Email ID

The email ID is a preferred way of identifying users as the trends of digitalization have let users sign up to popular email services and have a primary identification always enabled. On CleverTap, the email needs to be unique to be set as an identity.

> 👍 Common Use Case Examples with an Email ID
>
> Some use cases for an email as an identity include:
>
> * Video streaming services.
> * Various subscription-based services such as, online groceries or music streaming.

To pass an email to CleverTap as an identity, you need to ensure the *Email* field is present in the onUserLogin method. 

The following is a web example:
## Mobile Phone Number

The accessibility of smartphones has enabled businesses to use the mobile phone number as a valid form of identity, so users can sign up for any product this way and have an easy, onboarding experience. 

> 👍 Common Use Case Examples with a Mobile Phone Number
>
> Some use cases for mobile phone number as an identity include:
>
> * Any productivity apps as the users want to experience the actual app functionality easier and quicker.
> * Fintech services using mobile phone numbers for quicker login and signup.

To pass a mobile phone number to CleverTap as an identity, you need to ensure the *Phone* field is present in the onUserLogin method and the area code is specified in the value for the phone. 

The following is a web example:






























































































































































































































































































































































































































































































































































































































































































## Identity

> 🚧 Limitations with Emails and Mobile Phone Numbers
>
> The problem that arises with email and mobile phone numbers as identities is that they have to be unique for all the users in your user base. This means that the functionality to update an email or a phone number on apps is not a viable use case to implement emails or mobile phone numbers as identities because if the older identity is used by a different user, that data would be still associated with the first user’s profile.

To avoid the scenario above, you can use a third form of identity management using the *Identity* field as an identifier for the user profiles. This provides the capability to add any unique string used as a primary key on your systems as an identifier. Since this information is generally abstracted from the end user, this is highly recommended to use for the identity management scenario due to its immutable nature.


> 👍 Common Use Case Examples with a Unique Identity
>
> Some use cases for a unique identity as an identity include:
>
> * Identity can be used in place of an email or a mobile phone number where the user can change the latter two.
> * An identity field is viable and effective where the customers need to identify the user profiles based on their own identity which is common to some third-party platforms as well.

To pass an identity field to CleverTap as an identity, you need to ensure the *Identity* field is present in the onUserLogin method. 

The following is a web example:

@PM: IS JAVASCRIPT CORRECT?

















































































































































































































































































































































































































































































































































































































































































## Identity Reset

Identity reset is a mechanism provided to demerge the user profiles. Demerge is the segregation of two different unique identities from one CleverTap ID. Identity reset is recommended when there is a need to demerge a badly merged profile.

To reset an identity, perform the following steps:

1. From the dashboard, navigate to *Segments* > *Find People*.
2. Click on the appropriate profile once you have identified it.
3. Click **Reset Identities**.

This option contains a number associated with it indicating the number of identities associated with that profile.

![1999](https://files.readme.io/382378e-Reset_identities.png "Reset_identities.png")

## How Do You Want CleverTap to Handle Identified Profiles?

Depending on your business case, you can handle the identified profiles as per your requirements on the CleverTap dashboard.

![932](https://files.readme.io/54af1bb-How_Do_You_Want_CleverTap_to_Handle_Identified_Profiles.png "How Do You Want CleverTap to Handle Identified Profiles.png")

### Do Not Merge Identifiers on the Same Sevice 


This method is recommended to set up identity management on CleverTap. The OnUserLogin method used in development with any signup or login method ensures that even if multiple users perform the signup or login operation on the same device, their individual user data would be stored on separate user profiles. 

This is the ideal and recommended scenario as it ensures the correct encapsulation of user data and helps in tracking events much more efficiently. 

To configure this setting, perform the following steps:

1. From the dashboard, navigate to *Settings* > *User Identity*.
2. Under *How do you want CleverTap to handle identified profiles?*, select *Do not merge identifiers on the same device*. 

### Allow Multiple Identities to Merge on the Same Device 

If your business only requires a singular profile to track all the multiple users logging in through the same device, then this method of user identity management can be used.

To implement this method, the ProfilePush method is used in development with any signup or login method. This ensures that even if multiple users perform the signup or login operation on the same device, their individual user data would be stored on the same user profile which was created using the first user’s operations.

This is not an ideal and recommended scenario as it restricts multiple individual users to have individual profiles. This type of use case should be implemented in scenarios such as a booking desk application registering all the users onto a singular desk profile. 

To configure this setting, perform the following steps:

1. From the dashboard, navigate to *Settings* > *User Identity*.
2. Under *How do you want CleverTap to handle identified profiles?*, select *Allow multiple identities to merge on the same device*. 

## Do You Want to Use AdID and IDFA as Device Identifiers?

The Advertising ID (AdID) is a unique, user-resettable ID for advertising provided by Google Play services. Similarly, Identifier for Advertisers (IDFA) is a unique code that Apple assigns to each iPhone for third parties to track users for ad targeting.

![766](https://files.readme.io/f1e3b52-Do_You_Want_to_Use_ADID_and_IDFA_as_Device_Identifiers.png "Do You Want to Use ADID and IDFA as Device Identifiers.png")

### Yes, I Will Use AdID and IDFA as Device Identifiers


Conforming to the latest privacy policies designed by Apple, the latest CleverTap iOS SDK does not capture IDFA or other device IDs, such as IMEI. The Identifier for Vendors (IDFV) is used to create a CleverTap ID which is disclosed under *Other Data*.

The Google AdID and IDFV can be captured by the CleverTap SDK during integration. 

The current GDPR policies do not allow the usage of the Google AdID and the IDFA in tracking user data. So if your app conforms with the GDPR policies, it is not recommended to use the Google AdID or the IDFA as device identifiers.

If your use case and region are not governed by the GDPR policies, you can use the Google AdID to capture the user info.

When you use the Google Ad ID for creating a Clevertap ID/Profile, they display as: \_\_g&lt;google ad id without special characters&gt;. For iOS, this displays as: `-g<IDFA>`

### No, I Will Use a Custom Device Identifier

By default, the CleverTap Android SDK will not use the Google Ad ID to generate CleverTap IDs. In this case, you can set your own custom identifiers or let the CleverTap ID handle the ID creation to create user profiles.

If the app needs to be GDPR compliant or if you do not want to use the Google AdID, you can use the \_\_<Random Alphanumeric String> notation to generate the CleverTap ID. 

When creating the CleverTap ID using the custom identifier, the following format is: 

* \_\_h&lt;unique id&gt; for Android. 
* -h&lt;unique id&gt; for iOS.

### I Want to Use IDFV

The Identifier for Vendors (IDFV) is a code assigned to all apps by one developer and is shared across all apps by that developer on your device. The IDFV value is the same for apps from the same developer running on the same iOS-enabled device. This displays as: -`v<IDFV>`

The CleverTap iOS SDK does not track IDFA. CleverTap’s iOS SDK uses IDFV to track anonymous users from the SDK version 3.9 above.

You can use IDFV to collect data of users from CleverTap SDK versions 3.9 and above.

# Identity Generation 

{user.PER PM HARSH ON THE FOLLOWING SENTENCE: This language/title is inaccurate.  We don't “generate” identities. }
CleverTap uses two methods to generate identities for users, thus creating user profiles through: 

* OnUserLogin 
* ProfilePush			\
  &#x9;			&#x9;

## OnUserLogin

{user.DOCS NOTE: SUNIL (OR PM) TO ADVISE ON MISSING INFO IN THIS SECTION }
OnUserLogin is a CleverTap method to differentiate multiple users on the same device.
> 👍 OnUserLogin Example
>
> User A logs in from a single device then logs out. Now, user B logs in on the same device. OnUserLogin helps you to track events performed by A and B separately.

## ProfilePush

\<\< DOCS NOTE: SUNIL (OR PM) TO ADVISE ON MISSING INFO IN THIS SECTION >>\
ProfilePush is the CleverTap method of updating the user properties. For instance, when you want to update the user property customer type from Silver to Gold status.

> 👍 ProfilePush Example
>
> User A has upgraded their subscription from a free account to a paid account, you will then use ProfilePush in this situation to update the subscription status in the user property.

## Recommendation

It is recommended to use the OnUserLogin method whenever the users sign up or log in to your app. At any log-in possibility, the OnUserLogin works.

Contrary to that, ProfilePush works the best when you want to update the user properties of a logged-in user.

## Steps for Profile Creation

This section covers the steps for profile creation for Android and iOS.

### Android

After the integration of CleverTap SDK, two types of scenarios occur:

* If the app does not need to be GDPR compliant, use the Google Ad ID to create a CleverTap ID/Profile. This displays as: `__g<google ad id>`
* If the app needs to be GDPR compliant, use `__<Random Alphanumeric String>`

In addition, you have the option to set up a custom CleverTap ID which displays as: `__h<unique id>`

After the custom setup, an anonymous user profile will be created tracking all the user activity until a user signs up or logs in. Then, the following occurs:

* On signup or login, the identity is passed from the user end to CleverTap.
* This identity can be an email, a mobile phone number, or any other unique identifier.
* A mapping between the CleverTap ID and this identity ensures that the registered user’s profile gets merged with that of the user’s anonymous profile.
* This merged profile is now called *Addressed Profile*.

### iOS

After the integration of CleverTap SDK, two types of scenarios occur:

* If the app does not need to be GDPR compliant, create the CleverTap ID on the basis of IDFA which displays as: -g&lt;IDFA&gt;
* If the app needs to be GDPR compliant, use -v<Random Alphanumeric String>

In addition, you have the option to set up a custom CleverTap ID which displays as: -h<unique id>
After the custom setup, an anonymous user profile will be created tracking all the user activity until a user signs up or logs in. Then, the following occurs:

* On signup or login, the identity is passed from the user end to CleverTap.
* This identity can be an email, a mobile phone number, or a unique identity.
* A mapping between the CleverTap ID and this identity ensures that the registered user’s profile gets merged with that of the user’s anonymous profile.
* This merged profile is now called *Addressed Profile*.

![1999](https://files.readme.io/e3c8842-image4.png "image4.png")