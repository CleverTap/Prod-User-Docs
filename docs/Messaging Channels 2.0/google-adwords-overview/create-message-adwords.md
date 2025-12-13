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
[block:api-header]
{
  "title": "Create a New Campaign"
}
[/block]
Create a campaign to deliver your Google Adwords message. To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
3. From the *Messaging Channels* list, select **Adwords**. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d0aed96-Campaigns_list_end.png",
        "Campaigns_list_end.png",
        1056,
        519,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
The campaign page displays.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/48b0288-Campaign_Adwords_main.png",
        "Campaign_Adwords_main.png",
        1026,
        851,
        "#fafafb"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
After all the sections have been defined, you can publish the campaign. 


## Start Campaign

The *Start here* section displays the setup information. 

This section has the following parts:
* Start here: Check that the required platforms are integrated and ready for campaigns. 
* Goal: You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve with the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to *How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount? ". 

Click the *Filter* link to create more focused conversions using event properties.  For more information on event properties, see [Events](doc:events) ]. 

Define the conversion period by selecting the *Funnel Conversion Time*. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/00215dc-Push_notification_set_goal_track_conversion.png",
        "Push_notification_set_goal_track_conversion.png",
        919,
        361,
        "#fafafc"
      ]
    }
  ]
}
[/block]
## Define the Who

You must indicate the target audience for your Adwords campaign. You can target your Adwords campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a435b7-SMS_Who.png",
        "SMS_Who.png",
        961,
        766,
        "#f8f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
### Ad-hoc Segment
If you want to create an ad-hoc segment, you can select a type of segment on which to base your Adwords campaign. You can create the target on the basis of past user behavior and/or user properties.


On this basis, you would then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 


### Deliver Adwords Notifications based on Past Behavior (PBS)

You can also target users their past user behavior. For past behavior campaigns, you also have an option to calculate estimated reach to view how many users qualify for the campaign criteria and how many are reachable via Adwords as of now.
[block:image]
{
  "images": [
    {
      "image": [],
      "border": true
    }
  ]
}
[/block]

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send a Adwords notification to English-speaking female users who live in the United States. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5851a66-campaigns_user_properties.png",
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
This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit delivery of the messages to a specified number.

For campaigns based on *Past Behavior Segments*, we randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

  * Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.
   
  * Limit the number of users for each run of a campaign for *Fixed Time* or *Recurring* campaigns.

  * Prevent sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 
[block:callout]
{
  "type": "success",
  "body": "A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.",
  "title": "Safety Check Example"
}
[/block]
## Define the What

Now, you can set up the *What* which is the Adwords campaign content. Click *Go To Editor* to create your message. 

### Adwords Editor 

You can either append an existing audience list **or **create an audience list. Select the user details such as Email or Phone that you want to upload to this list. 

#### **Add qualified users using CleverTap**
[block:callout]
{
  "type": "warning",
  "body": "Check that you have available CRM lists before adding users.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a4622db-Campaign_Adwords_What.png",
        "Campaign_Adwords_What.png",
        1006,
        470,
        "#fbf9fa"
      ]
    }
  ]
}
[/block]
#### **Create a new audience on Google using CleverTap**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/082ca9c-Campaign_Adwords_What_create_audience.png",
        "Campaign_Adwords_What_create_audience.png",
        978,
        647,
        "#fbfafa"
      ],
      "border": true
    }
  ]
}
[/block]









### Message Types

#### By User Property

If you would like to send different message variants to your target audience based on the user properties they possess, this campaign type is your best bet. A good example would be when you want to send a localized update to people based on their preferred language.

Similar to creating A/B test variants, you can use the + button to add multiple variants based on a user property value. In the example below, we have used the *Customer Type* user property so users with different customer type property values will receive corresponding copies of the campaign based on their different levels (Silver, Gold, or Platinum).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aae31bc-campaigns_user_properties.png",
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

Past behavior campaigns can be scheduled to run at a specific time:

  * On a specific date and time.
  * On multiple specified dates and times.
  * Recurring at a periodicity you set.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed19319-Push_notification_editor_when.png",
        "Push_notification_editor_when.png",
        978,
        485,
        "#fbfaf8"
      ]
    }
  ]
}
[/block]
###Delivery preferences
 
Global campaign limits are limits you can apply to determine how many Adwords notifications each app user receives per day. If you want to override these settings for an important campaign, you can click on the *Don’t apply global campaign limits to this campaign* checkbox.

You can also specify *Do Not Disturb* (DND) hours during which notifications from this Adwords campaign are prevented from going out, either by discarding them or delaying delivery to after DND hours complete, such as 9 PM to 9 AM.

Since past behavior campaigns can have scheduled times, you have the option to stop a campaign delivery after a certain cut-off time, or even deliver at the specified time in the user’s timezone. For more information, refer to [Delivery in User’s Timezone](doc:notification-delivery-options).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac20918-Campaign_Adwords_delivery_preferences.png",
        "Campaign_Adwords_delivery_preferences.png",
        777,
        384,
        "#fafbfd"
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
2. View your campaign summary, then click **Publish Campaign**.


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