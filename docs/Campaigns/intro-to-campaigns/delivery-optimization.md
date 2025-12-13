---
title: Delivery Optimization
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

You can optimize push delivery with push implication and sending to app inbox. 

## Optimize with Push Amplification

Push notifications are a great way to engage customers despite the issue of low deliverability on certain device manufacturers. In addition, more and more users choose to opt out of push notifications.

With push amplification at your disposal, you can counter this challenge by enhancing the delivery of push notifications to devices that missed receiving them.

To enable this feature, navigate to *Settings* > *Engage* > *Setup* > *Push Amplification*. Turn on the push amplification toggle as displayed below:

<Image title="Screenshot 2019-01-09 at 6.58.11 AM.png" alt={945} className="border" border={true} src="https://files.readme.io/188e8ce-Screenshot_2019-01-09_at_6.58.11_AM.png" />

> 🚧 Toggling Push Notification Amplification
>
> Once you turn on push amplification, all the push campaigns created will be amplified from that moment onward and this applies the same way when you turn it off.

Once push amplification is turned on, your campaigns reach more users through your push notifications. You can check these boost numbers on your push campaign stats page.

![1580](https://files.readme.io/65a05d4-Push_amplification_report.png "Push amplification report.png")

Push amplification can be achieved via retrying the *Push* message as is (where messages are suppressed by the device) and *App Inbox* where the user has chosen to DND the push messages.

> 📘 Support for Push Amplification via Inbox
>
> We support *Push Amplification via Inbox* and retrying push notifications due to delivery issues with certain OEMs. 
>
> If the app is online when *Push* is delivered, the Inbox delivery is done on the next *App Launch* and not immediately after the *Push* is delivered.

## Optimize with App Inbox

Apart from push amplification, you can further increase delivery of push notification by sending a copy of the same message to *App Inbox*. 

To send a copy of the push message to **App Inbox**, click the checkbox that appears at the bottom of the message builder of push notification in the *What* section.

![1318](https://files.readme.io/777a4b6-New_1.png "New 1.png")

> 📘 App Inbox as its Own Channel
>
> *App Inbox* also exists as a stand-alone channel. For more information, refer to [App Inbox](https://docs.clevertap.com/docs/app-inbox).

  From this screen, you can do the following:

* You can customize the same push message for *App Inbox*. 
  * You can change the title color, message color, background color, and also add filter tags that classify your message into tabs. For more information, refer to [Message Tags](https://docs.clevertap.com/docs/app-inbox#section-message-tags). 
  * You can set a time to live (TTL) for *App Inbox* message in the setup section. For more information on setting up TTL, refer to [Time to Live](https://docs.clevertap.com/docs/app-inbox#section-time-to-live).

## Push Amplification and App Inbox Stats

You can view the stats for push messages copied to *App Inbox* on the *Push stats* page. The percentage boost represents the percentage of messages boosted by *App Inbox* as compared to the total of messages sent via *App Inbox* and *Push Amplification*.

To view the stats for the copied messages, you can use the tab *App Inbox stats*.

<Image title="Push amplification report for App Inbox.png" alt={1580} className="border" border={true} src="https://files.readme.io/1401bf8-Push_amplification_report_for_App_Inbox.png" />
