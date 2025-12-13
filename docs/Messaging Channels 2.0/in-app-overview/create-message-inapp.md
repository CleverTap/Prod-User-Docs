---
title: Create Message
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
# Create In-App Messages

The following section shows how to create various types of in-app messages.

## Create a Campaign

1. Navigate to the *Campaigns* page.
2. Click the  **+ Campaign** button.
3. Select *In-App Messages* from the list.

The campaign page displays. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/39118a1-campaign_inapp_main.png",
        "campaign_inapp_main.png",
        1174,
        1043,
        "#fbfafb"
      ]
    }
  ]
}
[/block]

## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:

* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve in the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to *How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount?*. 

Create focused conversions using event properties.  For more information on event properties, see [Events](doc:events). 

Define the conversion period by selecting the *Funnel Conversion Time*. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4fbbeb2-Push_notification_set_goal_track_conversion.png",
        "Push_notification_set_goal_track_conversion.png",
        919,
        361,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]

## Define the Who

You must indicate the target audience for your in-app campaign. You can target your in-app campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1fee47-campaign_Who_Live_segment.png",
        "campaign_Who_Live_segment.png",
        964,
        439,
        "#f6f6fc"
      ],
      "border": true
    }
  ]
}
[/block]
### Ad-hoc Segment
If you want to create an ad-hoc segment, you can select a type of segment on which to base your In-App campaign. You can create the target on the basis of user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered In-App campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes, the golden window within which most users transact on iOS and Android app platforms.

On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 


### Deliver Action Based In-App Notifications
You can trigger an in-app message based on an action. Users receive in-app messages when they perform an action in the app instead of waiting for the next app launch. This makes the message more contextual and increases conversion. The in-app message is not triggered for campaigns with delays.

### Deliver Push Notifications based on Past Behavior (PBS)
You can also target users their past user behavior. 

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send an in-app notification to English-speaking female users who live in the United States. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8bd1896-campaigns_user_properties.png",
        "campaigns_user_properties.png",
        516,
        204,
        "#f7f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
#### User Properties
The following table explains the various property types:
[block:parameters]
{
  "data": {
    "h-2": "Example",
    "h-0": "Property Type",
    "h-1": "Description",
    "0-0": "User Properties",
    "1-0": "Demographics",
    "2-0": "Geography",
    "3-0": "Geography Radius",
    "4-0": "Reachability",
    "5-0": "App Fields",
    "5-1": "App fields filters include *App Version*, *Device Make*, *Device Model*, *OS Version*, and CleverTap *SDK Version*. This information is sent by CleverTap's SDK for each device that has your app which means a single user can have multiple devices associated with their user profile.",
    "4-1": "Reachability filters include *Has email address*, *Has phone number*, *Unsubscribed email*, and *Unsubscribed SMS*.",
    "3-1": "User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides.",
    "2-1": "User's coarse location. Filters include *Country*, *Region*, and *City*. CleverTap's SDK can automatically detect this from the user's IP address.",
    "1-1": "Demographics filters include *Age* and *Gender*.",
    "0-1": "Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.",
    "1-2": "Age = 25 to 40 years\nGender = Female",
    "2-2": "Country = United States\nState = California\nCity = San Francisco",
    "0-2": "Customer Type = Platinum",
    "3-2": "Locations = San Francisco, USA; Paris, France",
    "5-2": "OS Version = 10",
    "4-2": "Unsubscribed email = No"
  },
  "cols": 3,
  "rows": 6
}
[/block]

To know more about what segments can be used, see [Segments](doc:segments).
[block:callout]
{
  "type": "danger",
  "body": "The CleverTap source event property is not supported for web pop-up and mobile in-app campaigns.",
  "title": "Source Event Property"
}
[/block]
### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups](doc:control-groups.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aaa1ae5-Control_Group_Editor.png",
        "Control_Group_Editor.png",
        933,
        549,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
### Targeting Cap

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A relevant use case is a limited offer where you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3aa9241-subset_image.png",
        "subset_image.png",
        406,
        87,
        "#5faeb1"
      ]
    }
  ]
}
[/block]
This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit the delivery of the messages to a specified number.

For triggered campaigns based on live user segments, the users receive a message as they qualify until the total quantity specified has been delivered after which the campaign ends. For campaigns based on the *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

  * Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.
   
  *  Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

  * Prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 
[block:callout]
{
  "type": "success",
  "body": "A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.",
  "title": "Safety Check Example"
}
[/block]
## Define the What

Now, you can set up the *What* which is the In-App campaign content where you have four different options:
* [Single Message](https://docs.clevertap.com/docs/create-message-inapp#section-single-message)
* [AB Test](https://docs.clevertap.com/docs/create-message-inapp#section-a-b-testing)
*  [Split Delivery](https://docs.clevertap.com/docs/create-message-inapp#section-split-delivery)
*  [By User Property](https://docs.clevertap.com/docs/create-message-inapp#section-by-user-property)

Click *Go To Editor* to create your message. The message templates display. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa744c4-Editor_What.png",
        "Editor_What.png",
        1188,
        233,
        "#faf5f7"
      ]
    }
  ]
}
[/block]

### In-App Templates

Select the template and fill in the required details.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bda0354-inapp_message_templates.png",
        "inapp_message_templates.png",
        1206,
        872,
        "#e8e4ec"
      ]
    }
  ]
}
[/block]
###### Image only notifications 
When selecting an *image only* template, you can send a message which only contains an image (without CTAs and/or title and/or message).

###### Content with image notifications
When selecting a *With Content Notification* template, you can send a message with a background image, title, message, and CTAs.

##### Template Aspect Ratio and Image Size Guide 

Follow this guide while creating in-app messages:
[block:parameters]
{
  "data": {
    "h-0": "Canvas Type",
    "h-1": "Canvas Aspect Ratio",
    "h-2": "Sample Image Sizes",
    "0-0": "Cover",
    "0-1": "Full Screen",
    "1-0": "Interstitial",
    "1-1": "1.78:1",
    "2-0": "Half Interstitial",
    "3-0": "Header",
    "4-0": "Footer",
    "5-0": "Native Alert",
    "3-1": "Height: 1:1\nWidth: Fit to screen",
    "4-1": "Height: 1:1\nWidth: Fit to screen",
    "5-1": "Native",
    "5-2": "N/A",
    "h-3": "Image Type Supported",
    "0-3": "Image",
    "1-3": "Image, gif, audio, video",
    "2-3": "Image",
    "3-3": "Logo Image",
    "4-3": "Logo Image",
    "5-3": "N/A",
    "3-2": "N/A",
    "0-2": "Screen Resolution",
    "2-1": "1.30:1",
    "1-2": "16:9",
    "2-2": "4:3",
    "4-2": "N/A"
  },
  "cols": 4,
  "rows": 6
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Image Cropping",
  "body": "Due to the multiple phone sizes on both Android and iOS, we will center crop images if the image does not fit the screen resolution.\n\nWe scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centered in the view."
}
[/block]
###### Sample Images
Below is a list of sample images, such as:
  * [Cover iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover-iPad.jpg)
  * [Cover](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Cover.jpg)
  * [Half Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad-Pro.jpg)
  * [Half Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Interstitial-ipad.jpg)
  * [Half Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Half-Intertitial.jpg)
  * [Interstitial iPad Pro](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad-Pro.jpg)
  * [Interstitial iPad](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Interstitial-iPad.jpg)
  * [Interstitial](https://eu1-dashboard-beepluginuploads3bucket-174u3y07szypz.s3.amazonaws.com/images/ZWW-WWW-WWRZ/Sample-Intertitial.jpg)

### In-App Editor

The In-App Editor has two types of templates, that is, *Basic* and *Custom*. You can use the *Basic* template to create HTML in-apps via a drag-drop method. As an alternative, you can also choose to use the *Custom HTML* option to build your own campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b9254f-campaign_inapp_message_editor.png",
        "campaign_inapp_message_editor.png",
        1206,
        2017,
        "#f4f2f8"
      ],
      "sizing": "80",
      "border": true
    }
  ]
}
[/block]

##### Action buttons 
Mobile in-app enables various types of call-to-action (CTA) to cater to different use cases for clients, such as the following: 

  * Close notification: It closes the notification after a tap. 
  * Open URL: A special type of CTA that enables the user to open a deeplink for Android or iOS.
  * Custom key-value pairs: The key-value pairs send back custom data when a user clicks the in-app button.

##### Select media 
Some things to consider when selecting media with orientation: 

  * Using the background option in in-app, you can choose the media that you want your end-users to see when the app is in portrait mode and in landscape mode.
  * You can choose to add the same image with different form factors or completely different images to give a unique experience on portrait and landscape. 

To [personalize](https://docs.clevertap.com/docs/personalize-message-inapp) the message, click the **Personalization** icon in the editor. All the available personalization options for the channel display.

Click the **Preview & Test **button to preview your message. 
Click **Done**.

[block:callout]
{
  "type": "info",
  "title": "Create Interactive In-Apps",
  "body": "You can create interactive in-app campaigns such as scratch card campaigns and swipe interaction campaigns using JavaScript.\n\nUsing the *Custom HTML* option, you can use Javascript in the HTML and create deep interactive in-app campaigns by adding the JavaScript code along with the HTML code. \n\n*Note*: JavaScript-based campaigns are available on version 3.5.0 and above."
}
[/block]
Enter all the necessary information to create a message. 
[block:callout]
{
  "type": "warning",
  "body": "The character limit for a message in English is 30 for the title and 128 for the message. \nThe character limit for a message in Chinese is 9 for the title and 38 for the message.",
  "title": "Character Limit"
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "Other templates are only supported on SDK versions 3.3.0 and above.\n\nWe do not currently support Typeform because its rendering requires access to local storage which is a security risk. CleverTap SDK WebView does not allow access to local storage.",
  "title": "SDK Version and Typeform"
}
[/block]
### Preview & Test

Once you are all done setting up the content of your campaign in *What* section, you have the option to send a test notification to any CleverTap user profile you have marked as a *Test profile* 
Click the **Preview & Test** button from the message editor to test a message.



### Message Types
You can create the following types of messages:

* [Single Message](https://docs.clevertap.com/docs/create-message-inapp#section-single-message)
* [AB Test](https://docs.clevertap.com/docs/create-message-inapp#section-a-b-testing)
*  [Split Delivery](https://docs.clevertap.com/docs/create-message-inapp#section-split-delivery)
*  [By User Property](https://docs.clevertap.com/docs/create-message-inapp#section-by-user-property)

### Single Message
In this campaign, we send the same message to all users who qualify as your target audience. This message type is best for broadcast messages and for applications that do not vary campaign communication based on differences between properties such as language, geography, or any other user properties.

### A/B Testing
A/B testing helps you understand what type of message copy works best to get clicks from users.

You can test up to three message variants on a test group and the variant that gets the most clicks is declared the winning variant and is automatically sent to the rest of your target audience.

When you create multiple variants for a campaign, you can also auto-copy what is already present in a current variant.


### Split Delivery
With split delivery, you can decide what percentage of your audience receives each message variant for the duration of the campaign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/26bbd1f-app_inbox_split_delivery.png",
        "app_inbox_split_delivery.png",
        582,
        588,
        "#fafbfb"
      ],
      "border": true
    }
  ]
}
[/block]

#### Split Delivery to Past Behavior Segments
For campaigns sent to *Past Behavior Segments* (grouping of users based on what they have done in the past), you have two options: launch the A/B test to a percentage of your target audience or send out an absolute number of messages. In either case, we deliver the variants equally to the test audience.

For example:
  * If you are testing three messages (e.g., Variant A, Variant B, Variant C).
  * Your campaign reach is 2,000,000 users.
  * You choose a test population of 15% of campaign reach (300,000 users).

Then, we send:
  * Variant A to 100,000 users.
  * Variant B to 100,000 users.
  * Variant C to 100,000 users.

After all 300,000 messages have been delivered, we calculate the winning message over this test group based on the number of click-throughs. We then automatically send the winning message to the remainder of your target audience which is 1,700,000 users in this example.

Note that for A/B testing, we ensure there is always an equal number of messages sent for each variant, so there is no bias introduced during the test phase and that the best-performing message is always declared the winner.

#### Split Delivery to Live User Segments 

With campaigns sent to live user segments (triggered campaigns), messages are delivered immediately when a user’s activity matches the criteria you have selected. For example, you can send a message when the user has completed a booking or purchase. Since it is not possible to determine the reach of triggered campaigns upfront, you need to decide how many total messages to send for A/B testing before a winner is declared.
[block:callout]
{
  "type": "success",
  "body": "If you select 500 users as your test audience, we will alternate delivery of Variant A and Variant B as users qualify for the campaign. After a total of messages are sent (Variant A – 250 and Variant B – 250), we then decide the winner based on the number of clicks and continue only with this winning message for the duration of the campaign.",
  "title": "Triggered Campaign Example"
}
[/block]
Deciding on a test audience for A/B testing triggered campaigns requires some estimation. We recommend you check the total messages that were sent for similar triggered campaigns in the past to get a sense of how many users may qualify. If you select a test audience that is too small such as 25 users, you will get a statistically insignificant sample. If your test group size exceeds the total number of users who ultimately qualify for that campaign, then no winner will be declared and each message variant will be alternatively delivered for the duration of the campaign.

### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the *Customer Type* user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6164ab8-campaigns_user_properties.png",
        "campaigns_user_properties.png",
        516,
        204,
        "#f7f8fc"
      ],
      "border": true
    }
  ]
}
[/block]



## Define the When

You can set up the *When* to schedule the campaign start and end using the options below:

Live campaigns can be set up on a specific event:
  * In response to a user event.
  * User event/inaction combination (e.g., abandoned cart scenario).
  * Based on a date event property value of an event (for example,  a reminder for upcoming travel booking).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0637733-Campaign_When_Live_segment.png",
        "Campaign_When_Live_segment.png",
        974,
        476,
        "#faf9f7"
      ]
    }
  ]
}
[/block]

### Set delay
You can choose to send an In-App message immediately (as soon as the user becomes eligible) or select a delay in seconds, minutes, hours, or days. 

###Delivery preferences

You can select the **Do Not Disturb** (DND) option to specify hours during which notifications from this In-App campaign are prevented from going out, either by discarding them or delaying delivery after DND hours complete, such as 9 PM to 9 AM.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9f68729-inapp_delivery_preferences.png",
        "inapp_delivery_preferences.png",
        795,
        385,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recurring Day",
  "body": "If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]

## Publish Campaign

After testing and once you are satisfied with the appearance of your campaign, finalize your campaign with the following steps:
1. Click **Continue** to view your campaign summary. The overview page displays.
2. View your campaign summary, and then click **Publish Campaign**.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b521e92-campaign_Publish.png",
        "campaign_Publish.png",
        1193,
        356,
        "#f0f0fc"
      ],
      "border": true
    }
  ]
}
[/block]