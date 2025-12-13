---
title: Add Role
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
DOCS NOTES

* BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE ([https://docs.clevertap.com/docs/role-based-access-control](https://docs.clevertap.com/docs/role-based-access-control)) IS UNPUBLISHED (OR DELETED) AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES
* [https://docs.clevertap.com/docs/roles](https://docs.clevertap.com/docs/roles) NEEDS TO BE PUBLISHED AT THE SAME TIME AS THIS PAGE 

## Overview

This section covers how to add a role, component access, and data access.

# Add a Custom Role

To add a custom role, perform the following steps:

1. From the dashboard, navigate to *Settings* > *Roles*.
2. Click **+ Role**.

![1403](https://files.readme.io/7be9e18-Add_a_role_1.png "Add a role 1.png")

3. Review and update the component access as required.
4. Click **Save & Continue**.

![1407](https://files.readme.io/c8857e3-Add_a_role_2.png "Add a role 2.png")

5. Select whether the role can access data for all end users or only selected end users.
6. Click **Save & Continue**. 

![1405](https://files.readme.io/b6201db-Add_a_role_3.png "Add a role 3.png")

7. Review the new added role, then click **Create Role**.

![1409](https://files.readme.io/a3e7e83-Add_a_role_4.png "Add a role 4.png")

8. Enter a role name.
9. Click **Save**.

![491](https://files.readme.io/0aa6c01-Clone_a_role_5.png "Clone a role 5.png")

## Define Access to Components: Basic

When inviting a new user, the admins can assign a custom role to the user. Admins can also create a new custom role or clone an existing custom role.

Set up a role by defining the following two items:

1. Component: Assign permissions for component access and define which feature components are available to the user role. You can also mask data, such as personally identifiable information or events.
2. Access levels: 
   * Read Access: Only allowed to view the feature (e.g., view campaign stats).
   * Write Access: Allowed to read and write the feature (e.g., create campaigns).

<Image title="2020-05-13_16-21-33_Custom Role.png" alt={1210} className="border" border={true} src="https://files.readme.io/26c2f69-2020-05-13_16-21-33_Custom_Role.png" />

## Define Access to Components: Advanced

Custom roles can be mapped to user groups for advanced role-based access control. You can give access to different datasets to various users and restrict access to the data you do not want them to view on the CleverTap dashboard. Admins can also restrict data access to new custom roles based on selected user properties such as geographies. Users assigned to these roles are limited to read/write data available to the particular role. 

> 👍 Advanced Custom Role Example
>
> You can grant access to a role *US Campaign Manager* where the role has write access to campaigns for only users in the United States. This user cannot create campaigns for end users in other geographies.

1. Assign permissions for component access and define which feature components are available to the user role. You can also mask data such as personally identifiable information or events. 

<Image title="Settings_RBAC.png" alt={859} className="border" width="80%" border={true} src="https://files.readme.io/7b90b39-Settings_RBAC.png" />

2. Limit the role to access data for only selected end users. This can be achieved by filtering end users using common properties such as User properties, App fields, Device Fields, Geography, Subscription Groups, and Segment.

![1369](https://files.readme.io/f0507e1-Mapping_User_Properties.png "Mapping User Properties.png")

## Segment Access

Segment access management in roles gives you the ability to better manage your security, compliance and data management. If you have dashboard users who are responsible for all marketing activities in specific sub-regions, you can grant access to only that segment of users who are from the sub-region.

> 👍 Segment Access Example
>
> You have operations in Spain, Germany, England, Greece, and Italy and each region is managed by a regional manager. You can create a role for each of these regions where access to end-user data is restricted by their geography. In this way, each regional manager will have access to only end users only from their region.

> 🚧 Access Restrictions
>
> By picking the user property that the role is granted access to, you are restricting access to all data on CleverTap. Even if the role is viewing *All Users* data, it is default limited to the access restriction for that role. You cannot assign more than one segment role per user.

## Component Access

Only the admin role can alter and assign access to custom roles. 

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

## Configure Roles for Privacy

Admins can customize the user role so that important information, such as the personal identity of end users cannot be visible to the user. 

![1167](https://files.readme.io/9516566-Chunk_1_-_Roles_3.png "Chunk 1 - Roles 3.png")

### Mask Personally Identifiable Information

Admins can mask end users' personally identifiable information on the CleverTap profile page for specific dashboard users by selecting *Mask personally identifiable information*. 

![1600](https://files.readme.io/d4d4532-Chunk_1_-_Mask_events.png "Chunk 1 - Mask events.png")

When selected, the following applies:

* All profile properties are shown as *-- Restricted data --*, including profile properties such as, Name, Identity, Location, Latitude and Longitude, Email, Phone Number, Gender, and all custom user properties under the *User Properties* tab.
* The profile photo is not shown.
* All profile downloads will return an access denied error message (e.g., Find Events page, Segments page). 
* Profile exports do not work.

### Mask Events

Admins can mask the events on the user profile page for a certain set of users by selecting *Mask events*. 

When selected, the following applies:

* On the user profile page, all event-related info will be shown as *-- Restricted data --* such as, Initially acquired from, Last session, and the Activity tab.
* Event exports and downloads do not work.

# Data Access for Role-based Access Control (RBAC)

This section covers things to consider when using RBAC.

## General Rules of Access

The general rules of access include:

* Any write access automatically gives read access to the user.
* All users can have multiple custom roles; however, a user cannot have multiple system roles.
* A user can have access to both system and custom roles at the same time. They can have one system role and unlimited custom roles.
* System roles cannot be altered.

## Access Rules and Handling Clashes

Permissions and access can be set while creating a custom role. The following order of preference applies.

* A user can only be assigned a system role and a custom role(s).

### Permission Clash

When a user is assigned multiple roles, a permission clash and a lower access level are enabled. For example, if a user is assigned both Admin and Creator roles, the Creator access is enabled.

### Component Clash

In the case of multiple custom roles, there can be situations when one role has access to a component and another role does not allow access to the same component. 

> 👍 Component Clash Example
>
> A user has two roles: A and B. 
>
> Role A has to write access for Product Experiences while role B does not have access to Product Experiences. In this scenario, the user will still have write access to the Product Experiences.
