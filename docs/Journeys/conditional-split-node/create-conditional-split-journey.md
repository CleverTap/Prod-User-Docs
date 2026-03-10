---
title: Create Conditional Split Journey
excerpt: Learn how to use the Conditional Split node within a CleverTap Journey.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

This document walks you through the steps to configure and use the Conditional Split node within a CleverTap Journey. The Conditional Split node enables personalized, real-time decision-making by routing users down different paths based on their profile attributes, event behavior, or a combination of both.

# Create Conditional Split Journey

Consider an example to understand how to build a journey using a Conditional Split node and how it works behind the scenes at each step. A movie streaming app wants to personalize content recommendations based on the movie genre selected by users during onboarding. By splitting users according to their `preferred_genre` (such as Action or Comedy), the app can deliver more relevant content suggestions and improve engagement through genre-specific emails and push notifications.

To create a journey using the Conditional Split node, perform the following steps:

1. Create a new Journey.
2. Define the Entry Segment. Here, it will be the Action Node where the _Onboarding Completed_ event will be the trigger event. When a user completes onboarding, they immediately enter the journey. Since this is a live trigger, the user proceeds to the next node in real time.
3. Drag and drop the **Conditional Split** node from the _Controllers_ section.
4. Click the Conditional Split node to set up the conditions per your requirements. Here, the

   * Condition Type: User Property
   * User Property: `preferred_genre`

   <Image align="center" alt="Set Up Conditional Split Node" border={true} caption="Set Up Conditional Split Node" src="https://files.readme.io/065befe1fc18cd125f35dd168844c2bd3e8ba61333ffe53893f5a3d97fbe85d9-Set_Up_Conditional_Split_Node.gif" />
5. Add the required engagement nodes for each path. Here, the split paths will be:
   * `preferred_genre` = Action
   * `preferred_genre` = Comedy
   * Others (fallback) → Default path with general recommendations. This path, labeled “Others”, captures all users who do not meet any configured conditions. This path appears last and cannot be reordered or renamed. All standard journey nodes can be connected to this path, except IntelliNODE.        
     <Image align="center" alt="Create Conditional Split Journey for Movie Streaming App" border={true} caption="Create Conditional Split Journey for Movie Streaming App" src="https://files.readme.io/414acef6279f741efbe0848bdea8a569f75d8cf85f39878940559a3efbe6d438-Conditional_Split_Movie_Streaming_App.png" />
     <br />
     <Callout icon="📘" theme="info">
       #### Nested Objects

       You can select nested user properties, for example, `insuranceDetails.planType`, `user_roles.role_name`. Nested properties appear grouped under their parent object in the selector.

       For example, an insurance app wants to personalize renewal reminders based on a user’s policy details stored inside a nested object. The app stores policy information under a nested user property called `insuranceDetails`, which contains: `insuranceDetails.planType`, `insuranceDetails.policyStatus`, `insuranceDetails.renewalMonth`

       The app wants to route users based on how their policy premium is paid, using a nested policy object stored on the user profile.

       <Image align="center" border={true} caption="Conditional Split Journey Using Nested Object" src="https://files.readme.io/f5e7caf7326656acf6fdf768b30ce56deb48ee12871456a24c1dec11f1e7a407-Conditional_Split_Journey_Using_Nested_Objects.png" />

       For more information about this feature, refer to [Nested Objects](doc:nested-objects-for-user-properties-and-custom-event-properties).
     </Callout>
6. **Save** or **Publish** the journey.

When the user reaches the Conditional Split node, CleverTap checks the real-time value of the `preferred_genre` user property and routes the user down the first matching path. The personalized emails/push notifications are triggered immediately based on the user’s split path. This ensures users receive hyper-relevant content immediately after joining, increasing engagement and satisfaction from Day 1.

<Callout icon="📘" theme="info">
  #### Node Connection Guidelines

  * Viewed and Sent paths from the same campaign node cannot connect to a Conditional Split node (to avoid conflicting logic)
  * You cannot attach multiple Conditional Split nodes in parallel to the same origin path. Parallel Conditional Split nodes are allowed if each originates from different paths, such as separate PBS branches.
  * The Conditional Split node routes users based on specific conditions. Since each user could follow a different path, you must handle each condition independently by connecting a separate node to each path.
</Callout>

# Order of Paths

The order of paths is important because CleverTap evaluates conditions in the order they are defined and routes the user down the first matching path. If broader or overlapping conditions are placed higher in the order, more specific conditions lower down might never be checked, leading to incorrect user routing. For example:

* Path 1: `plan_type` = Exists
* Path 2: `plan_type` = Premium

In this case, all users with a `plan_type` match Path 1 first, even if they are Premium.

# Sequential Conditional Split Nodes

You can chain multiple Conditional Split nodes to evaluate layered conditions. Each conditional split node evaluates conditions in the order they appear. This approach allows you to personalize paths based on event or user properties without needing complex segments. CleverTap supports up to three conditional split nodes in a journey, ideal for scenarios where decisions must be made step by step.

## Sequential Conditional Split Using User Properties

**Use Case**: A food delivery app wants to tailor promotional messages based on the user properties `subscription_plan` and `location`:

<Image align="center" alt="Sequential Split by User Properties" border={true} caption="Sequential Split by User Properties" src="https://files.readme.io/906ec81a7f1b98190f18f3fea13b9325c50be7a1cf06b1e5ae40faa11d1f294e-Sequential_Split_By_User_Properties.webp" width="45% " />

In this way, the app ensures that only Premium users in metro cities receive exclusive offers by chaining two conditional split nodes. In contrast, all other users receive appropriate alternatives based on plan and location.

## Sequential Conditional Split Using Event Properties

You can also chain multiple Conditional Split nodes to evaluate a series of event properties, provided each node follows a supported event trigger.

**Use Case**: A food delivery app wants to personalize messages after an order based on the type of order placed and the time it was placed.

* Conditional Split Node 1: Evaluates the event property `order_type` from the Order Placed event
  * `order_type` = Scheduled → Moves to Splitter 2
  * `order_type` = Instant → Sends a Thank You message
* Conditional Split Node 2 (connected to the “Scheduled” branch): Evaluates the event property delivery_slot
  * `delivery_slot` = Dinner → Sends a message promoting dessert add-ons
  * `delivery_slot` = Lunch → Sends a message offering a lunch combo upgrade

This setup tailors post-order engagement based on when and how the order was placed, enabling highly contextual and timely messaging.

# Usage Limits

* **Sequential Split**: A maximum of 3 Conditional Split nodes can be used sequentially in a single journey. This allows for layered decision logic while maintaining clarity and control.
* **Paths per Conditional Split Node**: Each Conditional Split node can support up to six defined condition paths, and a fallback path ("Others"), adding up to seven paths per node.
* **Account-wide Limit**: A maximum of 15 Conditional Split nodes can be used per account across journeys.

# Error Scenarios

The following are the error scenarios marketers may encounter while creating a Conditional Split journey:

* **Incomplete Split Criteria**

  This occurs when a user opens the Conditional Split node and attempts to publish it without configuring any split conditions. The journey cannot be published until all path conditions are defined.

  <Image align="center" alt="Incomplete Split Criteria Error" border={true} caption="Incomplete Split Criteria Error" src="https://files.readme.io/1a6f8d7c0090bc07646007e947af202ab93e1a73a8aac97ea00d8acd3c0d6c12-Incomplete_Split_Condition.gif" />
* **Previous Node Modified or Deleted**  
  This error occurs when the node connected to the Conditional Split, typically an Action or PBS node, is either modified to invalidate the existing conditions or deleted entirely from the journey canvas.

  <Image align="center" alt="Previous Node Deleted" border={true} caption="Previous Node Deleted" src="https://files.readme.io/2c491387a028f6eff91fd2f5a6274f29f7de3fdb07502c05109e5e1d859b8ce2-Conditonal_Split_Node_Uninitialized.gif" />

  To resolve this, do the following:

  1. Reconnect the Conditional Split node to a valid, configured segment or action node.
  2. Reconfigure the split paths using relevant user/event properties from the new upstream node.
  3. Validate the journey again before publishing.
* **Unsupported Data Types in Conditions**  
  This occurs when you attempt to select a property of type DateTime, List, or Number in the Split setup, which currently supports only String and Boolean.
* **Path Conditions Exceed Limit**  
  This occurs when you add more than the allowed number of paths. You can add six paths and one fallback path (automatically added), totaling seven paths per Conditional Split node.
* **Fallback Path Missing or Unlinked**  
  This occurs when the fallback path is deleted or left unconnected to any node.
