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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed8b403-Journeys_define_entry_node_drag.gif",
        "Journeys_define_entry_node_drag.gif",
        1218,
        536,
        "#f3f7fa"
      ]
    }
  ]
}
[/block]
Click the Segment node to define the qualifying criteria for your users. Define your qualifying criteria and click **Continue**. 
View the details and **Save & Close**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46d331f-Journeys_define_entry_node.png",
        "Journeys_define_entry_node.png",
        775,
        1424,
        "#f8f9fc"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
 Next, decide the type of engagement to send to the qualified users. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aae50d7-Journeys_define_engagement_node_drag.gif",
        "Journeys_define_engagement_node_drag.gif",
        1216,
        623,
        "#f4f5f6"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e9f457-Journeys_define_engagment_node.png",
        "Journeys_define_engagment_node.png",
        784,
        1826,
        "#ecedf0"
      ],
      "sizing": "80",
      "border": true
    }
  ]
}
[/block]
Add more nodes to plan for scenarios where the user does or does not respond. For example,e you want to send an additional nudge if the user does not buy a product or a thank you note if the user does purchase the product. You can decide the level of details for your Journey. 
[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "You can apply campaign limits in a Journey. However, global throttling is not supported in Journeys."
}
[/block]



# Connections 

Drag and drop blocks from the palette to the canvas to create connections. 

## Connect Segment & Engage Blocks
Once you have defined a segment of users, you can choose to communicate with the segment by dragging and dropping a channel of communication from the palette on the right-hand side. This communication could go to users who match the segment criteria specified by you, or to the rest of the users i.e. the users who don’t match your segment criteria.
[block:callout]
{
  "type": "info",
  "title": "Tip on Duplicating Segments",
  "body": "To duplicate a specific segment, use the copy/paste function by hovering over a segment, then perform the following:\n* MacOS: Alt + mouse click \n* Windows: Ctrl + mouse click"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a32f70-Journeys_Connect_Segment_Engage_Blocks.png",
        "Journeys_Connect_Segment_Engage_Blocks.png",
        1051,
        248,
        "#edf2ee"
      ],
      "border": true
    }
  ]
}
[/block]
## Connect Engage & Segment Blocks**
After a user receives a message, you can add a segment after that to ensure that only users who meet the criteria specified by you are taken further in the Journey. 

Example: After users receive a push notification, wait for 1 day, check if users have transacted, for the people that have transacted, send them down path A, and for those who haven’t send them down path B.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37b12e3-Journey_Connect_Engage_Segment_Blocks.png",
        "Journey_Connect_Engage_Segment_Blocks.png",
        973,
        388,
        "#ecf4f3"
      ],
      "border": true
    }
  ]
}
[/block]
## Connect Engage & Engage Blocks
After a user receives a message, you can follow it up immediately, or with a delay with another message on a channel of communication of your choosing. 

Example: After a user receives a push notification, you can wait for 3 days, and send another push notification.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee6bb98-Journeys_Connect_Engage_Engage_Blocks.png",
        "Journeys_Connect_Engage_Engage_Blocks.png",
        905,
        312,
        "#e2f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Connect Segment & Segment Blocks
After a user has been segmented, you can follow it up with another segment to further refine your Journey. 

Example: If someone has not transacted in the last 30 days, send users who qualify for this segment down path A and if one of these users adds an item to their cart, and doesn’t buy within 15 mins, send them down a specific path.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/430bb85-Journeys_Connect_Segment_Segment_Blocks.png",
        "Journeys_Connect_Segment_Segment_Blocks.png",
        999,
        431,
        "#f9f7f4"
      ],
      "border": true
    }
  ]
}
[/block]