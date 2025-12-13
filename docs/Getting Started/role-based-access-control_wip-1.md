---
title: Role-Based Access Control_WIP
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

As a part of our commitment to account security, CleverTap offers role-based access control (RBAC) for account administrators to enable different levels of access for dashboard users. Enterprise customers can create and assign custom roles with different permissions with advanced RBAC.

> 📘 RBAC for Product Experiences
>
> Role-based access control (RBAC) is now supported for *Product Experiences*. For more information, refer to [Product Experiences](doc:product-experiences).

## Invite Users

1. Navigate to *Settings* > *Users* > *Add User* 

<Image title="2020-05-13_16-08-43_Create User.png" alt={1219} className="border" border={true} src="https://files.readme.io/387c604-2020-05-13_16-08-43_Create_User.png" />

2. Enter the email address and assign the role.

<Image title="Screenshot 2019-04-08 at 1.21.17 PM.png" alt={1064} className="border" border={true} src="https://files.readme.io/ce5e89c-Screenshot_2019-04-08_at_1.21.17_PM.png" />

## User Roles

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

<Image title="2020-05-13_16-12-18_Create Role.png" alt={1235} className="border" border={true} src="https://files.readme.io/c4c349d-2020-05-13_16-12-18_Create_Role.png" />

## Define Access for Basic Custom Roles

When inviting a new user, the administrators can assign a custom role to the user. Administrators can also create a new custom role or clone an existing custom role.

Set up a role by defining two things:

1. Component - Select the component for which you want to grant access.
2. Access levels:

* Read Access - Only allowed to view the feature (e.g., view campaign stats). 
* Write Access - Allowed to read and write the feature (e.g., create campaigns). 

<Image title="2020-05-13_16-21-33_Custom Role.png" alt={1210} className="border" border={true} src="https://files.readme.io/26c2f69-2020-05-13_16-21-33_Custom_Role.png" />

## Custom Roles with Admin Rights

A custom role with *Read* and *Write* permissions under the user settings component can change their own role.

![690](https://files.readme.io/1a96ace-Read_and_Write.png "Read and Write.png")

If this permission is not needed, admins can uncheck the *User Settings* checkbox for the custom role.

![270](https://files.readme.io/17b515b-Custom_roles_on_admin_rights.png "Custom roles on admin rights.png")

## Define Access for Advanced Custom Roles

Custom roles can be mapped to user groups for advanced role-based access control. You can give access to different datasets to various users and restrict access to the data you don't want them to view on the CleverTap dashboard. Administrators can also restrict data access to new custom roles based on selected user properties such as geographies. Users assigned to these roles are limited to only read/write data available to the particular role. 

> 👍 Advanced Custom Role Example
>
> You can grant access to a role *US Campaign Manager* where the role has write access to campaigns for only users in the United States. You cannot create campaigns for users in other geographies.

1. Assign permissions for component access and define which feature components are available to the user role. You can also mask data such as personally identifiable information or events. 

<Image title="Settings_RBAC.png" alt={859} className="border" width="80%" border={true} src="https://files.readme.io/7b90b39-Settings_RBAC.png" />

2. Assign permissions for data access and define the user property data accessible by the user role.

![1369](https://files.readme.io/f0507e1-Mapping_User_Properties.png "Mapping User Properties.png")

## Segment Access

Segment access management in roles gives you the ability to better manage your security, compliance and data management. If you have dashboard users who are responsible for all marketing activities in specific sub-regions, you can grant access to only that segment of users who are from the sub-region.

> 👍 Segment Access Example
>
> You have operations in Spain, Germany, England, Greece, and Italy and each region is managed by a regional manager. You can create a role for each of these regions where access to end-user data is restricted by their geography. In this way, each regional manager will have access to only end-users only from their region.

> 📘 Note
>
> By picking the user property that the role is granted access to, you are restricting access to all data on CleverTap. Even if the role is viewing 'All Users' data, it is default limited to the access restriction for that role. You cannot assign more than one segment role per user.

## Edit, Clone and Delete Custom Roles

![1219](https://files.readme.io/29d8c80-2020-05-13_16-33-51_Edit-Clone.png "2020-05-13_16-33-51_Edit-Clone.png")

> 🚧 Deleting a Role
>
> When a custom role is deleted, all users with this role assignment will be re-assigned as *Member* by default.

![1218](https://files.readme.io/6e7cc0c-2020-05-13_16-35-55_Delete_role.png "2020-05-13_16-35-55_Delete role.png")

## Access Rules and Handling Clashes

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

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Component
      </th>

      <th>
        Subcomponents
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Boards
      </td>

      <td>
        * Daily Boards
        * Custom Boards
      </td>
    </tr>

    <tr>
      <td>
        Segments
      </td>

      <td>
        * **Manual segmentation**: Segments, Find People
        * **Automated segmentation**: Goals, IBM, RFM
      </td>
    </tr>

    <tr>
      <td>
        Analytics
      </td>

      <td>
        * **Core Analytics**: Events, Funnels, Cohorts, Trends, Attribution, Device Crossovers
        * **Advanced Analytics**: Pivots, Flows
      </td>
    </tr>

    <tr>
      <td>
        Engagement
      </td>

      <td>
        * **Campaigns**: Campaigns, Clever Campaigns

        - **Journeys**
        - **Recommendation**
        - **Catalogs**
      </td>
    </tr>

    <tr>
      <td>
        Real Impact
      </td>

      <td>
        * **Control groups**: Custom Control Group, System Control Group

        - **Real Impact dashboard**
      </td>
    </tr>

    <tr>
      <td>
        Settings
      </td>

      <td>
        * **Billing**: Billing, app usage, plans, invoices
        * **Account Settings**: Role Based Access Control, add new app, change account, timezone, privacy settings, uninstall
        * **User Settings**: Invite user, revoke access, account settings&#x9;

        - **Event and User Properties**&#x9;

        * **CSV Uploads**: Profile uploads and external user list&#x9;

        - **My Profile And Password**

        * **Exports**: Events and profile exports to amazon S3
        * **Downloads**: Download profiles
        * **Email Reports**: Campaign and Journey reports&#x9;
        * **Campaign Integration and Settings**: Push, Email, SMS, Web Push, FB, Google AdWords
        * **Campaign Settings**: Campaign limits, Best Time settings
      </td>
    </tr>
  </tbody>
</Table>
