---
title: App Inbox
excerpt: Learn how to drive conversions with App Inbox messages.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

_App Inbox_ is a messaging channel that provides the ability to deliver rich, individually customized content to your users. Messages that are sent to _App Inbox_ are saved on the user's device.


<Image src="https://files.readme.io/9906f6d-image.png" alt="App Inbox Notification" align="center" width="40% " caption="App Inbox Notification" border={true} />


# App Inbox as a Channel

<br />

Push notifications and In-App campaigns are great for grabbing the app user's attention, but they are short-lived. Once swiped off, they lose their ability to engage the customer. If the users are offline or busy, you lose the opportunity to engage with them forever.

App Inbox lets you send lasting content directly to your app from the CleverTap dashboard. Inbox messages are targetable to individual segments, similar to other messaging channels. Your inbox can look different from another user's inbox.

## Inbox Delivery Timing and Campaign Behavior

App Inbox messages are session-based, meaning they are fetched when the app launches, when a new session begins, or when a user pulls and refreshes. In live Push + App Inbox campaigns, the Push notification is delivered instantly, but the Inbox message appears only on the next app launch or session. This can lead to different delivery behaviors depending on the campaign type and trigger source.

Here is what to expect in various scenarios:

| Campaign Type    | Trigger Source | App Inbox Delivery                       |
| ---------------- | -------------- | ---------------------------------------- |
| App Inbox        | SDK            | Delivered in **next session/app launch** |
| App Inbox        | API            | Delivered in **next session/app launch** |
| Push + App Inbox | SDK            | Delivered in **next session/app launch** |
| Push + App Inbox | API            | Delivered in **next session/app launch** |

This behavior is by design and helps ensure Inbox messages are retrieved when the app is active.

<Callout icon="🚧" theme="warn">
  ### Trigger App Inbox Notifications via Journeys Only

  To trigger an App Inbox notification via API, you must configure it through a Journey.<br />Campaigns do not support API-triggered App Inbox notifications.

  For assistance, contact your Customer Success Manager (CSM).
</Callout>

# Examples

## Simple Message

This type of Inbox message consists only of the Title and the Message in the App Inbox. It is an app inbox without the image.<br />You can select this template from the WHAT section of the campaign.


<Image src="https://files.readme.io/99159fa-app_inbox_simple_message_sample.png" alt="484" align="center" width="smart" border={true} />


### Usage Example

Get the app inbox message after you have placed the order stating that the order has been accepted. Example: “Your order has been accepted by the restaurant”.

## Carousel Message with Content

Carousel messages in push notifications display multiple images within a single notification. It can be personalized for the campaign being run. For each carousel image, we can add a new personalized message based on the content. You can also add a link for each carousel message to navigate the users to that particular page.


<Image src="https://files.readme.io/017189e-2a_Carousel_message_with_Content.png" alt="1080" align="center" width="smart" border={true} />


<br />


<Image src="https://files.readme.io/a586da4-2b_Carousel_message_with_Content.png.png" alt="1080" align="center" width="smart" border={true} />


### Usage Example

Along with the advertising images, you can add the related Headline in the message content along and use personalization in these messages

## Carousel Message Without Content

Carousel messages without content can be designed attractively to grab the user's attention and convey your campaign's purpose. You can add your promotional campaign creatives for your products as images here without any text.

## Message with Icon

When you run a message with an icon app inbox campaign, unlike the “carousel with content” feature, you cannot add multiple images. You can just add a single image in the given format, along with any personalized or generic title and text you would like to send to users.


<Image src="https://files.readme.io/5f9780b-Message_with_Icon.png" alt="246" align="center" border={true} />
