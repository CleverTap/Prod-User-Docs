---
title: Managing Users
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

Your users perform one action in a Journey and then move on to the next action. However, there may be instances when they do not move forward in the Journey. 

## Users Waiting at Segment node

There may be users waiting at the Segment node. For example, users may add a product to the cart but do not buy it. They may have changed their decision or maybe they simply forgot about it. These users are waiting in the Journey until they perform the next action. You must be able to nudge them to perform the next action and continue the Journey. 

<Image title="Journeys_Segment_Waiting_Users_Blink.png" alt={456} border={true} src="https://files.readme.io/662237f-Journeys_Segment_Waiting_Users_Blink.png">
  Segment node
</Image>

You can send these users on a different path or exit them from the Journey completely. 

Plan for these users in advance. To send them on a different path, set the qualifying period and then send them to the following node to continue their Journey. 

### Set the qualifying window

Click the hexagon on the *Segment* node to set the qualifying window for the users. 

> 🚧 The qualifying window must be set up in combination with the drawing of the Node Timeout connector. The users will not move if the *Node Timeout* is not connected to another node.

<Image title="Journeys_Segment_timeout.gif" alt={1226} border={true} src="https://files.readme.io/6ae12e0-Journeys_Segment_timeout.gif">
  Node timeout
</Image>

### Connect to another node

Connect the *Node Timeout* connector to another node. After the qualifying window is complete, the user automatically moves on to the next node through this timeout connector. For understanding the node timeout evaluation schedule, refer to \<\<@sunil to add cross-reference>>

<Image title="Journey_Connect_Node_timeout.gif" alt={1238} border={true} src="https://files.readme.io/6e3878f-Journey_Connect_Node_timeout.gif">
  Connect Node
</Image>

> 📘 Note
>
> The yellow indicator on your segment node is a reminder that you may need to plan for *Waiting* *users* on this node in the Journey.

## Users waiting at Engage node

There may be another instance where the users have received a message but they may still wait for action. If the users do not click the message, then they are waiting for the next action.  It means that when you created the Journey, the node following the Engage node is connected with a *Viewed* or *Clicked* connector.  However, we have you covered! When you draw a  *Viewed* or *Clicked* connector, a *Phantom* node with a node timeout will appear automatically. You can set the qualifying window from this *Phantom* node to move the users further.

<Image title="Journeys_pseudo_node.gif" alt={1238} border={true} src="https://files.readme.io/7d174d7-Journeys_pseudo_node.gif">
  Phantom Node
</Image>

## Force exit users

You can use the *Force exit* operator node to create an exit for users in the Journey. For example,  if you want the users to exit and re-enter the current Journey you can set up this node.  Drag the Force exit node from the *Operator Node* pane and connect it to the *Segment* node.

<Image title="Journey_Segment_timeout_Force_exit.gif" alt={1240} border={true} src="https://files.readme.io/2335591-Journey_Segment_timeout_Force_exit.gif">
  Force exit
</Image>

## Update Profile Property

You may need to update your user's profiles based on some milestones. These milestones can be based on actions such as money spent, or time spent such as six months of active use, or a combination of both. For example, a ride-hailing app can update a user to platinum after 10 rides. 

To update a profile property within a Journey, drag a controller node called *User profile update* in the Journey. 

![1191](https://files.readme.io/31d6eef-Journeys_profile_property_node.png "Journeys_profile_property_node.png")

Update the profile property with the required values. You can perform the following actions:

* Set to - You can set a property value. For example, set the customer type property to Platinum. 
* Add to array - Add a value to a list. For example, if a user marks a Gotham as a favorite, add it as a profile property to the  *Favourite Shows* array. 
* Remove from array - Remove a value from a list. For example, remove a profile property called Gotham from the  *Favourite Shows* array.
* Increment - Increment an integer value. For example, increment the *Ride count* profile property whenever a user takes a ride. You can use it to track the number of rides taken by the user, in real-time. 
* Decrement - Reduce an integer value. For example, you can decrement the *Free Trials Count* property for every time a user takes a trial. 

<Image title="Journeys_node_user_profile_update.png" alt={768} className="border" border={true} src="https://files.readme.io/9f31c02-Journeys_node_user_profile_update.png" />
