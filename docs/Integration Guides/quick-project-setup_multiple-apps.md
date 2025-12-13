---
title: Quick Project Setup with multiple apps
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: This page must be available only to users who have access to this link.
  robots: noindex
next:
  description: ''
---
Create a project quickly after you log on to CleverTap. You can choose from the following platforms:

  * [Android](https://docs.clevertap.com/docs/quick-project-setup#section-setup-your-android-app)
  * [iOS](https://docs.clevertap.com/docs/quick-project-setup#section-setup-your-i-os-app)
  * [Website](https://docs.clevertap.com/docs/quick-project-setup#section-setup-your-website)
  * [API](https://docs.clevertap.com/docs/quick-project-setup#section-setup-api)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bfe1a41-Online_Signup_project_create.png",
        "Online_Signup_project_create.png",
        578,
        854,
        "#f8f9fa"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
You can choose the platform for your app. Select "Native" for native Android and iOS apps. You can also select other hybrid platforms for iOS and Android such as:
* [Cordova](https://developer.clevertap.com/docs/cordova)
* [Unity](https://developer.clevertap.com/docs/unity)
* [Xamarin](https://developer.clevertap.com/docs/xamarin)
* [React Native](https://developer.clevertap.com/docs/react-native)
* [Flutter](https://developer.clevertap.com/docs/flutter-sdk)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08183f3-Online_Signup_Account_Integration.png",
        "Online_Signup_Account_Integration.png",
        1189,
        654,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Setup App"
}
[/block]
You can set up the integration for your app from Settings > Project. Alternatively, you can simply select the list from the dashboard top menu click Create New Project.

#Setup your Android app

Follow the steps to set up your Android app.

1. Enter the PlayStore URL for your app. 
2. Integrate the CleverTap SDK. For more information, see [SDK](https://developer.clevertap.com/docs/android-quickstart-guide#section-step-1-install-sdk)
[block:code]
{
  "codes": [
    {
      "code": "dependencies {\n    implementation 'com.clevertap.android:clevertap-android-sdk:3.8.0'\n    implementation 'com.google.firebase:firebase-messaging:17.3.3'\n    implementation 'com.google.android.gms:play-services-base:16.0.1'\n    implementation 'com.android.support:support-v4:28.0.0'\n    //Mandatory for CleverTap Android SDK v3.6.4 and above add the following -\n    implementation 'com.android.installreferrer:installreferrer:1.0'\n    }\n// at the end of the build.gradle file\napply plugin: 'com.google.gms.google-services'",
      "language": "json"
    }
  ]
}
[/block]
3. Implement CleverTap dependencies. 

Add the following snippet within the tags in the AndroidManifest.xml file. For more information, see  [Android Manifest XML](https://developer.clevertap.com/docs/android-quickstart-guide#section-step-2-add-your-clever-tap-credentials-in-android-manifest-xml)
[block:code]
{
  "codes": [
    {
      "code": "<application\n    android:label=\"@string/app_name\"\n    android:icon=\"@drawable/ic_launcher\"\n    android:name=\"com.clevertap.android.sdk.Application\">\n  ",
      "language": "xml"
    }
  ]
}
[/block]
Add the following snippet to the same manifest file to allow the CleverTap SDK to access the Internet.
[block:code]
{
  "codes": [
    {
      "code": "<!-- Required to allow the app to send events and user profile information ->\n<uses-permission android:name=\"android.permission.INTERNET\"/>\n<!--Recommended so that CleverTap knows when to attempt a network call -->\n<uses-permission android:name=\"android.permission.ACCESS_NETWORK_STATE\"/>\n",
      "language": "xml"
    }
  ]
}
[/block]
 Add the following snippet to the same file to allow the CleverTap SDK to access the Internet.
[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI clevertapDefaultInstance = CleverTapAPI.getDefaultInstance(getApplicationContext());\n",
      "language": "xml"
    }
  ]
}
[/block]

4. Set up Firebase Cloud Messaging (FCM) to send push notifications using CleverTap.
Register the services inside the <application></application> tags of the Android manifest file.

For more information, see [Using FCM version 18.00 and above](https://developer.clevertap.com/docs/using-fcm-version-1800-and-above). 

[block:code]
{
  "codes": [
    {
      "code": "<service\n    android:name=\"com.clevertap.android.sdk.FcmTokenListenerService\">\n    <intent-filter>\n        <action android:name=\"com.google.firebase.INSTANCE_ID_EVENT\"/>\n    </intent-filter>\n</service>\n\n<service\n    android:name=\"com.clevertap.android.sdk.FcmMessageListenerService\">\n    <intent-filter>\n        <action android:name=\"com.google.firebase.MESSAGING_EVENT\"/>\n    </intent-filter>\n</service>\n\n",
      "language": "xml"
    }
  ]
}
[/block]
5a.  Setup a notification channel.  You must set a notification channel to send push notification for Android version O and above. For more information, see [Notification Channel](https://developer.clevertap.com/docs/android#section-push-notifications-for-android-o) 

Add the following snippet in the onCreate() method of the application’s MainActivity class to create Android notification channels.

[block:code]
{
  "codes": [
    {
      "code": "CleverTapAPI cleverTapAPI = CleverTapAPI.getDefaultInstance(getApplicationContext());\ncleverTapAPI.createNotificationChannel(getApplicationContext(),\"YourChannelId\",\"Your Channel Name\",\"Your Channel Description\",NotificationManager.IMPORTANCE_MAX,true);\n\n",
      "language": "java"
    }
  ]
}
[/block]
5b. Complete setup. Check that the events and engagement channels are working.

To complete push notification integration and enable advanced settings, go to [mobile push channel](https://developer.clevertap.com/docs/android#section-push-notifications).

6. Test your integration.

To start sending custom events to CleverTap using the Android SDK, call the `pushEvent( )` method with the custom event name you want to track.

Use the following to test [events](https://developer.clevertap.com/docs/android-quickstart-guide#section-step-7-track-custom-events) and [user profiles](https://developer.clevertap.com/docs/android-quickstart-guide#section-step-6-add-information-to-a-user-profile):
[block:code]
{
  "codes": [
    {
      "code": "cleverTapAPI.pushEvent(\"Test Event\");\n  ",
      "language": "java",
      "name": "Test events"
    },
    {
      "code": "// Do not call onUserLogin directly in the onCreate() lifecycle method\nHashMap<String, Object> profileUpdate = new HashMap<String, Object>();\nprofileUpdate.put(\"Name\", \"Jack Montana\");    // String\nprofileUpdate.put(\"Identity\", 61026032);      // String or number\nprofileUpdate.put(\"Email\", \"jack@gmail.com\"); // Email address of the user\nprofileUpdate.put(\"Phone\", \"+14155551234\");   // Phone (with the country code, starting with +)\nprofileUpdate.put(\"Gender\", \"M\");             // Can be either M or F\nprofileUpdate.put(\"DOB\", new Date());         // Date of Birth. Set the Date object to the appropriate value first\ncleverTapAPI.onUserLogin(profileUpdate);\n\n",
      "language": "java",
      "name": "Test user profiles"
    }
  ]
}
[/block]
#Setup your iOS app
Follow the steps to set up your iOS app.

1. Enter the AppStore URL for your app. This step is optional.
2. Install the CleverTap SDK.
To start integration, install CocoaPods. To integrate the app manually, see [manual integration](https://developer.clevertap.com/docs/ios-quickstart-guide#section-option-b-manual-install). Add the following snippet above in the Podfile and run the Pod install command to begin the installation of the CleverTap SDK.
[block:code]
{
  "codes": [
    {
      "code": "pod \"CleverTap-iOS-SDK\"",
      "language": "text"
    }
  ]
}
[/block]
3. Integrate SDK. For more information, see [SDK Integration](https://developer.clevertap.com/docs/ios-quickstart-guide#section-step-4-sdk-integration) 
Import the CleverTap SDK to the AppDelegate.swift file. Now add `[CleverTap autoIntegrate]` within the application: `didFinishLaunchingWithOptions`: method.This allows the CleverTap class used to track app launches, to receive in-app notifications, and enable deep link tracking.
[block:code]
{
  "codes": [
    {
      "code": "func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject:AnyObject]?) -> Bool {\n    ...\n    CleverTap.autoIntegrate()\n    ...\n}\n",
      "language": "text"
    }
  ]
}
[/block]
4. Set up push notifications
To integrate iOS push notifications and enable advanced settings, go to [mobile push channel setup](https://developer.clevertap.com/docs/ios#section-push-notifications).

5. Test your integration
Paste the snippet in the viewDidLoad class to start testing events and user profiles:
[block:code]
{
  "codes": [
    {
      "code": "CleverTap.sharedInstance()?.recordEvent(\"Product viewed\")",
      "language": "text",
      "name": "Test Events"
    },
    {
      "code": "let profile: Dictionary<String, AnyObject> = [\n    //Update pre-defined profile properties\n    \"Name\": \"Jack Montana\",\n    \"Email\": \"jack.montana@gmail.com\",\n    //Update custom profile properties\n    \"Plan type\": \"Silver\",\n    \"Favorite Food\": \"Pizza\"\n]\n\nCleverTap.sharedInstance()?.onUserLogin(profile);",
      "language": "text",
      "name": "Test user profiles"
    }
  ]
}
[/block]
#Add Multiple Apps
You can now have multiple apps under a single project. This allows you to use data across apps. For example, if a project has multiple apps, say gaming, media streaming, and music, then you can analyze the consolidated data for all apps in a single view.

To add an app, follow the steps:

1. Click Settings > Project. The Project page appears. 
2. Click the App tab. 
3. Click the + Add App button to add an app. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45b478d-Multiple_apps_add.png",
        "Multiple_apps_add.png",
        751,
        952,
        "#f8f9fb"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
4. Add the required details and click the Add App button. The App ID is a combination of the app name and the account ID. 

5. Integrate your app with CleverTap. For more information, see [Set up App](https://docs.clevertap.com/docs/quick-project-setup#section-setup-app).

The events raised for any of the apps will be received with the app name. For example, app_launched_gaming. This allows you to identify the app of origin for the system or custom event. You can now select the app from the app list during campaign creation. 

You can select multiple apps for sending an App Inbox message. 

You can use multiple apps with the following engagement channels:

## Integrating with App
1. Use the AppID available under Settings->Project->Apps as the Account ID when integrating your app with the CleverTap SDK.
2. This will ensure that all events coming from the App and uniquely identifiable and can be attributed to the App.
[Add Image and link to quick start guides]

For more information on integrating your app see:
  * [Android Quickstart Guide](https://developer.clevertap.com/docs/android-quickstart-guide)
  * [iOS Quickstart Guide](https://developer.clevertap.com/docs/ios-quickstart-guide)

#Channels
Once you have added the apps, profiles have been created and events have started flowing into CleverTap you can start using Campaigns to send engagement to your users
##Mobile push

Push notifications are brief messages you can send to your mobile app users. You can send the following campaigns:
  * [Past Behavior Campaigns](https://docs.clevertap.com/docs/quick-project-setup_multiple-apps#section-past-behaviour-campaigns)
  * [Live Campaigns](https://docs.clevertap.com/docs/quick-project-setup_multiple-apps#section-live-campaigns)

For more information on push campaigns see, [Mobile Push Notifications](https://docs.clevertap.com/docs/push).

### Past Behaviour campaigns
1. Under the who section you can select your targeting criteria for users you want to send out the push to. Ensure that you use the Event Property "CT App Name" = "Your App" to identify and target users basis events in the respective app.
2. You should select the App you want to send this Push Campaign to under "Select An App"
3. Schedule your notification and the campaign will be sent to the target user.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9524445-Campaigns_Who.png",
        "Campaigns_Who.png",
        1241,
        1475,
        "#fafaf9"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
### Live Campaigns 
1. Under the who section you can select you targeting criteria for users you want to send out the push to. Ensure that you use the Event Property "CT App Name" = "Your App" to identify and target users basis events from respective app.
2. You should select the App you want to send this Push Campaign to under "Select An App"
3. Schedule your notification and the campaign will sent to the target user.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e2cef47-Screenshot_2020-11-24_at_11.04.19_AM.png",
        "Screenshot 2020-11-24 at 11.04.19 AM.png",
        2880,
        1364,
        "#f6f6f8"
      ]
    }
  ]
}
[/block]
##Mobile In-App
You can send  In-App messages with Images, GIFs, video, and audio.

1. Under the Who section the Apps you add as targeting criteria for the event are the apps the InApp is eligible for delivery.
2. Once CleverTap receives the Target Event from any of the apps in the criteria the In-app that has been scheduled will be sent to the App the Target Event was received from.
3. If you use the "Limit to users who do this Event for the First Time" option, CleverTap will restrict the delivery to only the first App+Event that matches the targeting criteria only. InApp will be only delivered once.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6670969-Campaigns_Who_Mobile_inapp.png",
        "Campaigns_Who_Mobile_inapp.png",
        1010,
        536,
        "#f9fafc"
      ],
      "border": true
    }
  ]
}
[/block]
For more information, see [In-App Message](doc:inapp-campaigns).
##SMS
SMS notifications are brief text messages you can send to your app or website users even when they are outside of your app.

1. You can select the targeting criteria based on the Event + "CT App Name" filter.
2. SMS will be sent to mobile number on the profile if the targeting criteria is met.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d968a7a-Campaigns_Who_SMS.png",
        "Campaigns_Who_SMS.png",
        1094,
        606,
        "#fafafa"
      ]
    }
  ]
}
[/block]
For more information on SMS messages, see [SMS](doc:sms).
##App Inbox
App Inbox is a messaging channel that lets you deliver rich, individually customized content to your customers. You can send the following campaigns:

  * [Past Behavior Campaigns](https://docs.clevertap.com/docs/quick-project-setup_multiple-apps#section-past-behaviour-campaigns)
  * [Live Campaigns](https://docs.clevertap.com/docs/quick-project-setup_multiple-apps#section-live-campaigns)

For more information see, [App Inbox](doc:app-inbox).

### Past Behaviour Campaigns
1. Similar to Push Campaign. You can define the targeting criteria under the Who section.
2. Select the app to which the App Inbox message should be delivered.
3. When the targeting criteria are met, the App Inbox campaign is delivered to the target app.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5aafa3e-Campaigns_Who_app_inbox.png",
        "Campaigns_Who_app_inbox.png",
        1263,
        700,
        "#fafbfc"
      ]
    }
  ]
}
[/block]
### Live Action Campaigns
1. Under the Who section the Apps you add as targeting criteria for the event are the apps the App Inbox message is eligible for delivery.
2. Once CleverTap receives the Target Event from any of apps in the targeting criteria the App Inbox message that has been scheduled will be sent to the App the Target Event was received from.
3. If you use the "Limit to users who do this Event for the First Time" option, CleverTap will restrict the delivery to only the first App+Event that matches the targeting criteria only. InApp will be only delivered once.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/df3ff67-Screenshot_2020-11-24_at_11.06.15_AM.png",
        "Screenshot 2020-11-24 at 11.06.15 AM.png",
        2880,
        1074,
        "#f6f6f9"
      ]
    }
  ]
}
[/block]
##Native Display
1. Works similar to inApps and App Inbox. You can define your targeting criteria and include "CT App Name" to target events from specific apps.
2. Native Display will be delivered to any of the apps added in the targeting criteria from which the event is received.
3. If you select "Limit to Users who do this event for the First Time" , Native Display campaign will only be delivered to the first App from which event is received that matches the targeting criteria


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/77cab4f-Campaigns_Who_Native_display.png",
        "Campaigns_Who_Native_display.png",
        1079,
        537,
        "#f9fafc"
      ]
    }
  ]
}
[/block]
For more information, see [Native Display](doc:native-display).
##Email

1. Under the Who section you can define your targeting criteria using behavior and Events(with property CT App Name) to send email based on the criteria.
2. Email will be send on the email linked to qualified user profiles

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f8c6af-Campaigns_Who_Email.png",
        "Campaigns_Who_Email.png",
        1176,
        645,
        "#fafafb"
      ]
    }
  ]
}
[/block]
For more information, see [Email](doc:email).
## API
API's only support Past behaviour campaigns.
### Mobile Push and App inbox
1. To create a campaign via API in the payload the only new parameter that you need to add is  the "App Name" to which the push notification must be sent.

[block:code]
{
  "codes": [
    {
      "code": "{\n    \"name\": \"UAT API\",\n    \"send_to_all_devices\": false,\n    \"estimate_only\": false,\n    \"target_mode\":\"push\",\n    \"where\": {\n    \t\"event_name\": \"Added To Cart\",\n        \"from\": 20201101,\n        \"to\": 20201120 \n    },\n    \"app_name\": \"US edit\",\n    \"respect_frequency_caps\": false,\n    \"content\": {\n        \"title\": \"api\",\n        \"body\": \"How are you doing today?\",\n        \"platform_specific\": {\n            \"android\": {\n            \t\"wzrk_cid\": \"BRTesting\"\n            }\n        },\n        \"sender_name\":\"clevertap\"\n    },\n    \"devices\": [\n        \"android\"\n    ],\n    \"when\": \"now\"\n}",
      "language": "json"
    }
  ]
}
[/block]
# Journeys
1. No Support for push campaigns in journeys.
2. Can support live campaigns for inapp,,email,sms and native display

#Setup your Website

1. Add Website URL
Enter the Website URL for your project.

2. Integrate website
Paste the snippet in the <head></head> section of your website.
[block:code]
{
  "codes": [
    {
      "code": "<script type=\"text/javascript\">\n    var clevertap = {event:[], profile:[], account:[], onUserLogin:[], notifications:[], privacy:[]};\n // replace with the CLEVERTAP_ACCOUNT_ID with the actual ACCOUNT ID value from your Dashboard -> Settings page\nclevertap.account.push({\"id\": \"CLEVERTAP_ACCOUNT_ID\"});\nclevertap.privacy.push({optOut: false}); //set the flag to true, if the user of the device opts out of sharing their data\nclevertap.privacy.push({useIP: false}); //set the flag to true, if the user agrees to share their IP data\n(function () {\n        var wzrk = document.createElement('script');\n        wzrk.type = 'text/javascript';\n        wzrk.async = true;\n        wzrk.src = ('https:' == document.location.protocol ? 'https://d2r1yp2w7bby2u.cloudfront.net' : 'http://static.clevertap.com') + '/js/a.js?v=0';\n        var s = document.getElementsByTagName('script')[0];\n        s.parentNode.insertBefore(wzrk, s);\n})();\n</script>\n\n",
      "language": "javascript"
    }
  ]
}
[/block]
3. Set up push notifications
To integrate and enable web push notifications, go to [web push channel setup] (https://developer.clevertap.com/docs/web#section-web-push).

4. Test integration
Paste the following snippet in your browser’s console to start testing.
[block:code]
{
  "codes": [
    {
      "code": "clevertap.event.push(“Event Name”);",
      "language": "text",
      "name": "Test events"
    },
    {
      "code": "clevertap.profile.push({\n\"Site\": {\n    \"Name\": \"Jack Montana\", // User's name\n    \"Email\": “jackmontana@example.com”\n    }\n});\n",
      "language": "text",
      "name": "Test user profiles"
    }
  ]
}
[/block]
#Setup API

Set up your API to use events and user profiles. For more information on setting up API, see the [API Quickstart Guide](https://developer.clevertap.com/docs/api-quickstart-guide)

1. Upload to the API endpoint:
https://api.clevertap.com/1/upload



[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Use the URL based on your location:\n  * India - in1.api.clevertap.com\n  * Singapore - sg1.api.clevertap.com\n  * U.S - us1.api.clevertap.com"
}
[/block]
2. Use the JSON payload for events and user profiles.


[block:code]
{
  "codes": [
    {
      "code": "{\n    \"d\": [\n        {\n            \"FBID\": \"34322423\",\n            \"ts\": 1468308340, // time when the event occurred in UNIX epoch value in seconds\n            \"type\": \"event\",\n            \"evtName\": \"Product viewed\",\n            \"evtData\": {\n                \"Product name\": \"Casio Chronograph Watch\",\n                \"Category\": \"Mens Watch\",\n                \"Price\": 59.99,\n                \"Currency\": \"USD\"\n            }\n        },\n        {\n            \"identity\": \"jack@gmail.com\",\n            \"ts\": 1468208340,\n            \"type\": \"event\",\n            \"evtName\": \"Charged\",\n            \"evtData\": {\n                \"Amount\": 300,\n                \"Currency\": \"USD\",\n                \"Payment mode\": \"Credit Card\",\n                \"Delivery By\": \"$D_1468322268\",\n                \"Items\": [\n                    {\n                        \"Category\": \"books\",\n                        \"Book name\": \"The millionaire next door\",\n                        \"Quantity\": 1\n                    },\n                    {\n                        \"Category\": \"books\",\n                        \"Book name\": \"Achieving inner zen\",\n                        \"Quantity\": 4\n                    }\n                ]\n            }\n        }\n    ]\n}\n",
      "language": "json",
      "name": "Event Sample Payload"
    },
    {
      "code": "{\n    \"d\": [\n    {\n    \"identity\": \"1189549\",\n    \"ts\": 1468308340,\n    \"type\": \"profile\",\n    \"profileData\": {\n        \"Name\": \"Jack Montana\",\n        \"Name\": {\"$delete\" : 1}, //this will delete the value of name\n        \"Email\": \"jack@gmail.com\",\n        \"Phone\": \"+14155551234\",\n        \"Gender\": \"M\",\n        \"Gender\": {\"$delete\" : 1}, //this will delete the value of gender\n        \"MSG-sms\": false,\n        \"MSG-whatsapp\": true,\n        \"MSG-dndPhone\": true,\n        \"DOB\": \"$D_1487576752\",\n        \"Customer Type\": \"Platinum\",\n        \"Custom Multi Value\":{\"$remove\":[\"shoes\",\"bags\"]}, // To remove Multi Value properties\n        \"Custom Multi Value\":{\"$add\":[\"shoes\",\"bags\"]},  //To add Multi Value properties\n        \"My Number 1\": {\"$incr\" : 10}, //To increment integer data\n        \"My Number 2\": {\"$decr\" : 30} //To decrement integer data\n            }\n        }\n    ]\n}\n//$delete applicable only to name and gender fields\n\n",
      "language": "json",
      "name": "User Profiles Sample Payload"
    }
  ]
}
[/block]
3. Test integration
Send API request with payload to test integration.