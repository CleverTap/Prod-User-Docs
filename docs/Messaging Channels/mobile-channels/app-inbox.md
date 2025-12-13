---
title: App Inbox
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
App Inbox is a messaging channel that lets you deliver rich, individually customized content to your customers. Messages that are sent to App Inbox are saved on the user device. 

<Image title="iPhoneXs Max - black.png" alt={890} src="https://files.readme.io/effe757-iPhoneXs_Max_-_black.png">
  CleverTap's App Inbox
</Image>

## Why do you need App Inbox as a channel?

Push Notification and In-app campaigns are great for grabbing the attention of the app user but they are short-lived. Once swiped off, they lose their ability to engage the customer. If the user is not online or is busy, you lose the opportunity of engagement forever.

App Inbox allows you to send permanent content directly to your app from CleverTap dashboard. Moreover, the inbox messages are targetable to individual segments just like other messaging channels. Which means your inbox can look totally different from the inbox of another user. The possibilities are endless.

## How to get started?

To be able to use CleverTap's App Inbox in your app, you need to go through the following steps:

1. Update CleverTap SDK to version 3.4.0.
2. Follow the steps for integration of App Inbox with your app [here](https://developer.clevertap.com/v1.0/docs/android#section-app-inbox) for Android and [here](https://developer.clevertap.com/v1.0/docs/ios#section-app-inbox) for iOS.

That's it! Now your app is equipped with one of the most powerful channels for engagement. 

## Creating an App Inbox message

## Step 1: Create a Campaign

Click on the + Campaign button

<Image title="Screenshot 2020-06-09 at 4.47.07 PM.png" alt={2878} className="border" border={true} src="https://files.readme.io/1b130c7-Screenshot_2020-06-09_at_4.47.07_PM.png" />

Select App Inbox from the channel selection page.

<Image title="Screenshot 2020-06-10 at 10.13.15 AM.png" alt={2434} className="border" border={true} src="https://files.readme.io/f1ea07a-Screenshot_2020-06-10_at_10.13.15_AM.png" />

Pick the message type, target segment. You can also create an ad-hoc segment. 

Select the deliverability of your message by OS (Android, iOS) and Device (TV, Mobile, Tablet). 

### Select the message reach

You can choose to send your messages to all active devices of the user or the last active device.\
The last active device is the device that has the most recent user event after an app login.  Sending a message to all devices will enhance your message delivery and allow the user to have a unified experience across devices and increase engagement. 

<Image title="Screenshot 2020-06-10 at 10.26.18 AM.png" alt={2802} className="border" border={true} src="https://files.readme.io/a68eef9-Screenshot_2020-06-10_at_10.26.18_AM.png" />

### Select the type of message.

<Image title="Screenshot 2020-06-10 at 10.30.31 AM.png" alt={2800} className="border" border={true} src="https://files.readme.io/964db3f-Screenshot_2020-06-10_at_10.30.31_AM.png" />

## Step 2: Drafting an App Inbox message

<Image title="Screenshot 2020-06-10 at 10.31.04 AM.png" alt={2794} className="border" border={true} src="https://files.readme.io/6cdeae0-Screenshot_2020-06-10_at_10.31.04_AM.png" />

The message builder for App Inbox is where you can create a rich message that you feel will be best to engage your **audience**.

## Message variants

You can select different variants of the message such as Simple Message or [A/B & Multivariate Testing](doc:ab-multivariate-testing).

## Call to Action

App inbox enables various types of CTAs to cater to different use cases for the client. Here are the types:

**1. Click-on-message CTA**: Opens a deeplink when you click anywhere on the message (text or image or both)\
**2. Click-on-link CTA**: Additional links at the bottom that can be colored to attract user's attention.\
**3. Copy to clipboard CTA**: A special type of CTA that enables the user to copy to clipboard. This can be used to enable users to copy discount codes to your products and apply them at the time of checkout.\
**4. Open URL CTA**: A special type of CTA that enables the user to open deeplinks for Android or iOS.\
 **5. Custom key-value pairs CTA**: The key-value pairs send back custom data when a user clicks the App Inbox button. This data is not visible to the user. This feature is available for apps that use Clevertap android SDK version 3.6.1 or above and iOS SDK version 3.7.1 or above. 

<Image title="Campaign_App_Inbox_Message_CTA.png" alt={999} className="border" border={true} src="https://files.readme.io/2a29825-Campaign_App_Inbox_Message_CTA.png" />

## Message tags

You can "tag" an inbox message with one or more comma separated strings. These tags help you identify the messages inside the user's device. Additionally, these tags also help you classify your messages into different tabs in your app.

![224](https://files.readme.io/1b3dd25-Screenshot_2019-01-06_at_4.53.47_PM.png "Screenshot 2019-01-06 at 4.53.47 PM.png")

> 📘 Using message tags effectively
>
> Message tags are an excellent way to engage your users contextually. For example, some of your app users might be interested in "offers" while others in "news updates". You can have 2 separate tabs to categorise your inbox messages into those two buckets. Note that it's not compulsory to have tabs.
>
> You can define the names of the inbox tabs during configuration of App Inbox with your app. The same names should be entered as tags. In case you do not specify any tag, the message will go into the default bucket "All".

## Message templates

App inbox allows 4 message templates:

**1. Simple message**\
A simple message consists of the following elements:\
(a) Title\
(b) Message\
(c) Media (optional): Jpg, gif, mp4 vide and mp3 formats are supported\
(c) Call to action (optional)

<Image title="Screenshot 2019-01-18 at 6.26.52 PM.png" alt={585} border={true} src="https://files.readme.io/d3b5c15-Screenshot_2019-01-18_at_6.26.52_PM.png">
  App Inbox message template: Image with message and CTA
</Image>

**Supported media types**

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
        NA
      </td>

      <td>
        NA
      </td>

      <td>
        5 MB
      </td>
    </tr>
  </tbody>
</Table>

**2. Carousel message with content**\
This is a multi-slide template, where you can draft up to 5 slides containting images with content. This appears in the form of right and left scrolling carousel in the user app. This is a rich template which can be used in situations such as promoting a list of products, or movies that will release this weekend etc.

> 📘 Note
>
> CTAs in carousel messages are click-on-image and there are no provisions for external buttons.

**3. Carousel message without content**\
Similar to the above template, but without title text and messages. 

**4. Message with icon**\
This template can be used when you want to also include an icon in the message. It is similar to the simple message, and it includes an additional icon placeholder

## Step 3: Setup and schedule the campaign

The final step is to configure the setup of the campaign and scheduling it.

## Time to live

App Inbox campaign are by design persisted on the user device for a number of days. You can configure the number of days to keep the message on the user's device by setting the TTL.

![970](https://files.readme.io/2dccbb3-Screenshot_2019-01-06_at_5.26.25_PM.png "Screenshot 2019-01-06 at 5.26.25 PM.png")

The TTL can range between 1 day to 60 days. The message on the user's device stays there for the specified TTL, after which it is automatically removed. You can also have Infinite TTL, which means the message will never be deleted from the user's device. 

> 🚧 Choosing the right TTL
>
> You should choose a TTL that resonates with the purpose of your campaign. Some messages need to stay on the user's device for a longer period (such as coupon codes which are valid for a month) while some should last for a day or two (such as weekend discount offers).

Finally, click on Schedule Campaign. And you are done.

> 📘 Note
>
> Each message stored on the CleverTap platform for App Inbox is accounted for as a user event

## Delivering action based notification instantly

You can trigger an app inbox message instantly for an action. This means that users receive app notifications instantly when they perform an action in the app, instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. The instant app inbox message is not triggered for campaigns with delays or when the app inbox is coupled with a push message.

## Viewing App Inbox Stats

Once the campaign has gone out, you can view its stats by going into “Campaigns” on the CleverTap dashboard and clicking on the App Inbox campaign of interest.

**Qualified:** Number of devices which have an updated SDK enabled for App Inbox\
**Sent:** Number of messages sent to the qualified devices\
**Viewed:** Number of messages viewed by users\
**Clicked:** Number of clicks on the message CTAs
