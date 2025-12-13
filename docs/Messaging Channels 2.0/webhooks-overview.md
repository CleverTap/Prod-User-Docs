---
title: Webhooks
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

CleverTap webhooks enable developers to monitor specific user events and receive push notifications to their server when those events happen. CleverTap webhooks are often used to trigger business workflows. For example, if you want to get notified every time a user looks up an international flight in business class but then doesn’t book the flight within 30 minutes. You can set up a webhook in CleverTap to monitor for this specific event, get notified when it happens, and then trigger a process in your call center to contact the user to complete the booking.

Another popular use case for CleverTap webhooks is with e-commerce companies and cart abandonment. For example, if a user abandons their cart during a high-value transaction. You can set up a webhook in CleverTap to monitor for this specific event, get notified when it happens, and then trigger a call center workflow to contact the user to solve any issues and complete the purchase. 

There are six categories of webhooks that you can create to monitor user events. The table below describes each of those categories.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Type
      </th>

      <th>
        Description
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Single action
      </td>

      <td>
        User performed an action.
      </td>

      <td>
        User launched the app.
      </td>
    </tr>

    <tr>
      <td>
        Actions
      </td>

      <td>
        User performed multiple actions.
      </td>

      <td>
        User launched the app and viewed a notification.
      </td>
    </tr>

    <tr>
      <td>
        Inaction within time
      </td>

      <td>
        User performed an action, but does not perform another action within a certain time.
      </td>

      <td>
        User has not launched the app in three days.
      </td>
    </tr>

    <tr>
      <td>
        Inaction
      </td>

      <td>
        Users performed an action, but did not perform another action.
      </td>

      <td>
        User launched the app, but did not view a notification.
      </td>
    </tr>

    <tr>
      <td>
        Date time property
      </td>

      <td>
        Period of time after a date time property on a user event.
      </td>

      <td>
        User purchased an item and three days have passed.
      </td>
    </tr>

    <tr>
      <td>
        Actions with user properties
      </td>

      <td>
        Performed an action or not, filtered by their demographic properties.
      </td>

      <td>
        User purchased an item and lives in Canada.
      </td>
    </tr>
  </tbody>
</Table>

Webhooks are created in the CleverTap dashboard by defining a user segment and a callback URL on your server. CleverTap sends a webhook as an HTTP POST with information about the event when it occurs. You can customize the webhooks to use basic authentication and include any custom properties if needed.
