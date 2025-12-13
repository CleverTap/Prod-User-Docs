---
title: In-App Campaigns
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
> 🚧 Important Note
>
> To be able to use the template based In-app campaigns, please update your app with the CleverTap SDK version **3.3.0** or above
>
> A/B test does not need an SDK update. You can still send A/B on any SDK (including below 3.3.0) version as long as all the variants are **HTML templates**

## Introduction

As of **October 29, 2018**, we have released a new and improved In-apps with crisper message rendering capability

The capability also allows you to send InApp messages with Images, GIFs, Video and Audio

You can also do A/B testing on your InApps

## How to Guide

#### HTML InApps

**Step 1: Pick the Message Type**\
You can select one of the following message types

1. Single Message
2. A/B Test
3. Message on user property

<Image title="Screen Shot 2018-10-25 at 2.08.33 PM.png" alt={1161} className="border" border={true} src="https://files.readme.io/618b664-Screen_Shot_2018-10-25_at_2.08.33_PM.png" />

**Step 2: Pick the Device**\
You can send the campaign to iOS and/or Android\
You can send the campaign to Mobile and/or Tablet

![1163](https://files.readme.io/ac59c8b-Screen_Shot_2018-10-25_at_2.10.58_PM.png "Screen Shot 2018-10-25 at 2.10.58 PM.png")

**Step 3: Pick the Custom HTML Template**\
Pick the custom HTML template. Note that other templates are supported only on SDK versions 3.3.0 and above

<Image title="Screen Shot 2018-10-29 at 6.09.04 PM.png" alt={674} className="border" border={true} src="https://files.readme.io/1e44e50-Screen_Shot_2018-10-29_at_6.09.04_PM.png" />

**Step 4: Use the 'Builder' option**\
When you pick the 'Builder' option, you will be able to create HTML In-apps via a drag-drop method\
Alternatively, you can also choose to use the 'Custom HTML' option to build your own campaign

<Image title="Screen Shot 2018-10-29 at 6.12.53 PM.png" alt={1162} className="border" border={true} src="https://files.readme.io/9544986-Screen_Shot_2018-10-29_at_6.12.53_PM.png" />

> 📘 Create Interactive InApps
>
> You can create interactive InApp campaigns like scratch card campaigns, swipe interaction campaigns etc. using Javascript.\
> Using the Custom HTML option, you can use Javascript in the HTML and create deep interactive InApp campaigns. Just add the Javascript code along with the HTML code\
> Note: Javascript based campaigns are available on v3.5.0 and above

#### Native InApps

**Step 1: Pick the Message Type**\
You can select one of the following message types

1. Single Message
2. A/B Test
3. Message on user property

**Step 2: Pick the Device**\
You can send the campaign to iOS and/or Android\
You can send the campaign to Mobile and/or Tablet

**Step 3: Pick ANY Template**\
Since your entire user base is on SDK v3.3.0 and above, you can select any one of the below templates or Custom HTML template\
You will have to choose the canvas size and type before you start creating the message. The campaign canvas provided by default are the following

<Image title="Screen Shot 2018-10-25 at 2.16.21 PM.png" alt={1156} className="border" border={true} src="https://files.readme.io/fc872ca-Screen_Shot_2018-10-25_at_2.16.21_PM.png" />

**Step 4: Build the In-app message**

<Image title="Screenshot 2019-05-17 at 9.09.53 AM.png" alt={1322} className="border" border={true} src="https://files.readme.io/1d1f57b-Screenshot_2019-05-17_at_9.09.53_AM.png" />

Step 4a: Personalize Media\
Optionally, you can personalize In-App messages by using the 'personalized media' option. This option helps you to create recommendation In-Apps and also to upload personalized images for each of your user

<Image title="Screenshot 2019-07-03 at 11.04.11 PM.png" alt={643} className="border" border={true} src="https://files.readme.io/4931315-Screenshot_2019-07-03_at_11.04.11_PM.png" />

**Step 5: Pick the media for each orientation**

* Using the background option in InApps, you can choose the media that you want your end users to see when the app is in portrait mode and in landscape mode
* You can choose to add the same image with different form factors or different images altogether to give a unique experience on portrait and landscape

> 🚧 Note
>
> The information provided below is for customers whose entire audience have not updated their app to support the Native InApp capability
>
> Post releasing the app update, there will be users who will be on both old and new app versions. In this case, to send a campaign to both your user base, follow the steps below
>
> * You will NOT be able to use the A/B test and Message on User Property with this option

#### Users on older sdk versions

This will open 2 InApp builders\
**1. New version (SDK 3.3.0 and above)**\
New version will allow you to create the new InApp campaigns

<Image title="Screen Shot 2018-10-25 at 5.12.57 PM.png" alt={1346} className="border" border={true} src="https://files.readme.io/65c710b-Screen_Shot_2018-10-25_at_5.12.57_PM.png" />

**2. Legacy version (SDK 3.2.0 and below)**\
This will open the Legacy InApp builder.

<Image title="Screen Shot 2018-10-25 at 5.16.10 PM.png" alt={1368} className="border" border={true} src="https://files.readme.io/acff800-Screen_Shot_2018-10-25_at_5.16.10_PM.png" />

## Template Aspect Ratio and Image Size Guide

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
        Image type supported
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
        1.78 : 1
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
        1.30 : 1
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
        Height:\
        Width: Fit to screen
      </td>

      <td>
        1:1
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
        Height:\
        Width: Fit to screen
      </td>

      <td>
        1:1
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
        NA
      </td>

      <td>
        NA
      </td>
    </tr>
  </tbody>
</Table>

**Image only template**\
When selecting an *image only* template, you can send a message which only contains only an image (without CTAs and/or Title and/or Message)

**With Content Notification**\
When selecting an *With Content Notification* template, you can send a message with a background image, Title, Message and CTAs

> 📘 Image Cropping
>
> Due to the multiple phone sizes on both Android and iOS, we will **centre crop** images if the image does not fit the screen resolution
>
> We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centred in the view

## FAQs

#### 1. I need to send AB test and MV campaigns. Do I need to update my SDK?

* **No**. MV and AB test does not need SDK update.
* You can create a custom HTML campaign to all your variants.
* You cannot send template campaigns in that case

#### 2. I need to send crisp template campaigns. Do I need to update my SDK?

* **YES**. The new and improved templates work only with SDK v3.3.0 and above
* You cannot send these campaigns on SDK versions below that

#### 3. My partial user base is on old SDK and rest are on new. How do I send them the same campaign?

* To send such a campaign, you will have to pick the '**legacy**' option as per the screenshot below
* This will open 2 variants of the campaign
* The 'new In-app' will send the campaign to users on SDK v3.3.0 and above
* The 'old In-app' will send the campaign to users on SDK v3.2.x and below
* This legacy option will be available till March 31, 2019. It will be deprecated post that

#### 4. When should I use the Custom HTML builder?

* If you have not upgraded to the SDK version 3.3.0 or above, your users will not receive the template based campaigns. In this case you will have to use the custom html builder
* If the templates provided (Cover, Interstitial, etc.) does not meet your business use case, you can create your own HTML 

#### 5. How does my image get cropped?

* We follow the **centre crop**
* We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centred in the view 

#### 6. What size of media can I use?

* Image: Less than 500 kb
* Audio: Less than 5 Mb
* Video: Less than 50 Mb 

## Sample Images

[1. Cover iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover-iPad.jpg)\
[2. Cover](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover.jpg)\
[3. Half Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad-Pro.jpg)\
[4. Half Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad.jpg)\
[5. Half Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Intertitial.jpg)\
[6. Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad-Pro.jpg)\
[7. Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad.jpg)\
[8. Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Intertitial.jpg)

## Deprecation Notice
