---
title: Delivery Optimization_Campaign_redesign_WIP
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
## Overview

You can optimize push delivery with push implication and sending to app inbox. 

## Optimize with Push Amplification

Push notifications are a great way to engage customers despite the issue of low deliverability on certain device manufacturers. In addition, more and more users choose to opt out of push notifications.

With push amplification at your disposal, you can counter this challenge by enhancing the delivery of push notifications to devices that missed receiving them.

To enable this feature, navigate to *Settings* > *Engage* > *Setup* > *Push Amplification*. Turn on the push amplification toggle as displayed below:

<Image title="1 Delivery optimization toggle.png" alt={1050} className="border" border={true} src="https://files.readme.io/f99e426-1_Delivery_optimization_toggle.png" />

> 🚧 Toggling Push Notification Amplification
>
> Once you turn on push amplification, all the push campaigns created will be amplified from that moment onward and this applies the same way when you turn it off.

Once push amplification is turned on, your campaigns reach more users through your push notifications. You can check these boost numbers on your push campaign stats page.

@DK/PM: ABLE TO HELP CREATE A BETTER STAT PAGE WITH MORE DATA?

![1609](https://files.readme.io/b705c44-Campaigns_stats.png "Campaigns stats.png")

Push amplification can be achieved via retrying the *Push* message as is (where messages are suppressed by the device) and *App Inbox* where the user has chosen to DND the push messages.

> 📘 Support for Push Amplification via Inbox
>
> We support *Push Amplification via Inbox* and retrying push notifications due to delivery issues with certain OEMs. 
>
> If the app is online when *Push* is delivered, the Inbox delivery is done on the next *App Launch* and not immediately after the *Push* is delivered.

## Optimize with App Inbox

Apart from push amplification, you can further increase the delivery of push notifications by sending a copy of the same message to *App Inbox*. 

To send a copy of the push message to **App Inbox**, select the checkbox that appears at the bottom of the message builder of push notification in the *What* section.

![1602](https://files.readme.io/3fa685e-3_Optimize_with_App_Inbox.png "3 Optimize with App Inbox.png")

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

@DK/PM: PLEASE REFER TO ASK ABOVE. DOCS TO UPDATE THE FOLLOWING SCREENSHOT LATER.

<Image title="Campaigns stats.png" alt={1609} className="border" border={true} src="https://files.readme.io/a742f62-Campaigns_stats.png" />
