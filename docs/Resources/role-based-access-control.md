---
title: Role Based Access Control
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
[block:api-header]
{
  "title": "Introduction"
}
[/block]
As a part of our security strategy, CleverTap has introduced Role Based Access Control (RBAC) to allow defined, relevant and organised access to the dashboard users. You can now create and assign custom roles with different permissions. There are **three** standard system roles (Admin, Creator, Member) to begin with.
[block:api-header]
{
  "title": "Inviting Users"
}
[/block]
**Step 1:** Go to settings -> Users -> Invite User
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21c4a08-Screenshot_2019-04-08_at_1.19.58_PM.png",
        "Screenshot 2019-04-08 at 1.19.58 PM.png",
        1424,
        669,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 2: ** Enter the email address and assign the role
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce5e89c-Screenshot_2019-04-08_at_1.21.17_PM.png",
        "Screenshot 2019-04-08 at 1.21.17 PM.png",
        1064,
        616,
        "#919193"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "User Roles"
}
[/block]
## System Roles

CleverTap provides 3 predefined roles for every account. These are the roles that your account will have access to even if you do not create any other role. These roles cannot be cloned, deleted or edited -

1. **Admin**: Has full and unlimited access to the account.

 * Invite new users with Admin, Creator or Member role.
 * Revoke access of an existing user.
 * Create campaigns.
 * Stop and archive campaigns.
 * Approve or reject campaigns created by users in the Creator role.
 * View analytics.
 * Download user profiles.
 * Download reports.
 * Add and update billing details.

2. **Creator**: A Creator user has access to create, edit, schedule, and stop notification campaigns.
 
   * Create campaigns.
   * Stop and delete campaigns.
   * View analytics
   * Download reports.
   * A Creator cannot revoke user access or view billing information.


3. **Member**: A Member user has access to view analytics and reports in the account.

   * Read only access
   * View analytics, including campaign performance.

[block:callout]
{
  "type": "info",
  "title": "Custom Roles",
  "body": "Custom Roles is a part of CleverTap's 'Big Company Pack'. Connect with support@clevertap.com for more information"
}
[/block]
## Custom Roles: 

Go to settings -> Roles -> Add role

**Creating a custom role**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1057075-Screenshot_2019-04-08_at_7.08.57_PM.png",
        "Screenshot 2019-04-08 at 7.08.57 PM.png",
        1440,
        789,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
**Defining access for custom roles** 

While inviting a new user, you can assign a custom role to the user. You can either create a new custom role or clone an existing custom role.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/56ea521-Screenshot_2019-04-08_at_7.18.34_PM.png",
        "Screenshot 2019-04-08 at 7.18.34 PM.png",
        1417,
        783,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
**Edit, Clone and Delete Custom Roles**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04612ae-Screenshot_2019-04-08_at_7.15.57_PM.png",
        "Screenshot 2019-04-08 at 7.15.57 PM.png",
        1423,
        693,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Deleting a role",
  "body": "When a custom role is deleted, all users with this role assignment will be re-assigned as \"member\" by default."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/abae9e1-Screenshot_2019-04-08_at_7.21.06_PM.png",
        "Screenshot 2019-04-08 at 7.21.06 PM.png",
        1420,
        688,
        "#a5a5a6"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Access rules and handling clashes"
}
[/block]
Permissions and access can be set while creating a custom role. Following order of prevalence will apply.

  * A user can only be assigned a system role and a custom role(s)
  * **Permission Clash**: In case of multiple roles, if there is a permission clash, the most restricted access will apply (if a user is assigned multiple custom roles, only most restricted role will be authorised).
E.g.: A user has roles A and B. A allows read access to campaigns while B allows write access to campaigns. By the rule of ‘most restricted access trumps’, user will only be able to read campaigns.
  * **Component Clash**: In case of multiple custom roles, there can be cases where one role has access to a component while the other does not allow access to the same component. In this case, the user will have access to the component.
E.g.: A user has roles A and B. A allows Advanced Analytics (with write access) while B does not allow Advanced Analytics. In this case, user will have write access to Advanced Analytics component.

## General rules of access
  * Any write access will automatically give read access to the user.
  * There cannot be a user who has no role.
  * A user cannot have multiple system roles.
  * A user can have access to both system and custom role at the same time (Limited to one system role, no limit on multiple custom roles).
  * A user can have access to multiple custom roles.
  * System roles cannot be edited.

## Components of Access##

Only the admin role can edit the access of custom roles. 
[block:parameters]
{
  "data": {
    "h-0": "Component",
    "h-1": "Subcomponents",
    "0-0": "Boards",
    "1-0": "Segments",
    "2-0": "Analytics",
    "3-0": "Engagement",
    "4-0": "Real Impact",
    "5-0": "Settings",
    "6-0": "Others",
    "0-1": "* **System Boards**\n* **Custom Boards** ",
    "1-1": "* **Manual segmentation**: Segments, Find People\n* **Automated segmentation**: Goals, IBM, RFM",
    "2-1": "* **Basic Analytics**: Events, Funnels, Cohorts, Trends, Attribution, Device Crossovers\n* **Advanced Analytics**: Pivots, Flows ",
    "3-1": "* ** Campaigns**: Campaigns, Clever Campaigns\n* **Journeys**\n* **Recommendation**\n* **Catalogs**",
    "4-1": "* **Control groups**: Custom Control Group, System Control Group\n* **Real Impact dashboard** ",
    "5-1": "* **Billing**: Billing, app usage, plans, invoices\n* **Account Settings**: Role Based Access Control, add new app, change account, timezone, privacy settings, uninstall\n* **User Settings**: Invite user, revoke access, account settings\t\n* **Event and User Properties**\t\n* **CSV Uploads**: Profile uploads and external user list\t\n* **My Profile And Password\t**\n* **Exports**: Events and profile exports to amazon S3\n* **Downloads**: Download profiles\n* **Email Reports**: Campaign and Journey reports\t\n* **Campaign Integration and Settings**: Push, Email, SMS, Web Push, FB, Google AdWords\n* **Campaign Settings**: Campaign limits, Best Time settings",
    "6-1": "Delete user, De-merge user, Mark as test"
  },
  "cols": 2,
  "rows": 7
}
[/block]