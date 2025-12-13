---
title: Intro to Campaigns
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
CleverTap offers nine different messaging channels enabling you to create engagement strategies to reach your users with a personalized message at the right time.

This page describes the different messaging channels available and the ways to build campaigns in CleverTap.

# Messaging Channels

## Mobile Channels

**[Push](doc:push)**
Push notifications enable you to communicate with your users when they are not in your app. These messages appear on a user's lock screen or in a top/bottom banner, depending on platform and user configuration. 

**[In-App](doc:in-app) **
In-app notifications are pop-up messages that are shown to the user while they are in your app. While push notifications are viewed by the user outside the app, in-app notifications are viewed strictly inside the app. In-app notifications are great to show contextual messages, such as discount offers while the user is within the app, or to communicate with users who have turned off push notifications.

**[SMS](doc:sms)**
SMS notifications enable you to send brief communication to your users, such as one-time passwords to authorize their use on your app, or even links enabling users to download the latest version of your mobile app.

## Web Channels

**[Web Push](doc:web-push)**
Web Push notifications are browser-based messages you can send to your desktop or mobile web users even when they are not currently visiting your website. Web Push notifications operate similar to Mobile Push notifications, except the platform being targeted is the user’s desktop or mobile browser.

**[Web Pop-up](doc:web-pop-ups)**
Web pop-ups are interstitials messages that are displayed to the user while they are on your desktop or mobile website.

**[Web Exit Intent](doc:web-exit-intent) **
Exit Intent are similar to Web Pop-ups, except they are triggered when a user goes to navigate away from your website.

## Additional Channels

**[Email](doc:email) **

In CleverTap, you create the content for the email, specify the target audience, and determine when the campaign will be sent. CleverTap delivers the email messages to the third-party [email service provider](doc:email-partners) of your choosing via a simple configuration in the Dashboard.

**[Webhooks](doc:webhooks)**
CleverTap webhooks enable developers to monitor specific user events and receive push notifications to their server when those events happen. The details of each user who qualify for the campaign are sent to the endpoint, which can be used to export data to a third-party system.

**[Facebook Audience](doc:facebook-audience)**
Facebook Custom Audience is a great way to re-engage with your users outside of your app through ads on Facebook. The Facebook Audience module on the CleverTap dashboard makes it easy to set up Facebook Audience ads for all your users or just specific user segments. These segments can be created on the basis of past user behavior, user properties, or a combination of past user behavior and properties. 

# Build Campaigns

## Campaigns

Within the Engage tab of the CleverTap dashboard, there is a section called Campaigns. This is where you can create new campaigns and see existing ones.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cd73b00-Screenshot_2020-06-09_at_5.07.43_PM.png",
        "Screenshot 2020-06-09 at 5.07.43 PM.png",
        1439,
        714,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]
## Journeys

[Journeys](doc:journeys) is a visual campaign builder that lets you create omnichannel messaging experiences for your users. Journeys is ideal for engaging users across the lifecycle of your app. 

Here are a few sample use cases for Journeys:
  * Build User Onboarding Journeys that engage users over several days or weeks and on different channels as you educate them about your service.
  * Build Promotional Journeys to entice your users to transact at different points of time.
  * Long-running re-engagement campaigns to pull users back into your service if they begin to slip away.

## Clever Campaigns

[Clever Campaigns](doc:clever-campaigns) are pre-built messaging campaigns designed to help you engage and retain users at particularly crucial moments of the user lifecycle:
  * Convert newly acquired users into regular users
  * Encourage existing users to use your app more frequently
  * Run win-back campaigns on users who have uninstalled your app
  * Remind users to upgrade to the latest version of your app

# Campaign Reports

When you click on the Engage tab in the CleverTap dashboard it opens directly to the Campaign Reports table where you can see all your campaigns across every channel in one consolidated view.

Campaign Reports include the channel, delivery status, and key statistics you need to assess and compare performance. 
[block:image]
{
  "images": [
    {
      "image": [],
      "border": true,
      "caption": ""
    }
  ]
}
[/block]
Use quick filters to isolate campaigns of interest and the email report option to deliver a .csv file to your inbox which includes all the information in the table.
 
# Message Labels 

Message Labels allow you to tag campaigns by descriptive names or themes. Once applied, Labels allow you to group your various messaging campaigns such that you can isolate their performance or pinpoint behaviors of users exposed to that collection of messages.

For example, you may create a label called “Onboarding” to identify all the messaging campaigns (across all channels) that are related to onboarding your new users. Or you may create a label entitled “Reengage” to denote campaigns used to bring back users who have dropped off. Similarly you may create a label called “Score Updates” to identify only that class of notifications used to update users on the match.

Create Labels under the Message Settings menu. Apply Labels to individual messaging campaigns while you create them or via the Edit Campaign option in the Campaign Report table.

## Segments and Message Labels

One of the more powerful uses of Labels is in conjunction with the CleverTap Segmentation features. Each time a message is delivered to a user, CleverTap will record a Notification Sent event. As a Property of this event, we include any Label that you have assigned to that messaging campaign. 

Then from our Find People, Create Segment or any Analytics feature, you can isolate users who have been sent a messaging campaign with a particular Label.

For example you may want to see the 30 day retention of users who were sent your Onboarding messages to judge whether these messages were having an impact. After creating a Label entitled “Onboarding” and associating it with all the relevant campaigns, you can Create a new Segment then filter your Cohort analysis for 30 day retention to isolate the performance of just these users.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a7321a1-Screenshot_2020-06-09_at_11.44.17_PM.png",
        "Screenshot 2020-06-09 at 11.44.17 PM.png",
        1338,
        668,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]