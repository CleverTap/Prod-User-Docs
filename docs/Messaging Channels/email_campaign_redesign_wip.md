---
title: Email_Campaign_redesign_WIP
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

Email campaigns in CleverTap enable you to send messages to your users using either pre-built [email templates](doc:email-editor) or your own custom templates. 

You can send email campaigns to all your users or specific user segments. These segments can be created based on past or live user behavior, user properties, or a combination of user behavior and properties. Once a campaign has been sent, you can view detailed reports on how many messages were sent, and how many users converted as a result of the campaign.
[block:callout]
{
  "type": "info",
  "body": "Before you can start sending out email campaigns through CleverTap, you must first [integrate your email provider](doc:email-partners).",
  "title": "Integrate Your Email Provider"
}
[/block]
# Email Campaign Creation Steps

## Create a New Campaign

To start creating a new Email campaign, navigate to the *Campaigns* tab in the CleverTap dashboard and then click on the  **+ Campaign**  button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/458cdc9-Campaign_Listing_-_2.png",
        "Campaign Listing - 2.png",
        1436,
        783,
        "#f6f7f8"
      ],
      "border": true
    }
  ]
}
[/block]

Select **Email**  from the *Messaging Channels* list.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21efcc8-Campaign_Email_Select_Channel.png",
        "Campaign_Email_Select_Channel.png",
        1437,
        756,
        "#f2f3f6"
      ],
      "border": true
    }
  ]
}
[/block]
## Set up the campaign

Select the **Delivery Type**. 
Select the **Email Service Provider.**
Set a goal with **Conversion Tracking**. Add an event that represents a conversion goal for your campaign.

## Step 3: Define the Who

The next step is to specify the target audience for your Email campaign. 

You can target your *Email* campaign to a previously saved user segment from the list of pre-saved segments or bookmarks. The second choice is to create a new segment by clicking on the **+ Create ad-hoc segment** button. <<@vishal we do not have this anymore ?>>The third choice is to target all your users as shown below. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b79062-Campaign_Saved_Segment_PBS_Who.png",
        "Campaign_Saved_Segment_PBS_Who.png",
        1147,
        290,
        "#f4f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
Set the control group. 
Define a percentage of your audience who will not receive this campaign so you can better understand performance. For more information on control groups, see [Control Groups](doc:control-groups).



### Ad-Hoc Segment <<@vishal, we do not have this anymore ?>>
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
        "https://files.readme.io/38129ac-Campaign_Email_Estimated_reach.png",
        "Campaign_Email_Estimated_reach.png",
        1391,
        865,
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

#### Deliver to a Subset of the Target Audience

Sometimes you want to send a message to only a subset of the qualifying audience (Target Reach) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A great use case for this is a limited offer you want to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute you can simply limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

Here’s how it works:

In the campaign creation flow, when you are determining who to send your message to, under the Campaign Reach section, select the option to limit delivery of the messages to the number you choose.

For triggered campaigns (based on Live User Segments), as users qualify, they will receive the message until the total quantity specified has been delivered, after which the campaign ends. For campaigns based on *Past Behavior Segments*, we will randomly select the users who receive the message.

The campaign limits can also be configured as follows: 

  * Daily Limit - Limit the number of users for each day, for Best Time, User-Timezone, and Triggered campaigns.
   
  * Campaign Run Limit - Limit the number of users for each run of a campaign, for Fixed Time or Recurring campaigns.

  * Safety check - It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 
[block:callout]
{
  "type": "success",
  "body": "A customer has a budget for distributing 1000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.",
  "title": "Safety Check Example"
}
[/block]
## Define the What

You have three options for sending out an email in this section: 
* **Single message:** Send the same message to all users in your target audience. 
* **A/B test:** Send up to 3 message variants to a test group, to see which performs better. For more information on A/B test, see [Email A/B Testing](https://docs.clevertap.com/docs/email#section-email-a-b-testing).
* **Split Delivery:** Split your message delivery by percent of users.
* **Message on user property:** Localize messages based on user properties such as language. There is a section below that provides more information on [message personalization](https://docs.clevertap.com/docs/email#section-personalization).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d69063-Campaign_Email_What_Message.png",
        "Campaign_Email_What_Message.png",
        1438,
        747,
        "#e5e6ea"
      ],
      "border": true
    }
  ]
}
[/block]
Next, you will define the email content in our [Email Editor](doc:email-editor) tool. You can select one of the pre-built email templates, or you can create your own custom email template by clicking the + New email with rich media button.

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
The email message can be personalized for every user based on specific user property or event property values. See [the User Profiles page](doc:user-profiles) to learn more about user profile properties and events.

To use the personalization menu, type “@” in the text fields when creating the email message.
Emojis can be included in your email messages, just like regular text. You can copy-paste emojis from Emoji keyboards online.
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

###Liquid Tags

Liquid tags offer great flexibility in composing your message. You can have fixed or variable values and change the look and feel of your message by using Liquid Tags in the *New email with rich media* template.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f84b59-Campaign_Email_Liquid_Tags_example._.png",
        "Campaign_Email_Liquid_Tags_example. .png",
        1357,
        608,
        "#f9f9fa"
      ],
      "caption": ""
    }
  ]
}
[/block]
Each email is personalized to the receiver. 
[block:code]
{
  "codes": [
    {
      "code": "Hello John!\n\nHere is a special coupon for you: Gold4All\n",
      "language": "html",
      "name": "Output - Liquid"
    }
  ]
}
[/block]
For more information on using tags, see [Liquid Tags](doc:liquid-tags).

### Email with Drag and Drop

The *New email with drag and drop* template allows users to convert their drag and drop editor template into HTML and provides a one-way conversion to view and edit source code. 

From *Templates*, select **New email with drag and drop**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8f211e1-2020-06-17_12-41-37_Convert_to_HTML_Select_option.png",
        "2020-06-17_12-41-37_Convert to HTML_Select option.png",
        1816,
        481,
        "#f4f4f6"
      ]
    }
  ]
}
[/block]
After your template loads, select **More**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2817e52-2020-06-17_12-41-37_Convert_to_HTML_Click_more.png",
        "2020-06-17_12-41-37_Convert to HTML_Click more.png",
        1172,
        565,
        "#9c9ea0"
      ]
    }
  ]
}
[/block]
Select **Convert to HTML ** from the dropdown menu.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3695d3-2020-06-17_12-41-37_Convert_to_HTML_option.png",
        "2020-06-17_12-41-37_Convert to HTML option.png",
        351,
        447,
        "#f8f7f8"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This is a one-way conversion. Once you convert the template to HTML, you can't undo the action, so it's recommended you click **Convert Without Saving** until you are satisfied with your changes.",
  "title": "One-Way Conversion"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e17a37f-2020-06-17_13-13-46_Save_template.png",
        "2020-06-17_13-13-46_Save template.png",
        454,
        300,
        "#f3edee"
      ]
    }
  ]
}
[/block]
Type your edits into the HTML editor.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5cd74e4-2020-06-17_13-15-35_HTML_mode.png",
        "2020-06-17_13-15-35_HTML mode.png",
        1160,
        539,
        "#fcfdfd"
      ]
    }
  ]
}
[/block]
Select **Previews** and save your template when you are satisfied with the changes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e421ee0-2020-06-17_13-18-06_Preview.png",
        "2020-06-17_13-18-06_Preview.png",
        1156,
        557,
        "#9a9c9e"
      ]
    }
  ]
}
[/block]

###Preheaders
A Preheader text is a preview of your email that your users can scan before they open it. Preheaders can call attention to the key message in your email and entice the user to read the rest of the email. If there is no Preheader text, the email inbox simply displays the beginning of your email text. It's a great opportunity to influence open rates positively.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b49cf1-Campaigns_Email_Preheader_Output.png",
        "Campaigns_Email_Preheader_Output.png",
        1439,
        464,
        "#ebeced"
      ],
      "border": true
    }
  ]
}
[/block]
After you have created the what section, click Continue. To display Preheader in your message, enter the Preheader text in the Preheader box. You can preview the text at this stage. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a93bedf-Campaigns_Email_Preheader.png",
        "Campaigns_Email_Preheader.png",
        2714,
        1384,
        "#f7f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
It is recommended to limit the Preheader text to 100 characters. The final message will show the Preheader text along with the subject and the sender.

###Inbox Previews with Code Analysis
Inbox Previews with Code Analysis offers you an analysis of your custom HTML code. It also offers you previews across devices and inboxes before you send out a campaign. For more information, see how to perform [Code Analysis](https://docs.clevertap.com/docs/email-editor#section-inbox-previews-with-code-analysis) in email editor.

###Email Add-On

The Email Add-on offers you preview across devices and inboxes before you send out the campaign. It also allows you to test your email for deliverability by creating a spam report. The Email Add-On offers you 100 email previews and spam reports a month. 

Before we begin, check that you have enabled the Inbox Previews. For enabling the Inbox Previews, see [Enable Email Previews](doc:enabling-previews).

####**Step 1: Enable Inbox Previews (Optional)**
You can now preview your email across devices and inboxes before you send out the campaign. This will help you to understand how your email will be displayed on devices such as desktop or mobile, and email clients such as Gmail, Yahoo, and so on. 



[block:callout]
{
  "type": "warning",
  "body": "Check that you have enabled email previews. For more information, see [enabling previews](https://docs.clevertap.com/docs/enabling-previews).\n\nEmail previews are available only if you have opted for the email add-on from CleverTap.",
  "title": "Enable Email Previews"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ac2830-campaign_email_template_preview.png",
        "campaign_email_template_preview.png",
        1374,
        696,
        "#a9acad"
      ],
      "border": true
    }
  ]
}
[/block]
When you click *Previews*, a pop-up window with *Devices* and *Inbox* tabs will display. 

Under “Devices” you can view desktop and mobile previews. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a99f35a-campaign_email_template_preview_Devices.gif",
        "campaign_email_template_preview_Devices.gif",
        1384,
        664,
        "#b5b7bb"
      ],
      "border": true
    }
  ]
}
[/block]
Under “Inboxes”, you can check previews across various email clients.  

You can generate previews for various email clients by clicking the 'Run Tests' button in the preview window.
Each of these preview thumbnails can be clicked and viewed on a full scale.
You can also reload the preview images.

You will find the email clients listed under CleverTap > Settings > Email > Setup Previews.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ef3be30-Campaign_Email_Create_Message_Inboxes_Preview.png",
        "Campaign_Email_Create_Message_Inboxes_Preview.png",
        1440,
        731,
        "#cfced1"
      ],
      "border": true
    }
  ]
}
[/block]
At this stage, you can continue the campaign creation flow or save the message draft. If you save a draft, the previews will also be saved and regenerated when you open the draft again.
 
#### **Step 2: Check the Spam Report (Optional)**
You will likely want to ensure the deliverability of emails to your users. The spam report feature helps to determine the probability of the email message landing in a spam folder. You can check the spam report of your message at this stage after entering the sender details. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ac5a5f4-Campaign_Email_Create_Edit_Sender_Details.png",
        "Campaign_Email_Create_Edit_Sender_Details.png",
        1388,
        716,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]

After you enter sender details, click the 'Spam Report' button to check the spam report of your email, or continue building the campaign.  You will see a detailed report on your email message and a warning if the message does not pass any spam filter.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/654138e-Campaign_Email_EOA_Spam_Score.gif",
        "Campaign_Email_EOA_Spam_Score.gif",
        1440,
        690,
        "#eff1f6"
      ],
      "border": true
    }
  ]
}
[/block]

## Define the When
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19a1346-Campaign_Email_Campaign_Type.png",
        "Campaign_Email_Campaign_Type.png",
        1440,
        759,
        "#f0f1f4"
      ],
      "border": true
    }
  ]
}
[/block]

Select the delivery preferences, which will define when the campaign will run.

The following options are available: 
* **One time:** A one-time engagement, typically used for announcements and promotions that targets 
* **Multiple dates:** Engage with users multiple times. Used to reinforce upcoming events and other important messages.
* **Recurring:** Automate campaigns to go out every day, week or month. Automate onboarding, retention and other campaigns.
* **Single action:** Engage users as they perform an action. Eg: Message users as soon as they sign up.
* **Inaction within time:** Engage users who do not do something. Eg: Message users who install the app, but don't sign up within 2 hours.
* **On a date/time:** Engage users before or after a date-time. Eg: Message users 3 hours before their flight is scheduled.

Confirm the settings on the next page. Then click Continue.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4193084-Campaign_Email_Message_When.png",
        "Campaign_Email_Message_When.png",
        1440,
        759,
        "#f0f1f5"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If you specify a recurring day for a campaign, say the 7th of each month, then the campaign will start for the specified day and ignore the creation date. This is a precaution to avoid sending a campaign unintentionally on a prior date."
}
[/block]
### Delivery preferences
You have the following options available if you check the Advanced box:
* **Time zone:** This option allows you to deliver the email in the user's time zone.  
* **Campaign Do Not Disturb:** This option allows you to stop the delivery of the campaign during a specified time. 
* **Campaign Cut-off:** This option allows you to stop the delivery of the campaign after a specified time. 
* ** Global Throttle Limits:** These are limits you can apply to determine how many emails each app user receives per day. If you would like to override these settings for an important campaign, you can click on the “Don’t apply global campaign limits to this campaign” checkbox.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/717ef62-Campaign_Email_Message_Advanced.png",
        "Campaign_Email_Message_Advanced.png",
        1374,
        667,
        "#fdfdfd"
      ],
      "border": true
    }
  ]
}
[/block]

## Publish Campaign

You have the option to send a test email message to any email address using the Test Email option in the Email Editor tool. Click the More Options icon and click send a test email button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/94979e6-Campaigns_Email_Preview_Test.gif",
        "Campaigns_Email_Preview_Test.gif",
        1028,
        654,
        "#f5f6f7"
      ]
    }
  ]
}
[/block]
You have the option to add labels, conversion tracking, and a control group to this campaign.
* **Add labels:** Label your campaign with descriptive themes. Use these labels to then group campaigns and analyze performance.


Finally, you will see a summary of your email campaign. When you are ready to send the campaign, click the *Publish Campaign* button.
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

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "CleverTap can send transactional emails for you via Sendgrid. Please contact our support at support@clevertap to configure your account for Sendgrid dashboard."
}
[/block]
# Viewing Email Campaign Stats

Once the campaign has gone out, you can view its stats by going into Email under Campaigns on the CleverTap dashboard and clicking on the campaign of interest to see its total sends, opens, conversions, and revenue from conversions (if applicable).


# Tracking Links in Email Campaigns

You can track the distribution of clicks on each link that you include in your email campaign.  For example, you want to send an email promotion for an upcoming movie on your video streaming app. You can create an email campaign and add links for reviews, promotions, movie merchandise, and so on, and then send the campaign.  We will record the clicks for each link in the email and you can see them on the Campaign Stats page. Open the email campaign from the campaign list page. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d180aab-Campaign_Email_Split_Cicks.png",
        "Campaign_Email_Split_Cicks.png",
        1198,
        1351,
        "#e6ecf3"
      ],
      "border": true
    }
  ]
}
[/block]
To view the stats for each link, click 'View split of clicks'.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b747b3d-Campaign_Email_Split_Click_Display.png",
        "Campaign_Email_Split_Click_Display.png",
        1200,
        1640,
        "#eff1f3"
      ],
      "border": true
    }
  ]
}
[/block]

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
        "https://files.readme.io/2d0c585-Campaign_Email_Message_AB_Test.png",
        "Campaign_Email_Message_AB_Test.png",
        1437,
        736,
        "#e6e6ea"
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
Select the sample size and wait time until the winning message is decided. Then click Continue.
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
  "type": "info",
  "body": "We will determine the winner based on the number of clicks, and then deliver the winning message to the rest of your target audience. \n\nIn the screenshot above, we are sending the A/B test to a sample size of 10% who will receive either Variant A or B. In other words, 5% of the target segment will receive email Variant A and another 5% will receive email Variant B. We will wait for 45 minutes to evaluate the winner based on the number of clicks. The winner variant is then sent automatically to the remaining 90% of the target segment.\n\nIn the case of a tie between Variant A and B, we will send the remaining 90% email Variant A.",
  "title": "Winner Evaluation"
}
[/block]
You are finished with setting up the A/B test portion of building your email campaign. Now, you can complete the rest of the steps similar to a normal campaign. Clicking Schedule Notification will finalize your email campaign. 
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