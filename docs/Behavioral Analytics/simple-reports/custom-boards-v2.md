---
title: Custom Boards 2.0
excerpt: Understand what are custom boards in CleverTap.
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

The _Custom Boards_ is a feature in CleverTap that allows you to create and customize your board. CleverTap provides a set of default boards, such as the [Today View](doc:today-view), [Mobile App View](doc:mobile-app-view), [Uninstalls View](doc:uninstalls-view), [Revenue View ](doc:revenue-view), [NPS view](doc:nps-board), which you can use to analyze user activity in your application.

Each custom board you create is composed of Tiles, which are widgets you can pin to the board to track the metrics of your interest. You can pin Tiles and track the metrics using one of the following features: [Funnels](doc:funnels) and [Trends](doc:trends).

> 📘 Private Beta
>
> Currently, this feature is a Private Beta Release. If you want access to this feature, contact your Customer Success Manager.

For example, if you want to track the following metrics for the last 30 days:

* Weekly comparison of Unique users who purchased
* Total purchases by brand

As shown in the following image, you can create a custom board and add Tiles to track the above metrics. You can also pin those Tiles to the board.

<Image align="center" alt="Sample Custom Board" border={true} caption="Sample Custom Board" src="https://files.readme.io/021f591b447150ebc9711e8fbe07393f81110fef7680d15ba03ef12bc5c8f517-image.png" />

After you build your custom board, you can also share the board with others in your organization.

Custom boards can have the following features:

* [Boards](doc:custom-dashboards#boards)
* [Tiles](doc:custom-dashboards#cards)

# Boards

The board's section provides information about different boards created for the project and the operations that can be performed on these boards. On this page, users can view a list of all boards:

* Created by them,
* Shared with them, and
* Public boards that are available for users in their organization.

To access boards on the CleveTap dashboard, go to _Analytics_ > _Boards BETA. The_All boards_ page opens.

<Image align="center" alt="List of Boards" border={true} caption="List of Boards" src="https://files.readme.io/c736a32d0cae70aa89558c968d1744d0c783b08f34e27acf0970f70c31fd1c9f-image.png" />

## Create a Custom Board

This section covers how to create a custom board. To create a board:

1. Go to _Analytics_ > _Boards BETA_ from the left navigation menu.
2. Click **Create Board**.
3. Enter your board name and click **Create**.

## Operations

You can perform the following actions on a particular board:

### Share

CleverTap provides restricted board access so that the board owner can control the members who can view and contribute to the insights captured on the board. The board owner can add or remove members from the access list and can control access levels.

To share a board, perform the following steps:

1. Create your custom board.
2. Click the **Share** ![](https://files.readme.io/0710b8affc42e1398a0baf1d52f4a6c0eab19a0c4ed1ae6749f34d04e93fe6f9-Share_Me.png) icon. The _Share Board_ popup displays with restricted permissions by default. Use the search box to view and add users to this board.

<Image align="center" alt="Share the board" border={true} caption="Share the board" src="https://files.readme.io/f78e95fdb8583e08de9093b1050aa95a1d1705fcb00c9fcb17338bcd7caa619f-image.png" width="60% " />

3. Select the required users and click **Done**. The selected users can now access the board based on their permissions.

You can also copy the link and share the board. However, the user must have the required access to the board.

#### Shared Access Types

There are three levels of access:

* **Owner**: Full permissions to edit tiles, manage users, and delete the board.
* **Editor**: Full permissions similar to Owner, except they cannot remove the Owner.
* **Viewer**: Can view the board but cannot make changes.

#### Access Methods

There are two ways to assign access:

* **Individual Access**: The Owner or Editor manually adds users via email and assigns them _Editor_ or _Viewer_ access.
* **General Access**: The board can be set as _Anyone can View_ or _Anyone can Edit_, granting all users in the account that level of access.

> 📘 Note
>
> Both access types can coexist. For example, a board marked as General View can be visible to all users, while a few power users are assigned Individual Edit access to this board. In such cases, individual access overrides general access.

### Clone

This option is used when you want to track the same metrics with minor changes. Anyone who has access to your project can clone the board by clicking the three-dot menu at the top of the board and then selecting **Clone** from the list.

### Rename

You can rename the board clicking the three-dot menu at the top of the board and then selecting **Rename** from the list.

### Delete

You can delete the boards you created by clicking the three-dot menu at the top of the board and then selecting **Delete** from the list.

### Sort

You can sort the boards by the date they were created and by the person who created them. To do so, click the column header.

<Image align="center" alt="Sort Boards" border={true} caption="Sort Boards" src="https://files.readme.io/d1e35d99ecd88d878727236afb6b32761f33f28cbfc0c30234ca14c41a18ff87-image.png" />

### Search

You can search the boards by board name or the creator's email ID. To search boards, enter the search criteria under the Search text box.

## Board Limits

You can create a maximum of 500 boards. You can pin up to 20 tiles per board. You can  also share the board within the organization.

# Tiles

This section provides information about different operations that can be performed on the tile. Select the board to view all the included Tiles.

## Operations

You can perform the following actions on a particular tile:

### Add to Board

When you create your new board, you start with an empty board. CleverTap allows you to pin Funnels and  Trends.

To add a tile of the example metrics:

1. Go to Analytics > _Trends BETA_ from the board.
2. Run a Trend Analysis.
3. Click the **Add to Board**. Name the chart and add it to a new or existing board.

<Image align="center" alt="Add Trend to board" border={true} caption="Add Trend to the board" src="https://files.readme.io/7c30b05cc9a203a2f17af1552558641dc0a49be322dad0a8ff4adbfaff211f6d-image.png" />

### Rename a Tile

You can change the tile's name when you hover over any tile on a board.

<Image align="center" alt="Rename a Tile" border={true} caption="Rename  a Tile" src="https://files.readme.io/0cb85b542e65524ad15e3f4f83f20b8a1d327e84b10a4ae116eac03a433e338a-image.png" />

### Edit a Tile Query

Edit the query that is generating the tile. You can view the board that you are editing and the relative analytic metric.

To do so:

1. Click the ![](https://files.readme.io/b087d12e90e061ffef4b4f4f6e4409662d82a0d6ad35392feff582616b7395c4-ellipsis_icon.png) icon on the tile.
2. Click **Edit**.

<Image align="center" alt="Delete a Tile" border={true} caption="Edit  a Tile" src="https://files.readme.io/0cb85b542e65524ad15e3f4f83f20b8a1d327e84b10a4ae116eac03a433e338a-image.png" width="70% " />

3. The underlying query is displayed. You can adjust it and click **Save**.

<Image align="center" alt="Edit a tile and the query under it." border={true} caption="Edit a Tile" src="https://files.readme.io/3412b5d61663da15cb01eb59762bc76f7ee8b6b967d7d231dcfc9f1b02b90647-Edit_Tile.gif" />

### Delete

You can delete a tile when you hover over any tile on a board.

<Image align="center" alt="Delete a Tile" border={true} caption="Delete  a Tile" src="https://files.readme.io/0cb85b542e65524ad15e3f4f83f20b8a1d327e84b10a4ae116eac03a433e338a-image.png" />

### Resize

You can drag and resize the tile by hovering and dragging the bottom corners of the tile.

<Image align="center" alt="Resize Tile" border={true} caption="Resize Tile" src="https://files.readme.io/ef2ce1cabb0f4e3370a269d2315eba3174c69a929a0c8e14bec4107290623d14-2025-06-18_19-14-42.gif" />

### Move

You can reorder the sequence of tiles by hovering over them.

<Image align="center" alt="Move Tiles" border={true} caption="Move Tiles" src="https://files.readme.io/99464d41107cbb2c62e051a4259bac63018136e3776a3463e34cabc410d73e63-2025-06-18_19-17-20.gif" />