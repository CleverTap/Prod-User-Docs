---
title: Creating a Push Message
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
  pages:
    - type: link
      title: Delivery Options for Campaigns
      url: https://docs.clevertap.com/docs/timing-the-campaign-delivery
---
Push Notification is a great way for user engagement and product recall. You can choose the target users with our powerful segment filters to deliver your message. We will help you decide the voice of your brand. Your message can be as interesting or as lively you wish. Everything that you need is right here!

Here are some great tips to create a beautiful push message. 
https://clevertap.com/blog/push-notification-best-practices/

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0d135c5-Push_Campaign_Example.png",
        "Push_Campaign_Example.png",
        410,
        574,
        "#b59b93"
      ]
    }
  ]
}
[/block]

[block:embed]
{
  "html": false,
  "url": "https://files.readme.io/2c29710-push1.png",
  "title": null,
  "favicon": null
}
[/block]

#Steps to create a push message

* [Step 1: Create a push campaign](/docs/creating-a-push-message#section-step-1-create-a-push-campaign)
* [Step 2: Select a campaign type](/docs/creating-a-push-message#section-step-2-select-a-campaign-type)
 * [Past behavior segments](/docs/creating-a-push-message#section-filter-by-past-behavior-segments)
 * [Live user segments](/docs/creating-a-push-message#section-filter-by-live-user-segments) 
* [Step 3: Select the Message Frequency and Campaign Delivery](/docs/creating-a-push-message#section-step-3-select-the-campaign-delivery) 
* [Step 4: Select the Users](/docs/creating-a-push-message#section-step-4-select-the-users)
 * Existing segment 
 * Ad-hoc segment 
* [Step 5: Create your Message](docs/creating-a-push-message#section-step-5-create-your-message)
 * Single Message
  * A/B Test
  * Message on User Property
* [Step 5: Choose Control Groups and App Inbox Message](/docs/creating-a-push-message#section-step-5-choose-control-groups-and-app-inbox-message)
 * Control Groups
 * Time to live
* [Step 6: Schedule and Deliver Message](/docs/creating-a-push-message#section-step-6-schedule-and-deliver-message)
  
[block:api-header]
{
  "type": "basic",
  "title": "Step 1: Create a Push Campaign"
}
[/block]
Click **Engage**>**Create Campaign** from the dashboard. Select the **Push** channel. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/daf253d-Campaign_Create_Campaign.png",
        "Campaign_Create_Campaign.png",
        624,
        346,
        "#dbdde3"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Step 2: Select a Campaign Type"
}
[/block]
Choose the campaign type based on the segment. This selection enables the campaign delivery options.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4ac1fd-Campaign_Choose_segments.png",
        "Campaign_Choose_segments.png",
        668,
        398,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
## Filter by Past Behavior Segments
Select your target users by their past behavior. *For example, a customer that has applied a payment offer at least once in the past 30 days*.

##  Filter by Live User Segments
Select your target users by their current behavior. You can then create campaigns triggered by user behavior. *For example, a customer adds a product to the cart but does not buy it within 10 minutes. *We have observed that this is the window within which most users complete transactions; it is a good time to call for action.


[block:api-header]
{
  "title": "Step 3: Select the Campaign Delivery"
}
[/block]
You can decide **when** to deliver a campaign. You can choose to deliver the campaign immediately, or at a later date and time. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a5927a-Campaign_Campaign_Delivery.gif",
        "Campaign_Campaign_Delivery.gif",
        521,
        506,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]
  For campaign delivery options, see [Delivering a Campaign](https://docs.clevertap.com/docs/delivering-a-campaign)


[block:api-header]
{
  "title": "Step 4: Select the Users"
}
[/block]
It is time to select **who** will receive your message. You can select a saved segment of users or create an ad hoc segment. You will see the options to select your users based on the [campaign type ](https://docs.clevertap.com/docs/creating-a-push-message#section-step-2-select-a-campaign-type)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c2205e-Campaigns_Adhoc_Segment.png",
        "Campaigns_Adhoc_Segment.png",
        949,
        734,
        "#fdfdfd"
      ],
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]
You can control the users for your campaign message. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fafc416-Campaign_restrict_delivery.png",
        "Campaign_restrict_delivery.png",
        438,
        193,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]
It is always a good idea to estimate the reach of your campaign before sending it. You can also set a safety limit for a number of users to deliver your campaign. A campaign does not run if the number of qualified users exceeds the safety limit. You can also specify the intended number of users for your campaign. This is a safety precaution so that you do not exceed the number of intended recipients.  

For more on campaigns, reach see deciding the campaign reach.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1e46214-Campaign_campaign_reach.gif",
        "Campaign_campaign_reach.gif",
        436,
        495,
        "#f9f7ef"
      ],
      "border": true
    }
  ]
}
[/block]
#Step 5: Create your Message
You can now create your message! Decide what you want to deliver to your users. A Push message is a great way to communicate instantly with your user. We have some pointers for you to create great [push messages](https://clevertap.com/blog/push-notification-best-practices). 

Use the ‘@’ sign in the title or the message to list variables and create dynamic content. For example, you can enter ‘Hello @Name’ in the title. All users will receive a push message that is personalized with their names. For more information on dynamic content, see [Dynamic Content](doc:dynamic-content).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/121ab6d-Campaign_Single_Message.png",
        "Campaign_Single_Message.png",
        1355,
        357,
        "#f1f3f6"
      ],
      "border": true,
      "sizing": "full",
      "caption": ""
    }
  ]
}
[/block]
Make really personalized and  snappy messages with [Rich Media](/docs/creating-a-rich-message-1) 

#Step 5: Choose Control Groups and App Inbox Message

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b02466-Campaigns_Control_Group.gif",
        "Campaigns_Control_Group.gif",
        1030,
        212,
        "#fcfdfd"
      ],
      "border": true
    }
  ]
}
[/block]
You can **set up **your campaign here. Select the control group. Control groups are groups of randomly selected users who do not receive your campaign message. You can use the control group assigned by the system or create your own custom group. You can use these groups to compare and determine the effectiveness of your campaign. 
[block:callout]
{
  "type": "success",
  "body": "https://clevertap.com/blog/what-is-a-control-group/",
  "title": "Why are control groups important?"
}
[/block]

[block:embed]
{
  "html": false,
  "url": "https://github.com/cleversunil/CleverTap-Documentation/blob/master/Images/Campaigns/MobilePush/Campaign_Android_Push_to_live.mp4",
  "title": "cleversunil/CleverTap-Documentation",
  "favicon": "https://github.githubassets.com/favicon.ico",
  "image": "https://avatars1.githubusercontent.com/u/54270080?s=400&v=4"
}
[/block]



Set up the expiration time for your android push message, label a campaign, enable post action webhooks, and set up a conversion event. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e03588-Campaign_Push_Live_Annotated.png",
        "Campaign_Push_Live_Annotated.png",
        1011,
        503,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]
#Step 6: Schedule and Deliver Message
The overview page shows an overview of your campaign. You can make last-minute edits to this page.


[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Enter a name for your campaign and save it.