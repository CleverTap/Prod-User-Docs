---
title: Data Retention Policy_needs_update
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
# Overview

This page describes CleverTap's data retention policy (DRP) for user profiles and events. 

User profile data includes [identifiers, system properties, and custom properties](https://docs.clevertap.com/docs/user-profiles). The data retention policy for user profiles is store a current snapshot of a user profile forever. 

Event data includes [system events and custom events](https://docs.clevertap.com/docs/events). The data retention policy for events depends on both your plan type and settings you define in the CleverTap dashboard.

# Data Retention Policy by Plan Type

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Plan Type
      </th>

      <th>
        User Profile DRP
      </th>

      <th>
        Event DRP
      </th>

      <th>
        Can Modify Event DRP
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Business Plan** 
      </td>

      <td>
        Current snapshot stored forever.
      </td>

      <td>
        Automatically set to the maximum DRP of 10 years for all events. 

        When an event surpasses the DRP, the oldest event will be deleted first.
      </td>

      <td>
        Yes. Able to update the DRP for each event type. The minimum DRP that can be set is 3 months.
      </td>
    </tr>

    <tr>
      <td>
        **Enterprise Plan** 
      </td>

      <td>
        Current snapshot stored forever.
      </td>

      <td>
        Automatically set to the maximum DRP of 10 years for all events.

        When an event surpasses the DRP, the oldest event will be deleted first.
      </td>

      <td>
        Yes. Able to update the DRP for each event type. The minimum DRP that can be set is 3 months.
      </td>
    </tr>
  </tbody>
</Table>
