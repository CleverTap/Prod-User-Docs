---
title: App Tracking Transparency (ATT)
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

Apple announced at the Apple Worldwide Developers Conference (iWWDC) 2020 that starting with iOS 14, all apps will require users to opt into tracking. This means that the *Identifier for Advertisers (IDFA)* can only be tracked for users that explicitly opt-in. 

# IDFA and CleverTap

CleverTap is committed to complying with the new Apple privacy policy.  The CleverTap iOS SDK does not track IDFA. CleverTap’s iOS SDK uses *Identifier for Vendors (IDFV)* to track anonymous users. However,  you can set anything you want as the device identifier.

## Codebase Changes

Starting with the CleverTap SDK version 3.9.0 ( released August 29, 2020), we have removed all code that has the ability to access the device’s advertising identifier (IDFA). The CleverTap SDK versions for iOS lower than version 3.9.0  had the ability to access IDFA, see [tracking with the identifier for advertiser](https://developer.clevertap.com/docs/sdk-changes-for-gdpr-compliance#section-restrict-tracking-with-the-identifier-for-advertiser-idfa). However, these versions still did not capture IDFA automatically unless the customer configured it. 

> 🚧 Important
>
> We recommend upgrading to the latest version of the CleverTap SDK for all customers using versions  3.8.2 and lower.

## User Tracking

There is no impact on the vast majority of our customers because CleverTap iOS SDKs (version 3.9.0 and above) do not use IDFA to track anonymous user activity by default. 

## Install Attribution Events

It is likely that some attribution vendors may stop sending individual attribution events. Check with your attribution vendor to learn more about the possible impact.

# Device Information

CleverTap tracks the following information:

* IDFV
* App version and  build number
* Bundle ID
* iOS OS version
* Device model
* Cellular provider
* Network carrier
* Country code and timezone
* Wi-Fi and Bluetooth information
* Device width, height, and name

The [CleverTap iOS SDK](https://github.com/CleverTap/clevertap-ios-sdk) is open-source and all the device information that is captured is available in our [iOS Github Repository](https://github.com/CleverTap/clevertap-ios-sdk/blob/4c4e6cc0f494419c8f36a926788fa00be07758b9/CleverTapSDK/CTDeviceInfo.m#L29).

# App Store Connect - App Privacy

Starting from December 8, 2020, Apple requires App Privacy Details for all new apps and app updates. Refer to [app store connect](https://help.apple.com/app-store-connect/#/dev1b4647c5b) to understand Apple’s privacy rules and app integrations with multiple third-party SDKs to make the correct decision for your app.

For help with the privacy questionnaire, see [app store connect - app privacy](https://developer.clevertap.com/docs/app-store-connect-app-privacy).

# App Rejection and Recommended Steps

There may be cases when your app may be rejected by *Apple Review* with a note that your app is not compliant with the new privacy guidelines.

Apple privacy guidelines hint at rejecting apps that specifically track users across apps and websites using IDFA. However, we recommend reaching Apple support to understand the exact reason for app rejection. 

If you still need further information, please create a support ticket from the CleverTap dashboard. We would be happy to help you with any further queries.

# FAQs

## Q. What is IDFA?

The *Identifier for Advertisers (IDFA)* is an alphanumeric string that’s unique to each device, and which you only use for advertising. Learn more about IDFA at [Apple Advertising Identifier](https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614151-advertisingidentifier).

## Q. How can I continue to access IDFA?

If you choose to implement ATT, then we recommend that you pass the IDFA value as an event property with a *Custom Event* instead of setting it as a *Custom CleverTap ID*.
