---
title: Messaging Frequency Caps
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
# Overview

Frequency caps help you control the number of messages your users receive. 

It’s common to run multiple messaging campaigns simultaneously or in close proximity to one another. The same user may qualify for more than one of these campaigns and be subject to receive several messages in tight succession. 

Alternatively, for a recurring or triggered campaign, the same user may re-qualify for that campaign and again be subject to receiving the same message more than once. Frequency caps enable you to ensure your users don’t receive too many messages. 

In CleverTap, there are two types of frequency caps:
  * **Global Frequency Caps** control the maximum messages a user should get across campaigns for a particular channel of communication.
  * **Message-Level Frequency Caps** define how often messages can go to a particular user for a particular campaign.

When a frequency cap applies to a user, CleverTap will not deliver the associated message. The dropped messages will be accounted for in the Campaign Report error table.

# Global Frequency Caps
Global Frequency Caps operate on a per-channel basis and allow you to specify message cadence, dwell time between messages, and throttle limits (rates of delivery).

## Max Messages Per Channel

You can define the maximum number of messages a user should get for a specific channel of communication across campaigns.

**Example**
You can define a cadence of 3 push notification in 7 days. This will ensure that users get only 3 push messages in 7 days. 
 
## Dwell Time Between Messages
For a channel of communication, you can define the minimum time gap that should be maintained for messages, across campaigns. 

Example: There should be a minimum gap of at least 4 hours between messages.

Range:
  * Minimum gap - 5 mins
  * Maximum gap - 7 days


## Throttle
You can control the rate at which notifications are sent out of CleverTap. The control rate is defined as the number of messages every 5 mins.

**Example**
Send no more than 15000 messages every 5 mins. This will throttle the rate at which all campaigns go out.

Throttle limits are typically applicable to large, one-time campaigns. For example, if you intend to send message out to your entire base or a large subset of your base, and you include a call to action that takes the form of a link in the message, when you users receive the message and click they will be directed to the call to action resource you included. Depending on the size of your campaign, you may wish to set a throttle limit to ensure that your notifications are not all delivered at once such that a large number of users are not simultaneously being directed to the same resource.

# Message-Level Frequency Caps

Message-Level Caps enable you to control the number of times a particular ongoing campaign is delivered to the same user. 
[block:callout]
{
  "type": "warning",
  "body": "Message-level and Global frequency caps work together when applied simultaneously. A user may be subject to either or both frequency cap limits."
}
[/block]
These caps are important for recurring campaigns or triggered campaigns where the same user may re-qualify multiple time to receive a message.

**Control Options**
  * Send every time the user qualifies (default): This will send a message every time the user qualifies (can choose to respect global caps).
  * Send with a minimum gap of: This will allow you to set a minimum gap between subsequent messages. The minimum gap allowed is 5 minutes and the maximum allowed is 30 days.