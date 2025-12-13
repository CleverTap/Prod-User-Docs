---
title: Define a Journey
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

You can connect the Segment, Engagement, and Controller blocks from the Journey canvas to define how your users must move through the Journey. 

# Create a Journey

The first step is to define your target users. Drag the *Segment* block from the palette to the canvas. 

![1218](https://files.readme.io/ed8b403-Journeys_define_entry_node_drag.gif "Journeys_define_entry_node_drag.gif")

Click the Segment node to define the qualifying criteria for your users. Define your qualifying criteria and click **Continue**.\
View the details and **Save & Close**.

<Image title="Journeys_define_entry_node.png" alt={775} className="border" width="80%" border={true} src="https://files.readme.io/46d331f-Journeys_define_entry_node.png" />

 Next, decide the type of engagement to send to the qualified users. 

![1216](https://files.readme.io/aae50d7-Journeys_define_engagement_node_drag.gif "Journeys_define_engagement_node_drag.gif")

<Image title="Journeys_define_engagment_node.png" alt={784} className="border" width="80%" border={true} src="https://files.readme.io/5e9f457-Journeys_define_engagment_node.png" />

Add more nodes to plan for scenarios where the user does or does not respond. For example,e you want to send an additional nudge if the user does not buy a product or a thank you note if the user does purchase the product. You can decide the level of details for your Journey. 

> 🚧 Note
>
> You can apply campaign limits in a Journey. However, global throttling is not supported in Journeys.

# Connections

Drag and drop blocks from the palette to the canvas to create connections. 

## Connect Segment & Engage Blocks

Once you have defined a segment of users, you can choose to communicate with the segment by dragging and dropping a channel of communication from the palette on the right-hand side. This communication could go to users who match the segment criteria specified by you, or to the rest of the users i.e. the users who don’t match your segment criteria.

> 📘 Tip on Duplicating Segments
>
> To duplicate a specific segment, use the copy/paste function by hovering over a segment, then perform the following:
>
> * MacOS: Alt + mouse click 
> * Windows: Ctrl + mouse click

<Image title="Journeys_Connect_Segment_Engage_Blocks.png" alt={1051} className="border" border={true} src="https://files.readme.io/7a32f70-Journeys_Connect_Segment_Engage_Blocks.png" />

## Connect Engage & Segment Blocks\*\*

After a user receives a message, you can add a segment after that to ensure that only users who meet the criteria specified by you are taken further in the Journey. 

Example: After users receive a push notification, wait for 1 day, check if users have transacted, for the people that have transacted, send them down path A, and for those who haven’t send them down path B.

<Image title="Journey_Connect_Engage_Segment_Blocks.png" alt={973} className="border" border={true} src="https://files.readme.io/37b12e3-Journey_Connect_Engage_Segment_Blocks.png" />

## Connect Engage & Engage Blocks

After a user receives a message, you can follow it up immediately, or with a delay with another message on a channel of communication of your choosing. 

Example: After a user receives a push notification, you can wait for 3 days, and send another push notification.

<Image title="Journeys_Connect_Engage_Engage_Blocks.png" alt={905} className="border" border={true} src="https://files.readme.io/ee6bb98-Journeys_Connect_Engage_Engage_Blocks.png" />

## Connect Segment & Segment Blocks

After a user has been segmented, you can follow it up with another segment to further refine your Journey. 

Example: If someone has not transacted in the last 30 days, send users who qualify for this segment down path A and if one of these users adds an item to their cart, and doesn’t buy within 15 mins, send them down a specific path.

<Image title="Journeys_Connect_Segment_Segment_Blocks.png" alt={999} className="border" border={true} src="https://files.readme.io/430bb85-Journeys_Connect_Segment_Segment_Blocks.png" />
