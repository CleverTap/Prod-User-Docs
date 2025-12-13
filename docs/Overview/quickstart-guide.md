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
In this quickstart guide, you will email a discount code to users who have added an item to their shopping cart but then didn't complete a purchase. 

You will accomplish this in three easy steps through the CleverTap dashboard:

* Run a report to confirm if cart abandonment is a problem for your company.
* Create a segment to identify users who abandoned their cart.
* Build a campaign to email a discount code to users in that segment.

# CleverTap Demo Account

For the purposes of this quickstart guide, we will use a demo account that's part of the CleverTap dashboard. The demo account is already populated with user data, so you can experiment with CleverTap before integrating our SDK into your app. If you don't already have a CleverTap account, sign up for [one here](https://clevertap.com/sign-up/). 

To get to your CleverTap demo account:

* Log into your [CleverTap account](https://dashboard.clevertap.com/).
* Click on your account name on the top right of the CleverTap dashboard. It will be highlighted in blue. 
* Click on the Explore Demo Account button. 

<Image title="demo1.png" alt={280} className="border" border={true} src="https://files.readme.io/874322f-demo1.png" />

Now that we are logged into the demo account, let's analyze and solve our cart abandonment issue.

# Run a Report

As a data-driven marketer, before running a campaign to our users, we should first validate the issue. Our hypothesis is more than 10% of users abandoned their cart. Using CleverTap we can run a report to confirm if this hypothesis is true. 

Click on the Analyze tab in the CleverTap dashboard. Then click on Funnels. 

<Image title="funnels1.png" alt={153} className="border" border={true} src="https://files.readme.io/0295e3a-funnels1.png" />

The Funnel report in CleverTap enables you to see the drop off between different stages that you define. In this case, we want to understand the drop off between the number of users who add an item to their cart to the number of users who complete a purchase.

Under Step 1, select Product Viewed. Under Step 2, select Added to Cart. Under Step 3, select Charged. 

Product Viewed, Added to Cart, and Charged are events tracked by CleverTap. After you [integrate our SDK](https://clevertap-developer-docs.readme.io/v1.0/docs/getting-started) in your app, you can immediately start tracking and analyzing these events in the CleverTap dashboard.

<Image title="funnnel1.png" alt={1393} className="border" border={true} src="https://files.readme.io/f5f8cba-funnnel1.png" />

Unfortunately, the cart abandonment problem is worse than we thought. Only 47% of users who add an item to their cart complete a purchase, which means the other 53% abandon their cart.

Thankfully, you are using CleverTap and can start solving the problem in minutes!

<Image title="funnel2.png" alt={1141} className="border" border={true} src="https://files.readme.io/c43bceb-funnel2.png" />

# Create a Segment

A CleverTap segment is a group of users whose actions and profile properties match a set of criteria you have defined.

We will create a segment to identify users who added an item to their cart but then did not complete a purchase within 5 minutes.

In the CleverTap dashboard, click on the Segment tab, and then click on the Segments button. Now, create a new Segment by clicking + Segment.

<Image title="segment1.png" alt={1398} className="border" border={true} src="https://files.readme.io/91fdf39-segment1.png" />

On the next page, click on the + Create segment button within the Inaction within time box.

<Image title="segment2.png" alt={1250} className="border" border={true} src="https://files.readme.io/e12d3ed-segment2.png" />

Under the As soon as user does section, select Added to Cart, which tracks when an item was added to a user's shopping cart in the app. Under the within x minutes does not do section, select 5 minutes for the time and Charged for the event. 

These settings will create a continuously updated segment that identifies users who added an item but then did not complete a purchase within 5 minutes.

<Image title="segment3.png" alt={1404} className="border" border={true} src="https://files.readme.io/fa3110b-segment3.png" />

Save the segment as "Added To Cart but did not Charge within 5 mins". Then click Create.

<Image title="segment4.png" alt={901} className="border" border={true} src="https://files.readme.io/a76dd0b-segment4.png" />

# Build a Campaign

CleverTap offers nine different messaging channels enabling you to reach your users on the optimal channel, such as email, in-app notification, or push notification.

Click the Create Campaign icon next to the "Added To Cart but did not Charge within 5 mins" segment. Click on the Email button within the dropdown. 

<Image title="campaign1.png" alt={1404} className="border" border={true} src="https://files.readme.io/5108645-campaign1.png" />

Name the campaign Abandoned Cart Email. Then click Continue to When.

![1409](https://files.readme.io/dd8ee97-campaign2.png "campaign2.png")

Click Now for the Campaign start date and time. Select an end date for the Message end date and time section. This will keep the campaign running until the time you specify. Alternatively, you can keep the campaign running continuously by selecting Never end.

<Image title="campaign3.png" alt={1397} className="border" border={true} src="https://files.readme.io/3f87d72-campaign3.png" />

On the next page, keep the default settings, which will be pre-populated based on the segment you selected earlier. Add a gap of 14 days, so a user doesn't receive a discount code again until after 14 days have passed.

<Image title="campaign4.png" alt={1389} className="border" border={true} src="https://files.readme.io/5576477-campaign4.png" />

On this page, we will build the message users in this segment will receive. 

Fill out the email subject line and body. Using the @ symbol, you can make the email personalized for each user based on information from their profile properties. 

Then select Continue to Overview.

<Image title="campaign5.png" alt={1402} className="border" border={true} src="https://files.readme.io/0972c2c-campaign5.png" />

Click Schedule Notification and your campaign will be live. Since this a demo account, no emails will be sent. If you follow these same steps for your regular CleverTap account, users in this segment will receive an email.

<Image title="campaign6.png" alt={1396} className="border" border={true} src="https://files.readme.io/6307cbb-campaign6.png" />

# Next Steps

Congrats on building your first campaign in CleverTap! 

First, you ran a report to analyze if there was an issue with cart abandonment in your app. After confirming this issue, you created a segment to identify users who abandoned their cart. Finally, you set up a campaign to engage your users in that segment, and encouraged them to complete the purchase.

To start solving problems like these for your company, you will need to integrate our SDK into your app by following one of [these guides](https://developer.clevertap.com/docs). If you want to keep exploring more CleverTap features before integrating our SDK, check out our [core concept pages](doc:user-profiles).
