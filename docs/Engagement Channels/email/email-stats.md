---
title: Email Campaign Stats
excerpt: Measure the performance of your Email campaign.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# View Email Campaign Stats

After the email campaign is live, the following events are raised in case of email campaigns:

* *Notification Sent* when the email campaign is sent to the user.
* *Notification Viewed* when the user opens the email campaign.
* *Notification Clicked* when the user clicks on the email campaign.

You can view its stats by navigating to *Campaigns* from the CleverTap dashboard. To do so:

1. Click *Campaigns* from the dashboard. The *All Campaigns* page displays.
2. Select the email campaign you want to view the stats for. Or you can also filter campaigns using the **Filter** button (see figure below).

<Image title="Filter Email Campaign from All Campaigns" alt="Filter Email Campaigns" align="center" border={true} src="https://files.readme.io/3c129f67bad658bba473d9f0f4ccd6d3b13f10b3d4cd99769bee89a1b720472a-11.png">
  Filter Email Campaigns
</Image>

3. Click the campaign to open it. The *Stats* tab displays the following campaign stats: Sent, Viewed, Clicks, CTR, and Converted users.

<Image title="View Email Campaign Hero Stats" alt={2662} align="center" border={true} src="https://files.readme.io/76e4a96-Email_Campaign_Stats.png">
  Campaign Stats
</Image>

The stats card shows the total count and the percentage. You can track the following stats for your email campaign:

* Sent: The total number of emails sent. This count excludes the count for CC Sent and BCC Sent.
* These numbers do not include the CC and CC sent numbers.
* Viewed: It shows the open percentage for your message, which is calculated as (Viewed/Sent\*100). It also shows the total number of emails opened. The views of CC/BCC recipients will be attributed to the main recipient.
  * AMP for Email Viewed: Shows the percentage of your total emails rendered as [AMP emails](https://docs.clevertap.com/docs/ampforemail). Displayed in case of AMP Email campaigns.
  * HTML Viewed: Shows the percentage of your total emails rendered as HTML. 
* Clicks: It shows the percentage of clicks from the total sent messages. It is calculated as (Clicks/Sent\*100). It also shows the number of clicks on the emails. The clicks of CC/BCC recipients will be attributed to the main recipient.
  * AMP for Email Clicks: Shows the percentage of clicks on emails rendered as AMP. Displayed in case of AMP Email campaigns.
  * HTML Clicks: Shows the percentage of clicks on emails rendered as HTML.
* CTR: The clickthrough rate of the campaign. It is measured by (Click/Viewed\*100).
* Converted users: The percentage of total users that performed the conversion event. For example, purchased an item. It also shows the number of users that converted after receiving the campaign. 
* Errors: Number of errors for the campaign. These errors can be technical errors, such as email provider errors, or non-technical errors, such as message frequency exceeded. 
* Control group: Number of users considered part of a control group for the campaign.
* Subscription Groups: Displays the number of subscriptions and unsubscriptions across various email subscription groups, such as Newsletters and Monthly Recaps.

> 📘 Note
>
> * You can view unsubscribe data across various email subscription groups starting from August 8, 2024.
> * Tracking delivery related errors like Unsubscribes, Bounces, and Report as Spam are not available for CC/BCC recipients.

## Message Trend

Click **Message Trend** to view the message trends by Sent, Viewed, or Clicked. You can view the daily, weekly, or monthly trends.

<Image title="View Message Trend Stats of Email Campaign" alt={2680} align="center" border={true} src="https://files.readme.io/27a73a8-Email_Stats_Message_Trend.png">
  Message Trend
</Image>

## Conversion Performance Overview

Click *Conversion Performance* to view conversion, revenue performance, and users' conversion funnel. 

<Image title="View Conversion Stas of Email Campaign" alt={2726} align="center" border={true} src="https://files.readme.io/32d1f59-Email_stats_conversion_performance.png">
  Conversion Performance
</Image>

For A/B Test, Split Delivery, and Message on User Property campaigns, you can view stats for each variant under User conversion funnel.

### Conversion Performance

The conversion performance section shows the conversion boost achieved from your campaign.  You can compare your campaign conversions with the control group conversions to see the impact of your campaign. 

<Image title="View Conversion Performance Stats of Email Campaign" alt={1310} align="center" border={true} src="https://files.readme.io/7bf34ea-Email_Stats_Conversion_Conversion_hero.png">
  Conversion Performance Stats
</Image>

### Revenue Performance

The Revenue Performance section shows the revenue boost achieved from your campaign.

## Users Conversion Funnel

Shows the conversion funnel, that is *Sent* > *Viewed* > *Clicked* > *Converted*. You can understand the drop-offs at each step of the campaign.

<Image title="View Users Conversion Funnel of Email Campaign" alt={2592} align="center" border={true} src="https://files.readme.io/9e1b1ae-Email_Stats_Conversion_Performance_with_Viewed.png">
  Users' Conversion Funnel
</Image>

### Hide Viewed

The *Viewed* numbers in a report can sometimes be unusually high because of virus scanners, email forwards, email groups, and so on. For more information, refer to [Unusually High Email Opens and Clicks](doc:troubleshooting-open-click-tracking). In this case, you can hide the viewed step by selecting the \_Hide Viewed \_button.

<Image title="Hide Viewed Funnel of Users Conversion" alt={2698} align="center" border={true} src="https://files.readme.io/b4954e5-Email_Stats_Conversion_Performance_No_Viewed.png">
  Hide Viewed Funnel
</Image>

> 📘 Key Points to Remember
>
> The Conversion Performance number for *All Variants* may be equal to or less than the combined Conversion Performance number for each individual variant. For example, if the Conversion Performance number for All Variants is 10500, with Variant A at 5575 and Variant B at 5053, the total for Variants A and B combined is 10628, exceeding the total for *All Variants*.
>
> This scenario can occur due to the following reasons:
>
> * For Live campaigns, different variants are delivered to various devices, identified by different GUIDs for the same user. Consequently, the Conversion Performance number for All Variants might not match the sum of the Conversion Performance numbers for each variant. For instance, a user may receive Variant A before uninstalling the app and then receive Variant B after reinstalling it until their identity is established.
> * For Recurring campaigns (user property campaigns), the user can qualify more than once when and receive different message copy each time. For example, the user upgrades to a new plan. In this case, the message copy received by the user before and after upgrading the *Membership type* can be different.
>
> In both the cases, the same user is counted twice, once for Variant A and once for Variant B. However, when calculating the Conversion Performance number for *All Variants*, each user is counted only once.

## Split of Clicks

You can track the distribution of clicks on each link that you include in your email campaign.  For example, you want to send an email promotion for an upcoming movie on your video streaming app. You can create an email campaign, and add links for reviews, promotions, movie merchandise, and so on, and then send the campaign.  We will record the clicks for each link in the email, and you can see them on the Campaign Stats page. 

> 📘 Click Heat Map
>
> Click Heat Map lets you see exactly where users are clicking within your emails through a visual, color-coded overlay. Use these insights to optimize content placement, refine CTAs, and improve campaign performance across teams. It is currently in Private Beta. To gain access, contact your Customer Success Manager. For more information, refer to [Link Clicks](doc:email-campaign-stats-heatmap#link-clicks).

<Image title="View Split of Clicks for Clicked Links" alt={2708} align="center" border={true} src="https://files.readme.io/8dc04dc-Email_Stats_Split_Clicks.png">
  Split of Clicks
</Image>

### User Details of Clicks

You can view the details of users who clicked on your email campaign using the *View details of users who clicked* link present on the *Split of Clicks* tab. You are navigated to the *Events* page. Click the *People* tab to view user details. 

<Image title="View Event Analysis for Notification Clicked" alt={1049} align="center" border={true} src="https://files.readme.io/d55d148-Email_stats_notification_clicked.png">
  Event Analysis for Notification Clicked
</Image>

### View Detailed Engagement Stats

You can also view the user details for notifications *sent*, *viewed*, and *clicked* from the *Analytics* page of the CleverTap dashboard. Consider an example of viewing the user details for the *Notification Viewed* event. To do so:

1. Navigate to *Analytics* > *Events* from the CleverTap dashboard. 
2. Select the desired date range.
3. Select the *Notification Viewed* event and the required filter. Similarly, you can select the *Notification Sent* or *Notification Clicked* event to view the required user details of who performed that event.
4. Click **View details**.

<Image title="View Event Analysis for Notification Viewed" alt={2658} align="center" border={true} src="https://files.readme.io/46340b1-Events.png">
  Event Analysis for Notification Viewed
</Image>

## Errors

You can view campaign errors from the Stats > Errors tab.

<Image title="View Email Campaign Errors" alt={2702} align="center" border={true} src="https://files.readme.io/32a2a5067863c2ae9644851ed73ffe2b47b27d1dd6520827221c5a18a6c007af-Email_-_Errors.png">
  Email Campaign Errors
</Image>

### Bounces

A bounced email is an email message that gets rejected by a mail server. There are two types of bounces:

#### Soft Bounce

A soft bounce indicates that mail bounced due to one of the following reasons even though the email address was valid, and the email message reached the recipient's mail server:

* The mailbox was full (the user has consumed all the quota)
* The server was down
* The message was too large for the recipient's inbox\
  CleverTap campaign reports include soft bounces and do not mark the users as unsubscribed.

#### Hard Bounce

A hard bounce indicated that the email was returned to the sender and was completely undeliverable. However, common reasons it got rejected include:

* The email address is invalid
* The email address does not exist
* The recipient's email server has blocked the emails

CleverTap campaign reports include hard bounces and mark the users as unsubscribed.

> 📘 Retries for Soft Bounce
>
> The number of retries for a soft bounce depends on the Email Service Provider.
