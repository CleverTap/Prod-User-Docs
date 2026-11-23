---
title: Guardrails
excerpt: Learn how to set guardrails for your agent messaging
deprecated: false
hidden: false
metadata:
  robots: index
---
The _Guardrails_ tab sets hard limits on messaging that the agent always respects, regardless of what it would otherwise choose to send.

To complete the _Guardrails_ tab:

1. Under _Limits_, set how often the agent can send messages. Select a limit's checkbox to enable it, and then set the maximum number of messages allowed:

   - **Channel-wise limit**: The maximum number of messages the agent can send through a single channel across all users.
   - **Per user limit**: The maximum number of messages the agent can send to any one user. Select the period the limit applies to: Daily, Weekly, or Monthly.

2. Under _Exploration Size_, use the slider to divide your target audience into two groups:

   | Group                 | Description                                                                                                         | Default |
   | --------------------- | ------------------------------------------------------------------------------------------------------------------- | ------- |
   | **Exploration size**  | The percentage of users the agent uses to try different messaging approaches and content and learn what works best. | 20%     |
   | **Exploitation size** | The percentage of users who receive the agent's best-performing messaging approach and content.                     | 80%     |

   Drag the slider to change the split.&#x20;

3. (Optional) Turn on **Do Not Disturb (DND)** to define quiet hours. The agent does not send messages during DND hours and avoids scheduling its next action for a user inside a DND window. DND hours use the account's timezone.&#x20;

   The following image shows the _Guardrails_ tab with limits, exploration size, and the DND option:

   <Image src="https://files.readme.io/489126cce76e1b743bf0371f6197cc6b54af553f28357ea51dfbd0e731bb29b5-image.png" alt="Agent Guardrails" align="center" caption="Agent Guardrails" border={true} />


4. Click the **Save** icon in the top-right corner to save the agent.

<Callout icon="🚧" theme="warn">
  ### **Caution**

  DND windows use your account's timezone, not each user's local time. If your audience spans multiple timezones, a DND window can block messages during some users' daytime hours.
</Callout>

<Callout icon="📘" theme="info">
  ### **Note**

  You can save a draft at any time. Incomplete tabs are marked with a red indicator in the top navigation bar.&#x20;
</Callout>

<br />

<br />