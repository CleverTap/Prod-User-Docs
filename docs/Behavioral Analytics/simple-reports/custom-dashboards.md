---
title: Custom Dashboards
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
# Overview

CleverTap provides a set of default dashboards, such as the [Today View](doc:today-view) which you can use to analyze user activity in your application. *Custom Dashboards* is a feature in CleverTap that provides the capability to create and customize your own board. 

Each custom dashboard you create is composed of cards which are widgets that you can pin to the board to track metrics you are most interested in. You can pin cards that track [events](doc:events), [funnels](doc:funnels), [segments](doc:segments), [trends](https://docs.clevertap.com/docs/trends), and [cohorts](https://docs.clevertap.com/docs/cohorts).

For example, if you want to create a custom dashboard to analyze *App Launch* events over the past 30 days, you can add a line graph card to view the number of *App Launch* events and a bar graph to view the distribution between App Launched and Charged.

<Image title="Overview 1 - custom board.png" alt={1405} className="border" border={true} src="https://files.readme.io/f580ff9-Overview_1_-_custom_board.png" />

After you build your custom dashboard, you can pin it to a custom board and can also share it with other people in your organization.

# Build Your First Custom Dashboard

This section covers how to build a custom dashboard.

## Create a New Board

Follow the steps below to create a new board:

1. From the left navigation menu, click **Boards**.
2. To create a new board, click on **+ Board**.
3. Name your board, then click **Create**.

## Pin a Card

When you create your new board, you start with an empty board. 

If you click on any of the sections (e.g., *Events*, *Funnels*, etc) within the empty board, you are taken to that page in your CleverTap account. 

<Image title="Dashboard 1 - Pin a card.png" alt={524} className="border" border={true} src="https://files.readme.io/f8ed409-Dashboard_1_-_Pin_a_card.png" />

1. Click **Segments**. You are now on the *Segments* page in your CleverTap account where you have a list of segments you have created.

<Image title="Dashboard 2 - Custom Dashboard Segment.png" alt={1400} className="border" border={true} src="https://files.readme.io/49b1fa1-Dashboard_2_-_Custom_Dashboard_Segment.png" />

2. Click on one of the segments you have created. You are taken to the report page for that segment. 
3. Now, click on the pin icon. 

<Image title="Dashboard 3 - Custom Dashboard Segment pin.png" alt={1409} className="border" border={true} src="https://files.readme.io/e23fa24-Dashboard_3_-_Custom_Dashboard_Segment_pin.png" />

4. Name the card and select an existing board or create a new board by selecting *Pin to a new board*. 

<Image title="Dashboard 4 - Name the board.png" alt={559} className="border" border={true} src="https://files.readme.io/fe390c6-Dashboard_4_-_Name_the_board.png" />

5. Once complete, click **Pin**.

# Features

Custom dashboards have various features, including boards, cards, workflows, and dashboard shareability.

## Boards

This section shows how to view a board list page, how to edit a board, and more.

### Board List Page

Users can view a list of all boards created by them and all public boards available for users in their organization. 

Users can also do the following on this page:

* Sort the boards by date.
* Search for boards.
* Clone a board.
* Delete a board.

<Image title="Boards 1 - list.png" alt={1400} className="border" border={true} src="https://files.readme.io/d08a36c-Boards_1_-_list.png" />

### Edit a Board

Once you are in a board, you can take the following actions:

* Set as default view.
* Mark as favorite.
* Change the date range of all cards on the board.
* Refresh the board.
* Share the board.
* Clone a board.
* Edit a board name.
* Delete a board.

![1405](https://files.readme.io/44fb22d-Boards_2_-_edit_a_board.png "Boards 2 - edit a board.png")

## Cards

This section shows how to pin, rename, edit, or delete a card.

### Pin a Card

After you click on a segment, you can find different card options to pin to a board. 

1. Navigate to *Segment* > *Segment*.
2. Select a segment.
3. Click the pin icon to pin the report to an existing or new board.

<Image title="Cards 1 - pin a card.png" alt={693} className="border" border={true} src="https://files.readme.io/80633fb-Cards_1_-_pin_a_card.png" />

### Rename a Card

When you hover on any card in a board, you have an option to change the card's name.

1. Click the pencil icon.
2. Rename the card.
3. Click the checkmark to save.

<Image title="Cards 2 - rename a card.png" alt={1405} className="border" border={true} src="https://files.readme.io/74a8387-Cards_2_-_rename_a_card.png" />

### Delete, Edit, or Resize a Card

When you hover on any card in a board, you see an option to delete the card. 

1. Click on the trash can icon.
2. Click **Delete**.

> 📘 Who Can Delete Cards
>
> On public boards, only the creator of the board or the admin can delete cards.

<Image title="Cards 3 - delete edit resize a card.png" alt={1405} className="border" border={true} src="https://files.readme.io/168ff01-Cards_3_-_delete_edit_resize_a_card.png" />

## Workflows

Users can pin workflows from *Events*, *Funnels*, *Segments*, *Find People*, *Trends*, and *Cohorts* to their custom dashboard.

### Pinning to a Custom Dashboard

To pin a workflow to a custom dashboard:

1. From the CleverTap dashboard, navigate to *Analytics* > *Cohorts*.
2. Select a segment from the *For segment* dropdown menu.
3. Select an event from the *First event* dropdown menu.
4. Select an event from the *Return event* dropdown menu.
5. Select the *Compare to another segment* checkbox and select a segment definition from the dropdown menu.
6. From *Advanced* options, select a retention mode from the dropdown menu.
7. Click **View Cohort**. 

<Image title="Workflows 1 - view cohort.png" alt={4812} width="100%" src="https://files.readme.io/c16a74b-Workflows_1_-_view_cohort.png" />

> 📘 Other Analytics Features
>
> The following steps can also be performed for *Events*, *Funnels*, *Segments*, *Find People*, and *Trends*.

9. In the *Cohort* area, click the pin icon on the right.

<Image title="Workflows 2 - pinning custom board.png" alt={1412} width="100%" src="https://files.readme.io/189b2dd-Workflows_2_-_pinning_custom_board.png" />

10. Enter a card name and select an existing board or create a new board by selecting *Pin to a new board.*
11. Click **Pin**. A message displays at the top of the screen letting you know that the cohort workflow has been pinned to your custom board. 

<Image title="Workflows 3 - name the board and pin.png" alt={560} width="100%" src="https://files.readme.io/d102dd2-Workflows_3_-_name_the_board_and_pin.png" />

12. Click on the link.

<Image title="Workflows 4 - new pin confirmation displays.png" alt={1392} width="100%" src="https://files.readme.io/de5ced3-Workflows_4_-_new_pin_confirmation_displays.png" />

Your new dashboard displays.

![1411](https://files.readme.io/3163d1b-Workflows_5_-_addition_to_custom_board.png "Workflows 5 - addition to custom board.png")

## Dashboard Shareability

CleverTap provides restricted dashboard access so that the owner of a dashboard can control the members who can view and contribute to the insights captured on the dashboard. The dashboard owner can add and remove members from the access list and can control access levels. 

### Sharing Custom Dashboards

To share a dashboard, perform the following steps:

1. Refer to the steps in [Build Your First Custom Dashboard](https://docs.clevertap.com/docs/custom-dashboards#build-your-first-custom-dashboard) and create a dashboard. Once a dashboard is created, a *Share* icon displays in the list of options; however, the icon is only visible to the board's creator.

![1405](https://files.readme.io/3d86d16-Dashboard_sharing_0_-_board_to_share.png "Dashboard sharing 0 - board to share.png")

2. Click the **Share** icon. The *Share Board* displays with restricted permissions by default. Use the search box to view and add users to this board. 

<Image title="Dashboard_Share_Default_Access.png" alt={560} className="border" border={true} src="https://files.readme.io/9dc40d8-Dashboard_Share_Default_Access.png" />

3. Select a user and click **Send**. An email is sent to the user with a link to the board. To add multiple users, select as many users as needed before clicking **Send**.

![560](https://files.readme.io/7c2077b-Dashboard_sharing_1_-_select_user.png "Dashboard sharing 1 - select user.png")

4. To change the default permissions, click the **Change** link on the *Share Board*. 

![560](https://files.readme.io/2a2382e-Dashboard_sharing_0_-_main_share_board.png "Dashboard sharing 0 - main share board.png")

5. Select a new permission, then click **Save**. 

<Image title="Dashboard_Share_Change_Access.png" alt={561} className="border" border={true} src="https://files.readme.io/f86eabc-Dashboard_Share_Change_Access.png" />

### Removing Users from Custom Dashboards

To remove access to your shared dashboard, perform the following steps:

1. Click the **Share** icon.
2. Select the permission from the list next to the name of the person.

![549](https://files.readme.io/ba40299-Dashboard_sharing_2_-_remove_user_from_sharing.png "Dashboard sharing 2 - remove user from sharing.png")

5. Click **Remove**.
6. Click **Save**.

### Editing User Permissions

You can also use the dropdown menu to edit the permissions of the user to either *Viewer* (view-only access) or *Editor* (view and edit access).

1. Click the **Share** icon.
2. Select the permission from the list next to the name of the person.
3. Click **Viewer** or **Editor**.
4. Click **Save**.

![550](https://files.readme.io/7d86064-Dashboard_sharing_3_-_edit_user_settings.png "Dashboard sharing 3 - edit user settings.png")

# Board Limits

The following table describes a list of board limits:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Plan Type
      </th>

      <th>
        Limits
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Free Plan
      </td>

      <td>
        Each user can create up to 10 boards.\
        Users can pin up to 20 cards per board.\
        Users can share the board within the organization.\
        Users can pin up to 5 boards on the left navigation.
      </td>
    </tr>

    <tr>
      <td>
        Paid Plans (Enterprise/Business)
      </td>

      <td>
        Each user can create up to 100 boards.\
        Users can pin up to 20 cards per board.\
        Users can share the board within the organization.\
        Users can pin up to 5 boards on the left navigation.
      </td>
    </tr>
  </tbody>
</Table>

# Access Controls

Access controls vary depending on your access level.

### [Admin](https://docs.clevertap.com/docs/managing-dashboard-access#section-admin-role) 

Admins can:

* Create a board.
* Delete their board.
* Delete board(s) created by creators or other admins.
* Pin a card to their board.
* Pin a card to any public board.
* Delete a pinned card from their board.
* Delete any pinned cards from other public boards.

### [Creator or Approver](https://docs.clevertap.com/docs/managing-dashboard-access#section-approver-role)

Creators can:

* Create aboard.
* Delete their board.
* Pin a card to their board.
* Pin a card to any public board.

### [Members](https://docs.clevertap.com/docs/managing-dashboard-access#section-member-role)

  Members can:

* Create a private board.
* Delete their board.
* Pin a card to their board.
* Cannot pin a card to any public board.
