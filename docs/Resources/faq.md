---
title: FAQs
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
# Common Android SDK Questions

## Q. How do I exclude In-app from the Android activity?

In-App notifications are pop-ups that you can show to your users while they are on your app. To exclude the in-app notification on a particular activity or page, you can use the following code.

```xml
<meta-data
    android:name="CLEVERTAP_INAPP_EXCLUDE"
    android:value="YourSplashActivity1, YourSplashActivity2" />
```

For more information, see [In-app notifications](https://developer.clevertap.com/docs/android#section-in-app-notifications)

# Push Notification Errors in Android

## 1. Invalid FCM API Key

An "Invalid FCM API Key" error appears when the FCM API key in the CleverTap dashboard is incorrect. You will not be able to send any notifications till the FCM API key is added to your settings. To update the FCM API key - 

* Navigate to Settings > Engage > Channels > Mobile Push. 
* Update the valid FCM API key as it appears in your Firebase project. 

<Image title="Push_Notification_FCM_API_Key.png" alt={1172} width="100%" border={true} src="https://files.readme.io/4d0f805-Push_Notification_FCM_API_Key.png">
  Update FCM API key
</Image>

For more information, see finding your [FCM API Key](https://developer.clevertap.com/docs/find-your-fcm-sender-id-fcm-server-api-key)

## 2. FCM Token Invalid

The  FCM token is not linked to any device that has your app. Notifications are not delivered because the token is not valid.  Check the format of the FCM project number and registration token you pass on to CleverTap. For more information see [Troubleshooting push notifications](https://developer.clevertap.com/docs/troubleshooting-push-notifications)

## 3. FCM Error

This is a Firebase (Android) error. The "FCM error" is not part of the "standard published list" and it is sometimes incorrectly identified as an Android bug.

## 4. FCM Not Registered

Most likely the users have uninstalled the app from their device.

One of the common non-technical errors is "Undelivered due to App Uninstall", in campaign reports. This error occurs when the users uninstall your app while you are trying to reach them via a push notification.

The FCM Not Registered error occurs in two scenarios:

* When the users have uninstalled your app and you are trying to schedule a push notification to them
* When users have cleared the device cache memory, which in turn removes the token from the device

## 5. FCM Mismatch Sender ID

An FCM sender ID mismatch occurs when the sender ID entered in the CleverTap dashboard under Push Notification settings does not match with the sender ID in the FCM project for your app created on Firebase.

You must match the sender ID/server keys at the following 3 locations:

* App-level which registers token with the said FCM sender ID mentioned.
* In the CleverTap dashboard.
* FCM project

If you have checked the sender ID for mismatch and the error still persists, check the following: 

* Does the app build and the CleverTap account contain mismatched sender IDs?
* Do you have multiple Firebase projects?
* Do you have multiple Platform IDs, that is, maybe your app is using two Firebase projects?

# Push Notification Errors in iOS

 \##1. APNS Device Token Does Not Match The Specified Topic 

Apple Push Notification service (APNs) returns this error when the device token doesn't match the specified topic.

In the context of CleverTap, you will get this error when you try to send the notification with a wrong certificate. Check that you use a production certificate for the production environment. This error is caused because of incorrect configurations. 

Check the provisioning profile used to deploy the app and send the device token to the CleverTap dashboard. To avoid this error, the "App bundle ID" of the provisioning profile and the CleverTap push certificate (p12 certificate) must match.

## 2. APNS Unregistered

The Push notification delivery to the target fails because the device token is inactive for the specified topic. If the device token is not valid/inactive you may have to wait till the user installs the app again. You can then start sending notifications. 

## 3. APNS Topic Disallowed

The topic is currently the bundle identifier of the target application on an iOS device. The "APNS Topic Disallowed" error appears when you specify the incorrect "App Bundle ID" in the Account Settings. For more information, see [Apple documentation](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html).

To resolve this error, check the value of the "App Bundle ID" and "APNs push mode" that you have configured in the CleverTap Dashboard under Push Settings.

## 4. APNS Temporarily Blacklisted

You are temporarily blacklisted from sending push notifications to the device, which can be due to sending bad tokens. The push notification will not be delivered for some duration.

## 5. APNS Failed Delivery 

The notification to the device sent from CleverTap failed to deliver due to either of the following reasons

* The app was uninstalled and the token is no longer valid.
* You have sent too many notifications in short duration to the same device.

If the user has uninstalled the app then you may have to wait until the user installs the app again before the user can receive your notifications.\
For more info about APNs, see [Handling Notification Responses from APNs](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/handling_notification_responses_from_apns).

## 6. APNs Bad Device Token

The push notification delivery to the target device has failed due to an invalid token. The APNs bad device token error occurs when there is a mismatch between the APNs push mode on your app and the CleverTap dashboard.\
For example, you have set the APNs push mode in your app to the "development" stage and in the "CleverTap" dashboard you have set up to "production" stage. To check your CleverTap dashboard APNs push mode: Navigate to Settings > Engage > Mobile Push> iOS.

<Image title="Push_Notification_iOS_API_Key.png" alt={1166} className="border" border={true} src="https://files.readme.io/20ff216-Push_Notification_iOS_API_Key.png" />

# Campaign Errors

## 1. SMS Errors

An SMS error is a common campaign error that occurs while scheduling the SMS campaign. The SMS error appears if the SMS service provider’s endpoint is unavailable. It is applicable to generic integrations and MSG91 (SMS provider).

The SMS error shows the following message: 

"Error java.net.SocketTimeoutException: Read timed out for message". It is referred to as the "SocketTimeoutException" error.

SMS error appears when CleverTap sends the SMS payload to the SMS provider’s endpoint but it does not get an acknowledgment within 15 seconds. 

You can view the errors within the campaign reports under the "Error" section.  The "SMS error" appears under the "Technical Errors" category.

> 📘 Note
>
> The issue generally means a socket timeout exception. Sometimes it can also mean connection request exception.

For other integrated vendors we have the equivalent errors :\
a. Exotel server error\
b. Twilio server error\
c. Gupshup server error\
d. Netcore service error\
e. Nexmo SMS error

## 2. Web Push Unsubscribed

The error "BrowserUnsubscribed" appears after your app users unsubscribe themselves for web push notifications from Chrome browser settings. 

When you try to engage these unsubscribed users through web push, the "BrowserUnsubscribed" error appears.

## 3. How do I enable Push impressions?

To enable Push impressions:

* Go to  Settings > Schema > Events/User Properties.
* Click "Push Impressions" event and toggle the Mobile push button to enable Push impressions for the account. 

<Image title="FAQs_Push_Impresions_Enable.png" alt={1437} className="border" border={true} src="https://files.readme.io/902d879-FAQs_Push_Impresions_Enable.png" />

## 4. Daily Limit Exceeded

While creating a recurring push campaign, CleverTap allows you to set the daily limit. For example, you can set a daily send limit to 10,000/day, after which you will get "Daily limit Exceeded" error, and set an overall cap limit to 1,00,000 users after which the campaign will stop.

You would generally set a daily limit in a Triggered Campaign, where you are using a live segment. These campaigns are triggered based on an event and therefore you would want a daily limit for your campaigns. 

<Image title="Campaigns_per_day.png" alt={1126} className="border" border={true} src="https://files.readme.io/47a68a3-Campaigns_per_day.png" />

 You can set the campaign limits within the "Who" section while creating the campaign.

## 5. Per Run Limit Exceeded

The Per Run Limit is a limit enforced on the number of users that are sent in one campaign run.  For example, you can set a maximum segment limit to 100000 users and the campaign stops running after the set limit for each run.

You see the Per Run Limit Exceeded error when the campaign stops running after the number of qualified users exceeds the set limit. 

You would generally set a per run limit for past behavior and custom list segments. This is because the campaign is sent to all the qualified users based on their past actions. Therefore you would want a per run limit for these campaigns.  

<Image title="Campaigns_per_run.png" alt={1399} className="border" width="100%" border={true} src="https://files.readme.io/131c866-Campaigns_per_run.png" />

You can set this maximum segment size from the "Who" section while creating the campaign.

## Q. Why is the reachability for my campaigns so low?

When you create a segment, you can view the reachability of this segment across all channels such as, "Web Push", "Mobile Push", "SMS", "Email", and "Audiences." This helps you to check the reachability of your campaigns even before you create them.  

<Image title="segment_rechability.gif" alt={1438} className="border" width="100%" border={true} src="https://files.readme.io/742acc4-segment_rechability.gif" />

Following are some of the reasons that may affect your "Mobile Push" reachability:

* Token Not Present: One of the key reasons for low reachability is because the push token is not available in the user profile.
* User Unsubscribe: The user may have unsubscribed from your app and does not wish to receive push notifications. 
* Token not generated: The token did not generate on the first app launch.
* App Uninstall: User has uninstalled the app.

## Q. User DND Set Error

 A "User DND Set Error" occurs when you qualify users for a campaign even though they have unsubscribed from the target device.  This error informs you that these users have been passed into the error bucket. 

## Q. Frequency Caps Exceed Error 

The Global Frequency feature allows you to restrict the maximum number of messages you can schedule each day for your user and across different channels.

Go to the Settings > Setup > Campaign limits to cap the frequency for various channels. 

Here, you can define the number of messages you wish to send to each user in "X" number of days. 

<Image title="Campaigns_global_frequency.png" alt={893} className="border" width="100%" border={true} src="https://files.readme.io/7bd8ab2-Campaigns_global_frequency.png" />

You can also specify the "Dwell Time", which is the duration you wish to specify between two messages, and "Throttle", which enables you to control the flow of your messages. 

For more information on dwell time, see [Dwell Time](https://docs.clevertap.com/docs/messaging-frequency-caps#section-dwell-time-between-messages)

For more information on throttling, see [Throttle](https://docs.clevertap.com/docs/messaging-frequency-caps#section-dwell-time-between-messages).

Now when you create a campaign and if you wish to disable the "Global frequency limit", then clear the "Global Campaign Limit" option under the "Who" section. The "Global Campaign Limit" is enabled by default.

<Image title="Campaigns_global_campaign_limits.png" alt={1200} className="border" border={true} src="https://files.readme.io/1a73eec-Campaigns_global_campaign_limits.png" />

# Dashboard Errors

 \##Q. How can I upload a CSV file from the dashboard?

You can bulk upload user profiles using the CSV Upload feature. You can also use this feature to add or update information for existing user profiles.

Follow the steps to upload the CSV file in your CleverTap dashboard:

1. Login to your CleverTap account, and then click the Settings button.
2. Click on the CSV Uploads button.
3. Click the Import new profiles from CSV button.
4. Select the CSV file from your computer, and then click the Upload button.
5. Enter a name for the upload.

Your CSV upload is processed almost instantly. After the uploaded CSV is processed, the status for that upload is changed to "completed".

For more information on CSV upload, see [CSV Upload](doc:csv-upload).

## Q. How can I delete the events data from the dashboard without discarding events?

You can simply reset the DRP for each event. All the event data beyond the selected date range is discarded. 

For example, if you set the DRP of an event to 12 months, we will store the data for the past 12 months. All the data prior to the 12 months are deleted. You can optimize your container and avoid flooding it with too much data.  

Follow the steps to adjust the DRP for each event:

1. Go to "Events & User Properties" under the dashboard settings section
2. Select the event for which you wish to adjust/reduce the DRP.

<Image title="Settings_DRP_Limit.png" alt={1437} className="border" border={true} src="https://files.readme.io/85e8e1a-Settings_DRP_Limit.png" />

> ❗️ Note
>
> Analyze your data before reducing the DRP. Only remove the data that will not affect your campaigns.  The maximum reduction in data DRP is upto 3 months.

# Events & User Profiles

## Q. How can I export data from CleverTap

You can export the data from CleverTap using one of the three following methods:

* S3 Export (AWS) -  You can export your event and profile data in the AWS S3 bucket using CleverTap Data Exports. For more information on using our data export, see [Data Export to AWS S3](doc:data-export-to-aws-s3).

* Export via API - You can export your events and user data with our APIs. For more information, see [Export Data with API](https://developer.clevertap.com/docs/api-overview).

* Find people - You can download the profile data directly from the CleverTap dashboard through the Find People page. To download the data from "Find People", follow the steps mentioned below:

* Step 1: Navigate to the "Find People" section and define the criteria that you wish to export.

* Step 2: Click "View Details.”

* Step 3: Click on the download icon (beneath the user count) to initiate the download (refer to the screenshot below).

<Image title="FAQs_Events_and_Profiles_Export_data.png" alt={1224} className="border" border={true} src="https://files.readme.io/55a31f1-FAQs_Events_and_Profiles_Export_data.png" />

# Webhooks

## Q. What is a Webhook dispatched failed error?

The "Webhook dispatched failed" error is raised when the CleverTap server does not receive a "200 OK" response. A "200 OK" response is an acknowledgment from the REST API server that the API request was received successfully. An error can arise in either of the three scenarios:

* When CleverTap sends the payload to your endpoint and we do not receive a "200 OK" response after retrying 3 times after a wait of 15 seconds. 
* When CleverTap sends the payload and your endpoint health is down.
* When you may receive the payload at your endpoint but not send a "200 OK" response to CleverTap server within the timeout frame of 1 second. CleverTap displays a "Webhook dispatch failed error" in this case.

We recommend, as a best practice, to queue the payload at your end and provide us a "200 OK" in response.

# Identity

## Q. What is Duplicate Platform ID Error

"Duplicate Platform ID Error" occurs in one of the following scenarios:

* When a single token is assigned to multiple profiles and both the profiles qualify for the campaign. Here,  CleverTap sends the notification to the profile that qualifies first, and the other profile is marked as a "Duplicate Platform ID."
* When the same mobile number is assigned to multiple profiles and they qualify in your campaign. Here, only one profile receives the notification, and the other profiles are marked as a "Duplicate Platform ID".

# CSV Uploads

## 1. CSV uploads - identity passed as "Identity."

Uploading your historical user data via CSV is simple and quick. However, there are a few key pointers to note before uploading your user data via CSV. 

* The identity field must be defined as "identity" with a small "i" and not "Identity".
* The "Identity" field is a mandatory column 
* Check that your CSV complies with the CSV standards, else the upload is denied.
* You can download the sample CSV file for a quick check from the settings section under "CSV uploads."

Sample CSV :

<Image title="Identity_CSV_Uploads.png" alt={1298} className="border" border={true} src="https://files.readme.io/61b074a-Identity_CSV_Uploads.png" />
