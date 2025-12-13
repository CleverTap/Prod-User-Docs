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
Consumers across the globe are increasingly shifting from phone calls, emails, and social media platforms to real-time messaging apps. They’re turning to WhatsApp, Facebook Messenger, Telegram, and other local apps to connect with family, friends, and colleagues. A similar experience is expected from brands - that they **talk** to their users in real-time rather than waiting for responses from agents in call centers or passively communicating over emails.

## Use cases

Engaging your end users with chat based conversations has a huge impact on your business metrics.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Example Industry
      </th>

      <th>
        Use cases
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Travel & hospitality
      </td>

      <td>
        * Transactional messages like bookings, refunds, cancellations 
        * Reminders for upcoming flights, gate information on silent airports
      </td>
    </tr>

    <tr>
      <td>
        Food Delivery
      </td>

      <td>
        * Food delivery status, including information on driver and ETA
        * Thank you messages after order delivery
      </td>
    </tr>

    <tr>
      <td>
        Streaming Media/OTT
      </td>

      <td>
        * Premium service options when a user finishes a movie/episode
      </td>
    </tr>
  </tbody>
</Table>

# Auto Responders

You can have a set of auto-responses to answer customer queries. These can help unburden your agents and also significantly reduce the response time for the customer.  

## Set up FAQs

You can add an FAQ from the Auto Responders page or upload a CSV file with multiple FAQs. 

1. Go to Conversations > Setup > Autoresponders. The Auto Responders page appears. 
2. Click the Edit button on the FAQs section to add FAQs.  The FAQ page appears. 
3. Click the +FAQ button to add FAQs. The Create an FAQ window appears. 

![871](https://files.readme.io/c30a510-Conversations_FAQs_create.png "Conversations_FAQs_create.png")

4. Create a new FAQ or select Upload CSV to upload a CSV file.  Download the sample CSV to see the format for uploading your FAQs.

![731](https://files.readme.io/2c7c841-Conversations_FAQs_upload.png "Conversations_FAQs_upload.png")

7. Click the Test FAQ link to test your FAQs. It shows the specified response when you enter a keyword.

<Image title="Conversations_FAQs_create_Test.gif" alt={1196} className="border" border={true} src="https://files.readme.io/7c08504-Conversations_FAQs_create_Test.gif" />

> 📘 Note
>
> The View Matched link appears only for a saved FAQ. Clicking the FAQ link shows you the expected answer and the mapped FAQ.

### Test FAQ

When you test a response, you can see the matching FAQ for it.  To test response for a saved FAQ, follow the steps:

1. Click Conversations > Autoresponders > Test FAQ link. The Test FAQs window appears.
2. Enter a string to test the response.  The response appears with a link to the matching FAQ. 
3. Click the View matched link to view the FAQ that best matches the response. 

<Image title="Conversations_FAQs_Test_Existing.gif" alt={1194} className="border" border={true} src="https://files.readme.io/4b1d709-Conversations_FAQs_Test_Existing.gif" />

### Edit or Archive FAQs

To view the FAQ list:

1. Go to Conversations > Setup > Autoresponders. The Auto Responders page appears. 
2. Click the Edit button on FAQs section to view  FAQs.  The FAQs page appears.\
   You can now view, edit, or archive FAQs from this page. 

<Image title="Conversations_FAQs_list_actions.gif" alt={1340} className="border" border={true} src="https://files.readme.io/916f5a6-Conversations_FAQs_list_actions.gif" />

### FAQ Types

There are 4 types of FAQs that you can create. The 'type' tag helps you to distinguish your FAQs accurately

1. Greetings -  Add a greeting such as a hi, hello, good morning, and so on.
2. General - Any conversation which is specific to your business need.
3. Closing - Add an end for the conversation. For example, "Thank you for contacting us. Have a good day".
4. Filler - Add a filler in the conversation. For example, "Please wait while I fetch your information". 

> 📘 Adding a question to an FAQ
>
> When setting up an autoresponder, it is mandatory to add at least 1 question to the FAQ. Our NLP model (on which the responder is built) will ensure that if similar questions are asked by your users, the autoresponder responds with the right answer

## Set up Quick Reply

Quick Reply can help you set the context for a conversation, generally during your non-business hours. To create quick replies:

1. Go to Conversations > Setup > Autoresponders. The Auto Responders page appears. 
2. Click the Edit button on the Quick Reply section to add quick replies.  The Quick Reply page appears. 
3. Create a quick reply and select the time period when the Quick Reply must be active.

<Image title="Conversations_Quick_reply_create.png" alt={730} className="border" width="100%" border={true} src="https://files.readme.io/5db99c2-Conversations_Quick_reply_create.png" />

## Prioritize

You can prioritize FAQs over quick replies and vice versa.\
To prioritize Autoresponders do the following:

1. Go to Conversations > Setup > Autoresponders. The Auto Responders page appears. 
2. From Prioritize auto responders section, select FAQs and Quick Reply from the list. The priority is set by the order of selection.  

## Auto Responder Flow

The following image shows the flow of the autoresponder:

<Image title="Conversations_Autoresponder_Flow.png" alt={6407} className="border" width="100%" border={true} src="https://files.readme.io/0f85a76-Conversations_Autoresponder_Flow.png" />

> 🚧 Note
>
> This flow assumes that the FAQ responder is configured first in the “Responders chain” section.

## FAQ Best Practices

1. Check that the questions are detailed and clearly worded. Always prefer complete and meaningful sentences.\
   Example:

* Correct - How can I recover the password of my account? 
* Incorrect - Wrong Password

2. Add enough context to a question. Check that the answer contains all the relevant information for the user.\
   Example:

* Correct -  How can I return my order?
* Incorrect -  How to return?

3. Avoid having questions that have less than 5 words. However, it is okay to have short responses for closing, fillers, or greeting.\
   Example:

* Correct - Do you have COD as a payment option?
* Incorrect - COD Please 

4. Check that the FAQ sets are contextually exclusive from each other. 

5. Try to add related questions in the same FAQ to provide more context. The responder model can handle spelling errors as long as they do not affect the meaning of the sentence. Context and flow are more important than simple spelling errors or grammatical variations.\
   However, acronyms and lingos must be added in related questions separately.\
   Example:\
   FAQ - Do you have cash on delivery as a payment option?\
   Related Questions:

* Do you have COD as a payment method?
* Can I pay after the delivery is completed?

6. The responder works best for the English language. Use of any other language for adding FAQs (For example, writing Hindi using Roman/Latin script) may result in unpredictable performance. 

## Role Based Access: Agent Role

CleverTap has a system role of **Agent** which allows dashboard users to access Conversations. Apart from Agent, an admin can also access Conversations. You can have multiple agents Conversations dashboard.

> 📘 Agent Role
>
> Agent role is a system role along with Admin, Member, Creator and Approver. A user who is allocated an Agent role will be able to access Conversations.

To assign an Agent role to a dashboard user, you can go to Account->Settings->Users page. Once there, pick a user to whom you want to assign Agent role. For more details on user role management, please check out [Role Based Access Control](doc:role-based-access-control)  

<Image title="Screenshot 2019-06-17 at 8.51.59 AM.png" alt={1436} src="https://files.readme.io/4708d74-Screenshot_2019-06-17_at_8.51.59_AM.png">
  Assigning an agent role to a dashboard user
</Image>

If you are an authenticated user (Role = admin or agent), you can access conversations by clicking on **Conversations** from the left navigation bar. 

> 🚧 What happens when more than one agent tries to chat with the same user?
>
> It might so happen 2 or more agents click on the same conversation. In such cases, only the first agent can chat with the user and the agents who clicked later will not be able to chat.

The Conversations dashboard looks like the following:

<Image title="Conversations_Dashboard.png" alt={1097} src="https://files.readme.io/492b43f-Conversations_Dashboard.png">
  Conversations dashboard
</Image>

You will see a list of conversations when you arrive on the dashboard. These conversations appear when your end users reply to one of your campaigns.

You can click on one of the messages to open the chat window. The chat window is the panel that appears on the right where you can chat with your users seamlessly.

<Image title="Conversations_Whatsapp_Attachment.gif" alt={1198} src="https://files.readme.io/5ab0a24-Conversations_Whatsapp_Attachment.gif">
  Active chat window in Conversations
</Image>

Unlike [WhatsApp](doc:whatsapp) campaigns, where you had to use a templated messages, Conversations allows you to use free form messages and attach files.

## Converting user queries into customer support tickets

> 📘 Customer support ticketing
>
> CleverTap provides putting a 'ticket' status to on-going chats with your end-users. This helps in categorising and later searching based on resolution status of your customer's queries.

<Image title="Conversations_Dashboard_Tickets_View.png" alt={853} width="100%" border={true} src="https://files.readme.io/2e496cf-Conversations_Dashboard_Tickets_View.png">
  Ticketing in Conversations
</Image>

There the 5 ticket statuses that can be assigned:\
**1. New:** As soon as a user replies to a campaign message, it is marked as New. This is irrespective of the previous ticket status with that user.\
**2. Active:** When an agent replies to the user.\
**3. Pending:** When the user replies back to the agent.\
**4. Resolved:** When the agent resolves the conversation.\
**5. Inactive:** These are all conversations that are past the 24-hour conversation.

> 📘 Inactive conversations
>
> Note: The max limit for inactive conversations to appear in the inactive tab is 15 da

Changing status

1. Agent can move the status from one to the other
2. Tickets auto change status based on the below criteria

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Flow
      </th>

      <th>
        Status
      </th>

      <th>
        Location
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        When user messages you for the 1st time
      </td>

      <td>
        New
      </td>

      <td>
        All conversations
      </td>
    </tr>

    <tr>
      <td>
        When your agent replies back to the user
      </td>

      <td>
        Active
      </td>

      <td>
        My conversations (for the agent)
      </td>
    </tr>

    <tr>
      <td>
        When user replies back to the agent
      </td>

      <td>
        Pending
      </td>

      <td>
        My conversations (for the agent)
      </td>
    </tr>

    <tr>
      <td>
        When agent resolves the conversation
      </td>

      <td>
        Resolved
      </td>

      <td>
        All conversation
      </td>
    </tr>

    <tr>
      <td>
        When 24 hour window expires
      </td>

      <td>
        Inactive
      </td>

      <td>
        Inactive conversations
      </td>
    </tr>
  </tbody>
</Table>

Please note that **ticket status** is similar to a system profile property and hence, it is also queryable on the dashboard.

## **Updating status manually**

Assigning a ticket to a Conversation is fairly simple. If you click on a conversation and close it, a pop-up appears asking you to assign a ticket before closing it. You can update the ticket status here.

<Image title="Conversations_Update_Status_Manual.gif" alt={1077} src="https://files.readme.io/52ac75f-Conversations_Update_Status_Manual.gif">
  Click on the 'X' on chat window and you will see this popup to update the ticket status.
</Image>

## Searching and sorting Conversations

If you have millions of conversations going CleverTap provides an easy way to search your conversations by clicking on the Search bar on top of the Conversations dashboard. The following filters are available:

1. Search bar - filters on user name, latest message text
2. Campaign - filters based on campaign names
3. Label - filters based on campaign labels
4. Ticket status - filters based on ticket status
