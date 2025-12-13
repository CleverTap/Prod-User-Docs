---
title: Web Pop-Up
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
# Overview

Web notifications are popup messages that can be displayed on desktop or mobile websites.

CleverTap web notifications come in two types:

* Those displayed in a footer of your site. These are available for desktop and mobile websites.
* Those displayed just before the user exits your website, known as exit intent web-popups. These are available for desktop only.

## Web Pop-Up

Web pop-ups enable you to send quick alerts, offers, or even how-to tidbits to your users using our in-built web popup builder or if you prefer, your own custom HTML templates. CleverTap’s exit intent web pop-ups enable you to encourage subscribes or gather information from users, just before they leave your website. CleverTap’s rich segmentation enables displaying time-sensitive, relevant, and personalized web pop-up campaigns in large-scale. 

The prerequisite to setting up web pop-up campaigns involves integrating your website with the CleverTap JavaScript plugin, as [shown here](https://developer.clevertap.com/docs/web).

## Web Exit Intent

The Web → Pop Ups/Exit Intent module on the CleverTap dashboard (under “Campaigns”) makes it easy to set up web pop-up campaigns for all your users or specific user segments. 

These segments can be created on the basis of user action on one of your webpages, user visits to a specific webpage of yours, user visits to your website via external ad referrer, or even based on number of webpages of yours a user has visited so far. 

Once a campaign has been sent, you can view detailed reports on how many messages were sent, how many users converted as a result, and more.

# Web Pop-Up Campaign Creation

## Step 1: Create a New Campaign

After "+ Campaign", select "Web Pop-up" under Channel

<Image title="Screenshot 2020-06-10 at 11.05.20 AM.png" alt={2780} className="border" border={true} src="https://files.readme.io/7639943-Screenshot_2020-06-10_at_11.05.20_AM.png" />

Select the type of Web Pop-up

![2790](https://files.readme.io/954d3a2-Screenshot_2020-06-10_at_11.09.33_AM.png "Screenshot 2020-06-10 at 11.09.33 AM.png")

## Step 2: Define the Who

The next step would be to indicate the target audience for your web pop-up campaign. You can target your web pop-up campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 

<Image title="Campaign_Saved_Segment_PBS_Who.png" alt={1147} className="border" border={true} src="https://files.readme.io/8097f5a-Campaign_Saved_Segment_PBS_Who.png" />

If you choose to create an ad-hoc segment, you can now select a type of segment on which to base your web pop-up campaign. 

<Image title="image8.png" alt={1297} className="border" border={true} src="https://files.readme.io/41b94e9-image8.png" />

The target can be created either on the basis of the following triggers:

* User action on one of your webpages (Single action).
* User visits to a specific webpage URL of yours (Page visit).

<Image title="image2.png" alt={1299} className="border" border={true} src="https://files.readme.io/148bc5d-image2.png" />

* User visits to your website via external ad referrer URL (Referrer entry)

<Image title="image14.png" alt={1299} className="border" border={true} src="https://files.readme.io/aaca28b-image14.png" />

* Number of webpages of yours a user has visited so far in their session (Page count)

<Image title="image3.png" alt={379} className="border" border={true} src="https://files.readme.io/08b8491-image3.png" />

For instance, we can choose to create a live “Single action” campaign that will target users as soon as they apply a payment offer on your desktop or mobile website.

On this basis, in the next step, here is how we would set up the “WHO”. You can also further check the “Filter this stream based on these users’ past behavior/user properties” checkbox to filter by any past user behavior or user properties.

## Step 3: Define the When

Then, you can set up the “WHEN” to schedule the campaign start and end, as shown below.

If it is a limited-time incentive, you might want to end the web pop-up at a particular end date and time. If always relevant, you can specify that the campaign should never end. However, if you change your mind later, you can always stop the campaign by clicking on the red “stop” icon next to the campaign in the main web pop-up campaigns page. 

Additionally, you can even specify a minor delay so that the web pop-up is displayed, say, a few minutes after the user does the trigger action for the campaign to give them time to, say, apply the payment offer. You can set campaign frequency here, as well, by specifying any specific days of the week and times of the day you would like for it to display. 

Finally, you can specify how often users receive the campaign: Bypass global campaign limits by checking the ‘Exclude from campaign limits’ radio button, or send once per session.

<Image title="image13.png" alt={748} className="border" border={true} src="https://files.readme.io/f8907a4-image13.png" />

## Step 4: Define the What

Finally, you can go on the next step that involves setting up web pop-up campaign content (“WHAT”).\
You can use the in-built editor to type out your message title and body, or use our “Custom” HTML editor to paste your own custom HTML templates. 

Our in-built web pop-up campaign creator enables you to customize the look of your web pop-up: Choose from “Box”, “Banner”, or “Interstitial” layouts for your pop-up, specify whether to show on Desktop, Tablet, Mobile, select pop-up background color and text color, pop-up position, and even specify a pop-up icon (choose from our default icon images, or provide your own publicly-hosted icon URL) with look (with rounded corners, if preferred) and a close icon if you would like.

<Image title="image5.png" alt={788} className="border" border={true} src="https://files.readme.io/09c19ea-image5.png" />

<Image title="image12.png" alt={281} className="border" border={true} src="https://files.readme.io/956fb36-image12.png" />

For exit intent web pop-ups, you can specify a button with text, customize button background and text color, and even include an image (with a publicly-hosted image URL) within our in-built web pop-up builder.

<Image title="image7.png" alt={640} className="border" border={true} src="https://files.readme.io/7a003c4-image7.png" />

Upon web pop-up click, you can either do nothing, open a web URL, or invoke your custom JavaScript.

**Personalization**\
The web pop-up message can be personalized for every user based on specific user property or event property values. See User Profiles to learn more about user profile properties and events (dynamic replacements).

To invoke the personalization menu, type “@” in the text fields while typing out the web pop-up message.

Emojis can be included in your web pop-up messages, just like regular text. You can use the CleverTap emoji picker, or copy-paste emojis from Emoji keyboards online.

<Image title="image1.png" alt={388} className="border" border={true} src="https://files.readme.io/2aaf38a-image1.png" />

## Step 5: Test & Schedule Campaign

Once you are all done setting up the content of your campaign in “WHAT”, you can easily preview your notification in a sample webpage we serve up by clicking on “Preview notification”.

<Image title="image6.png" alt={143} className="border" border={true} src="https://files.readme.io/17c3296-image6.png" />

Post-testing, when you are satisfied with the appearance of your campaign, you can “Continue to Overview” to view your campaign summary, the hit “Schedule notification”.

<Image title="image15.png" alt={138} className="border" border={true} src="https://files.readme.io/2e7d281-image15.png" />

# Define a Custom Callback

Using the following custom callback functions, you will be able to control the look, feel, and location of your web pop-up.

You will need to explicitly call clevertap.raiseNotificationViewed(); & clevertap.raiseNotificationClicked(); to ensure that notification views and clicks are tracked on CleverTap.

To define the callback and raise the clicked and viewed events, you will need to add the following snippet to the JavaScript embed code comprising your CleverTap web integration.

```javascript
clevertap.notificationCallback = function(msg){
      // Raise the notification viewed and clicked events in the callback
      clevertap.raiseNotificationViewed();
      console.log(JSON.stringify(msg));// Your custom rendering implementation here
      var $button = jQuery("<button></button>");// Element on whose click you want to raise the notification clicked event
      $button.click(function(){
         clevertap.raiseNotificationClicked();
      });
};
```

The message will be in the following format.

```json
{
    "msgContent": {
        "title": "hello title!",
        "description": “hello message!"
    },
    "msgId": "1439796272_20160219",
    "kv": {
        "key1":"value1",
        "key2":"value2"
    }
}
```

msgId contains the campaign ID and the date-stamp so that you can programmatically decide whether to display the notification. kv contains the custom key-value pairs.

# Viewing Web Pop-up Campaign Stats

Once the campaign has gone out, you can view its stats by going into “Web” → “Pop Ups”/”Exit Intent” under “Campaigns” on the CleverTap dashboard and clicking on the campaign of interest to see its total impressions, clicks, conversions, and revenue from conversions (if applicable):
