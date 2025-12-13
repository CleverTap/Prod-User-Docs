---
title: Recommended Delay for Inaction Campaigns_Campaign_redesign_WIP
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
# Overview

*Recommended Delay* is a feature that recommends the best time to send a message for an inaction campaign which is designed to engage users who do not do a certain action. 

# Use Cases

In this first scenario, nudge users who install your app (action) but do not purchase something within a two-hour (inaction) timeframe.  Here, the two-hour gap is selected based on manual analytics. Using the *Recommend Delay* feature, you can let CleverTap automatically decide the golden period within which the user should have purchased and then send out a message to re-engage users who do not purchase within that period.

In this second scenario, the average time it takes a user to add an item to their cart (action 1) and then checkout (action 2) is five minutes. If the user has not completed the checkout process within five minutes of adding the item to their cart (inaction), then the likelihood that a user will check out drops substantially. If you use the *Recommended Delay* feature, we will recommend the best time to wait before you send a notification to the user if they have not completed the checkout process.

# How It Works

CleverTap creates this recommendation by calculating the average time users take to convert from one action to another action. 

Beyond this average time, the likelihood that a user completes the second action drops substantially; however, if you send a message to the user at that point, you can increase the conversion rate for the second action.

# Create an Inaction Campaign

To create an inaction campaign, perform the following steps:

1. From the dashboard, navigate to *Campaigns*. 
2. Click **+ Campaign**.
3. Select a messaging channel.

<Image title="2x Create a campaign.png" alt={1571} className="border" border={true} src="https://files.readme.io/5de46d2-2x_Create_a_campaign.png" />

4. Navigate to *Setup* > *Delivery Type*.
5. Select *Live Behavior*. 
6. Click **Done**.

@DK/PM: IN STEP 3, SHOULDN'T WE SPECIFY THE CHANNEL? I COULD ONLY MAKE THE 'LIVE BEHAVIOR' COME UP FOR IN-APP, SMS, EMAIL, WHATSAPP, WEB PUSH, WEBHOOKS, SEGMENTS AND MPARTICLE.

@DK/PM: IS THE FOLLOWING SCREENSHOT CORRECT?

<Image title="Delivery type - live behavior.png" alt={669} className="border" border={true} src="https://files.readme.io/3f18514-Delivery_type_-_live_behavior.png" />

7. Under the *Set a goal* section, select *Conversion Tracking*.
8. Select event properties, revenue property, and funnel conversion time.
9. Click **Done**.

<Image title="2 select action.png" alt={1337} className="border" border={true} src="https://files.readme.io/d72257d-2_select_action.png" />

10. Navigate to *Who* > *Target Segment*.
11. Select any required user properties.
12. Click **or find best delay**.

@DK/PM: UPDATED STEPS 10-12. 

@DK/PM: IS THE DEFINITION OF 'BEST DELAY' THE SAME AS 'RECOMMENDED DELAY' AS DESCRIBED ABOVE IN THE USE CASE SECTION? SOMANI WAS ADVISING WE DEFINE 'BEST DELAY.' PLEASE CONFIRM. THANKS.

<Image title="Screenshot 2021-07-01 at 4.42.35 PM.png" alt={2254} className="border" border={true} src="https://files.readme.io/1b4de2a-Screenshot_2021-07-01_at_4.42.35_PM.png" />
