---
title: Create Message
excerpt: Understand how to create a campaign for Google Ads
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

Remarketing with Google Ads is a way to re-engage users outside your app or website by showing them ads across the Google Search Network, YouTube, and Gmail. Using CleverTap, you segment your users, export those segments to your Google Ads account as audiences, and run targeted remarketing campaigns against them.

For example, suppose a group of users viewed a product in your app but did not purchase it. You can build a segment of those users in CleverTap, export it to Google Ads, and serve them ads for that product the next time they are on Google Search, YouTube, or Gmail.

The Google Ads remarketing module under _Campaigns_ on the CleverTap dashboard is easy to set up for all your users or for distinct user segments. You can base these segments on past user behavior, user properties, or a combination of both.

<Callout icon="📘" theme="info">
  ### Note

  Before you create a campaign, check that you have connected your Google Ads account in _Settings > Channels > Remarketing > Google_. For more information, refer to [Google Ads Setup](doc:setup-google-adwords).
</Callout>

## Create a New Campaign

Create a campaign to deliver your Google Ads message.<br />To create a new campaign:

1. From the CleverTap dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select **Google Ads**.


<Image src="https://files.readme.io/9274b7e0980ecaf3b04114a69445e8468bc4ca5a2c1bae6f99c703af8a71c27e-google_adds.png" alt="Create a New Google Ads Campaign" align="center" caption="Create a New Google Ads Campaign" border={true} />


The _Campaigns_ page displays.


<Image src="https://files.readme.io/1e69901-New_Google_Ads_Campaign.png" alt="Google Ads Campaign Configuration Page" align="center" caption="Google Ads Campaign Configuration Page" border={true} />


Define all the sections and publish the campaign.

## Start Campaign Setup

The _Start here_ step is where you select the Google Ads account for the campaign and set an optional conversion goal. It has the following sections.

### Ad Account

Select the Google Ads account that receives the exported users. This is the first section in the _Start here_ step.

**Export destination** (required): Select the Google Ads account to which you want to export qualified users. The dropdown lists all connected Google Ads accounts. If you set a default account in _Settings > Channels > Remarketing > Google_, it is pre-selected here. You can change the selection for this campaign.

If the account you want is not listed, click **Connect account** to connect a new Google Ads account, then click **Refresh** to update the list.

The campaign cannot proceed until a Google Ads account is selected.

### Set a goal

You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve with the campaign. This selection is optional.

Select **Conversion tracking** to enable goal tracking for the campaign. You can define your conversion goal further by filtering an event by event properties.

The campaign goal can be as generic or as specific as you want. It can answer questions from _How many users were influenced for purchasing an X amount?_ to _How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount?_


<Image src="https://files.readme.io/00215dc-Push_notification_set_goal_track_conversion.png" alt="919" align="center" caption="Goal Conversion Tracking" border={true} />


## Define the Audience

You must indicate the target audience for your Ads campaign. You can specify your target audience from the _Target segment_ section. Here, you can create a new segment or use a previously saved user segment from the _segment_ list.

For Past Behavior segments, you also calculate the _Estimated reach_.


<Image src="https://files.readme.io/5a435b7-SMS_Who.png" alt="961" align="center" caption="Segment Your Target Audience" border={true} />


### Segment

If you want to create an ad-hoc segment, you can select a type of segment on which to base your Ads campaign. You can create the target based on past user behavior and user properties.

On this basis, you would then set up the _Who_ by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under _Estimated reach_.

### Deliver Ads Notifications based on Past Behavior (PBS)

You can also target users based on their past user behavior. For past behavior campaigns, you also have an option to calculate _Estimated reach_. The estimated reach shows the number of users that qualify for the campaign criteria and the number of reachable users.

### Filter by User Properties

Using the _With user properties_ filter in the _Who_ section, you can segment your campaign to only reach users who meet specific criteria.

For example, you can send an Ads notification to English-speaking female users who live in the United States.


<Image src="https://files.readme.io/5851a66-campaigns_user_properties.png" alt="516" align="center" caption="Filter by User Properties" border={true} />


The following table explains the various property types:

| Property Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                        | Example                                                                   |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------ |
| User Properties  | Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.                                                                                                                                                                                                                                                                             | Customer Type = Platinum                                                  |
| Demographics     | Demographics filters include _Age_ and _Gender_.                                                                                                                                                                                                                                                                                                                                                                                   | Age = 25 to 40 years<br />Gender = Female                                 |
| Geography        | User's coarse location. Filters include _Country_, _Region_, and _City_. CleverTap's SDK can automatically detect this from the user's IP address.                                                                                                                                                                                                                                                                                 | Country = United States<br />State = California<br />City = San Francisco |
| Geography Radius | User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides. | Locations = San Francisco, USA; Paris, France                             |
| Reachability     | Reachability filters include _Has email address_, _Has phone number_, _Unsubscribed email_, and _Unsubscribed SMS_.                                                                                                                                                                                                                                                                                                                | Unsubscribed email = No                                                   |
| App Fields       | App fields filters include _App Version_, _Device Make_, _Device Model_, _OS Version_, and CleverTap _SDK Version_. This information is sent by CleverTap's SDK for each device that has your app, which means a single user can have multiple devices associated with their user profile.                                                                                                                                         | OS Version = 10                                                           |

To know more about what segments can be used, see [Segments](doc:segments).

## Define the Message Content

Now, you can set up the _What_, that is, you can select the audience to which you want to export the user details.

### Ads Editor

In the _What_ section, select the audience type and the user details to upload. The Google Ads account is selected in the Setup step.

#### Choose the audience type

Select one of the following audience types:

- **Add qualified users to existing audience**: Append the qualified users to an audience that already exists on the selected Google Ads account. Select the audience from the drop-down.
- **Create a new audience on Google Ads account with qualified users**: Create a new audience on the selected Google Ads account and add the qualified users to it.

<Callout icon="🚧" theme="warn">
  ### Note

  Check that you have available CRM lists before adding users to an existing audience.
</Callout>


<Image src="https://files.readme.io/8e5c43cb954b5b947cd24248bb3193b6ff5cf7cda1f8d3ae3c5ec1b739ad5a6f-what_for_google_ads.png" alt="Configure Audience Type In What Section" align="center" caption="Configure Audience Type In What Section" border={true} />


#### Select the user details to upload

Select the user details to upload for matching. The user details are grouped into three types, shown as separate options:

- **Account & Location**: Account information (Email, Phone, First Name, Last Name) and Location (Country, ZIP). You can select one or more of these details together.
- **Google Advertising ID**: Google's device advertising identifier.
- **Identifier for Advertisers**: The advertiser-facing device advertising identifier.

You can upload only one type at a time. The three types are mutually exclusive and cannot be combined in a single upload. Within **Account & Location**, you can combine any of the available details.

Only details that are mapped to a CleverTap user property are available for selection. Unmapped details, including the **Google Advertising ID** and **Identifier for Advertisers** options and individual fields within **Account & Location**, appear disabled. To enable them, click **Add here** in the panel, or configure the mappings in _Settings > Channels > Remarketing > Google > Map Properties_.


<Image src="https://files.readme.io/2dbf2eff3db95efa67bc8a509f1b6058f16265a143b7f92bac5783642062f8c1-create_new_audience_what_google_ads.png" alt="978" align="center" caption="Create a New Audience on Google Using CleverTap" border={true} />


## Define the Campaign Schedule

You can set up the _When_ to schedule the campaign start and end using the options below:

The delivery preferences for Google Ad campaigns can be set as follows:

- Send Now: Select this option to send the campaign right away.
- Schedule for later: Select this option to send the campaign on a specific date and time.
- Set as Recurring: Select this option to send the campaign at specific intervals.


<Image src="https://files.readme.io/a12d764-when.png" alt="Define the Campaign Schedule" align="center" caption="Define the Campaign Schedule" border={true} />


<br />

<Callout icon="📘" theme="info">
  ### Recurring Day

  If you specify a recurring day for a campaign such as the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date.
</Callout>

## Publish Campaign

After testing and previewing the appearance of your campaign, finalize your campaign by clicking **Publish Campaign**.


<Image src="https://files.readme.io/b521e92-campaign_Publish.png" alt="1193" align="center" caption="Publish Campaign" border={true} />


<br />
