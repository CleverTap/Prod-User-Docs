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

<Image title="image2.png" alt={1382} className="border" border={true} src="https://files.readme.io/6916e12-image2.png" />

After you build your Custom Dashboard, you can pin the board to the left navigation menu of your CleverTap account for quick access next time you login. You can also share the board with other people in your organization.

# Build Your First Custom Dashboard

## Step 1: Create a New Board

From the left navigation menu, click on Boards and then click on All Boards. To create a new board, click on + Board.

<Image title="board2.png" alt={1287} className="border" border={true} src="https://files.readme.io/10b2b19-board2.png" />

Name your board, click Public, and then click Add.

> 👍 Board Visibility
>
> There are two options for board visibility: Public or Private. Setting a board to public will make the board visible throughout your organization. A private board will only be visible to the creator.

<Image title="board3.png" alt={729} className="border" border={true} src="https://files.readme.io/b83e17f-board3.png" />

## Step 2: Pin a Card

When you create your new board, you will see an empty board. 

If you click on Events, Segments, Funnels, or Find people within the empty board, you will be taken to that page in your CleverTap account. 

<Image title="board5.png" alt={720} className="border" border={true} src="https://files.readme.io/2e38d8a-board5.png" />

Click on Segments. You will now be on the Segments page in your CleverTap account, where you will see a list of Segments you have created.

<Image title="segment.png" alt={1273} className="border" border={true} src="https://files.readme.io/dae43a6-segment.png" />

Click on one of the Segments you have created. You will be taken to the Report page for that Segment. Now click on the Pin icon. 

<Image title="pin.png" alt={1265} className="border" border={true} src="https://files.readme.io/3e415bf-pin.png" />

You will prompted to name the card. Then you can pin the card to the board you created in step 1 or create a new board.

<Image title="name1.png" alt={700} className="border" border={true} src="https://files.readme.io/a279eac-name1.png" />

## Step 3: Pin the Board

Repeat step 2 to add another card to your board. 

To get quicker access to this board next time you login to CleverTap, click on the Hamburger menu (the three vertical dots on the right) and then click on the Pin to your menu button.

<Image title="image2.png" alt={1382} className="border" border={true} src="https://files.readme.io/653e09c-image2.png" />

# Features

## Boards

### Board List Page

Users will be able to see a list of all boards created by them and all public boards available for users in their organization. Users can also do the following on this page:

* Sort the boards to search for their board(s) of interest.
* Search for boards.
* Clone a board.
* Delete a board.
* Pin a board to their left navigation menu.

<Image title="boards7.png" alt={1281} className="border" border={true} src="https://files.readme.io/6e8b011-boards7.png" />

### Create a New Board

From the left navigation menu, click on Boards and then click on All Boards. To create a new board, click on + Board. 

![1287](https://files.readme.io/8dc0846-boards8.png "boards8.png")

When you create a board, you can choose the name and its visibility. You can either create a private board that will only be visible to the creator, or a public board that will be visible to everybody within the organization.

<Image title="name3.png" alt={729} className="border" border={true} src="https://files.readme.io/c83220b-name3.png" />

### Edit a Board

If you click on the Hamburger menu within a board, you will see these options:

* Bulk change the dates of all cards on the board.
* Pin/unpin a board to the left navigation menu. Pinning a board to the left navigation menu will allow the user to see the board(s) on the left navigation.
* Clone a board.
* Delete a board.
* Switch a board's visibility to a Private/Public board. 

![1382](https://files.readme.io/3f4099f-image2_2.png "image2 2.png")

## Cards

### Pin a Card

If you click on the Events, Segments, Funnels, or Find People sections of your CleverTap account, you will find different card options to pin to a board. 

For example, in the screenshot below you can pin the line graph of the Segment shown in the report.

<Image title="pin.png" alt={1265} className="border" border={true} src="https://files.readme.io/6d2049b-pin.png" />

### Rename a Card

When you hover on any card in a board, you will see an option to change the card's name.

<Image title="image3 2.png" alt={647} className="border" border={true} src="https://files.readme.io/e90b55b-image3_2.png" />

### Delete a Card

When you hover on any card in a board, you will see an option to delete the card. On Public Boards, only the creator of the board or the Admin can delete cards.

<Image title="image3.png" alt={647} className="border" border={true} src="https://files.readme.io/21be8d7-image3.png" />

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
