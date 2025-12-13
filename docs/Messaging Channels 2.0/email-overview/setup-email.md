---
title: Setup
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
DOCS NOTES: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGES ARE UNPUBLISHED (OR DELETED)
https://docs.clevertap.com/docs/enabling-previews

REFERENCE CONFLUENCE PAGE: https://wizrocket.atlassian.net/wiki/spaces/SUC/pages/1720386423/SendGrid+Email+Onboarding

@DOCS: FELICE WILL PUBLISH LATER ONCE ALL SUB-SECTIONS HAVE BEEN APPROVED. 

# Overview
This section covers various email tasks, including the integrations, the setup, the warmup process, and inbox previews. No matter what type of customers emails, all businesses have the same goal to get to the correct, recipient's inbox. By setting up your email properly, you ensure successful email deliverability.

While metrics, such as clicks and opens, are important to look at, your emails need to get delivered first before they can get clicked on or opened rather than being routed to the spam folder or being blocked by the inbox provider.

To maintain consistent delivery rates, businesses need to constantly prioritize the health of their email program. This means properly establishing the infrastructure and authentication, maintaining a positive sending reputation, creating a great user experience, and adapting the program to meet new and changing regulations.

#Email Integrations
Before you can create email campaigns, you must integrate an email service provider with CleverTap. 

CleverTap supports integrations with popular email service providers. Select your email service provider from the following list:
  * [Mandrill](doc:mandrill) 
  * [Amazon Simple Email Service](doc:amazon-simple-email-service) 
  * [Postmark](doc:postmark) 
  * [SendGrid](doc:sendgrid) 
  * [Mailgun](doc:mailgun)
  * [Generic SMTP](doc:generic-smtp)
  * [Gmail/Google Apps](doc:gmail-google-apps) 

#Email Setup
Once you have integrated an email service provider with CleverTap, you can set up your email.

To add a provider, perform the following steps:
1. From the dashboard, navigate to *Settings* > *Engage* > *Channels* > *Email*.
2. Click **+ Provider** to add a provider. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9206de0-Plus_provider.png",
        "Plus provider.png",
        1162,
        460,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]
3. Add the SMS provider's information.
4. Click **Save**.

## Search Email Clients
To search for an email client, perform the following steps:
1. From the dashboard, navigate to *Settings* > *Engage* > *Channels* > *Email*.
2. Enter the provider name in the search box.

# Email Warmup Process
The email warmup process is done to ease the inboxing process and establish a positive sending reputation with internet service providers (ISPs). It is essential when you are planning to use a new, dedicated IP address/domain where you plan on deploying large volumes of emails. This strategy is designed to set you apart from spammers and let ISPs know the type of mailing you are doing.

##IP Warming
IP warming is the practice of gradually increasing the volume of mail sent with a dedicated IP address according to a predetermined schedule. This gradual process helps to establish a reputation with ISPs as a legitimate email sender and also improves the deliverability of your emails.

[block:callout]
{
  "type": "info",
  "body": "We recommend that you have a list of contacts of more than 10,000 emails.",
  "title": "Recommended List of Contacts"
}
[/block]
During this warmup period, ISPs evaluate your email list health, sending behavior, email list health, and whether you are providing relevant and valuable information to your recipients. The more engagement you receive, the better the ISPs will favor your IP. You can monitor and optimize your entire email campaign. Once you have built a good reputation during the warmup period, you can focus on your email strategy, the content, and the tracking results.
[block:callout]
{
  "type": "info",
  "body": "<< @PM/TEAM: CAN SOMEONE CONFIRM THIS NOTE AND ADD MORE INSIGHTS/DETAILS? >> \n\nIf you have set up your email service provider with SendGrid, their consultants can help you with IP warming and monitor your domain as well as your IP quality.",
  "title": "SendGrid Support"
}
[/block]
##Populate Historical Data into CleverTap
From the initial days of deployment, you will want to upload all the active engaged users from your previous email provider so that it helps you have a good response rate which in return helps to improve your sender reputation.

Following is the criteria which we request you to export from the previous email sender and upload into our CleverTap dashboard:
  * Email opened users in the last 30/60/90/180 days respectively.
  * Email clicked users in the last 30/60/90/180 days respectively.
  * Suppression lists (unsubscribes, bounces, spam reports). 

For more information, refer to [CSV Upload](https://docs.clevertap.com/docs/csv-upload).

The following is a sample format on how to upload the users into CleverTap via a CSV upload based on the previous user engagements. 
[block:callout]
{
  "type": "warning",
  "body": "The emails must be under the *identity* column where:\n* The letter \"i\" has to be lowercase.\n*  *identity* always has to be the first column irrespective of their user properties.",
  "title": "CSV Requirements"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8219ca0-Historical_data.png",
        "Historical data.png",
        512,
        384,
        "#d5dbca"
      ]
    }
  ]
}
[/block]
After you upload the users based on the recency of the users, you can find these details during the email campaign creation in the *Who* step. 

For more information on creating an email campaign, refer to [Email](https://docs.clevertap.com/docs/email).

<< @PM: IS THIS SCREENSHOT STILL VALID? >>

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/724be4c-Display_common_properties.png",
        "Display common properties.png",
        512,
        293,
        "#faf6f6"
      ]
    }
  ]
}
[/block]
The following is a sample format on how to upload the suppression list of users.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c2dde94-Sample_format.png",
        "Sample format.png",
        512,
        285,
        "#d8d9b5"
      ]
    }
  ]
}
[/block]
##Warmup Plan Steps
The following shows the steps broken down by days as per your warmup plan where you should start sending emails to your most highly engaged users.
  * Day 1: 100 users.
  * Day 2: 180 users. You should not send to the same users from day 1.
  * Day 3: 320 users. You should not send to the same users from day 1 and 2.
  * Day 4: 600 users. You should not send to the same users from day 1, 2, and 3.
  * Day 5: 1,000 users. You should not send to the same users from day 1, 2, 3, and 4.

Follow the same steps for the remaining days of your warmup plan. If the users are unique, we would only require one email template until your overall list gets exhausted.

If you are planning to send openers from these day sends during the warmup plan, we always have to create new email content in order to not receive the same email again.

This checklist created for your warmup process is to ensure a smooth transition:
  * Check for all the links whether they are redirecting to the desired page.
  * Check for all the images whether they are rendering properly or not.
  * Check for the unsubscribe link whether it is working or not.

##IP Warming Best Practices
Here are some IP warming best practices to consider:
  * Begin with the most active and engaged users (openers/clickers of last 30, 60, and 90 days respectively).
  * Start by sending small volumes of email and increase the amount you send each day as gradually as possible.
  * Ensure that your email list is clean and does not have old or unverified emails.
  * Ensure that your first content is highly engaging and maximizes the likelihood that users click, open, and engage with your email.
  * When the IP warming is complete, continue sending as consistently as possible.
  * Carefully monitor your sender's reputation while you conduct the IP warming process. 

# Inbox Previews

Before you can use inbox previews, you must enable them. Inbox previews with code analysis let you view an analysis of your HTML code. It also provides the capability to view previews across devices and inboxes before you send out a campaign. 

## Enable or Disable Inbox Previews
To enable or disable the inbox preview, perform the following steps:
1. From the dashboard, navigate to *Settings* > *Engage* > *Channels* > *Email*.
2. Select the *Previews* tab.
3. Select a client from the list.
4. Click on the ellipsis, and click **Enable** or **Disable**.


[block:callout]
{
  "type": "info",
  "title": "Multi-select",
  "body": "You can also select multiple clients, then enable or disable previews by clicking **Enable in inbox previews** or **Disable in inbox previews**."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49e8f2d-Enable_an_inbox_preview.png",
        "Enable an inbox preview.png",
        1172,
        539,
        "#f9f8f7"
      ]
    }
  ]
}
[/block]
The *Previews* tab lists the available email inboxes. For example, a mobile device that runs Gmail on Android 8 or a computer that runs Apple Mail 10 on an OS X 10.10 operating system. 

[block:callout]
{
  "type": "warning",
  "body": "You must specify the accounts that must have email previews and spam reports before signing up. Email previews are available only if you have opted for the email add-on from CleverTap. \nThis feature is not available for trial accounts. \n\n<<@PM/Harsh should we still keep this note?>>",
  "title": "Account Specifications"
}
[/block]
<< @PM: THE SECTIONS BELOW UNDER 'EMAIL AUTHENTICATION' WERE COPIED/PASTED FROM https://docs.google.com/document/d/1LO9-QvAUs8_Pzt-7G-2wDjo0726ScrU3aNPNsruYJdo/edit CAN EVERYTHING BE SHOWN AS IS? IF SO, DOCS WILL EDIT IT TO ADHERE TO OUR STYLE GUIDE LATER. >>

# Email Authentication
Authentication is the process of attempting to verify the digital identity of the sender of a communication. There are three main types of email authentication: SPF, DKIM, and DMARC (optional).

##SPF Record (Setup by SendGrid)
SPF stands for Sender Policy Framework. SPF is an email authentication method that identifies the mail servers that are approved to send emails from a specific domain. ISPs use this validation protocol to determine when spammers and phishers are trying to impersonate your brand to send malicious emails from your domain.
While inbox providers generally don’t block email solely based on a missing SPF record, it’s one more data point that contributes to your positive sender reputation. Plus, it helps protect your brand.

###How to check for the SPF records
Log in to your CleverTap account and create a campaign in the Email channel.
Send a test mail to your email id.
Log in to your email account and navigate to the test email received in your inbox.
Open the header content for that particular email. (Follow the steps particular to your mailbox providers such as Google, Yahoo or Hotmail or even the email client you are using such as IBM Lotus Notes or Outlook)
Search for the keyword “SPF” in that text and if you find “spf=pass”, this signifies that the SPF records are properly in place.

##DKIM Email Signature (Setup by SendGrid)
DKIM stands for DomainKeys Identified Mail. DKIM allows you to publish a key that ISPs use to verify that the email message didn’t change in transit and the sender can take ownership of the content. DKIM defends against malicious modification of messages in transit, and it carries a lot of reputation weight with inbox providers. Messages not signed with a DKIM signature aren’t likely to see the inbox.

###How to check for the DKIM records
Log in to your CleverTap account and create a campaign in the Email channel.
Send a test mail to your email id.
Log in to your email account and navigate to the test email received in your inbox.
Open the header content for that particular email. (Follow the steps particular to your mailbox providers such as Google, Yahoo or Hotmail or even the email client you are using such as IBM Lotus Notes or Outlook)
Search for the keyword “DKIM” in that text and if you find “dkim=pass”, this signifies that the SPF records are properly in place.

##DMARC Record Publishing (This will be required to be set up at your end)
A Domain-based Message Authentication, Reporting & Conformance (DMARC) record is a protocol that uses SPF and DKIM to determine the authenticity of an email. The protocol allows you to specify how you want ISPs to handle emails that were not authenticated using SPF or DKIM. You can decide to send those emails straight to the junk folder or have them blocked altogether.

##BIMI (This will be required to be set up at your end)
BIMI is an acronym of Brand Indicators for Message Identification. It is an open standard created jointly by several big players in the email market, such as Google and Verizon Media/Yahoo.
BIMI provides the MBP with a consistent and reliable way of retrieving the correct logo for every email. Brands benefit from BIMI due to the fact that email recipients see the familiar brand logo immediately. Recognizing a logo is much faster than reading and creates a different and additional level of trust. After all; “a picture is worth a thousand words.” Open rates of emails should increase after BIMI is implemented. Additionally, due to the way how BIMI is designed, it helps to prevent fraudulent emails.
BIMI is an open standard, so anyone can implement and use it. BIMI builds upon the well-established standards of SPF, DKIM, and DMARC. Provided these are already in place, BIMI is just a small step away.

These are the main, minimal steps required:
Implement DMARC as it is required for BIMI.
DMARC policy has to be set to “reject” or “quarantine.”
Create your logo as a square SVG file without any text.
Publish your logo on an accessible web-source.
Create a DNS TXT record for your emails’ “From:” address. Something like: default._bimi.yourbrand.com IN TXT "v=BIMI1; l=https://subdomain.yourbrand.com/image/logo.svg; a=;"
OR
With a Verified Mark Certificate:
default._bimi.yourbrand.com IN TXT "v=BIMI1; l=https://subdomain.yourbrand.com/image/logo.svg; a=cert;https://subdomain.brand.com/vmc/logo.pem;"