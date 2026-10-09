---
title: Reward Functions
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

A Reward Function defines which user actions count as good outcomes (positive signals) and which count as bad outcomes (negative signals).

Without a shared Reward Function, you'd have to define "what counts as success" separately inside every agent, and there'd be nothing stopping two agents from quietly defining the same goal in two slightly different ways — which makes it harder for the underlying model to learn cleanly from your account's full engagement history.

A Reward Function reduces that redundancy: you don't need to redefine your business goal for every agent you set up. Reward Functions are independent of any single agent. You create a Reward Function once for your account, and any agent that needs one, a One-Time Agent or a Lifecycle Agent, selects it from a list.

## Types of Reward Functions

CleverTap provides System and Custom Reward Functions. Every account starts with two ready-made System Reward Functions you can use immediately.&#x20;

- Use a System Reward Function when your goal is simple, optimizing raw notification clicks, or a single conversion event.
- Create a Custom Reward Function when your business goal spans multiple funnel stages, needs negative signals beyond the built-in ones, or uses event names specific to your industry.

## System Reward Functions

These come with every account and need no setup. Their name, description, and overall structure are locked and cannot be changed.

| Reward Function                  | Positive Signal      | Negative Signal(s)                                                    | Editable                 |
| -------------------------------- | -------------------- | --------------------------------------------------------------------- | ------------------------ |
| **Notification Click Optimizer** | Notification Clicked | App Uninstalled (highest priority); channel unsubscribe (any channel) | No                       |
| **Conversion Event**             | Charged (default)    | App Uninstalled (highest priority); channel unsubscribe (any channel) | Only the positive signal |

<Callout icon="ℹ️" theme="info">
  ### Tip

  - If your business tracks conversions under a different event name, such as "Order Placed," "Subscription Started," "Booking Confirmed", update the Conversion Event Reward Function's positive event to match. Its name and structure stay fixed; only the event itself changes.&#x20;
  - You can also add a second and third priority level here.&#x20;
  - This edit is only available when the Reward Function isn't currently in use by a running Agent.
</Callout>

## Custom Reward Function

A Custom Reward Function is fully editable and lets you tailor signals to your business's funnel.

To create a Custom Reward Function:

1. From the _CleverTap dashboard_, navigate to _Decisioning_ > _Reward Function_, and then click **Create**. The _Create Reward Function_ section appears.


<Image src="https://files.readme.io/be7d7944c2e0d1886164e8eddd3128fdcbfd8ae6a4b23817b903effec7da130b-image.png" align="center" caption="Reward Function" border={true} />


2. Enter a name in the _Function Name_ field. Names can be up to 200 characters and must be unique in your account.


<Image src="https://files.readme.io/1f6bca66eee14d65ccfd7305911ebaf4986ee76e37ee217775c1ad406d592e24-image.png" align="center" caption="Setup" border={true} />


3. Enter a _Description_, up to 500 characters, explaining the business goal this Reward Function optimizes for. For example, a retailer might name theirs _Maximize Purchases_, described as: _"Optimizes for users completing a purchase. Penalizes channel unsubscribes to reduce communication fatigue."_
4. Under _Positive Signals_, add at least one positive signal, which is a user action you want the agent to optimize toward.<br />a. Click **Add Positive Signal** to add a signal. Each signal you add is its own priority level; drag a signal using its handle to reorder priority, the topmost signal is Priority 1, the highest.<br />b. Click **+** next to a signal to add another event to it. Any one event within a signal satisfies that priority level, events within a signal are evaluated as OR, not AND.

   For example:

| Priority             | Event(s)                         | What It Means                             |
| -------------------- | -------------------------------- | ----------------------------------------- |
| Priority 1 (highest) | Charged                          | Primary conversion goal                   |
| Priority 2           | Add to Cart _or_ Add to Wishlist | Mid-funnel intent — either counts equally |
| Priority 3           | Product Viewed                   | Top-of-funnel engagement                  |

4. Under _Negative Signals_, optionally add signal(s) that may adversely affect conversion. Click **Add Negative Signal**, following the same pattern as positive signals.

5) Click **Save**.

<Callout icon="📘" theme="info">
  ### Note

  Your account can have up to 5 Reward Functions in total: the 2 built-in System ones (always present and do not count against your custom quota) plus up to 3 Custom ones you create.&#x20;

  A Reward Function needs at least one positive event to be saved; you cannot save an empty one.
</Callout>

## View and Filter Reward Functions

The _Reward Function_ page lists every Reward Function in your account.

Use **Filters** to narrow the list:

- **Time Period**: filter by when the Reward Function was created. Defaults to _All time_.
- **Created By**: filter by the user who created it.
- **Type**: filter by _System_ or _Custom_.
