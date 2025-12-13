---
title: Role-Based Access Control
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
  "title": "Overview"
}
[/block]
As a part of our commitment to account security, CleverTap offers role-based access control (RBAC) for account administrators to enable different levels of access for dashboard users. Enterprise customers can create and assign custom roles with different permissions with advanced RBAC.
[block:callout]
{
  "type": "info",
  "title": "RBAC for Product Experiences",
  "body": "Role-based access control (RBAC) is now supported for *Product Experiences*. For more information, refer to [Product Experiences](doc:product-experiences)."
}
[/block]

[block:api-header]
{
  "title": "Invite Users"
}
[/block]
1. Navigate to *Settings* > *Users* > *Add User* 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/387c604-2020-05-13_16-08-43_Create_User.png",
        "2020-05-13_16-08-43_Create User.png",
        1219,
        603,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
2. Enter the email address and assign the role.
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

CleverTap provides three standard system roles for every account. These roles cannot be cloned, deleted, or edited.

1. **Admin**: Full and unlimited access to the account.

 * Assign new users as Admin, Creator, or Member.
 * Revoke access of an existing user.
 * Create campaigns.
 * Stop and archive campaigns.
 * Approve or reject campaigns created by users in the Creator role.
 * View analytics.
 * Download user profiles.
 * Download reports.
 * Add and update billing details.

2. **Creator**: Create, edit, schedule, and stop any type of engagement such as campaigns, journeys, and product experiences.
 
 * Create engagements.
 * Stop and delete engagements.
 * View analytics.
 * Download reports.
 * A Creator cannot revoke user access or view billing information.

3. **Member**: View analytics and reports in the account.

 * Read-only access.
 * View analytics, including campaign performance.


## Custom Roles 
To create a custom role, perform the following steps:
1. Navigate to *Settings* > *Roles*.  
2. Click **+Role**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4c349d-2020-05-13_16-12-18_Create_Role.png",
        "2020-05-13_16-12-18_Create Role.png",
        1235,
        725,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
## Define Access for Basic Custom Roles

When inviting a new user, the administrators can assign a custom role to the user. Administrators can also create a new custom role or clone an existing custom role.

Set up a role by defining two things:

1. Component - Select the component for which you want to grant access.
2. Access levels:

  * Read Access - Only allowed to view the feature (e.g., view campaign stats). 
  * Write Access - Allowed to read and write the feature (e.g., create campaigns). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/26c2f69-2020-05-13_16-21-33_Custom_Role.png",
        "2020-05-13_16-21-33_Custom Role.png",
        1210,
        719,
        "#f6f7f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Define Access for Advanced Custom Roles

Custom roles can be mapped to user groups for advanced role-based access control. You can give access to different datasets to various users and restrict access to the data you don't want them to view on the CleverTap dashboard. Administrators can also restrict data access to new custom roles based on selected user properties such as geographies. Users assigned to these roles are limited to only read/write data available to the particular role. 
[block:callout]
{
  "type": "success",
  "body": "You can grant access to a role *US Campaign Manager* where the role has write access to campaigns for only users in the United States. You cannot create campaigns for users in other geographies.",
  "title": "Advanced Custom Role Example"
}
[/block]
1.  Assign permissions for component access and define which feature components are available to the user role. You can also mask data such as personally identifiable information or events. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b90b39-Settings_RBAC.png",
        "Settings_RBAC.png",
        859,
        1673,
        "#fafafb"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
2. Assign permissions for data access and define the user property data accessible by the user role.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f0507e1-Mapping_User_Properties.png",
        "Mapping User Properties.png",
        1369,
        631,
        "#f7f8f8"
      ],
      "caption": ""
    }
  ]
}
[/block]
## Segment Access
Segment access management in roles gives you the ability to better manage your security, compliance and data management. If you have dashboard users who are responsible for all marketing activities in specific sub-regions, you can grant access to only that segment of users who are from the sub-region.
[block:callout]
{
  "type": "success",
  "body": "You have operations in Spain, Germany, England, Greece, and Italy and each region is managed by a regional manager. You can create a role for each of these regions where access to end-user data is restricted by their geography. In this way, each regional manager will have access to only end-users only from their region.",
  "title": "Segment Access Example"
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "By picking the user property that the role is granted access to, you are restricting access to all data on CleverTap. Even if the role is viewing 'All Users' data, it is default limited to the access restriction for that role. You cannot assign more than one segment role per user."
}
[/block]

## Edit, Clone and Delete Custom Roles
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29d8c80-2020-05-13_16-33-51_Edit-Clone.png",
        "2020-05-13_16-33-51_Edit-Clone.png",
        1219,
        630,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Deleting a Role",
  "body": "When a custom role is deleted, all users with this role assignment will be re-assigned as *Member* by default."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e7cc0c-2020-05-13_16-35-55_Delete_role.png",
        "2020-05-13_16-35-55_Delete role.png",
        1218,
        634,
        "#a1a0a1"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Access Rules and Handling Clashes"
}
[/block]
Permissions and access can be set while creating a custom role. The following order of preference applies.

  * A user can only be assigned a system role and a custom role(s).
  * **Permission Clash**: When a user is assigned multiple roles, there is a permission clash and the role with the lower access level is enabled. For example, if a user is assigned both Admin and Creator roles, the Creator access is enabled.
  * **Component Clash**: In the case of multiple custom roles, there can be situations when one role has access to a component and another role does not allow access to the same component. For example, a user has two roles: “A” and “B.” Role A has write access for Product Experiences while role B does not have access to Product Experiences. In this scenario, the user will still have write access to the Product Experiences.

## General rules of access
  * Any write access automatically gives read access to the user.
  * All users can have multiple custom roles; however, a user cannot have multiple system roles. 
  * A user can have access to both system and custom roles at the same time. They can have one system role and unlimited custom roles. 
  * System roles cannot be altered.

## Components of Access

Only the Admin role can alter and assign access to custom roles. 
[block:parameters]
{
  "data": {
    "h-0": "Component",
    "h-1": "Subcomponents",
    "0-0": "Boards",
    "5-0": "Settings",
    "0-1": "* Daily Boards\n* Custom Boards",
    "5-1": "* **Billing**: Billing, app usage, plans, invoices\n* **Account Settings**: Role Based Access Control, add new app, change account, timezone, privacy settings, uninstall\n* **User Settings**: Invite user, revoke access, account settings\t\n* **Event and User Properties**\t\n* **CSV Uploads**: Profile uploads and external user list\t\n* **My Profile And Password\t**\n* **Exports**: Events and profile exports to amazon S3\n* **Downloads**: Download profiles\n* **Email Reports**: Campaign and Journey reports\t\n* **Campaign Integration and Settings**: Push, Email, SMS, Web Push, FB, Google AdWords\n* **Campaign Settings**: Campaign limits, Best Time settings",
    "1-0": "Segments",
    "2-0": "Analytics",
    "2-1": "* **Core Analytics**: Events, Funnels, Cohorts, Trends, Attribution, Device Crossovers\n* **Advanced Analytics**: Pivots, Flows",
    "1-1": "* **Manual segmentation**: Segments, Find People\n* **Automated segmentation**: Goals, IBM, RFM",
    "3-0": "Engagement",
    "3-1": "* ** Campaigns**: Campaigns, Clever Campaigns\n* **Journeys**\n* **Recommendation**\n* **Catalogs**",
    "4-0": "Real Impact",
    "4-1": "* **Control groups**: Custom Control Group, System Control Group\n* **Real Impact dashboard**"
  },
  "cols": 2,
  "rows": 6
}
[/block]