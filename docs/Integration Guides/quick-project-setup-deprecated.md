---
title: Quick Project Setup
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
      "border": true
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

To complete push notification integration and enable advanced settings, navigate to [mobile push channel](https://developer.clevertap.com/docs/android#section-push-notifications).

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
To integrate iOS push notifications and enable advanced settings, navigate to [mobile push channel setup](https://developer.clevertap.com/docs/ios#section-push-notifications).

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
#Setup your Website

1. Website URL
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
To integrate and enable web push notifications, navigate to [web push channel setup] (https://developer.clevertap.com/docs/web#section-web-push).

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

Set up your API to use events and user profiles. For more information on setting up API, see the [API Quick Start Guide](https://developer.clevertap.com/docs/api-quickstart-guide).

1. Upload to the API endpoint:
https://api.clevertap.com/1/upload



[block:callout]
{
  "type": "info",
  "title": "URLs for Your Specific Location",
  "body": "Use the URL based on your location:\n  * India: in1.api.clevertap.com\n  * Singapore: sg1.api.clevertap.com\n  * U.S.: us1.api.clevertap.com"
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