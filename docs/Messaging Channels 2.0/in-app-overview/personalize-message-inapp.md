---
title: Personalize Message
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

You can personalize the push notification title and message body for every user based on specific user property or event property values. For more information on user profile properties and events (dynamic replacements), refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [Events](doc:events).

## Message Personalization

To invoke the personalization menu, type the @ symbol in the title or the text fields while creating the push notification message.

You can include emojis in your push notifications as you would in a regular text. You can use the CleverTap emoji picker or copy-paste emojis from an emoji keyboard online.

You can also add dynamic replacements in the push title and body. Notice a preview of the available push notification as displayed below.

<Image title="campaign_push_personalization.png" alt={1095} className="border" border={true} src="https://files.readme.io/281aede-campaign_push_personalization.png" />

You can add emojis using CleverTap’s built-in emoji picker by clicking on the smiley face icon.

# Personalization Setup

You can personalize messages by clicking the gear icon in the editor to open personalization options. 

# Recommendations

After you have uploaded a catalog, you can display personalized recommendations to your customers. Imagine having a rolling carousel displayed to your customers based on their personal likes!  For more information on recommendations, see [Recommendations](doc:recommendations).

# Constant event property

Engage the user on multiple actions and inactions. For example, person A added to cart white coat and person B added to cart blue jeans, but they both did not purchase the items. 

You can create a campaign for each product added to the cart or you can use a *constant event property* to personalize the campaign to each user that did not purchase the item. 

For example, you can map the *prod\_name* property of the *charged* event to the *product\_name* property of the *added to cart* event. You can then hold this property constant across both events. Based on this property, you can now personalize the message received by each user. Imagine having to create a campaign for each product added to the cart instead.  For more information on using a constant event property, see [Constant Event Property](doc:constant-property).
