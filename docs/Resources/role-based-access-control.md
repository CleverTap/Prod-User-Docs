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
## Introduction

As a part of our security strategy, CleverTap has introduced Role Based Access Control (RBAC) to allow defined, relevant and organised access to the dashboard users. You can now create and assign custom roles with different permissions. There are **three** standard system roles (Admin, Creator, Member) to begin with.

## Inviting Users

**Step 1:** Go to settings -> Users -> Invite User

<Image title="Screenshot 2019-04-08 at 1.19.58 PM.png" alt={1424} className="border" border={true} src="https://files.readme.io/21c4a08-Screenshot_2019-04-08_at_1.19.58_PM.png" />

**Step 2:** Enter the email address and assign the role

<Image title="Screenshot 2019-04-08 at 1.21.17 PM.png" alt={1064} className="border" border={true} src="https://files.readme.io/ce5e89c-Screenshot_2019-04-08_at_1.21.17_PM.png" />

## User Roles

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

> 📘 Custom Roles
>
> Custom Roles is a part of CleverTap's 'Big Company Pack'. Connect with [support@clevertap.com](mailto:support@clevertap.com) for more information

## Custom Roles:

Go to settings -> Roles -> Add role

**Creating a custom role**

<Image title="Screenshot 2019-04-08 at 7.08.57 PM.png" alt={1440} className="border" border={true} src="https://files.readme.io/1057075-Screenshot_2019-04-08_at_7.08.57_PM.png" />

**Defining access for custom roles** 

While inviting a new user, you can assign a custom role to the user. You can either create a new custom role or clone an existing custom role.

<Image title="Screenshot 2019-04-08 at 7.18.34 PM.png" alt={1417} className="border" border={true} src="https://files.readme.io/56ea521-Screenshot_2019-04-08_at_7.18.34_PM.png" />

**Edit, Clone and Delete Custom Roles**

![1423](https://files.readme.io/04612ae-Screenshot_2019-04-08_at_7.15.57_PM.png "Screenshot 2019-04-08 at 7.15.57 PM.png")

> 🚧 Deleting a role
>
> When a custom role is deleted, all users with this role assignment will be re-assigned as "member" by default.

<Image title="Screenshot 2019-04-08 at 7.21.06 PM.png" alt={1420} className="border" border={true} src="https://files.readme.io/abae9e1-Screenshot_2019-04-08_at_7.21.06_PM.png" />

## Access rules and handling clashes

Permissions and access can be set while creating a custom role. Following order of prevalence will apply.

* A user can only be assigned a system role and a custom role(s)
* **Permission Clash**: In case of multiple roles, if there is a permission clash, the most restricted access will apply (if a user is assigned multiple custom roles, only most restricted role will be authorised).\
  E.g.: A user has roles A and B. A allows read access to campaigns while B allows write access to campaigns. By the rule of ‘most restricted access trumps’, user will only be able to read campaigns.
* **Component Clash**: In case of multiple custom roles, there can be cases where one role has access to a component while the other does not allow access to the same component. In this case, the user will have access to the component.\
  E.g.: A user has roles A and B. A allows Advanced Analytics (with write access) while B does not allow Advanced Analytics. In this case, user will have write access to Advanced Analytics component.

## General rules of access

* Any write access will automatically give read access to the user.
* There cannot be a user who has no role.
* A user cannot have multiple system roles.
* A user can have access to both system and custom role at the same time (Limited to one system role, no limit on multiple custom roles).
* A user can have access to multiple custom roles.
* System roles cannot be edited.

## Components of Access#\#

Only the admin role can edit the access of custom roles. 

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
        * **System Boards**
        * **Custom Boards** 
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
        * **Basic Analytics**: Events, Funnels, Cohorts, Trends, Attribution, Device Crossovers
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

    <tr>
      <td>
        Others
      </td>

      <td>
        Delete user, De-merge user, Mark as test
      </td>
    </tr>
  </tbody>
</Table>
