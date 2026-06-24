---
title: Coupon Operations
excerpt: >-
  Learn how to manage, track, and take actions on your coupon lists using
  filters and status-based controls.
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

This document explains the available coupon statuses, the actions you can perform at each stage, and how to use filters to locate specific coupons quickly. For details about viewing and navigating the list of coupons, refer to [View Coupons](doc:view-coupons).

# Coupon Status

The status of a coupon determines whether it can be used in campaigns or modified. Use statuses to manage the coupon lifecycle effectively.

| Status        | Description                                                                            | Available Actions      |
| :------------ | :------------------------------------------------------------------------------------- | :--------------------- |
| **Draft**     | Coupon list has been created but is not available for campaigns yet.                   | Archive                |
| **Scheduled** | Coupon list is set to become active at a future date and time.                         | End, Archive           |
| **Active**    | Coupon list is live and available for use in promotional campaigns.                    | Pause, End, Archive    |
| **Paused**    | Coupon list is temporarily inactive; it cannot be used in campaigns until reactivated. | Activate, End, Archive |
| **Ended**     | Coupon list has expired or has been manually ended. It cannot be used further.         | Archive                |
| **Archived**  | Coupon list is permanently disabled and becomes view-only.                             | No actions             |

# Available Actions

Depending on the coupon list status, you can take different actions on a coupon list.

| Action             | Effect                                                                                                                                            |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Pause**          | Temporarily deactivates an active coupon list, making it unavailable for campaigns.                                                               |
| **Activate**       | Reactivates a paused coupon list, making it available for use again.                                                                              |
| **End**            | Stops the coupon list distribution, preventing further usage.                                                                                     |
| **Archive**        | Permanently disables a coupon list. It becomes read-only and cannot be reused.                                                                    |
| **Download Codes** | Allows you to download the list of coupon codes for record-keeping or offline distribution. It is only applicable to the Bulk downloadable codes. |

# Filter Coupons

Use _Filters_ to quickly sort and manage coupons based on their type, reward effect, reward type, and current status. This helps in locating specific coupons for review or action.


<Image src="https://files.readme.io/4a686e3a66fc9814bc68553b7e3649fd35f8d11c9c738f365babfe656fc3d4e6-Filter_Coupons.gif" alt="Filter Available Coupons" align="center" border={true} />


Filter Available Coupons

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<Table align={[null,null,"left"]}>
  <thead>
    <tr>
      <th>
        Filter Category
      </th>

      <th>
        Description
      </th>

      <th>
        Options Available
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Coupon Type**
      </td>

      <td>
        Filters coupons based on how they are distributed—shared codes or unique codes, assigned manually or through user actions.
      </td>

      <td>
        <li> **Single code for all users**: A single coupon code that can be used by all users.</li> <li>**Single code based on user actions**: A single code distributed to a specific segment through promo campaigns based on user actions defined in the Promo campaign.</li> <li>**Downloadable bulk unique codes**: Unique coupon codes generated in bulk for manual distribution.</li> <li>**Bulk unique codes based on user actions**: Unique codes automatically assigned to users based on defined actions.</li> <p> For more information, refer to [Select Coupon Type](doc:create-coupons#select-coupon-type).</p>
      </td>
    </tr>

    <tr>
      <td>
        **Reward Effect**
      </td>

      <td>
        Defines which part of the order the reward applies to: the full order value, selected products, or a custom-defined order property.
      </td>

      <td>
        <li>**Entire order**: The reward or discount applies to the entire order value.</li> <li>**Specific products**: The reward or discount applies only to selected products.</li> <li>**Custom order property**: The reward is applied based on a custom property of the order, as defined in the setup.</li>
      </td>
    </tr>

    <tr>
      <td>
        **Reward Type**
      </td>

      <td>
        Filters coupons based on how the reward is structured—fixed amount or percentage, applied as a discount or cashback.
      </td>

      <td>
        <li>**Flat discount**: A fixed amount of discount applied to the order.</li> <li>**Percentage-based discount**: A percentage-based discount applied to the order total or specific products.</li> <li>**Flat cashback**: Fixed cashback points credited to the user.</li> <li>**Percentage-based cashback**: Cashback provided as a percentage of the order amount.</li>
      </td>
    </tr>

    <tr>
      <td>
        **Status**
      </td>

      <td>
        Filters coupons based on their current status in the lifecycle.
      </td>

      <td>
        <li>**Active**: Coupon list is live and available for use in promotional campaigns.</li> <li>**Paused**: Coupon list is temporarily inactive; it cannot be used in campaigns until reactivated.</li> <li>**Draft**: Coupon list has been created but is not available for campaigns yet.</li> <li>**Scheduled**: Coupon list is set to become active at a future date and time.</li> <li>**Ended**: Coupon list has expired or has been manually ended. It cannot be used further.</li> <li>**Archived**: Coupon list is permanently disabled and becomes view-only.</li>
      </td>
    </tr>
  </tbody>
</Table>

<br />
