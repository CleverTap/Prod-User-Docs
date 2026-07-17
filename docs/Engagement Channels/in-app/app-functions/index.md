---
title: App Functions
excerpt: Learn how to use App Functions in In-App
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

CleverTap's App Functions enable you to trigger native OS-level prompts, such as requesting app ratings, push notification permissions, or opening URLs. These functions can be embedded in In-App campaigns or triggered as standalone campaigns to engage users contextually and effectively.

<Callout icon="📘" theme="info">
  ### Private Beta

  App Functions is currently released in Private Beta. If you want access to this feature, contact your Customer Success Manager.
</Callout>

# System App Functions

System App Functions enable direct interaction with native device capabilities through OS-level prompts. These prebuilt functions drive user engagement by requesting critical permissions, collecting feedback, or deep-linking users to relevant destinations.

## Request Push Permission

[Request Push Permission](doc:register-for-push) - Prompt users to enable push notifications using a native OS dialog. This function is essential for re-engagement and retention, as push notifications can send timely and personalized messages without opening the app.


<Image src="https://files.readme.io/b711a89-Alert_push_primer.png" alt="Register for Push In-App" align="center" width="smart" border={true} />


## Request App Rating

[Request App Rating](doc:app-rating-primer) - Trigger a native app review prompt integrated with the App Store (iOS) and Google Play (Android). Use this function to encourage satisfied users to leave positive reviews, boosting your app's visibility and credibility.


<Image src="https://files.readme.io/dcc93b8ca32a13a7ba12c0a02d2403342daac6c6431b49084b50c3e271763ae6-ChatGPT_Image_Jun_17_2025_08_11_13_PM.png" alt="App Rating In-App" align="center" width="40% " />


## Open URL

[Open URL](doc:open-url) - Open a secure web page in the default device browser or use deeplinks to direct users to specific sections within your app. This function is ideal for directing users to external content, such as offers and partner pages, or internal In-app content.

# Custom App Functions

Custom App Functions provide the ability to define and register your own native functions that can be triggered from CleverTap In-App campaigns. Unlike System App Functions, which invoke OS-level prompts, Custom App Functions execute logic implemented directly in your app, such as showing a custom UI, navigating to a specific screen, or calling an internal API.

Custom App Functions are defined as either **visual** (which contain UI logic and are included in the In-App queue) or **non-visual** (which are triggered directly without UI logic).

Your development team registers Custom App Functions in your app using the CleverTap SDK. Once registered, these functions become available in the CleverTap dashboard for use in your In-App campaigns.

For SDK implementation details, refer to the platform-specific guides in the following table:

| **Platform** | **Documentation**                                                                                                           |
| ------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Android      | [Android Custom Code In-App Templates](https://developer.clevertap.com/docs/android-custom-code-in-app-templates)           |
| iOS          | [iOS Custom Code In-App Templates](https://developer.clevertap.com/docs/ios-custom-code-in-app-templates)                   |
| React Native | [React Native Custom Code In-App Templates](https://developer.clevertap.com/docs/react-native-custom-code-in-app-templates) |
| Flutter      | [Flutter Custom Code In-App Templates](https://developer.clevertap.com/docs/flutter-custom-code-in-app-templates)           |
| Unity        | [Unity Custom Code In-App Templates](https://developer.clevertap.com/docs/unity-custom-code-in-app-templates)               |

<Callout icon="📘" theme="info">
  ### Developer Resource

  The guides linked above are intended for your development team. They cover SDK-level implementation for registering Custom App Functions in your app.
</Callout>

# Use App Functions

You can use App Functions in your in-app campaign in the following two ways:

- As a _button action_ within a message
- As _standalone campaign_.

## Button Action in In-App Campaign

You can attach an App Function to a button using the [Advanced In-App Builder](doc:advanced-in-app-builder) as follows:

1. Create an In-App campaign.
2. Go to _What > Advanced In-App Builder_.
3. Add a button element to the layout.
4. From the _On Tap_ list, select _App Function_.
5. Select one of the available functions: [Request App Rating](doc:app-rating-primer)  or [Request Push Permission](doc:register-for-push).

This will help you set context by displaying a lead-in message before invoking the system prompt.

## Standalone Campaign

You can use App Functions as stand-alone campaigns. It will trigger the system prompt on the user's device. Follow the steps below:

1. Create an In-App campaign.
2. In the **What** section, select the  _App Functions_ tab.
3. Select a function from the list, such as Request App Rating, Request Push Permission, or Open URL.
4. Define campaign targeting and scheduling as usual.

<Callout icon="📘" theme="info">
  ### Open URL System Prompt

  When an Open URL prompt is triggered from a stand-alone campaign, it opens the link directly in the device’s browser, which may interrupt the in-app experience.
</Callout>

# Event Tracking Matrix

CleverTap tracks user interactions only within its In-App campaigns, such as button clicks and other campaign-driven actions. Due to OS limitations, access to interactions with native system prompts (such as permission popups managed by the device’s operating system) is unavailable.

Refer to the following matrix to understand which events can and cannot be tracked.

| **App Function**            | **Used As**   | **What's Tracked**               | **Notes**                                                                                          |
| --------------------------- | ------------- | -------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Request App Rating**      | Button Action | Viewed, Clicked (on In-App only) | OS controls the actual rating prompt. No way to track if the user completed the rating.            |
|                             | Standalone    | None                             | Interaction tracking is limited by the OS.                                                         |
| **Request Push Permission** | Button Action | Viewed, Clicked (on In-App only) | OS controls the actual push permission prompt. No way to track if the user granted the permission. |
|                             | Standalone    | Viewed                           | You can only track if the In-App prompt was displayed.                                             |
| **Open URL**                | Button Action | Viewed, Clicked                  | Tracks CTA clicks, not the destination URL.                                                        |
|                             | Standalone    | Viewed                           | Tracks the impression, not clicks.                                                                 |

<br />
