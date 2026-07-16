---
title: Schema
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
# Overview

A Schema is a framework for maintaining, organizing, and structuring your data. It enforces rules to maintain data integrity, allowing you to avoid data quality issues later. Schema standardizes your data before you even begin using it. Since bad data incdurs high costs in terms of effort and money, you can save a significant amount of manual effort in tracking your data over time.

To preserve data sanity, the schema table stores event and user properties in a pre-defined order. It ensures better output because it enforces standardization of the incoming data and avoids duplication or corruption of data. Better input leads to a better outcome in your campaigns and journeys. It also provides more accurate insights into your data analytics.

# Events

You can see your events under _Settings_ > _Schema Events_. On this page, you can view all the events you are working with, along with editing or discarding to searching and filtering them.

The _Events_ schema has four parts:

- [Custom events](https://docs.clevertap.com/docs/schema#section-custom-events)
- [System events](https://docs.clevertap.com/docs/schema#section-system-events)
- [Conversion event](https://docs.clevertap.com/docs/schema#section-conversion-event)
- [Qualifying event](https://docs.clevertap.com/docs/schema#section-qualifying-event)

# Custom Events

Custom events are events that you can define, edit, remove, and so on. These are your app events that you can fully control.

1. Navigate to _Settings_ > _Schema_ > _Events_.
2. Click the **Custom events** tab.

If you have already defined your events, they are all present on this tab.


<Image src="https://files.readme.io/a13c357-Custom_Events.png" align="center" caption="View Custom Events" border={true} />


| Event Detail   | Description                                                                                                                                                                                                                                                                                                                                                         |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Event name** | The name of the event as it is displayed on the dashboard.                                                                                                                                                                                                                                                                                                          |
| **Type**       | There are two types:<ul><li>**Defined:** Events that are part of your schema definition.</li><li>**Undefined:** Events that are not defined in the schema but passed to CleverTap.</li></ul>                                                                                                                                                                        |
| **Status**     | An event can have any of the following statuses:<ul><li>**Active:** An event that has been passed to CleverTap.</li><li>**Inactive:** An event that has not yet been passed to CleverTap.</li><li>**Discarded:** An event for which all past data has been dropped. Any future data that is passed for the event with the same name will also be dropped.</li></ul> |
| **DRP**        | Data retention policy defines the length of time that the data is retained.                                                                                                                                                                                                                                                                                         |
| **This month** | The number of occurrences of the event in the current month.                                                                                                                                                                                                                                                                                                        |
| **Last month** | The number of occurrences of the event in the previous month.                                                                                                                                                                                                                                                                                                       |
| **Count**      | A count can be an event, event property, or a user property update.                                                                                                                                                                                                                                                                                                 |
| **Properties** | Attributes that provide additional context around the event. For more information, refer to [Event Property](doc:events#event-properties).                                                                                                                                                                                                                          |

## Add Event

You can add an event from the _Custom events_ tab.

1. Navigate to _Settings_ > _Schema Events_ > _Custom events_.
2. Click the **+Event** button to add an event.
3. Add the event name. This name must be unique in the schema.


<Image src="https://files.readme.io/6a62a19-Add_New_Event.png" align="center" caption="Add Custom Event" border={true} />


For more information, refer to [Event Property](doc:events#event-properties).

### AI-Generated Descriptions for Custom Events

The system now automatically generates clear and consistent descriptions using AI, whenever a description field is clicked while creating or updating a custom event. You can choose to _Accept_ or _Dismiss_ the generated description. After accepting it, you can edit the description if needed.

This AI-generated description is further leveraged in the advanced AI features such as Prompt-to-Segmentation, Prompt-to-Analytics, and Prompt-to-Journeys.


<Image src="https://files.readme.io/56fe6da791b6e91a5bc71074e56b538495cdc52ed85f01e670bf1652263d6dbf-2026-03-24_12-13-17_1.gif" align="center" caption="AI-Generated Descriptions for Custom Events" border={true} />


## Edit Event

The name cannot be changed after the event is published.

1. Click the edit icon on the event row.
2. Edit the event name.
3. Click the checkmark.

## Set Data Retention Policy

The data retention policy (DRP) retains an event for the specified time before discarding it automatically. Your subscription plan will decide the default DRP limit.

1. Navigate to _Settings_ > _Schema_ > _Events_.
2. From the System Events tab, click the ellipsis on the event row and click **Set DRP**.
3. Select _Custom_, then enter your specific time limit.

<Callout icon="📘" theme="info">
  ###

  **CleverTap Essentials Plan Limit**

  The default DRP for CleverTap Essentials Plan users is one year, which cannot be changed.
</Callout>

4. Click **Save**.


<Image src="https://files.readme.io/ba7f979-SET_DRP.png" align="center" caption="Set Data Retention Policy" border={true} />


## Remove Event

You must be careful before removing an event. If you ever need to remove an event from the schema, remove it from the event row on the _Events_ page. You can only remove an inactive event from your schema; however, the effects are minimal because the event is not active. This action does not drop another event coming in with the same name.

1. Click the ellipsis menu on the event row.
2. Click **Remove**.


<Image src="https://files.readme.io/b6033f7-Custom_Events.png" align="center" caption="Remove an Event" border={true} />


After an event is removed:

- The entire event row is removed from the schema.
- If an event comes in with the same name, it is considered an undefined event.

## Discard Event

You can discard an active event from the schema. You can still see the event row in the schema; however, it will be marked as discarded.

<Callout icon="❗️" theme="error">
  ###

  **When Discarding an Event**

  You can only discard an active event. Exercise extreme caution when discarding an event because this action cannot be undone. This action has an impact on your schema because it purges all data for the discarded event. It also drops any future incoming event with the same name.
</Callout>

1. Click the ellipsis menu on the event row.
2. Click **Discard**.


<Image src="https://files.readme.io/6f94655-Discard_event.png" align="center" caption="Discard an Event" border={true} />


## Define Event

The events that are passed to CleverTap but not defined are marked as undefined events. You can define these events from the event row. Defining an event marks it as a recognized event in the schema, and therefore, when the event is received, this will not cause any error.

1. Click the ellipsis menu on the event row.
2. Select _Define Event_, and a new window displays.
3. Click **Define & Save**.

## Publish Schema/Events

To publish the events, perform the following:

1. Check that you have all the required events.
2. Click the **Publish Events** button.

| Event Name             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Property name**      | The name of the property.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Type**               | The type of property:<ul><li>**Defined:** Properties that you have added to the schema.</li><li>**Undefined:** Properties that you have not added to the schema and are currently receiving data.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Status**             | An event property can have any of the following statuses:<ul><li>**Active:** An event property that has been passed to CleverTap.</li><li>**Inactive:** An event property that has not yet been passed to CleverTap.</li><li>**Discarded:** An event property for which all past data has been dropped. Any future data passed for this user property with the same name will also be dropped.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Required**           | Defines whether a property is mandatory for the event:<ul><li><p><strong>Yes:</strong> The property is mandatory. The event is dropped if it is received without the event property.<br /><em>Note:</em> Use with caution. If an event is received without the required property, the entire event is dropped. This helps keep data clean but may unintentionally drop valid events.</p></li><li><p><strong>No:</strong> The property is optional. The event is allowed even if it is received without the event property.</p></li></ul>                                                                                                                                                                                                                                                                                        |
| **Data type**          | Defines the data type of the event property:<ul><li>String</li><li>Integer</li><li>Float</li><li>Boolean</li><li>Mixed</li><li>List</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Data type fallback** | The fallback action if the event property is not in the defined format:<ul><li><strong>Drop event:</strong> Drops the incoming event if the data type does not match.<br /><em>Note:</em> This action cannot be undone and purges all past and future data for the event.</li><li><strong>Drop event property:</strong> Drops the incoming event property if the data type does not match.<br /><em>Note:</em> This action cannot be undone and purges all past and future data for the event property.</li><li><strong>Allow property:</strong> Allows the property even if the data type does not match.</li></ul>An error is reported for all actions. A <em>drop</em> has higher severity, while <em>allow</em> has lower severity. For more information, see [Error Stream](https://docs.clevertap.com/docs/error-stream). |
| **Created on**         | The date when the user property was created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Description**        | The description of the event property. You can set this from the ellipsis menu on the event property row. The property is optional, and the event is allowed even if it is received without the event property.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

<Callout icon="📘" theme="info">
  ###

  **Effect of Changing the Data Type of an Event or User Property**

  - If you change the user or event property's data type, then all the incoming data will be validated as per the schema definition once you publish the changes.
  - The values already present in the old data type will not change in the new data type.
  - For the users who already have the value of the user/event property in the old data type, you will have to again pass the user/event property with the value that will have a new data type.
</Callout>

## Add Event Property

To add an event property:

1. Click the number of properties shown in the _Custom events_ tab
2. Click **+Property**, then click **Add new**.<br />You can also add an event property from the catalog by clicking **Add from catalog**. For more information, refer to [Add Columns from a Catalog](doc:catalog-data-ingestion#add-columns-from-a-catalog).
3. Enter a property name and choose the relevant property details.
4. Select the checkmark.


<Image src="https://files.readme.io/9a45a27-Add_property.png" align="center" caption="Add Event Property" border={true} />


### AI-Generated Descriptions for Event Properties

The system now automatically generates clear and consistent descriptions using AI, whenever a description field is clicked while creating or updating a event property. You can choose to _Accept_ or _Dismiss_ the generated description. After accepting it, you can edit the description if needed.

This AI-generated description is further leveraged in the advanced AI features such as Prompt-to-Segmentation, Prompt-to-Analytics, and Prompt-to-Journeys.


<Image src="https://files.readme.io/7382ad8ae86487a7d17b3c2cb618d1c10601d468825dcc15db8bf5b94e812e80-2026-03-24_12-23-09_1.gif" align="center" caption="AI-Generated Descriptions for Event Properties" border={true} />


## Edit Event Property

You can edit any column; however, you can only edit names for unpublished event properties.

1. Click the edit icon on the property row from the _Custom events_ tab.
2. Edit the property name and any other appropriate property details.
3. Click the checkmark.


<Image src="https://files.readme.io/804cbdc-Edit_Event_Property.png" align="center" caption="Edit Event Property" border={true} />


## Remove Event Property

You can remove an unpublished event property.

1. Click the ellipsis icon on the property row from the _Custom events_ tab.
2. Click **Remove**.

After an event property is removed:

- The entire event property row is removed from the schema.
- If an event property comes in with the same name, it is considered undefined.

## Discard Event

You can discard an active event from the schema. You can still see the event row in the schema; however, the event is marked as discarded. Post discarding, CleverTap removes the data after 16 days. However, you can choose to restore the discarded event after 24 hours. For more information, refer to [Restore Events](doc:schema#restore-event).

<Callout icon="❗️" theme="error">
  ### Caution When Discarding an Event

  You can discard only an active event. Discarding an event purges all data for that event and drops any future incoming events with the same name. This action impacts your schema. A discarded event can be restored, but only after 24 hours.
</Callout>

1. Click the ellipsis menu on the event row.
2. Click **Discard**.


<Image src="https://files.readme.io/6f94655-Discard_event.png" align="center" caption="Discard an Event" border={true} />


<Callout icon="📘" theme="info">
  ###

  **Discard Access**

  Only admin users can discard events.
</Callout>

## Restore Event

You can restore a previously discarded event, event property, or user property from the schema. Once restored, it becomes available again across Campaigns, Journeys, Analytics, and other features that use the schema.

<Callout icon="🚧" theme="warn">
  ###

  **Cooldown Period for Restore and Re-discard**

  - After you discard an item, you cannot restore it for the next 24 hours.
  - After you restore an item, you cannot discard it again for the next 24 hours.

  These measures prevent accidental or repeated changes to your schema.
</Callout>

### Restore a Single Item

1. Go to the _Custom events_ page.
2. Locate the discarded event you want to restore.
3. Click the ![](https://files.readme.io/d1a1a29245a043e42fe9f768ccb6c41e50dc1693d8b3553ac09edd9cadcc8355-Restore_Icon.png) icon.
4. In the confirmation window, click **Restore**.


<Image src="https://files.readme.io/b64c088b7f531e770b0e9b81441008e59bb5b099c0a00a2f8b0be2826e0b9568-image.png" align="center" caption="Restore Custom Event" border={true} />


### Restore Multiple Items

1. Go to the Events, or Event Properties, or User Properties table on the _Custom events_ page.
2. Select the discarded items you want to restore.
3. Click the ![](https://files.readme.io/4f93c7fed376db11d7b36dd4e54539e1a2284761341d8dfc3e227322f366d3d5-Restore_Icon.png) icon from the toolbar.
4. In the confirmation window, click **Restore**.


<Image src="https://files.readme.io/f3def79a65dda3e144e4a8711f3e4e0407dc1b61b35dbcb12699fbde4ba41230-image.png" align="center" caption="Bulk Restore Discarded Items" border={true} />


<Callout icon="📘" theme="info">
  ###

  **Restore Access**

  Only admin users can restore the discarded events.
</Callout>

# User Properties

This section shows how to manage your user properties.

1. Navigate to _Settings_ > _Schema_ > _User Properties_.  All the user properties are listed on this page.
2. Click any of the properties on the user property row to see the property details.

From this page, you can also search and filter properties.

| Property Detail        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Property name**      | The name of the user property.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Type**               | The type of property:<ul><li><strong>Defined:</strong> Properties that you have added to the schema.</li><li><strong>Undefined:</strong> Properties that you have not added to the schema and are currently receiving data.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                             |
| **Status**             | A user property can have any of the following statuses:<ul><li><strong>Active:</strong> A user property that has been passed to CleverTap.</li><li><strong>Inactive:</strong> A user property that has not yet been passed to CleverTap.</li><li><strong>Discarded:</strong> A user property for which all past data has been dropped. Any future data passed for this user property with the same name will also be dropped.</li></ul>                                                                                                                                                                                           |
| **Data type**          | Defines the data type of the user property:<ul><li>String</li><li>Integer</li><li>Float</li><li>Boolean</li><li>Mixed</li><li>List</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Data type fallback** | Includes the following actions:<ul><li><strong>Drop user property:</strong> Drops the incoming property if the data type does not match.<br /><em>Note:</em> Use with extreme caution. This action cannot be undone and purges all past and future data for the discarded user property.</li><li><strong>Allow property:</strong> Allows the property even if the data type does not match.<br />An error is reported for all actions. A <em>drop</em> has higher severity, while <em>allow</em> has lower severity. For more information, see <a href="https://docs.clevertap.com/docs/error-stream">Error Stream</a>.</li></ul> |
| **Created on**         | The date when the user property was created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

## Add User Property

To add a user property from this page:

1. Click the **+Property** button.
2. Enter a property name and choose a data type.
3. Click the checkmark.


<Image src="https://files.readme.io/fc5ba43-Add_User_Property.png" align="center" caption="Add User Property" border={true} />


### AI-Generated Descriptions for User Properties

The system now automatically generates clear and consistent descriptions using AI, whenever a description field is clicked while creating or updating a user property. You can choose to _Accept_ or _Dismiss_ the generated description. After accepting it, you can edit the description if needed.

This AI-generated description is further leveraged in the advanced AI features such as Prompt-to-Segmentation, Prompt-to-Analytics, and Prompt-to-Journeys.


<Image src="https://files.readme.io/5d86035f9560a43cd30ada370de9b3251562b1e81432bc25cf08e0cd44188fdb-2026-03-24_12-17-12_1.gif" align="center" caption="AI-Generated Descriptions for User Properties" border={true} />


## Edit User Property

You can edit any column; however, you can only edit names for unpublished user properties. To edit a property, click the edit icon on the property row.

1. Click the edit icon on the property row.
2. Edit the property name and the data type.
3. Click the checkmark.


<Image src="https://files.readme.io/0afe960-Edit_User_Property.png" align="center" caption="Edit User Property" border={true} />


## Remove User Property

You can remove an unpublished property.

1. Click the ellipsis icon on the property row.
2. Click **Remove**.

After a user property is removed:

- The entire user property row is removed from the schema.
- If a user property comes in with the same name, it is considered as an undefined user property.

## Discard User Property

You can discard a published user property from the schema. You can still see the property row in the schema; however, it will be marked as discarded.

1. Click the ellipsis icon on the property row.
2. Click **Discard**, and a new window displays.
3. Click **Discard** again.


<Image src="https://files.readme.io/d75580c-Discard_User_Property.png" align="center" caption="Discard User Property" border={true} />


<Callout icon="❗️" theme="error">
  ###

  **When Discarding a User Property**

  Exercise extreme caution when discarding a user property. This action cannot be undone. This action has an impact on your schema because it purges data for the discarded user property. It also drops any future incoming user property with the same name.
</Callout>

## Create Linked Event for User Property

You can link an event with a user property. This allows you to trigger campaigns, conversions, and exits based on changes in user properties. For example, a gaming app has a user property named `Game Level` that represents a user's progress in the game. You can link an event named `Game Level Upgraded` to the `Game Level` user property. By doing so, any change in this property to a higher level will activate a campaign. The campaign will congratulate the users and grant them a reward or a unique power corresponding to their achievement.

<Callout icon="📘" theme="info">
  ###

  **Key Points to Remember**

  - This feature is supported only for messaging channels such as Push, SMS, Email, In-App, Webhooks, and remarketing channels such as Google Ads and Facebook Audiences.
  - For In-App, CleverTap SDK v7.0.0 or higher is required.
  - User property updates via Journeys are not supported for this feature.
</Callout>

To link an event with a user property:

1. Navigate to _Settings_ > _Schema_ > _User Property_ from the CleverTap dashboard.
2. Click the ![](https://files.readme.io/01a6671-Ellipsis.png) icon and select _Create Linked Event_.
3. Enter the _Event Name_ and click **Create Event**.

Create Linked Event

### Create Linked Events in Bulk

You can select multiple user properties at a time and link a required event to it.

To create linked events in bulk:

1. Select the user properties you want to link and click the ![](https://files.readme.io/9bd94d1-Bulk_Link.png) icon.


   <Image src="https://files.readme.io/6675b4f-Bulk_Link_Event.png" align="center" caption="Bulk Link Events" border={true} />


2. Enter the events you want to link for each user property and click **Create**.


   <Image src="https://files.readme.io/7b5b7fd-Create_Linked_Events_in_Bulk.png" align="center" caption="Create Linked Events in Bulk" border={true} />


### Discard Linked Event

You can discard a linked event from the user property.

To discard linked events:

1. Click the ![](https://files.readme.io/01a6671-Ellipsis.png) icon of the user property.
2. Select _Discard Linked Event_ and click **Discard**.


<Image src="https://files.readme.io/5980787-Discard_Linked_Event.gif" align="center" caption="Discard a Linked Event" border={true} />


<Callout icon="📘" theme="info">
  ###

  **Key Points to Remember**

  The following are the key points to consider when creating linked events:

  - You can link only one event with a user property.
  - You can link events only on active properties.
  - You cannot create a linked event with the same name as a system event.
  - Discarding a linked event from the user property:
    - Delinks the event and the user property.
    - Stops receiving additional data associated with the user property.
    - Does not delete any data.
</Callout>

# System Events

System events are tracked automatically. CleverTap offers the capability to configure system events, enabling businesses to monitor and analyze user actions in their applications. However, some businesses may not have an immediate need for certain system events, resulting in potentially avoidable expenses. CleverTap allows businesses to configure those unused system events, providing a seamless process to address this issue.

## Configure System Events

To configure the tracking of system events:

1. Navigate to _Settings_ > _Schema_ > _Events_ from the CleverTap dashboard.
2. Select the event that you want to configure from the _System events_ tab.
3. Click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon and select _Enable/Disable_ from the list.


<Image src="https://files.readme.io/4454bcf-UTM_Tracking_Toggle_Off.gif" align="center" caption="Turn Off Toggle to Disable Tracking UTM Visited" border={true} />


Currently, you can enable or disable tracking for the following events from the CleverTap dashboard:

<Accordion title="Push Impressions">
  The Push Impression event is tracked when a push notification sent from CleverTap is delivered to a user’s device. After the toggle for Push Impressions is turned on, the CleverTap SDK starts recording an event whenever a push notification sent via CleverTap is delivered to the user’s device.

  The *Push Impression* event has its own event properties and the users can configure these non-required event properties to optimize the cost.

  To do so:

  1. Navigate to *Settings* > *Schema* > *Events* from the CleverTap dashboard.
  2. Select the *Push Impressions* event from the *System events* tab.
  3. Click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon and select *Setup push impressions* from the list.
  4. Turn ON the **Mobile Push** toggle and click **Save**. The *Push impressions tracking enables* message displays on the screen.

  <Image align="center" border={true} src="https://files.readme.io/94f4dcb-Turn_Off_Push_Impression_Tracking.gif" />

  ### Disable Event Property Tracking

  The users can disable the tracking of some of the *Push Impression* event properties from the CleverTap dashboard. However, there are a few Push Impression event properties for which you do not have the option to disable the tracking. These are listed as follows:

  <Table align={["left","left","left"]}>
    <thead>
      <tr>
        <th>
          Property
        </th>

        <th>
          Property Description
        </th>

        <th>
          Configurable
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td>
          `wzrk_push_amp`
        </td>

        <td>
          Indicates whether push amplification is enabled.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_pn`
        </td>

        <td>
          Indicates whether the push notification is sent from CleverTap.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `CT Source`
        </td>

        <td>
          Specifies the source of the CleverTap campaign.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_id`
        </td>

        <td>
          Specifies the CleverTap campaign ID associated with the notification.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_pid`
        </td>

        <td>
          Specifies the unique ID for the push notification.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_pivot`
        </td>

        <td>
          Indicates the variant used in the A/B test campaign.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_acct_id`
        </td>

        <td>
          Specifies the CleverTap Account ID.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `CT App Version`
        </td>

        <td>
          Indicates the version of the CleverTap App.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_dt`
        </td>

        <td>
          Specifies the delivery type for the notification.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_acts`
        </td>

        <td>
          Refers to the CTA button included in the notification.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_pn_h`
        </td>

        <td>
          Indicates the RenderMax health status of the push notification.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_pn`
        </td>

        <td>
          Indicates that the notification is sent from CleverTap, if present.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_bp`
        </td>

        <td>
          Displays an image in the notification if the URL is present.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_sound`
        </td>

        <td>
          Plays the default or custom Android notification sound if present.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `nt`
        </td>

        <td>
          Displays the notification title; defaults to app name if absent or empty.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `nm`
        </td>

        <td>
          Displays the notification body; ignores the notification if absent or empty.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_dl`
        </td>

        <td>
          Opens the specified deeplink when the notification is clicked, if present.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_d`
        </td>

        <td>
          Ignores the notification if this key is present.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `ico`
        </td>

        <td>
          Displays the small notification icon from the specified URL if present and not empty.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_pivot`
        </td>

        <td>
          Identifies the variant type in A/B testing if present and not empty..
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_rnv`
        </td>

        <td>
          Raises the Push Impressions event if present and not empty.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_nms`
        </td>

        <td>
          Displays summary text with the image if present and not empty.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_st`
        </td>

        <td>
          Displays subtitle text next to the app name if present and not empty.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_clr`
        </td>

        <td>
          Applies the hex color to the small icon and app name (on Android versions below Pie) if present and not empty.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_bpds`
        </td>

        <td>
          Indicates the image rendering status with the following values:

          <ul><li> NO\_IMAGE- No image included</li>
          <li>SUCCESS- Image downloaded successfully</li>
          <li> NO\_NETWORK- Image included but no network connectivity</li>
          <li> DOWNLOAD\_FAILED- Image download failed due to an external error</li></ul>
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_cid`
        </td>

        <td>
          Refers to the channel ID used for the push notification.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_mutable_content`
        </td>

        <td>
          Enables rendering of rich push notification via extension class if set to true.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_bi`
        </td>

        <td>
          Specifies the badge icon to be displayed in the push notification.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_bc`
        </td>

        <td>
          Specifies the badge count to be shown on the app icon.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `Campaign Type`
        </td>

        <td>
          Indicates the campaign’s channel type (for example, Push, Email, SMS).
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_ttl`
        </td>

        <td>
          Specifies the time to live (TTL) for the notification.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_ttl_s`
        </td>

        <td>
          Specifies the time to live for the notification in seconds.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_cts`
        </td>

        <td>
          Records the timestamp when the notification is clicked.
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_ck`
        </td>

        <td>
          Defines the collapse key (typically a timestamp) for the notification.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_collapsible`
        </td>

        <td>
          Specifies whether the notification is collapsible.
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_category`
        </td>

        <td>
          Specifies the notification category for APNS (iOS only).
        </td>

        <td>
          Yes
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_interruption_level`
        </td>

        <td>
          Sets the interruption level on APNS (iOS only).
        </td>

        <td>
          No
        </td>
      </tr>

      <tr>
        <td>
          `wzrk_relevance_score`
        </td>

        <td>
          Assigns the relevance score on APNS (iOS only).
        </td>

        <td>
          No
        </td>
      </tr>
    </tbody>
  </Table>

  To disable the tracking of Push Impression event properties:

  1. From the *System events* tab, click the *Properties* hyperlink. The Push Impressions properties list opens.

     <Image align="center" border={true} src="https://files.readme.io/1dd0fc5-View_Push_Impressions_Properties.png" />
  2. Select the configurable property, click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon, and select *Disable Property* from the list. The *Enable property tracking* popup opens.

     <Image align="center" border={true} src="https://files.readme.io/479d1ac-Disable_a_Push_Impression_Property.gif" />
  3. Click **Disable** to confirm your action. The *Property tracking successfully disabled* message displays on the screen. The status of the event property changes to *Active*. Once disabled, if you want to enable the tracking later, you can do so by clicking the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon and selecting **Enable Property** from the list.

  <Callout icon="📘" theme="info">
    **Key Points to Remember**

    The following are some of the points to consider when configuring the *Push Impressions* event:

    * The event property tracking feature is not available for required properties.
    * The **Status** is always *Active* for mandatory properties.
    * The tracking of configurable properties is enabled by default for new (new users of CleverTap dashboard) or returning users (existing users who turned off push impression feature) of Push Impression feature.
    * For existing users, the tracking of event properties remains as is, however, they have the additional capability to enable/disable tracking for the same.
  </Callout>
</Accordion>

<Accordion title="Web Session Started">
  This is a web entry event similar to the App launched event. This event refers to the event triggered when a user starts a session or engages with your website. This event will be recorded in two cases:

  * When a user opens a webpage.
  * When a user reloads the browser after 20 minutes of inactivity.

  <Callout icon="📘" theme="info">
    **Default Behavior**

    This event is disabled by default for all customers and can be configured by the customers. When enabled, it captures the unique visitors to the website in a particular session.
  </Callout>
</Accordion>

<Accordion title="UTM Visited">
  The *UTM Visited* event is tracked when a user clicks on a link from a marketing campaign that has a UTM parameter defined on it. This event is also tracked when a CleverTap-integrated attribution platform, such as AppsFlyer or Branch, sends this information to CleverTap. This event is recorded for your marketing campaigns from external sources, such as Google Ads or Facebook.

  <Callout icon="📘" theme="info">
    **Default Behavior**

    The UTM Visited tracking is ON for new customers by default. For existing customers, the tracking of UTM Visited remains as is. However, they have the capability to enable or disable the same.
  </Callout>
</Accordion>

<Callout icon="📘" theme="info">
  ###

  **Configuring Other System Events**

  For the remaining system events, you can only change the DRP.
</Callout>

# Conversion Event

The conversion event helps track conversion.

To set a conversion event:

1. Navigate to _Settings_ > _Schema_ > _Events_.
2. Click the **Conversion event** tab.

To track revenue, set the user conversion event and revenue property. This property must be a numeric value.

# Qualifying Event

To set a qualifying event:

1. Navigate to _Settings_ > _Schema_ > _Events_.
2. Click the **Qualifying event** tab.

This event qualifies users as active if they have performed the event at least once in the defined time.

Currently, the [active %](https://docs.clevertap.com/docs/trends#section-active) tab uses the qualifying event on the _Trends_ page.


<Image src="https://files.readme.io/5d67342-set_qualifying.png" align="center" caption="Set Qualifying Event" border={true} />


# Download Schema Data from Dashboard

You can download event and user property data from the _Schema_ page as a CSV file. The downloaded report includes event and property metadata, such as name, type, status, and creation date, along with the dependency columns, such as Campaign Count, Campaign IDs, Journey Count, Journey IDs, Segment Count, and Segment IDs

## Event Data

To download event data as a CSV:

1. Go to _Settings_ > _Schema_ > _Events_.
2. From the _System events_ or _Custom events_ tab, click **Download as CSV**. A dialog appears where you choose whether to include property-level data.
3. Click **Download**.

The following image shows the Download CSV button in the _System Events_ tab:


<Image src="https://files.readme.io/ed95a6f665ff336263b433b47db1cacc31586d7e1ada34a551b34e081c56b45c-image.png" alt="Download as CSV button in the System Events tab" align="center" caption="Download Event Data" border={true} />


## User Property Data

To download user property data as a CSV:

1. Go to _Settings_ > _Schema_ > _User Properties_.
2. Click **Download as CSV**. A confirmation dialog appears.
3. Click **Download**.

The following image shows the Download CSV button in the _Custom User Property_ tab:


<Image src="https://files.readme.io/08adc1d3e4b44b853d69ac2f9f82a5823fe7fd649ffb886ab67a1edcb4501ad8-image.png" alt="Download as CSV button in the Custom User Property tab" align="center" caption="Download User Property Data" border={true} />


## CSV Columns

The following table describes the core columns included in the downloaded CSV. The dependency columns, Campaign Count, Campaign IDs, Journey Count, Journey IDs, Segment Count, and Segment IDs, show how each schema element is used across Campaigns, Journeys, and Segments.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Property Name / Event Name
      </td>

      <td>
        Name of the schema element.
      </td>
    </tr>

    <tr>
      <td>
        Type
      </td>

      <td>
        Indicates whether the element is _Defined_ or _Undefined_. A defined element has been explicitly added and configured in the schema. An _Undefined_ element has been observed in ingested data but has not yet been formally defined.
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        - **Active** -The event or property is currently receiving data.
        - **Inactive** - The event or property has been defined in the schema but has not yet received any data.
        - **Discarded** - All existing data for the event or user property definition has been removed, and any new incoming data with the same name is dropped rather than recorded. Campaigns, Journeys, and Segments that depend on this event or property stop working while it is discarded. The event can be restored, but only after a 24-hour cooldown period.
      </td>
    </tr>

    <tr>
      <td>
        Created On
      </td>

      <td>
        Date when this element was added to the schema.
      </td>
    </tr>

    <tr>
      <td>
        Campaign Count
      </td>

      <td>
        Number of campaigns that use this element.
      </td>
    </tr>

    <tr>
      <td>
        Campaign IDs
      </td>

      <td>
        IDs of the campaigns that use this element, separated by semicolons.
      </td>
    </tr>

    <tr>
      <td>
        Journey Count
      </td>

      <td>
        Number of journeys that use this element.
      </td>
    </tr>

    <tr>
      <td>
        Journey IDs
      </td>

      <td>
        IDs of the journeys that use this element, separated by semicolons.
      </td>
    </tr>

    <tr>
      <td>
        Segment Count
      </td>

      <td>
        Number of segments that use this element.
      </td>
    </tr>

    <tr>
      <td>
        Segment IDs
      </td>

      <td>
        IDs of the segments that use this element, separated by semicolons.
      </td>
    </tr>
  </tbody>
</Table>

## Download with API

To download event data or user profile data with the API, refer to the following:

- Use the [Events Schema API](https://developer.clevertap.com/docs/get-schema#section-get-events-schema-api) to download event data.
- Use the [User Properties Schema API](https://developer.clevertap.com/docs/get-schema#section-get-user-properties-schema-api) to download user profile data.

# Considerations

There are some specific validations when creating events and properties. For more information, refer to [Platform Considerations](doc:platform-considerations).

# FAQs

### Can we get all past behavior data for an event after discarding it?

No, we cannot get all past behavior data for an event after discarding it.

### Does a discarded event appear under the user profile in the user's activity?

No, a discarded event does not appear under the user profile in the user's activity.

### For how many days can I get the data of discarded events?

You will not get any event data after discarding an event. We recommend you export that event before you delete it.

### If we disable the UTM Visited event from the schema, can it still be ingested through third-party mediums such as attribution tools like AppsFlyer or Customer Data Platforms (CDPs) like Segment?

When the UTM Visited event is disabled from the schema, it is dropped at the processing layer, rendering it inaccessible for ingestion from any third-party medium.

<br />
