---
title: Amazon Simple Email Service
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
CleverTap supports sending emails through *Amazon SES*. 

# Integrating Amazon SES with CleverTap
To integrate Amazon SES with CleverTap, follow the steps below:

1. In the dashboard, navigate to *Settings* and click on **Integrate Email**.
2. Select *Amazon SES*.
3. Navigate to *Server Name* and *Port* values should be grabbed from your *Amazon SES* > *Dashboard* > *SMTP Settings*.
4. *Username* and *Password* values should match your SMTP credentials from *Amazon SES*. These are not your AWS account credentials.
5. *From Address* should have one of the values from *Amazon SES* > *Dashboard* > *Verified Senders* > *Email addresses list*. Most people will not open an email unless they recognize the sender.
6. Save your settings.
7. Click **Send a test email** and fill in your details to test the configuration details you entered. Has it arrived in your inbox? If not, refer to the troubleshooting steps below.

# Enabling Bounce and Complaint Processing

When an email is classified as bounced, CleverTap needs to be notified so that no further deliveries to that mailbox are attempted. This is considered a good practice and helps improve your sender reputation.

To enable support for bounce processing, follow the steps below:
1. Navigate to *Amazon SNS*.
2. Create a *Topic*.
3. Select the *Topic* and navigate to *Actions* > *Subscribe to Topic*.
4. Select *HTTPS* as the *Protocol*.
5. As the *Endpoint* value, add the *Callback URL* as shown in your CleverTap *Email* page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b7d933a-Callback_URL_v1_CLEVER-4714.png",
        "Callback_URL_v1_CLEVER-4714.png",
        1900,
        1260,
        "#fafbfb"
      ]
    }
  ]
}
[/block]
6. Save your settings by clicking on **Create Subscription**.
7. Navigate to *Amazon SES*.
8. Select the *Email Address* you had previously added to the CleverTap Dashboard.
9. Click on *View Details*.
10. Click on *Notifications* > *Edit Configuration*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5ae062-AWS_Domains_Notifications__v1_-_CLEVER-4714.png",
        "AWS Domains_Notifications__v1_-_CLEVER-4714.png",
        2862,
        1428,
        "#f7f7f7"
      ]
    }
  ]
}
[/block]
11. Under *SNS Topic Configuration*, select the topics you created earlier such as *Bounces*, *Complaints*, and *Deliveries* by clicking on the **Include original headers** checkboxes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc1da78-Edit_Notification_Configuration.png",
        "Edit Notification Configuration.png",
        2785,
        1407,
        "#cccfd1"
      ]
    }
  ]
}
[/block]
12. Save the configuration.

# Handling Unsubscribe Requests

To handle unsubscribed requests from users, refer to the steps in [Handling Unsubscribes](doc:handling-unsubscribes).

# Troubleshooting

The following explains some troubleshooting scenarios: 

  * Sandbox mode: If you’re getting an *Invalid Credentials* message when saving your settings, it could be that your *Amazon SES* account is a sandboxed one. You need a valid production-ready *Amazon SES* account to save your credentials. 
  * Spam: Check your *Spam* folder to see if the message has been classified as *Spam* by your email provider.
  * Email rendering: If your email does not render properly, check the subject line for newline characters or too many additional spaces. *Amazon SES* email converts data from UTF-8 format to a 7-bit ASCII format before sending it out. The next line characters or additional spaces may interfere with this conversion.