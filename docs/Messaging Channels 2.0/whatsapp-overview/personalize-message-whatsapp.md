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

You can personalize the WhatsApp title and message body for every user based on specific user property or event property values. For more information on user profile properties and events (dynamic replacements), refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [Events](doc:events).


## Message Personalization

To invoke the personalization menu, type the @ symbol in the title or the text fields while creating the WhatsApp notification message.

You can also add dynamic replacements in the WhatsApp title and body. Notice a preview of the available WhatsApp notification as displayed below.


# Personalization Setup

You can personalize messages by clicking the gear icon in the editor to open personalization options. 

# Recommendations

After you have uploaded a catalog, you can display personalized recommendations to your customers. Imagine having a rolling carousel displayed to your customers based on their personal likes!  For more information on recommendations, see [Recommendations](doc:recommendations).

# Constant event property  

Engage the user on multiple actions and inactions. For example, person A added to cart white coat and person B added to cart blue jeans, but they both did not purchase the items. 

You can create a campaign for each product added to the cart or you can use a *constant event property* to personalize the campaign to each user that did not purchase the item. 

For example, you can map the *prod_name* property of the *charged* event to the *product_name* property of the *added to cart* event. You can then hold this property constant across both events. Based on this property, you can now personalize the message received by each user. Imagine having to create a campaign for each product added to the cart instead.  For more information on using a constant event property, see [Constant Event Property](doc:constant-property).