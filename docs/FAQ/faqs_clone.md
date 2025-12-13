---
title: FAQs_new_updates_WIP
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
#Push Notification Errors in Android

##Invalid FCM API Key

An invalid FCM API key error is displayed when the FCM API key in the CleverTap dashboard is incorrect. You will not be able to send any notifications until the FCM API key is added to your settings.

Follow the steps below to update the FCM API key:
1. Navigate to *Settings* > *Engage* > *Mobile Push*. 
2. Update the valid FCM API key as it is displayed in your Firebase project. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fbb0429-FAQ_FCM_Credentials.png",
        "FAQ_FCM_Credentials.png",
        972,
        591,
        "#f9fafb"
      ],
      "caption": "",
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
For more information, refer to [Find Your FCM Sender ID & FCM Server API Key](https://developer.clevertap.com/docs/find-your-fcm-sender-id-fcm-server-api-key).

##FCM Token Invalid

The FCM token is not linked to any device that has your app. Since the token is not a valid one, notifications will not be delivered. Check the format of the FCM project number and registration token you pass on to CleverTap.

For more information, refer to [Troubleshooting Push Notifications](https://developer.clevertap.com/docs/troubleshooting-push-notifications).

##FCM Error

This is a Firebase (Android) error. The FCM error is not part of the standard published list and is sometimes incorrectly identified as an Android bug.

##FCM Not Registered

Most likely, the users have uninstalled the app from their device. One of the common non-technical errors is *Undelivered due to App Uninstall* in campaign reports. This error occurs when the users uninstall your app while you are trying to reach them via a push notification.

The *FCM Not Registered* error occurs in two scenarios:

  * When the users have uninstalled your app and you are trying to schedule a push notification to them.
  * When users have cleared the device cache memory, which in turn removes the token from the device.

##FCM Mismatch Sender ID

An FCM sender ID mismatch occurs when the sender ID entered in the CleverTap dashboard under *Push Notification* settings does not match with the sender ID in the FCM project for your app created on Firebase.

There are three places where these sender ID/server keys have to be matched. You must match the sender ID/server keys at the following three locations:

  *  App-level which registers token with the said FCM sender ID mentioned.
  *  In the CleverTap dashboard.
  *  FCM project.

If you have checked the sender ID for mismatch and the error still persists, check the following: 

  * Does the app build and the CleverTap account contain mismatched sender IDs?
  * Do you have multiple Firebase projects?
  * Do you have multiple Platform IDs if your app is using two Firebase projects?


#Push Notification Errors in iOS

 ##APNS Device Token Does Not Match The Specified Topic 

*Apple Push Notification* service (APNs) returns this when the device token does not match the specified topic.

In the context of CleverTap, you get this error when you try to send the notification with a wrong certificate. Check that you are using a production certificate for the production environment to avoid unsatisfactory configurations.

Check the provisioning profile used to deploy the app and send the device token to the CleverTap dashboard. To avoid this error, the *App Bundle ID* of the provisioning profile and the CleverTap push certificate (p12 certificate) must match.

##APNS Unregistered

The *Push* notification delivery to the target has failed as the device token is inactive for the specified topic. Since the device token is not valid/inactive, nothing can be done that will deliver the notification unless the user installs the app again.

##APNS Topic Disallowed

The topic is currently the bundle identifier of the target application on an iOS device. The *APNS Topic Disallowed* error appears when you specify the incorrect *App Bundle ID* in the *Account Settings*. 

For more information, refer to [Registering Your App with APNs](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns) in the Apple documentation.

To resolve this error, check the value of the *App Bundle ID* and *APNs push mode* you have configured in the CleverTap Dashboard under *Push Settings*.

##APNS Temporarily Blacklisted

You are temporarily blacklisted from sending push notifications to the device which can be due to sending bad tokens. The push notification will not be delivered for some duration.

##APNS Failed Delivery 

The notification to the device sent from CleverTap failed to deliver due to either of the following reasons:
  * The app was uninstalled and the token is no longer valid.
  * You have sent too many back-to-back notifications very quickly to the same device.

If the user has uninstalled the app, not much can be done to deliver the notification.
 
For more information, refer to [Handling Notification Responses from APNs](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/handling_notification_responses_from_apns) in the Apple documentation.

##APNs Bad Device Token

The push notification delivery to the target device has failed due to an invalid token. The APNs bad device token error occurs when there is a mismatch between the APNs push mode on your app and the CleverTap dashboard. 

For example, you have set the APNs push mode in your app to *development* stage and in the CleverTap dashboard, you have set up to *production* stage. 

To check your CleverTap dashboard APNs push mode, navigate to *Settings* > *Engage* > *Mobile Push* > *iOS*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4110924-New_final_Push_Notification_iOS_API_Key.png",
        "New final Push Notification iOS API Key.png",
        939,
        650,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]
#Campaign Errors

##SMS Errors

An SMS error is a common campaign error that occurs while scheduling the SMS campaign. The SMS error appears if the SMS service provider’s endpoint is unavailable. It is applicable to generic integrations and MSG91 (SMS provider).

The SMS error shows the following message: 

"Error java.net.SocketTimeoutException: Read timed out for message." It is referred to as the "SocketTimeoutException" error.

An SMS error displays when CleverTap sends the SMS payload to the SMS provider’s endpoint, but it does not get an acknowledgment within 15 seconds. 

You can view the errors within the campaign reports under the *Error* section. The SMS error appears under the *Technical Errors* category.
[block:callout]
{
  "type": "info",
  "body": "The issue generally means a socket timeout exception. Sometimes, it can also mean a connection request exception.",
  "title": "Note"
}
[/block]
For other integrated vendors, we have the following equivalent errors: 
* Exotel server error
* Twilio server error
* Gupshup server error
* Netcore service error
* Nexmo SMS error

##Web Push Unsubscribed

The error "BrowserUnsubscribed" appears after your app users unsubscribe themselves for web push notifications from Chrome browser settings. 

When you try to engage these unsubscribed users through web push, the "BrowserUnsubscribed" error appears.

##Enabling Push Impressions

To enable *Push impressions*, follow the steps below:
1. Go to *Settings* > *Schema* > *Events*.
2. Search for *Push Impressions*, then click on the vertical ellipsis.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ebf8ae7-Push_Impression_event_FAQ.png",
        "Push Impression event FAQ.png",
        1161,
        454,
        "#f7f7f9"
      ]
    }
  ]
}
[/block]
3. Click on **Setup push impressions**.
4. Click on **Save** to enable the option.

##Daily Limit Exceeded

While creating a recurring push campaign, you can set the daily limit. For example, you can set a daily send limit to 10,000 per day after which you get a *Daily limit Exceeded* error. You can also set an overall cap limit to 1,00,000 users after which the campaign will stop.

You would generally set a daily limit in a triggered campaign where you are using a live segment. These campaigns are triggered based on an event and therefore, you would want a daily limit for your campaigns. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7583368-New_final_Campaigns_per_day.png",
        "New final Campaigns per day.png",
        1385,
        693,
        "#faf9f9"
      ],
      "border": true
    }
  ]
}
[/block]
You can set the campaign limits within the *Who* section while creating the campaign.

##Per Run Limit Exceeded

The *Per Run Limit* is a limit enforced on the number of users that are sent in one campaign run. For example, you can set a maximum segment limit to 100000 users and the campaign stops running after the set limit for each run.

You see the *Per Run Limit Exceeded* error when the campaign stops running after the number of qualified users exceeds the set limit. 

You would generally set a per run limit for past behavior and custom list segments. This is because the campaign is sent to all the qualified users based on their past actions. Therefore, you would want a per run limit for these campaigns.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4906675-New_final_Campaigns_per_run.png",
        "New final Campaigns_per_run.png",
        1388,
        710,
        "#f9f9f9"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
You can set this maximum segment size from the *Who* section while creating the campaign.

##Q. Why is the reachability for my campaigns so low?

When you create a segment, you can view the reachability of this segment across all channels such as, *Web Push*, *Mobile Push*, *SMS*, *Email*, and *Audiences*. This helps you to check the reachability of your campaigns even before you create them.  
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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d7f417-New_final_Segment_Reachability.png",
        "New final Segment Reachability.png",
        592,
        407,
        "#fafafc"
      ]
    }
  ]
}
[/block]
Some of the reasons that may affect your *Mobile Push* reachability include:
  * Token Not Present: One of the key reasons for low reachability is because the push token is not available in the user profile.
  * User Unsubscribe: The user may have unsubscribed from your app and does not want to receive push notifications. 
  * Token Not Generated: The token did not generate on the first app launch.
  * App Uninstall: User has uninstalled the app.

##Q. How does the *User DND Set* error occur?

The *User DND Set* error occurs when you qualify users for a campaign even though they have unsubscribed on the target device. This error informs you that these users have been passed into the error bucket. 

##Q. What is the *Frequency Caps Exceed* error? 

The *Global Frequency* feature restricts the maximum number of messages you can schedule each day for your user and across different channels.

Go to *Settings* > *Setup* > *Campaign limits* to cap the frequency for various channels. 

From this page, you can define the number of messages you want to send to each user in X number of days. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc18f57-New_final_Previous_Campaigns_global_frequency.png",
        "New final Previous Campaigns_global_frequency.png",
        945,
        604,
        "#f9f9fb"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
You can also specify the *Dwell time* which is the gap you want to keep between two messages, and *Throttle* which controls the flow of your messages. 

For more information on dwell time, refer to [Dwell Time Between Messages](https://docs.clevertap.com/docs/messaging-frequency-caps#section-dwell-time-between-messages).

For more information on throttling, refer to [Throttle](https://docs.clevertap.com/docs/messaging-frequency-caps#section-throttle).

Now when you create a campaign and you want to disable the *Global frequency limit*, clear the *Global Campaign Limit* option under the *Who* section. The *Global Campaign Limit* is enabled by default.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/17c411a-New_final_Campaigns_global_campaign_limits.png",
        "New final Campaigns_global_campaign_limits.png",
        1377,
        695,
        "#f8f7f6"
      ],
      "border": true
    }
  ]
}
[/block]
#Dashboard Errors

 ##Q. How can I upload a CSV file from the dashboard?

You can bulk upload user profiles using the CSV Upload feature. You can also use this feature to add or update information for existing user profiles.

Follow the steps below to upload the CSV file in your CleverTap dashboard:

1. Login to your CleverTap account, and then click the *Settings* button.
2. Click on the **CSV Uploads** button.
3. Click the **Import new profiles from CSV** button.
4. Select the CSV file from your computer, and then click the **Upload** button.
5. Enter a name for the upload.

Your CSV upload is processed in near real-time. After the uploaded CSV is processed, the status for that upload is changed to *completed*.

For more information on CSV upload, refer to [CSV Upload](doc:csv-upload).

##Q. How can I delete the events data from the dashboard without discarding events?

You can simply reset the DRP for each event. All the event data beyond the selected date range is discarded. 

For example, if you set the DRP of an event to 12 months, we will store the data for the past 12 months. All the data prior to the 12 months are deleted. You can optimize your container and avoid flooding it with too much data.  

Follow these steps to adjust the DRP for each event:

1. Go to *Settings* > *Schema* > *Events*.
2. Click on the vertical ellipsis of the event for which you want to adjust/reduce the DRP.
3. Click **Set DRP**.
3. Choose the storage time accordingly.
4. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a23f436-New_final_Settings_DRP_Limit.png",
        "New final Settings_DRP_Limit.png",
        1163,
        568,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "body": "Analyze your data before reducing the DRP. Only remove the data that will not affect your campaigns. The maximum reduction in data DRP is up to three months.",
  "title": "Note"
}
[/block]
#Events and User Profiles

##Q. How can I export data from CleverTap?

You can export the data from CleverTap using one of the three methods below:

* S3 Export (AWS) -  You can export your event and profile data in the AWS S3 bucket using CleverTap Data Exports. For more information on using our data export, refer to [Data Export to AWS S3](doc:data-export-to-aws-s3).

* Export via API - You can export your events and user data with our APIs. For more information, refer to [API Overview](https://developer.clevertap.com/docs/api-overview).

* Find people - You can download the profile data directly from the CleverTap dashboard through the *Find People* page with the following steps:

 1. Navigate to *Segments* > *Find People*.
 2. Define the criteria that you want to export, then click **View Details**.
 3. Click on the download icon below *Total users* to initiate the export.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0b238d-Final_new_FAQs_Events_and_Profiles_Export_data.png",
        "Final new FAQs_Events_and_Profiles_Export_data.png",
        1167,
        321,
        "#f4f5fa"
      ],
      "border": true
    }
  ]
}
[/block]
#Webhooks

##Q. What is a *Webhook Dispatched Failed* error?

The *Webhook Dispatched Failed* error occurs when CleverTap server does not receive a "200 OK" response. A "200 OK" response is an acknowledgment from the REST API server that the API request was received successfully. 

An error can occur in either of the three scenarios:

  * When CleverTap sends the payload to your endpoint and we do not receive a "200 OK" response after retrying 3 times after a wait of 15 seconds. 
  * When CleverTap sends the payload and your endpoint health is down.
  * When you may receive the payload at your endpoint but not send a "200 OK" response to CleverTap server within the timeout frame of 1 second. CleverTap displays a *Webhook Dispatched Failed* error in this case.

As a best practice, we recommend to queue the payload at your end and provide us a "200 OK" in response.

#Identity

##Q. How does Clevertap calculate unique users from the dashboard?

CleverTap identifies and calculates users via multiple steps.

### Creation of a Profile

A user profile is created when a user installs an app and the CleverTap SDK is initialized. 

For example, a user installs the app in device 1 and an anonymous profile A is created. After the user logs in to the app, all the user data is updated to the user's profile, and the profile is now marked as identified.

### Merging of Profiles

If the user installs the app on another device, that is device 2, then another anonymous profile is created, say Profile B.

For example, when the user logs in from device 2, then the profile B is then merged with Profile A.
All the events from device 2 after the user login are now pushed to Profile A.

### Profiles After Merging

When we run a query on the dashboard for any pre-login event, the exact number of events are displayed; however, CleverTap still counts both profiles. This means the count of users for the same event will be 2 (Profile A and Profile B). 

We determine all the possibilities and perform a best-case scenario to show all the events for the same user, which is Profile A. The anonymous profile is displayed in grey color. 

The events before login are not mapped again to the profile A. They are maintained on the anonymous profile.

##Q. What is a *Duplicate Platform ID* error?

The *Duplicate Platform ID* error occurs in one of the following scenarios:

  * When a single token is assigned to multiple profiles and both the profiles qualify for the campaign. CleverTap sends the notification to the profile that qualifies first, and the other profile is marked as a *Duplicate Platform ID*.
  * When the same mobile number is assigned to multiple profiles and they qualify in your campaign. Only one profile receives the notification, and the other profiles are marked as a *Duplicate Platform ID*.

#Settings

##Q. What is CleverTap DRP?

The CleverTap DRP stands for data retention policy which is the duration for which you want to store your data with CleverTap. The CleverTap DRP is only applicable for events and user profile data. 

The data retention policy for user profile includes identifiers, system properties, and custom properties. The data retention policy for user profiles can store a current snapshot of a user profile forever. 

However, the data retention policy for events includes system and custom events. The data retention policy for events depends on both the customer plan type and the setting defined in the CleverTap dashboard.

If you want to check the DRP of all the events and user properties related to your account, navigate to *Events and User Properties* under the *Settings* section. 
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
DRP works on the concept of a rolling window and the default DRP is set to two months. For example, if DRP was set on January 1, 2000, then the data will be available until March 1, 2000. After this March date, the data will be dropped and will not be available.

Refer to the following table to understand DRP by different plan type:

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
    "1-3": "Yes, you can update the DRP for each event type. The minimum DRP that can be set is 3 months.",
    "2-3": "Yes, you can update the DRP for each event type. The minimum DRP that can be set is 3 months."
  },
  "cols": 4,
  "rows": 3
}
[/block]
#CSV Uploads

CSV uploads - identity passed as *Identity*.

Uploading your historical user data via CSV is quick and simple. However, note the following key pointers before uploading your user data via CSV: 

  * The identity field must be defined as *identity* with a lowercase *i* and not *Identity*.
  * The *identity* field is a mandatory column. 
  * Check that your CSV complies with the CSV standards, otherwise the upload will be denied.
  * You can download the sample CSV file for a quick check from the *Settings* section under *CSV uploads*.

Below is a sample CSV:
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
##Q. How do I find IPs to send out emails, webhooks, SMS, and push notifications?
You can find the IPs for your region such as, *In*, *Sg*, and *Eu* under *Settings* > *Integration* > *Push Notification*. The IPs are only visible under *Push Notifications*; however, these are the same IPs used for all the engagement channels. The IPs in the *Integration* setup of the new dashboard is visible under *Settings* > *Engage*> *Channels* > *Mobile Push* > *FCM credentials*. Click on **FCM credentials** to expand it and you can see the IPs on the right.

##Q. How do you handle unsubscribe and bounce for callbacks, such as Mandrill or SendGrid?
CleverTap must receive notification for any email that is classified as bounced,  rejected, or user unsubscribed. We do not attempt any further deliveries to mailboxes. 

For more information, refer to [Sendgrid Bounces, Rejections, and Unsubscriptions](https://docs.clevertap.com/docs/sendgrid#section-step-2-bounces-rejections-and-unsubscriptions) and [Mandril Bounces, Rejections, and Unsubscriptions](https://docs.clevertap.com/docs/mandrill#section-step-2-bounces-rejections-and-unsubscriptions).

A service provider tracks any user unsubscribes using the unsubscription link in your email. The service provider then sends this information to CleverTap through the callback URL. 

The communication preference for users is marked as false (MSG_Email=False). 
The hard bounce and unsubscribed users both fall under unsubscription. Follow the steps below to find the number of users who have unsubscribed via email:

1. Go to *Segments* > *Find People*. 
2. From the *Display* common properties, select *Reachability* > *Unsubscribed* > *Yes*.

##Q. How do you annotate an email?
Email annotations in the *Promotions* tab bring email messages to life with images, deals, expiration dates, and more. The email annotation can be performed in the drag-and-drop email editor and also in the custom HTML email editor.

Use the <meta> tag in the drag-and-drop editor to annotate an email.  Below is the sample code that can be used in the HTML block of the drag-and-drop editor:

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
For custom HTML implementation, refer to [Get started: How to annotate your email](https://developers.google.com/gmail/promotab/overview) in the Google documentation. The *Promotions* tab capability works in custom HTML with both inline microdata and the script tag.

When you test this feature, be aware of the following:

* Check that the target audience email addresses are not GSuite emails.
* The availability start date must be far off from the end date. If the values of the start date and end date are closer to the current date, then the mail is most likely to appear in the *Top Picks* of the *Promotions* tab.

##Q. How do you add custom fonts in email?
You need the CleverTap custom HTML builder for your email campaigns.

You can add custom fonts to emails by adding a link tag to the header of your email HTML. It means the font must be hosted somewhere on the internet. Below is an example:
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
Custom fonts may not be supported by all email clients. If you are adding a custom font to emails, you may also want to specify fallback fonts. This ensures the latter font is picked up if the first font is unavailable. 

Below is an example:
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
##Q. What does the *Do not stack on mobile devices* mean?  
Do not stack on mobile devices alerts you it will disable the resizing and repositioning of the content per the device screen width. 

**With Stacking on Mobile**


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
**Without Stacking on Mobile**


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

##Q. How do you add a GIF file in an email?
You can add a GIF file using the content field image or custom HTML by following the steps below:

1. Select the *New Email with drag and drop* template. 
2. From the *Content* tab, click **Image**. 
3. Drag and drop the image icon in the email body. 
3. Click **Browse**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f1ef5d-New_final_GIF_file_Browse.png",
        "New final GIF file Browse.png",
        1322,
        544,
        "#fafafb"
      ],
      "caption": ""
    }
  ]
}
[/block]
4. Click **Upload** and select your GIF file.
5. In the *File manager*, find your GIF file and click **Insert**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75a7d1b-New_file_GIF_file_Upload.png",
        "New file GIF file Upload.png",
        1318,
        547,
        "#eeedf3"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "* Images/GIFs must be less than 5 MB. However, we recommend the media must be less than 1 MB for optimal results. The media may not load in user's inbox because all your users may not have a high-speed internet connection.\n* The media formats supported are JPEG, GIF, and MP4."
}
[/block]
##Q. How do I send a test email notification?
To send a test email notification from the *What* section in the email campaign, navigate to *Sender details* >  *More* > *Send test email*. 
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
##Q. Can I integrate an email provider that is not listed in documents?
Yes. You can use Generic SMTP to integrate any email provider of your choice. For more information, see [Generic SMTP](https://docs.clevertap.com/docs/generic-smtp).

#Push Notifications

##Q. Why does the image not render in push notifications for Android?
The image rendering in a push notification is determined by three factors:

1. Image size - There is no size limit as long as there is a stable internet connection; however, if there is an unstable internet connection, the chance of failure when downloading images is higher, therefore smaller size images are recommended. 
2. User's internet connection - The push is only rendered with the title and message if it is unable to download the image within around 10 seconds. 
3. CDN (Content Delivery Network) throughput - Check that your CDN for hosting the images is scalable. This is because the OS downloads the image every time a push is sent to a user. For example, if your user base is 5 million users, then you must be able to scale the CDN to support push notifications for this user base. 

##Q. Why does the image not render in push notifications for iOS?

To render the image push notification for iOS, you must enable the rich media notification in iOS. You can enable *Rich Push Notifications* by using a notification service extension. This is a separate and distinct binary embedded in your app bundle. 

To enable the notification service extension, refer to [UNNotificationServiceExtension](https://developer.apple.com/documentation/usernotifications/unnotificationserviceextension) in the Apple documentation.

##Q. Why am I receiving blank push notifications? 

This may happen if you are custom handling/custom rendering the push notifications and enabled the uninstall tracking. You need to check for the following:

* The push notifications are not handled by CleverTap SDK and the handling is performed through your custom code. This custom code must read the payload defined by CleverTap and fetch the *Title*, *Message*, and other parameters using the keys mentioned in the payload.

* If the custom code is unable to understand the payload defined by CleverTap, then the push notifications are displayed without a message.

* Below is a sample payload for Android that can help to identify the keys and their respective values  for custom push rendering:

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
* Also, CleverTap sends a silent push notification (blank push) to track *App Uninstalls* if *Uninstall* tracking is enabled on the CleverTap dashboard. If you are custom handling the push notifications, you are parsing the payload by yourself and rendering the notifications on the device using your own method, you must check for the `nm` or `nt` tags. These tags in the payload of the push hold the title and message of the push notification. If these tags are empty, then the push must not be rendered. The code must identify the silent push notification and the normal push notification.

* If the above is not implemented, then the users will get blank push notifications around midnight when the *App Uninstall* sweep runs on CleverTap.

##Q. Why are push impressions not raised?

Check that the push impression event is enabled with the following steps:
1. Go to *Settings* > *Schema* > *Events*.
2. Search for *Push Impressions*, then click on the vertical ellipsis.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ebf8ae7-Push_Impression_event_FAQ.png",
        "Push Impression event FAQ.png",
        1161,
        454,
        "#f7f7f9"
      ]
    }
  ]
}
[/block]
3. Click on **Setup push impressions**.
4. Click on **Save** to enable the option.

Check the SDK version used for Android and iOS. The *Push Impression* event feature is available from 3.5.1 SDK version for Android and for iOS, it is v3.7.1.

For iOS, you must also implement an API in your app. For more information, refer to [Rich Push Notifications](https://developer.clevertap.com/docs/rich-push-notifications). For Android, once your app is on SDK v3.5.1+, the push impression statistics will start showing for qualified users on a push notification campaign because the feature is already enabled in your event settings.

For more information, refer to [Custom Android Push Notifications Handling](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling).

##Q. What is the format of the payload of the push notification for Android?
Below is an example payload for Android: 
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"wzrk_acct_id\": \"CleverTap_Account_ID\",\n  \"custom key\": \"custom value\",\n  \"wzrk_acts\": [\n    {\n      \"l\": \"Action button 1\",\n      \"dl\": \"deep link for action button 1\",\n      \"id\": \"action id of the action button 1\",\n      \"ico\": \"Icon resource identifier for action button 1\"\n    }\n  ],\n  \"nm\": \"the message of the push\",\n  \"nt\": \"title of the push\",\n  \"pr\": \"max\",\n  \"ico\": \"large icon url\",\n  \"wzrk_pivot\": \"wzrk_default\",\n  \"wzrk_sound\": \"Custom sound file name\",\n  \"wzrk_cid\": \"Notification Channel ID\",\n  \"wzrk_nms\": \"Summary text field\",\n  \"wzrk_rnv\": true,\n  \"wzrk_ttl\": 1586148291,\n  \"wzrk_push_amp\": false,\n  \"wzrk_bc\": 1,\n  \"wzrk_bi\": \"badge_icon\",\n  \"wzrk_bp\": \"image URL\",\n  \"wzrk_ck\": \"collapse notification\",\n  \"wzrk_dl\": \"deep link url here\",\n  \"wzrk_dt\": \"FIREBASE\",\n  \"wzrk_id\": \"0_0\",\n  \"wzrk_pn\": true,\n  \"wzrk_st\": \"subtitle\"\n}\n",
      "language": "json"
    }
  ]
}
[/block]
The above payload is received as bundle data and JSON is only for representation purposes.

Below are the keys for the push notification:

[block:parameters]
{
  "data": {
    "h-0": "Key",
    "h-1": "Description",
    "0-0": "wzrk_acct_id",
    "0-1": "CleverTap account ID",
    "1-0": "custom key",
    "1-1": "Any custom key the user can add",
    "2-0": "wzrk_acts",
    "2-1": "Action button payload",
    "3-0": "nm",
    "3-1": "Notification message",
    "4-0": "nt",
    "4-1": "Notification title",
    "5-0": "ico",
    "5-1": "Icon resource identifier for an action button",
    "6-0": "wzrk_pivot",
    "6-1": "Variant A or B of A/B campaign",
    "7-0": "wzrk_cid",
    "7-1": "Notification channel ID",
    "8-0": "wzrk_nms",
    "8-1": "Summary text",
    "9-0": "wzrk_rnv",
    "9-1": "A flag to raise notification viewed event. If present and not empty, it will raise a notification viewed event.",
    "10-0": "wzrk_ttl",
    "10-1": "Time to live (TTL)",
    "11-0": "wzrk_push_amp",
    "11-1": "Push amp",
    "12-0": "wzrk_bc",
    "12-1": "Badge count",
    "13-0": "wzrk_bi",
    "13-1": "Badge icon",
    "14-0": "wzrk_bp",
    "14-1": "Image URL",
    "15-0": "wzrk_ck",
    "15-1": "Collapse key",
    "16-0": "wzrk_dl",
    "16-1": "Deep link URL",
    "17-0": "wzrk_dt",
    "17-1": "Service used to send the message (e.g. FIREBASE)",
    "18-0": "wzrk_id",
    "19-0": "wzrk_pn",
    "20-0": "wzrk_st",
    "20-1": "Subtitle",
    "19-1": "Push notification. If present, this notification is sent from CleverTap.",
    "18-1": "Campaign ID",
    "21-0": "wzrk_pid",
    "21-1": "Refers to Campaign ID with the date of the campaign creation."
  },
  "cols": 2,
  "rows": 22
}
[/block]

##Q. What is the format of the payload of the push notification for iOS?
Below is an example payload for iOS: 
[block:code]
{
  "codes": [
    {
      "code": "[CleverTap]: Handling notification: {\n  \"W$dt\" = APPLE;\n  \"W$id\" = \"1591036839_20200601\";\n  \"W$pivot\" = \"wzrk_default\";\n  \"W$rnv\" = 1;\n  aps =   {\n    alert =     {\n      body = Testing;\n      title = Campaign;\n    };\n    \"mutable-content\" = 1;\n    sound = default;\n  };\n  \"ct_mediaType\" = image;\n  \"ct_mediaUrl\" = \"https://formpicture.com/photo.png\";\n  \"wzrk_acct_id\" = \"TEST-Z48-Z75-785Z\";\n  \"wzrk_dl\" = \"https://www.google.com\";\n}\n",
      "language": "json"
    }
  ]
}
[/block]
Below are the keys for the push notification:
[block:parameters]
{
  "data": {
    "h-0": "Key",
    "h-1": "Description",
    "0-0": "W$dt",
    "0-1": "Notification service",
    "1-0": "W$id",
    "1-1": "Campaign ID_date",
    "2-0": "W$pivot",
    "2-1": "Variant",
    "3-0": "W$rnv",
    "3-1": "Raises notification viewed",
    "4-0": "body",
    "4-1": "Notification message",
    "5-0": "title",
    "5-1": "Notification title",
    "6-0": "mutable-content",
    "6-1": "Value is 1 if enabled and 0 if disabled",
    "7-0": "sound",
    "7-1": "Notification sound (default is OS)",
    "8-0": "ct_mediaType",
    "8-1": "Type of media",
    "9-0": "ct_mediaUrl",
    "9-1": "Media link",
    "10-0": "wzrk_acct_id",
    "10-1": "Account ID",
    "11-0": "wzrk_dl",
    "11-1": "Deeplink URL"
  },
  "cols": 2,
  "rows": 12
}
[/block]
##Q. How do you add a small icon in the push notification? 

Sometimes, the small icon may not appear in the notification even if you add the small icon in the Android manifest file. 

To set a custom notification icon (only for the small icon), add the following metadata entry in your AndroidManifest.xml:
[block:code]
{
  "codes": [
    {
      "code": "<meta-data\n    android:name=\"CLEVERTAP_NOTIFICATION_ICON\"\n    android:value=\"ic_stat_red_star\"/> <!-- name of your file in the drawable directory without the file extension. -->\n",
      "language": "xml"
    }
  ]
}
[/block]
If the small icon still does not appear, check the following in your Android project: 
 * Your app must have a small icon file in your drawable resources.
 *  You are using a PNG file and not a JPEG file for the small icon. 
 * The background in your icon file is transparent. 
 * The small icon image must be monochrome without alpha channels (RGB colors) and with 60-70% opacity such as, white pixels on a transparent backdrop.

For more information, refer to [Set the Small Notification Icon](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon) and [Create App Icons with Image Asset Studio](https://developer.android.com/studio/write/image-asset-studio) in the Android documentation.

##Q. What is an *Action ID* in Android? 

For Android push notifications, you can add up to three action buttons. You can define the title, deep-link, and the action ID of each button. 

The application uses the value of the action ID to identify the button that was clicked.

The default behavior (i.e., when closing the notification is handled using CleverTap SDK) for clicking on the action button is that the user is directed to the deep link or application and the notification is dismissed automatically.

You can handle the closing of the notification yourself at the code level and only then, your app can get the action ID values. Based on the action ID value of the action button clicked, you can perform any operations as per your requirement.

For more information on Android, refer to [Action Buttons](https://developer.clevertap.com/docs/android#section-action-buttons).

For iOS:
You must implement a category for iOS. You can enter the name of the category while creating the campaign. Each category must be registered with the app. Each such category is associated with actions the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it, although the number of actions actually displayed depends on the type of notification delivered. This enables users to take multiple actions for the notification. For example, a single media push notification can have two buttons such as, *Buy Now* and *Save for Later*.

For more information on iOS, refer to [Advanced iOS Push Notifications](https://developer.clevertap.com/docs/ios#section-advanced-ios-push-notifications).

##Q. Why do I receive the same message body twice in a push notification?

If you are custom handling your push notifications and using CleverTapAPI.createNotification() and your own function (for example: `sendNotification()`) for displaying notifications in the custom message listener service, then the message may be sent twice. Remove the `sendNotification()` method and use the `CleverTapAPI.createNotification()` method only. The `CleverTapAPI.createNotification()` method creates a notification that is handled via CleverTap.
[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "If you want to display the notification using your own function, then remove the call to the CleverTap SDK for displaying the notification. This ensures that multiple calls are not made to display a push."
}
[/block]
##Q. Why do my *Notification Clicked* and *Viewed event* rates show as zero?

Check if you are [custom handling](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling) push notifications. Follow the steps below for custom handling:

1. Enable the event toggle from *Settings* > *Events and User properties* > *Push Impressions* (Only for SDK version 3.5.1 and above).

2. Add the following line of code after you render the notification: 
[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI.getDefaultInstance(this).pushNotificationViewedEvent(extras);\n",
      "language": "text"
    }
  ]
}
[/block]
3. For *Notification Clicked*, add the following line under intent: 
[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI.getDefaultInstance(application).pushNotificationClickedEvent(activity.getIntent().getExtras());\n\n",
      "language": "text"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The increase in container usage is directly proportional to the *Notification Sent* event after this feature is turned on.",
  "title": "Note"
}
[/block]
##Q. Why do push notifications with images truncate the text in the message?
This is an expected behavior because Android truncates message text with image. The rendered image shares the space leaving less space available for the message text. There is no fixed character limit for the message text. This depends on the device used to view the push notification. If the user device has a small screen resolution, then the message text is cropped after a few words. However, a user may see all the characters on a big-screen resolution.

When creating notifications, bear in mind big text and a big image.

If you want to see the full text (big text) or you want to add the text in multiple lines, then do either of the following:

  * Send the notification without an image (big image).
  * Custom handle the push notification at your end to support both such as, big text and a big image.

##Q. Why do Android users receive two notifications from the same campaign after integrating Xiaomi Push services?
For a greater chance of delivery success, we send a push notification through both Xiaomi Cloud Push and Firebase Cloud Messaging (FCM) push services. If a message is delivered and rendered through one of these push services, the notification from the other cloud service is suppressed by the CleverTap SDK.

If you are custom rendering the push notifications, then push notifications are being rendered by your custom code, you will have to implement the suppression mechanism at your end.

The mechanism should check if a push notification has already been rendered for the campaign and suppress the payload from another push service. This ensures the user receives only one push notification for a given campaign.

##Q. Why is my push notification campaign running slowly?
If you feel that the push campaigns are executing slowly, then it could be due to either of the following reasons:

* Personalized messages - If personalization is used in the message, then the push notifications will not be sent in batches containing multiple users because the content of the push is different for each user. The push request for each user is made separately and this increases the time to process.

* Throttle - The push campaign can execute slowly as it adheres to the throttle limit that is set for push notifications in the *Campaign Limits* under *Account Settings*. The throttle limit specified from the dashboard during the campaign creation is considered throughout the lifetime of the campaign. Throttle for existing campaigns is not updated when the global throttle is updated. The new throttle is considered only for the new campaigns.

##Q. What is the recommended image dimension in push notifications with a CTA?

The recommended aspect ratio is 16:9 and the minimum recommended size is 533.33 X 300 pixels. The supported file types are PNG, JPG, and JPEG and the maximum size is 40 kb.

You can adjust the dimensions accordingly. You can also refer to the following link to calculate the aspect ratio: https://calculateaspectratio.com.

##Q. Where can I update Xiaomi/Huawei credentials?

After you have an app secret and package name, you must update it on the CleverTap dashboard using the following steps:

1. Click **Settings** from the dashboard.
2. Click **Channels** > **Mobile push**. The push notification setup page displays.
3. Click **Huawei** or **Xiaomi** push notifications and add App secret and package name/App ID.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e6c6f1-New_final_Previous_Campaigns_mobile_push_settings_xiaomi_huwaei.png",
        "New final Previous Campaigns_mobile_push_settings_xiaomi_huwaei.png",
        931,
        663,
        "#fafafb"
      ]
    }
  ]
}
[/block]
##Q. Will my users get a push notification immediately after their inactive device becomes active?
If the user device is inactive (no Internet or switched off) and the user turns it on again within the time to live (TTL), then the push notification is delivered.

##Q. How can I have a small icon instead of a white square box on the top left screen?
The small icon must be set at the code level in the manifest file. The small icon must be alpha. You can create the icon using the Image Asset Studio tool included in the Android Studio.

For more information, refer to [Set the Small Notification Icon](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon).

##Q. How can I redirect the users to MWeb when they click the push notification?
To redirect users to MWeb, you can add the URL of the page as a deep link when creating a campaign. The users are redirected to the page specified in the deep link. For example, https://clevertap.com/.

##Q. How do you resolve the popup for installing the HMS core app on non-Huawei devices?

This popup appears on non-Huawei devices after implementing Huawei push notifications. To avoid this popup, check for HMS class on all devices and trigger the push registration service only if `HMSclass` is available on the device. For more information, refer to [Preferentially Using HMS for Determination](https://developer.huawei.com/consumer/en/doc/development/Tools-Guides/push-conversion-0000001050060304#EN-US_TOPIC_0000001050060304__section330733914368) in the Huawei documentation. 

##Q. Why do I see 0% push notifications for Xiaomi and 100% for Firebase (FCM)?
The Xiaomi/Baidu/Huawei push notifications may show 0% on campaign stats if all the notifications are delivered through FCM. For a greater chance of delivery success, CleverTap sends a push notification through the Xiaomi/Baidu/Huawei Push and Firebase Cloud Messaging (FCM) push services. If a message is delivered through any one of these push services, then the notification from the other cloud services is suppressed. There is no priority that is defined for the messaging service and there are no changes to the current flow of FCM. This ensures the user receives the push notification only once.

Services that are not integrated are shown as *N/A*. 

##Q. How can I send multiple notifications from the same campaign?
If you select *Send campaign every time the user qualifies* when creating a campaign, then the user receives multiple notifications from the same campaign.


#Android

##Q. How do I enable the debug mode?
You can enable the CleverTap debug logs by placing the following code in the `onCreate` method in your Java file, such as: 

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
For more information, refer to [Android Debugging](https://developer.clevertap.com/docs/android#section-debugging). 

##Q. How can I add lifecycle callbacks?
If you have a custom application class, call the `ActivityLifecycleCallback.register(this);` method before the `super.onCreate()` method in your class. 

For more information, refer to [Initialize the CleverTap SDK](https://developer.clevertap.com/docs/android-quickstart-guide#section-step-4-initialize-the-clever-tap-sdk).

##Q. How can I update the location?
CleverTap records two types of geographical information, such as:

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
* Unkown -  The city-level information which is tracked by CleverTap using reverse IP methodology to map the user's location, based on the device IP. This information is updated on every *App Launch*. 
* Lat/Long - The latitude and longitude information you pass to CleverTap. The circle you gave selected on the map fetches users based on this latitude and longitude that you pass to Clevertap.

To get the users' city, region, and country on every app launch, allow the CleverTap SDK to collect user locations (which we then collect by reverse-IP lookup via our third-party location provider, MaxMind). 
[block:callout]
{
  "type": "info",
  "body": "MaxMind has an accuracy of 70% in India.",
  "title": "Note"
}
[/block]
Below is how you can enable the location tracking:

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
For more information, refer to [Custom Android Push Notifications Handling](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling).

##Q. Why does CleverTap not capture the device token on the first app launch?
 
CleverTap may not receive the push token on the first app launch because of the following reasons:

* Not using CleverTap’s token listener service -  Check that your custom token listener sends out a token to CleverTap immediately. The tokens are fetched on every app launch. Since the token is not generated at the first app launch, it is not available when the CleverTap SDK checks for it. The CleverTap SDK then fetches the token from cache on the second app launch. This is a fail-safe in the CleverTap SDK that fetches the token and sends it to CleverTap with the *App Launched* event.   

Use the following code to enable sending tokens to CleverTap as soon as they are received by your listener. 
[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI.getDefaultInstance(this).pushFcmRegistrationId(token,true);\n\n",
      "language": "java"
    }
  ]
}
[/block]
* Using Firebase 18 or above -  When you upgrade your Firebase messaging dependency version to 18.0 or greater, you must implement a single service for both Token and Message Listener services to get the token on the first app launch. There is no need to implement separate FCMMessageListenerService and FCMTokenListenerService to get the token on the first app launch.

For more information, refer to [Use FCM Version 18.0.0 and Above](https://developer.clevertap.com/docs/using-fcm-version-1800-and-above).

##Q. What is the correct format for sending a date-time value in Android? 
The date-time values must be passed in the correct format to be considered as date-time value. Pass the property value in either of the following formats for Android:

* new java.util.Date()
* “$D_EPOCH”

#iOS

##Q. Is there an action ID for iOS similar to Android?

The iOS equivalent for action ID is *category*. You can add the name of the category while creating a campaign. Each category must be registered with the app. This category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it. The actual number of actions actually displayed for the category depends on the type of notification delivered. Users can perform multiple actions for the notification. For example, a single media push notification can have two buttons such as, *Buy Now* and *Save for Later*.

For more information, refer to [Advanced iOS Push Notifications](https://developer.clevertap.com/docs/ios#section-advanced-ios-push-notifications).

##Q. Why does the word, *modified*, appear in the title for iOS push notifications?
The word *modified* displays in push notifications if you enable the advanced option in a campaign. Implement the *Rich Push* notifications in a future update to address this issue. If you are not using *Rich Push*, then uncheck the advanced option you have selected in the campaign.

##Q. What is the correct format for sending a date-time value in iOS? 

The date-time values must be passed in the correct format to be considered as date-time value. Pass the property value in either of the following formats for iOS: 

* [NSDate date]
* “$D_EPOCH”

##Q. How do I disable IDFA tracking in iOS?
To disable the IDFA tracking, follow the steps below:
1. Check that you have not added the `CleverTapUseIFA` flag in the info.plist file.
2. Remove the *AdSupport* framework from your build if you have added it in your linked libraries.
3. When submitting your app to the app store, you are asked if your app supports IDFA. Select *No*.

#Web

##Q. Why am I not able to make CleverTap API requests from my website (CORS)?

CleverTap follows the Cross-Origin Resource Sharing (CORS) standard. To adhere to this standard, all the [CleverTap API](https://developer.clevertap.com/docs/api-overview) calls must be made from the server-side.


##Q. What is the correct format for sending a date-time value from the website?
If you want to raise a date-time value for a property from the website, then check that the value is either of the following:

1. JavaScript’s new Date() method

2. “$D_EpochValue”

The values are considered as strings if they are not passed in the proper format.

#In-app

##Q. How do you analyze the CTA button for in-app campaigns?
The data for a number of clicks on each CTA button is available under the *Analytics* section in the dashboard. 

Follow the steps below:

1. In *Events*, query for the *Notification Clicked* event filtered by the campaign ID, then in the result, go to *Trend & Properties*.
2. Scroll down to the *Event property* table and select the event property as "wzrk_c2a" from the dropdown to see a distribution of clicks across the various buttons on that respective email campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fbcfb49-New_final_CTA_Button_Analysis_2.png",
        "New final CTA_Button_Analysis 2.png",
        1163,
        543,
        "#f2f8f9"
      ],
      "border": true
    }
  ]
}
[/block]

##Q. Why does the in-app notification give an error FCM payload too large? 
The test in-app is sent within a push notification. The limit for push notification payload as defined by FCM is 4KB, beyond which the notification is not sent.  If the in-app notification has a large HTML code or a heavy size, it shows an error and the test in-app is not sent. 

However, this does not apply to a live campaign because there are no push notifications.  To resolve this error, you can first schedule a live campaign with this HTML for internal users. 

##Q. Why does the in-app campaign not render an API event?
The in-app works for SDK events, such as events raised from the device. There can be delays in the APIs and by design, the in-app is meant to be sent in real-time to the user. Therefore, the in-apps need to be triggered by a mobile SDK event.

##Q. How can one close the in-app notification on the click of a button?
The workaround is to create a button and add the reference of that button to a dummy hyperlink. This closes the in-app notification because the link does not exist, so there is no redirection.

Here is a sample link: wzrk://thisisadummylink

##Q. How do I exclude in-app from the Android activity?

If your application has a splash screen (e.g., logo screen or loading page) displayed on app launch, then the In-App triggered on *App Launch* would be attempted to be displayed on this screen. As soon as this screen is dismissed, the In-App will be dismissed too.

In such cases, the splash screen must be excluded. Mention the *Activities* on which you do not want In-App notifications to show in the android:value of the metadata tag in the AndroidManifest.xml file.
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

For more information, refer to [In-App Notifications](https://developer.clevertap.com/docs/android#section-in-app-notifications).

##Q. Why do I receive a CleverTap push notification even after sending a test in-app?

An in-app test is always sent like push notification. The entry action (event) does not matter. When you click the *send a test notification* option, this message, "Touch this notification to open your app and view your view your notification" is sent out as a push notification. When this notification is clicked, the app opens and displays your in-app notification. This is applicable only to a test notification. The live campaign will schedule as usual and show the in-app after a user qualifies (performing the entry event).

##Q. Why can I not see the videos on *Interstitial* in-app notifications?
The video must meet the following requirements:
  * The video must be in MP4 format.
  * The video size must be lower than 50MB.
  * The dependencies which are required to include audio/video in the in-app notification are included.

Add the following dependencies below in your application’s build.gradle file: 
[block:code]
{
  "codes": [
    {
      "code": "Dependencies {\n\n implementation 'com.google.android.exoplayer:exoplayer:2.8.4'\n\n implementation 'com.google.android.exoplayer:exoplayer-hls:2.8.4'\n\nimplementation 'com.google.android.exoplayer:exoplayer-ui:2.8.4'}",
      "language": "groovy"
    }
  ]
}
[/block]

##Q. How do I close an in-app notification automatically after a specific duration?
You can use the set `timeout` function in custom HTML to dismiss the in-app. 

Below is a sample code:
[block:code]
{
  "codes": [
    {
      "code": "<!DOCTYPE html >\n<html id=\"myClass\">\n<head>\n    <title></title>\n    <script src=\"https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js\"></script>\n</head>\n<body style=\"background: white\">\n<h1>Test</h1>\n<!-- <button style=\"visibility: hidden;\" id = \"theSubmitButton\" onclick=\"window.location.href='wzrk://this_leads_to_nowhere'\">Click me</button>  -->\n\n<p><button id=\"theSubmitButton\" onclick=\"window.location.href='wzrk://exit'\" style=\"visibility: hidden;\">Click me</button></p>\n\n<p id=\"demo\"> </p>\n<script>\n   setTimeout(function myFunction() {\n       document.getElementById('theSubmitButton').click();\n   }, 1000); // Change time for whatever miliseconds required.\n   </script></body>\n</html>",
      "language": "html"
    }
  ]
}
[/block]
##Q. How do I analyze the CTA button for in-app campaigns?

To view the data for a number of clicks on each CTA button, go to *Analytics* > *Events* from the dashboard. Then, follow the steps below:

1. Select the *Notification Clicked* event and filter it by the campaign ID.
Click the **View Details** button. The event details page displays.
2. Click the **Trend & Properties** tab.
3. Scroll down to the *Event property* table and select the event property as "wzrk_c2a" from the list. 
4. A distribution of clicks across the various buttons on that respective in-app popup campaign displays.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ddcf857-CTA_Wzrk_property.png",
        "CTA_Wzrk_property.png",
        1439,
        636,
        "#e7efec"
      ],
      "border": true
    }
  ]
}
[/block]
##Q. My in-app shows 0 views even after qualifying multiple users. What could be going wrong?

The in-app notifications require SDK version 3.5.1 and above. The warm-up time for campaign is three to five minutes. Check the following before scheduling an in-app campaign: 

  * In-apps require the app to be open and the event must be fired from the mobile SDK. Hence, the in-app campaigns do not work on an event that is triggered via API. 
  * There cannot be multiple in-apps running on the same event. The in-app that was created first is displayed, and the other events show 0 views.

##Q. Why does the in-app notification disappear from the user's device in a few seconds?

The in-app notification is dismissed if you display it over the splash/logo screen because the in-app is automatically dismissed when the underlying splash screen is dismissed. Exclude the splash screen to avoid displaying an in-app. 

Add the following meta-data in the AndroidManifest.xml to exclude the splash screen from your in-app notification:

[block:code]
{
  "codes": [
    {
      "code": "{code}\n<meta-data\nandroid:name=\"CLEVERTAP_INAPP_EXCLUDE\"\nandroid:value=\"YourSplashActivity1, YourSplashActivity2\" />\n{code}\n",
      "language": "xml"
    }
  ]
}
[/block]
Add the activities to exclude from in-app notifications in the `android:value` row of the metadata tag.

##Q. Does the in-app message support GIF files?
The CleverTap SDK version 3.3.0 and above supports GIF within the interstitial in-app messages. You also send GIF files in in-app campaigns using a custom HTML.

For more information, refer to [Template Aspect Ratio and Image Size Guide](https://docs.clevertap.com/docs/inapp-campaigns#section-template-aspect-ratio-and-image-size-guide).

##Q. What happens when I run multiple in-app campaigns simultaneously? Do they stack up over one another? 

You can run multiple in-app campaigns at the same time but on different events. If you try to run multiple in-app campaigns on the same event, then the in-app message from the first campaign is rendered. All other subsequent in-app messages from other campaigns are ignored. 


##Q. Can I handle the URL at the client side for in-app campaigns?

This is supported for CleverTap Android SDK version 3.6.1 and above and CleverTap iOS SDK version 3.7.1 and above. It works for the following templates:

  * Cover
  * Interstitial 
  * Half-interstitial
  * Header
  * Footer

You can add the key-value pair for a button-click in the *What* section of the campaign creation screen:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ffcc8ae-In-app_client_side.png",
        "In-app_client_side.png",
        656,
        483,
        "#fbfbfc"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
You must implement the button-click callback in your [iOS](https://developer.clevertap.com/docs/ios#section-in-app-notification-button-on-click-callbacks) and [Android](https://developer.clevertap.com/docs/android#section-in-app-notifications) apps where you can get these key-value pairs.

##Q. How do I add a Google form in an in-app notification?
You can create surveys inside an in-app campaign using the Clevertap custom HTML feature. You can add the embed HTML code provided by a Google form when you click on a button. 

Below is a sample code:
[block:code]
{
  "codes": [
    {
      "code": "<html>\n<head>\n\t<title></title>\n</head>\n<body>\n<p><iframe frameborder=\"0\" height=\"700px\" marginheight=\"0\" marginwidth=\"0\" src=\"https://docs.google.com/forms/d/e/1FAIpQLSeVoF3S7pRJxXvkFLJW_fqRHqtq-ZdLi5HQcQxDRF0ZGqCWfA/viewform?embedded=true\" style=\"padding-top: 25px; max-height: 100%\" width=\"100%\">Loading…</iframe></p>\n</body>\n</html>\n",
      "language": "html"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d12600e-In-app_embed_html.png",
        "In-app_embed_html.png",
        601,
        407,
        "#bfc3cd"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]

The CleverTap SDK supports embedding Javascript code inside custom in-apps. You can write your own HTML code and use it in an in-app.

##Q. How do you add custom fonts in in-app campaigns?
You can use custom fonts in a regular HTML page by importing it in the head tag of the HTML code and then using it in the CSS.


`<head> tag of HTML`
[block:code]
{
  "codes": [
    {
      "code": "<link href='[PLACE SOURCE URL FOR FONT HERE]' rel='stylesheet' type='text/css'>\n  <link href=\"https://fonts.googleapis.com/css2?family=Oswald:wght@700&family=Roboto&display=swap\" rel=\"stylesheet\">\n",
      "language": "html"
    }
  ]
}
[/block]
`CSS` 
[block:code]
{
  "codes": [
    {
      "code": ".sample-class { \n  font-family: '[Name of font]', arial, serif; \n}\nfont-family: 'Oswald', sans-serif;\n",
      "language": "css"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You must select custom HTML to use your custom font in the in-app campaign."
}
[/block]
#SMS
##Q. What is a *Profile not reachable* error?

The error *Profile not reachable* occurs whenever the qualified device is not reachable via the selected communication channel. 

Some examples include:
* SMS - The profile does not have a phone number or the user has unsubscribed from SMS communication.
* Push - Device token is not present during the time of the campaign.
* Emails - The user has unsubscribed or the e-mail communication flag has been set to false.
The reachability of the user can be checked by checking the communication preferences under the user's profile.

##Q. What is a *Duplicate Profile for the channel* error?
This error indicates two different profiles have the same credentials such as, phone number, push token, and email (based on the communication channel). The engagement is sent to the first profile and this error is raised for the second profile.

##Q. What is the character limit for SMS?
The limit for a standard SMS is 140- 160 characters after which the remainder of the message is sent as a new SMS.

##Q. Why do some emojis and characters not display in my SMS body?

To resolve this issue, check that your service provider supports sending special characters/emojis in an SMS.

##Q. What are IP addresses that must be whitelisted for sending out the SMS?

You can get the list of IPs from the following setting in the CleverTap dashboard:
1. Go to CleverTap account settings > *Integration* > *Push Notification*.
2. Whitelist all the listed IPs to send out SMS messages:
  * 34.249.27.35
  * 34.250.139.131
  * 52.209.30.153
  * 54.72.72.185

#App Inbox

##Q. When is the *App Inbox* sent to the user in case of the *Live Segment* and *Past Behavior* segment? 

The *App Inbox for Past Behaviour Segment* is sent on the qualified user's device as soon as the user launches the application. The *App Inbox* message for *Live User Segment* is sent as soon as the user performs the event. 

##Q. Can events triggered by API or Web be used to send the *App Inbox* campaign?
*App Inbox* requires the user to be present on the application. Therefore, *App Inbox* campaigns do not work on an event that is triggered via API or web. Additionally, events from an API may not be real-time and hence the campaign is not triggered. 

##Q. Why is there is an option to add a channel ID when sending a test app inbox message, but not while sending messages from a campaign?
A channel ID is not required for sending app inbox notifications. However,  it is required for a test app inbox notification because it is rendered as a push notification on the user's device. It is mandatory to have a channel ID for sending push notifications on Android devices for versions 8 and above.

##Q. Why is the push notification rendered immediately for *Push+App Inbox* campaigns but not for *App Inbox* notification?

For app inbox campaigns, once you create the campaign, you must wait for campaign warmup time (5-10 minutes) and then launch the app to get the messages.

The app inbox is not rendered even if you launch the app within the campaign warmup time and you will not be able to receive the same App Inbox further.