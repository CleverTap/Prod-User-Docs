---
title: Native Display_Campaign redesign
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

Native Display provides the ability to embed content natively within your app screen without interrupting the app experience. It also provides the ability to change the content of your app dynamically and deliver relevant and contextual content to your users. 

> 👍 Native Display Example
>
> You can create a native display campaign to display recommended content to users on a carousel as soon as they launch the app.

![4012](https://files.readme.io/4d4364e-Campaigns_Ad_view_Example_Image.png "Campaigns_Ad_view_Example_Image.png")

The native display campaign gives you the ability to modify sections of your app or show banner advertisements on live triggers and segmentation. This capability is available for iOS (SDK version 3.7 and above) and Android (SDK version 3.6.2 and above). 

Follow the steps for the integration of native display with your app for [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) and [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios).

# Create a Native Display Campaign

Perform the following steps to create a native display campaign:

1. Click **Native Display** under *Campaigns* on the CleverTap dashboard.
2. Click **+ Campaign**.

<Image title="7809a74-Screenshot_2020-06-09_at_4.47.07_PM.png" alt={2752} className="border" border={true} src="https://files.readme.io/cbc1c6c-7809a74-Screenshot_2020-06-09_at_4.47.07_PM.png" />

3. Select **Native Display** from the *Messaging Channels* list.

<Image title="Screenshot 2020-06-10 at 10.49.12 AM.png" alt={2768} className="border" border={true} src="https://files.readme.io/c05e66b-Screenshot_2020-06-10_at_10.49.12_AM.png" />

## Set up the campaign.

Set a goal with conversion tracking. 

<Image title="Screenshot 2020-06-10 at 10.49.37 AM.png" alt={2492} className="border" border={true} src="https://files.readme.io/15511c4-Screenshot_2020-06-10_at_10.49.37_AM.png" />

## Define the Who

1. Select the target segment. 
2. Configure the Limits and Control group
3. Set the [Constant Event Property](doc:constant-property) .

## Define the What

 Define the message for the campaign.

<Image title="Screenshot 2020-06-10 at 10.52.56 AM.png" alt={2776} className="border" border={true} src="https://files.readme.io/c5f7c20-Screenshot_2020-06-10_at_10.52.56_AM.png" />

1. Select one of the following message types:

* Single message
* [A/B and multivariate test](https://docs.clevertap.com/docs/ab-multivariate-testing) 
* Message on user property

2. Select any or all of the following device types:

* iOS
* Android
* Mobile
* Tablet
* TV (Android)

3. Select the template for the campaign. Check that you have completed the integration steps for [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) and [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios) before you set up a campaign. 

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Template
      </th>

      <th>
        Template Category
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Single banner
      </td>

      <td>
        Media (images, gif, video) only
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Media (images, gif, video) + Text
      </td>
    </tr>

    <tr>
      <td>
        Carousel banners
      </td>

      <td>
        Media (images, gif) only
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Media (images, gif) + Text
      </td>
    </tr>

    <tr>
      <td>
        Banner with icon
      </td>

      <td>
        Media (images, gif, video) only
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Media (images, gif, video) + Text
      </td>
    </tr>

    <tr>
      <td>
        Custom key value
      </td>

      <td>
        Any
      </td>
    </tr>
  </tbody>
</Table>

4. Personalize your content by typing the @ symbol in the *Title* box and other text boxes to list all the available *Profile* and *Event* variables. 
5. Select a variable and provide the default value. For more information, refer to [Personalize Messages](doc:personalize-messages).

<Image title="Screenshot 2020-06-10 at 10.53.38 AM.png" alt={2784} className="border" border={true} src="https://files.readme.io/3dcc0b0-Screenshot_2020-06-10_at_10.53.38_AM.png" />

> 🚧 Maximum Image Sizes
>
> The maximum sizes are as follows:
>
> * Image: 500 KB
> * Audio file: 5 MB
> * Video file: 50 MB
>
> The supported file formats include .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color).

6. Enter the custom key-value pairs. You can enter a value or type the @ symbol in the *Value* box to list specific *Profile* and *Event* properties. The key can have any value. 

For example, if you want to change the carousel images for your users based on their language and favorite food, you can set the custom key-value pairs for this change.

<Image title="Campaign_Ad_View_Custom_Key_Value.png" alt={884} className="border" border={true} src="https://files.readme.io/e5ec4b2-Campaign_Ad_View_Custom_Key_Value.png" />

## Define the When

Currently, the frequency of the campaign is not managed by CleverTap. We send the configured content when the event is triggered. 

\<\<@vishal is this still true ?>>

> 📘 Recurring Day
>
> If you specify a recurring day for a campaign, such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.

Select any live segment or create an ad-hoc live segment. You can filter by any event property for the selected event. You can also filter on any past behavior or user property.

<Image title="Screenshot 2020-06-10 at 11.02.36 AM.png" alt={2792} className="border" border={true} src="https://files.readme.io/bd017ba-Screenshot_2020-06-10_at_11.02.36_AM.png" />

## Publish Campaign

1. Review your campaign and check if everything is in order. 
2. Click the **Publish Campaign** button to schedule and send out your campaign.  

<Image title="Screenshot 2020-06-10 at 11.03.21 AM.png" alt={2778} className="border" border={true} src="https://files.readme.io/48e9afc-Screenshot_2020-06-10_at_11.03.21_AM.png" />

# View Campaign Stats

Open the native display campaign from the campaign list page. The *Notification Clicked* and *Notification Viewed* events are tracked after you send the events and after the integration is complete.

<Image title="Campaigns_Ad_view_report.png" alt={1239} className="border" border={true} src="https://files.readme.io/0c13c9e-Campaigns_Ad_view_report.png" />
