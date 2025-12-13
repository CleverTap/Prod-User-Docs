---
title: Email
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
# Overview

Email campaigns in CleverTap enable you to send messages to your users using either pre-built [email templates](doc:email-editor) or your own custom templates. 

You can send Email campaigns to all your users or specific user segments. These segments can be created based on past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent, and how many users converted as a result of the campaign.
[block:callout]
{
  "type": "success",
  "body": "Before you can start sending out email campaigns through CleverTap, you must first [integrate your email provider](doc:email-partners).",
  "title": "Integrate Your Email Provider"
}
[/block]
# Email Campaign Creation Steps

## Step 1: Create a New Campaign

To start creating a new Email campaign, first go to the Engage tab in the CleverTap dashboard, click on the Campaigns button, and then click on the  + Campaign button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ddb734f-ec1.png",
        "ec1.png",
        1234,
        577,
        "#d9dbdf"
      ],
      "border": true
    }
  ]
}
[/block]
Click Select under the Email channel.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f41e986-ec2.png",
        "ec2.png",
        1237,
        619,
        "#eeeff2"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 2: Define the When
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe7beeb-ec3.png",
        "ec3.png",
        1238,
        635,
        "#eff0f3"
      ],
      "border": true
    }
  ]
}
[/block]
Click Select under the campaign type you want, which will define when the campaign will run.

The following options are available: 
* **One time:** A one time engagement, typically used for announcements and promotions that targets 
* **Multiple dates:** Engage with users multiple times. Used to reinforce upcoming events and other important messages.
* **Recurring:** Automate campaigns to go out every day, week or month. Automate onboarding, retention and other campaigns.
* **Single action:** Engage users as they perform an action. Eg: Message users as soon as they sign up.
* **Inaction within time:** Engage users who do not do something. Eg: Message users who install the app, but don't sign up within 2 hours.
* **On a date/time:** Engage users before or after a date time. Eg: Message users 3 hours before their flight is scheduled.

Confirm the settings on the next page. Then click Continue.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52f3055-ec4.png",
        "ec4.png",
        1242,
        554,
        "#f0f1f5"
      ],
      "border": true
    }
  ]
}
[/block]
### Advanced Options

You have the following options available if you check the Advanced box:
* **Time zone:** This option allows you to deliver the email in the user's time zone.  
* **Campaign Do Not Disturb:** This option allows you to stop delivery of the campaign during a specified time. 
* **Campaign Cut-off:** This option allows you to stop delivery of the campaign after a specified time. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e027cb-Screen_Shot_2018-07-17_at_12.57.00_AM.png",
        "Screen Shot 2018-07-17 at 12.57.00 AM.png",
        1242,
        640,
        "#fcfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 3: Define the Who

The next step is to specify the target audience for your Email campaign. 

You can target your Email campaign to a previously saved user segment from the list of pre-saved segments or bookmarks. The second choice is to create a new segment on the fly by clicking on + Create ad-hoc segment button. The third choice is to target all your users as shown below. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/24eae55-ec5.png",
        "ec5.png",
        1240,
        532,
        "#eeeff3"
      ],
      "border": true
    }
  ]
}
[/block]

### Ad-Hoc Segment

If you choose to create an ad-hoc segment, the target segment can be created based on [user interests](doc:psychographic-segmentation), past user behavior, and user properties. You can also filter the segment based on users who did not do something using the Did not do option.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f8d516f-Screen_Shot_2018-07-17_at_1.03.40_AM.png",
        "Screen Shot 2018-07-17 at 1.03.40 AM.png",
        1296,
        700,
        "#fcfcfd"
      ],
      "border": true
    }
  ]
}
[/block]
### Estimated Reach

You will have the option to see the Estimated Reach, which will estimate how many users qualify for the campaign criteria and who are also reachable through email. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1e8ce94-Screen_Shot_2019-08-23_at_3.27.36_PM.png",
        "Screen Shot 2019-08-23 at 3.27.36 PM.png",
        1391,
        740,
        "#fbfbfa"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Why is the estimated reach of my campaign lower than expected?",
  "body": "Some of your users might have unsubscribed from your marketing communications, so they will not be included in the segment of users who will receive this campaign. Another possible reason is some of your user profiles in CleverTap might not include the user's email address."
}
[/block]

# Deliver to a Subset of the Target Audience

Sometimes you want to send a message to only a subset of the qualifying audience (Target Reach) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A great use case for this is a limited offer you wish to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute you can simply limit the number of users who will receive the message to exactly the number of coupons you wish to distribute.

Here’s how it works:

In the campaign creation flow, when you are determining who to send your message to, under the Campaign Reach section, select the option to limit delivery of the messages to the number you choose.

For triggered campaigns (based on Live User Segments), as users qualify, they will receive the message until the total quantity specified has been delivered, after which the campaign ends. For campaigns based on Past Behavior Segments we’ll randomly select the users that receive the message.

The campaign limits can also be configured as follows: 

  * Daily Limit - Limit the number of users for each day, for Best Time, User-Timezone, and Triggered campaigns.
   
  * Campaign Run Limit - Limit the number of users for each run of a campaign, for Fixed Time or Recurring campaigns.

  * Safety check - It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. For example, a customer has a budget for distributing 1000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget. 




## Step 4: Defining the What

You have three options for sending out an email in this section: 
* **Single message:** Send the same message to all users in your target audience. 
* **A/B test:** Send up to 3 message variants to a test group, to see which performs better. Please review [this section](https://docs.clevertap.com/docs/email#section-email-a-b-testing) for information on email A/B testing.
* **Message on user property:** Localize messages based on user properties like language. There is a section below that provides more information on message personalization.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb18b00-ec6.png",
        "ec6.png",
        1242,
        598,
        "#f0f1f4"
      ],
      "border": true
    }
  ]
}
[/block]
Next, you will define the email content in our [Email Editor](doc:email-editor) tool. You can select one of the pre-built email templates, or you can create your own custom email template by clicking the + Create a template with custom HTML button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cb7a048-ec7.png",
        "ec7.png",
        1247,
        718,
        "#b8b9be"
      ],
      "border": true
    }
  ]
}
[/block]
After you select an email template, you can add content to it, and customize the style and layout with buttons and images.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/df8a762-ec8.png",
        "ec8.png",
        1236,
        719,
        "#acaeb2"
      ],
      "border": true
    }
  ]
}
[/block]
### Personalization
The Email message can be personalized for every user based on specific user property or event property values. See [the User Profiles page](doc:user-profiles) to learn more about user profile properties and events.

To use the personalization menu, type “@” in the text fields while typing out the Email message.
Emojis can be included in your Email messages, just like regular text. You can copy-paste emojis from Emoji keyboards online.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/abb6e04-image9.png",
        "image9.png",
        288,
        220,
        "#eef0f6"
      ],
      "border": true
    }
  ]
}
[/block]
 ## Step 5: Test Email

You have the option to send a test email message to any email address using the Test Email option in the Email Editor tool.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/06232a9-ec11.png",
        "ec11.png",
        802,
        506,
        "#aeafb2"
      ]
    }
  ]
}
[/block]
## Step 6: Schedule Campaign

On this page, you have to select the [email provider](doc:email-partners) CleverTap will use to send the campaign to your users.

You have the option to add labels, conversion tracking, and a control group to this campaign.
* **Add labels:** Label your campaign with descriptive themes. Use these labels to then group campaigns and analyze performance.
* **Setup conversion tracking:** Add an event that represents a conversion goal for your campaign.
* **Enable a control group:** Define a percentage of your audience who will not receive this campaign so you can better understand performance.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0bad678-Screen_Shot_2018-07-17_at_1.21.29_AM.png",
        "Screen Shot 2018-07-17 at 1.21.29 AM.png",
        1299,
        679,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]
Finally, you will see a summary of your email campaign. Once you are ready to send the campaign, click the Schedule notification button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de0ded3-ec10.png",
        "ec10.png",
        1310,
        734,
        "#fcfcfd"
      ],
      "border": true
    }
  ]
}
[/block]
# Viewing Email Campaign Stats

Once the campaign has gone out, you can view its stats by going into Email under Campaigns on the CleverTap dashboard and clicking on the campaign of interest to see its total sends, opens, conversions, and revenue from conversions (if applicable).

# Tracking Links in Email Campaigns

When including links in your email, please tag them each with distinct UTM parameters (source = wizrocket (say), medium = email (say), campaign = campaign1_link1 (say), and so on). 

Then, you can go into "Events" or "Find People", select the "UTM Visited" event, and filter by UTM campaign = campaign1_link1, or campaign1_link2, and so on.

You will then have "UTM Visited" events raised for each link click - one with no UTM parameters (that will show up in campaign stats for overall clicks), and one with UTM parameters that you can analyze in "Events" or "Find People" as described above.

# Email A/B Testing

CleverTap's Email A/B Testing feature lets you compare up to three different versions of an email to find the best performing one. You pick the size of the test audience for the A/B test, we will determine the winner based on the number of clicks, and then deliver the winning message to the rest of your target audience.

## Setup Steps

Creating an email campaign using the A/B testing feature follows a similar pattern to creating a normal email campaign. After choosing the segment to target and frequency of communication, you will be given an option to run the campaign as an A/B test. 

Click Select in the A/B test box to setup the email A/B test.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8cbbeec-ab1.png",
        "ab1.png",
        1323,
        469,
        "#f1f1f4"
      ],
      "border": true
    }
  ]
}
[/block]
On the next page, build two or three different variations of the email you want to send. You can modify the email template, content, subject line, and sender name. 

Click Continue once you are finished building the email variations.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5529989-ab2.png",
        "ab2.png",
        1342,
        488,
        "#bebdc2"
      ],
      "border": true
    }
  ]
}
[/block]
Pick the sample size and wait time until the winning message is decided. Then click Continue.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d0183c6-ab3.png",
        "ab3.png",
        1320,
        679,
        "#f0f1f5"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "body": "We will determine the winner based on the number of clicks, and then deliver the winning message to the rest of your target audience. \n\nIn the screenshot above, we are sending the A/B test to a sample size of 10% who will receive either Variant A or B. In other words, 5% of the target segment will receive email Variant A and another 5% will receive email Variant B. We will wait for 45 minutes to evaluate the winner based on the number of clicks. The winner variant is then sent automatically to the remaining 90% of the target segment.\n\nIn the case of a tie between Variant A and B, we will send the remaining 90% email Variant A.",
  "title": "Winner Evaluation"
}
[/block]
You are finished with setting up the A/B test portion of building your email campaign. Now, you will complete the rest of steps similar to a normal campaign. Clicking Schedule Notification will finalize your email campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e949ea8-ab4.png",
        "ab4.png",
        1332,
        563,
        "#eff0f4"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f9096d9-ab5.png",
        "ab5.png",
        1325,
        777,
        "#f0f1f5"
      ],
      "border": true
    }
  ]
}
[/block]