---
title: Copy of User Flow in Journeys
excerpt: Understand how to nudge users to perform the desired action.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Overview

Your users perform one action in a Journey and then move on to the next action. However, there may be instances when they do not move forward in the Journey if not handled correctly.\
We will walk through various combinations to ensure all users' participation in journeys.

## Users Waiting at Segment Node

In scenarios where the next node in a Journey is a Segment Node, the Users will wait till they qualify for the node or exit via Journey Timeouts or Goals.\
For instance, you have shown the Users a Welcome message In-app and are now waiting for them to qualify for the next Segment Node, *Redeem Offer*. In this case, you’d want to set a time limit based on which the users should move down a different path if they don’t qualify for the Segment. This will allow you to nudge the Users to Redeem their offer in this example, and then they can join the main journey again.

<Image title="Users waiting at Segment node to qualify for the Journey" alt={456} align="center" width="90% " border={true} src="https://files.readme.io/662237f-Journeys_Segment_Waiting_Users_Blink.png">
  Users Waiting at Segment Node
</Image>

### Set the Qualifying Window

Click the **hexagon**![hexagon](https://files.readme.io/a7efd36-Hexagon.png) on the *Segment* node to set the qualifying window for the users. 

> 🚧
>
> The qualifying window must be set up in combination with the drawing of the Node Timeout connector. The users will not move if the *Node Timeout* is not connected to another node.

<Image title="Set the qualifying window for the Journey" alt={1440} align="center" width="90% " border={true} src="https://files.readme.io/aeabc0d-Qualifying_Window.gif">
  Set Qualifying Window
</Image>

### Connect to Another Node

Connect the *Node Timeout* connector to another node. After the qualifying window is complete, the user automatically moves to the next node through this timeout connector.

<Image title="Connect the node timeout connector to another node" alt={838} align="center" width="90% " border={true} src="https://files.readme.io/27822b5-Node_Timeout.gif">
  Node Timeout Connector
</Image>

> 📘 Note
>
> The yellow indicator on your segment node is a reminder that you may need to plan for *Waiting* *users* on this node in the Journey.

## Users Waiting at Engage Node

There may be another instance where the users have received a message but they may still wait for action. If the users do not click the message, then they are waiting for the next action.  It means that when you created the Journey, the node following the Engage node is connected with a *Viewed* or *Clicked* connector. When you draw a *Viewed* or *Clicked* connector, a *Phantom* node with a node timeout will appear automatically. You can set the qualifying window from this *Phantom* node to move the users further.

<Image title="Phantom node with a node timeout" alt={1438} align="center" width="90% " border={true} src="https://files.readme.io/f676ab4-User_Waiting_at_Engage_Node.gif">
  Users Waiting at Engage Node
</Image>