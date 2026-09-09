---
title: Boards 2.0
excerpt: >-
  Learn how to create boards to monitor key metrics, track performance, and
  share insights across your team, all in one place.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
# Overview

A Board is a configurable view of tiles from different analyses, such as [Trends](doc:trends-v2), [Funnels](doc:funnels-v2), [Pivots](doc:pivots-v2), [Cohorts](doc:cohorts-v2), and [Flows](doc:flows-v2), bringing together multiple analyses into a single, shareable view. Instead of navigating between different reports, you can monitor key metrics as visual tiles on a Board.

When working with product analytics, users often juggle across multiple reports or analyses simultaneously, each in a separate view. Boards solve this by bringing all your analyses into a single, shareable view.

Boards are particularly useful for teams that regularly monitor performance metrics but share analysis by exporting charts or taking screenshots. For example, product managers tracking feature adoption, marketers reviewing campaign funnels, growth teams analyzing retention, or executives reviewing KPIs.

With Boards 2.0, you can do the following:

* Create and manage multiple boards tailored to specific goals or teams.
* Add analysis tiles from Trends, Funnels, Pivots, Cohorts, and Flows.
* Apply date-range and segment filters that dynamically update supported tiles in a single step.
* Share boards with configurable access levels (view-only or edit) without anyone needing to rebuild the analysis themselves.
* Interact with tile data, hover, compare, and explore directly on the board, without switching between analysis screens.

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information about this feature or any queries, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

# Create a Board

Creating a board gives you a blank canvas to start organizing your analyses. You can create as many boards as you need, be it one per team, product area, or campaign.

For example, suppose you are a product manager for an e-commerce app. You can create a board called _Checkout Performance_ to track add-to-cart rates (Trends), checkout drop-off steps (Funnels), and repeat purchase behavior (Cohorts), all in one view that your team can access anytime.

To create a new board:

1. Go to _Analytics_ > _Boards Beta_ from the CleverTap dashboard.
2. Click **Create Board**.
3. Enter a descriptive _Board name_.
4. Click **Create**.


<Image src="https://files.readme.io/ca1511293f0c3f5dda32180d3a3996f6e073651e3f4ca29900d887537d4706bc-2026-04-13_11-53-53_1.gif" align="center" caption="Create a Board" border={true} />


The board opens immediately as an empty dashboard, ready for you to add tiles.

<Callout icon="📘" theme="info">
  #### Best Practice for Naming a Board

  Use specific, descriptive board names from the start. A name such as _July Acquisition_ is more useful than _Board 1_, especially when you have multiple boards.
</Callout>

# Manage Boards

Once you have boards set up, you can perform several management operations to keep your boards page organized. Access these options from the board menu by clicking the ![](https://files.readme.io/c538b4435fb5f68ee8201296aa64c4fa97e4d6a4443aa3f3665d947a260f4e2d-Ellipsis_icon_Boards.png)icon in the top-right corner of any board.


<Image src="https://files.readme.io/795c0c41a4facdc5ab3f1209efd41f0f331ee64e526b426fa0eccd59cdba3ba9-image.png" align="center" caption="Board Operations" border={true} />


The following operations are available from the board menu:

* **Rename**: Update the name of an existing board at any time. This is useful when a board's focus evolves. For example, renaming _Q2 Funnel Review_ to _Q3 Funnel Review_ at the beginning of a new quarter.
* **Clone**: Create an exact copy of a board, including all its tiles and configurations. Cloning is helpful when you want to reuse a board structure for a different time period, region, or audience segment without rebuilding it from scratch. The cloned board appears in your board list with a  _Cloned_ prefix. You can then rename it as required.
* **Delete**: Permanently remove a board and all its tiles. This action cannot be undone; use it only when the board is no longer needed.

<Callout icon="📘" theme="info">
  #### Cloned Board Ownership

  When you clone a board, you become the owner of the cloned copy, regardless of who owned the original. You will have full edit and delete permissions on the clone.
</Callout>

# Share Boards

Sharing a board lets your teammates view or collaborate on the same set of analyses without needing to set up their own. This is especially useful for cross-functional reviews, stakeholder reporting, or async collaboration.

To share a board:

1. Click the ![](https://files.readme.io/ac4b6e3242b25813de0bc371e8ab741cb8019cfc928c3ff287499a192155dce6-Share_Boards_Icon.png) icon of the board you want to share.
2. In the _Share_ modal, either:
   1. Add users by selecting their email addresses from the _Select People_ dropdown, or
   2. Copy the board link to share directly via chat, email, or documents.
3. Assign an [access type](doc:boards-v2#access-type) for each invited user.
4. Click **Done**.


<Image src="https://files.readme.io/8ae5b3d58555f550a40e18ecf0598e96b903889426075d7056567ab6a9eef173-image.png" align="center" caption="Share a Board" border={true} />


## Access Type

When inviting users to a board, you control what they can do with it using the following options:

* **Viewer**: A Viewer can open the board, explore tile data, hover over data points, and apply filters for their own session. However, they cannot make any permanent changes, add, edit, rename, or delete tiles, and modify board settings. A _Viewer_ access is best for stakeholders, executives, or anyone who only requires insights without modifying the board.
* **Editor**: An _Editor_ has full access to modify the board. They can add and remove tiles, rename tiles, apply saved filters, and change board settings. Editors can also invite other users. Editor access is best for teammates who are actively contributing to or maintaining the analysis.


<Image src="https://files.readme.io/b52316435f6efad76a6374d0722f246460113a3f960bc974e378b096eb4da8bc-image.png" align="center" caption="Access Types on Board" border={true} />


## Visibility Settings

Beyond individual invites, you can set a board's overall visibility to control who can discover and access it using the following options:

* **Restricted (default)**: Only users explicitly invited can access the board. It will not appear in search or directory listings for others. This is the most secure setting and is recommended for sensitive or work-in-progress boards.
* **Anyone can view**: Any user in your organization with the link can open and view the board, without needing an explicit invite. They are automatically granted _Viewer_ access. The board may also appear in shared directories.
* **Anyone can edit**: Any user in your organization with the link can view and edit the board. Use this setting carefully. It is best suited for highly collaborative boards where the entire team is expected to contribute.


<Image src="https://files.readme.io/ac54ea100335b7f5104daa401434bdc68ee87cad0e155aa45ce81dad6480ef37-image.png" align="center" caption="Visibility Settings for a Board" border={true} />


<Callout icon="📘" theme="info">
  #### Important

  When sharing a copied board link, recipients view that board based on its current visibility setting. If the board is set to _Restricted_, only users who have already been invited can open the link. Changing a board from _Restricted_ to _Anyone can view_ or _Anyone can edit_ immediately grants access to all users who have the link or edit access. If the board contains sensitive data, confirm with your team before changing visibility.
</Callout>

# Add a Tile to a Board

Tiles are the building blocks of a board. Each tile represents a saved visualization or a table from one of the supported analysis types. You can add as many tiles as you need, mix different analysis types on the same board, and rearrange them to suit your layout.

You can add a tile to a board from within the individual analysis screens (for example, Trends or Funnels) or from the board itself. Once added, the tile appears on the board and reflects the configuration you set in the analysis when you added it.

For example, if you want to build a Trends analysis tracking daily active users over the past 30 days and want to add it to your _Product Health_ board:

1. Click **Add Tile** from a Board.
2. Select _Trends_  and configure your analysis query (events, filters, chart type, date range, etc.).
3. Click **View Analysis**.
4. Once the analysis loads, click **Save**.
5. Select the target board (for example, Product Metrics) from the list. If you have not created a board yet, you can create one inline.
6. (Optional) Enter a _Tile name_ (for example, Daily Active Users in Last 30 Days).
7. Click **Save**.


<Image src="https://files.readme.io/dfb9b2c542fe787794bf8e348a30411d856e028429a00b2618a17330069ee188-image.png" align="center" caption="Add Tile to a Board" border={true} />


You can add tiles from any of the following analyses:

| Anlysis | What it shows on the board                                     |
| :------ | :------------------------------------------------------------- |
| Trends  | Line, bar, pie, or number charts of event metrics over time    |
| Funnels | Conversion rates across sequential steps                       |
| Pivots  | Tabular breakdowns of metrics by properties                    |
| Cohorts | Retention tables for user groups over time                     |
| Flows   | User path visualizations between events                        |
| Note    | Gives context, ownership, or instructions right inside a board |

<Callout icon="📘" theme="info">
  #### Important

  Each tile reflects the exact configuration applied in the analysis at the time it was added, including events, filters, breakdown properties, and chart type. If you later modify the original analysis, the tile does not automatically update unless you add it again or edit it from the board.
</Callout>

# Explore Data on Tiles

You do not need to leave the board to dig into your data. Each tile supports direct interaction, so you can explore metrics in context.

For example, you can:

* Hover over any data point to view a detailed tooltip with exact values, dates, and segment breakdowns.
* Compare metrics visually across time periods or user segments without switching tabs.

This in-board interactivity is especially useful during team reviews or when presenting data live, as you can explore the data without losing the board context.

## Apply Filters

Board-level filters let you update data across all supported tiles simultaneously, without reconfiguring each tile individually. This makes it easy to slice the same board for different time periods, geographies, user segments, or other dimensions.

When you apply a filter, all supported tiles update dynamically, and you can view the charts and tables refresh in real time to reflect the filtered data. No page reload is required.

Boards support the following two types of filters:

* [Date Range](doc:boards-v2#date-range)
* [Segment](doc:boards-v2#segment)

Each filter targets a different dimension of your data. You can apply one or both at the same time to narrow down what is displayed across the board.

### Date Range

Restrict each tile's data to a specific time window. For example, on a `Product Metrics` board, you might apply a date range of March 1 to March 31 to view all tile data scoped to March.


<Image src="https://files.readme.io/98b9036244cb74bb6d188951b23ea701c3fcd2f09335308c98b47f1e2b60e8cd-2026-04-13_13-29-03_1.gif" align="center" caption="Filter Board Data for a Date Range" border={true} />


You can select preset ranges (Last 7 days, Last 30 days, etc.) or a custom date range.

### Segment

Filter tiles by a defined user segment. For example, applying a `Churn After Purchase` segment to the board will update all supported tiles to show data only for users on mobile devices.


<Image src="https://files.readme.io/321dbb82de394b3c58fd5809a3e6b0aa9858134410baf384f07626145af350be-2026-04-13_13-31-43_1.gif" align="center" caption="Filter Board Data for a Segment" border={true} />


Segments must be pre-configured in your workspace before they can be applied here.

#### Filter Behavior by Tile Types

Not all tiles respond to board-level filters. Some tiles behave differently depending on what board-level filter is applied.

The table below shows how board-level filters respond to the board-level filters:

| Tile Type                        | Responds to Date Filter | Responds to Segment Filter |
| :------------------------------- | :---------------------- | :------------------------- |
| Trends, Funnels, Pivots, Cohorts | Yes                     | Yes                        |
| Flows                            | No                      | No                         |
| Note                             | No                      | No                         |

# Tile Operations

Each tile on a board has its own set of actions, accessible from the tile menu. These actions let you manage individual tiles without affecting the rest of the board.

To access the tile menu, click the ![](https://files.readme.io/e4c0310e2942b4fdf5b775b1a2cec22665f0af13cf4ab4aaae2802abef36d28b-Ellipsis_icon_Boards.png) icon in the top-right corner of any tile.


<Image src="https://files.readme.io/d25577affd29ff3f44f41380c0576bcc7e9686d5dcb19934983585334fbbd792-image.png" align="center" caption="Tile Operations In a Board" border={true} />


The following sections describe each operation in detail.

* [Edit](doc:boards-v2#edit)
* [Rename](doc:boards-v2#rename)
* [Rename Legend](doc:boards-v2#rename-legend)
* [Rename Legend & Steps](doc:boards-v2#rename-legend-&-steps)
* [Clone](doc:boards-v2#clone)
* [Export](doc:boards-v2#export)
* [Delete](doc:boards-v2#delete)

## Edit

Opens the underlying analysis (for example, Trends or Funnels) in edit mode, where you can make changes to events, filters, date ranges, or chart types. Once saved, the tile on the board updates to reflect the changes.

Use _Edit_ when the tile configuration needs to change. For example, when you want to add a new event to a Trends chart or modify the steps in a Funnel.

<Callout icon="📘" theme="info">
  #### Edit Tile Behavior

  Editing a tile opens the original saved analysis. Any changes saved in edit mode will update the analysis itself, not just the tile instance on the board.
</Callout>


<Image src="https://files.readme.io/c91ffb6ceb1932b1ab128dcdfd68dbc7a186ec23809f106bd14d219a893597bf-2026-05-19_23-26-52_1.gif" align="center" caption="Editing a Funnel Tile" border={true} />


## Rename Tile

Updates a tile's display name as it appears on the board. This does not affect the underlying analysis name.

Use _Rename Tile_ when the default analysis name is not descriptive enough for the board context. For example, rename _Untitled Trends_ to _Weekly Signups by Channel_.


<Image src="https://files.readme.io/5dd576d4d092136f2512b42af9b7efcd8b409a3816c3081127b506e9f52a777b-2026-05-19_23-28-48_1.gif" align="center" caption="Renaming a Note Tile" border={true} />


## Rename Legend

Updates the legend labels displayed on a Trends tile's chart. This is useful when the default event or property names are too technical or ambiguous for a broader audience.

Use _Rename Legend_ when presenting boards to non-technical stakeholders who may not recognize internal event naming conventions. For example, rename _Engaged Users_ to _Engaged Users in Last 30 Days_.


<Image src="https://files.readme.io/adebeb8eb75e5ff2b064faff32dc7ebb9ef7aedd0286acd49da33105651ff78b-2026-05-19_23-31-03_1.gif" align="center" caption="Renaming Legend of a Trends Tile" border={true} />


## Rename Legend & Steps

Updates both the legend labels and the step names displayed on a Funnels tile. This is useful when default event names or funnel step labels are not self-explanatory to the intended audience.

Use _Rename Legend & Steps_ when sharing a Funnels tile with stakeholders who are unfamiliar with the internal event names used to define funnel steps.


<Image src="https://files.readme.io/1a895588fd520171681321b710344b98e09b6dec0a3ef07f8720eb0f45fc2f1a-2026-05-19_23-33-03_1.gif" align="center" caption="Renaming Legends and Steps of a Funnel Tile" border={true} />


## Clone

Creates a duplicate of the tile on the same board. The cloned tile retains all configuration from the original and can be edited or renamed independently.

Use _Clone_ when creating a variant of an existing tile is required. For example, clone a Trends tile and edit it to display data for a different user segment.


<Image src="https://files.readme.io/b068f180a3b75568ba746a26f9747650b687f14df2108a59870f60c9bdbfb696-2026-05-19_23-35-56_1.gif" align="center" caption="Cloning a Pivot Tile" border={true} />


## Export

Downloads the tile's data as a file for offline use or sharing. The export format varies by tile type. For example, chart-based tiles, such as Trends, can be exported as PNG, PDF, or CSV, while table-based tiles, such as Pivots, can be exported as CSV.

Use _Export_ when sharing a specific chart or table with someone outside the platform, or when including it in a presentation or report.


<Image src="https://files.readme.io/1ee60fa1c2b8dd588be4a989524dd2659ad20a788ccc463b92457982c5854b82-2026-05-19_23-38-55_1.gif" align="center" caption="Exporting a Funnel Tile as a PDF" border={true} />


## Delete

Permanently removes a tile from the board. This does not delete the original analysis. Only the tile instance on the board is removed.

<Callout icon="📘" theme="info">
  #### Important

  Deleted tiles cannot be restored. If a tile is accidentally deleted, it must be added again from the original analysis.
</Callout>


<Image src="https://files.readme.io/27cc0b11c0e1a80c6a4a3d62f9652eaec96a416ec52261cf3d133b57ec7fb066-2026-05-19_23-41-31_1.gif" align="center" caption="Deleting a Pivot Tile" border={true} />


# Example Use Case: Monitoring Campaign Performance

Here is a practical end-to-end example of how you might use Boards 2.0 to monitor a marketing campaign:

1. Create a board called _Summer Campaign Performance_.
2. Add the following tiles:
   1. A Trends tile tracking daily click-through rates from campaign emails
   2. A Funnel tile showing drop-off at each step of the sign-up flow
   3. A Cohorts tile measuring 7-day retention for users acquired during the campaign
3. Apply a date filter scoped to the campaign period (for example, July 1 to July 31) to view data only for that window.
4. Share the board with your marketing team, assigning _Viewer_ access to stakeholders and providing _Editor_ access to analysts who will maintain the board.

With everything in one place, your team can track campaign performance in real time, identify funnel drop-off points, and understand retention, all without switching between separate reports.

# Best Practices

To ensure smooth board management and avoid disruptions in analysis, follow these best practices:

* Group related analyses into a single board organized by goal (for example, one board for acquisition, one for retention, one for monetization) rather than putting everything on one board.
* Use clear, descriptive tile names that explain what the data shows, including the metric, time frame, or segment where relevant (for example, New User Signups for Last 7 Days).
* Share boards with stakeholders proactively rather than sending one-off screenshots. Boards stay up to date and allow viewers to explore the data themselves.
* Avoid overloading a single board with too many tiles. A board with more than 15 tiles can become hard to navigate. Consider splitting by audience or use case.

# FAQs

Find answers to the following common questions about managing Boards:

### Q. Can I add the same analysis to multiple boards?

Yes. Each instance is an independent tile, and the changes to one board do not affect the others.

### Q. Does editing a tile change the original analysis?

Yes. When you click _Edit_ on a tile, it opens the original analysis. Any changes you save will be reflected in the tile and in the analysis itself.

### Q. Why is my board-level filter not affecting some tiles?

The _Flows_ and _Note_ tiles do not respond to date or segment filters. For more information, refer to the [Filter Behavior by File Types](doc:boards-v2#filter-behavior-by-file-types).

### Q. Who can delete a board?

The board owner and any _Editor_ can delete a board. _Viewers_ cannot delete boards.

### Q Can I reorder tiles on a board?

Yes. You can drag and drop tiles to rearrange them on the board layout.

### Q. Is there a limit on the number of tiles per board?

Yes. You can add a maximum of 20 tiles per board.
