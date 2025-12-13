---
title: Group Unsubscribe
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
## Overview

CleverTap offers Group Unsubscribe which allows customers to opt-out of certain groups of messages. With Group Unsubscribe, the customer unsubscribes only from a certain group of messages and continues receiving the messages they are interested in.

## Subscription Groups

Every marketing campaign or outgoing communication messages can be grouped into different subscription group categories. Customers might be interested and want to receive messages about a particular category, but might want to opt-out of a different category of messages.

## Create Subscription Groups

Perform the following steps to create a Subscription Group from a particular campaign.

1. From the CleverTap dashboard, select *Settings*, and then select *Subscription Groups*.
2. Enter the name of the group, provide a brief description, and select the *Email* channel.

![1650](https://files.readme.io/2c0d02c-2020-08-19_08-43-42_Create_Subscription_Group.png "2020-08-19_08-43-42_Create Subscription Group.png")

3. Click **Save**.

> 📘 Active Subscription Groups
>
> Customers can set up 50 active groups. They can also archive groups to create new ones.

## Use Subscription Groups in Segments

1. From the CleverTap dashboard, select *Segments* and then click *Find People*.
2. From *Display common properties such as* click **+Properties.**

![1570](https://files.readme.io/8cb9775-2020-08-19_08-59-56_Display_common_properties_such_as_.png "2020-08-19_08-59-56_Display common properties such as .png")

3. Click **+Properties** and select *Subscription Groups* from the dropdown menu.

![861](https://files.readme.io/1c7ba97-2020-08-19_09-10-12_Select_Subscription_Group.png "2020-08-19_09-10-12_Select Subscription Group.png")

4. Select the *Exclude/Include* parameter and accept the All default or select one or multiple options.

![1484](https://files.readme.io/1851ef2-2020-08-19_09-24-43_Select_options_for_subscription_group.png "2020-08-19_09-24-43_Select options for subscription group.png")

## Create Campaigns Subscription Groups

1. From the CleverTap dashboard, select *Campaign* and create an email campaign. (Refer to [here](https://docs.clevertap.com/docs/email) for the steps for creating an email campaign).
2. From *Do not send this campaign to the following subscription groups*, select the groups you don't want to include in your campaign.

![1650](https://files.readme.io/17d7430-2020-08-19_09-39-27_Who_for_creating_email_campaign.png "2020-08-19_09-39-27_Who for creating email campaign.png")

3. Click **Apply**.
4. Click **Continue**
5. Complete creating the email campaign.

## Use Subscription Groups in Email Landing Page

Follow the steps provided [here](https://docs.clevertap.com/docs/handling-unsubscribes) to add the Subscription Group configuration in your email landing page.

## Track Unsubscribes

Every time a user unsubscribes, CleverTap raises a system event called *Channel Unsubscribed* which updates the property of the user with the status of subscription for the group.

![1012](https://files.readme.io/b1c9872-Unsubscribe_last_step.png "Unsubscribe last step.png")
