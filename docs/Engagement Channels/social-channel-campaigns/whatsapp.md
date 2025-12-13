---
title: WhatsApp
excerpt: A guide to creating WhatsApp campaigns on CleverTap
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
WhatsApp is a popular messaging channel that enables secure and trustworthy communications. The most attractive value WhatsApp provides is that it's advertisement and spam-free. Recently, WhatsApp has started allowing businesses to communicate with their users in a more friendly and interactive manner. 

CleverTap allows you to use WhatsApp as a channel to engage your users in a reliably and securely. Additionally, you can also use CleverTap's [Conversations](doc:conversations) to chat with your users on WhatsApp.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2f2d935-Whatsapp_3_new_1.png",
        "Whatsapp_3_new (1).png",
        1251,
        1551,
        "#9ba29c"
      ],
      "caption": "Business to user messaging using WhatsApp as a channel"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Why do you need WhatsApp as a channel?"
}
[/block]

WhatsApp messages have high reachability and readability rates due to its security and trustworthiness. That makes it one of the most attractive channels of engagement for businesses. 

**Following are some real scenarios:**
1. Send real-time notifications to customers regarding delivery alerts and booking confirmations
2. Send personalized recommendations about new products, offers, and services through rich media sharing
3. Delight your customers with reminders about their upcoming bookings
4. Enable your customer support team to respond to customer queries instantly

A WhatsApp message can be configured and sent like any other campaign on CleverTap. After sending the campaign, you can measure the performance of that campaign. 

When a user responds to one of your messages, CleverTap gives you the capability to reply to the user directly from the dashboard.
[block:api-header]
{
  "title": "How to get started"
}
[/block]
CleverTap uses API endpoints from [Nexmo](https://www.nexmo.com/products/messages/whatsapp) to connect with WhatsApp. You can do the following:

1. Contact CleverTap's sales team to get a WhatsApp Business account for your organization. You can contact them at sales@clevertap.com.
2. CleverTap's customer success team will then create the accounts for you which will enable you to use WhatsApp as an engagement channel.

Alternatively, if you already have a Nexmo account, you can plug in the details by going to Account->Settings->Integrations->WhatsApp page.
[block:api-header]
{
  "title": "Opting in users into WhatsApp"
}
[/block]
Most people do not like getting unsolicited messages on WhatsApp. Therefore, it's important for you to explicitly request permission, before sending messages to users on their WhatsApp account. 

CleverTap, by default, keeps all the profiles opted-out of WhatsApp. To opt-in profiles, update the profile using the following code:
[block:code]
{
  "codes": [
    {
      "code": "\"MSG-whatsapp\":true",
      "language": "json"
    }
  ]
}
[/block]
There are two ways to opt in users for WhatsApp:
1. [Opt in via updating user's profile property](https://developer.clevertap.com/docs/concepts-user-profiles#section-updating-the-user-profile) 
2. [Opt in via API profile update](https://developer.clevertap.com/docs/upload-user-profiles-api) 
[block:api-header]
{
  "title": "Understanding Message Templates in WhatsApp"
}
[/block]
WhatsApp restricts brand initiated messages (the messages that you send via campaigns) to pre-approved templates. You can fill in the variables in the templates to personalize a message. For example:

*Hello {{1}}, Congratulations on your ticket booking. Here is your ticket number: {{2}}. Please ensure you visit us on {{3}}. Enjoy your experience.*

The variables *{{1}}* or *{{2}}* or *{{3}}* can be replaced by a text of your choice. You can use CleverTap's event and profile personalization to personalize the message for your audience.

To set up a message template, follow this [guide] on Facebook (https://developers.facebook.com/docs/whatsapp/message-templates/).
[block:api-header]
{
  "title": "Configuring message templates"
}
[/block]
All your message templates must be approved by WhatsApp. At CleverTap, we help you with the verification. You can get help in creating templates [here](https://developers.facebook.com/docs/whatsapp/message-templates/creation/). After your templates are verified, you can enter them on the WhatsApp settings page Templates tab.

To use WhatsApp with CleverTap, it is important to copy the templates accurately in Settings. To do this, go to Account -> Settings -> Integrations -> WhatsApp. Click on the Templates tab and add your templates for WhatsApp campaigns.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6139fec-Screenshot_2019-06-16_at_9.57.43_PM.png",
        "Screenshot 2019-06-16 at 9.57.43 PM.png",
        1438,
        800,
        "#f6f7f8"
      ]
    }
  ]
}
[/block]
Click on **+Add New** button and a **Add new whatsapp message template** appears. Add the template. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c9aa3fe-Screenshot_2019-06-16_at_10.42.19_PM.png",
        "Screenshot 2019-06-16 at 10.42.19 PM.png",
        1423,
        655,
        "#606061"
      ]
    }
  ]
}
[/block]
Check that the namespace and template text is copied correctly from your Facebook page. 
After copying the text, click **Save** to save the template.  
[block:callout]
{
  "type": "warning",
  "title": "Important note",
  "body": "While copying message templates from Facebook business dashboard, make sure you use the following format for namespace:\n**<template_namespace>:<template_name>** \n\nThis will ensure your templates get added to CleverTap dashboard"
}
[/block]

[block:api-header]
{
  "title": "Creating a WhatsApp campaign"
}
[/block]
## Step 1: Creating a Campaign

Click the + Campaign button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/36c8ee4-Screenshot_2019-06-02_at_7.38.58_PM.png",
        "Screenshot 2019-06-02 at 7.38.58 PM.png",
        1419,
        596,
        "#dcdee2"
      ]
    }
  ]
}
[/block]
Select WhatsApp from the channel selection page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/abe7f9c-Screenshot_2019-06-02_at_7.43.32_PM.png",
        "Screenshot 2019-06-02 at 7.43.32 PM.png",
        1440,
        706,
        "#f1f1f4"
      ]
    }
  ]
}
[/block]
Select the message type and the target segment.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ceff63d-Screenshot_2019-06-02_at_7.50.01_PM.png",
        "Screenshot 2019-06-02 at 7.50.01 PM.png",
        1440,
        641,
        "#f0f1f4"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "Unlike other channels such as Push or SMS, WhatsApp doesn't support multiple date campaigns or recurring campaigns. This is to prevent misuse and spam.\n\nThe four types of campaigns possible are:\n\n**One time:** for past behavior segments. For example, send a WhatsApp message to all users who booked tickets last week.\n\n**Single action:** for live user segments. For example, send a confirmation to all users after buying a movie ticket from the app.\n\n**Inaction within time:** For example, send a reminder to all the users who added an item to the cart, but didn't check out within 30 minutes. \n\n**On a date/time:** For example, send a message to users one day before the flight departure, regarding do's and don'ts.",
  "title": "Campaign types"
}
[/block]
## Step 2: Drafting your message 
Select a message type - Single or Multivariate. 

Select a message template. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cdc8541-Screenshot_2019-06-02_at_8.57.20_PM.png",
        "Screenshot 2019-06-02 at 8.57.20 PM.png",
        1439,
        735,
        "#f4f1f3"
      ]
    }
  ]
}
[/block]
After you have selected the message template, you will see the options to replace the variable fields with your custom input.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc77607-Screenshot_2019-06-03_at_12.18.58_PM.png",
        "Screenshot 2019-06-03 at 12.18.58 PM.png",
        1377,
        685,
        "#efeeed"
      ]
    }
  ]
}
[/block]
## Step 3: Saving and scheduling your campaign

It is now time to save and schedule your campaign. This will ensure that your WhatsApp message reaches your intended audience.

[block:api-header]
{
  "title": "Campaign stats in WhatsApp"
}
[/block]
You can click the campaign from the campaign list page to view the statistics. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71b7448-Screenshot_2019-06-16_at_10.51.44_PM.png",
        "Screenshot 2019-06-16 at 10.51.44 PM.png",
        1327,
        370,
        "#f8f9fb"
      ],
      "caption": "Campaign Stats for WhatsApp"
    }
  ]
}
[/block]
You can track the status of your messages sent under the following heads:
**Sent:** Messages sent from CleverTap
**Errors:** Errors occurred while sending the messages to the user
**Delivered:** Messages delivered to the user's WhatsApp app
**Read:** Messages that the users have read. Equivalent to Notification Viewed
**Control group:** Users who were excluded from the WhatsApp campaign because they belong to  the  control group
**Replied:** Number of replies sent by the user to the business