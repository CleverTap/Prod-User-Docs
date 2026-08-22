---
title: Role-Based Access Control
excerpt: ''
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

As part of our continued commitment to account security and effective collaboration, CleverTap provides Role-Based Access Control (RBAC) to help administrators manage user access across the dashboard.

RBAC enables you to assign role-specific permissions, ensuring that each team member, agency partner, or regional stakeholder has access only to the features and data relevant to their responsibilities. With granular access controls, organizations can manage campaigns, data visibility, and account settings securely and efficiently.

# Invite Users and Assign Roles

The admin must invite new users to assign roles and can also reassign existing users' roles. For more information about inviting users to the dashboard, refer to [Manage Users](doc:manage-users#invite-users).

# Components of Access

The following table outlines the available components and their respective subcomponents that can be permissioned when setting up or modifying a role. There are two types of roles: System and Custom. System roles are pre-defined and cannot be changed. For custom roles, an _Admin_ role can configure or assign access to these roles.

| **Component**                    | **Subcomponents**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Boards**                       | • _System Boards_ <br /> • _Custom Boards_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Segments**                     | • _Manual Segmentation_: Segments, Find People <br /> • _Automated Segmentation_: Goals, IBS, RFM                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Analyze**                      | • _Core Analytics_: Events, Funnels, Cohorts, Trends, Attribution, Device Crossovers <br /> • _Advanced Analytics_: Pivots, Flows                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Engage**                       | • _Campaigns_: Channel Campaigns<br /> • _Journeys_ <br /> • _Recommendations_ <br /> • _Catalogs_ <br /> • _Global Campaign Limit (GCL)_: Define the maximum number of campaigns that can run concurrently <br /> • _Global Throttle Limit (GTL)_: Control the number of messages sent per user per day <br /> • _Bulletins_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Real Impact**                  | • _Control Groups_: Custom Control Group, System Control Group <br /> • _Real Impact Dashboard_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Settings**                     | • _Billing_: Billing, app usage, plan, invoices <br /> • _Account Settings_: Add new app, change account, timezone, privacy settings <br /> • _User Settings_: Invite user, revoke access, passcode settings <br /> • _CSV Uploads_: Profile uploads, external user list <br /> • _My Profile and Password_ <br /> • _Exports_: Event and profile exports to Amazon S3 <br /> • _Downloads_: Download profile <br /> • _Email Reports_: Campaign and Journey reports <br /> • _Campaign Integration and Settings_: Push, Email, SMS, Web Push, Facebook, Google AdWords <br /> • _Campaign Settings_: Campaign limits, best time settings <br /> • _SFTP Imports_: Event and profile imports via SFTP <br /> • _SSO Settings_: Enable/disable SAML SSO <br /> • _GCS Exports_: Event and profile exports to Google Cloud Storage <br /> • _Custom List Segment_ <br /> • _Session Analytics_: Enable session tracking <br /> • _Geofences_: Create geofence clusters <br /> • _Attribution Partner Settings_ <br /> • _MIXPANEL Exports_: Event exports to Mixpanel <br /> • _Amplitude Exports_: Event exports to Amplitude <br /> • _Mparticle Exports_: Event and profile exports to Mparticle <br /> • _Security_: IP Whitelisting, 2FA <br /> • _Segment Exports_: Event exports to Segment.io <br /> • _Azure Exports_: Event and profile exports to Azure Blob Storage <br /> • _Role Settings_: Role-based access control <br /> • _CDP Imports_: Event and profile imports from external datasource |
| **Others**                       | • _User Profile Management_: Delete user, de-merge user, mark as test <br /> • _Error Stream_: Error stream                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Schema**                       | • _Event and Profile Properties Schema_ <br /> • _Conversion Event_ <br /> • _Qualifying Event_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Optimization Features**        | • _Lifecycle Optimizer_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Product Experiences (Legacy)** | • _Setup_: Legacy Setup <br /> • _Experiences & Experiments_: Legacy Experiences & Experiments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **CMS**                          | • _Files_: CMS Files <br /> • _Templates_: CMS Templates                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Product Experiences**          | • _Remote Config & A/B tests_: Remote Config, A/B tests                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Promotions**                   | No sub-options                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

# Types of Roles

Roles in CleverTap can be broadly categorized as System Roles and Custom Roles. The following sections discuss each of these roles in detail.

## System Roles in CleverTap

CleverTap provides four standard system roles. These roles are predefined and _cannot be cloned, deleted, or edited_.

<Table>
  <thead>
    <tr>
      <th>
        **Role**
      </th>

      <th>
        **Description**
      </th>

      <th>
        **Key Permissions**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Admin**
      </td>

      <td>
        Full and unlimited access to the account.
      </td>

      <td>
        - Assign users to any role (Admin, Creator, Member, or Custom)  <br /> - Revoke user access  <br /> - Create, stop, and archive campaigns  <br /> - Approve/reject campaigns from Creators  <br /> - View analytics  <br /> - Download user profiles and reports  <br /> - Add/update billing details  <br /> - Modify event and profile schema  <br /> - Manage security settings (IP Whitelisting, 2FA, Campaign Approval Workflow)
      </td>
    </tr>

    <tr>
      <td>
        **Creator**
      </td>

      <td>
        Create and manage all types of engagement (campaigns, journeys, product experiences).
      </td>

      <td>
        - Create, stop, and delete engagements  <br /> - View analytics  <br /> - Download reports  <br /> -_Cannot revoke user access or view billing details_.
      </td>
    </tr>

    <tr>
      <td>
        **Member**
      </td>

      <td>
        Read-only access to view analytics and reports.
      </td>

      <td>
        - View campaign performance  <br /> - Access dashboards and reports
      </td>
    </tr>

    <tr>
      <td>
        **Approver**
      </td>

      <td>
        Approve campaigns created by users in the Creator role.
      </td>

      <td>
        - Assign users to Creator, Member, or Custom Roles  <br /> - Create, stop, and archive campaigns  <br /> - Approve/reject campaigns from Creators  <br /> - View analytics  <br /> - Download user profiles and reports
      </td>
    </tr>

    <tr>
      <td>
        **Agent**
      </td>

      <td>
        Read-only access to view analytics and reports. Access to Conversations.
      </td>

      <td>
        Replying to customer chats, ticket statuses, and managing chats with users. No access to campaign, billing, and so on. For more information, refer to [Conversations](https://docs.clevertap.com/docs/conversations) .
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Note
>
> The Approver role can only be accessed when the [Campaign Approval Workflow](https://docs.clevertap.com/docs/campaign-approval-workflow) feature is turned on.

## Custom Roles

Custom Roles in CleverTap allow administrators to define and assign precise access controls based on specific business needs. You can configure permissions at a granular level—across components, engagement features, and data access—ensuring that each user has access only to what’s relevant to their role. Custom Roles are of two types:

- _Basic Custom Role_: Allows you to provide access to dashboard components and engagement permissions.
- _Advanced Custom Role_: Allows you to define data access at a granular level, as well as dashboard components and engagement permissions.

# Define Access for Custom Roles

Once a custom role is created, administrators can configure specific permissions for components, engagement features, and data access to ensure each user has appropriate and secure access based on their responsibilities.

## Define Access for Basic Custom Roles

Basic Custom Roles refer to user-defined roles that are not tied to advanced data segmentation or user property filters. These roles allow you to control access at the component level—such as Boards, Campaigns, or Analytics—based on standard read/write permissions.

Administrators can assign a Basic Custom Role when inviting new users or by cloning and modifying an existing role.

To define a Basic Custom Role, configure the following:

- _Access Level_ :
  - Read Access: Grants view-only access to the selected component. Users can see the data (such as campaign statistics) but cannot make changes or download content.
  - Write Access: Grants full access to create, edit, and manage the selected component, including modifying configurations such as throttle limits.
- _Component_: Choose the feature or module (such as Campaigns or Journeys) to which the user should have access.
- _Engagement Permissions_: Use this setting to control which roles can engage with users through specific channels and apply global campaign or throttle limits as required.
- _Data Access_: Provide users access to different datasets and restrict access to the data you do not want them to view on the CleverTap dashboard.

### Component Access

You can assign granular permissions to the users for each component. Define which components are available to the user role. You can specify whether the users must have complete or restricted access to Campaigns and Journeys. For more information, refer to [Components of Access](doc:role-based-access-control-advance-governance#components-of-access).


<Image src="https://files.readme.io/d2ea0b423c0110329211f10128bb02901c3794fbfa6ccc7d2e28d76140e3b522-image.png" alt="Provide Component Access" align="center" caption="Provide Component Access" border={true} />


### Data Access

You can restrict the customer data accessible to users in a role. Define whether users can access data for all users or only for users that match specific property conditions.

1. Assign permissions for component access and define which feature components are available to the user role.
2. (Optional) Mask personally identifiable information or events.


<Image src="https://files.readme.io/1af497f814be9cf7d8d455df901c684d70784f7e433a271a50d20c98eaac2b8c-image.png" align="center" caption="Masking - Visible" border={true} />


Users assigned to a role control how sensitive data appears to them through the _Masked Properties_ setting. With the _Visible_ toggle, users can view masked data fields in plain text. With the _Masked_ toggle, users see the data in its masked form and cannot view the original content.


<Image src="https://files.readme.io/5337f8b0cb175cc859d0ef860f119ae6a0ca17eecb4fba468a925e9dca709f1a-image.png" align="center" caption="Masking - Masked" border={true} />


3. Assign permissions for data access and define the user property data accessible by the user role.


<Image src="https://files.readme.io/48280be8f79416863dd18df52ca1ff4de120eb52208392dcb92802a30897c77d-Data_Access.png" alt="1369" align="center" caption="Map User Properties" border={true} />


<br />


<Image src="https://files.readme.io/bd9bed1198633873aef028c7555db50359ce1a408ad201ca8a53b3c3ff38da14-Overview.png" alt="Overview of Data Access" align="center" caption="Overview of Data Access" border={true} />


### Engagement Permissions

This tab is visible only to roles with _Write_ access to engagement components, such as Campaigns and Journeys. You can define the Limits and Channel access from this tab.


<Image src="https://files.readme.io/4882c07e60aac57d6f21b8a884f4cc4b65949b9205cc4a37e5d61f9de8123a3c-image.png" alt="Limits and Channels Permissions" align="center" caption="Limits and Channels Permissions" border={true} />


#### Global Campaign and Throttle Limit Access

Administrators can define whether users can modify limits for campaigns and journeys, ensuring better control over engagement volume and compliance.

The following table explains the Global Campaign and Throttle Limit for user roles when creating or editing an engagement, that is, Campaigns or Journeys:

| Read | Write | Apply by Default in Engagements | User Access Provided                                                                                                                                                                                                                                                     |
| :--- | :---- | :------------------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Yes  | Yes   | Yes                             | The limit is applied by default. Users can choose to enable or disable it based on the use case. For example, a team member sending both transactional and promotional messages can choose to apply limits only to promotional campaigns.                                |
| Yes  | No    | Yes                             | The limit is applied by default for this role. Users can view the specified limit but cannot modify it. For example, a marketer sending regular promotional messages can see the applied limits but cannot adjust them, ensuring adherence to predefined sending limits. |
| Yes  | Yes   | No                              | The limit is not applied by default. Users can choose to apply the limit if needed. For example, a team member who mainly sends transactional messages but occasionally runs promotional campaigns can enable limits when required.                                      |
| Yes  | No    | No                              | No limits are applied. Users can view the limit but cannot change it. For example, a team member responsible for transactional messages does not have limits enforced to ensure critical communication is always sent.                                                   |

You can view the impact of assigned permissions when creating campaigns or journeys. For more information, refer to  [Global Campaign and Throttle Limits](https://docs.clevertap.com/docs/global-campaign-and-throttle-limits-permissions).

#### Channel Level Access

Channel-level access lets administrators control which users can view or manage campaigns and journeys for specific communication channels such as Push Notifications, Emails, SMS, Web Push, App Inbox, and so on. In multi-team setups, not every user needs access to every channel. Channel-level permissions help teams collaborate effectively by controlling who can view or modify campaigns within each channel, ensuring users interact only with channels relevant to their role or team.

A user should first have access to the Campaigns or Journeys in general. From there, their channel-level permissions determine their role within each channel:

- **Read access**: Users with read access to Campaigns or Journeys can view content across all channels. This ensures a consistent experience within Journeys.
- **Write access**: If users have write access to Campaigns or Journeys, they can create, edit, clone, publish, or delete content, but only for channels where they have been explicitly granted channel-level write access.

> 📘 Channel Write Restrictions
>
> - For example, if a user role has write access to Push Notifications but not to Emails, the user can:
>   - Create and edit Push Notification campaigns.
>   - View Email campaigns but cannot create, edit, or clone them.
>   - Drag and drop only Push Notification nodes (not Email nodes) inside Journeys.
>   - Campaign actions such as labeling, archiving, pausing, stopping, and publishing can only be performed on Push Notification campaigns.

If a user does not have the necessary permissions to access campaigns or journeys, contact the admin to request access.


<Image src="https://files.readme.io/5a04d9f08557d3ed7705766c495c01a1f91c92c540e798003dae802dbe706ba5-image.png" alt="Limited Access Error" align="center" width="45%" caption="Limited Access Error" border={true} />


## Define Access for Advanced Custom Roles

Custom roles can be mapped to user groups for advanced role-based access control. You can give various users access to different datasets and restrict access to the data you do not want them to view on the CleverTap dashboard. Administrators can also restrict data access to new custom roles based on selected user properties, such as geographies. Users assigned to these roles are limited to only reading or modifying the data available to the particular role.<br />For example, you can grant the _US Campaign Manager_ role write access to campaigns only for United States users. This role cannot create campaigns for users in other geographies.

> 📘 Private Beta
>
> Currently, this is a Private Beta Release. If you want access to this feature, contact your Account Manager.

### Data Access and Segment Restrictions

The Advanced Custom Roles allow configuring Data Access permissions. In addition to the [Components Access](https://docs.clevertap.com/docs/role-based-access-control#component-access) and [Engagement Permissions](https://docs.clevertap.com/docs/role-based-access-control#engagement-permissions) tab, the Data Access tab allows you to define which users a role can view and interact with on the CleverTap dashboard.

You can choose to grant access to all users or apply filters using user properties or predefined segments to restrict access.

This functionality helps enforce role-based data visibility, which is particularly useful for distributed teams, regional ownership, and compliance-driven environments.

<details>
<summary><strong>Example 1: Regional Access by User Property</strong></summary>

A regional marketing manager for France is assigned a role with a user property filter where `Country = France`. Even when viewing "All Users" reports, the manager will only see data related to users in France. Information from other regions remains inaccessible.

</details>

<details>
<summary><strong>Example 2: Segment-Based Access</strong></summary>

A custom role is restricted to:

- Users in the segment _Engaged Users – at least 4 times_
- Users with the `Customer Type = Gold`

This ensures that the user can only access data for a specified user base, even when broad filters such as _All Users_ are selected.


<Image src="https://files.readme.io/f62296e501c9f46c71b55f805bed20ce877d6f369ac56638d3654a5e34e923b4-image.png" align="center" caption="Map User Properties and Events" border={true} />


> 📘 **Note**
>
> When you restrict access using a user property or segment, the limitation applies globally—even if the role attempts to view _All Users_.
>
> You _cannot assign more than one segment role per user_.

### Masking Personally Identifiable Information and Events

This option allows you to mask personal information, such as Email, Phone number, Location, Gender, User properties, and other sensitive data, as well as the event activity of a user profile for a specific user role. For more information, refer to [PII Masking](https://docs.clevertap.com/docs/pii-masking).

### Access Overview

The _Overview&#x20;_&#x74;ab provides a summary of the role configuration, including role name, assigned permissions, data access settings, and engagement limits. This view allows administrators to quickly review and validate all access controls before finalizing the custom role.


<Image src="https://files.readme.io/429c0d7eb339cbe7aa0d34bf17bb05e0d50f57bf767f136d58d9fe32c151467e-image.png" align="center" caption="Role Overview" border={true} />


# Create Custom Roles

To create a custom role, perform the following steps:

1. Navigate to _Settings_ > _Roles_ from the dashboard.
2. Click **Create Role**.


   <Image src="https://files.readme.io/e11fe26a29c4d603936cbc2073e919a2b75525de36bf1f8a27c9606c8d8a0077-image.png" align="center" caption="Create New Role" border={true} />


3) The _Create Role_ page appears. Select the required permissions for each tab and click **Next** when done.
4) In the final step, specify the name and click **Create** to add the new role. The Overview tab displays permissions assigned to the new role.

# Manage Custom Roles

You can edit, clone, or delete custom roles. To edit, clone, or delete a role, hover over the role and select the corresponding icon.


<Image src="https://files.readme.io/bbc503426c5f5508969bfd86cb7bf2fb77244764e89cc88e4ff9ded187ffb1aa-image.png" alt="Role Operations" align="center" caption="Role Operations" border={true} />


## Handle Access Conflicts

Permissions and access can be set while creating a custom role. The following order of preference applies.

- **Role Assignment**: A user can only be assigned system role(s) and custom role(s).
- **Permission Conflict on System Roles**: When a user is assigned multiple system roles, a permission conflict occurs, and the role with the higher access level is enabled. For example, if a user is assigned both Admin and Creator roles, Admin access is enabled. Thus, a user cannot have multiple system roles enabled simultaneously.
- **Component Conflict between System Role and Custom Role**: When a user is assigned both a system role and a custom role, there may be situations in which one role grants access to a component, while the other does not. In this case, the permissions will be a union. For example, a user has two roles: “Creator” and “Custom B.” Role Creator has write access to Campaigns, while role Custom B does not have access to Campaigns. In this scenario, write access is granted.
- **Component Conflict on Custom Roles**: When a user is assigned multiple custom roles, there can be situations where one role has access to a component, and another role does not allow access to the same component. In this case, the permissions are restricted to the intersection of the roles. For example, a user has two roles: “Custom A” and “Custom B.” Role Custom A has write access to Campaigns, while role Custom B does not have access to Campaigns. In this scenario, the user will not have write access to the Campaigns.


<Image src="https://files.readme.io/2ca1e03-Jash-Deepen-Document-v1.png" alt="Permission Clash For Custom Roles" align="center" caption="Permission Conflict for Custom Roles" border={true} />


# Enforcement Across Campaign Actions

Users can view all channels while creating or managing campaigns, but can only take action (create, edit, clone, stop, archive, label, or publish) on campaigns for channels where they have write access. Restricted channels are visible but disabled. RBAC is enforced across all entry points (for example, Listings, Segments, Analytics, or URL access).

- **Bulk actions** (like stop, archive, or label) fail entirely if any selected campaign is unauthorized.
- **Cloning** is only allowed if the user has write access to all channels used in the original campaign.
- **Push + App Inbox**: If the user does not have write access for App Inbox, the option to send it with Push is disabled.
- **Direct URL access** is validated against RBAC before allowing publish or edit.
- **Campaigns created via API** are not restricted by RBAC settings.

# General Rules of Access

These rules define how CleverTap applies access controls across system and custom roles. Understanding these guidelines helps ensure roles are assigned appropriately and that permissions are enforced consistently across the platform.

- Any role with write access automatically includes read access.
- A user can have only one system role at a time.
- A user can be assigned multiple custom roles, with one important exception: If a custom role includes data access restrictions based on user properties (such as geography or customer tier), the user can only be assigned one such role.<br />For example, if one custom role is restricted to users in the U.S. and another to users in India, the user can be assigned only one of these roles. This ensures that data access remains isolated to a single segment and prevents overlapping access.
- Users can hold one system role and multiple custom roles (excluding filtered roles).

# FAQs

<details>
<summary>Do RBAC settings apply to campaigns created via API?</summary>

No, RBAC restrictions for campaigns do not apply to API-created campaigns.

</details>

<details>
<summary>What happens if a user has multiple roles with conflicting channel access?</summary>

- If one role grants <strong>write access</strong> and another does not, the most restrictive permission is applied.
- For example, if Role A grants write access and Role B is read-only, the user will only have <strong>read-only</strong> access.

</details>

<details>
<summary>Will users with restricted channel access still be able to view campaigns and journey setups?</summary>

Yes. All users have <strong>read or view-only access</strong> to all campaign channels by default. This helps them view multi-channel Conversations only — replying, ticket statuses, managing chats with users. No campaign or billing etc.setups (such as in journeys) even if they can’t edit them. However, they cannot create, edit, clone, or publish campaigns for channels where write access is restricted.

</details>

<details>
  <summary>Can users with restricted channel access create campaigns or journeys from Analytics or Segments?</summary>

No. If a user does not have write access to Campaigns and Journeys, CleverTap blocks them from creating campaigns directly from the Analytics or Segments sections.<br />An error message is shown when the user tries to initiate the action.

</details>

<br />
