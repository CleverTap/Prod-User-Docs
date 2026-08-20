---
title: Guardrails
excerpt: Learn how to set guardrails for your agent messaging
deprecated: false
hidden: true
metadata:
  robots: index
---
The _Guardrails_ tab configures the hard limits for messages that the agent must always respect, regardless of what its model recommends.&#x20;

To complete the _Guardrails_ tab:

1. Under _Limits_, configure message frequency constraints. Select a checkbox to enable a limit, then set the maximum number of messages allowed.
   - **Channel-wise limit** — The maximum number of messages the agent can send through a single channel across all users.
   - **Set the Per user limit**. It is the maximum number of messages the agent can send to any one individual user.
2. Under _User Distribution_, set the testing split for the agent's learning strategy. The slider divides your target audience into two groups:

| Group                 | Description                                                                                                     | Default |
| --------------------- | --------------------------------------------------------------------------------------------------------------- | ------- |
| **Exploration size**  | The percentage of users the agent uses to test and learn from different combinations and ordering of messaging. | 20%     |
| **Exploitation size** | The percentage of users the agent engages with using its best-performing messaging sequence.                    | 80%     |

Adjust the slider to change the balance.

3. (Optional) Select **Do Not Disturb (DND)** to define quiet hours. The agent does not send messages to users during DND hours. By default, DND limits use the user's own timezone.

<Callout icon="🚧" theme="warn">
  ### **Caution**

  Messages that fall within a DND window are dropped, not rescheduled. If a large portion of your audience is in the same timezone, a wide DND window can significantly reduce message delivery.
</Callout>

The following image shows the _Guardrails_ tab with limits, user distribution, and the DND option:


<Image src="https://files.readme.io/7ce0550d2073f7d8753f1ca589b84758db35c45f29241d29c31dcdc739269d1c-image.png" alt="Agent Guardrails" align="center" caption="Agent Guardrails" border={true} />


<br />

4. Click the **Save** icon in the top-right corner of the window to save the agent.

<Callout icon="📘" theme="info">
  ### **Note**

  You can save a draft at any time. Incomplete tabs are marked with a red indicator in the top navigation bar.
</Callout>
