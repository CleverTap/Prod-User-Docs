---
title: SendGrid
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
CleverTap supports sending emails through SendGrid. 

# Step 1: Integrate SendGrid with CleverTap
  * In the dashboard, navigate to Settings and click on Integrate Email.
  * Select SendGrid.
  * In the Host text box, fill the host value as smtp.sendgrid.net.
  * In the Port text box, fill Port value as 587.
  * Fill in the Username value as your SendGrid username.
  * Password value is the same as your SendGrid account login password.
  * From Address – this value is used as the sender email address. Most people will not open an email unless they recognize the sender.
  * Save your settings.
  * Finally, click Send a test email and fill in your details to test the configuration details you entered. Has it arrived in your inbox? If not, see troubleshooting steps below.

# Step 2: Bounces, Rejections, and Unsubscriptions

When an email is classified as bounced, rejected or when a user unsubscribes, CleverTap needs to be notified so that no further deliveries to that mailbox are attempted. This is considered a good practice and helps improve your sender reputation. Good sender reputation virtually guarantees better delivery rates.

To enable support for bounce processing, follow the steps below:
  * Navigate to Mail Settings and enable Event Notification.
  * Go to Settings from within Event Notification.
  * In the HTTP Post URL input box, add the Callback URL, as shown in the image below.
  * Check the following from the Select Options menu – Dropped, Bounced, and Unsubscribed From.
  * Save your settings.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/339f1a2-email1.png",
        "email1.png",
        863,
        1103,
        "#f4f5f7"
      ],
      "border": true
    }
  ]
}
[/block]
**Notes**
  * When an email bounces, drops or unsubscribes, CleverTap will mark the user’s email address as inactive.
  * The count of email bounces is shown on the email report screen.

# Step 3: Troubleshooting
Check your SPAM folder to see if the message has been classified as SPAM by your email provider.