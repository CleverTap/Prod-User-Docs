---
title: Amazon Simple Email Service
excerpt: Learn how to integrate Amazon SES as an Email provider on CleverTap.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
CleverTap supports sending emails through *Amazon SES*.

# Integrating Amazon SES with CleverTap

To integrate Amazon SES with CleverTap, follow the steps below:

1. From the CleverTap dashboard, navigate to *Settings* > *Channels*> Email
2. Click **+Provider**
3. Select *Amazon SES* from the provider dropdown.

<Image align="center" className="border" border={true} src="https://files.readme.io/bb0eaed-small-Amazon_SES.png" />

4. Paste the *Server Name* and *Port*  from your Amazon SES account. Navigate to *Amazon SES* > *Dashboard* > *SMTP Settings* to locate these credentials.  

<Image align="center" className="border" border={true} src="https://files.readme.io/234ce8d-small-CleverTap_Amazon_SES_Integration.png" />

5. *Username* and *Password* values should match your SMTP credentials from *Amazon SES*. These are not your AWS account credentials.
6. *From Address* should have one of the values from *Amazon SES* > *Dashboard* > *Verified Senders* > *Email addresses list*. Most people will not open an email unless they recognize the sender. 

<Image align="center" className="border" border={true} src="https://files.readme.io/24dbaf5-small-amazon_ses_.png" />

7. Click **Save**
8. Click **Send a test email** and fill in your details to test the configuration details you entered. If you are not able to successfully test the email, refer to the troubleshooting steps below.

# Enabling Bounce and Complaint Processing

When an email is classified as bounced, CleverTap needs to be notified so that no further deliveries to that mailbox are attempted. This is considered a good practice and helps improve sender reputation.

To enable support for bounce processing, follow the steps below:

1. Navigate to *Amazon SNS*.
2. Create a *Topic*.
3. Select the *Topic* and navigate to *Actions* > *Subscribe to Topic*.
4. Select *HTTPS* as the *Protocol*.
5. As the *Endpoint* value, add the *Callback URL* as shown in your CleverTap *Email* page.

<Image title="Enter email provider credentials to enable bounce and complaint processing." alt={1900} align="center" border={true} src="https://files.readme.io/b7d933a-Callback_URL_v1_CLEVER-4714.png">
  Email Provider Credentials
</Image>

6. Save your settings by clicking on **Create Subscription**.
7. Navigate to *Amazon SES*.
8. Select the *Email Address* you had previously added to the CleverTap Dashboard.
9. Click on *View Details*.
10. Click on *Notifications* > *Edit Configuration*.

<Image title="Configure Amazon SES for email bounces, complaints and deliveries." alt={2862} align="center" border={true} src="https://files.readme.io/e5ae062-AWS_Domains_Notifications__v1_-_CLEVER-4714.png">
  Email Configurations
</Image>

11. Under *SNS Topic Configuration*, select the topics you created earlier such as *Bounces*, *Complaints*, and *Deliveries* by clicking on the **Include original headers** checkboxes.

<Image title="Edit Notification Configuration" alt={2785} align="center" border={true} src="https://files.readme.io/cc1da78-Edit_Notification_Configuration.png">
  Edit Notification Configuration
</Image>

12. Save the configuration.

# Handling Unsubscribe Requests

To handle unsubscribed requests from users, refer to the steps in [Handling Unsubscribes](doc:handling-unsubscribes).

# Troubleshooting

The following explains some troubleshooting scenarios: 

* Sandbox mode: If you’re getting an *Invalid Credentials* message when saving your settings, it could be that your *Amazon SES* account is a sandboxed one. You need a valid production-ready *Amazon SES* account to save your credentials. 
* Spam: Check your *Spam* folder to see if the message has been classified as *Spam* by your email provider.
* Email rendering: If your email does not render properly, check the subject line for newline characters or too many additional spaces. *Amazon SES* email converts data from UTF-8 format to a 7-bit ASCII format before sending it out. The next line characters or additional spaces may interfere with this conversion.

## Dispatch Failed Error

The Dispatch Failed Error occurs in the following situations:

* Email credentials are incorrectly passed, making it impossible to establish a connection with the Email Service Provider.
* When the payload is sent from CleverTap's end to the Email Service Provider, and CleverTaps does not receive a "200 OK" response from their end, resulting in the error.

This error typically happens when the Email Service Provider is unable to handle the concurrent limit with which we make an SMTP connection.

If the selected credentials and configurations are correct, the error may occur due to intermittent unavailability of the service provider, causing the endpoint to be unavailable and resulting in the "SMTP Dispatch Failed" error.\
To resolve this error, we recommend contacting the Email Service Provider for assistance.
