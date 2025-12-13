---
title: Email with PreHeaders
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

> 👍 Integrate Your Email Provider
>
> Before you can start sending out email campaigns through CleverTap, you must first [integrate your email provider](doc:email-partners).

# Email Campaign Creation Steps

## Step 1: Create a New Campaign

To start creating a new Email campaign, first go to the Engage tab in the CleverTap dashboard, click on the Campaigns button, and then click on the  + Campaign button.

<Image title="Campaign_main_list.png" alt={1436} className="border" border={true} src="https://files.readme.io/4829543-Campaign_main_list.png" />

Select the Email channel.

<Image title="Campaign_Email_Select_Channel.png" alt={1437} className="border" border={true} src="https://files.readme.io/21efcc8-Campaign_Email_Select_Channel.png" />

## Step 2: Define the When

<Image title="Campaign_Email_Campaign_Type.png" alt={1440} className="border" border={true} src="https://files.readme.io/19a1346-Campaign_Email_Campaign_Type.png" />

Select the campaign type that you want, which will define when the campaign will run.

The following options are available: 

* **One time:** A one-time engagement, typically used for announcements and promotions that targets 
* **Multiple dates:** Engage with users multiple times. Used to reinforce upcoming events and other important messages.
* **Recurring:** Automate campaigns to go out every day, week or month. Automate onboarding, retention and other campaigns.
* **Single action:** Engage users as they perform an action. Eg: Message users as soon as they sign up.
* **Inaction within time:** Engage users who do not do something. Eg: Message users who install the app, but don't sign up within 2 hours.
* **On a date/time:** Engage users before or after a date-time. Eg: Message users 3 hours before their flight is scheduled.

Confirm the settings on the next page. Then click Continue.

<Image title="Campaign_Email_Message_When.png" alt={1440} className="border" border={true} src="https://files.readme.io/4193084-Campaign_Email_Message_When.png" />

### Advanced Options

You have the following options available if you check the Advanced box:

* **Time zone:** This option allows you to deliver the email in the user's time zone.  
* **Campaign Do Not Disturb:** This option allows you to stop the delivery of the campaign during a specified time. 
* **Campaign Cut-off:** This option allows you to stop the delivery of the campaign after a specified time. 
* **Global Throttle Limits** Global campaign limits are limits you can apply to determine how many emails each app user receives per day. If you would like to override these settings for an important campaign, you can click on the “Don’t apply global campaign limits to this campaign” checkbox.

<Image title="Campaign_Email_Message_Advanced.png" alt={1374} className="border" border={true} src="https://files.readme.io/717ef62-Campaign_Email_Message_Advanced.png" />

## Step 3: Define the Who

The next step is to specify the target audience for your Email campaign. 

You can target your Email campaign to a previously saved user segment from the list of pre-saved segments or bookmarks. The second choice is to create a new segment on the fly by clicking on + Create ad-hoc segment button. The third choice is to target all your users as shown below. 

<Image title="Campaign_Email_All_users.png" alt={1440} className="border" border={true} src="https://files.readme.io/da81700-Campaign_Email_All_users.png" />

### Ad-Hoc Segment

If you choose to create an ad-hoc segment, the target segment can be created based on [user interests](doc:psychographic-segmentation), past user behavior, and user properties. You can also filter the segment based on users who did not do something using the Did not do option.

<Image title="Screen Shot 2018-07-17 at 1.03.40 AM.png" alt={1296} className="border" border={true} src="https://files.readme.io/f8d516f-Screen_Shot_2018-07-17_at_1.03.40_AM.png" />

### Estimated Reach

You will have the option to see the Estimated Reach, which will estimate how many users qualify for the campaign criteria and who are also reachable through email. 

<Image title="Campaign_Email_Estimated_reach.png" alt={1391} className="border" border={true} src="https://files.readme.io/38129ac-Campaign_Email_Estimated_reach.png" />

> 📘 Why is the estimated reach of my campaign lower than expected?
>
> Some of your users might have unsubscribed from your marketing communications, so they will not be included in the segment of users who will receive this campaign. Another possible reason is some of your user profiles in CleverTap might not include the user's email address.

# Deliver to a Subset of the Target Audience

Sometimes you want to send a message to only a subset of the qualifying audience (Target Reach) for a campaign or avoid sending it if the number of qualified users exceeds the specified number.

A great use case for this is a limited offer you wish to send a fixed number of coupon codes you want to distribute. If the total reach for your campaign exceeds the number of coupon codes you can distribute you can simply limit the number of users who will receive the message to exactly the number of coupons you wish to distribute.

Here’s how it works:

In the campaign creation flow, when you are determining who to send your message to, under the Campaign Reach section, select the option to limit delivery of the messages to the number you choose.

For triggered campaigns (based on Live User Segments), as users qualify, they will receive the message until the total quantity specified has been delivered, after which the campaign ends. For campaigns based on Past Behavior Segments, we’ll randomly select the users that receive the message.

The campaign limits can also be configured as follows: 

* Daily Limit - Limit the number of users for each day, for Best Time, User-Timezone, and Triggered campaigns.

* Campaign Run Limit - Limit the number of users for each run of a campaign, for Fixed Time or Recurring campaigns.

* Safety check - It prevents sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. For example, a customer has a budget for distributing 1000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget. 

## Step 4: Define the What

You have three options for sending out an email in this section: 

* **Single message:** Send the same message to all users in your target audience. 
* **A/B test:** Send up to 3 message variants to a test group, to see which performs better. For more information on A/B test, see [Email A/B Testing](https://docs.clevertap.com/docs/email#section-email-a-b-testing).
* **Message on user property:** Localize messages based on user properties such as language. There is a section below that provides more information on [message personalization](https://docs.clevertap.com/docs/email#section-personalization).

<Image title="Campaign_Email_What_Message.png" alt={1438} className="border" border={true} src="https://files.readme.io/6d69063-Campaign_Email_What_Message.png" />

Next, you will define the email content in our [Email Editor](doc:email-editor) tool. You can select one of the pre-built email templates, or you can create your own custom email template by clicking the + New email with rich media button.

After you select an email template, you can add content to it, and customize the style and layout with buttons and images.

<Image title="ec8.png" alt={1236} className="border" border={true} src="https://files.readme.io/df8a762-ec8.png" />

### Personalization

The email message can be personalized for every user based on specific user property or event property values. See [the User Profiles page](doc:user-profiles) to learn more about user profile properties and events.

To use the personalization menu, type “@” in the text fields when creating the email message.\
Emojis can be included in your email messages, just like regular text. You can copy-paste emojis from Emoji keyboards online.

<Image title="image9.png" alt={288} className="border" border={true} src="https://files.readme.io/abb6e04-image9.png" />

### Liquid Tags

Liquid tags offer great flexibility in composing your message. You can have fixed or variable values and change the look and feel of your message by using Liquid Tags in the "new email with rich media" template.

![1357](https://files.readme.io/7f84b59-Campaign_Email_Liquid_Tags_example._.png "Campaign_Email_Liquid_Tags_example. .png")

Each email is personalized to the receiver. 

```html Output - Liquid
Hello John!

Here is a special coupon for you: Gold4All
```

For more information on using tags, see [Liquid Tags](doc:liquid-tags).

### Preheaders

A Preheader text is a preview of your email that your users can scan before they open it. Preheaders can call attention to the key message in your email and entice the user to read the rest of the email. If there is no Preheader text, the email inbox simply displays the beginning of your email text. It's a great opportunity to influence open rates positively.

<Image title="Campaigns_Email_Preheader_Output.png" alt={1378} className="border" border={true} src="https://files.readme.io/ab079b9-Campaigns_Email_Preheader_Output.png" />

After you have created the what section, click Continue. To display Preheader in your message, enter the Preheader text in the Preheader box. You can preview the text at this stage. 

<Image title="Campaigns_Email_Preheader.png" alt={2714} className="border" border={true} src="https://files.readme.io/a93bedf-Campaigns_Email_Preheader.png" />

It is recommended to limit the Preheader text to 100 characters. The final message will show the Preheader text along with the subject and the sender. 

### Email Add-On

The Email Add-on offers you preview across devices and inboxes before you send out the campaign. It also allows you to test your email for deliverability by creating a spam report. The Email Add-On offers you 300 email previews and spam reports a month. 

Before we begin, check that you have enabled the Inbox Previews. For enabling the Inbox Previews, see [Enable Email Previews](doc:enabling-previews).

#### **Step 1: Enable Inbox Previews (Optional)**

You can now preview your email across devices and inboxes before you send out the campaign. This will help you to understand how your email will be displayed on devices such as desktop or mobile, and email clients such as Gmail, Yahoo, and so on. 

> 🚧
>
> Check that you have enabled email previews. For more information, see [enabling previews](https://docs.clevertap.com/docs/enabling-previews).
>
> Email previews are available only if you have opted for the email add-on from CleverTap.

<Image title="campaign_email_template_preview.png" alt={1374} className="border" border={true} src="https://files.readme.io/6ac2830-campaign_email_template_preview.png" />

When you click “Previews”, a popup window with “Devices” and “Inbox” tabs will appear. 

Under “Devices” you can view desktop and mobile previews. 

<Image title="campaign_email_template_preview_Devices.gif" alt={1384} className="border" border={true} src="https://files.readme.io/a99f35a-campaign_email_template_preview_Devices.gif" />

Under “Inboxes”, you can check previews across various email clients.  

You can generate previews for various email clients by clicking the 'Run Tests' button in the preview window.\
Each of these preview thumbnails can be clicked and viewed on a full scale.\
You can also reload the preview images.

You will find the email clients listed under CleverTap > Settings > Email > Setup Previews.

<Image title="Campaign_Email_Create_Message_Inboxes_Preview.png" alt={1440} className="border" border={true} src="https://files.readme.io/ef3be30-Campaign_Email_Create_Message_Inboxes_Preview.png" />

At this stage, you can continue the campaign creation flow or save the message draft. If you save a draft, the previews will also be saved and regenerated when you open the draft again.

#### **Step 2: Check the Spam Report (Optional)**

You will likely want to ensure the deliverability of emails to your users. The spam report feature helps to determine the probability of the email message landing in a spam folder. You can check the spam report of your message at this stage after entering the sender details. 

<Image title="Campaign_Email_Create_Edit_Sender_Details.png" alt={1388} className="border" border={true} src="https://files.readme.io/ac5a5f4-Campaign_Email_Create_Edit_Sender_Details.png" />

After you enter sender details, click the 'Spam Report' button to check the spam report of your email, or continue building the campaign.  You will see a detailed report on your email message and a warning if the message does not pass any spam filter.

<Image title="Campaign_Email_EOA_Spam_Score.gif" alt={1440} className="border" border={true} src="https://files.readme.io/654138e-Campaign_Email_EOA_Spam_Score.gif" />

## Step 5: Test Email

You have the option to send a test email message to any email address using the Test Email option in the Email Editor tool. Click the More Options icon and click send a test email button. 

![1028](https://files.readme.io/94979e6-Campaigns_Email_Preview_Test.gif "Campaigns_Email_Preview_Test.gif")

## Step 6: Schedule Campaign

On this page, you have to select the [email provider](doc:email-partners) CleverTap will use to send the campaign to your users.

You have the option to add labels, conversion tracking, and a control group to this campaign.

* **Add labels:** Label your campaign with descriptive themes. Use these labels to then group campaigns and analyze performance.
* **Setup conversion tracking:** Add an event that represents a conversion goal for your campaign.
* **Enable a control group:** Define a percentage of your audience who will not receive this campaign so you can better understand performance.

<Image title="Screen Shot 2018-07-17 at 1.21.29 AM.png" alt={1299} className="border" border={true} src="https://files.readme.io/0bad678-Screen_Shot_2018-07-17_at_1.21.29_AM.png" />

Finally, you will see a summary of your email campaign. When you are ready to send the campaign, click the Schedule notification button.

<Image title="ec10.png" alt={1310} className="border" border={true} src="https://files.readme.io/de0ded3-ec10.png" />

# Viewing Email Campaign Stats

Once the campaign has gone out, you can view its stats by going into Email under Campaigns on the CleverTap dashboard and clicking on the campaign of interest to see its total sends, opens, conversions, and revenue from conversions (if applicable).

# Tracking Links in Email Campaigns

You can track the distribution of clicks on each link that you include in your email campaign.  For example, you want to send an email promotion for an upcoming movie on your video streaming app. You can create an email campaign and add links for reviews, promotions, movie merchandise, and so on, and then send the campaign.  We will record the clicks for each link in the email and you can see them on the Campaign Stats page. Open the email campaign from the campaign list page. 

<Image title="Campaign_Email_Split_Cicks.png" alt={1198} className="border" border={true} src="https://files.readme.io/d180aab-Campaign_Email_Split_Cicks.png" />

To view the stats for each link, click 'View split of clicks'.

<Image title="Campaign_Email_Split_Click_Display.png" alt={1200} className="border" border={true} src="https://files.readme.io/b747b3d-Campaign_Email_Split_Click_Display.png" />

# Email A/B Testing

CleverTap's Email A/B Testing feature lets you compare up to three different versions of an email to find the best performing one. You pick the size of the test audience for the A/B test, we will determine the winner based on the number of clicks, and then deliver the winning message to the rest of your target audience.

## Setup Steps

Creating an email campaign using the A/B testing feature follows a similar pattern to creating a normal email campaign. After choosing the segment to target and frequency of communication, you will be given an option to run the campaign as an A/B test. 

Click Select in the A/B test box to setup the email A/B test.

<Image title="Campaign_Email_Message_AB_Test.png" alt={1437} className="border" border={true} src="https://files.readme.io/2d0c585-Campaign_Email_Message_AB_Test.png" />

On the next page, build two or three different variations of the email you want to send. You can modify the email template, content, subject line, and sender name. 

Click Continue once you are finished building the email variations.

<Image title="ab2.png" alt={1342} className="border" border={true} src="https://files.readme.io/5529989-ab2.png" />

Select the sample size and wait time until the winning message is decided. Then click Continue.

![1320](https://files.readme.io/d0183c6-ab3.png "ab3.png")

> 👍 Winner Evaluation
>
> We will determine the winner based on the number of clicks, and then deliver the winning message to the rest of your target audience. 
>
> In the screenshot above, we are sending the A/B test to a sample size of 10% who will receive either Variant A or B. In other words, 5% of the target segment will receive email Variant A and another 5% will receive email Variant B. We will wait for 45 minutes to evaluate the winner based on the number of clicks. The winner variant is then sent automatically to the remaining 90% of the target segment.
>
> In the case of a tie between Variant A and B, we will send the remaining 90% email Variant A.

You are finished with setting up the A/B test portion of building your email campaign. Now, you can complete the rest of the steps similar to a normal campaign. Clicking Schedule Notification will finalize your email campaign.

<Image title="ab5.png" alt={1325} className="border" border={true} src="https://files.readme.io/f9096d9-ab5.png" />
