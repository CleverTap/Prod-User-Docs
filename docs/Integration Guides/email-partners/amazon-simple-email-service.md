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
CleverTap supports sending emails through Amazon SES. 

# Step 1: Integrating Amazon SES with CleverTap

* In the dashboard, navigate to Settings and click on Integrate Email.
* Select Amazon SES.
* Go to Server Name and Port values should grabbed from your Amazon SES → Dashboard → SMTP Settings.
* Username and Password values should your SMTP credentials from Amazon SES. These are not your AWS account credentials.
* From Address – This should have one of the values from Amazon SES → Dashboard → Verified Senders → Email addresses list. Most people will not open an email unless they recognize the sender.
* Save your settings.
* Finally, click Send a test email and fill in your details to test the configuration details you entered. Has it arrived in your inbox? If not, see troubleshooting steps below.

# Step 2. Enabling Bounce Processing

When an email is classified as bounced, CleverTap needs to be notified so that no further deliveries to that mailbox are attempted. This is considered a good practice and helps improve your sender reputation.

To enable support for bounce processing, follow the steps below.

* Go to Amazon SNS
* Create a Topic. Learn more here
* Now select that Topic, and navigate to Actions → Subscribe to Topic
* Select HTTPS as the Protocol
* As the Endpoint value, add the Callback URL as shown in your CleverTap Email Settings page
* Save your settings by clicking on Create Subscription
* Navigate to Amazon SES
* Select the Email Address that you had previously added to the CleverTap Dashboard
* Click on View Details
* Click on Notifications → Edit Configuration
* Under SNS Topic Configuration, select the Topic you created earlier
* Save the configuration

# Step 3. Handling Unsubscribe Requests

To handle unsubscribe requests from users, you can follow the steps [mentioned here](doc:handling-unsubscribes).

# Step 4: Troubleshooting

* Sandbox mode: If you’re getting an Invalid Credentials message when saving your settings, it could be that your Amazon SES account is a sandboxed one. You need a valid production ready Amazon SES account to save your credentials. Learn more here
* Spam: Check your SPAM folder to see if the message has been classified as SPAM by your email provider
