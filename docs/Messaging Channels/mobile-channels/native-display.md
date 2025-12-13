---
title: Native Display
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
Apps can increase their interactions per app-visit and conversion rate simply by serving up relevant content. This decreases your bounce rate. You can use Native Display to send content that speaks to your user and add up to 5 points to the existing CTR. 

Native display helps you display content natively within your app without interrupting the app experience. You can dynamically change the content of your app and deliver relevant and contextual content to your users. This gives you the ability to delight your users by displaying the content that they will love. 

For example, you can create a Native Display campaign to display recommended content to users on a carousel as soon as they launch the app.

![4012](https://files.readme.io/4d4364e-Campaigns_Ad_view_Example_Image.png "Campaigns_Ad_view_Example_Image.png")

# Getting Started

The native display campaign gives you the ability to modify sections of your app or show banner advertisements on live triggers and segmentation. This capability is available for iOS (SDK version 3.7 and above) and Android (SDK version 3.6.2 and above). 

Follow the steps for the integration of Native Display with your app for [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) and [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios).

# Creating a Native Display campaign

To start creating a campaign, click "Native Display" under “Campaigns” on the CleverTap dashboard.

## Step 1: Create a Campaign

Click the "+ Campaign" button.

<Image title="Screenshot 2020-06-09 at 4.47.07 PM.png" alt={2878} className="border" border={true} src="https://files.readme.io/7809a74-Screenshot_2020-06-09_at_4.47.07_PM.png" />

Click Native Display from the Channel page.

<Image title="Screenshot 2020-06-10 at 10.49.12 AM.png" alt={2768} className="border" border={true} src="https://files.readme.io/c05e66b-Screenshot_2020-06-10_at_10.49.12_AM.png" />

## Step 2: Define the delivery for the campaign: The When

Select the start and end of the campaign.

<Image title="Screenshot 2020-06-10 at 10.49.37 AM.png" alt={2492} className="border" border={true} src="https://files.readme.io/15511c4-Screenshot_2020-06-10_at_10.49.37_AM.png" />

Currently, the frequency of the campaign is not managed by Clevertap. We send the configured content when the event is triggered. 

## Step 3: Define the users for the campaign: The Who

Select any live segment or create an ad-hoc live segment. You can filter by any event property for the selected event. 

<Image title="Screenshot 2020-06-10 at 11.02.36 AM.png" alt={2792} className="border" border={true} src="https://files.readme.io/bd017ba-Screenshot_2020-06-10_at_11.02.36_AM.png" />

You can also filter on any past behavior or user property

## Step 4: Define the message for the campaign: The What

<Image title="Screenshot 2020-06-10 at 10.52.56 AM.png" alt={2776} className="border" border={true} src="https://files.readme.io/c5f7c20-Screenshot_2020-06-10_at_10.52.56_AM.png" />

### 1: Select the Message Type

You can select one of the following message types:

* Single Message
* [A/B and Multivariate Test](https://docs.clevertap.com/docs/ab-multivariate-testing) 
* Message on user property\`

### 2: Select the OS and Devices

Select the operating system for your campaign, that is, iOS and/or Android.\
Select Mobile and/or Tablet.

### 3: Select the Template

Select the template for the campaign. Check that you have completed the integration steps for [iOS](https://developer.clevertap.com/docs/ios#section-setting-native-display-in-ios) and [Android](https://developer.clevertap.com/docs/android#section-setting-native-display-in-android) before you set up a campaign. 

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Template
      </th>

      <th>
        Template category
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Single banner
      </td>

      <td>
        Media(images, gif, video) only
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Media(images, gif, video) + Text
      </td>
    </tr>

    <tr>
      <td>
        Carousel banners
      </td>

      <td>
        Media(images, gif) only
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Media(images, gif) + Text
      </td>
    </tr>

    <tr>
      <td>
        Banner with icon
      </td>

      <td>
        Media(images, gif, video) only
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Media(images, gif, video) + Text
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

### 4: Personalize your Content

Entering "@" in the Title box and other text boxes will list all the available Profile and Event variables. Select a variable and provide the default value. For more information, see [Personalize Messages](doc:personalize-messages).

<Image title="Screenshot 2020-06-10 at 10.53.38 AM.png" alt={2784} className="border" border={true} src="https://files.readme.io/3dcc0b0-Screenshot_2020-06-10_at_10.53.38_AM.png" />

> 🚧 Max image size - 500KB | Max audio file size - 5MB | Max video file size - 50MB\
> Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color)

### 5: Add Custom Key Value pairs for your app

Enter the custom key value pairs. You can either enter a value or enter the "@" key in the Value box to list all Profile and Event properties. The key can have any value. 

For example, you want to change the carousel images for your users based on their language and favorite food. You can set the custom key value pairs for this change.

<Image title="Campaign_Ad_View_Custom_Key_Value.png" alt={884} className="border" border={true} src="https://files.readme.io/e5ec4b2-Campaign_Ad_View_Custom_Key_Value.png" />

## Step 6: Setup the Campaign

Set up the control group and labels. Set up conversion tracking for events. 

<Image title="Screenshot 2020-06-10 at 10.54.19 AM.png" alt={2778} className="border" border={true} src="https://files.readme.io/9233f68-Screenshot_2020-06-10_at_10.54.19_AM.png" />

# Step 6: Schedule notification

Review your campaign and check if everything is in order. Click the Schedule Notification button to schedule and send out your campaign.  

<Image title="Screenshot 2020-06-10 at 11.03.21 AM.png" alt={2778} className="border" border={true} src="https://files.readme.io/48e9afc-Screenshot_2020-06-10_at_11.03.21_AM.png" />

# View Campaign Stats

Open the Native Display campaign from the campaign list page. The "Notification Clicked" and "Notification Viewed" events are tracked after you send the events and after the integration is complete.

<Image title="Campaigns_Ad_view_report.png" alt={1239} className="border" border={true} src="https://files.readme.io/0c13c9e-Campaigns_Ad_view_report.png" />
