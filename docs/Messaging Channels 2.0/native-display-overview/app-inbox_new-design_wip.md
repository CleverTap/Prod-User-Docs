---
title: App Inbox_New Design_WIP
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
## Overview

*App Inbox* is a messaging channel that provides the ability to deliver rich, individually customized content to your users. Messages that are sent to *App Inbox* are saved on the user's device. 

![890](https://files.readme.io/effe757-iPhoneXs_Max_-_black.png "iPhoneXs Max - black.png")

# App Inbox As a Channel

Push notification and in-app campaigns are great for grabbing the attention of the app user but they are short-lived. Once swiped off, they lose their ability to engage the customer. If the user is not online or is busy, you lose the opportunity to engage with them forever.

*App Inbox* provides the ability to send permanent content directly to your app from the CleverTap dashboard. Moreover, the inbox messages are targetable to individual segments such as other messaging channels. Your inbox can look different from the inbox of another user; the possibilities are endless.

# How to Get Started

To use CleverTap's *App Inbox* in your app, you must first go through the following steps:

1. Update CleverTap SDK to version 3.4.0.
2. Follow the steps for integration of *App Inbox* with your app. For more information, refer to [iOS App Inbox](https://developer.clevertap.com/v1.0/docs/ios#section-app-inbox) and [Android App Inbox](https://developer.clevertap.com/v1.0/docs/android#section-app-inbox).

Now, your app is equipped with one of the most powerful channels for engagement. 

# Create an App Inbox Message

Get started with creating an app inbox message by using the following steps:

## Create a Campaign

1. Navigate to *Messages* > *Campaigns*.
2. Click on **+ Campaign**.

<Image title="Create an App Inbox Message - new 1.png" alt={1334} className="border" border={true} src="https://files.readme.io/42b642b-Create_an_App_Inbox_Message_-_new_1.png" />

3. Select *App Inbox* from the channel selection page.

<Image title="Create an App Inbox Message - new 2.png" alt={1093} className="border" border={true} src="https://files.readme.io/9e8cac4-Create_an_App_Inbox_Message_-_new_2.png" />

4. Pick the message type and target segment. You can also create an ad-hoc segment. 

5. Select the deliverability of your message by OS (iOS, Android) and device (Mobile, Tablet, TV). 

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign, such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

6. Select the message reach.

You can choose to send your messages to all active devices of the user or the last active device.\
The last active device is the device that has the most recent user event after an app login. Sending a message to all devices enhances your message delivery and increase engagement by providing the user a unified experience across devices. 

<Image title="Screenshot 2020-06-10 at 10.26.18 AM.png" alt={2802} className="border" border={true} src="https://files.readme.io/a68eef9-Screenshot_2020-06-10_at_10.26.18_AM.png" />

7. Select the type of message and template.

<Image title="Screenshot 2020-06-10 at 10.30.31 AM.png" alt={2800} className="border" border={true} src="https://files.readme.io/964db3f-Screenshot_2020-06-10_at_10.30.31_AM.png" />

### Message Variants

The different variants of the message include a *Simple message* or *[A/B & Multivariate Testing](doc:ab-multivariate-testing)*.

### Message Templates

You have the following four choices of message templates:

#### Simple Message 

A simple message consists of the following elements:\
(a) Title.\
(b) Message.\
(c) Media (optional): jpg, gif, mp4 video, and mp3 formats are supported.\
(c) Call to action (optional).

Below is a message template showing an image with a message and a CTA:

<Image title="Screenshot 2019-01-18 at 6.26.52 PM.png" alt={585} className="border" border={true} src="https://files.readme.io/d3b5c15-Screenshot_2019-01-18_at_6.26.52_PM.png" />

#### Supported Media Types

The supported media types include:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Media Type
      </th>

      <th>
        16:9 Aspect Ratio
      </th>

      <th>
        1:1 Aspect Ratio
      </th>

      <th>
        Max Size
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Image (jpg, png, gif)
      </td>

      <td>
        Yes
      </td>

      <td>
        Yes
      </td>

      <td>
        500 KB
      </td>
    </tr>

    <tr>
      <td>
        Video (mp4)
      </td>

      <td>
        Yes
      </td>

      <td>
        Yes
      </td>

      <td>
        50 MB
      </td>
    </tr>

    <tr>
      <td>
        Audio (mp3)
      </td>

      <td>
        N/A
      </td>

      <td>
        N/A
      </td>

      <td>
        5 MB
      </td>
    </tr>
  </tbody>
</Table>

#### Carousel Message with Content

This is a multi-slide template where you can draft up to five slides containing images with content. The carousel in the user app displays in the form of right and left scrolls. This is a rich template that can be used in situations such as, promoting a list of products or movies that will release this weekend.

> 📘 CTAs in Carousel Messages
>
> CTAs in carousel messages are click-on-image without provisions for external buttons.

#### Carousel Message without Content

This template is similar to the one right above but without a title text and messages. 

#### Message with Icon

This template is similar to the simple message with the extra ability to include an additional icon placeholder.

## Draft an App Inbox Message

The message builder for *App Inbox* is where you can create a rich message to engage your targeted audience.

1. Enter your text and message.

<Image title="Screenshot 2020-06-10 at 10.31.04 AM.png" alt={2794} className="border" border={true} src="https://files.readme.io/6cdeae0-Screenshot_2020-06-10_at_10.31.04_AM.png" />

### Call to Action

*App Inbox* enables various types of call to action (CTA) to cater to different use cases for the client.

2. (Optional) Choose from one of the following five types:

* Click-on-message CTA: This opens a deep link when you click anywhere on the message (text or image or both).
* Click-on-link CTA: You can add additional, colored links at the bottom of your message to attract the user's attention. 
* Copy to clipboard CTA: The user can copy text to their clipboard such as, copying discount codes to your products and applying them at the time of checkout.
* Open URL CTA: The user can open deep links for iOS or Android.
* Custom key-value pairs CTA: The key-value pairs send back custom data when a user clicks the *App Inbox* button. This data is not visible to the user. This feature is available for apps that use Clevertap Android SDK version 3.6.1 or above and iOS SDK version 3.7.1 or above. 

<Image title="Campaign_App_Inbox_Message_CTA.png" alt={999} className="border" border={true} src="https://files.readme.io/2a29825-Campaign_App_Inbox_Message_CTA.png" />

### Message Tags

3. (Optional) You can tag an inbox message with one or more comma-separated strings. 

These tags help you identify the messages inside the user's device. Also, these tags help you classify your messages into different tabs in your app.

![224](https://files.readme.io/1b3dd25-Screenshot_2019-01-06_at_4.53.47_PM.png "Screenshot 2019-01-06 at 4.53.47 PM.png")

> 📘 Using Message Tags
>
> Message tags are an excellent way to engage your users contextually. For example, some of your app users might be interested in offers while others in news updates. You can have two separate tabs to categorize your inbox messages into those two buckets. Note that it is not compulsory to have tabs.
>
> You can define the names of the inbox tabs during the configuration of *App Inbox* with your app. The same names should be entered as tags. In case you do not specify any tag, the message will go into the default bucket *All*.

## Set Up and Schedule the Campaign

The final step is to configure the setup of the campaign and schedule it.

### Time to Live (TTL)

*App Inbox* campaigns are by design persisted on the user device for a number of days. 

1. You can configure the number of days (or hours) to keep the message on the user's device by setting the TTL.

![979](https://files.readme.io/90a11b8-Time_to_live_-_new.png "Time to live - new.png")

The TTL can range between 1 day to 60 days. The default value for TTL is 2 days. You can define the TTL for a maximum of 28 days. The message on the user's device stays there for the specified TTL after which it is automatically removed. You can also have *Infinite TTL* which means the message will never be deleted from the user's device. 

> 🚧 Choosing the Right TTL
>
> You should choose a TTL that resonates with the purpose of your campaign. Some messages need to stay on the user's device for a longer period (coupon codes which are valid for a month) while some should last for a day or two (weekend discount offers).

2. As a final step, click on **Schedule notification**.

> 📘 How a Message is Accounted For
>
> Each message stored on the CleverTap platform for *App Inbox* is accounted for as a user event.

# Deliver Action Based Notification Instantly

You can trigger an *App Inbox* message instantly for an action which means that users receive app notifications instantly when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant *App Inbox* message is not triggered for campaigns with delays or when the *App Inbox* is coupled with a push message.

# View App Inbox Stats

Once the campaign has gone out, you can view its stats by:

* Qualified: Number of devices that have an updated SDK enabled for *App Inbox*.
* Sent: Number of messages sent to the qualified devices.
* Viewed: Number of messages viewed by users.
* Clicked: Number of clicks on the message CTAs. 

1. Navigate to *Messages* > *Campaigns* on the CleverTap dashboard.
2. Search by name or ID, or select *App Inbox* under the *Channel* dropdown, then click **Apply**. 
3. Click on the campaign you are looking for.
