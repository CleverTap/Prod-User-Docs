---
title: Journey Approval Workflow
excerpt: Learn about journey workflow management.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
## Overview

As your team grows, Journeys reach more users, and a misconfigured one can have a significant impact. The Journey Approval Workflow adds a formal review step before any Journey goes live, so the right person signs off before users are enrolled.

<Callout icon="📘" theme="info">
  #### Private Beta

  Approval Workflow  is currently released in Private Beta. If you want to enable this for your account, contact Customer Success Manager.
</Callout>

With Journey Approval enabled, you build and save the Journey, then submit it to a designated Approver for review. The Approver reviews the Journey's setup, entry criteria, node configuration, and overall flow, then approves or rejects it. If approved, you publish the Journey, and it goes live. If rejected, you receive the reason by email, revise the Journey, and resubmit.

<Callout icon="📘" theme="info">
  #### Admins and Approvers can Publish without Approval Flow

  Admins can publish a Journey from any state, including _Draft_ and _Approval Pending_, without going through the approval flow. Approvers can also publish _Draft_ Journeys directly. Neither role is required to submit a Journey for approval before publishing.
</Callout>

### Use Cases

Journey Approval is useful whenever your team needs a review step before a Journey goes live. Common scenarios include:

- **Role separation:** Your team has dedicated Journey builders and separate stakeholders who sign off on messaging, targeting, or flow logic before Journeys reach users.
- **Compliance and governance:** Your industry or internal policies require documented evidence that someone reviewed and approved automated messaging before it was sent.
- **Onboarding new creators:** New team members can build and submit Journeys for a senior reviewer to approve, reducing the risk of errors reaching users.
- **High-stakes Journeys:** Journeys targeting large segments, running during peak business periods, or tied to revenue events benefit from a second review before launch.


<Image src="https://files.readme.io/16b2a2e4620cdfc35f40de91a8b15ab207e1759b4acc2dc94fd850bb9e694b7a-ChatGPT_Image_Sep_28_2026_11_03_33_AM.png" alt="A workflow diagram that explains the approval lifecycle of a Journey" align="center" caption="Journey Approval Workflow" border={true} />


## Enable or Disable Journey Approval

Only users with the Admin role can enable or disable Journey Approval. Your account plan must include Approval Management to access this feature.

Go to _Settings_ > _Security_ > _Approval Management_. Turn on **Enable Journey Approval on the Dashboard**.


<Image src="https://files.readme.io/4ae51b757813e55ab8334363f492e198fac97d51d449145decdb0c4f8856dade-image_2.png" alt="The Approval Management Section" align="center" caption="Approval Management Section" border={true} />


<Callout icon="🚧" theme="warn">
  #### Disabling Journey Approval Resets Active Journeys to Draft

  If you disable Journey Approval, all Journeys in _Approval Pending_, _Approved_, or _Rejected_ states move back to _Draft_ and their approval details are cleared.
</Callout>

### Assign Approver Access

After enabling Journey Approval, assign Approver access to the users who will review and approve Journeys. Two types of users count as Approvers:

- Users assigned the system **Approver** role.
- Users assigned a custom role with the **Approve** permission enabled for Journeys.

The Approver role for Journeys has these characteristics:

- The role includes write access to Journeys by default.
- Multiple users can hold the Approver role simultaneously.
- When _Teams_ is enabled, the role is team-specific. The approver selection list is filtered by the Journey's team and excludes the user submitting the Journey. For example, if a Journey belongs to Team A, the approver selection dialog shows only Approvers assigned to Team A. If the creator also holds Approver access, they are still excluded from the list because they are the one submitting the Journey.

#### Create Custom Role with Approver Access

To give a user Approver access through a custom role:

1. Go to _Settings_ and select _Roles_.
2. Click **Create Role**.


<Image src="https://files.readme.io/6e0d3cd6dbf020540f01b5a075d2c8ed4bfff4721534708fcbd06c7d0d12ac0a-Screenshot_2026-10-26_at_10.54.36.png" alt="The Roles section in Settings" align="center" caption="Roles Section" border={true} />


3. On the _Component Access_ tab, scroll to the _Engage_ section and find the _Journeys_ row. The Journeys row has three permissions: **Read**, **Write**, and **Approve**.

4. Select the **Approve** checkbox. Read and Write access are enabled automatically when you select Approve.


<Image src="https://files.readme.io/9b0fd6d68cc724e3ddb574a939fc5d371d4d24ff835151b7ab7135b68bed9fd3-Screenshot_2026-10-26_at_10.57.51.png" alt="The Component Access section in Create Role" align="center" caption="Component Access section in Create Role" border={true} />


<Callout icon="📘" theme="info">
  #### Journeys Permission Hierarchy

  Journeys permissions are cumulative. Selecting **Approve** enables Read and Write automatically. Selecting **Write** enables Read automatically. Read is the minimum permission level.
</Callout>

5. To complete the setup of the custom role and assign it to users, refer to [Role-Based Access Control](https://docs.clevertap.com/docs/role-based-access-control).

## Submit and Publish Journey

When Journey Approval is enabled, users with the Creator role follow a three-stage process to publish a Journey: submission, review, and final publish.

### Submit Journey for Approval

To submit a Journey for approval, perform the following steps:

1. Build a Journey on the Journey canvas and save it.
2. Click **Send for Approval** in the top-right corner of the canvas.


<Image src="https://files.readme.io/12f1b4c3536a1cbedba6a2d3711e9cfe8c248c522e3122a597ebd3c4deaf5d55-image_3.png" alt="Journey Builder with the Send for Approval option for Creator roles" align="center" caption="Journey Builder with the Send for Approval option for Creator roles" border={true} />


3. In the _Send for Approval_ dialog, select **Select approvers**.&#x20;
4. From the approver selection dropdown, select one or more approvers. The dropdown shows two columns: _Available approvers_ and _Selected approvers_. You can search for an approver, or click **Select All** and then click **Apply**.


<Image src="https://files.readme.io/231bb4aa3558920d45f79e8aaa7a86175956f44997619f7755a972cd97e2d3b6-image_4.png" alt="Selecting Approvers for Journey Approval in the Journey Canvas" align="center" caption="Select Approvers for Approval in the Journey Builder" border={true} />


<Callout icon="📘" theme="info">
  #### When No Approvers are Set Up on your Account

  If no Approvers are configured on your account, the _Send for Approval_ dialog shows the message: "No approvers are set up for this account, so all Admins will be notified — any Admin can publish it directly." The approver picker is not shown. Select **Send for Approval** to proceed.
</Callout>

5. Click **Send for Approval**.
   - The Journey status changes to _Approval Pending_.
   - Each selected approver receives an email notification.


<Image src="https://files.readme.io/017421ce36d703b789b8a9b59cb6d8c0a5089bbc9534134559677d20eac16869-Screenshot_2026-10-26_at_10.45.47.png" alt="The Approval Pending tab in Journeys" align="center" caption="Approval Pending Tab" border={true} />


### Review and Decide on Journey

Users with Approver access can approve or reject a Journey from the canvas. Admins do not need to approve or reject; they can publish the Journey directly from the canvas. The users selected during submission receive an email notification; selection determines who is notified, not who is permitted to act.

To review and act on a Journey submitted for approval, perform the following steps:

1. Open the Journey from the link in the approval email.
2. On the Journey canvas, review the setup, entry criteria, and flow. The canvas shows **Approve** and **Reject** buttons in the top-right corner.
3. Select **Approve** or **Reject**.


<Image src="https://files.readme.io/85a0a27d65981c22acb1848cb81600155053f7adef76f89c278b933c1106ef77-j2_copy.png" alt="Journey Builder showing the Approve and Reject button from the Approver's perspective." align="center" caption="Journey Builder" border={true} />


### Handle Approval Outcome

After the Approver acts, the Journey moves to one of two states: _Approved_ or _Rejected_.

#### Publish Approved Journey

When the Approver selects **Approve**, the Journey status changes to _Approved_. You receive an email notification. Complete the following steps to publish the Journey.

1. Open the Journey canvas and select **Publish**.
2. In the _Publish journey_ dialog, enter a name in the _Name_ field. The _Description_ field is optional.
3. Click **Publish**. The Journey status changes to _Running_.


<Image src="https://files.readme.io/9fbc61e0c383fabab4db6014a50905c3f009b5a84d4a55b0c22108a18ce79526-image_11.png" align="center" caption="Approved Journey with the Publish option" border={true} />


<Callout icon="📘" theme="info">
  #### Journey Publishing Rights

  - Once a Journey is approved, the creator, any eligible Approver, or a user with the Admin role can publish it.
  - Admins can also publish a Journey from any state, including _Draft_, _Approval Pending_, and _Rejected_, without requiring prior approval.
  - When Teams is enabled, Approvers can approve and publish only Journeys in their own team. Admins are not limited by team.
</Callout>

For example, a marketing manager builds a new user onboarding Journey and submits it for approval. After the team lead approves it, the manager opens the Journey, selects **Publish**, names it, and launches it.

<Callout icon="🚧" theme="warn">
  #### Approved Journeys are Read-Only

  You cannot edit a Journey in the _Approved_ state. To make changes, clone the Journey from the Journeys list. The clone starts as a _Draft_ you can edit and submit for approval.
</Callout>

#### Handle Rejected Journey

When the Approver selects **Reject**:

- The Journey status changes to _Rejected_.
- You receive an email with the reason for rejection.
- The canvas shows a **REJECTED** status label in the top bar.


<Image src="https://files.readme.io/b3c5814308bd4b45a6c798c5a305861759c6fd5434d9e58344c418750a74305d-Screenshot_2026-09-22_at_2.51.32_PM.png" alt="The Rejected tab in Journeys, showing all the Journeys that have been rejected." align="center" caption="Rejected Tab in Journeys" border={true} />


To view the rejection details on the canvas, select the **REJECTED** label. A dialog appears showing the **Rejected by** field (the Approver's email address) and the **Reason** for rejection.


<Image src="https://files.readme.io/cfa61ca8f7c808dbf3ba2d4630cf1ca01b99e8d115b5c52b0327c00d74440860-image_7.png" alt="The Rejection reason pop-up in the Journey Canvas" align="center" caption="Rejection Reason in the Journey Canvas" border={true} />


<Callout icon="🚧" theme="warn">
  #### Note Rejection Reason Before You Edit

  Note the rejection reason before you start editing. When you edit and save a Journey in the _Rejected_ state, it automatically resets to _Draft_ and the rejection details, including the **Rejected by** information and **Reason**, are permanently cleared from the canvas.&#x20;
</Callout>

To resubmit the Journey, edit it on the canvas and save. Saving automatically resets the Journey to _Draft_ and clears the approval request. Click **Send for Approval** to resubmit.

For example, a campaign manager submits a re-engagement Journey for approval. The Approver rejects it because the entry segment is incorrect. The manager selects the **REJECTED** label to note the reason, corrects the entry criteria, saves the Journey, and selects **Send for Approval** to resubmit.


<Image src="https://files.readme.io/c7146a5c44084378c7a8bef99ffb4a4df7b3fae12e5d109c1d814c1ae5d69078-image.png" alt="Journey canvas shown in the REJECTED state" align="center" caption="Journey Canvas in REJECTED state" border={true} />


## FAQs

### What happens to rejected Journeys?

When a Journey is rejected, the creator receives an email with the reason for rejection. You can also view the rejection details on the canvas by selecting the **REJECTED** label, which shows who rejected the Journey and the reason. You can edit the Journey and resubmit it for approval.

### Where can I check the reason for rejection?

You can find the reason for the rejection in the rejection email. You can also view it on the Journey canvas by selecting the **REJECTED** label. Note that editing and saving the Journey permanently clears the rejection details from the canvas.

### Can a creator edit a Journey that has been submitted for approval?

Yes. Edit the Journey on the canvas and save it. Saving automatically resets the Journey to _Draft_ and clears the approval request, including the assigned Approver. You can then make your changes and select **Send for Approval** to resubmit.

### Can I edit an Approved Journey?

No. Journeys in the _Approved_ state are read-only. To make changes, clone the Journey from the Journeys list. The clone starts as a _Draft_ you can edit and submit for approval.

### What happens if Journey Approval is disabled while Journeys are active?

All Journeys in _Approval Pending_, _Approved_, or _Rejected_ states move back to _Draft,_ and their approval details are cleared.

### Who can approve a Journey?

Users with Approver access can approve or reject a Journey. The users selected during submission receive an email notification — they are not the only ones permitted to act. Admins don't need to approve or reject: they can publish the Journey directly. When Teams is enabled, only Approvers within the Journey's team can approve or reject it. Admins aren't limited by team.

### Who can publish a Journey?

It depends on the Journey's state:

- **Draft:** Admins and Approvers can publish a Draft Journey directly without going through the approval flow.
- **Approved:** The creator, any eligible Approver, or a user with the Admin role can publish it.
- **Any state:** Admins can publish a Journey from any state, including _Approval Pending_ and _Rejected_.

### Can an Approver edit a Journey that is pending approval?

Yes. Approvers have write access to Journeys by default. Editing and saving the Journey resets it to _Draft_ and clears the approval request. Since Approvers are not required to go through the approval flow, they can publish the Journey directly after editing without resubmitting for approval.

<br />
