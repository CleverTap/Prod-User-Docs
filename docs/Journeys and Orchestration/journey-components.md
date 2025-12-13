---
title: Journey components
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
# Journey Components

A Journey is a combination of *Segment* nodes and *Engagement* nodes. You can connect *Segment* nodes and *Engagement* nodes to each other to create powerful automation.

## Types of Segment nodes \<\<@vishal, DK, please provide input for blank tabes>>

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Segment Node
      </th>

      <th>
        What it does
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Action
      </td>

      <td>
        As soon as the user performs an action, the user enters this node.
      </td>

      <td>
        Qualification to this node occurs as soon as the user performs the said event.
      </td>
    </tr>

    <tr>
      <td>
        Inaction
      </td>

      <td>
        Segment users who did the 1st event, but did not do the second event within a specified time interval.
      </td>

      <td>
        For example, Qualify users who added to cart, but did not purchase within five mins.
      </td>
    </tr>

    <tr>
      <td>
        Past Behavior
      </td>

      <td>
        Segment users who performed and did not perform a set of events in the past *n* days.
      </td>

      <td>
        For example,Users who did Video Watched AND did not do Subscription Paid in the Last 30 days.
      </td>
    </tr>

    <tr>
      <td>
        Date Time
      </td>

      <td>
        Segment users based on a date time property value like flight time, etc.
      </td>

      <td>
        For example, users who have their flight after 2 hours.
      </td>
    </tr>

    <tr>
      <td>
        Journey Trigger
      </td>

      <td>
        You can use this node in the entry criteria only.\
        A user is qualified on this node when the same user is qualified for the corresponding node in another Journey, from where the current Journey is triggered.
      </td>

      <td>
        For example, Journey 1 has a push message node. You want to move all users who were sent the push into another Journey. Journey trigger allows you to do this.
      </td>
    </tr>

    <tr>
      <td>
        Page Visit
      </td>

      <td>
        Segment users as soon as they visit a specific page.
      </td>

      <td>
        Web based segment.
      </td>
    </tr>

    <tr>
      <td>
        Referrer Entry
      </td>

      <td>
        Segment users based on a referring website or campaign.
      </td>

      <td>
        Web based segment.
      </td>
    </tr>

    <tr>
      <td>
        Page Count
      </td>

      <td>
        Segment users based on the number of pages visited by them.
      </td>

      <td>
        Web based segment.
      </td>
    </tr>

    <tr>
      <td>
        Custom list
      </td>

      <td>
        You can use this node in the entry criteria only.  You can upload custom lists of users for engage in the Journey.
      </td>

      <td>
        Custom segment. For example, users from your Retail Point of Sale (POS).
      </td>
    </tr>
  </tbody>
</Table>

## Types of Engagement nodes

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Engagement Node
      </th>

      <th>
        What it does
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Push
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        SMS
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Email
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Webhook
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Web Push
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Web Pop-up
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Exit Intent
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        In-app
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Inbox
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Facebook
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Google
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Amazon event bridge
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        Segment
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        mParticle
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

# Controllers

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Controller Node
      </th>

      <th>
        What it does
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Force exit
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        User profile update
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>
