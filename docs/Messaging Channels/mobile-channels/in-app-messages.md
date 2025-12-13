---
title: In-App Messages_Campaign_redesign_WIP
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
# Overview

As of October 29, 2018, we have released a new and improved in-apps with crisper message rendering capability which provides the capability to send in-app messages with images, GIFs, video, and audio. You can also do A/B testing on your in-apps.\
\<\<@vishal do we still have customers using the old in-app? should we continue showing this information?>>

> 🚧 SDK Version
>
> To use the template-based in-app campaigns, update your app with the CleverTap SDK version 3.3.0 or above.
>
> A/B test does not need an SDK update. You can still send an A/B test on any SDK (including version below 3.3.0) version as long as all the variants are HTML templates.

# Create In-App Messages

The following section shows how to create various types of in-app messages.

## Create a Campaign

1. Navigate to *Campaigns* page.
2. Click on **+ Campaign**.
3. Select *In-App Messages* from the *Messaging Channels* list.
4. Set a goal and conversion tracking for your message. 

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign such as the 7th of each month, the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

5. You must indicate the target audience for your mobile in-app campaign. You can select the type of segment and define the criteria. 

![1316](https://files.readme.io/b7a048c-campaign_who_segment.png "campaign_who_segment.png")

\<\<@vishal, what happens to saved segments in this case ? do they appear in the list ?>>

6. Set the date and time and delivery preferences from the *When* section.

Once done, follow the steps from one of the sections below:

## HTML In-Apps 

This section shows the steps for HTML in-app campaigns. Use the *What* section to create your message.

1. Select one of the following message types: 

* Single message
* A/B test
* Message on user property

2. Click *Go To Editor*.

<Image title="In-app Messages.png" alt={1230} className="border" border={true} src="https://files.readme.io/9d976c0-In-app_Messages.png" />

2. Select any or all of the following device types:

* iOS
* Android
* Mobile 
* Tablet
* TV (Android) 

![1230](https://files.readme.io/9769e08-In-app_Messages.png "In-app Messages.png")

3. Select the *Custom HTML* template. 

<Image title="In-app Messages - Custom HTML.png" alt={837} className="border" border={true} src="https://files.readme.io/33ebd64-In-app_Messages_-_Custom_HTML.png" />

> 🚧 SDK Version and Typeform
>
> Other templates are only supported on SDK versions 3.3.0 and above.
>
> We do not currently support Typeform because its rendering requires access to local storage which is a security risk. CleverTap SDK WebView does not allow access to local storage.

> ❗️ Source Event Property
>
> The CleverTap source event property is not supported for web pop-up and mobile in-app campaigns.

4. Choose the builder option to create HTML in-apps via a drag-drop method. As an alternative, you can also choose to use the *Custom HTML* option to build your own campaign.

<Image title="In-app Messages - Builder.png" alt={1369} className="border" border={true} src="https://files.readme.io/23cf7b8-In-app_Messages_-_Builder.png" />

> 📘 Create Interactive In-Apps
>
> You can create interactive in-app campaigns such as scratch card campaigns and swipe interaction campaigns using JavaScript.
>
> Using the *Custom HTML* option, you can use Javascript in the HTML and create deep interactive in-app campaigns by adding the JavaScript code along with the HTML code. 
>
> *Note*: JavaScript-based campaigns are available on version 3.5.0 and above.

## Native In-Apps

This section shows the steps for native in-app campaigns.

1. Select one of the following message types:

* Single message
* A/B test
* Message on user property

2. Select any or all of the following device types:

* iOS
* Android
* Mobile 
* Tablet
* TV (Android) 

3. Select any template.

Since your entire user base is on SDK version 3.3.0 and above, you can select any of the templates or *Custom HTML* template.

You must choose the canvas size and type before you start creating the message. The campaign canvas provided by default are the following:

<Image title="In-app Messages - Any template.png" alt={1226} className="border" border={true} src="https://files.readme.io/d2c48b1-In-app_Messages_-_Any_template.png" />

4. Build the in-app message by entering all the necessary information.

<Image title="In-app Messages - Build a message.png" alt={1379} className="border" border={true} src="https://files.readme.io/1741219-In-app_Messages_-_Build_a_message.png" />

> 🚧 Character Limit
>
> The character limit for a message in English is 30 for the title and 128 for the message.\
> The character limit for a message in Chinese is 9 for the title and 38 for the message.

4a. Select *Personalize media* to personalize in-app messages. 

This option helps to create recommendations in-apps and to upload personalized images for each of your users.

<Image title="Screenshot 2019-07-03 at 11.04.11 PM.png" alt={643} className="border" border={true} src="https://files.readme.io/4931315-Screenshot_2019-07-03_at_11.04.11_PM.png" />

4b. Select *On click action*.

Mobile in-app enables various types of call-to-action (CTA) to cater to different use cases for clients, such as the following: 

* Close notification: It closes the notification after a tap. 
* Open URL: A special type of CTA that enables the user to open a deeplink for Android or iOS.
* Custom key-value pairs: The key-value pairs send back custom data when a user clicks the in-app button. This data is not visible to the user. This feature is available for apps that use Clevertap Android SDK version 3.6.1 or above and iOS SDK version 3.7.1 or above.

![663](https://files.readme.io/3b5a2a2-Campaign_Inapp_CTA.png "Campaign_Inapp_CTA.png")

5. Pick the media for each orientation while noting:

* Using the background option in in-app, you can choose the media that you want your end-users to see when the app is in portrait mode and in landscape mode.
* You can choose to add the same image with different form factors or completely different images to give a unique experience on portrait and landscape. 

## Users on New and Old SDK Versions

> 🚧 Users on Both Old and New App Versions
>
> The information provided below is for customers whose entire audience has not updated their app to support the native in-app capability.
>
> Post releasing the app update, there will be users who will be on both old and new app versions. In this case, to send a campaign to both your user base, follow the steps below.
>
> You will *not* be able to use the A/B test and message on user property with this option.

Depending on your SDK version, use one of the following steps to create in-app campaigns:

### New Version (SDK 3.3.0 and Above)

This section shows the steps for in-app campaigns with the new SDK.

1. Select *New in-app* if you are using a new version.

<Image title="In-app Messages - Latest SDK.png" alt={1348} className="border" border={true} src="https://files.readme.io/dd0bfa8-In-app_Messages_-_Latest_SDK.png" />

### Legacy Version (SDK 3.2.0 and Below)

This section shows the steps for in-app campaigns with the old SDK.

1. Select *Legacy In-app* if you are using an old SDK version.

<Image title="In-app Messages - Legacy In-app.png" alt={1342} className="border" border={true} src="https://files.readme.io/ba383ba-In-app_Messages_-_Legacy_In-app.png" />

# Template Aspect Ratio and Image Size Guide

Follow this guide while creating in-app messages:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Canvas Type
      </th>

      <th>
        Canvas Aspect Ratio
      </th>

      <th>
        Sample Image Sizes
      </th>

      <th>
        Image Type Supported
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Cover
      </td>

      <td>
        Full Screen
      </td>

      <td>
        Screen Resolution
      </td>

      <td>
        Image
      </td>
    </tr>

    <tr>
      <td>
        Interstitial
      </td>

      <td>
        1.78:1
      </td>

      <td>
        16:9
      </td>

      <td>
        Image, gif, audio, video
      </td>
    </tr>

    <tr>
      <td>
        Half Interstitial
      </td>

      <td>
        1.30:1
      </td>

      <td>
        4:3
      </td>

      <td>
        Image
      </td>
    </tr>

    <tr>
      <td>
        Header
      </td>

      <td>
        Height: 1:1\
        Width: Fit to screen
      </td>

      <td>
        N/A
      </td>

      <td>
        Logo Image
      </td>
    </tr>

    <tr>
      <td>
        Footer
      </td>

      <td>
        Height: 1:1\
        Width: Fit to screen
      </td>

      <td>
        N/A
      </td>

      <td>
        Logo Image
      </td>
    </tr>

    <tr>
      <td>
        Native Alert
      </td>

      <td>
        Native
      </td>

      <td>
        N/A
      </td>

      <td>
        N/A
      </td>
    </tr>
  </tbody>
</Table>

## Image Only Template 

When selecting an *image only* template, you can send a message which only contains an image (without CTAs and/or title and/or message).

## With Content Notification

When selecting a *With Content Notification* template, you can send a message with a background image, title, message, and CTAs.

> 📘 Image Cropping
>
> Due to the multiple phone sizes on both Android and iOS, we will center crop images if the image does not fit the screen resolution.
>
> We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centered in the view.

# FAQs 

## I need to send an A/B test and multivariant campaigns. Do I need to update my SDK?

* No, you do not need an SDK update.
* You can create a custom HTML campaign for all your variants.
* You cannot send template campaigns in that case.

## I need to send crisp template campaigns. Do I need to update my SDK?

* Yes, the new and improved templates only work with SDK version 3.3.0 and above.
* You cannot send these campaigns on SDK versions below that.

## My partial user base is on an old SDK and the rest are on new. How do I send them the same campaign?

* To send a campaign, you will have to pick the legacy option.
* This will open two variants of the campaign.
* The *New In-App* will send the campaign to users on SDK version 3.3.0 and above.
* The *Legacy In-App* will send the campaign to users on SDK version 3.2.x and below.
* This legacy option will be available until March 31, 2019, and will be deprecated after this date.

## When should I use the custom HTML builder?

* If you have not upgraded to the SDK version 3.3.0 or above, your users will not receive the template-based campaigns. In this case, you will have to use the custom HTML builder.
* If the templates provided (Cover, Interstitial, etc.) do not meet your business use case, you can create your own HTML.

## How does my image get cropped?

* We follow the center crop.
* We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centered in the view. 

## What size of media can I use?

* Image: Less than 500 kb.
* Audio: Less than 5 Mb.
* Video: Less than 50 Mb.

## What is the character limit for my message?

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Language
      </th>

      <th>
        Title
      </th>

      <th>
        Message
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        English
      </td>

      <td>
        30
      </td>

      <td>
        128
      </td>
    </tr>

    <tr>
      <td>
        Chinese
      </td>

      <td>
        9
      </td>

      <td>
        38
      </td>
    </tr>
  </tbody>
</Table>

## What is the Time to Live (TTL) for my message?

The default value for TTL is two days. You can define the TTL for a maximum of 28 days. 

# Sample Images

Below is a list of sample images, such as:

* [Cover iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover-iPad.jpg)
* [Cover](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover.jpg)
* [Half Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad-Pro.jpg)
* [Half Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad.jpg)
* [Half Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Intertitial.jpg)
* [Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad-Pro.jpg)
* [Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad.jpg)
* [Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Intertitial.jpg)
