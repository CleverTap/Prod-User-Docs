---
title: Journey Operations
excerpt: Understand how to perform various operations for your journey.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Manage Journeys

1. Select **Journeys**. This takes you to the _All Journeys_ page.
2. Select a journey's checkbox to manage its functioning.


<Image src="https://files.readme.io/821ac308207ce2eab2f2d89959c008dac88da604f9fa8cc017b38fe24df58c23-Manage_Journeys.png" alt="1345" align="center" width="90% " caption="Manage Journeys" border={true} />


This activates the _Action Buttons_ displayed on the top left. The buttons are:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Action Buttons
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Pause and Resume**![Pause\_Resume](https://files.readme.io/70f33f0-Pause_Resume.png)
      </td>

      <td>
        Temporarily halts the qualification of new users in the Journey. Users already in the journey will continue traveling through it or continue receiving messages. You can select more than one Journey to pause or resume them altogether.
      </td>
    </tr>

    <tr>
      <td>
        * **Stop**![Stop](https://files.readme.io/e99e396-Stop.png)
      </td>

      <td>
        Completely halts the journey. It stops:

        * qualification of new users
        * movement of users within the journey
        * delivery of campaigns.

        **NOTE**: Restarting a stopped journey is not possible. You can select more than one Journey to stop them together.
      </td>
    </tr>

    <tr>
      <td>
        **Ellipsis**![Ellipsis](https://files.readme.io/38242f5-ellipsis.png)
      </td>

      <td>
        More actions are available from the ellipsis icon:

        * **Clone**: Enables you to copy an existing journey.

          You can choose to copy it within the same project by selecting Current project or to a different project by selecting Another project.

          If you select Another project, choose the destination project where the journey should be copied. The copied journey is created as a draft in the destination project.

          For more information, refer to [Copy Engagements Across Projects](doc:copy-engagements-across-projects).
        * **Edit**: Enables you to edit the journey. You cannot edit all parts of the Journey once it has been published. You can only edit the Journey content.
      </td>
    </tr>

    <tr>
      <td>
        **Operations using Keyboard Shortcuts**
      </td>

      <td>
        Using keyboard shortcuts, you can manage journeys. Click the ![](https://files.readme.io/62eb9da-Keyboard_Shortcuts.png) icon to learn about the keyboard shortcuts.

        <Image border={true} src="https://files.readme.io/49b92ca83dec3c82f02d06660743508c38824ab6bcc59a5966193cbd9d8419e8-Journey_Keyboard_Shortcuts.png" className="border" />

        For example, press **Shift** and select the nodes you want to copy, and then press **Option/Alt** and drag the selected nodes to copy them, as shown in the following gif:

        <Image border={true} src="https://files.readme.io/2e6e7b0589b29da37c97677845d1457caecce7417c7abe4e7fd10899908ae8a1-Multi-select_Nodes_to_copy_1.gif" className="border" />
      </td>
    </tr>
  </tbody>
</Table>

## Summarize Journey

Journeys with many nodes, conditions, and paths can be hard to read at a glance. Journey Summarizer generates a short, plain-language summary of a journey so you can understand who qualifies, what the goal is, and how users move through the journey without opening every node.

Use it to:

* Get up to speed on a journey a teammate built.
* Explain a journey to a stakeholder without walking through the canvas.
* Confirm that a journey does what you intended before you share it.
* Get information on how a journey is set up. It doesn't show performance numbers. To see how a journey is performing, refer to the _Journey Stats_ and _Node Stats_ tabs.

### View a Journey Summary

1. Select **Journeys**. This takes you to the _All Journeys_ page.

2. Select the journey you want to summarize. The journey details page opens.

3. Click the **Journey Summarizer icon**.

   A **Summary** pop-up opens.


   <Image src="https://files.readme.io/72a8841d8c723042933b73e372e67cfb3ff6ec87576ac1177bb3811b2a86efaf-Journey_Summarizer.gif" alt="A gif showing how Journey Summarizer works" align="center" caption="Journey Summarizer Workflow" border={true} />


### Journey Summary Properties

| Field               | Description                                                                                                                                                                                                                                                                                                                                                       |
| :------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Journey Name**    | The name of the journey.                                                                                                                                                                                                                                                                                                                                          |
| **Qualification**   | The condition users must meet to enter the journey. For example, a summary might read: "Users qualify when they have done Charged Today at least once."                                                                                                                                                                                                           |
| **Goal**            | The goal is configured for the journey. If the journey has no goal, the summary says so.                                                                                                                                                                                                                                                                          |
| **Engagement Flow** | The order in which users move through the journey and the messages they receive, if any. Some journeys do not send messages to users. They are used only to update user properties. For example, the **Engagement Flow** might read: "Qualified users enter the journey, receive one webhook immediately, then move to a second webhook after the first is sent." |

<Callout icon="📘" theme="info">
  #### **Journey Summarizer Distinction**

  The summary is separate from journey comments. It does not replace the comments your team adds to a journey.
</Callout>

### Best Practices

* Check the summary against what you intended. If **the Qualification** or **Engagement Flow** does not match your plan, review the journey before publishing it.
* Give your journeys clear names and descriptive node labels. The summary is built from your journey's setup, so clear naming makes it easier to read.
