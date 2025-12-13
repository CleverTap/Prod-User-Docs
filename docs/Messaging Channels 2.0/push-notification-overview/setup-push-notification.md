---
title: Setup
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
# Mobile Push Setup

Set up your mobile push notifications from the CleverTap dashboard. 
Navigate to *Settings > Channels> Mobile push*. 

## Android

Set up and enter credentials for all the platforms that your application supports:

1. [FCM](https://developer.clevertap.com/docs/find-your-fcm-sender-id-fcm-server-api-key)
2. [Xiaomi](https://developer.clevertap.com/docs/xiaomi-push-notifications#section-get-the-apps-package-name-app-id-app-key-app-secret)
3. [Baidu](https://developer.clevertap.com/docs/baidu-push-notifications#section-get-the-apps-api-key-secret-key)
4. [Huwaei](https://developer.clevertap.com/docs/clevertap-huawei-push-integration#section-get-the-apps-app-id-app-secret)


### Notification channels

For Android 8.0 and above, you can create a group of channels that your users. The users can then choose to turn on or turn off the subscription to these channels.  Create a list of channels that will be available in campaign creation. 

## iOS

You can either create and upload an [APNs Auth Key](https://developer.clevertap.com/docs/how-to-create-an-ios-apns-auth-key), or an [APNs Push Certificate](https://developer.clevertap.com/docs/how-to-create-an-ios-apns-certificate).
We recommend that you create and upload an APNs Auth Key.


# Raising Events

<<@vishal, need a short description here>>

## Raising Push Impression Event 

You can raise and record push notifications delivered to your users’ Android devices.

1. Navigate to *Settings* > *Schema* > *Events*.
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
3. Click on **Setup push impressions**. A new window displays.
4. Turn on the *Mobile Push* toggle. 
5. Click on **Save** to enable the option.

After the toggle is on, all the push notifications delivered are recorded under the *Push Impressions* event. The viewed and conversion count from this event is also available under *Analytics* > *Events*.


[block:callout]
{
  "type": "warning",
  "body": "Some things to consider include:\n1. The push event can only be raised for CleverTap SDK version 3.5.1 and above for Android and version 3.5.0 and above for iOS.\n2. If the notification channel is incorrect, the push notification is not delivered on the device and therefore, no event is raised for the push impression.",
  "title": "SDK Considerations"
}
[/block]

## Raising Notification Viewed Event for iOS
To raise the *Notification Viewed* event for iOS, it is mandatory to enable the *Mutable Content* under the iOS section of the campaign creation.

For more information on how to enable *Notification Viewed* for your account, refer to our [developer documentation](https://developer.clevertap.com/docs). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bd5135-campaign_iOS.png",
        "campaign_iOS.png",
        1251,
        1507,
        "#ebe8f0"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]

# Push Campaign Throttling

You can throttle the rate at which CleverTap delivers push notifications under *Settings* > *Setup* > *Campaign Limits*. If your user base is large and all users receive and click on a push notification at roughly the same time to open the app, you could experience a significant, unwanted load on your systems.

By using push campaign throttling, you can meter how quickly CleverTap delivers your notifications.
[block:callout]
{
  "type": "success",
  "title": "Push Campaign Throttling Example",
  "body": "If your reachable audience for a campaign is 500,000 users and your back-end systems can only support up to 20% of them, you can set a throttle limit to 100,000 notifications per 15-minute interval. The entire campaign will then deliver in 1 hour 15 minutes."
}
[/block]