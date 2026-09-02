---
title: Manage Email Notification Preferences
excerpt: >-
  Learn how to use Notification Management to control which CleverTap email
  alerts you receive.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

CleverTap notifies you about activities in your account, such as when a campaign report is ready, a teammate shares a segment with you, your plan changes, or an outage occurs. Notification Management allows you to decide which of these actually land in your inbox. Unsubscribe from categories for which you do not require notifications.

<Callout icon="📘" theme="info">
  ### Mandatory Notifications

  Alerts such as downtime notices or billing changes remain mandatory, so you are always informed about important account activities, and you cannot unsubscribe from them.&#x20;
</Callout>

The following image shows the _My Profile&#x20;_&#x70;age:


<Image src="https://files.readme.io/f45ffe37018ba9998a421627f8954b095f5c33ddc1db5b62eb5073038fee6bea-image.png" alt="The account menu open from the top-right avatar, with the My Profile tab active on the Notification page" align="center" caption="My Profile" border={true} />


## Notification Categories

Notification Management groups related alerts into categories. Click the arrow next to a category to expand or collapse and view the individual alerts inside. The Email column shows whether you currently receive that alert, a checked box indicates that the email notification is on. You can [Edit your preferences](doc:manage-email-notification-preferences#edit-your-preferences) by checking or unchecking that particular notification.<br /><br />Follow the steps to view the Notification Categories:

1. Click your profile avatar in the top-right corner of the dashboard.
2. Click your name in the list to open _My Profile_.
3. Switch to the _Notification_ tab. <br />The _Notification Management&#x20;_&#x70;age opens, which lists the notification categories available to you.

The following image shows the Notification categories:


<Image src="https://files.readme.io/3a063b5b02ee17c377ae5d3d6fa2cc1872a0e5a5740a7f9a11998df7e87f60f6-image.png" alt="The Notification tab on My Profile, showing categories expanded into individual alerts with checkboxes" align="center" caption="Notification Tab" border={true} />


<Callout icon="📘" theme="info">
  ### Role-Based Visibility

  The categories you see depend on your role. Non-admin users cannot view admin-only categories, such as Billing & Payments, Downtime & Outages, and so on.
</Callout>

The following table lists the notification categories and alerts with the descriptions:

| Category                   | Alert                       | Description                                                        | Mandatory/Optional | Visibility  |
| -------------------------- | --------------------------- | ------------------------------------------------------------------ | ------------------ | ----------- |
| Campaign & Journey Reports | Campaign Reports            | Daily/weekly campaign performance reports                          | Optional           | All users   |
| Campaign & Journey Reports | Journey Reports             | Journey and project activity reports                               | Optional           | All users   |
| Billing, Usage & Capacity  | Billing & Payments          | Payment receipts, failures, and billing alerts                     | Mandatory          | Admins only |
| Billing, Usage & Capacity  | Usage & Overage Alerts      | Container, MAU, and overage threshold notifications                | Mandatory          | Admins only |
| Billing, Usage & Capacity  | Capacity Alerts             | Events, properties, licensing limits, and email add-on usage       | Mandatory          | Admins only |
| Passcode Alerts            | Passcode Alerts             | Passcode expiry and generation alerts                              | Mandatory          | Admins only |
| Downtime & Outages         | Downtime & Outages          | Scheduled and unscheduled downtime notifications                   | Mandatory          | Admins only |
| Engagement & Collaboration | Segments & Catalogs         | Segment and catalog processing notifications                       | Optional           | All users   |
| Engagement & Collaboration | WhatsApp Notifications      | WhatsApp Connect/Direct add-on and template alerts                 | Optional           | All users   |
| Engagement & Collaboration | Collaboration & Sharing     | Board sharing and team notifications                               | Optional           | All users   |
| Subscription & Account     | Subscription & Plan Changes | Add-on, upgrade, downgrade, and plan trial notifications           | Mandatory          | Admins only |
| Subscription & Account     | Account Settings            | Event, control group, font, dormant profile, and archiving changes | Mandatory          | Admins only |
| Data & Integration         | Data Import/Export          | SFTP, CSV, parse, and export notifications                         | Optional           | All users   |
| Data & Integration         | Other Integrations          | Facebook, domain, and subscription management                      | Optional           | All users   |

## Edit your Preferences

Perform the following steps to edit your preferences:

1. On the Notification tab, click **Edit Preferences** in the top-right corner.
2. Expand any category to view the notification list.
3. Check the alerts you want to start receiving, and uncheck the ones you want to stop receiving.
4. Click **Save Preferences** to apply your changes.

The following image shows how to edit your preferences:


<Image src="https://files.readme.io/97980ee255efa4c50c2e887526c096ac316d331434b38d467e1e518277dcde68-2026-09-02_14-24-51_1.gif" alt="Editing preferences on the Notification tab: Journey Reports unchecked while locked categories such as Billing & Payments stay disabled" align="center" caption="Edit Preferences" border={true} />


CleverTap confirms the update immediately with a message that reads, _Notification preferences for email saved successfully_. Your new preferences are applied.

<br />
