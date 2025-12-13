---
title: FAQs_Clone
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
#Common Android SDK Questions

Q. How do I exclude In-app from the Android activity?

In-App notifications are pop-ups that you can show to your users while they are on your app. To exclude the in-app notification on a particular activity or page, you can use the following code.

[block:code]
{
  "codes": [
    {
      "code": "<meta-data\n    android:name=\"CLEVERTAP_INAPP_EXCLUDE\"\n    android:value=\"YourSplashActivity1, YourSplashActivity2\" /> ",
      "language": "xml"
    }
  ]
}
[/block]
For more information, see [In-app notifications](https://developer.clevertap.com/docs/android#section-in-app-notifications)

#Push Notification Errors in Android

1. Invalid FCM API Key

An "Invalid FCM API Key" error appears when the FCM API key in the CleverTap dashboard is incorrect. You will not be able to send any notifications till the FCM API key is added to your settings. To update the FCM API key - 
  * Navigate to Settings > Engage > Mobile Push. 
  * Update the valid FCM API key as it appears in your Firebase project. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d0f805-Push_Notification_FCM_API_Key.png",
        "Push_Notification_FCM_API_Key.png",
        1172,
        1037,
        "#fafafa"
      ],
      "caption": "Update FCM API key",
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]

For more information, see finding your [FCM API Key](https://developer.clevertap.com/docs/find-your-fcm-sender-id-fcm-server-api-key)

2. FCM Token Invalid

The  FCM token is not linked to any device that has your app.
Since the token is not a valid one, notifications will not be delivered.
Check the format of the FCM project number and registration token you pass on to CleverTap.
For more information see [Troubleshooting push notifications](https://developer.clevertap.com/docs/troubleshooting-push-notifications)

3. FCM Error

This is a Firebase (Android) error. The "FCM error" is not part of the "standard published list" and sometimes incorrectly identified as an Android bug.

4. FCM Not Registered

Most likely the users have uninstalled the app from their device.

One of the common non-technical errors is "Undelivered due to App Uninstall", in campaign reports. This error occurs when the users uninstall your app while you are trying to reach them via a push notification.

The FCM Not Registered error occurs in two scenarios:

  * When the users have uninstalled your app and you are trying to schedule a push notification to them
  * When users have cleared the device cache memory, which in turn removes the token from the device

5. FCM Mismatch Sender ID

An FCM sender ID mismatch occurs when the sender ID entered in the CleverTap dashboard under Push Notification settings does not match with the sender ID in the FCM project for your app created on Firebase.

An FCM sender ID mismatch occurs when the sender ID entered in the CleverTap dashboard under Push Notification settings does not match with the sender ID in the FCM project for your app created on Firebase.

There are three places where these sender ID/ server keys have to be matched.

You must match the sender ID/server keys at the following 3 locations:

  *  App-level which registers token with the said FCM sender ID mentioned.
  *  In the CleverTap dashboard.
  *  FCM project

If you have checked the sender ID for mismatch and the error still persists, check the following: 

  * Does the app build and the CleverTap account contain mismatched sender IDs?
  * Do you have multiple Firebase projects?
  * Do you have multiple Platform IDs, that is, your app is using two Firebase projects?


#Push Notification Errors in iOS

 1. APNS Device Token Does Not Match The Specified Topic 

Apple Push Notification service (APNs) returns this when the device token doesn't match the specified topic.

In the context of CleverTap, you will get this error when you try to send the notification with a wrong certificate. Check that you use a production certificate for the production environment. It is because of bad configurations. 

Check the provisioning profile used to deploy the app and send the device token to the CleverTap dashboard. To avoid this error, the "App bundle ID" of the provisioning profile and the CleverTap push certificate (p12 certificate) must match.

2. APNS Unregistered

The Push notification delivery to the target has failed as the device token is inactive for the specified topic. Since the device token is not valid/inactive nothing can be done that will deliver the notification unless the user installs the app again.

3. APNS Topic Disallowed

The topic is currently the bundle identifier of the target application on an iOS device. The "APNS Topic Disallowed" error appears when you specify the incorrect "App Bundle ID" in the Account Settings. For more information, see [Apple documentation](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html).

To resolve this error, check the value of the "App Bundle ID" and "APNs push mode" that you have configured in the CleverTap Dashboard under Push Settings.

4. APNS Temporarily Blacklisted

You are temporarily blacklisted from sending push notifications to the device, which can be due to sending bad tokens. The push notification will not be delivered for some duration.

5. APNS Failed Delivery 

The notification to the device sent from CleverTap failed to deliver due to either of the following reasons
  * The app was uninstalled and the token is no longer valid.
  * You have sent too many back to back notifications very quickly to the same device.

If the user has uninstalled the app there is not much that can be done to deliver the notification 
 For more info about APNs, see [Handling Notification Responses from APNs](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/handling_notification_responses_from_apns).

6. APNs Bad Device Token

The push notification delivery to the target device has failed due to an invalid token. The APNs bad device token error occurs when there is a mismatch between the APNs push mode on your app and the CleverTap dashboard. 
For example, you have set the APNs push mode in your app to "development" stage and in the "CleverTap" dashboard you have set up to "production" stage. To check your CleverTap dashboard APNs push mode: Navigate to Settings > Engage > Mobile Push> iOS.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/20ff216-Push_Notification_iOS_API_Key.png",
        "Push_Notification_iOS_API_Key.png",
        1166,
        761,
        "#f9f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
#Campaign Errors

1. SMS Errors

An SMS error is a common campaign error that occurs while scheduling the SMS campaign. The SMS error appears if the SMS service provider’s endpoint is unavailable. It is applicable to generic integrations and MSG91 (SMS provider).

The SMS error shows the following message: 

"Error java.net.SocketTimeoutException: Read timed out for message". It is referred to as the "SocketTimeoutException" error.

SMS error appears when CleverTap sends the SMS payload to the SMS provider’s endpoint but it does not get an acknowledgment within 15 seconds. 

You can view the errors within the campaign reports under the "Error" section.  The "SMS error" appears under the "Technical Errors" category.
[block:callout]
{
  "type": "info",
  "body": "The issue generally means a socket timeout exception. Sometimes it can also mean connection request exception.",
  "title": "Note"
}
[/block]
For other integrated vendors we have the equivalent errors : 
a. Exotel server error
b. Twilio server error
c. Gupshup server error
d. Netcore service error
e. Nexmo SMS error

2. Web Push Unsubscribed

The error "BrowserUnsubscribed" appears after your app users unsubscribe themselves for web push notifications from Chrome browser settings. 

When you try to engage these unsubscribed users through web push, the "BrowserUnsubscribed" error appears.

3. How do I enable Push impressions?

To enable Push impressions:
  * Go to  Settings > Schema > Events/User Properties.
  * Click "Push Impressions" event and toggle the Mobile push button to enable Push impressions for the account. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/902d879-FAQs_Push_Impresions_Enable.png",
        "FAQs_Push_Impresions_Enable.png",
        1437,
        764,
        "#f5f5f5"
      ],
      "border": true
    }
  ]
}
[/block]

4. Daily Limit Exceeded

While creating a recurring push campaign, CleverTap allows you to set the daily limit. For example, you can set a daily send limit to 10,000/day, after which you will get "Daily limit Exceeded" error, and set an overall cap limit to 1,00,000 users after which the campaign will stop.

You would generally set a daily limit in a Triggered Campaign, where you are using a live segment. These campaigns are triggered based on an event and therefore you would want a daily limit for your campaigns. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47a68a3-Campaigns_per_day.png",
        "Campaigns_per_day.png",
        1126,
        657,
        "#f9f9fb"
      ],
      "border": true
    }
  ]
}
[/block]

 You can set the campaign limits within the "Who" section while creating the campaign.

5. Per Run Limit Exceeded

The Per Run Limit is a limit enforced on the number of users that are sent in one campaign run.  For example, you can set a maximum segment limit to 100000 users and the campaign stops running after the set limit for each run.

You see the Per Run Limit Exceeded error when the campaign stops running after the number of qualified users exceeds the set limit. 

You would generally set a per run limit for past behavior and custom list segments. This is because the campaign is sent to all the qualified users based on their past actions. Therefore you would want a per run limit for these campaigns.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/131c866-Campaigns_per_run.png",
        "Campaigns_per_run.png",
        1399,
        764,
        "#fafaf8"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
You can set this maximum segment size from the "Who" section while creating the campaign.

Q. Why is the reachability for my campaigns so low?

When you create a segment, you can view the reachability of this segment across all channels such as, "Web Push", "Mobile Push", "SMS", "Email", and "Audiences." This helps you to check the reachability of your campaigns even before you create them.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/742acc4-segment_rechability.gif",
        "segment_rechability.gif",
        1438,
        765,
        "#f9f9f8"
      ],
      "border": true
    }
  ]
}
[/block]
Following are some of the reasons that may affect your "Mobile Push" reachability:
  * Token Not Present: One of the key reasons for low reachability is because the push token is not available in the user profile.
  * User Unsubscribe: The user may have unsubscribed from your app and does not wish to receive push notifications. 
  * Token not generated: The token did not generate on the first app launch.
  * App Uninstall: User has uninstalled the app.


Q. User DND Set Error

 A "User DND set Error" occurs when you qualify users for a campaign even though they have unsubscribed on the target device.  This error informs you that these users have been passed into the error bucket. 

Q. Frequency Caps Exceed Error 

The Global Frequency feature allows you to restrict the maximum number of messages you can schedule each day for your user and across different channels.

Go to the Settings > Setup > Campaign limits to cap the frequency for various channels. 

Here, you can define the number of messages you wish to send to each user in "X" number of days. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7bd8ab2-Campaigns_global_frequency.png",
        "Campaigns_global_frequency.png",
        893,
        598,
        "#f9f9fb"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
You can also specify the "Dwell Time", which is the gap you wish to keep between two messages, and "Throttle", which enables you to control the flow of your messages. 

For more information on dwell time, see [Dwell Time](https://docs.clevertap.com/docs/messaging-frequency-caps#section-dwell-time-between-messages)

For more information on throttling, see [Throttle](https://docs.clevertap.com/docs/messaging-frequency-caps#section-dwell-time-between-messages).

Now when you create a campaign and you wish to disable the "Global frequency limit", then clear the "Global Campaign Limit" option under the "Who" section. The "Global Campaign Limit" is enabled by default.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a73eec-Campaigns_global_campaign_limits.png",
        "Campaigns_global_campaign_limits.png",
        1200,
        649,
        "#f9f8f6"
      ],
      "border": true
    }
  ]
}
[/block]
#Dashboard Errors

 Q. How can I upload a CSV file from the dashboard?

You can bulk upload user profiles using the CSV Upload feature. You can also use this feature to add or update information for existing user profiles.

Follow the steps to upload the CSV file in your CleverTap dashboard:

1. Login to your CleverTap account, and then click the Settings button.
2. Click on the CSV Uploads button.
3. Click the Import new profiles from CSV button.
4. Select the CSV file from your computer, and then click the Upload button.
5. Enter a name for the upload.

Your CSV upload is processed in near real-time. After the uploaded CSV is processed, the status for that upload is changed to "completed".

You can also refer to the following document:
For more information on CSV upload, see [CSV Upload](doc:csv-upload).

Q. How can I delete the events data from the dashboard without discarding events?

You can simply reset the DRP for each event. All the event data beyond the selected date range is discarded. 

For example, if you set the DRP of an event to 12 months, we will store the data for the past 12 months. All the data prior to the 12 months are deleted. You can optimize your container and avoid flooding it with too much data.  

Follow the steps to adjust the DRP for each event:

1. Go to "Events & User Properties" under the dashboard settings section
2. Select the event for which you wish to adjust/reduce the DRP.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/85e8e1a-Settings_DRP_Limit.png",
        "Settings_DRP_Limit.png",
        1437,
        764,
        "#f5f5f4"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "body": "Analyze your data before reducing the DRP. Only remove the data that will not affect your campaigns.  The maximum reduction in data DRP is upto 3 months.",
  "title": "Note"
}
[/block]
#Events & User Profiles

Q. How can I export data from CleverTap

You can export the data from CleverTap using one of the three following methods:

* S3 Export (AWS) -  You can export your event and profile data in the AWS S3 bucket using CleverTap Data Exports. For more information on using our data export, see [Data Export to AWS S3](doc:data-export-to-aws-s3).

* Export via API - You can export your events and user data with our APIs. For more information, see [Export Data with API](https://developer.clevertap.com/docs/api-overview).

* Find people - You can download the profile data directly from the CleverTap dashboard through the Find People page. To download the data from "Find People", follow the steps mentioned below:

 * Step 1: Navigate to the "Find People" section and define the criteria that you wish to export.
 * Step 2: Click "View Details.”
 * Step 3: Click on the download icon (beneath the user count) to initiate the download (refer to the screenshot below).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55a31f1-FAQs_Events_and_Profiles_Export_data.png",
        "FAQs_Events_and_Profiles_Export_data.png",
        1224,
        335,
        "#f4f6fb"
      ],
      "border": true
    }
  ]
}
[/block]
#Webhooks

Q. What is a Webhook dispatched failed error?

The "Webhook dispatched failed" error is raised when CleverTap server does not receive a "200 OK" response. A "200 OK" response is an acknowledgment from the REST API server that the API request was received successfully. An error can arise in either of the three scenarios:

  * When CleverTap sends the payload to your endpoint and we do not receive a "200 OK" response after retrying 3 times after a wait of 15 seconds. 
  * When CleverTap sends the payload and your endpoint health is down.
  * When you may receive the payload at your endpoint but not send a "200 OK" response to CleverTap server within the timeout frame of 1 second. CleverTap displays a "Webhook dispatch failed error" in this case.

We recommend, as a best practice, to queue the payload at your end and provide us a "200 OK" in response.

#Identity

How does Clevertap calculate unique users from the dashboard?

CleverTap identifies and calculates users via multiple steps:

* Step 1 - Creation of a Profile

A user profile is created when a user installs an app and the CleverTap SDK is initialized. 

For example, a user installs the app in device 1 and an anonymous profile A is created. After the user logs in to the app, all the user data is updated to the user's profile, and the profile is now marked as identified.

* Step 2 - Merging of profiles
If the user installs the app on another device, that is device 2, then another anonymous profile is created, say Profile B.

For example, when the user logs in from device 2, then the profile B is then merged with Profile A.
All the events from device 2 after the user login are now pushed to Profile A.

* Step 3 - Profiles after merging
When we run a query on the dashboard for any pre-login event, the exact number of events are displayed.

However, CleverTap still counts both profiles. It means that the count of users for the same event will be 2, that is, Profile A and Profile B. 

We determine all the possibilities and perform a best-case scenario to show all the events for the same user, which is Profile A. The anonymous profile is displayed in grey color. 

The events before login are not mapped again to the profile A. They are maintained on the anonymous profile.

Q. What is Duplicate Platform ID Error

"Duplicate Platform ID Error" occurs in one of the following scenarios:

  * When a single token is assigned to multiple profiles and both the profiles qualify for the campaign. Here,  CleverTap sends the notification to the profile that qualifies first, and the other profile is marked as a "Duplicate Platform ID."
  * When the same mobile number is assigned to multiple profiles and they qualify in your campaign. Here, only one profile receives the notification, and the other profiles are marked as a "Duplicate Platform ID".

#Settings

Q. What is CleverTap DRP?

The CleverTap DRP stands for Data Retention Policy. It means the duration for which you would like to store your data with CleverTap. The CleverTap DRP is applicable for events and user profile data only. 

The data retention policy for user profile includes identifiers, system properties, and custom properties. The data retention policy for user profiles can store a current snapshot of a user profile forever. 

However, the data retention policy for events includes system and custom events. The data retention policy for events depends on both, the customer plan type and the setting defined in the CleverTap dashboard.

If you wish to check the DRP of all the events and user properties related to your account,  navigate to "Events and User Properties" under the Settings section. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/083ef3f-settings_event_storage_DRP.png",
        "settings_event_storage_DRP.png",
        1435,
        705,
        "#f6f6f6"
      ],
      "border": true
    }
  ]
}
[/block]
DRP works on the concept of a rolling window and the default DRP is set to 2 months. For example, if DRP was set on 1st Jan 2000 then the data will be available till 1 March 2000, post which the data will be dropped and will not be available.

You can refer the below table to understand DRP by different plan type:

[block:parameters]
{
  "data": {
    "h-0": "Plan Type",
    "h-1": "User Profile DRP",
    "h-2": "Event DRP",
    "h-3": "Can Modify Event DRP",
    "0-0": "Free Plan",
    "1-0": "Business Plan",
    "2-0": "Enterprise Plan",
    "0-1": "Current Snapshot Stored Forever",
    "1-1": "Current Snapshot Stored Forever",
    "2-1": "Current Snapshot Stored Forever",
    "0-2": "60 days for all events. This account has a limitation of 100M events. If the 100M max event limit is hit before the 60 day DRP, events will be deleted starting with the oldest event first.",
    "1-2": "Automatically set to the maximum DRP of 10 years for all events.\nWhen an event surpasses the DRP, the oldest event is be deleted first.",
    "2-2": "Automatically set to the maximum DRP of 10 years for all events.\nWhen an event surpasses the DRP, the oldest event is be deleted first.",
    "0-3": "No",
    "1-3": "Yes. You can update the DRP for each event type. The minimum DRP that can be set is 3 months.",
    "2-3": "Yes. You can update the DRP for each event type. The minimum DRP that can be set is 3 months."
  },
  "cols": 4,
  "rows": 3
}
[/block]
#CSV Uploads

CSV uploads - identity passed as "Identity."

Uploading your historical user data via CSV is simple and quick. However, there are a few key pointers to note before uploading your user data via CSV. 

  * The identity field must be defined as "identity" with a small "i" and not "Identity".
  * The "Identity" field is a mandatory column 
  * Check that your CSV complies with the CSV standards, else the upload is denied.
  * You can download the sample CSV file for a quick check from the settings section under "CSV uploads."

Sample CSV :
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/61b074a-Identity_CSV_Uploads.png",
        "Identity_CSV_Uploads.png",
        1298,
        344,
        "#e3e3e3"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "New FAQs"
}
[/block]
#Email
##How do I find IPs to send out Emails/ Webhooks/ SMS/ Push notifications?
You can find the IPs for different regions such as In, Sg, and Eu under  Settings > Integration > Push Notification. The IPs are visible under Push Notifications only. However, these are the same IPs used for all the engagement channels. The IPs in the Integration setup of new dashboard is visible in the Account settings > Engage> Channels > Mobile Push > FCM credentials. {@harsh, which path is the correct one?  I do not see IPs at either of the paths}

##Q. How do you handle unsubscribe and bounce for callbacks such as Mandrill or SendGrid?
CleverTap must receive notification for any email that is classified as bounced,  rejected, or user unsubscribed. We do not attempt any further deliveries to such mailboxes. 

For more information, see [Sendgrid](https://docs.clevertap.com/docs/sendgrid#section-step-2-bounces-rejections-and-unsubscriptions) and Mandril(https://docs.clevertap.com/docs/mandrill#section-step-2-bounces-rejections-and-unsubscriptions)

A service provider tracks any user unsubscribes using the unsubscription link in your email. The service provider then sends this information to CleverTap through the callback URL. 

The communication preference for such users is marked as false (MSG_Email=False). 
The hard bounce and unsubscribed users both fall under unsubscription. Follow the steps to find the number of users that have unsubscribed via email:

1. Go to Segments > Find People. 
2. From the Display common properties, select Reachability > Unsubscribed > Yes

##Q. How do you annotate an email?
You can annotate an email from the Setup promo tab. 

Email annotations in the Promotions tab bring email messages to life with images, deals, expiration dates, and more. The Email annotation can be performed in the Drag and Drop Email Editor and also in the custom HTML email editor.

Use the <meta> tag in the drag and drop editor to annotate an email.  Here is the sample code that can be used in the HTML block of drag and drop editor:

[block:code]
{
  "codes": [
    {
      "code": "<p>\n<div itemscope itemtype=\"http://schema.org/Organization\">\n\n<meta itemprop=\"logo\" content=\"https://www.gstatic.com/images/branding/product/1x/googleg_48dp.png\" />\n\n</div>\n\n<div itemscope itemtype=\"http://schema.org/DiscountOffer\">\n\n<meta itemprop=\"description\" content=\"40% off\" />\n\n<meta itemprop=\"discountCode\" content=\"DISCOUNTCODE\" />\n\n<meta itemprop=\"availabilityStarts\" content=\"2020-03-20T08:00:00-07:00\" />\n\n<meta itemprop=\"availabilityEnds\" content=\"2020-03-21T23:59:59-07:00\" />\n\n</div>\n\n<div itemscope itemtype=\"http://schema.org/PromotionCard\">\n\n<meta itemprop=\"image\" content=\"https://gmail-ads-markup-test.sandbox.google.com/sample.png\" />\n\n</div> This is metadata in HTML block of drag and drop editor</p>\n",
      "language": "html"
    }
  ]
}
[/block]
For Custom HTML implementation, see [gmail promotab](https://developers.google.com/gmail/promotab/overview ). This promo tab capability works in custom HTML with both inline microdata and the script tag.

Things to look out for while testing this feature:

Check that the target audience email addresses are not GSuite emails.
The availability start date must be far off from the end date. If the values of the start date and end date are closer to the current date, then the mail is most likely to appear in the Top Picks of the promotions tab.

##Q. What is the character limit in the dynamic content custom HTML?
The character limit in the dynamic content custom HTML is 1000 characters.

##Q. How do you add Custom fonts in email?
You would need the CleverTap custom HTML builder for your email campaigns.

You can add custom fonts to emails by adding a link tag to the header of your email HTML. It means that the font must be hosted somewhere on the internet. Here is an example:
[block:code]
{
  "codes": [
    {
      "code": "<html>\n<head>\n    <link href=\"https://fonts.googleapis.com/css?family=Roboto\" rel=\"stylesheet\" type=\"text/css\" />\n</head>\n<body>\n<h1 style=\"font-family:'Roboto'\">Test text</h1>\n</body>\n</html>\n",
      "language": "html"
    }
  ]
}
[/block]
Custom fonts may not be supported by all email clients. If you are adding a custom font to emails, you may also want to specify fallback fonts. This ensures that the latter font is picked up if the first font is unavailable. Following is an example:
[block:code]
{
  "codes": [
    {
      "code": "<h1 style=\"font-family: Lato, 'Lucida Grande', Tahoma, Sans-Serif;\">Welcome</h1>\n\n",
      "language": "html"
    }
  ]
}
[/block]
##Q. What does the “Do not stack on mobile devices” mean?  
Answer: Do not stack on mobile devices which will disable the resizing and repositioning of the content per the device screen width. 
**With stacking on Mobile**


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ed477f-campaigns_email_Stack_images.png",
        "campaigns_email_Stack_images.png",
        1080,
        1683,
        "#ecedee"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
**Without stacking on Mobile**


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de9274d-campaigns_email_Not_Stack_images.png",
        "campaigns_email_Not_Stack_images.png",
        1080,
        1120,
        "#e2e4e5"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
##Q. How do you analyze the CTA button for In-app campaigns?
The data for a number of clicks on each CTA button is available under the Analytics section in the dashboard.

 Follow the steps below:

In "Events", query for the "Notification Clicked" event filtered by the campaign ID, then in the result, go to "Trend & Properties"

<<@harsh need a proper screenshot>>

Scroll down to the "Event property" table and select the event property as "wzrk_c2a" from the drop-down to see a distribution of clicks across the various buttons on that respective email campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d452ca-image_7.png",
        "image (7).png",
        1382,
        618,
        "#f1f6f8"
      ],
      "border": true
    }
  ]
}
[/block]
##Q. How do you add a GIF file in an email?
You can add a GIF file using the content field image or custom HTML. 

Follow the steps to add a GIF file:

1. Select the "New Email with drag and drop" template. 
2. From the Content tab, click Image. 
3. Drag and drop this Image icon in the email body 
3. Click [Browse]. You will see the upload option.
4. Upload the GIF file.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5ee8193-Screenshot_2020-07-16_at_6.53.50_PM.png",
        "Screenshot 2020-07-16 at 6.53.50 PM.png",
        1382,
        618,
        "#f8f8f8"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4efbed8-Screenshot_2020-07-16_at_6.58.40_PM.png",
        "Screenshot 2020-07-16 at 6.58.40 PM.png",
        1382,
        618,
        "#ebecf1"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "* Images/Gif must be less than 5 MB. However, we recommend that the media must be less than 1 MB for optimal results. The media may not load in user's inbox because all your users may not have a high-speed internet connection.\n* The media formats supported are JPEG, GIF, and MP4."
}
[/block]
##Q. How do I send a test email notification?
Follow the steps to send a test email notification from the "What" section in the email campaign:
Sender details >  More > Send test email. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f7cf154-campaigns_email_test_mail.png",
        "campaigns_email_test_mail.png",
        1443,
        714,
        "#f8f7f7"
      ],
      "border": true
    }
  ]
}
[/block]
##Q. How can I add a survey link in emails?

CleverTap only tracks the users who have clicked on any of the links present in the email notification. When the user is directed to a specific web page, the details that are entered by the user on that specific page are not captured by CleverTap. 
To download the list of users, {@harsh, to download a list of users who have taken the survey?}you can search  in the “Find People” section:

Notification Clicked > Campaign ID

The survey results are visible on Survey Monkey/the external platform on which you have hosted your survey. {@harsh, this answer does not tell you how to add a survey link in email. There seems to be a disconnect between the question and answer}

#Push Notifications

##Q. Why does the image not render in push notifications for Android?
The image rendering in a push notification is determined by three factors:

1. Image size -The image size must be smaller than 40KB. 
2. User's internet connection -  The push is rendered only with the title and message if it is unable to download the image within  ~10 seconds.
3. CDN (Content Delivery Network) throughput - Check that your CDN for hosting the images is scalable. This is because the OS downloads the image every time a push is sent to a user. For example, if your user base is 5 million users, then you must be able to scale the CDN to support push notifications for such a user base. 


##Q. Why does the image not render in push notifications for iOS?

To render the image push notification for iOS, you must enable the rich media notification in iOS. You can enable Rich Push Notifications via using a Notification Service Extension. This is a separate and distinct binary embedded in your app bundle. Please find the below link to enable the Notification Service Extension.

For more information, see [Apple Notification Service Extension](https://developer.apple.com/documentation/usernotifications/unnotificationserviceextension).

Keywords: Push Notifications, iOS, Rich Media, Image, Not displayed, Not rendered.

##Q: Why am I receiving blank push notifications? 

This may happen if you are custom handling/custom rendering the push notifications and enabled the uninstall tracking. You will need to check for the following:

* The push notifications are not handled by CleverTap SDK and the handling is performed through your custom code. This custom code must read the payload defined by CleverTap and fetch the Title, Message, and other parameters using the keys mentioned in the payload.

* If the custom code is unable to understand the payload defined by CleverTap, then the push notifications are displayed without a message.

* Following is a sample payload for Android that will help to identify the keys and their respective values  for custom push rendering:

[block:code]
{
  "codes": [
    {
      "code": "{\nwzrk_acct_id=CleverTap_Account_ID, \ncustom key=custom value, //custom key values (optional)\nwzrk_acts=[\n{\"l\":\"Action button 1\",\n\"dl\":\"deep link for action button 1\",\n\"id\":\"action id of the action button 1\",\"\nico\":\"Icon resource identifier for action button 1\"}\n], \nnm=the message of the push, //Message text\nnt=title of the push, //Title text\npr=max, \nico=large icon url, \nwzrk_pivot=wzrk_default, \nwzrk_sound=Custom sound file name, \nwzrk_cid=123456, //Notificaiton channel id \nwzrk_nms=Summary text field, // Summary text\nwzrk_rnv=true, \nwzrk_ttl=1586148291, //Time to live in epoch\nwzrk_push_amp=false, \nwzrk_bc=badge icon, \nwzrk_bi=2, \nwzrk_bp=image URL, \nwzrk_ck=collapse notification, //Collapse key\nwzrk_dl=deep link url here, \nwzrk_dt=FIREBASE, \nwzrk_id=0_0, \nwzrk_pn=true, \nwzrk_st=subtitle //Subtitle text\n}",
      "language": "json"
    }
  ]
}
[/block]
* Also, CleverTap sends a silent push notification (blank push) to track App Uninstalls if Uninstall tracking is enabled on the CleverTap dashboard. If you are custom handling the push notifications, that is, you are parsing the payload by yourself and rendering the notifications on the device using your own method, you must check for the `nm` or `nt` tags. These tags in the payload of the push hold the title and message of the push notification. If these tags are empty then the push must not be rendered. The code must identify the silent push notification and the normal push notification.

* If the above is not implemented then the users will get blank push notifications around midnight when the App Uninstall sweep runs on CleverTap.


##Q. Why are Push Impressions not raised?

Check that the push impression event is enabled:

*  Check that the "Push Impressions" event is enabled in Settings > Schema > Event/User Properties. See the Event tab. If the "Push Impressions" event is not enabled, then enable this event with the following steps:
Click on settings > Schema > Events & User properties —> Search for “Push Impressions” and click on it —> Enable the option.
 * Check the SDK version used for Android and iOS. The "Push Impression" event feature is available from 3.5.1 SDK version for android and for iOS it is v3.7.1.
* For iOS, you must also implement an API in your app. For more information, see [Rich Push Notifications](https://developer.clevertap.com/docs/rich-push-notifications). For Android, once your app is on SDK v3.5.1+, the push impression statistics will start showing for qualified users on a push notification campaign because the feature is already enabled in your event settings.

* For custom handling push notification on Android, see [push notification viewed](https://developer.clevertap.com/docs/android#section-push-notification-viewed).

##Q. What is the format of the payload of the push notification for Android and iOS?
Following is an example payload: 
[block:code]
{
  "codes": [
    {
      "code": "{\nwzrk_acct_id=CleverTap_Account_ID, \ncustom key=custom value, \nwzrk_acts=[\n{\"l\":\"Action button 1\",\n\"dl\":\"deep link for action button 1\",\n\"id\":\"action id of the action button 1\",\"\nico\":\"Icon resource identifier for action button 1\"}\n], \nnm=the message of the push, \nnt=title of the push, pr=max, \nico=large icon url, \nwzrk_pivot=wzrk_default, \nwzrk_sound=Custom sound file name, \nwzrk_cid=123456, \nwzrk_nms=Summary text field, \nwzrk_rnv=true, \nwzrk_ttl=1586148291, \nwzrk_push_amp=false, \nwzrk_bc=badge icon, \nwzrk_bi=2, \nwzrk_bp=image URL, \nwzrk_ck=collapse notification, \nwzrk_dl=deep link url here, \nwzrk_dt=FIREBASE, \nwzrk_id=0_0, \nwzrk_pn=true, \nwzrk_st=subtitle\n}\n",
      "language": "json"
    }
  ]
}
[/block]
Following are the keys for the push notification:


[block:parameters]
{
  "data": {
    "h-0": "Key",
    "h-1": "Description",
    "0-0": "wzrk_acct_id",
    "0-1": "CleverTap Account ID",
    "1-0": "custom key",
    "1-1": "Any custom key that the user can add",
    "2-0": "wzrk_acts",
    "2-1": "Action Button Payload",
    "3-0": "nm",
    "3-1": "Notification message",
    "4-0": "nt",
    "4-1": "Notification Title",
    "5-0": "ico",
    "5-1": "Icon resource identifier for an action button",
    "6-0": "wzrk_pivot",
    "6-1": "Variant A or B of A/B Campaign }",
    "7-0": "wzrk_cid",
    "7-1": "Channel id",
    "8-0": "wzrk_nms",
    "8-1": "Summary Text",
    "9-0": "wzrk_rnv",
    "9-1": "This is a flag to raise notification viewed event. If present and not empty, it will raise notification viewed event.",
    "10-0": "wzrk_ttl",
    "10-1": "Time to Live (TTL)",
    "11-0": "wzrk_push_amp",
    "11-1": "Push Amp",
    "12-0": "wzrk_bc",
    "12-1": "Badge icon",
    "13-0": "wzrk_bi",
    "13-1": "badge icon",
    "14-0": "wzrk_bp",
    "14-1": "Image URL",
    "15-0": "wzrk_ck",
    "15-1": "The Collapse key",
    "16-0": "wzrk_dl",
    "16-1": "The Deep Link URL",
    "17-0": "wzrk_dt",
    "17-1": "The service used to send the message, for example, FIREBASE.",
    "18-0": "wzrk_id",
    "19-0": "wzrk_pn",
    "20-0": "wzrk_st",
    "20-1": "subtitle",
    "19-1": "push notification. If present, this notification is sent from CleverTap.",
    "18-1": "The Campaign Id"
  },
  "cols": 2,
  "rows": 21
}
[/block]
##Q. How do you add a small icon in the push notification? 

Sometimes, the small icon may not appear in the notification even if you add the small icon in the Android Manifest file. 

To set the small notification icon for the app see [small notification icon](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon).
You can use the help of your development team to resolve the issue. Check for the following in your app code:

  * Your app must have a small icon file in your drawable resources.
  *  You are using a PNG file and not a JPEG file for the small icon. 
  * The background in your icon file is transparent. 
  * The small icon image must be monochrome without alpha channels ( RGB colors) with 60-70% opacity, that is, white pixels on a transparent backdrop.

For more information, see :
* [set the small notification icon in CleverTap](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon)
* [Image asset studio in Android](https://developer.android.com/studio/write/image-asset-studio)

##Q. What is action ID in android ? 
Android can have only up to 3 action buttons. You must assign an Action ID to each button so that it can be identified by the app. The Action ID is a user-defined string. It is available as a [bundle extra](https://developer.clevertap.com/docs/android#section-action-buttons) on the notification click intent message so that you can identify the action button that is clicked. This is a mandatory field.

This enables users to take multiple actions for the notification. For example, a single media push notification can have two buttons – ‘Buy Now’ and ‘Save for Later’.

For more information, see [action buttons in Android](https://developer.clevertap.com/docs/android#section-action-buttons)

##Q. Why do I receive the same message body twice in a push notification?
This may happen if you are custom handling your push notifications and using the `CleverTapAPI.createNotification()` and `sendNotification()` method in the custom message listener service. The message is displayed twice because both these methods display the notification.

Remove the `sendNotification()` method and use the `CleverTapAPI.createNotification()` to resolve this issue. The `CleverTapAPI.createNotification()` creates a notification that is handled via CleverTap. {@harsh, is the description correct now?}
[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "If you wish to use display the notification through your own code then it must read all the CleverTap's keywords and display the push notification using your custom method."
}
[/block]
##Q. Why does my Notification Clicked and Viewed event rate shows as zero?

Check if you are [custom handling](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling) push notifications. Follow the steps for custom handling:

1. Enable the event toggle from Settings > Events and User properties > Push Impressions (Only for SDK version 3.5.1 and above)

2. Add the following line of code after you render the notification: `CleverTapAPI.getDefaultInstance(this).pushNotificationViewedEvent(extras);`

3. For Notification Clicked, add the following line under  intent: `CleverTapAPI.getDefaultInstance(application).pushNotificationClickedEvent(activity.getIntent().getExtras());`
[block:callout]
{
  "type": "info",
  "body": "The increase in container usage is directly proportional to the Notification Sent event after this feature is turned on.",
  "title": "Note"
}
[/block]
##Q.  Why do push notifications with images truncate the text in the message?
This is expected behavior because Android truncates message text with image. The rendered image shares the space leaving less space available for the message text. There is no fixed character limit for the message text. This depends on the device used to view the push notification. If the user device has a small screen resolution then the message text is cropped after a few words. However, a user may see all the characters on a big-screen resolution.

Ther are two things to bear in mind with creating notifications - big text and a big image.

If you want to see the full text (big text) or you want to add the text in multiple lines, then do either of the following:

  * Send the notification without an image (big image), or
  * Custom handle the push notification at your end to support both, that is, big text and a big image.

##Q. Why do Android users receive two notifications from the same campaign after integrating Xiaomi Push services?
For a greater chance of delivery success, we send a push notification through both Xiaomi Cloud Push and Firebase Cloud Messaging (FCM) push services. If a message is delivered and rendered through one of these push services, the notification from the other cloud service is suppressed by the CleverTap SDK.

If you are custom rendering the Push notifications then Push Notifications are being rendered by your custom code, you will have to implement the Suppression mechanism at your end.

The mechanism should check if a Push notification has already been rendered for the campaign and suppress the Payload from another push service. This will ensure that the user receives only one Push notification for a given campaign.

##Q. Why is my push notification campaign running slowly?
If you feel that the push campaigns are executing slowly then it could be due to either of the following reasons:

* Personalized messages - If personalization is used in the message, then the push notifications will not be sent in batches containing multiple users because the content of the push is different for each user. The push request for each user is made separately and this increases the time to process.

* Throttle - The push campaign can execute slowly as it adheres to the throttle limit that is set for push notifications in the Campaign Limits under Account Settings. The throttle limit specified from the dashboard during the campaign creation is considered throughout the lifetime of the campaign. Throttle for existing campaigns is not updated when the global throttle is updated. The new throttle is considered only for the new campaigns.

##Q. What is the recommended image dimension in push notifications with CTA?

The Aspect ratio: 16:9 and Recommended Size - 533.33 X 300 pixels minimum.
The supported file types are PNG, JPG, and JPEG.
The Maximum size is 40Kb {@harsh, is it Kb or KB?}

We recommend maintaining an Aspect ratio of 16:9. You can adjust the dimensions accordingly. You can also refer to the following link to calculate the aspect ratio: 
https://calculateaspectratio.com

##Q. Where can I update Xiaomi/Huawei credentials?

After you have App secret and package name, you must update it on the CleverTap dashboard. Follow the steps: 

1. Click to settings from the dashboard.
2. Click Channels>  mobile push. The push notification setup page appears.
3. Click Huawei or Xiaomi push notifications and add App secret and package name/App ID.



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f2d6c3-Campaigns_mobile_push_settings_xiaomi_huwaei.png",
        "Campaigns_mobile_push_settings_xiaomi_huwaei.png",
        998,
        1275,
        "#fafafb"
      ]
    }
  ]
}
[/block]
##Q. How can I analyze the CTA button for push campaigns?
<<@harsh, I have drastically changed the description. please review as whole>>
1. Go to Analytics > Funnels. 
2. Select the funnel steps.
3. Click View funnel. 

The stats in the funnel can give you more insight about user clicks:
<<@harsh need screenshots with data and without any annotations>>

The Analyze section for the notification click appears and the results are distributed by the 'wzrk_c2a'  event property.

<<@harsh need screenshots with data and without any annotations>>

You can also query the events dashboard. Follow these steps:

1. Click Analytics > Events
2. Select the "Notification Clicked" event and click the View details button.
3. Click the  "Trend & Properties" tab
4. Scroll down to the "Event property" table and select the event property as "wzrk_c2a" from the list to see a distribution of clicks across the various buttons on that respective  Push campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9973240-Push_notifications_CTA_analyze.png",
        "Push_notifications_CTA_analyze.png",
        1192,
        563,
        "#e6f2f8"
      ],
      "border": true
    }
  ]
}
[/block]
##Q. Will my users get a push notification immediately after their inactive device becomes active?
If the user device is inactive(no Internet or switched off) and the user turns it on again within the Time To Live (TTL) then the push notification is delivered.

##Q: How can I have a small icon instead of a white square box on the top left screen?
The small icon must be set at the code level in the Manifest file. The small icon must be alpha. You can create the icon using the Image Asset Studio tool included in Android Studio.
For more information, see [adding a small icon](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon)

##Q. How can I redirect the users to MWeb when they click the push notification?
To redirect users to MWeb, you can add the URL of the page as a deep link when creating a campaign. The users are redirected to the page specified in the deep link. For example, https://clevertap.com/

##Q. How do I add bulletins message in push notifications?

You can write the message on the next line and the message will be displayed in the same format. {@harsh, did not understand this sentence}

{@harsh, the image is a bit confusing. The title and the text both are labeled test.}



[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If you are custom handling the push notifications then your implementation must to handle such payload and display them as it is. {@harsh, did not understand this sentence}"
}
[/block]
{@harsh, is the code snippet JSON?}
[block:code]
{
  "codes": [
    {
      "code": "{wzrk_acct_id=W44-Z4K-K65Z, nm=1. test\n    2. test\n    3. test, nt=test, wzrk_pivot=wzrk_default, wzrk_cid=123456, wzrk_rnv=true, wzrk_ttl=1593174515, wzrk_push_amp=false, wzrk_bc=, wzrk_bi=2, wzrk_dt=FIREBASE, wzrk_id=0_0, wzrk_pn=true}\n",
      "language": "text"
    }
  ]
}
[/block]
The key for notification is `nm`, where you can file the value of message text.{@harsh, did not understand this sentence}

##Q. How to resolve the popup for installing the HMS core app on non-Huawei devices?

This popup appears on non-Huawei devices after implementing Huawei push notifications. To avoid this popup, check for HMS class on all devices and trigger the push registration service only if `HMSclass` is available on the device. For more information, see the [Developing an App](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/SafetyDetectAppsCheckAPIDevelopment) step in the Huawei documentation. 

##Q.  Why do I see 0% push notifications for Xiaomi and 100% for Firebase (FCM)?
The Xiaomi push notifications may show 0% on campaign stats if all the notifications are delivered through FCM. For a greater chance of delivery success, CleverTap sends a push notification through both the Xiaomi Cloud Push and Firebase Cloud Messaging (FCM) push services. If a message is delivered through any one of these push services, then the notification from the other cloud service is suppressed. There is no priority that is defined for the messaging service and there are no changes to the current flow of FCM. This ensures that the user receives the push notification once.

As the other services are not integrated hence it is showing N/A. {@harsh, what does this mean?} For more information see the Xiaomi push notifications(https://developer.clevertap.com/docs/xiaomi-push-notifications).

##Q. How can I send multiple notifications from the same campaign?
If you select  "Send campaign every time the user qualifies" when creating a campaign, then the user receives multiple notifications from the same campaign.


#Android

##Q. How do I enable debug mode?
You can enable the CleverTap debug logs by placing the following code in the `onCreate` method in your Java file:

[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI.setDebugLevel(CleverTapAPI.LogLevel.DEBUG); //Set Log level to DEBUG log warnings or other important messages\n\nCleverTapAPI.setDebugLevel(199); //This numerical value in brackets can be anything greater than 5.",
      "language": "java"
    }
  ]
}
[/block]
For more information, see [Android debugging](https://developer.clevertap.com/docs/android#section-debugging). 


##Q. How can I add lifecycle callbacks?
If you have a custom application class, call the `ActivityLifecycleCallback.register(this);` before `super.onCreate()` in your class. {@harsh, are these two methods ?}
For more information, see [Initialize CleverTap SDK](https://developer.clevertap.com/docs/android-quickstart-guide#section-step-4-initialize-the-clever-tap-sdk).

##Q. How can I update the location?
CleverTap records two types of geographical information:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/986d84b-Location_record.png",
        "Location_record.png",
        441,
        185,
        "#dddddf"
      ]
    }
  ]
}
[/block]
* Unkown -  The city-level information which is tracked by CleverTap using "MaxMind", a third-party tool that uses reverse IP methodology to map the user's location, based on the device IP. This information is updated on every App Launch. {@harsh, should we mention our third-party tool in customer-facing document?}
* Lat/Long - The latitude and longitude information that you pass to CleverTap. The circle that you've selected on the map, fetches users based on this latitude and longitude that you pass to Clevertap.

To get the users' city, region, and country in on every app launch, allow the CleverTap SDK to collect user locations (which we then collect by reverse-IP lookup via our third-party location provider, MaxMind). Maxmind has an accuracy of 70% in India.

Here's how you can enable the location tracking:

* [Device Network Information Reporting in Android](https://developer.clevertap.com/docs/sdk-changes-for-gdpr-compliance#section-device-network-information-reporting-in-android)

[block:code]
{
  "codes": [
    {
      "code": "cleverTap.enableDeviceNetworkInfoReporting(true);",
      "language": "java"
    }
  ]
}
[/block]
* [Device Network Information Reporting in iOS](https://developer.clevertap.com/docs/sdk-changes-for-gdpr-compliance#section-device-network-information-reporting-in-i-os) 
[block:code]
{
  "codes": [
    {
      "code": "[[CleverTap sharedInstance]enableDeviceNetworkInfoReporting:YES];",
      "language": "objectivec"
    },
    {
      "code": "CleverTap.sharedInstance().enableDeviceNetworkInfoReporting(true)",
      "language": "swift"
    }
  ]
}
[/block]
##Q. Can I send push notifications from both Firebase and CleverTap in my app?

Yes.  You can mention your own listener service that is implemented In the AndroidManifest.xml file. You can then choose to render the notification either from CleverTap or your own service.
For more information, see [Custom Android push notifications](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling).

##Q. Why doesn't CleverTap capture the device token on the first app launch?
 
CleverTap may not receive the push token on the first app launch because of the following reasons:

* Not using CleverTap’s token listener service -  Check that your custom token listener sends out a token to CleverTap immediately. The tokens are fetched on the second app launch. This is a fail-safe in the CleverTap SDK that fetches the token and sends it to CleverTap with the App Launched event.  {@harsh, a fail-safe against what ?} Because the token is not generated at the first app launch, it is not available when the CleverTap SDK checks for it.

Use the following code to enable sending tokens to CleverTap as soon as they are received by your listener. {@harsh, is this code Java?}
[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI.getDefaultInstance(this).pushFcmRegistrationId(token,true);\n\n",
      "language": "text"
    }
  ]
}
[/block]
* Using Firebase 18 or above -  When you upgrade your Firebase messaging dependency version to 18.0 or greater, you must implement a single service for both Token and Message Listener services to get the token on the first app launch. There is no need to implement separate FCMMessageListenerService and FCMTokenListenerService, to get the token on the first app launch.
For more information, see [FCM version 18.0 and above](https://developer.clevertap.com/docs/using-fcm-version-1800-and-above).

##Q. What is the correct format for sending a date-time value in Android? 
The date-time values must be passed in the correct format to be considered as date-time value. Pass the property value in either of the following formats for Android: {@harsh, should it be rather $D_epochinseconds or epochinseconds? Also, why the square brackets and double quotes ?}

* new java.util.Date()
* “$D_EPOCH”

#iOS

##Q. Is there an action ID for iOS, similar to android?

The iOS equivalent for action ID is "category". You can add the name of the category while creating a campaign. Each category must be registered with the app. This category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it. The actual number of actions actually displayed for the category depends on the type of notification delivered. This allows the users to perform multiple actions for the notification. For example, a single media push notification can have two buttons – ‘Buy Now’ and “Save for Later”.

For more information, see [Advanced iOS Push Notifications](https://developer.clevertap.com/docs/ios#section-advanced-ios-push-notifications)

##Q. How to pass push token in manual integration?

You can use the following custom method and pass it inside the `didfinishlaunchwithoption` function of the app delegate file as shown below.
Call the User notification delegate and then add the following code accordingly in your app delegate file.
{@harsh please check the first two lines of the code for objective C and Swift}
[block:code]
{
  "codes": [
    {
      "code": "//registerForPush()\nfunc registerForPush() {\n    // Register for Push notifications\n UNUserNotificationCenter.current().delegate = self\n // request Permissions\n UNUserNotificationCenter.current().requestAuthorization(options: [.sound, .badge, .alert], completionHandler: {granted, error in\n if granted {\n DispatchQueue.main.async {\n UIApplication.shared.registerForRemoteNotifications()\n }\n }\n })\n }",
      "language": "objectivec"
    },
    {
      "code": "//[self registerPush];\n(void)registerPush { \n UNUserNotificationCenter *center = [UNUserNotificationCenter currentNotificationCenter];\n \n [center requestAuthorizationWithOptions:(UNAuthorizationOptionSound | UNAuthorizationOptionAlert | UNAuthorizationOptionBadge) completionHandler:^(BOOL granted, NSError * _Nullable error){\n if( !error ){\n dispatch_async(dispatch_get_main_queue(), ^(void) {\n [[UIApplication sharedApplication] registerForRemoteNotifications];\n });\n }\n }];\n}  ",
      "language": "swift"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The methods may vary according to the iOS version.",
  "title": "Note"
}
[/block]
##Q. Why does the word"[modified]" appear in the title for iOS push notifications?
The word"[modified]" appears in push notifications, if you enable the advanced option in a campaign. Implement the Rich Push notifications in a future update to address this issue. If you are not using Rich Push then uncheck the advanced option that you have selected in the campaign.

##Q. What is the correct format for sending a date-time value in iOS? 

The date-time values must be passed in the correct format to be considered as date-time value. Pass the property value in either of the following formats for iOS: {@harsh, should it be rather $D_epochinseconds or epochinseconds?, Also, why the square brackets and double quotes ?}

* [NSDate date]
* “$D_EPOCH”

##Q. How do I disable IDFA tracking in iOS?
To disable the IDFA tracking, follow the steps:
1. Check that you have not added the `CleverTapUseIFA` flag in the info.plist file.
2. Remove the AdSupport framework from your build if you have added that {@harsh, not sure what That means here} in your linked libraries
3. When submitting your app to the app store, you are asked if your app supports IDFA. Select NO.