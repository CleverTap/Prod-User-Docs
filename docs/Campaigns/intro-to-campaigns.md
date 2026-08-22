---
title: Campaign Overview
excerpt: Understand how to engage with users through Campaigns.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Marketing campaigns promote products through different types of media. Campaigns are designed with different goals in mind, including building a brand image, introducing a new product, and increasing sales of an existing product. Defining a campaign's goal usually influences the required marketing efforts and identifies the most effective media channels for targeting a particular audience. Read on to learn more about CleverTap campaigns.

# Messaging Channels

CleverTap offers different messaging channels for creating engagement strategies to help users with a personalized message at the right time. Click **+ Campaigns** and select the messaging channels from the list of available channels in CleverTap. These messaging channels can be broadly classified into four categories: Mobile Channels, Web Channels, Remarketing Channels, and Additional Channels.

## Mobile Channels

The mobile channels include:

### [Push](doc:push)

Push notifications enable you to communicate with your users when they are not in your app. Depending on the platform and user configuration, these messages appear on a user's lock screen or in a top/bottom banner.

### [In-App Messages](doc:in-app)

In-app messages are pop-up messages that are shown to the user while they are in your app. While the user views push notifications outside the app, in-app notifications are viewed inside the app.  
In-app notifications are great for showing contextual messages, such as discount offers while the user is within the app or communicating with users who have turned off push notifications.

### [App Inbox](doc:app-inbox)

App Inbox is a messaging channel that provides the ability to deliver rich, individually customized content to your users. Messages sent to the App Inbox get saved on the user's device.

### [Native Display](doc:native-display)

Native Display provides the ability to embed content natively within your app screen without interrupting the app experience. It also provides the ability to change your app's content dynamically and deliver relevant and contextual content to your users.

## Web Channels

The web channels include:

### [Web Push](doc:web-push)

Web Push notifications are browser-based messages you can send to your desktop or mobile web users even if they are not currently visiting your website.

### [Web Pop-up](doc:web-pop-ups)

Web pop-ups are interstitial messages displayed to the user while they are on the desktop or mobile website.

### [Web Exit Intent](doc:web-exit-intent-overview)

Exit Intent messages are similar to Web Pop-ups, except they are triggered when a user navigates away from your website.

## Remarketing Channels

The remarketing channels include:

### [Facebook Audiences](doc:facebook-audiences)

Facebook Custom Audience is a great way to re-engage your users outside of your app through ads on Facebook. The Facebook Audience module on the CleverTap Dashboard makes it easy to set up Facebook Audience ads for all your users or specific user segments. Base these segments on past user behavior, user properties, or a combination of past user behavior and properties.

### [Google Ads](doc:google-adwords)

Remarketing with Google Ads is a great way to re-engage with users outside your app or website via the Google Ads network.

## Additional Channels

### [Email](doc:email)

In CleverTap, you create the email content, specify the target audience, and determine when the campaign activates. CleverTap delivers the email messages to the third-party email service provider of your choice via a simple configuration in the Dashboard.

### [Webhooks](doc:webhooks-overview)

CleverTap webhooks enable developers to monitor specific user events and receive data on their servers directly in the JSON format when those events occur. Each qualified user's details are sent to the endpoint, which exports data to a third-party system.

### [SMS](doc:sms)

SMS notifications enable you to send short communications to your users, such as reactivating users who have uninstalled the app or providing links to download the latest version of the mobile app.

# Campaigns

You can create new campaigns and view existing ones under **Campaigns**, which is available in the left pane. Once a campaign is published, you can stop it but cannot pause it.

## Campaigns Operations

You can perform different actions on the campaigns from the _All Campaigns_ page. Each operation is discussed briefly in the sections to follow.

### Filter Campaigns

You can quickly search your campaigns by applying the required filters. To do so:

1. Navigate to _Messages_ > _Campaigns_ from the CleverTap dashboard. The _All Campaigns_ page opens.
2. Click the ![](https://files.readme.io/ac0ed6a-Filter_icon.png) icon. The Filter Campaigns window opens on the right side of the screen.

<Image align="center" alt="Filter Campaigns" border={true} caption="Filter Campaigns" title="Click the Filter icon to filter campaigns" src="https://files.readme.io/fbf5087fbe1294fd42ffd5cb82fd3af9a700ac6acf9d276225ad5365e6fc93ce-Filter_Campaigns.png" />

3. Select from the following filters and click **Apply**:
   * **Channel**: Filters based on the type of messaging channel used. The following are the available options: Email, SMS, Push Notifications, Mobile In-app, Web, Audiences, Web Push, Webhooks, Google Ads,  App Inbox, WhatsApp, Partner, Native Display, and Web Native Display.
   * **Type**: Filters based on the type of campaign. The campaign can be a Single Message, A/B Test, or Message on user property type of campaign.
   * **Status**: Filters campaign based on the current status of the campaign. The following are the possible statuses: Scheduled, Running, Stopped, Completed, Draft, Awaiting Next Run, Rejected and Approval Pending.
   * **Created by:** Filters based on the email ID of the person who created the campaign.
   * **Label**: Filters based on the labels assigned to the campaigns.
   * **Delivery**: Filters based on the delivery type of the campaign. The following are the available options: One Time, Inaction, Action, On a date/time, Recurring, API, and Multiple Date.

<Image align="center" alt="Apply Campaign Filters" border={true} caption="Apply Campaign Filters" src="https://files.readme.io/80bdbc6-Apply_Campaign_Filter.gif" />

All the campaigns that meet the criteria are listed under the _All Campaigns_ page. Also, you can save the filter by clicking the _Save Filter_ link.

You can also apply quick filters from the top of the _All Campaigns_ page.

### Archive Campaigns

Archiving campaigns helps to keep your CleverTap account organized and clutter-free, making it easy to find and view the campaigns you want. To do so:

1. Navigate to _Messages_ > _Campaigns_ from the CleverTap dashboard. The _All Campaigns_ page opens.
2. Select the campaigns you may want to archive and click the ![](https://files.readme.io/b46b84b-Archive_icon.png) icon.
3. Click **Save** to archive the selected campaigns or click **Cancel** to undo the action.

<Image align="center" alt="Archive Selected Campaigns" border={true} caption="Archive Selected Campaigns" src="https://files.readme.io/65f3a7d89e189d529f8e9017160947cf6ca85a38901927ebc060e9984b47aa9a-Archive_Campaigns.gif" />

> 📘 Note
>
> Toggle the _Archive Campaigns_ option to veiw the archived campaigns.

### Stop Campaigns

You may want to stop a particular campaign after monitoring and evaluating its efficacy. To do so:

1. Navigate to _Messages_ > _Campaigns_ from the CleverTap dashboard. The _All Campaigns_ page opens.
2. Select the running campaigns you may want to stop and click the ![](https://files.readme.io/c2fcde8-Stop_icon.png) icon.

<Image align="center" alt="Stop Selected Campaigns" border={true} caption="Stop Selected Campaigns" src="https://files.readme.io/e4ba1596611e5ec12b7ce1d2ba899ca33952b7a70206a9e9f9a193427fa73e1b-Stop_Campaigns.png" />

3. Click **Save** to archive the selected campaigns or click **Cancel** to undo the action.

### Clone Campaign

Cloning a campaign helps to create a new campaign from an existing campaign with minor or no modifications. To do so:

1. Go to _Messages_ > _Campaigns_ from the CleverTap dashboard. The _All Campaigns_ page opens.
2. Select the campaign you want to clone, then click the <Image border={true} width="22px" src="https://files.readme.io/68006daf054f34d82693eef99039c1ffb82ec3f1257a1619bd9cce24d06522fe-Ellipses_icon.png" className="border" /> icon.
3. Choose where you want to copy the campaign:
   * Current project to clone within the same project
   * Another project to clone it to a different project
4. If you select Another project, choose the destination project. The cloned campaign is created as a draft in the selected project. For more information, refer to [Copy Engagements Across Projects](doc:copy-engagements-across-projects).

   <Image align="center" border={true} caption="Clone Selected Campaign Across Projects" src="https://files.readme.io/e600c0de36fadc80582e25ec52318fabaaa564a5c154bd32b10feef4aef3d301-Clone_Campaign_Across_Projects.gif" />

<Callout icon="📘" theme="info">
  #### Note

  You can copy your engagements to one or more projects. CleverTap prefixes the name of the copied engagement with Clone of to help you identify duplicates. You can rename the engagement later.
</Callout>

5. Click **Clone**. You can choose to open the cloned engagement in a new tab. If the destination project does not include required events, segments, or user properties, CleverTap flags them for review. You can fix them directly in the destination project and publish them.

## Campaign Reports

Selecting _Campaigns_ from the CleverTap Dashboard opens the Campaign Reports table where you can see all your campaigns across every channel in one consolidated view.

Campaign Reports include the channel, delivery status, and key statistics to assess and compare performance.

Use quick filters to isolate campaigns of interest and the email report option to deliver a CSV file to your inbox that includes all the information in the table.

<Image align="center" border={true} src="https://files.readme.io/7687a1e2d0fb8b12e136e6a60993757456de75c46e651dbda3485525c5fcd1b5-Subscribe_to_Reports.gif" className="border" />

# Journeys

[Journeys](doc:journeys) is a visual campaign builder to create an omnichannel messaging experience for your users. Journeys are ideal for engaging users across the lifecycle of your app.

Here are a few sample use cases for Journeys:

* Build User Onboarding Journeys that engage users over several days or weeks and on different channels as you educate them about your service.
* Build Promotional Journeys to entice your users to transact at different points in time.
* Long-running re-engagement campaigns to pull users back into your service if they begin to slip away.

# Message Labels

Message Labels enable you to categorize campaigns with descriptive names or themes, facilitating the grouping and analysis of campaign performance and user behavior.

For instance, you can create a label such as _Onboarding_ to categorize campaigns related to new user onboarding across all channels. Alternatively, a label such as _Re-engage_ can be used for campaigns aimed at re-engaging inactive users. Similarly, a label such as _Score Updates_ can be applied to notifications providing match updates.

Labels can be created under the _Message Settings_ menu, allowing for the creation of multiple labels simultaneously. The labels cannot start with or contain the following symbols: ”, , %, >, \<, and !

<Image align="center" alt="Create Multiple Message Labels" border={true} caption="Create Multiple Message Labels" src="https://files.readme.io/f9cd0350976bbbb7452a822ff49fc74ccbdfe2ff3fdde71476a1b352e7aafc5b-Apply_Labels_to_Campaigns.gif" />

You can create a maximum of 900 labels on the CleverTap dashboard. Labels can be applied to individual campaigns during creation or using the _Edit Campaign_ option from the _All Campaigns_ page.

## Segments and Message Labels

One of the more powerful uses of Labels is the combination with CleverTap Segmentation features. Each time a message is delivered to a user, CleverTap will record a Notification Sent event. As a Property of this event, we include any label that you have assigned to that messaging campaign.

Then from our Find People, Create Segment, or any other Analytics feature, you can isolate users who have been sent a messaging campaign with a particular Label.

For example, you may want to see the 30-day retention of users who were sent Onboarding messages to judge whether these messages were having an impact. After creating a label called _Onboarding_ and associating it with all the relevant campaigns, you can create a new segment and then filter your cohort analysis for 30-day retention to isolate the performance of only these users.

<Image align="center" alt={1404} border={true} caption="Segments and Message Labels" title="Campaign optimization using Segments and Message Labels." src="https://files.readme.io/b961bc7-Filter_by_Users.png" />
