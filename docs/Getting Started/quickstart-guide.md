---
title: Quickstart Guide
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
Using this guide, you will email a discount code to users who have added an item to their shopping cart but didn't complete a purchase. 

You will accomplish this in three easy steps through the CleverTap dashboard:

* Run a report to confirm if cart abandonment is a problem for your company.
* Create a segment to identify users who abandoned their cart.
* Build a campaign to email a discount code to users in that segment.

# CleverTap Demo Account

For the purposes of this guide, we will use a demo account that's part of the CleverTap dashboard. The demo account is already populated with user data, so you can experiment with CleverTap before integrating our SDK into your app. If you don't already have a CleverTap account, sign up for [one here](https://clevertap.com/sign-up/). 

To access your CleverTap demo account:

* Log into your [CleverTap account](https://dashboard.clevertap.com/).
* Click on your account name on the top right of the CleverTap dashboard, which will be highlighted in blue. 
* Click **Explore Demo Account** button. 

<Image title="demo1.png" alt={280} className="border" border={true} src="https://files.readme.io/874322f-demo1.png" />

Once logged into the demo account, analyze and solve our cart abandonment issue.

# Run a Report

As a data-driven marketer, before running a campaign to our users, we should first validate the issue. Our hypothesis is more than 10% of users abandoned their cart. Using CleverTap we can run a report to confirm if this hypothesis is true. 

1. From the CleverTap dashboard, select Analytics, then click on **Funnels**. 

The Funnel report in CleverTap enables you to see the drop off between different stages that you define. In this case, we want to understand the drop off between the number of users who add an item to their cart to the number of users who complete a purchase.

2. Select Funnel steps:

* Under Step 1, select *Product Viewed*. 
* Under Step 2, select *Added to Cart*. 
* Under Step 3, select *Charged*. 

Product Viewed, Added to Cart, and Charged are events tracked by CleverTap. After you [integrate our SDK](https://clevertap-developer-docs.readme.io/v1.0/docs/getting-started) in your app, you can immediately start tracking and analyzing these events in the CleverTap dashboard.

<Image title="f5f8cba-QCS Funnel_1.png" alt={1237} className="border" border={true} src="https://files.readme.io/c47f5de-f5f8cba-QCS_Funnel_1.png" />

Unfortunately, the cart abandonment problem is worse than thought. Only 47% of users who add an item to their cart complete a purchase, which means the other 53% abandon their cart.

Thankfully, you are using CleverTap and can start solving the problem in minutes!

<Image title="funnel2.png" alt={1141} className="border" border={true} src="https://files.readme.io/c43bceb-funnel2.png" />

# Create a Segment

A CleverTap segment is a group of users whose actions and profile properties match a set of criteria you have defined. Segments are created to identify users who added an item to their cart but then did not complete a purchase within five minutes.

1. From the CleverTap dashboard, click **Segment, and then click the** Segments\*\* option.
2. Click **+ Segment** to create a new Segment.

<Image title="91fdf39-segment1.png" alt={1239} className="border" border={true} src="https://files.readme.io/c7cf411-91fdf39-segment1.png" />

3. On the next page, click **+ Create segment** within the *Inaction within time* box.

<Image title="segment2.png" alt={1250} className="border" border={true} src="https://files.readme.io/e12d3ed-segment2.png" />

4. Under the *As soon as user does* section, select *Added to Cart*, which tracks when an item was added to a user's shopping cart in the app. 
5. In the *And within X minutes does not do section*, select five minutes for the time and Charged for the event. 

These settings will create a continuously updated segment that identifies users who added an item but then did not complete a purchase within five minutes.

<Image title="fa3110b-segment3.png" alt={1244} className="border" border={true} src="https://files.readme.io/aa8998c-fa3110b-segment3.png" />

6. Save the segment as *Added To Cart but did not Charge within 5 mins*, and then click **Create**.

<Image title="segment4.png" alt={901} className="border" border={true} src="https://files.readme.io/a76dd0b-segment4.png" />

# Build a Campaign

CleverTap offers nine different messaging channels enabling you to reach your users on the optimal channel, such as email, in-app notification, or push notification.

1. Click the **Create Campaign** icon next to the *Added To Cart but did not Charge within 5 mins* segment. 
2. Select *Email* in the dropdown menu. 

<Image title="5108645-campaign1.png" alt={1271} className="border" border={true} src="https://files.readme.io/5b3b184-5108645-campaign1.png" />

3. Name the campaign *Abandoned Cart Email*, and then click **Continue to When**.

![1266](https://files.readme.io/79d3d0c-dd8ee97-campaign2.png "dd8ee97-campaign2.png")

4. Click *Now* for the *Campaign start date and time*. 
5. Select an end date for the *Message end date and time* section. This keeps the campaign running until the time you specify. Alternatively, you can keep the campaign running continuously by selecting *Never end*.

<Image title="3f87d72-campaign3.png" alt={1260} className="border" border={true} src="https://files.readme.io/f65ca32-3f87d72-campaign3.png" />

On the next page, keep the default settings, which is pre-populated based on the segment you selected earlier. 

6. Add a gap of 14 days, so a user doesn't receive a discount code again until after 14 days have passed.

<Image title="5576477-campaign4.png" alt={1254} className="border" border={true} src="https://files.readme.io/b78331c-5576477-campaign4.png" />

On the next page, build the message users in this segment receives. 

7. Fill out the email subject line and body. Using the @ symbol, you can make the email personalized for each user based on information from their profile properties. 
8. Select *Continue to Overview*.

<Image title="0972c2c-campaign5.png" alt={1261} className="border" border={true} src="https://files.readme.io/5be27ab-0972c2c-campaign5.png" />

9. Click **Schedule Notification and your campaign will be live**. 

Since this a demo account, no emails will be sent. If you follow these same steps for your regular CleverTap account, each user in this segment will receive an email.

<Image title="6307cbb-campaign6.png" alt={1286} className="border" border={true} src="https://files.readme.io/6ca4ed5-6307cbb-campaign6.png" />

# Next Steps

Congrats on building your first campaign in CleverTap! 

First, you ran a report to analyze if there was an issue with cart abandonment in your app. After confirming this issue, you created a segment to identify users who abandoned their cart. Finally, you set up a campaign to engage your users in that segment and encouraged them to complete the purchase.

To start solving problems like these for your company, you need to integrate our SDK into your app by following one of [these guides](https://developer.clevertap.com/docs). If you want to keep exploring more CleverTap features before integrating our SDK, check out our [core concepts pages](doc:user-profiles).

To quickly integrate your app and get started, see [Quick Project Setup](https://docs.clevertap.com/docs/quick-project-setup).
