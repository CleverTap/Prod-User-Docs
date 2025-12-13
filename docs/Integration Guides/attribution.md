---
title: Attribution Partners
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
CleverTap can track app installations, measure attribution with third-party sources, and view reports in the CleverTap Dashboard.

CleverTap supports integrations with the following third-party attribution providers:

* [Adjust](doc:adjust)
* [AppsFlyer](doc:appsflyer) 
* [Branch](doc:branch)

# Types of Data

CleverTap receives event data from the specified attribution partner and then processes and saves it. The following three types of event data are received from our attribution partners:

* **Inorganic Install Events** - These install events are attributed to some media source, for example, paid advertisements running on some third-party applications. It implies that the application is installed as a result of engaging with any advertisement.
* **Organic Install Events** - These install events are attributed to the website or app store or referrals. It implies that the application is installed either from the website, app store, or via referrals and not by engaging with any kind of advertisements.
* **Custom Events** - These events can be any events (other than install events) that are provided by the attribution partner and tracked in the app. 

The following table lists the default toggle state for each event:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Attribution Partner
      </th>

      <th>
        Inorganic Intall Events
      </th>

      <th>
        Organic Install Events
      </th>

      <th>
        Custom Events
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        CleverTap
      </td>

      <td>
        NA
      </td>

      <td>
        ON
      </td>

      <td>
        NA
      </td>
    </tr>

    <tr>
      <td>
        Adjust
      </td>

      <td>
        Always On
      </td>

      <td>
        OFF
      </td>

      <td>
        OFF
      </td>
    </tr>

    <tr>
      <td>
        AppsFlyer
      </td>

      <td>
        Always On
      </td>

      <td>
        OFF
      </td>

      <td>
        OFF
      </td>
    </tr>

    <tr>
      <td>
        Branch
      </td>

      <td>
        Always On
      </td>

      <td>
        NA
      </td>

      <td>
        OFF
      </td>
    </tr>
  </tbody>
</Table>

# Enabling Attribution Data

You can enable or disable the tracking of event data from the Attribution Partners page of the CleverTap dashboard. 

> 📘 Note
>
> To update the settings of this page, the user must have admin access or the required access rights.

To enable event data:

1. Go to *Settings > Partners > Attribution Partners*.
2. Click the **Edit** icon to view the toggle options.

<Image title="Attribution Partners_1.png" alt={1946} border={true} src="https://files.readme.io/2434871-Attribution_Partners_1.png">
  Clicking Edit icon
</Image>

The status for events can be as follows:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Status
      </th>

      <th>
        Definition
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        On
      </td>

      <td>
        Accept event data when shared by the partner.
      </td>
    </tr>

    <tr>
      <td>
        Off
      </td>

      <td>
        Decline event data shared by the partner.
      </td>
    </tr>

    <tr>
      <td>
        NA
      </td>

      <td>
        Event data not shared by the partner.
      </td>
    </tr>

    <tr>
      <td>
        Always On
      </td>

      <td>
        Always accept event data shared by the partner.
      </td>
    </tr>
  </tbody>
</Table>

3. Turn on the toggle to track event data for the required partner. You are prompted to save the changes.

<Image title="Click Save.png" alt={490} width="80%" border={true} src="https://files.readme.io/148c653-Click_Save.png">
  Saving Changes
</Image>

4. Click **Save**. On clicking, the respective attribution partner information is updated.

> 🚧 Warning
>
> If you enable more than one organic attribution partner, a warning for duplication of events is displayed at the top of the page as shown in the figure below. It is recommended to track the organic install event from only one attribution partner.

<Image title="Duplication of events.png" alt={1976} border={true} src="https://files.readme.io/6ad3d3e-Duplication_of_events.png">
  Warning for duplication of events
</Image>
