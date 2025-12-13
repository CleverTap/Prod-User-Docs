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

## Use cases

Engaging your end users with chat based conversations has a huge impact on your business metrics.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Example Industry
      </th>

      <th>
        Use cases
      </th>

      <th>
        Impacted metric
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
        * Custom discounts to book a return flight
        * Recommendations about hotels for an upcoming stay
      </td>

      <td>
        Increased customer satisfaction
      </td>
    </tr>

    <tr>
      <td>
        Food Delivery
      </td>

      <td>
        * Food delivery status, including information on driver and ETA
        * Thank you messages after order delivery
        * Custom discounts/refunds in case of a late/wrong delivery
      </td>

      <td>
        Increased user engagement
      </td>
    </tr>

    <tr>
      <td>
        Streaming Media/OTT
      </td>

      <td>
        * Recommendations for new shows/movies/upcoming matches 
        * Premium service options when a user finishes a movie/episode
      </td>

      <td>
        Increased user engagement
      </td>
    </tr>
  </tbody>
</Table>

## Role based access for Conversations: Agent Role

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

<Image title="Screenshot 2019-06-06 at 4.46.00 PM.png" alt={1436} src="https://files.readme.io/ce8c561-Screenshot_2019-06-06_at_4.46.00_PM.png">
  Conversations dashboard
</Image>

You will see a list of conversations when you arrive on the dashboard. These conversations appear when your end users reply on one of your campaigns.

You can click on one of the messages to open the chat window. The chat window is the panel that appears on the right where you can chat with your users seamlessly.

<Image title="Screenshot 2019-06-17 at 9.04.25 AM.png" alt={360} src="https://files.readme.io/6bafdd0-Screenshot_2019-06-17_at_9.04.25_AM.png">
  Active chat window in Conversations
</Image>

Unlike [WhatsApp](doc:whatsapp) campaigns, where you had to use a templated messages, Conversations allows you to use free form messages.

## Converting user queries into customer support tickets

> 📘 Customer support ticketing
>
> CleverTap provides putting a 'ticket' status to on-going chats with your end-users. This helps in categorising and later searching based on resolution status of your customer's queries.

<Image title="Screenshot 2019-06-17 at 9.18.23 AM.png" alt={1207} src="https://files.readme.io/a2ef691-Screenshot_2019-06-17_at_9.18.23_AM.png">
  Ticketing in Conversations
</Image>

There the 3 ticket statuses that can be assigned:\
**1. New:** As soon as a user replies on a campaign message, it is marked as New. This is irrespective of the previous ticket status with that user.\
**2. Pending:** You can mark a query as pending if you think you will come back with a resolution to it later.\
**3. Closed:** You can close a query as soon as you resolve it.

However, it's upto you (the Agent) to mark the tickets as you deem fit.

Please note that **ticket status** is similar to a system profile property and hence, it is also queryable on the dashboard.

## **How to assign a ticket to a conversation?**

Assigning a ticket to a Conversation is fairly simple. If you click on a conversation, and close it, a pop-up appears asking you to assign a ticket before closing it. You can update the ticket status here.

<Image title="Screenshot 2019-06-17 at 9.23.55 AM.png" alt={1227} src="https://files.readme.io/b45c27c-Screenshot_2019-06-17_at_9.23.55_AM.png">
  Click on the 'X' on chat window and you will see this popup to update the ticket status.
</Image>

## Active and Inactive conversations

A conversation is marked active when an end user has replied to any campaign message. It will show up in the active tab, The active conversation remains so for 24 hours until the last replied message.

Inactive conversations are those whose 24-hour window has been over. They will appear inside the Inactive tab. 

Note: The max limit for inactive conversations to appear in the inactive tab is 15 days.

![660](https://files.readme.io/ae4344f-Screenshot_2019-06-06_at_4.50.30_PM.png "Screenshot 2019-06-06 at 4.50.30 PM.png")

## Searching and sorting Conversations

If you have millions of conversations going CleverTap provides an easy way to search your conversations by clicking on the Search bar on top of the Conversations dashboard. The following filters are available:

1. Search bar - filters on user name, latest message text
2. Campaign - filters based on campaign names
3. Label - filters based on campaign labels
4. Ticket status - filters based on ticket status
