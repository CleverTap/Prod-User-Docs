---
title: Group Unsubscribe
excerpt: Allow users to opt-out of a specific group of messages.
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    DOCS NOTE: COMPARE/REVIEW WITH THE EXISTING PAGE:
    https://docs.clevertap.com/docs/handling-unsubscribes
  robots: index
next:
  description: ''
---
## Overview

CleverTap offers Group Unsubscribe, which lets customers opt out of specific message groups. With Group Unsubscribe, the customer unsubscribes only from a particular group of messages but continues receiving the messages of interest. CleverTap tracks group unsubscribe if you are using a [CleverTap-hosted Unsubscribe page](doc:manage-email-preferences) or [CleverTap's unsubscription methods](doc:handling-unsubscribes) in your Custom Unsubscribe page.

## Subscription Groups

You can group every marketing campaign or outgoing communication message into different subscription group categories. Customers may like to receive messages about a particular category but might opt out of a separate category of messages.

## Create Subscription Groups

Perform the following steps to create a Subscription Group from a particular campaign.

1. From the CleverTap dashboard, select _Settings_ > _Engage_ > _Setup_ _Subscription Groups_.
2. Enter the group's name, provide a brief description, and select the _Email_ channel.

<Image align="center" alt={1027} border={true} caption="Create Subscription Group" title="Create Email Subscription Group" src="https://files.readme.io/2c812d9-Email_subscription_group_setup.png" width="smart" />

3. Click **Save**.

> 📘 Active Subscription Groups
>
> Customers can set up 50 active groups. They can also archive groups to create new ones.

## Use Subscription Groups in Segments

1. From the CleverTap dashboard, select  _Segments_  > _Find People_.

2. From _Display common properties such as_ section, click **+Properties.**

3. Click **+Properties** and select _Subscription Groups_ from the dropdown menu.

<Image align="center" alt={929} border={true} caption="Use Subscription Groups in Segments" title="Use Subscription Groups in Segments" src="https://files.readme.io/fca954f-Email_subscription_group_list.png" />

4. Select the _Exclude/Include_ parameter and accept the All default or select one or multiple options.

<Image align="center" alt={926} border={true} caption="Include/Exclude Subscription Groups" title="Include/Exclude Email Subscription Groups" src="https://files.readme.io/4412785-Email_subscription_group_include_exclude.png" width="smart" />

## Use Subscription Groups in Campaigns

Subscription groups allow users to select the content they want to receive, reducing unsubscription rates and fostering strong brand-user relationships. This approach enhances user satisfaction and builds a more personalized connection with your audience.

You can select the subscription group you want to include in your campaign from the _Select Subscription Groups_ list. This allows you to target users who have subscribed to all the groups you selected for the campaign. To do so:

1. From the CleverTap dashboard, select _Campaign_ and create an email campaign. Refer to [Create Email Campaign](https://docs.clevertap.com/docs/create-message-email).
2. From the _Who_ > _Control group and targeting cap_ > _Send campaign only to users subscribed to all groups selected below_.
3. Select the groups you want to include in your campaign from the _Select subscription groups_ list.

<Image align="center" border={true} src="https://files.readme.io/e0653d9-image.png" className="border" />

4. Click **Done** and click **Continue**.
5. Complete creating the email campaign.

## Use Subscription Groups in Email Landing Page

Refer to [handling unsubscribes](https://docs.clevertap.com/docs/handling-unsubscribes) to add the Subscription Group configuration to your email landing page.

## Track Unsubscribes

Whenever a user unsubscribes, CleverTap raises a system event called _Channel Unsubscribed_ which updates the user's property with the status of subscription for the group.

<Image align="center" alt={1012} border={true} caption="Track Subscription Groups" title="Track Unsubscribes" src="https://files.readme.io/b1c9872-Unsubscribe_last_step.png" width="50% " />
