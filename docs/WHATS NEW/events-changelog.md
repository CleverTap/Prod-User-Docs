---
title: Events Changelog
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Welcome to the Events changelog document for CleverTap. This changelog provides insights into system event updates in CleverTap, ensuring you use CleverTap effectively and monitor your metrics with greater accuracy.

We are dedicated to empowering businesses with advanced mobile marketing and analytics capabilities and delivering continuous improvements to meet our users' evolving needs. Stay tuned as we update this changelog regularly, informing our customers about any changes to existing system events or the introduction of new ones.

# February 2026

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Change Release Date
      </th>

      <th style={{ textAlign: "left" }}>
        Event Name
      </th>

      <th style={{ textAlign: "left" }}>
        Property Name
      </th>

      <th style={{ textAlign: "left" }}>
        Update Type
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        February 26, 2026
      </td>

      <td style={{ textAlign: "left" }}>
        Push Impression, Notification Clicked
      </td>

      <td style={{ textAlign: "left" }}>
        wzrk_sif
      </td>

      <td style={{ textAlign: "left" }}>
        Event Property Added
      </td>

      <td style={{ textAlign: "left" }}>
        Boolean property that indicates whether the push notification was delivered silently (no popup shown when the app is open). For more information, refer to [Push Editor](doc:push-editor#android-options).
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        wzrk_dismiss
      </td>

      <td style={{ textAlign: "left" }}>
        Event Property Added
      </td>

      <td style={{ textAlign: "left" }}>
        This property enables automatic dismissal of a push notification from the notification tray after a specified duration.

        On Android 8.0 or later, you can configure the dismissal time (in seconds). Once the set duration elapses, the notification is removed from the tray even if the user has not interacted with it.

        For example, setting `wzrk_dismiss` = 10 removes the notification after 10 seconds.

        This is useful for time-sensitive notifications, such as flash sale alerts, which may become irrelevant after a short period.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>
        wzrk_sticky
      </td>

      <td style={{ textAlign: "left" }}>
        Event Property Added
      </td>

      <td style={{ textAlign: "left" }}>
        This property controls whether a push notification remains pinned in the notification tray and cannot be dismissed by swiping.

        For Android 14 and above, you can configure a notification as sticky using `wzrk_sticky` with a value of true or false. When set to true, the notification persists in the tray and cannot be swiped away by the user.

        The notification remains visible until the user interacts with it (for example, by tapping it) or it is programmatically dismissed.

        This is useful for critical or ongoing updates, such as OTPs, ride status updates, or delivery tracking notifications.
      </td>
    </tr>
  </tbody>
</Table>

# October 2025

| Change Release Date | Event Name              | Property Name | Update Type | Description                                                                                                                                                                                                                                |
| :------------------ | :---------------------- | :------------ | :---------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| October 8, 2026     | CT Custom Reward Issued |               | Event Added | This event is raised when a custom reward is issued to a user through a Promo campaign or API. For more information about the properties of this event, refer to CT Custom Reward Issued under [System Events](doc:events#system-events) . |

# June 2025

| Change Release Date | Event Name                  | Property Name | Update Type | Description                                                                                                                                                                                                                    |
| :------------------ | :-------------------------- | :------------ | :---------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| July 1, 2025        | Notification Failed         |               | Event Added | This event captures the errors that occurred in the WhatsApp campaign.                                                                                                                                                         |
| June 30, 2025       | CT Coupon Rewarded          |               | Event Added | This event is raised when the coupon is issued to a user through a Promo campaign. For more information about the properties of this event, refer to CT Coupon Rewarded under [System Events](doc:events#system-events).       |
| June 30, 2025       | CT Coupon Redeemed          |               | Event Added | This event is raised when the user redeems the coupon through the coupon redemption API. For more information about the properties of this event, refer to CT Coupon Redeemed under [System Events](doc:events#system-events). |
| June 30, 2025       | CT Coupon Reverted          |               | Event Added | This event is raised when a redeemed coupon is reversed. For more information about the properties of this event, refer to CT Coupon Reverted under [System Events](doc:events#system-events).                                 |
| June 30, 2025       | CT Points Credited          |               | Event Added | This event is raised when points are credited to the loyalty wallet. For more information about the properties of this event, refer to CT Points Credited under [System Events](doc:events#system-events).                     |
| June 30, 2025       | CT Points Debited           |               | Event Added | This event is raised when points are debited from the loyalty wallet. For more information about the properties of this event, refer to CT Points Debited under [System Events](doc:events#system-events).                     |
| June 30, 2025       | CT Partner Voucher Rewarded |               | Event Added | This event is raised when a user receives a third-party partner voucher. For more information about the properties of this event, refer to CT Partner Voucher Rewarded under [System Events](doc:events#system-events).        |

# February 2025

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Change Release Date
      </th>

      <th>
        Event Name
      </th>

      <th>
        Property Name
      </th>

      <th>
        Update Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        February 5th, 2025
      </td>

      <td>
        Notification Delivered
      </td>

      <td>
        * <br />
      </td>

      <td>
        Others
      </td>

      <td>
        This event is raised for Email campaigns, indicating the successful delivery to the end user. For more information, refer to [Email Campaign Stats](doc:email-campaign-stats-delivered).

        _Note_: Delivered is currently released in Private Beta. Contact your Customer Success Manager to enable this for email campaigns.
      </td>
    </tr>
  </tbody>
</Table>

# October

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Change Release Date
      </th>

      <th>
        Event Name
      </th>

      <th>
        Property Name
      </th>

      <th>
        Update Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        October 11th, 2024
      </td>

      <td>
        Notification Failed
      </td>

      <td>

      </td>

      <td>
        Others
      </td>

      <td>
        This event also captures errors that occur in email campaigns. For more information, refer to [Events](doc:events).

        _Note_: This event is currently in Private Beta. Contact your account manager to enable this event.
      </td>
    </tr>
  </tbody>
</Table>

# June

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Change Release Date
      </th>

      <th>
        Event Name
      </th>

      <th>
        Property Name
      </th>

      <th>
        Update Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        June 19th, 2024
      </td>

      <td>
        Notification Failed
      </td>

      <td>

      </td>

      <td>
        Event Added
      </td>

      <td>
        This event captures the errors that occurred in the campaign.

        This event is currently in private beta and can be enabled upon request. Contact your account manager if you need access to this event.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Campaign ID
      </td>

      <td>

      </td>

      <td>
        The property helps identify the specific campaign associated with the error.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Campaign Type
      </td>

      <td>

      </td>

      <td>
        The property indicates the type of campaign (for example, WhatsApp, SMS).
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Error
      </td>

      <td>

      </td>

      <td>
        The property describes the title of the error observed in the campaign.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Label
      </td>

      <td>

      </td>

      <td>
        The property denotes the specific label associated with the error.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Variant
      </td>

      <td>

      </td>

      <td>
        The property helps identify the errors for a specific campaign variant in the case of A/B, split delivery, or multi-variant campaigns.
      </td>
    </tr>
  </tbody>
</Table>

# May

| Change Release Date | Event Name        | Property Name | Update Type      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| :------------------ | :---------------- | :------------ | :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| May 15, 2024        | Push Unregistered |               | Properties Added |                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|                     |                   | Source        |                  | <ul><li> **CT_Push**: Indicating that the event is raised via silent Push. In this case, FCM returns a [404 Unregistered error]() for stale tokens from devices that have not connected to FCM for 270 days or for users who have uninstalled the app. </li> <li> **CT_SDK**: Indicating that the event is raised via OnUserLogin() method.</li> <li> **CT_Target**: Indicating that the event is raised via campaigns or journeys. </li></ul> |
|                     |                   | Token Value   |                  | The property contains the actual token value.                                                                                                                                                                                                                                                                                                                                                                                                  |
|                     |                   | Token Type    |                  | <ul><li> FCM </li> <li> Baidu </li> <li> Huawei </li></ul>                                                                                                                                                                                                                                                                                                                                                                                     |
|                     |                   | targetId      |                  | The property denotes the ID of the campaign or journey.                                                                                                                                                                                                                                                                                                                                                                                        |

# April

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Change Release Date
      </th>

      <th>
        Event Name
      </th>

      <th>
        Property Name
      </th>

      <th>
        Update Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        April 2, 2024
      </td>

      <td>
        Notification Clicked
      </td>

      <td>

      </td>

      <td>
        Property Added
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        button_id
      </td>

      <td>

      </td>

      <td>
        The property is visible for the event if the _Notification Clicked_ event is tracked for button clicks associated with the new Image Interstitial template. Therefore, the customers adopting this template will see this new property.

        For more information, refer to [In-App Image Interstitial Template](doc:in-app-editor#image-interstitial).
      </td>
    </tr>
  </tbody>
</Table>
