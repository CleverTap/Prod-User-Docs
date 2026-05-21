---
title: Product Experiences Approval
excerpt: Learn about the Prouct Experience workflow management.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Product Experiences Approval Workflow is a creator-approver control that gives you increased oversight over changes to _A/B Tests_ and _Remote Config Variables_ before they go live. When enabled, any action that changes the state of an experiment, such as starting, scheduling, pausing, finishing, editing, or deleting, requires explicit approval from the approver before it takes effect. This prevents unauthorized or accidental changes from reaching your production audiences.

<Image align="center" alt="Product Experience Workflow Custom Role Permissions" border={true} caption="Product Experiences Permissions" src="https://files.readme.io/374ec1c6cbe5990177d6d8c40afebce5d82852beaa2af420b21f33b65c920be5-image.png" />

The approval workflow applies to:

* A/B Tests
* Remote Config Variables

## Enable or Disable the Product Experiences Approval Workflow

To enable the approval workflow, go to _Settings_ > _Security_ > _Approval management_ > _Product Experiences [A/B Tests]_ toggle from the CleverTap dashboard.

<Image align="center" alt="Enable or Disable Approval for Product Experiences" border={true} caption="Enable or Disable Approval for Product Experiences" src="https://files.readme.io/2977515553aa4ac05bf63611bf467b063ee4a7bd378408e461e75cc83b6f6076-image.png" />

<Callout icon="📘" theme="info">
  Note

  Your account must have the A/B Testing feature enabled. The approval workflow toggle is disabled by default. If the toggle is unavailable, contact your CleverTap account manager.
</Callout>

<Callout icon="📘" theme="info">
  Note

  If you disable the approval workflow, the pending approvals are automatically reverted to their previous states.
</Callout>

## Assign Approver Access to Users

After enabling the workflow, you can assign the _Approver_ role to specific users, or create custom roles with approver access for the Product Experiences feature.

For more information on assigning roles, refer to Role [Based Access Control](https://docs.clevertap.com/docs/role-based-access-control) .

The following users are considered approvers:

* Any user with the system **Admin** role
* Any user with the system **Approver** role
* Any user with a custom role that includes approve permission for Product Experiences

<Callout icon="📘" theme="info">
  Note

  Approver assignments are per account. A user who is an approver on one account is not automatically an approver on another. A creator cannot approve their own submission.
</Callout>

# Product Experiences Approval Workflow

After enabling the approval workflow, a new process is required to start, schedule, pause, finish, edit, or delete an experiment. It involves the following steps:

1. The creator creates or modifies an A/B Test or Remote Config Variable.
2. The creator submits the change for approval. The system transitions the experiment to a _Pending Approval_ state, and an email notification is sent to all Admins and Approvers on the account.
3. The approver reviews the proposed change and either approves or rejects it.

The following are some of the key points to remember for the Product Experiences Approval Workflow:

* _Approval precedes the change_: The experiment remains in its current live state until the approver explicitly approves it.
* _Rejection reverts the experiment_: If rejected, the experiment returns to its previous state. For example, if a running A/B Test is submitted for a pause and the approver rejects it, the test continues running unchanged.
* _Creators cannot approve A/B Tests_: The system intentionally separates roles. Only users with the Approver or Admin role can approve experiments.
* _Staged edits on live experiments_: If a running or paused experiment is edited but not yet published, the staged edits are submitted for approval like any other change. If rejected, the staged edits are discarded, and the experiment continues in its current state.
* _Finishing an A/B Test_: When an approver approves a finish action, they may optionally select a winning variant to roll out to 100% of users before the test closes.

<Callout icon="📘" theme="info">
  Note:

  If the approval workflow is disabled while approvals are pending, all pending changes are automatically reverted to their previous states. Creators are not automatically notified, so communicate this change to your team manually.
</Callout>

## Experiment States

An experiment moves through the following states during the approval workflow. States prefixed with **PENDING_** indicate that approver action is required.

| Current State    | Action Submitted | Pending State      | On Approval     | On Rejection                          |
| ---------------- | ---------------- | ------------------ | --------------- | ------------------------------------- |
| Draft            | Start            | APPROVAL PENDING   | Running         | Draft                                 |
| Draft            | Schedule         | SCHEDULING PENDING | Scheduled       | Draft                                 |
| Running          | Pause            | PAUSE PENDING      | Paused          | Running                               |
| Running          | Finish           | FINISH PENDING     | Finished        | Running                               |
| Running / Paused | Publish edits    | APPROVAL PENDING   | Changes go live | Edits discarded, experiment unchanged |
| Paused           | Resume           | RESUME PENDING     | Running         | Paused                                |
| Paused           | Finish           | FINISH PENDING     | Finished        | Paused                                |
| Finished         | Delete           | DELETE PENDING     | Deleted         | Finished                              |

## Approve or Reject a Change

An admin or approver can approve or reject a change from the dashboard.

<Image align="center" alt="Approve or Reject an experiment" border={true} caption="Approve or Reject Experiment" src="https://files.readme.io/01f4b4f11156ca125010155c7ded822e6670074892af1054a028093d1b5b0086-image.png" />

1. Open the pending experiment from the dashboard.
2. Review the proposed change, such as configuration details, variant setup, targeting, and so on.
3. Click **Approve** or **Reject**.
4. Optionally, add feedback (up to 1,024 characters). Feedback is visible to the creator and recommended when rejecting.

# Notifications

The following table shows the notifications sent to users for each event:

| Event                                 | Who Is Notified                                 |
| ------------------------------------- | ----------------------------------------------- |
| Change submitted for approval         | All Admins and Approvers on the account (email) |
| Change approved                       | Creator who submitted, all Admins (email)       |
| Change rejected                       | Creator who submitted, all Admins (email)       |
| Approval workflow enabled or disabled | All Admins and Approvers on the account (email) |

# FAQs

### Q. Can a Creator approve their own request?

A. No. The system enforces role separation. Only users with the Approver or Admin role can approve experiments, and they cannot approve submissions they created themselves.

### Q. What happens if I disable the approval workflow while approvals are pending?

A. All pending approvals are automatically reverted to their previous state. No experiment transitions silently. Note that creators are not automatically notified, so communicate this change to your team.

### Q. What if the designated approver is unavailable?

A. Any Admin on the account can approve. Check that at least one Admin is always reachable. If required, grant additional users the Approver role from _Settings_ > _Team_.

### Q. Can I edit an experiment while it is pending approval?

A. No. The pending state locks the experiment. You must wait for the approver to act, that is, approve or reject the approval request, before making further changes.

### Q. What happens to a scheduled experiment if approval is rejected?

A. The experiment reverts to Draft. It does not run at the scheduled time.

### Q. Does the approval workflow apply to both A/B Tests and Remote Config Variables?

A. Yes. Enabling the Product Experiences toggle applies the workflow to both A/B Tests and Remote Config Variable changes simultaneously.
