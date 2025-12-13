---
title: Unusually High Email Opens and Clicks
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
A well-designed email campaign can help you get more reach and conversions. However, for a set of campaigns or users (for example, B2B domains) you may sometimes observe unusually high email open and click counts. It can be due to a variety of reasons. 

# Unusually High Opens

Multiple opens means that the recipient opened your email multiple times.  However, there may be instances where the email *opens* exceeds expectation, or *opens* for a recipient are registered multiple times in quick succession. It can be due to the following reasons:

* Email Clients - Many email clients such as (Outlook or Apple Mail) have a preview pane as part of the inbox view. A recipient scrolling over your email in their inbox (even passively), can trigger an email open notification. Industry-wide opens are tracked using images. When an image is displayed, the email is counted as open. This display is controlled by the email client and is not distinguishable from human opens. 

* Email Forwards - The forwarded email is an exact copy of the original email. Forwarded emails can also add to the *open* count.  The open is attributed to the original recipient, even if the email is opened by the recipient of the forwarded email. 

* Virus Scanners - These scanners sometimes preview emails to determine spam. There is no way to distinguish between machine opens and human opens.

* Email Groups - If a user signs up for your service with a group address then all the opens are attributed to a single profile or email address that qualified for the email campaign.

# Unusually High Clicks

* Email Forwards - CleverTap adds unique tracking info to each URL in an email campaign. The forwarded email is an exact copy of the original email. All the clicks are attributed to the original recipient even if the email is clicked by the recipient of the email forward. There is no way to distinguish between the original recipient and the forwarded email recipient.

* Spam Filters - A spam filter may be clicking the links in your emails. Aggressive spam filters click links in emails to check for malicious activity before delivering them to the recipients. Unfortunately, there's no way to see if a link was clicked by a spam filter or your intended recipient. However, if you see an unusually high number of clicks from a single domain, it's likely to be a spam filter.
