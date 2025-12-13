---
title: Conversations
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
Consumers across the globe are increasingly shifting from phone calls, emails, and social media platforms to real-time messaging apps. They’re turning to WhatsApp, Facebook Messenger, Telegram, and other local apps to connect with family, friends, and colleagues. A similar experience is expected from brands - that they **talk** to their users in real-time rather than waiting for responses from agents in call centres or passively communicating over emails.

**Conversations is currently available in public beta.**
[block:api-header]
{
  "title": "Use cases"
}
[/block]
Engaging your end users with chat based conversations has a huge impact on your business metrics.
[block:parameters]
{
  "data": {
    "h-0": "Example Industry",
    "h-1": "Use cases",
    "h-2": "Impacted metric",
    "0-0": "Travel & hospitality",
    "0-1": "* Transactional messages like bookings, refunds, cancellations \n* Reminders for upcoming flights, gate information on silent airports\n* Custom discounts to book a return flight\n* Recommendations about hotels for an upcoming stay",
    "0-2": "Increased customer satisfaction",
    "1-0": "Food Delivery",
    "1-1": "* Food delivery status, including information on driver and ETA\n* Thank you messages after order delivery\n* Custom discounts/refunds in case of a late/wrong delivery",
    "1-2": "Increased user engagement",
    "2-0": "Streaming Media/OTT",
    "2-1": "* Recommendations for new shows/movies/upcoming matches \n* Premium service options when a user finishes a movie/episode",
    "2-2": "Increased user engagement"
  },
  "cols": 3,
  "rows": 3
}
[/block]

[block:api-header]
{
  "title": "Role based access for Conversations: Agent Role"
}
[/block]
CleverTap has a system role of **Agent** which allows dashboard users to access Conversations. Apart from Agent, an admin can also access Conversations. You can have multiple agents Conversations dashboard.
[block:callout]
{
  "type": "info",
  "title": "Agent Role",
  "body": "Agent role is a system role along with Admin, Member, Creator and Approver. A user who is allocated an Agent role will be able to access Conversations."
}
[/block]
To assign an Agent role to a dashboard user, you can go to Account->Settings->Users page. Once there, pick a user to whom you want to assign Agent role. For more details on user role management, please check out [Role Based Access Control](doc:role-based-access-control)  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4708d74-Screenshot_2019-06-17_at_8.51.59_AM.png",
        "Screenshot 2019-06-17 at 8.51.59 AM.png",
        1436,
        746,
        "#909091"
      ],
      "caption": "Assigning an agent role to a dashboard user"
    }
  ]
}
[/block]
If you are an authenticated user (Role = admin or agent), you can access conversations by clicking on **Conversations** from the left navigation bar. 
[block:callout]
{
  "type": "warning",
  "title": "What happens when more than one agent tries to chat with the same user?",
  "body": "It might so happen 2 or more agents click on the same conversation. In such cases, only the first agent can chat with the user and the agents who clicked later will not be able to chat."
}
[/block]
The Conversations dashboard looks like the following:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce8c561-Screenshot_2019-06-06_at_4.46.00_PM.png",
        "Screenshot 2019-06-06 at 4.46.00 PM.png",
        1436,
        727,
        "#dfdfe4"
      ],
      "caption": "Conversations dashboard"
    }
  ]
}
[/block]
You will see a list of conversations when you arrive on the dashboard. These conversations appear when your end users reply on one of your campaigns.

You can click on one of the messages to open the chat window. The chat window is the panel that appears on the right where you can chat with your users seamlessly.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6bafdd0-Screenshot_2019-06-17_at_9.04.25_AM.png",
        "Screenshot 2019-06-17 at 9.04.25 AM.png",
        360,
        590,
        "#eaeef0"
      ],
      "caption": "Active chat window in Conversations"
    }
  ]
}
[/block]
Unlike [WhatsApp](doc:whatsapp) campaigns, where you had to use a templated messages, Conversations allows you to use free form messages.
[block:api-header]
{
  "title": "Converting user queries into customer support tickets"
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Customer support ticketing",
  "body": "CleverTap provides putting a 'ticket' status to on-going chats with your end-users. This helps in categorising and later searching based on resolution status of your customer's queries."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a2ef691-Screenshot_2019-06-17_at_9.18.23_AM.png",
        "Screenshot 2019-06-17 at 9.18.23 AM.png",
        1207,
        600,
        "#f8f7f8"
      ],
      "caption": "Ticketing in Conversations"
    }
  ]
}
[/block]

There the 3 ticket statuses that can be assigned:
**1. New:** As soon as a user replies on a campaign message, it is marked as New. This is irrespective of the previous ticket status with that user.
**2. Pending:** You can mark a query as pending if you think you will come back with a resolution to it later.
**3. Closed:** You can close a query as soon as you resolve it.

However, it's upto you (the Agent) to mark the tickets as you deem fit.

Please note that **ticket status** is similar to a system profile property and hence, it is also queryable on the dashboard.

## **How to assign a ticket to a conversation?** 
Assigning a ticket to a Conversation is fairly simple. If you click on a conversation, and close it, a pop-up appears asking you to assign a ticket before closing it. You can update the ticket status here.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b45c27c-Screenshot_2019-06-17_at_9.23.55_AM.png",
        "Screenshot 2019-06-17 at 9.23.55 AM.png",
        1227,
        604,
        "#cfd0d2"
      ],
      "caption": "Click on the 'X' on chat window and you will see this popup to update the ticket status."
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Active and Inactive conversations"
}
[/block]
A conversation is marked active when an end user has replied to any campaign message. It will show up in the active tab, The active conversation remains so for 24 hours until the last replied message.

Inactive conversations are those whose 24-hour window has been over. They will appear inside the Inactive tab. 

Note: The max limit for inactive conversations to appear in the inactive tab is 15 days.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae4344f-Screenshot_2019-06-06_at_4.50.30_PM.png",
        "Screenshot 2019-06-06 at 4.50.30 PM.png",
        660,
        212,
        "#f8f5f7"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Searching and sorting Conversations"
}
[/block]
If you have millions of conversations going CleverTap provides an easy way to search your conversations by clicking on the Search bar on top of the Conversations dashboard. The following filters are available:
1. Search bar - filters on user name, latest message text
2. Campaign - filters based on campaign names
3. Label - filters based on campaign labels
4. Ticket status - filters based on ticket status