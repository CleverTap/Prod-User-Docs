---
title: Legacy Push (To be Deprecated)
deprecated: false
hidden: true
metadata:
  robots: index
---
Explore troubleshooting tips and FAQs for Push Notifications by expanding the sections below for detailed information.

<Callout icon="📘" theme="info">
  **Legacy Push to be Deprecated**

  The Legacy Push to be deprecated from **18-May-2026**. For information, refer to [Push Editor](doc:push-editor) and [FAQs](doc:push-faqs).
</Callout>

# FAQs

<details>
  <summary>Push Notification Rendering</summary>

  ### Why does the Push notification image not render for Android?

  Rendering of the image in a push notification is dependent on three factors:

  * **Image Size**: The image size must be less than 40Kb.
  * **User's Internet Connection**: The OS (Android and iOS) tries to download the image for \~10 seconds. If it cannot download the image within this time, the push is rendered only with the title and message without the image.
  * **Content Delivery Network(CDN) Throughput**: Because the OS downloads the image every time a push is sent to a user, the CDN you use to host images must also be scalable. Let's say the notification is sent to 5 million users. The OS tries to download the image from the CDN for all these users. The CDN must be scalable for such a base.

  ### Why does the image not render in push notifications for iOS?

  To render the image push notification for iOS, you must enable the rich media notification in iOS. You can enable *Rich Push Notifications* using a notification service extension. This is a separate and distinct binary embedded in your app bundle.

  For more information on enabling the notification service extension, refer to [UNNotificationServiceExtension](https://developer.apple.com/documentation/usernotifications/unnotificationserviceextension) in the Apple documentation.

  ### Why do images not render for the Push notifications? Primarily for  Chinese OEMs such as OnePlus?

  Chinese handsets have tweaked the OS to enhance battery life. Battery optimization is a vital in preventing image rendering in a push notification. This behavior is prominent across makes like Oppo, OnePlus, etc. Because of the battery optimization layer, the app sometimes kills the background services, preventing the notification from rendering. This behavior varies by user and device based on the app's usage pattern and device usage and timings. Additionally, if the notification is clicked as soon as received, the app might open irrespective of the settings. However, if the notifications stay in the user's tray for a specific time (the threshold varies from device to device), the app does not open upon clicking the notification.\
  Please find the further details as follows:\
  Based on our observations in OnePlus Devices: 

  * Under*Settings* >*Recent App Management*, you have two options: Normal Clear *and\_Deep Clear*. Generally, if \_Deep clear\* is selected, clicking on a notification does not open the app.
  * Along with  *Recent App Management*, battery optimization has two options under*Advanced optimization* >*Deep optimization* &*Sleep standby optimization*.\
    This option also prevents opening the app after clicking the notification.\
    This behavior varies from user to user using a OnePlus device basis the app's usage pattern.

  ### Why am I receiving blank push notifications?

  This may happen if you custom hand or custom render the Push notifications, and have enabled uninstall tracking. Check for the following:

  * CleverTap SDK does not handle the Push notification and the handling is performed through your custom code. This custom code must read the payload defined by CleverTap and fetch the *Title*, *Message*, and other parameters using the keys mentioned in the payload.

  * If the custom code is unable to understand the payload defined by CleverTap, then the Push notifications are displayed without a message.

  * Below is a sample payload for Android that can help identify the keys and their respective values  for custom push rendering:

  ```json
  {
  wzrk_acct_id=CleverTap_Account_ID, 
  custom key=custom value, //custom key values (optional)
  wzrk_acts=[
  {"l":"Action button 1",
  "dl":"deep link for action button 1",
  "id":"action id of the action button 1","
  ico":"Icon resource identifier for action button 1"}
  ], 
  nm=the message of the push, //Message text
  nt=title of the push, //Title text
  pr=max, 
  ico=large icon url, 
  wzrk_pivot=wzrk_default, 
  wzrk_sound=Custom sound file name, 
  wzrk_cid=123456, //Notificaiton channel id 
  wzrk_nms=Summary text field, // Summary text
  wzrk_rnv=true, 
  wzrk_ttl=1586148291, //Time to live in epoch
  wzrk_push_amp=false, 
  wzrk_bc=badge icon, 
  wzrk_bi=2, 
  wzrk_bp=image URL, 
  wzrk_ck=collapse notification, //Collapse key
  wzrk_dl=deep link url here, 
  wzrk_dt=FIREBASE, 
  wzrk_id=0_0, 
  wzrk_pn=true, 
  wzrk_st=subtitle //Subtitle text
  }
  ```

  * Also, CleverTap sends a silent Push notification (blank push) to track *App Uninstalls* if *Uninstall* tracking is enabled on the CleverTap dashboard. If you custom handle the Push notifications, you are parsing the payload yourself and rendering the notifications on the device using your own method. You must check for the `nm` or `nt` tags. These tags in the Push payload hold the title and message of the Push notification. If these tags are empty, then the Push must not be rendered. The code must identify the silent push notification and the normal push notification.

  * If the above is not implemented, then the users will get blank Push notifications around midnight when the *App Uninstall* sweep runs on CleverTap.

  ### What is the recommended image dimension in push notifications with CTA?

  The following is the recommended image dimension in push notifications with CTA:

  * **Aspect ratio**: 16:9 and Recommended Size - 533.33 X 300 pixels minimum.
  * **Supported File Types**: PNG, JPG, JPEG
  * **Max Image Size**: 40Kb\
    We recommend maintaining an aspect ratio of 16:9. Adjust the dimensions accordingly. You can calculate the aspect ratio from websites such as [https://calculateaspectratio.com](https://calculateaspectratio.com).

  ### Why do I receive the same message body twice in a push notification?

  If you are custom handling your push notifications and using `CleverTapAPI.createNotification()` and your own function (for example: `sendNotification()`) for displaying notifications in the custom message listener service, the message may be sent twice. Remove the `sendNotification()` method and use the `CleverTapAPI.createNotification()` method only. The `CleverTapAPI.createNotification()` method creates a notification that is handled via CleverTap.

  > 🚧 Note
  >
  > If you want to display the notification using your own function, then remove the call to the CleverTap SDK for displaying the notification. This ensures that multiple calls are not made to display a push.

  ### Why do push notifications with images truncate the text in the message?

  This is an expected behavior because Android truncates message text with images. The rendered image shares the space, leaving less space for the message text. There is no fixed character limit for the message text. This depends on the device used to view the push notification. If the user device has a small screen resolution, the message text is cropped after a few words; however, a user may see all the characters on a big-screen resolution.

  When creating notifications, be careful about big text and a big image.

  If you want to see the full text (big text) or you want to add the text in multiple lines, then do either of the following:

  * Send the notification without an image (big image).
  * Custom handle the push notification at your end to support big text and a big image.

  ### Why is my push notification campaign running slowly?

  If you feel that the push campaigns are executing slowly, then it could be due to either of the following reasons:

  * **Personalized Messages**: If personalization is used in the message, the push notifications will not be sent in batches containing multiple users because the push content differs for each user. The push request for each user is made separately, increasing the process time.

  * **Throttle**: The push campaign can execute slowly as it adheres to the throttle limit set for push notifications in the *Campaign Limits* under *Account Settings*. The throttle limit specified from the dashboard during the campaign creation is considered throughout the campaign's lifetime. The throttle for existing campaigns is not updated when the global throttle is updated. The new throttle is considered only for the new campaigns.

  ### Why does the word *modified* display in the title for iOS push notifications?

  The word *modified* displays in push notifications if you enable the advanced option in a campaign. Implement the *Rich Push* notifications in a future update to address this issue. If you are not using *Rich Push*, clear the advanced option you selected in the campaign.
</details>

<details>
  <summary>Push Notification Analysis</summary>

  ### Why are push impressions not raised?

  Check that the Push impression event is enabled with the following steps:

  1. Navigate to *Settings* > *Schema* > *Events*.
  2. Search *Push Impressions* and click the vertical ellipsis.

  <Image align="center" border={true} src="https://files.readme.io/ebf8ae7-Push_Impression_event_FAQ.png" alt="Setup Push Impressions" title="Push Impression event FAQ.png" />

  3. Click **Setup push impressions**. A new window displays.
  4. Click **Save** to enable the option.

  If the steps above fail, check the SDK version used for Android and iOS. The *Push Impression* event feature is available from the v3.5.1 SDK version for Android and from 3.7.1 for iOS.

  For iOS, you must also implement an API in your app. For more information, refer to [Rich Push Notifications](https://developer.clevertap.com/docs/rich-push-notifications). For Android, once your app is on SDK v3.5.1+, the push impression statistics will start showing for qualified users on a Push notification campaign because the feature is already enabled in your event settings.

  For more information, refer to [Custom Android Push Notifications Handling](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling).

  ### How do I analyze the CTA button for a push campaign?

  To track the number of clicks on the Click-To-Action (CTA) buttons of the push notification, navigate to,\
  *Analytics* > *Events*.\
  Search the *Notification Clicked* event filtered by the campaign.

  <Image align="center" border={true} src="https://files.readme.io/a1eeb55-Analyze_CTA_1.png" alt={1232} title="Analyze the CTA Button" />

  On the result, go to *Trend & Properties*. Scroll down to the *Event property* table and filter by *wzrk\_c2a* in the dropdown to view click distribution for campaign buttons.

  <Image align="center" border={true} src="https://files.readme.io/9d5e8c1-Analyze_CTA_2.png" alt={1046} title="Clicks Across Various Buttons" />
</details>

<details>
  <summary> Push Notification Delivery</summary>

  ### How to optimize delivery rates of Push Notifications?

  To optimize delivery rates of push notifications, perform the following:

  * Ensure that all users targeted in the campaign are using the Push Impression-enabled SDK v3.5.0.
  * If you are targeting Android or iOS:
    * **Android**: Android supports out-of-the-box impressions.
    * **iOS**: Check whether the iOS implementation has been completed. For more information, refer to [iOS Push Impression](https://developer.clevertap.com/docs/push-notifications-ios#push-impressions).
  * If the above-mentioned checks are passed, but the push impressions remain low, perform the following:
    * Use Pull Notifications. For more information, refer to [Optimize Delivery](https://docs.clevertap.com/docs/push-optimize-delivery).\
      OR
    * Integrate with other push notification providers, such as [Xiaomi](https://developer.clevertap.com/docs/xiaomi-push-notifications), [Huawei](https://developer.clevertap.com/docs/clevertap-huawei-push-integration), or [Baidu](https://developer.clevertap.com/docs/baidu-push-notifications), to increase reach and deliverability.

  ### What are the timeouts and retry limits for Push Notifications?

  The following are the timeout and retry limits for Push Notifications:

  | Channel     | Timeout (ConnectionRequest)                      | Retry Limits |
  | :---------- | :----------------------------------------------- | :----------- |
  | APNs Push   | 10 Seconds (Read and Connect), 30 Seconds (Read) | 1            |
  | FCM Push    | 10 Seconds                                       | 3            |
  | Xiaomi Push | 10 Seconds                                       | 3            |
  | Huawei Push | 10 Seconds                                       | 3            |
  | Baidu Push  | 10 Seconds                                       | 3            |
  | Chrome      | 10 Seconds                                       | 6            |
  | Firefox     | 10 Seconds                                       | 3            |
  | KaiOS       | 10 Seconds                                       | 3            |
  | Safari      | 10 Seconds (Read and Connect), 30 Sec (Read)     | 3            |

  For more information, refer to the [Channel-Specific Timeouts and Retries](doc:platform-considerations#channel-specific-timeouts-and-retries).

  ### Can I send push notifications from both Firebase and CleverTap in my app?

  Yes, you can mention your own listener service that is implemented In the AndroidManifest.xml file. You can then choose to render the notification either from CleverTap or your own service. For more information, refer to [Custom Android Push Notifications Handling](https://developer.clevertap.com/docs/android#section-custom-android-push-notifications-handling).
</details>

<details>
  <summary>User Interaction</summary>

  ### Does a push notification appear for an inactive device after it becomes active?

  The user's device may be inactive if the user's internet service is unavailable or the phone is switched off or out of the network/coverage area. The user does not receive any notification. However, a notification is delivered based on the TTL period when the user gets connectivity later.

  ### Why do Android users receive two notifications from the same campaign after integrating Xiaomi Push services?

  For a greater chance of delivery success, we send a push notification through both Xiaomi Cloud Push and Firebase Cloud Messaging (FCM) push services. If a message is delivered and rendered through one of these push services, the notification from the other cloud service is suppressed by the CleverTap SDK.

  If you custom render the push notifications, then the push notifications are being rendered by your custom code. You will have to implement the suppression mechanism at your end.

  The mechanism should check if a push notification has already been rendered for the campaign and suppress the payload from another push service. This ensures the user receives only one push notification for a given campaign.

  ### How do you add a small icon in the push notification?

  Sometimes, the small icon may not appear in the notification even if you add the small icon in the Android manifest file.

  To set a custom notification icon (only for the small icon), add the following metadata entry in your AndroidManifest.xml:

  ```xml
  <meta-data
      android:name="CLEVERTAP_NOTIFICATION_ICON"
      android:value="ic_stat_red_star"/> <!-- name of your file in the drawable directory without the file extension. -->
  ```

  If the small icon still does not appear, check the following in your Android project:

  * Your app must have a small icon file in your drawable resources.
  * You are using a PNG file and not a JPEG file for the small icon.
  * The background in your icon file is transparent.
  * The small icon image must be monochrome without alpha channels (RGB colors) and with 60-70% opacity, such as white pixels on a transparent backdrop.

  For more information, refer to [Set the Small Notification Icon](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon) and [Create App Icons with Image Asset Studio](https://developer.android.com/studio/write/image-asset-studio) in the Android documentation.

  ### How can I have a small icon on the top left screen instead of a white square box?

  The small icon must be set at the code level in the manifest file. The small icon must be alpha. You can create the icon using the Image Asset Studio tool included in the Android Studio.

  For more information, refer to [Set the Small Notification Icon](https://developer.clevertap.com/docs/android#section-set-the-small-notification-icon).
</details>

<details>
  <summary>Configuration</summary>

  ### My application infrastructure can only support handling 100K users in a given time duration. How do I achieve this rate-limiting from CleverTap while sending push notifications?

  This can be achieved by throttling campaigns. The push campaign adheres to the throttle limit set for push notifications in the *Campaign Limits* under *Account Settings*.\
  This can then be enabled or disabled during the setup of campaign creation. For more information, refer to [Throttling](https://docs.clevertap.com/docs/setup-push-notification#push-campaign-throttling).

  ### Where can I update Xiaomi/Huawei credentials?

  After you have an app secret and package name, you must update it on the CleverTap dashboard using the following steps:

  1. Click **Settings** from the dashboard.
  2. Click **Channels** > **Mobile push**. The push notification setup page displays.
  3. Click **Huawei** or **Xiaomi** push notifications and add the App secret and package name/App ID.

  <Image align="center" border={true} src="https://files.readme.io/afab9c0-New_final_Previous_Campaigns_mobile_push_settings_xiaomi_huwaei.png" alt="Xiaomi/Huawei credentials" title="New final Previous Campaigns_mobile_push_settings_xiaomi_huwaei.png" />

  ### How can I redirect the users to MWeb when they click the push notification?

  To redirect users to MWeb, you can add the page URL as a deep link when creating a campaign. The users are redirected to the page specified in the deep link. For example, [https://clevertap.com/](https://clevertap.com/).

  ### How do you resolve the popup for installing the HMS core app on non-Huawei devices?

  This popup appears on non-Huawei devices after implementing Huawei push notifications. To avoid this popup, check for HMS class on all devices and trigger the push registration service only if `HMSclass` is available on the device. For more information, refer to [Preferentially Using HMS for Determination](https://developer.huawei.com/consumer/en/doc/development/Tools-Guides/push-conversion-0000001050060304#EN-US_TOPIC_0000001050060304__section330733914368) in the Huawei documentation.

  ### Why do I see 0% push notifications for Xiaomi and 100% for Firebase (FCM)?

  The Xiaomi/Baidu/Huawei push notifications may show 0% on campaign stats if all the notifications are delivered through FCM. For a greater chance of delivery success, CleverTap sends a push notification through the Xiaomi/Baidu/Huawei Push and Firebase Cloud Messaging (FCM) push services. If a message is delivered through any one of these push services, then the notification from the other cloud services is suppressed. No priority is defined for the messaging service, and there are no changes to the current flow of FCM. This ensures the user receives the push notification only once.

  The services that are not integrated with CleverTap are shown as *N/A*.

  ### How do I disable IDFA tracking in iOS?

  To disable the IDFA tracking, follow the steps below:

  1. Check that you have not added the `CleverTapUseIFA` flag in the info.plist file.
  2. Remove the *AdSupport* framework from your build if you add it to your linked libraries.
  3. When submitting your app to the app store, you are asked if your app supports IDFA. Select *No*.

  > 📘 Note
  >
  > IDFA is not supported for iOS versions 14 and higher.

  ### Is there an action ID for iOS similar to Android?

  The iOS equivalent for action ID is *category*. These categories are static and must be shipped with the app. You can add the name of the category while creating a campaign. Each category must be registered with the app. This category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four actions associated with it. The actual number of actions actually displayed for the category depends on the type of notification delivered. Users can perform multiple actions for the notification. For example, a single media push notification can have two buttons such as, *Buy Now* and *Save for Later*.

  For more information, refer to [Advanced iOS Push Notifications](https://developer.clevertap.com/docs/ios#section-advanced-ios-push-notifications).

  ### What is the format of the push notification payload for Android?

  Following is an example payload for Android:

  ```json
  {
    "wzrk_acct_id": "CleverTap_Account_ID",
    "custom key": "custom value",
    "wzrk_acts": [
      {
        "l": "Action button 1",
        "dl": "deep link for action button 1",
        "id": "action id of the action button 1",
        "ico": "Icon resource identifier for action button 1"
      }
    ],
    "nm": "the message of the push",
    "nt": "title of the push",
    "pr": "max",
    "ico": "large icon url",
    "wzrk_pivot": "wzrk_default",
    "wzrk_sound": "Custom sound file name",
    "wzrk_cid": "Notification Channel ID",
    "wzrk_nms": "Summary text field",
    "wzrk_rnv": true,
    "wzrk_ttl": 1586148291,
    "wzrk_push_amp": false,
    "wzrk_bc": 1,
    "wzrk_bi": "badge_icon",
    "wzrk_bp": "image URL",
    "wzrk_ck": "collapse notification",
    "wzrk_dl": "deep link url here",
    "wzrk_dt": "FIREBASE",
    "wzrk_id": "0_0",
    "wzrk_pn": true,
    "wzrk_st": "subtitle"
  }
  ```

  This payload is received as bundle data, and the JSON is only for representation purposes.

  Following are the keys for the push notification:

  | Key             | Description                                                                                                     |
  | :-------------- | :-------------------------------------------------------------------------------------------------------------- |
  | wzrk\_acct\_id  | CleverTap account ID                                                                                            |
  | custom key      | Any custom key the user can add                                                                                 |
  | wzrk\_acts      | Action button payload                                                                                           |
  | nm              | Notification message                                                                                            |
  | nt              | Notification title                                                                                              |
  | ico             | Icon resource identifier for an action button                                                                   |
  | wzrk\_pivot     | Variant A or B of A/B campaign                                                                                  |
  | wzrk\_cid       | Notification channel ID                                                                                         |
  | wzrk\_nms       | Summary text                                                                                                    |
  | wzrk\_rnv       | A flag to raise notification viewed event. If present and not empty, it will raise a notification viewed event. |
  | wzrk\_ttl       | Time to live (TTL)                                                                                              |
  | wzrk\_push\_amp | Push amp                                                                                                        |
  | wzrk\_bc        | Badge count                                                                                                     |
  | wzrk\_bi        | Badge icon                                                                                                      |
  | wzrk\_bp        | Image URL                                                                                                       |
  | wzrk\_ck        | Collapse key                                                                                                    |
  | wzrk\_dl        | Deep link URL                                                                                                   |
  | wzrk\_dt        | Service used to send the message (e.g. FIREBASE)                                                                |
  | wzrk\_id        | Campaign ID                                                                                                     |
  | wzrk\_pn        | Push notification. If present, this notification is sent from CleverTap.                                        |
  | wzrk\_st        | Subtitle                                                                                                        |
  | wzrk\_pid       | Refers to Campaign ID with the date of the campaign creation.                                                   |

  ### What is an Action ID in Android?

  For Android push notifications, you can add up to three action buttons. You can define the title, deep link, and the action ID of each button.

  The application uses the value of the action ID to identify the button that was clicked.

  The default behavior (when closing the notification is handled using CleverTap SDK) for clicking on the action button is that the user is directed to the deep link or application, and the notification is dismissed automatically.

  You can handle the closing of the notification yourself at the code level, and only then your app can get the action ID values. Based on the action ID value of the action button clicked you can perform any operations as per your requirement.

  For more information on Android, refer to [Action Buttons](https://developer.clevertap.com/docs/android#section-action-buttons).

  **For iOS**: You must implement a category for iOS. You can enter the name of the category while creating the campaign. Each category must be registered with the app. Each category is associated with actions that the user can perform when a notification of rich media type is delivered. Each category can have up to four associated actions, although the number of actions displayed depends on the type of notification delivered. This enables users to take multiple actions for the notification. For example, a single media push notification can have two buttons such as, *Buy Now* and *Save for Later*.

  For more information on iOS, refer to [Advanced iOS Push Notifications](https://developer.clevertap.com/docs/ios#section-advanced-ios-push-notifications).

  ### What is the format of the push notification payload for iOS?

  Following is an example payload for iOS:

  ```json
  [CleverTap]: Handling notification: {
    "W$dt" = APPLE;
    "W$id" = "1591036839_20200601";
    "W$pivot" = "wzrk_default";
    "W$rnv" = 1;
    aps =   {
      alert =     {
        body = Testing;
        title = Campaign;
      };
      "mutable-content" = 1;
      sound = default;
    };
    "ct_mediaType" = image;
    "ct_mediaUrl" = "https://formpicture.com/photo.png";
    "wzrk_acct_id" = "TEST-Z48-Z75-785Z";
    "wzrk_dl" = "https://www.google.com";
  }
  ```

  Following are the keys for the push notification:

  | Key             | Description                             |
  | :-------------- | :-------------------------------------- |
  | W$dt            | Notification service                    |
  | W$id            | Campaign ID\_date                       |
  | W$pivot         | Variant                                 |
  | W$rnv           | Raises notification viewed              |
  | body            | Notification message                    |
  | title           | Notification title                      |
  | mutable-content | Value is 1 if enabled and 0 if disabled |
  | sound           | Notification sound (default is OS)      |
  | ct\_mediaType   | Type of media                           |
  | ct\_mediaUrl    | Media link                              |
  | wzrk\_acct\_id  | Account ID                              |
  | wzrk\_dl        | Deeplink URL                            |

  ### Why do I see an increase in the number of errors after migrating to the NextGen Segment Builder?

  After migrating to the NextGen Segment Builder, you may notice an increase in errors. This is due to a fundamental change in how user properties are evaluated.

  Previously, filters in the *Who* section were evaluated during campaign user qualification in the old segment builder. With the NextGen Segment Builder, this evaluation now happens during campaign dispatch. Here is how it works:

  Consider an example of a campaign that is triggered by user action and includes filters such as *region = India* or *gender = Male*.

  * **During the qualification phase**, all user profiles performing the specified event qualify for the campaign, regardless of the user property.
  * **During the dispatching phase**, the user properties for the qualifying profiles are fetched, which will be used for evaluation.
    * Profiles without tokens are marked as unreachable, as their User Properties cannot be evaluated.
    * Profiles with tokens are evaluated:
      * Those matching the filters (for example, *Region = India and Gender = Male*) receive the campaign notification.
      * Those not matching the filters are silently dropped from the campaign.
      * User properties will not be available for profiles without tokens, and hence they are marked as errors. These errors appear in the system for easier identification.

  While silently dropped profiles are of no direct interest to the campaign and thus excluded, they can still be identified using the [Find People/Segments](doc:find-people) page from the CleverTap dashboard. For more information on user profile properties and events, refer to [User Profiles ](doc:user-profiles)and [Events](doc:events).

  > 📘 Note
  >
  > The NextGen Segment Builder is currently in Private Beta. For more information, refer to [NextGen Segment Builder](doc:segmentation).
</details>

# Troubleshooting

<details>
  <summary>Push Notification Errors in iOS</summary>

  ### APNS Device Token Does Not Match The Specified Topic

  *Apple Push Notification* service (APNs) returns this when the device token does not match the specified topic.

  In the context of CleverTap, you get this error when you try to send the notification with the wrong certificate. Check that you are using a production certificate for the production environment to avoid unsatisfactory configurations.

  Check the provisioning profile used to deploy the app and send the device token to the CleverTap dashboard. To avoid this error, the provisioning profile's  *App Bundle ID* and the CleverTap push certificate (p12 certificate) must match.

  ### APNS Unregistered

  The *Push* notification delivery to the target has failed as the device token is inactive for the specified topic. If the device token is not valid/inactive,  the notification is not delivered unless the user installs the app again.

  ### APNS Topic Disallowed

  The topic is currently the bundle identifier of the target application on an iOS device. The *APNS Topic Disallowed* error appears when you specify the incorrect *App Bundle ID* in the *Account Settings*.

  For more information, refer to [Registering Your App with APNs](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns) in the Apple documentation.

  To resolve this error, check the value of the *App Bundle ID* and *APNs push mode* that you have configured in the CleverTap Dashboard under *Push Settings*.

  ### APNS Temporarily Blacklisted

  You are temporarily blacklisted from sending push notifications to the device because you sent bad tokens. The push notification will not be delivered for some duration.

  ### APNS Failed Delivery

  The notification to the device sent from CleverTap failed to deliver due to either of the following reasons:

  * The app was uninstalled, and the token is no longer valid.
  * You have sent too many notifications successively and quickly to the same device.

  If the user has uninstalled the app, not much can be done to deliver the notification.

  For more information, refer to [Handling Notification Responses from APNs](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/handling_notification_responses_from_apns) in the Apple documentation.

  ### APNs Bad Device Token

  The push notification delivery to the target device has failed due to an invalid token. The APNs bad device token error occurs when there is a mismatch between the APN push mode on your app and the CleverTap dashboard.

  For example, you have set the APNs push mode in your app to the *development* stage, and in the CleverTap dashboard, you have set up the APNs to the *production* stage.

  To check your CleverTap dashboard APNs push mode, navigate to *Settings* > *Engage* > *Channels* > *Mobile Push* > *iOS*.
</details>

<details>
  <summary> Push Notification Errors in Android</summary>

  ### Invalid FCM API Key

  An invalid FCM API key error is displayed when the FCM API key in the CleverTap dashboard is incorrect. You cannot send any notifications until you add an FCM API key to your settings.

  Follow the steps to update the FCM API key:

  1. Navigate to *Settings* > *Engage* > *Channels* > *Mobile Push*.
  2. Update the valid FCM API key as it is displayed in your Firebase project.

  <Image align="center" border={true} src="https://files.readme.io/e19b51f0c6ba7545df72006184cc25d9ebc84098c934ea79d082b98043b36abf-FCM_Screenshot_Update.png" alt="Set FCM Credentials" />

  For more information, refer to [Find Your FCM Sender ID & FCM Server API Key](https://developer.clevertap.com/docs/find-your-fcm-sender-id-fcm-server-api-key).

  ### FCM Token Invalid

  The FCM token is not linked to any device that has your app. If the token is not valid, notifications are not delivered. Check the format of the FCM project number and registration token that you pass on to CleverTap.

  For more information, refer to [Troubleshooting Push Notifications](https://developer.clevertap.com/docs/troubleshooting-push-notifications).

  ### FCM Error

  This is a Firebase (Android) error. The FCM error is not part of the standard published list and is sometimes incorrectly identified as an Android bug.

  ### FCM Not Registered

  Most likely, the users have uninstalled the app from their devices. One of the common non-technical errors is *Undelivered due to App Uninstall* in campaign reports. This error occurs when the users uninstall your app while you are trying to reach them via a push notification.

  The *FCM Not Registered* error occurs in two scenarios:

  * When the users have uninstalled your app and you are trying to schedule a push notification for them.
  * When users have cleared the device cache memory, which in turn removes the token from the device.

  ### Wrong FCM API Key

  An FCM sender ID mismatch occurs when the sender ID entered in the CleverTap dashboard under *Push Notification* settings does not match the sender ID in the FCM project for your app created on Firebase.

  You must match the sender ID/server keys at the following three locations:

  * App-level, which registers the token with the said FCM sender ID mentioned.
  * In the CleverTap dashboard.
  * FCM project.

  If you have checked the sender ID for mismatch and the error still persists, check the following:

  * Does the app build and the CleverTap account contain mismatched sender IDs?
  * Do you have multiple Firebase projects?
  * Do you have multiple Platform IDs if your app uses two Firebase projects?

  ### FCM Legacy Push Discontinued

  Firebase deprecated its legacy APIs starting June 20, 2023, and discontinued them from June 2024.

  You must migrate to the new FCM V1 APIs to ensure uninterrupted delivery of the push notifications. For more information about migration steps, refer to [Configure Push Notifications](https://developer.clevertap.com/docs/android-push#configure-push-notifications).
</details>

<details>
  <summary>Limit Exceeded Error</summary>

  ### Daily Limit Exceeded

  While creating a recurring push campaign, you can set the daily limit. For example, you can set a daily send limit to 10,000 per day, after which you get a *Daily limit Exceeded* error. You can also set an overall cap limit to 1,00,000 users, after which the campaign stops.

  You would generally set a daily limit in a triggered campaign where you are using a live segment. These campaigns are triggered based on an event and therefore, you would want a daily limit for your campaigns.

  <Image align="center" border={true} src="https://files.readme.io/1f29c93-Daily_Limit_Exceeded_v2.png" alt={1386} title="Daily Limit Exceeded v2.png" />

  You can set the campaign limits within the *Who* section while creating the campaign.

  ### Per Run Limit Exceeded

  The *Per Run Limit* is a limit enforced on the number of users who are sent in one campaign run. For example, you can set a maximum segment limit to 100,000 users, and the campaign stops running after the set limit for each run.

  The *Per Run Limit Exceeded* error occurs when the campaign stops running after the number of qualified users exceeds the set limit.

  You would generally set a per-run limit for past behavior and custom list segments. This is because the campaign is sent to all the qualified users based on their past actions. Therefore, you would want a per-run limit for these campaigns.

  <Image align="center" border={true} src="https://files.readme.io/f04bdde-New_final_Campaigns_per_run.png" width="100%" alt={1388} title="New final Campaigns_per_run.png" />

  While creating the campaign, you can set the maximum segment size from the *Who* section.

  ### FCM Rate Limit Exceeded

  Each Firebase project using the HTTP v1 APIs is strictly limited to a specific number of requests per minute. When your account's per-minute limit is reached, the FCM V1 API responds with 429 (Quota Exceeded). However, CleverTap attempts to resend the request up to three times before marking it as a failed delivery and raising the *FCM Rate limit exceeded* error. To optimize this, you can use CleverTap's *Throttle* feature under the *Campaign Limits* section to help you stay within your allocated quota. For more information, refer to [HTTP v1 API Rate Limits](https://staging.docs.dev.clevertap.net/docs/android-push#http-v1-api-rate-limits).
</details>