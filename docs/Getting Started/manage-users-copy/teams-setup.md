---
title: Teams Setup
excerpt: >-
  Learn how to manage user access and content visibility in CleverTap using
  Team-based grouping and role-based permissions.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The Teams feature helps organizations collaborate more effectively in CleverTap by aligning entity access, ownership, and approvals with real-world business structures. It brings clarity, control, and scalability to your user and content management workflows. 

With Teams enabled, users and content are grouped at the Team level within a project, mirroring structures like regions, product lines, or lifecycle stages. Whether operating across geographies or verticals, Teams ensures:

* Users access content relevant to their responsibilities
* Collaboration is scoped to the right group
* Entity ownership is always clear and auditable

> 📘 **Private Beta**
>
> This feature is released in Private Beta and is enabled for select customers only. To enable this feature, contact your Customer Success Manager or raise a support ticket.

CleverTap governs user access through two independent layers:

* **Roles**: Define what actions a user can perform (for example, create, edit, approve) based on permissions assigned via Role-Based Access Control (RBAC).
* **Teams**: Define which entities (Campaigns, Journeys, Segments, Events, and Content Management System Assets) a user can access, based on their team membership.

By combining Roles and Teams, CleverTap ensures both action-level control and content-level visibility, making governance simple, scalable, and aligned with business needs.

# User Roles and Access

The Teams feature currently governs user access to Campaigns, Journeys, Segments, Events, and Content Management System (CMS) Assets. Access is determined by the assigned roles, which can either be user or admin:

* **Non-admin Users** are scoped to the Teams they belong to, helping them focus only on entities relevant to their goals and responsibilities.
* **Admins** are added to all Teams by default to ensure they have full oversight across projects. They manage all entities across all Teams and the Default Team.

This table summarizes the scope of access for different user roles: 

| Role         | Entity Access                                                                                                                                                                                                |
| :----------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Admin        | All entities, across all teams                                                                                                                                                                               |
| Non-admin    | Only entities belonging to their teams                                                                                                                                                                       |
| Approver     | Can approve Campaigns, Journeys, and Events created by users on their team if they have approval permissions.                                                                                                |
| Custom Roles | Access is limited to the user’s assigned teams and governed by their configured permissions. For example, a Team Marketing Manager can publish journeys for Team A, but cannot access anything under Team B. |

> 📘 Audit Logging for Team Actions
>
> CleverTap captures Audit logs for the following Team-related actions: Team creation, Team updates, user additions, and user removals.

# Working across Teams

CleverTap allows users to seamlessly switch between multiple teams they are assigned to. This helps users focus on the right business context, such as regional teams, product lines, or lifecycle stages, without needing separate logins or configurations. 

Users only see the teams they are assigned to. When a user logs in for the first time after Teams is enabled (or after a new invitation), the following logic determines the default team selection:

| Team Assignment | Dashboard Behavior                                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| Single team     | Selects the most recently assigned team.                                                                           |
| Multiple teams  | Selects the team earliest created team to help the user get started; you can switch teams using the team switcher. |

> 📘 **Key Points to Remember**
>
> * Switching Teams is seamless and helps users move between contexts, such as regions or products, without separate logins or dashboards. To switch Teams, click the Teams switcher dropdown under *Project Name* on the left nav.
>
> <Image alt="Teams Switcher Dropdown" align="center" width="60% " border={true} src="https://files.readme.io/5d1f7437a2c7500087855d2606135288c52dc428be3bfd4f94e1387448b53f77-Switcher.png">
>   Teams Switcher Dropdown
> </Image>
>
> * All open tabs auto-refresh on team switch to ensure consistency across sessions.
>
> <Image alt="Switching Teams" align="center" width="50% " border={true} src="https://files.readme.io/fbd6bdc2ebcee842c0cbaf1f269084add2773b626690aa166a1f465029801068-Modal__Switch_team.png">
>   Switching Teams
> </Image>
>
> * Switching teams updates the visible entities, such as campaigns, journeys, segments, events, and CMS assets based on the selected team. When switching teams, the user roles and permissions remain unchanged; only the visible content (entities and events) changes as per the selected team. 
> * Ensure your changes are saved before switching teams. Any unsaved progress in an open session (for example, in an in-progress campaign draft or journey setup) will be lost when the team is switched.

# Manage Teams

This section outlines how to configure and manage teams within your CleverTap account. Team setup is critical in managing access across Campaigns, Journeys, and Segments. Refer to the following subsections: 

* [Create Team](doc:teams-setup#create-team)
* [Edit Team](doc:teams-setup#edit-team)
* [Assign Teams to Existing Users](doc:teams-setup#assign-teams-to-existing-users)
* [Assign Teams to New Users](https://docs.clevertap.com/docs/teams-setup#assign-teams-to-new-users)
* [Bulk Update Teams for Users](doc:teams-setup#bulk-update-teams-for-users)
* [Export Team User Details](doc:teams-setup#export-team-user-details)

> 🚧 **Note**
>
> Users can create, edit, approve, or publish campaigns based on their role permissions. For more information on roles, refer to [Role-Based Access Control](https://docs.clevertap.com/docs/role-based-access-control).

## Create Team

To access the Teams listing page, go to *Project Settings* and click **Teams**. To create a new Team, click **Create Team**.

<Image alt="Teams Listing Page" align="center" border={true} src="https://files.readme.io/dab06247c127097061a32f062d51371279259cc1c64f23f4315bc7c154f74d65-Teams_Listing_Page.png">
  Teams Listing Page
</Image>

The following fields are required:

* **Name**: Mandatory field. The name must be unique and limited to 50 alphanumeric characters. Special characters and duplicate names are not allowed, and an error message appears if a conflict occurs.
* **Description**: Optional field. Add a short description for the team, which can be up to 200 characters long.
* **Custom event access**: Mandatory field. Admins can define event-level visibility when creating or editing a team. This option allows you to control which events your team can access. You can choose from:
  * **All events**: Users can access all custom events. This is the default setting.
  * **Only selected events**: Access is limited to events chosen by the admin.
  * **All excluding selected events**: All events are visible except the ones that are excluded.

<Image alt="Create Team" align="center" border={true} src="https://files.readme.io/1a9f486c9d469944715581cfd3f01d867ca49f23d9cd3995791dcc2ef0e00375-teamss.png">
  Create Team
</Image>

<Image alt="Event Selection for Including/Excluding Events" align="center" border={true} src="https://files.readme.io/dd1020390721e277cd3886ecef044094fb77b99f16e797484e58d352de8e94fd-event_selection.png">
  Event Selection for Including/Excluding Events
</Image>

## Edit Team

To edit a Team, perform the following steps:

1. Go to *Project Settings* and click **Teams**. Click **Edit Team**. 
2. Edit the **Name** and **Description** fields. You can also view users and their roles on the team.
3. Click Custom event access to control which events the team can access. You can choose from *All events, Only selected events,* and *All excluding selected events.*

<Image alt="Edit Team" align="center" border={true} src="https://files.readme.io/afffc53e2bdefd07f5880dc67cdae686f81ef2ed614f34a45d9c4bd19641e73f-Edit_teams_-_new.png">
  Edit Team
</Image>

## Assign Teams to Existing Users

To assign a team to a user, perform the following steps:

1. Go to *Settings* and click **Users**. 
2. Click the ![](https://files.readme.io/4185dca9130a3a5b6c52845e8560d6c0ac7ff732ae0d7c7704e7a83b4803845f-ellipses_icon.png)   icon next to the desired user and select **Manage roles & teams** from the dropdown.

<Image alt="Manage Roles and Teams" align="center" border={true} src="https://files.readme.io/48f2f2948896e70dd5522d157e91a6801e57a71d0cf475575239ac63f00601d8-teams_users.png">
  Manage Roles and Teams
</Image>

> 📘 Note
>
> A user must always belong to at least one Team. You cannot remove a user from all Teams.

## Assign Teams to New Users

When inviting a user from the dashboard, the admin can select one or more Teams to assign to the user during the invitation process. For users added via SSO (Single Sign-On), if the `accountList` attribute is configured, the user is initially placed in the Default Team. The admin can later update the user's team membership from the *Users* page.

## Bulk Update Teams for Users

Admins can bulk **add** or **remove** Teams for users from the *Users page*. Validation ensures each user belongs to at least one team after bulk operations.

<Image alt="Bulk Update" align="center" border={true} src="https://files.readme.io/9bb13c4cea1973745f9c036dbff3861248d98215e0c769d115d2bbfbd7650361-Bulk_Updating.png">
  Bulk Update
</Image>

## Export Team User Details

You can export user details by selecting **Download as CSV** from  *Settings* > *Users*. The CSV includes a Teams column, showing the teams each user belongs to, along with other key information such as *Name*, *Role*, *Email*, and *Status*. You can use this export to audit team membership across your organization, identify users who are not assigned to the right teams, and so on.

# Event Visibility in Teams

Admins can define event-level visibility when creating or editing a team. This ensures that users only view relevant event data for their use case. 

* System events are always visible to all users and cannot be restricted.
* Charged event is a custom event and follows the same rules.
* The Default Team also has All Events access by default, and can be edited.

For example, users working across multiple business units or teams need the flexibility to manage campaigns without granting blanket access to other teams' data, including Events Data. Here, CleverTap offers the capability to enforce event-level access for all users across teams.

> 📘 **Note**
>
> Event visibility is enforced across the entire dashboard, including Analytics, Segmentation, Campaigns, Journeys, Promos, Best-time, Bulletins, and so on, based on the selected team context.

# Impact of Teams Across Dashboard

With Teams enabled, users operate within a scoped environment, ensuring that content, events, and data across CleverTap are always relevant to their assigned business context. The following dashboard modules are impacted by team-based access. Each user’s experience is scoped to the teams they belong to, as follows:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Module
      </th>

      <th>
        Impact
      </th>

      <th>
        What Happens When You Switch Teams
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Analytics
      </td>

      <td>
        Users see and use only team-accessible events in queries.
      </td>

      <td>
        Event dropdown updates to reflect the event access for selected team. Users can only view and analyze queries built using events available to that team.
      </td>
    </tr>

    <tr>
      <td>
        Best Time
      </td>

      <td>
        <ul><li> Shows only events accessible to the team.</li><li> A maximum of 10 configurations allowed across all your projects on the CleverTap dashboard.</li></ul>
      </td>

      <td>
        The Event Configuration list updates to show only events allowed for the selected team. Users can view and use only configurations tied to those events.
      </td>
    </tr>

    <tr>
      <td>
        Bulletins
      </td>

      <td>
        Business Event dropdown shows only events accessible to the selected team. Users can view and configure only those events assigned to their team.
      </td>

      <td>
        The event list updates automatically to reflect event access for your new team.
      </td>
    </tr>

    <tr>
      <td>
        Content Manager
      </td>

      <td>
        <ul><li> Files, templates, blocks, and folders are only visible to the team that created them. </li> <li> Users cannot reuse or edit content created by other teams. </li> <li> All CMS asset names (templates, files, blocks, folders) must be **globally unique** across the account. </li> <li> To ensure consistency and avoid naming conflicts, asset names must be globally unique, even if users cannot see content created by other teams.</li></ul>
      </td>

      <td>
        CMS assets created in another team are not accessible or visible. Campaigns that reference such content must recreate it in the new team context.
      </td>
    </tr>

    <tr>
      <td>
        Engagements
      </td>

      <td>
        <ul><li>Users can view and manage only those campaigns that belong to their team(s).</li> <li>The **Who** section in campaign setup displays only segments created within the same team context.</li> <li>Liquid Tags, Conversion Tracking, Personalization Setup, etc. show team-specific event data. </li></ul>
      </td>

      <td>
        Content reuse and targeting remain scoped to team-owned assets, ensuring controlled distribution and message governance. For more information, refer to 

        [Using Teams in Engagements](https://docs.clevertap.com/docs/using-teams-in-engagements)

         .
      </td>
    </tr>

    <tr>
      <td>
        Promos
      </td>

      <td>
        <ul><li>When setting up a promo, the Event dropdown shows only events configured for the selected team.</li><li>Targeting rules are designed to work with team-specific event data, helping teams build precise, relevant campaigns.</li></ul>
      </td>

      <td>
        <ul><li>Event dropdown in rule builder shows only events configured for the selected team.</li><li> Switching teams refreshes this list based on updated event access.</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        Segmentation
      </td>

      <td>
        Users can view, edit, and use only the segments created by their own teams. When building segments, only events visible to the team are available in the builder
      </td>

      <td>
        Users do not have access to segments from the previous team. Segment list and filters update based on new team context. For more information, refer to 

        [Using Teams in Segmentation](https://docs.clevertap.com/docs/using-teams-in-segmentation)

        .
      </td>
    </tr>
  </tbody>
</Table>

# Team Handling for Existing Users and Entities

When Teams is enabled, a **Default Team** is automatically created. This team includes all existing users and entities to ensure continuity, visibility, and access control. The Default team:

* Cannot be deleted or renamed
* Includes all users and entities that existed before Teams was enabled

To ensure seamless access:

* Any new user or entity created without a team assignment is automatically added to the Default Team
* If a user belongs only to the Default Team, any entity they create will also be associated with it

# FAQs

Here are answers to common questions about setting up Teams in the CleverTap dashboard.

### Can teams be deleted?

No. To ensure content traceability, teams, including the Default Team, cannot be deleted.

### What happens to existing users and entities when Teams is enabled?

All existing users and entities are automatically added to the **Default Team**.

### Can Admins be removed from a specific Team?

No, admins are automatically added to all Teams and cannot be removed.

### Can a user be part of multiple Teams?

Yes. Users can belong to multiple Teams simultaneously. They will be able to view and manage entities across all of those Teams. 

### What happens if a user is removed from a Team?

When a user is removed from a team, they lose visibility and access to entities in that Team. However, any content they create while on the team remains with that team.

# Additional Resources

For more information on Teams, refer to the following Teams resources:

* [Using Teams in Segmentation](https://docs.clevertap.com/docs/using-teams-in-segmentation)
* [Customs List API](https://developer.clevertap.com/docs/custom-list-api-teams)
* [Using Teams in Engagements](https://docs.clevertap.com/docs/using-teams-in-engagements)
* [Create Campaign API](https://developer.clevertap.com/docs/create-campaign)
* [Email Templates API](https://developer.clevertap.com/docs/email-templates-api)
