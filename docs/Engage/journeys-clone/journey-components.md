---
title: Journey Components
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
A Journey is a combination of Segment nodes, Engagement nodes, and Operator nodes. You can connect segment nodes and engagement nodes to each other to create powerful automation.

# Segment Nodes

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Segment Node
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Connectors from this node
      </th>

      <th style={{ textAlign: "left" }}>
        Exceptions
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        Action
      </td>

      <td style={{ textAlign: "left" }}>
        A user enters this node immediately after performing an action.
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Inaction
      </td>

      <td style={{ textAlign: "left" }}>
        These are segment users who performed the first event, but did not perform  the second event within a specified time interval.

        For example,  users who added to cart, but did not purchase within 5 minutes.
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.No\
        3.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Past Behaviour
      </td>

      <td style={{ textAlign: "left" }}>
        These are segment users who performed an event but did not  another set of events in the past 'n' number of  days.

        For example, users who watched Video AND did not pay for subscription  in the past 30 days.
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.No\
        3.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Date Time
      </td>

      <td style={{ textAlign: "left" }}>
        These are segment users based on a date time property value such as flight time.

        For example, users who have their flight scheduled after 2 hours.
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Journey Trigger
      </td>

      <td style={{ textAlign: "left" }}>
        This node can only be used in the entry criteria.\
        A Journey is triggered from another Journey. The users enter the triggered Journey from another Journey.  

        For example, Journey 1 has a Push message node. You want to move all users who are sent the push into Journey 2.  You can use the Journey trigger to move these users.
      </td>

      <td style={{ textAlign: "left" }}>
        Yes
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Page Visit
      </td>

      <td style={{ textAlign: "left" }}>
        These are segment users who enter the Journey as soon as they visit a specific page.

        This is a web-based segment
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Referrer Entry
      </td>

      <td style={{ textAlign: "left" }}>
        These are the segment users who enter the Journey from a referring website or campaign.

        This is a web-based segment.
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Page Count
      </td>

      <td style={{ textAlign: "left" }}>
        These are the segment users who enter a Journey when they visit a specified number of pages.  

        This is a web-based segment.
      </td>

      <td style={{ textAlign: "left" }}>
        1.Yes\
        2.Node Timeout
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>
  </tbody>
</Table>

# Engagement Nodes

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Engage Node
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Connectors
      </th>

      <th style={{ textAlign: "left" }}>
        Exceptions
      </th>

      <th style={{ textAlign: "left" }}>

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        Push
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Failed\
        3.Clicked\
        4.Unreachable
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        SMS
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Failed\
        3.Unreachable
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Email
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Failed\
        3.Viewed\
        4.Clicked\
        5.Unreachable
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Web Push
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Failed\
        3.Viewed\
        4.Clicked\
        5.Unreachable
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Webhook
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        Sent
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        In-app
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Viewed\
        3.Clicked
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Web Pop-up
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Viewed\
        3.Clicked
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Inbox
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Viewed\
        3.Clicked
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Exit Intent
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        1.Sent\
        2.Viewed\
        3.Clicked
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>
  </tbody>
</Table>

# Operator Nodes

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Operator Node
      </th>

      <th>
        Description
      </th>

      <th>
        Connectors
      </th>

      <th>
        Exceptions
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
        None
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

# Segment Timer

TBD

# Flow Timer

TBD

# Connectors

TBD
