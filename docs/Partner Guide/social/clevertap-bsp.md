---
title: CleverTap
excerpt: Understand how to integrate the WhatsApp channel using CleverTap as a BSP.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

CleverTap is an official WhatsApp Business Service Provider (BSP). You can access WhatsApp business API directly from the CleverTap dashboard and create WhatsApp campaigns within a few minutes after WhatsApp onboarding. CleverTap's WhatsApp Business API removes the dependency of having any external WhatsApp BSP integration to use the WhatsApp channel with the CleverTap dashboard.

## Prerequisites For WhatsApp Onboarding

Listed below are the prerequisites to get started with WhatsApp onboarding with CleverTap BSP.

- You need a verified Facebook Business Manager page to access advanced WhatsApp features. To verify your account, you must submit a few vital documents. [Click here](https://en-gb.facebook.com/business/help/159334372093366) for more information about the list of documents required at a country level for account verification.

For non-verified pages, businesses can still have restricted access for up to 30 days.

<Callout icon="🚧" theme="warn">
  ### Admin Access

  It is mandatory for the user proceeding with the WhatsApp onboarding on CleverTap to have admin access to the Facebook Business Manager page.
</Callout>

- Ensure you provide a dedicated WhatsApp number for long-term use, as this number can not be changed later. This number must be a new number and should not be active on personal WhatsApp or Business WhatsApp applications.
- Ensure that your WhatsApp number is active, as you will receive an OTP for verification during the onboarding process.
- While onboarding, ensure that you enter your display name the same as the one used on the Facebook business manager page (also known as the legal name). If the display name doesn't match the business name, you must provide a web URL showing proof of association in the header/footer.
- Lastly, ensure that your business meets Facebook's [commerce policy](https://www.facebook.com/policies_center/commerce/).

<Callout icon="❗️" theme="error">
  ### Unique WhatsApp Number

  You must use a distinct WhatsApp number for each CleverTap project.
</Callout>

## Integrate WhatsApp using CleverTap BSP

To integrate WhatsApp using CleverTap BSP, follow the steps below:

1. Navigate to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Direct_ from the CleverTap dashboard.
2. Click **+ Provider** and select _CleverTap BSP_ from the _Provider_ dropdown.
3. Read all the prerequisites and click **Continue with Facebook**.
4. To register and connect your WhatsApp business account with CleverTap:

   i. Create or select your Meta and WhatsApp Business Account.<br />ii. Create your WhatsApp Business profile.<br />iii. Verify your WhatsApp Business number.

After completing the registration, your business is reviewed within 24 hours for compliance with WhatsApp's commerce policy.

5. After your onboarding is successful, you must complete the setup on the CleverTap dashboard.


<Image src="https://files.readme.io/9ee5198-bsp.png" alt="1134" align="center" caption="CleverTap BSP Setup" border={true} />


6. Select your _WABA Name_, _Nickname_, and mobile number to complete the setup.

7. Click **Save and Complete Setup**

<Callout icon="📘" theme="info">
  ### Note

  After completing the WhatsApp onboarding process, businesses can immediately:

  - Send business-initiated conversations to 250 unique customers in a rolling 24-hour period.
  - Register up to two phone numbers until the WABA display name is approved. Once the display name is approved you can add up to 50 numbers.
</Callout>

## Configure WhatsApp Username

WhatsApp supports usernames, an optional feature introduced by Meta that allows businesses to be identified by a unique handle in addition to their phone number. Businesses can configure a username directly from the _Mobile Number_ tab in CleverTap.

<Callout icon="📘" theme="info">
  ### **Note**

  This feature is available only for CleverTap BSP providers. It is not available for Gupshup, Nexmo, Generic WhatsApp, or archived providers.
</Callout>

### Prerequisites

The following conditions must be met before you configure a username:

- WhatsApp onboarding must be completed using CleverTap BSP.
- Your Meta Business account must have a verified display name.
- The username you want to claim must not already be taken.
- You must have the **Creator** role on the CleverTap dashboard.

### Configure a Username

To configure a username for your WhatsApp number:

1. Navigate to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Direct_ from the CleverTap dashboard.

2. Select your provider and click the _Mobile Number_ tab.

3. Click the **⋮** menu next to your number.

4. Select **Configure Username** from the dropdown.&#x20;


   <Image src="https://files.readme.io/c9165d5b22c977758f57fd77b3e421e0ff79972021f47acf3eb3c4c6ea2b787f-Configure_user_name.png" align="center" caption="Configure Username" border={true} />


5. Enter your desired username in the _Username_ field, or select one from the _Reserved Usernames_ suggestions to pre-fill the field.&#x20;


   <Image src="https://files.readme.io/224c8412bc76a3c4314df5257d1609d08e182739732cfdc1f67e63cfc91ce148-configure_username.png" align="center" width="65%" caption="Add Username" border={true} />


6. Click **Save**.

### Username Rules

For the complete and up-to-date list of username requirements, refer to [Meta's WhatsApp username documentation](https://developers.facebook.com/documentation/business-messaging/whatsapp/business-scoped-user-ids/).

### Reserved Usernames

The _Configure Username_ modal displays a list of username suggestions generated by Meta based on your business display name and WABA profile. Selecting any suggestion pre-fills the _Username_ field. These are not usernames that have already been claimed or blocked. They are recommendations specific to your WhatsApp Business Account.

### Force Update Username

The _Force Update Username_ checkbox applies in a specific scenario: if a username you want to configure is already assigned to another phone number within the same WhatsApp Business Account, selecting this checkbox transfers the username from that number to the current one.

<Callout icon="⚠️" theme="warn">
  ### **Warning**

  Using **Force Update Username** removes the username from the phone number it is currently assigned to. Ensure that the affected number no longer requires that username before proceeding.
</Callout>

### Username Status

After saving, the _Username Status_ column on the _Mobile Number_ tab reflects the current state of your username. The following statuses are possible:

| Status           | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| _Not Configured_ | No username has been set for this number.                                   |
| _Reserved_       | The username has been claimed and is awaiting approval from Meta.           |
| _Active_         | Meta has approved the username. It is live and associated with this number. |

## Creating WhatsApp Message Templates

CleverTap BSP customers can easily create WhatsApp Message Templates directly from our platform. There's no need to create the template in Meta first and then recreate it on the CleverTap dashboard. CleverTap automatically syncs the status of your templates with the Meta dashboard, ensuring that your templates always have the latest status in CleverTap.

If required, you can manually [refresh the status of the templates](doc:whatsapp-message-templates#edit-delete-or-refresh-whatsapp-message-templates). You can [import the templates from Meta into CleverTap](doc:whatsapp-message-templates#import-templates) if you want to sync the actual templates

To create different WhatsApp message templates on CleverTap, refer to this detailed document on [Creating WhatsApp Templates](doc:whatsapp-message-templates#create-whatsapp-template).

## Create a Campaign

To create a WhatsApp campaign using CleverTap BSP, refer to this detailed document on [How to create a WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign).

## Create a Journey

To create a WhatsApp journey using CleverTap BSP, refer to this detailed document on [How to Create a WhatsApp Journey](https://docs.clevertap.com/docs/engagement-nodes-whatsapp).

## Creating WhatsApp Message Templates (in Meta)

If you have trouble creating message templates from your CleverTap account, you can create them directly from your Meta account and import them. To get started with template creation in your WhatsApp Business Manager Account provided by Facebook, follow the steps:

1. Log in to your [Facebook Business Manager account](https://business.facebook.com/).


<Image src="https://files.readme.io/3f97347-FB_Manager.png" alt="2868" align="center" caption="WhatsApp Manager" border={true} />


2. Open the hamburger menu at the top of the page and select **WhatsApp Manager**. The  WhatsApp Business accounts page opens.
3. Click **Message templates** from the left navigation menu under _Account tools_ as shown below. The list of templates is displayed, where you can see all of your existing templates, their status, and quality ratings.


<Image src="https://files.readme.io/57c5e4b-image_19.png" alt="2618" align="center" caption="Message Templates" border={true} />


4. Click **Create Template**. The template creation page opens.


<Image src="https://files.readme.io/be1b049-image_22.png" alt="2716" align="center" caption="Template Configuration" border={true} />


4. Select the Category, Name, and Language :
   - _Category_: Select the type of template you want to create. You can hover over the template types to view details for each template.
     <Callout icon="📘" theme="info">
       ### Unsupported Template Categories

       The **Marketing (Product Messages)** and **Authentication templates** are not supported. We recommend not creating these templates in the WhatsApp Manager Account as they can cause compatibility issues.
     </Callout>
   - _Name_: Enter the template's name in lowercase letters, numbers, and underscores only.
   - _Language_: Select the languages for your message template. You can delete or add more languages in the next step.
5. Click **Continue** after filling up all the required details.
6. Configure the template per your requirement and provide a contextual sample for each custom variable added to the template.


<Image src="https://files.readme.io/1212308--92-WhatsApp-Manager.png" alt="Define Template Content" align="center" caption="Define Template Content" border={true} />


7. (Optional) Enhance user interactions with messages by incorporating **interactive buttons**. The following information allows you to create and utilize _Call to action (CTA)_ and _Quick Reply_ buttons within your templates:

- **Call to Action (CTA) Buttons:**
  - Meta supports the following CTA buttons: _Call Phone_ and _Visit Website_.
  - WhatsApp supports only two CTA buttons with Templates. You can include one _Call Phone CTA_ button and one _Visit Website CTA_ button in your templates.
  - The _Visit Website CTA button_ supports static and dynamic redirection URLs.
    - For static redirection URLs, enter the complete URL for redirection (for example, [https://www.example.com/gp/bestsellers](https://www.example.com/gp/bestsellers)).
    - For dynamic redirection URLs, enter the domain of the URL along with a variable (for example, [https://www.example.com/{{1}}](https://www.example.com/{{1}})).

<Callout icon="📘" theme="info">
  ### Tracking Clicks With _Visit Website_ CTAs

  To track clicks in the CTA, we recommend selecting dynamic URLs. Use the following URLs as the Website URL based on your CleverTap account region:

  EU1:[https://ct1.io/{{1}}](https://ct1.io/{{1}})

  IN1: [https://ct3.io/{{1}}](https://ct3.io/{{1}})

  SG1: [https://ct4.io/{{1}}](https://ct4.io/{{1}})

  US1: [https://ct5.io/{{1}}](https://ct5.io/{{1}})
</Callout>

- **Quick Reply Buttons:**
  - Quick Reply buttons allow the users to choose from predefined response options. For more information about Quick Reply buttons, refer to [WhatsApp Quick Replies](https://faq.whatsapp.com/1791149784551042/?helpref=uf_share).
  - WhatsApp supports up to three _Quick Reply buttons_ in templates, allowing users to select a suitable option quickly.

8. (Optional) Click **Add Sample** to add an optional content example for your template. This helps in understanding the type of message you want to send during the review and approval process.

<Callout icon="❗️" theme="error">
  ### Sample Content for Template

  Ensure that the sample content that you add does not include any actual user or customer information.
</Callout>

9. Click **Submit**.

Your template is now sent for review. The status of your template is visible under _Message templates_. After your message is approved, you can copy the message template and paste it into the CleverTap dashboard. To learn more about the template creation process, refer to this [detailed document](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343) by Facebook.

<Callout icon="📘" theme="info">
  ### Pre-Approved Message Templates

  Facebook offers some pre-approved WhatsApp message templates for testing. You can use these templates in the CleverTap dashboard to start sending test messages as soon as you complete WhatsApp onboarding.
</Callout>

## FAQs

### Onboarding

**Q. What is Facebook business manager account verification?**<br />A. As the [prerequisite](doc:clevertap-bsp#prerequisites) for WhatsApp onboarding explains, your Facebook business manager account needs to be verified to get full WABA access. Facebook business verification is the way for Facebook to know that your business is a legitimate organization. Your business must be registered as per the business registration process of your country.

**Q. Do I need to verify the Facebook manager account again if it is already verified?**<br />A. Facebook business verification is also required for other purposes, along with getting WABA access. Given this, there are chances that you have already verified your business manager account. You do not have to go through the verification process if your account is verified.

**Q. How do I check if my Facebook business manager account is verified or not?**<br />A.  To check if your Facebook business manager account is verified, open your Facebook business manager account and navigate to _Settings_. Scroll down and click _Security Settings_. If your Business manager account is verified, the "Security Center" section displays as follows:

**Q. What are the requirements for business verification?**<br />A. To verify the business manager account, you must fill in the business details. Ensure that the information provided aligns with the details registered with local authorities. As long as Facebook can verify your organization from the given information, there is no need to provide supporting documents for verification. To check the exact requirements for verification in your country, refer to the [detailed documentation](https://www.facebook.com/business/help/159334372093366)

**Q. My Facebook business manager is not verified; how do I get it verified?**<br />A. Follow the steps given in this [document](https://www.facebook.com/business/help/2058515294227817?id=180505742745347) to understand the steps required for getting your Facebook business manager account verified.

**Q. How long does Facebook take to verify the business manager account?**<br />A.  Facebook takes a few weeks to verify the business manager account. This is subjective to how soon Facebook can verify your documents and can take longer in some cases.

**Q. What happens if I complete WhatsApp onboarding without business verification?**<br />A. Previously, businesses could not send any messages before completing the account verification. This meant if verification took a few weeks, they had to wait that long to start using the WhatsApp Business APIs.

While waiting for verification, businesses can use the unverified trial experience (sandbox) to test the functionality. During the trial experience, businesses are allowed to initiate a conversation with a limited number of users, but the business can respond to unlimited incoming chats. [Read more](https://www.facebook.com/business/help/2640149499569241).

**Q. Are there any repercussions if I do not verify the Facebook business manager account?**<br />A. It is important to start your Facebook Business verification as soon as possible. In most cases, the account is verified the same day as the process starts, but in some cases, this may take some time. If the business is not verified by Facebook or approved as per WhatsApp commerce and display name policy within 30 days, the number goes offline.

**Q. What are the best practices for WhatsApp display names?**<br />A. Do not add extra words, spaces, or special characters to your company or brand name used in the business display name. To learn more, refer to the [document](https://www.facebook.com/business/help/338047025165344).

**Q. I have completed onboarding; how do I check if my WABA account/display name is approved?**

A. Display approval happens after your business is verified, so if you have not verified your business yet, start the verification at the earliest.

To check your display number approval status, open your Facebook business manager account and navigate to _WhatsApp business manager_ from the hamburger icon in the left navigation bar. Now, select the WhatsApp account associated with the number for which you want to check the display name approval status, and then click _Phone numbers_ from the left navigation bar under _Account tools_.


<Image src="https://files.readme.io/f1f512a-waba.png" alt="1852" align="center" caption="Display Number Approval Status" border={true} />


Now, click _View_ under Certificate. If your display name is approved, the Display name has an _Approved_ tag in front of it, as shown below:


<Image src="https://files.readme.io/1a38601-approved.png" alt="1358" align="center" caption="Approval Status" border={true} />


**Q. How do I check my current messaging limit?**<br />A. To check your current messaging limits, open your Facebook business manager account and navigate to WhatsApp business manager from the hamburger icon in the left navigation bar. Further, select the WhatsApp account associated with the number for which you want to check the Display name approval status and then click _Phone numbers_ from the left navigation bar under _Account tools_. Your messaging limit appears under _Messaging limit_ in the phone numbers table.


<Image src="https://files.readme.io/19a0128-mess_limit.png" alt="2876" align="center" caption="Check Messaging Limit" border={true} />


**Q. How do I increase the messaging limit?**<br />A. To learn about the messaging limit levels, refer to this [detailed document by Meta](https://developers.facebook.com/docs/whatsapp/messaging-limits#messaging).

**Q. How do I check my Whatsapp message usage ?**

A. You can check your WhatsApp usage for the current month from your Meta Business Manager account. To view your usage:

1. Login to your account and select WhatsApp Manager from the Tools shortcuts or under Engage Customers > WhatsApp Manager.


<Image src="https://files.readme.io/1345c2e-meta_business_login.png" alt="login to meta business account" align="center" caption="Meta Business Login" border={true} />


Your WhatsApp accounts and onboarded numbers are displayed.


<Image src="https://files.readme.io/1287cd8-WhatsApp_numbers.png" alt="WhatsApp Insights View" align="center" caption="WhatsApp Insights View" border={true} />


2. Select any of the numbers to view usage and charges.
3. Go to Account Tools > Insights.
4. Select the date range to display usage.


<Image src="https://files.readme.io/777c470-WhatsApp_numbers_and_their_stats.png" alt="View usage by date range" align="center" caption="View usage by date range" border={true} />


### Message Templates

**Q. What are message templates?**

A. As explained earlier, there are two types of conversations - user-initiated and business-initiated. In the case of user-initiated conversations, you can send any text to end-users. However, if your business initiates the conversation, you can only send the message reviewed and approved by Facebook. These approved text messages are called Message templates.

**Q. How much time does Facebook take to review the templates?**<br />A. It can take up to 24 hours for approval. Once approved, a notification appears in your WhatsApp Manager, and we send an email to your Business Manager admins. In addition, we also send a webhook notification if you subscribe to message template status changes. Learn more about [Monitoring Status Changes](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#monitoring-status-changes).

**Q. Are there any best practices for message templates?**<br />A. Facebook expects you to create templates for genuine use cases and not violate their [policy](https://www.whatsapp.com/legal/business-policy/?fbclid=IwAR3dL90AcNa3qrmGiyDvsWjfhk0dpACCfAMzo5jUrt82CMjxPempfxYl1Dg). There is no single correct approach to creating templates but following these basic guidelines will help in getting your templates approved quickly and customers also enjoy interaction with your business.

1. Templates should be short, simple, and have only the necessary text to pass on the required information to the customer.
2. Templates must not have any grammatical or spelling mistakes. Templates that include major spelling or grammatical mistakes are likely to be rejected. Templates with minor punctuation errors or grammatical inconsistencies may be approved but should be avoided.
3. Be mindful of formatting errors. Ensure that you are not missing any sequence in variables ie. {{1}},{{3}},{{4}} or used the curly braces properly in dynamic variables.
4. Title of the template should explain how the template is going to be used. for example, if you are creating a template for sending booking information, the title should be booking\_update. Also, note that the title can not be changed later so name the templates in such a way that it is easier to identify your templates easily.
5. If you plan to use any redirection URLs, ensure that you provide full URLs. Using short URLs in templates might cause templates to be rejected.
6. Use the same language in the template content you chose in the template language field. For example, if you chose Arabic as the template language, then write template content in Arabic.

Refer to these detailed documents by [Facebook](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#quality-rating-and-template-status) to learn more about the best practices for WhatsApp message templates.

**Q. How do I create new templates?**<br />A. Refer to the [Add Message Template](doc:clevertap-bsp#add-message-template) section.

**Q. What are the common reasons for template rejection?**<br />A. Listed below are the common reasons for template rejections:

- Variable parameters are missing or have mismatched curly braces. The correct format is {{1}}.
- Variable parameters contain special characters such as a #, $, or %.
- Variable parameters are not sequential. For example, {{1}}, {{2}}, {{4}}, {{5}} are defined but {{3}} does not exist.
- The message template contains content that violates [WhatsApp's Commerce Policy](https://www.whatsapp.com/legal/commerce-policy?l=et).
- The message template contains content that violates [WhatsApp's Business Policy](https://www.whatsapp.com/legal/business-policy/?lang=en).
- The content contains potentially abusive or threatening content, such as threatening a customer with legal action or threatening to shame them publicly.
- The message template is a duplicate of an existing template. If a template is submitted with the same content in the body and footer of an existing template, the duplicate template is rejected. A rejection email notification, including the rejection reason that appears in _Account Quality_ on WhatsApp Manager, is sent. You may refer to the Account Quality notification to see the name and language of the existing template with the same content as the rejected duplicate template. You may also choose to edit the template and resubmit. Please note that this check does not apply to OTP templates.

**Q. Can I edit the templates after they are approved?**<br />A. You can edit a template using the WhatsApp Manager or the [Message Template](https://developers.facebook.com/docs/whatsapp/business-management-api/message-templates#edit-a-message-template) endpoint. Note that if you edit a message template and resubmit it for approval, its status changes to _In Review_ and cannot be sent to customers until its status changes to _Active_.

**Q. What is template quality, and how do I check the quality of my templates?**<br />A. To check the quality rating of your templates, open your Facebook business manager account and navigate to _WhatsApp business manager_ from the hamburger icon in the left navigation bar. Further, select the WhatsApp account associated with the number for which you want to check the template quality rating, and then click on _Message templates_ from the left nav bar under account tools.

**Q. What are common template statuses?**<br />A. Templates can have the following statuses:

- In-Review: This indicates that the template is still under review. Review can take up to 24 hours.
- Rejected: Indicates that the template has been rejected during the review process. [Learn more](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#appeals).
- Active - Quality pending: Indicates that the message template is yet to receive quality customer feedback. Message templates with this status can be sent to customers. Learn more about [Quality Rating](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#quality-rating).
- Active - High Quality: Indicates that the template has received little or no negative customer feedback. Message templates with this status can be sent to customers. Learn more about [Quality Rating](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#quality-rating).
- Active - Medium Quality: Indicates that the template has received negative feedback from multiple customers but may soon become paused or disabled. Message templates with this status can be sent to customers. Learn more about [Quality Rating](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#quality-rating).
- Active - Low Quality: Indicates that the template has received negative feedback from multiple customers. Message templates with this status can be sent to customers but are in danger of being paused or disabled soon, so we recommend that you address the issues that customers report. Learn more about [Quality Rating](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#quality-rating).
- Paused: Indicates that the template has been paused due to recurring negative customer feedback. Message templates with this status cannot be sent to customers. Learn more about [Template Pausing](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#template-pausing).
- Disabled: Indicates that the template has been disabled due to recurring negative customer feedback or for violating one or more of our policies. Message templates with this status cannot be sent to customers. You may be able to edit a disabled message template and request an appeal. [Learn more](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#appeals).
- Appeal Requested: Indicates that an appeal has been requested. [Learn more](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/#appeals)

### Number Quality

**Q. What is number quality and connection status?**<br />A. Your quality rating indicates how template messages have been received by your users in the last 24 hours. There are three different states of messaging quality:

- Green: High quality
- Yellow: Medium quality
- Red: Low-quality

If your Quality rating remains Red for seven or more days, your number's connection status changes to _Flagged_ or _Restricted_.

- Flagged: Indicates that the quality rating has reached a low state. Businesses can not upgrade messaging limit tiers during the Flagged phase. If the message quality improves to a high or medium state by the seventh day from when your status was moved to Flagged, the status changes to _Connected_. If the quality rating does not improve, the status still changes to Connected, but you are placed in a lower messaging limit tier.
- Restricted: Indicates that you have reached your messaging limit. During a Restricted phase, you can not send any notification messages until the 24-hour window is reset. However, you can respond to any messages that customers initiate. [Learn more](https://www.facebook.com/business/help/896873687365001).

**Q. How do I check my number quality?**<br />A.  Navigate to Facebook business manager and open WhatsApp business manager. Further, click _Phone number_ under _Account tools_. This will show you the number quality and status of your numbers.


<Image src="https://files.readme.io/a6f98eb-message.png" alt="1910" align="center" caption="Number Quality" border={true} />


**Q. What to do if the number quality is Red? How to improve Quality Rating?**<br />A. Follow the guidelines below to improve your Quality Rating:

- Reduce the WhatsApp campaigns for a week and send only important notifications and target your champion user base only.
- Ensure that your templates comply with the WhatsApp Business Policy.
- Ensure that your messages are clear, personalized, and useful to users.
- Avoid sending open-ended welcome or introductory messages.
- Only send template messages to users that have opted in to receive messages on that specific topic. For example, if a user opted-in for COVID updates but starts receiving other health updates, they may respond negatively because they did not opt-in for that specific communication.
- Be mindful of your messaging frequency. Avoid sending users too many notifications in a day.
- Be thoughtful of informational messages, and optimize the content and the message length.
- Check if your organization has added and sent a new template within the last 7 days. This may help determine a problematic template(s).

### Number Migration

**Q. I want to migrate my number from CleverTap to external BSP; what is the process?**<br />A. Please contact your account manager to seek support for the migration process or raise a ticket with our support team from your CleverTap dashboard.

**Q. I want to migrate numbers from external BSP to CleverTap BSP; how do I get this done?**<br />A. Please contact your account manager to seek support for the migration process.<br />Also, refer to this [document](https://developers.facebook.com/docs/whatsapp/business-management-api/guides/migrate-phone-to-different-waba/) to know more about the migration process.
