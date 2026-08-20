---
title: Messages
excerpt: Learn how to messages for each stage in the Lifecycle Agent.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Messages step is where you build the content pool for each engagement stage of your Lifecycle Agent. The agent picks from this pool at runtime, choosing which message to send to each user.

The following image shows the Messages step for an agent with three stages (Welcome, Educate, Offer) and two messages configured in the Welcome stage.


<Image src="https://files.readme.io/037dc2f2efa4ef4d66920cbcfbed9a607a5af0ad3fb80af25f9a97aa72244a79-image.png" alt="Lifecycle Agent Messages Example" align="center" caption="Lifecycle Agent Messages Example" border={true} />


Every stage you defined in the Engagement Strategy step appears here as a stage card showing the stage name and current message count. Select a card to view or manage its messages.

Each message is mapped to a specific stage of a specific agent and is not reusable elsewhere, though you can reference an existing CleverTap template as a starting point. Add as many messages per stage as required; a larger content pool gives the agent more variants to test and optimize.

<br />

<Callout icon="📘" theme="info">
  ### Note

  The channels available when you add a message are limited to the channels enabled for that stage in the _Engagement Strategy_ step. If a channel does not appear in the list, return to the _Engagement Strategy_ step and add it to the stage's allowed channels.
</Callout>

## Add a Message

Perform the following steps to add a message to a stage.

1. Select the stage to which you want to add the message.The message list for the selected stage displays below.
2. Click **Add Message**.
3. Enter a name for the message in the **Message Name** field.
4. Select a channel from the following supported options:
   - Push Notifications
   - Email
   - SMS
   - WhatsApp
   - Web Push
   - Inbox
5. Select an existing CleverTap template to base the message on, and adjust it as needed.
6. Click **Save**.&#x20;

## Manage Messages

Hover over a message row in the list to reveal the row actions: edit, clone, and delete. To act on multiple messages at once, use the row checkboxes and the selection bar that appears above the list.

### Edit

Select the edit action to open the message and edit the content.&#x20;

### Clone

Select the clone action to create a copy of the message in the same stage. Rename the copy and adjust any fields as needed.

### Delete

Perform the following steps to delete one or more messages from a stage:

1. Select the stage card that contains the messages you want to delete.
2. Select the checkbox next to each message you want to delete. To delete every message in the stage, select the checkbox in the table header. A selection bar displays the number of selected messages along with the delete icon, **Deselect all**, and **Clear selection** actions.
3. Click the delete icon in the selection bar.
4. Confirm the deletion in the prompt.

<Callout icon="📘" theme="info">
  ### Note

  To delete a single message, hover over its row and select the delete action. Deleted messages cannot be recovered. If a deleted message was the only one in its stage, the agent has no content to send for that stage until you add a replacement.
</Callout>

### Find a Message

Use the search field to filter the list by message name, or select the filter icon to filter by channel. Select any column header with a sort indicator to sort the list.

<br />
