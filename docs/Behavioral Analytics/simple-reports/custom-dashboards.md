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

CleverTap provides a set of default dashboards, such as the [Today View](doc:today-view), which you can use to quickly analyze user activity in your application. Custom Dashboards is a new feature in CleverTap that allows you to create and customize your own board. 

Each Custom Dashboard you create is composed of cards, which are widgets that you can pin to the board to track metrics you are most interested in. You can pin cards that track [events](doc:events), [funnels](doc:funnels), and [segments](doc:segments-2).

For example, let's say you want to create a Custom Dashboard to analyze App Launch events over the past 30 days. You could add a histogram card, which will show you the distribution of App Launch events. You could also add a line graph card to see the number of App Launch events per day. 

<Image title="Custom_Dashboard_Main.png" alt={1182} className="border" border={true} src="https://files.readme.io/ae65151-Custom_Dashboard_Main.png" />

After you build your Custom Dashboard, you can pin the board to the left navigation menu of your CleverTap account for quick access next time you login. You can also share the board with other people in your organization.

# Build Your First Custom Dashboard

## Step 1: Create a New Board

From the left navigation menu, click Custom Boards. To create a new board, click on + Board.

Name your board, click Public, and then click Add.

> 👍 Board Visibility
>
> There are two options for board visibility: Public or Private. Setting a board to public will make the board visible throughout your organization. A private board will only be visible to the creator.

## Step 2: Pin a Card

When you create your new board, you will see an empty board. 

If you click on Events, Segments, Funnels, or Find people within the empty board, you will be taken to that page in your CleverTap account. 

<Image title="Custom_Dashboard_Empty.png" alt={608} className="border" border={true} src="https://files.readme.io/876454b-Custom_Dashboard_Empty.png" />

Click on Segments. You will now be on the Segments page in your CleverTap account, where you will see a list of Segments you have created.

<Image title="Custom_Dashboard_Segment.png" alt={1176} className="border" border={true} src="https://files.readme.io/06d8f80-Custom_Dashboard_Segment.png" />

Click on one of the Segments you have created. You will be taken to the Report page for that Segment. Now click on the Pin icon. 

<Image title="Custom_Dashboard_Segment_pin.png" alt={1189} className="border" border={true} src="https://files.readme.io/3e83064-Custom_Dashboard_Segment_pin.png" />

Name the card and choose the board of your choice. You can also create a new board at this step. 

<Image title="Custom_Dashboard_Segment_pin_Name.png" alt={562} className="border" border={true} src="https://files.readme.io/4266aa8-Custom_Dashboard_Segment_pin_Name.png" />

## Step 3: Your Boards

Repeat step 2 to add another card to your board. 

To get quicker access to this board next time you login to CleverTap, click the My Boards tab. 

<Image title="Custom_Dashboard_my_boards.png" alt={1165} className="border" border={true} src="https://files.readme.io/494dede-Custom_Dashboard_my_boards.png" />

# Features

## Boards

### Board List Page

Users will be able to see a list of all boards created by them and all public boards available for users in their organization. Users can also do the following on this page:

* Sort the boards to search for their board(s) of interest.
* Search for boards.
* Clone a board.
* Delete a board.
* Pin a board to their left navigation menu.

<Image title="Custom_Dashboard_Main_list.png" alt={1167} className="border" border={true} src="https://files.readme.io/b60819a-Custom_Dashboard_Main_list.png" />

### Edit a Board

If you click on the Hamburger menu within a board, you will see these options:

* Bulk change the dates of all cards on the board.
* Pin/unpin a board to the left navigation menu. Pinning a board to the left navigation menu will allow the user to see the board(s) on the left navigation.
* Clone a board.
* Delete a board.
* Switch a board's visibility to a Private/Public board. 

![1185](https://files.readme.io/64e0bea-Custom_Dashboard_Main_edit.png "Custom_Dashboard_Main_edit.png")

## Cards

### Pin a Card

If you click on the Events, Segments, Funnels, or Find People sections of your CleverTap account, you will find different card options to pin to a board. 

For example, in the screenshot below you can pin the line graph of the Segment shown in the report.

<Image title="Custom_Dashboard_Segment_pin_edit.png" alt={1190} className="border" border={true} src="https://files.readme.io/d7d80c8-Custom_Dashboard_Segment_pin_edit.png" />

### Rename a Card

When you hover on any card in a board, you will see an option to change the card's name.

<Image title="Custom_Dashboard_card_rename.png" alt={1182} className="border" border={true} src="https://files.readme.io/de72695-Custom_Dashboard_card_rename.png" />

### Delete, edit or resize a Card

When you hover on any card in a board, you will see an option to delete the card. On Public Boards, only the creator of the board or the Admin can delete cards.

<Image title="Custom_Dashboard_card_delete.png" alt={1187} className="border" border={true} src="https://files.readme.io/ea0ef09-Custom_Dashboard_card_delete.png" />

## Workflows

Users are able to pin workflows from Cohorts, Funnels, Events, and Trends to their custom dashboard.

### Pin a Workflow

To pin a workflow to a custom dashboard, select *Analytics* from the CleverTap dashboard, and then *Cohorts*.

> 📘 Other Analytics Features
>
> The following steps can also be performed for Funnels, Events, and Trends.

<Image title="00.01.png" alt={2406} width="100%" src="https://files.readme.io/b7ef670-00.01.png" />

1. Select a segment from the *For segment* dropdown menu.
2. Select an event from the *First event* dropdown menu.
3. Select an event from the *Return event* dropdown menu.
4. Select the *Compare to another segment* checkbox and select a segment definition from the dropdown menu.
5. From *Advanced* options, select a retention mode from the dropdown menu.
6. Click **View Cohort**. 

<Image title="00.02.png" alt={2395} width="100%" src="https://files.readme.io/673372b-00.02.png" />

7. In the *Cohort* area, click the pin icon on the right.

<Image title="00.03.png" alt={2428} width="100%" src="https://files.readme.io/067a578-00.03.png" />

8. In the *Pin cohort to custom boards* window, enter a card name.

<Image title="00.04.png" alt={2434} width="100%" src="https://files.readme.io/ea2cc6c-00.04.png" />

9. In the *Pin to existing boards* section of the window, select a board from the dropdown menu.

<Image title="00.05.png" alt={2414} width="100%" src="https://files.readme.io/da9150c-00.05.png" />

10. Select all the workflows you want to pin to your custom dashboard.
11. Select the *Pin to a new checkbox* if you want to pin your workflows to a new board.

<Image title="00.06.png" alt={2396} width="100%" src="https://files.readme.io/18a5613-00.06.png" />

12. Give your new board a name.

<Image title="00.07.png" alt={2412} width="100%" src="https://files.readme.io/6ac02cd-00.07.png" />

13. If you want to make your board private, select the toggle. Private boards are only visible to you members of your organization who have a link.

<Image title="00.08.png" alt={2409} width="100%" src="https://files.readme.io/a5fc8fc-00.08.png" />

14. Click **Pin**. A message displays at the top of the screen letting you know that the cohort workflow has been your custom board. 

<Image title="00.09.png" alt={2413} width="100%" src="https://files.readme.io/f0ee636-00.09.png" />

15. Click the **Go to custom board** link.

![2404](https://files.readme.io/2f8a569-00.10.png "00.10.png")

A message displays that cohorts the number of boards you selected your custom dashboard. 

![2403](https://files.readme.io/6b72e39-00.11.png "00.11.png")

16. From the CleverTap dashboard, select *Custom Boards* to view the workflows pinned to your board.

<Image title="00.12.png" alt={2027} width="100%" src="https://files.readme.io/3517b9b-00.12.png" />

# Board Limits

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
        Users can share the board within the org.\
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
        Users can share the board within the org.\
        Users can pin up to 5 boards on the left navigation.
      </td>
    </tr>
  </tbody>
</Table>

# Access Controls

### [Admin](doc:managing-dashboard-access) 

* Admins can create a board.
* Admins can delete their board.
* Admins can delete board(s) created by creators or other Admins.
* Admins can switch their board between private-public.
* Admins can pin a card to their board.
* Admins can pin a card to any public board.
* Admins can delete a pinned card from their board.
* Admins can delete any pinned cards from other Public boards.

### [Creator or Approver](doc:managing-dashboard-access)

* Creators can create a board.
* Creators can delete their board.
* Creators can switch their board between private-public.
* Creators can pin a card to their board.
* Creators can pin a card to any public board.

### [Members](doc:managing-dashboard-access)

* Members can create a private board.
* Members can delete their board.
* Members CANNOT switch their board between private-public.
* Members can pin a card to their board.
* Members CANNOT pin a card to any public board.

# Video Tutorial

<HTMLBlock>{`
<div><iframe width="560" height="315" src="https://www.youtube.com/embed/ffdqTqZvIAM?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe></div>

<style></style>
`}</HTMLBlock>
