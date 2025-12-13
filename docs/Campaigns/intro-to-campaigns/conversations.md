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
[block:api-header]
{
  "title": "Overview"
}
[/block]

Consumers across the globe are increasingly shifting from phone calls, emails, and social media platforms to real-time messaging apps. They are turning to WhatsApp, Facebook Messenger, Telegram, and other local apps to connect with family, friends, and colleagues. A similar experience is expected from brands to communicate with their users in real-time rather than waiting for responses from agents in call centers or passively communicating over emails.

[block:api-header]
{
  "title": "Use Cases"
}
[/block]
Engaging your end-users with chat-based conversations has a huge impact on your business metrics. The following table demonstrates some use cases:
[block:parameters]
{
  "data": {
    "h-0": "Example Industry",
    "h-1": "Use Cases",
    "h-2": "Impacted metric",
    "0-0": "Travel and Hospitality",
    "0-1": "* Transactional messages like bookings, refunds, cancelations \n* Reminders for upcoming flights or gate information on silent airports",
    "0-2": "Increased customer satisfaction",
    "1-0": "Food Delivery",
    "1-1": "* Food delivery status, including information on driver and ETA\n* Thank you messages after order delivery",
    "1-2": "Increased user engagement",
    "2-0": "Streaming Media/OTT",
    "2-1": "* Premium service options when a user finishes a movie/episode",
    "2-2": "Increased user engagement"
  },
  "cols": 2,
  "rows": 3
}
[/block]
#Auto Responders
You can have a set of auto-responses to answer customer queries which can help relieve your agents and also significantly reduce the response time for the customer.  

##Set Up FAQs
You can add an FAQ from the *Autoresponders* page or upload a CSV file with multiple FAQs. To do so, perform the following steps:
  1. From the dashboard, navigate to *Conversations* > *Setup* > *Autoresponders*.
  2. Click the **Create** or **Edit** button on the FAQs section to add FAQs. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58b15ef-1x_Autoresponders_dashboard.png",
        "1x Autoresponders dashboard.png",
        1403,
        604,
        "#fafbfc"
      ]
    }
  ]
}
[/block]
  3. Click the **+ FAQ** button to add FAQs. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3216aaf-1x_Plus_FAQ.png",
        "1x Plus FAQ.png",
        1403,
        450,
        "#f9f9fb"
      ]
    }
  ]
}
[/block]
The *Create an FAQ* window displays. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c30a510-Conversations_FAQs_create.png",
        "Conversations_FAQs_create.png",
        871,
        690,
        "#f9fafb"
      ]
    }
  ]
}
[/block]
4.  Create a new FAQ or select *Upload CSV* to upload a CSV file. Download the sample CSV to view the format for uploading your FAQs.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c7c841-Conversations_FAQs_upload.png",
        "Conversations_FAQs_upload.png",
        731,
        283,
        "#f8f9fc"
      ]
    }
  ]
}
[/block]
5. Click the **Test FAQ** link to test your FAQs. It shows the specified response when you enter a keyword.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/218c5da-1_Test_FAQ.png",
        "1 Test FAQ.png",
        1187,
        706,
        "#f5f6f8"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "View Matched and FAQ Links",
  "body": "The *View Matched* link displays only for a saved FAQ. Clicking the FAQ link shows you the expected answer and the mapped FAQ."
}
[/block]

###Test FAQ
When you test a response, you can see the matching FAQ for it. To test response for a saved FAQ, follow the steps:

1. From the dashboard, navigate to *Conversations* > *Autoresponders*. 
2. Click the *Test FAQ* link. The *Test FAQs* window displays.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba417be-1x_Plus_FAQ.png",
        "1x Plus FAQ.png",
        1403,
        450,
        "#f9f9fb"
      ]
    }
  ]
}
[/block]
3. Enter a string to test the response. The response displays a link to the matching FAQ. 
4. Click the **View matched** link to view the FAQ that best matches the response. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e8f9bf6-2_View_matched.png",
        "2 View matched.png",
        1411,
        801,
        "#f6f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
###Edit or Archive FAQs
To view the FAQ list, perform the following steps:
 1. From the dashboard, navigate to *Conversations* > *Setup* > *Autoresponders*. 
 2. Click the **Edit** button on FAQs section to view FAQs.
3. View, edit, clone, or archive FAQs. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5ebaa4-3_Edit_or_Archive_FAQ.png",
        "3 Edit or Archive FAQ.png",
        1400,
        461,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
###FAQ Types
You can create four types of FAQs to help distinguish your FAQs, such as:
  * Greetings: Add a greeting such as hi, hello, good morning, and so on.
  * General: Any conversation which is specific to your business need.
  * Closing: Add an end to the conversation. For example, "Thank you for contacting us. Have a good day."
  * Filler: Add a filler in the conversation. For example, "Please wait while I fetch your information."
[block:callout]
{
  "type": "info",
  "title": "Adding a Question to an FAQ",
  "body": "When setting up an autoresponder, it is mandatory to add at least one question to the FAQ. Our NLP model (on which the responder is built) ensures that if similar questions are asked by your users, the autoresponder responds with the right answer."
}
[/block]
##Set Up a Quick Reply
A quick reply can help you set the context for a conversation, generally during your non-business hours. To create quick replies, perform the following steps:
1. From the dashboard, navigate to *Conversations* > *Setup* > *Autoresponders*. 
2. Click the **Edit** button on the *Quick Reply* section to add quick replies. The Quick Reply page displays. 
3. Create a quick reply and select the time period when the *Quick Reply* must be active.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5db99c2-Conversations_Quick_reply_create.png",
        "Conversations_Quick_reply_create.png",
        730,
        588,
        "#f8f9fb"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
##Prioritize

You can prioritize FAQs over quick replies and vice versa. To prioritize autoresponders, perform the following steps:

1. From the dashboard, navigate to *Conversations* > *Setup* > *Autoresponders*. 
2. Select *FAQs* and *Quick Reply* from the list. The priority is set by the order of selection.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f3420e6-3x_prioritize.png",
        "3x prioritize.png",
        1401,
        671,
        "#fafafb"
      ]
    }
  ]
}
[/block]
3. Click **Save**.

##Autoresponder Flow
The following image shows the flow of the autoresponder:


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f85a76-Conversations_Autoresponder_Flow.png",
        "Conversations_Autoresponder_Flow.png",
        6407,
        6237,
        "#fbfdfc"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "This flow assumes that the FAQ responder is configured first in the *Responders chain* section.",
  "title": "FAQ Responder Configuration"
}
[/block]
##FAQ Best Practices

This section covers FAQ best practices, including:

1. Check that the questions are detailed and clear. Always use complete and meaningful sentences. 
Example:
  * Correct: How can I recover the password of my account? 
  * Incorrect: Wrong password.
  
2. Add enough context to a question. Check that the answer contains all the relevant information for the user. 
Example:
  * Correct: How can I return my order?
  * Incorrect: How to return?

3. Avoid having questions that have less than five words, however, it is okay to have short responses for closing, fillers, or greeting. 
Example:
  * Correct: Do you have COD as a payment option?
  * Incorrect: COD please. 

4. Check that the FAQ sets are contextually exclusive from each other. 

5. Try to add related questions in the same FAQ to provide more context. The responder model can handle spelling errors as long as they do not affect the meaning of the sentence. Context and flow are more important than simple spelling errors or grammatical variations.

On the other hand, acronyms and lingos must be added in related questions separately. 
Example FAQ: Do you have cash on delivery as a payment option?

Related example questions:
  * Do you have COD as a payment method?
  * Can I pay after the delivery is completed?

6. The responder works best for the English language. Use of any other language for adding FAQs. For example, writing Hindi using Roman/Latin script may result in unpredictable performance. 

[block:api-header]
{
  "title": "Role Based Access: Agent Role"
}
[/block]
CleverTap has a system role of agents which gives the capability to dashboard users to access conversations. Apart from an agent, an admin can also access conversations. You can have multiple agents in the conversations dashboard.
[block:callout]
{
  "type": "info",
  "title": "Agent Role",
  "body": "Agent role is a system role along with an admin, a member, a creator, and an approver. A user who is allocated an agent role will be able to access conversations."
}
[/block]
To assign an agent role to a dashboard user, perform the following steps:
1. From the dashboard, navigate to *Account* > *Settings* > *Users*. 
2. Select a user to assign an *Agent* role. 

For more details on user role management, refer to [Role Based Access Control](doc:role-based-access-control).  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/48ae0b9-4_Assign_agent.png",
        "4 Assign agent.png",
        1403,
        558,
        "#f8f9fa"
      ],
      "caption": ""
    }
  ]
}
[/block]
If you are an authenticated user (Role = Admin or Agent), you can access conversations by clicking on *Conversations* from the left navigation bar. 
[block:callout]
{
  "type": "warning",
  "title": "One Agent per Conversation",
  "body": "It might happen that two or more agents click on the same conversation. In such cases, only the first agent can chat with the user and the agents who clicked later will not be able to chat."
}
[/block]
The *Conversations* dashboard looks like the following:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/78261b5-5_Conversations_dashboard.png",
        "5 Conversations dashboard.png",
        1414,
        483,
        "#f9f9fa"
      ],
      "caption": ""
    }
  ]
}
[/block]
You see a list of conversations when you arrive on the dashboard. These conversations display when your end-users reply to one of your campaigns.

You can click any of the messages to open the chat window. The chat window is the panel that displays on the right where you can chat with your users seamlessly.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f56f3f1-6_Chat_live.png",
        "6 Chat live.png",
        1418,
        801,
        "#ebf0ee"
      ],
      "caption": "",
      "border": false
    }
  ]
}
[/block]
Unlike [WhatsApp](doc:whatsapp) campaigns where you have to use a templated messages, *Conversations* lets you use free form messages and attach files.
[block:api-header]
{
  "title": "Converting User Queries into Customer Support Tickets"
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Customer Support Ticketing",
  "body": "CleverTap provides putting a ticket status to ongoing chats with your end-users. This helps in categorizing and later searching based on the resolution status of your customer's queries."
}
[/block]
You can assign one of the following five ticket statuses:
  * New: As soon as a user replies to a campaign message, it is marked as *New*. This is irrespective of the previous ticket status with that user.
  * Active: When an agent replies to the user.
  * Pending: When the user replies back to the agent.
  * Resolved: When the agent resolves the conversation.
  * Inactive: These are all conversations that are past the 24-hour conversation. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08ae725-5_Conversations_dashboard.png",
        "5 Conversations dashboard.png",
        1414,
        483,
        "#f9f9fa"
      ],
      "caption": "Ticketing in Conversations",
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The maximum limit for inactive conversations to appear in the inactive tab is 15.",
  "title": "Inactive Conversations"
}
[/block]
Change Status
An agent can move the status from one to the other. As shown in the following table, tickets auto change status based on these criteria:
[block:parameters]
{
  "data": {
    "h-0": "Flow",
    "h-1": "Status",
    "h-2": "Location",
    "0-0": "When user messages you for the first time",
    "0-1": "New",
    "0-2": "All conversations",
    "1-0": "When your agent replies back to the user",
    "1-1": "Active",
    "1-2": "My conversations (for the agent)",
    "2-0": "When user replies back to the agent",
    "2-1": "Pending",
    "2-2": "My conversations (for the agent)",
    "3-0": "When agent resolves the conversation",
    "3-1": "Resolved",
    "3-2": "All conversation",
    "4-0": "When a 24-hour window expires",
    "4-1": "Inactive",
    "4-2": "Inactive conversations"
  },
  "cols": 3,
  "rows": 5
}
[/block]
The ticket status is similar to a system profile property and hence, it is also searchable on the dashboard.

## Update Status Manually 
To assign a ticket to a conversation, perform the following steps:
1. Cick on a conversation and close it. A pop-up displays asking you to assign a ticket before closing it.
2. Select a new ticket status.
3. Click **Assign and close**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb69aec-7_Update_ticket_status.png",
        "7 Update ticket status.png",
        1427,
        800,
        "#c3c5c6"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Search and Sort Conversations"
}
[/block]
If you have millions of conversations going, CleverTap provides an easy way to search your conversations by clicking on the search bar on top of the conversations dashboard. 

The following filters are available:
  * Search bar: Filters on user name, latest message text.
  * Campaign: Filters based on campaign names.
  * Label: Filters based on campaign labels.
  * Ticket status: Filters based on ticket status.