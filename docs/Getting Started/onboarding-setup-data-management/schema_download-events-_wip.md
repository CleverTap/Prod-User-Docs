---
title: Schema_download events _WIP
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

Schema is a framework to maintain your data, organize, and structure it. It enforces rules to maintain data integrity so that you can avoid data quality issues later. Schema standardizes your data before you even begin using it. Since bad data leads to a big cost in effort and money, you can save a lot of manual effort on tracking your data in the long run.

A schema table stores event and user properties in a pre-defined order to preserve data sanity. It ensures better output because it enforces standardization of the incoming data and avoids duplication or corruption of data. Better input leads to better output in your campaigns and journeys. It also provides more accurate insights in your data analytics.

# Events

You can see your events under *Settings* > *Schema Events*. On this page, you can view all the events you are working with, along with editing or discarding to searching and filtering them.

The *Events* schema has four parts: 

* [Custom events](https://docs.clevertap.com/docs/schema#section-custom-events) 
* [System events](https://docs.clevertap.com/docs/schema#section-system-events)
* [Conversion event](https://docs.clevertap.com/docs/schema#section-conversion-event) 
* [Qualifying event](https://docs.clevertap.com/docs/schema#section-qualifying-event) 

# Custom Events

Go to *Settings* > *Schema* > *Events*. Click the **Custom events** tab. 

Custom events are events that you can define, edit, remove, and so on. These are your app events that you can fully control. 

If you have already defined your events, they are all present on this tab. 

<Image title="Schema_Custom_Event_tab_main.png" alt={1182} className="border" border={true} src="https://files.readme.io/b80e1b8-Schema_Custom_Event_tab_main.png" />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Event detail
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Event name
      </td>

      <td>
        The name of the event as it is displayed on the dashboard.
      </td>
    </tr>

    <tr>
      <td>
        Type
      </td>

      <td>
        These are of two types:

        * Defined - Events that are part of your schema definition. 
        * Undefined - Events that are not defined in the schema but passed to CleverTap.
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        An event can have any of the following statuses:

        * Active - An event that has been passed to CleverTap. 
        * Inactive - An event which has not yet been passed to CleverTap.
        * Discarded - An event for which all past data has been dropped. Any future data that is passed for the event with the same name will also be dropped.
      </td>
    </tr>

    <tr>
      <td>
        DRP
      </td>

      <td>
        Data retention policy defines the length of time that the data is retained.
      </td>
    </tr>

    <tr>
      <td>
        This month
      </td>

      <td>
        The number of occurrences of the event in the current month.
      </td>
    </tr>

    <tr>
      <td>
        Last month
      </td>

      <td>
        The number of occurrences of the event in the previous month.
      </td>
    </tr>

    <tr>
      <td>
        Data Points
      </td>

      <td>
        A data point can be an event, event property, or a user property update.
      </td>
    </tr>

    <tr>
      <td>
        Properties
      </td>

      <td>
        Attributes that provide additional context around the event. For more information, see [Event Property](https://docs.clevertap.com/docs/schema#section-event-property).
      </td>
    </tr>
  </tbody>
</Table>

## Add Event

You can add an event from the *Custom events* tab. 

To add an event,  go to *Settings* > *Schema Events* > *Custom events*.

Click the **+Event** button to add an event. Add the event name. This name must be unique in the schema.

<Image title="Schema_Custom_Event_tab_main.png" alt={1182} className="border" border={true} src="https://files.readme.io/62b6153-Schema_Custom_Event_tab_main.png" />

For more information, see [Event Property](https://docs.clevertap.com/docs/schema#section-event-property).

## Edit Event

The name cannot be changed after the event is published.

To edit an event, click the edit icon on the event row. 

<Image title="Schema_Custom_Event_edit.png" alt={1196} className="border" border={true} src="https://files.readme.io/3fa0b42-Schema_Custom_Event_edit.png" />

## Set Data Retention Policy 

The data retention policy (DRP) retains an event for the specified time period before it is automatically discarded. Your subscription plan will decide the default DRP limit. This limit can be changed later. You can set the DRP to a minimum of 3 months and a maximum of 10 years. 

To set the DRP for an event, click the ellipsis menu on the event row and set the DRP. 

1. To set the DRP, click the ellipsis on the event row and select **Set DRP**. 
2. Select *Custom*, then set the slider to your specific time limit. 
3. Click **Save**. 

<Image title="Schema_Event_Set_DRP.png" alt={1197} className="border" border={true} src="https://files.readme.io/182357c-Schema_Event_Set_DRP.png" />

## Remove Event

You must be careful before removing an event. If you ever need to remove an event from the schema, you can remove it from the event row on the *Events* page. You can only remove an inactive event from your schema. However, the effects are minimal because the event is not active. This action does not drop another event coming in with the same name. 

To remove an event,  click the ellipsis menu on the event row and select **Remove**. 

<Image title="Schema_Custom_Event_remove.gif" alt={1190} className="border" border={true} src="https://files.readme.io/299ea33-Schema_Custom_Event_remove.gif" />

After an event is removed:

* The entire event row is removed from the schema.
* If an event comes in with the same name, it is considered as an undefined event.

## Discard Event

You can discard an active event from the schema. You can still see the event row in the schema. However, it will be marked as discarded.  

> ❗️ Note
>
> You can only discard an active event. Exercise extreme caution when discarding an event. This action cannot be undone. This action has an impact on your schema because it purges all data for the discarded event. It also drops any future incoming event with the same name.

To discard an event,  click the ellipsis menu on the event row and select **Discard**. 

<Image title="Schema_Custom_Event_discard.png" alt={1185} className="border" border={true} src="https://files.readme.io/f54134a-Schema_Custom_Event_discard.png" />

## Define Event

The events that are passed to CleverTap but not defined are marked as an undefined event. You can define these events from the event row. Defining an event marks it as a recognized event in the schema and therefore, when the event is received, this will not cause any error.

To define an event, click the ellipsis menu on the event row and select *Define Event*. Click **Define & Save**. 

<Image title="Schema_Event_Define.png" alt={1195} className="border" border={true} src="https://files.readme.io/2e440ef-Schema_Event_Define.png" />

## Publish Schema/Events 

Check that you have all the required events. You can then publish the events by clicking the **Publish Events** button. All the new events flowing in will be validated against the new rules set.\
You will get a confirmation email.

<Image title="Schema_Custom_Event_tab_Publish_events.png" alt={1172} className="border" width="100%" border={true} src="https://files.readme.io/16f841b-Schema_Custom_Event_tab_Publish_events.png" />

# Handle Undefined Data

You can handle all the undefined events simultaneously. To handle all undefined data, click the ellipsis menu on the *Events* page row, then select *Handle undefined data*.  The *Undefined data settings* page will be displayed. 

<Image title="Schema_custom_event_handle_undefined_all.png" alt={1191} className="border" border={true} src="https://files.readme.io/0fe398c-Schema_custom_event_handle_undefined_all.png" />

If an undefined event occurs:

* Allow event - The event is allowed to start recording data, even if it has not been defined in the schema.  
* Drop event - If the event is not defined in the schema, then it is dropped.

> ❗️ Note
>
> Exercise this option with caution. This is a powerful option to keep your data clean, but you will lose any unexpected data. This action cannot be undone.

If an undefined event property occurs:\
This option is only applicable to defined events that have undefined event properties. 

* Drop event - The event is dropped along with the event property.

> ❗️ Note
>
> Exercise this option with caution. If a defined event records an undefined event property, then the entire event is dropped. This is a powerful option to keep your data clean, but you could drop an existing event if it starts receiving an undefined property.

* Drop event property - Only the event property is dropped but the event is allowed.
* Allow event property - The event property is allowed to start recording data. 

> 📘 Note
>
> An error is reported for all actions. A drop will have a higher severity and allow will have a lower severity. For more information, see [Error Stream](https://docs.clevertap.com/docs/error-stream).

# Event Property

Go to *Settings* > *Schema* > *Events*. Click the **Custom events** tab. All the events are listed on this page. Click any of the properties on the event row to see the property details. 

<Image title="Schema_Custom_Event_Property_Main.png" alt={1192} className="border" border={true} src="https://files.readme.io/1c8b40b-Schema_Custom_Event_Property_Main.png" />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Property Detail
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Property name
      </td>

      <td>
        The name of the property
      </td>
    </tr>

    <tr>
      <td>
        Type
      </td>

      <td>
        The type of property:

        * Defined -  Properties that you have added to the schema. 
        * Undefined - Properties that you have not added to the schema and are currently receiving data.
      </td>
    </tr>

    <tr>
      <td>
        Description
      </td>

      <td>
        The description of the event property. You can set the description from the ellipsis menu on the event property row.
      </td>
    </tr>

    <tr>
      <td>
        Required
      </td>

      <td>
        Defines whether a property is mandatory for the event.

        * Yes - The property is mandatory. The event is dropped if it is received without the event property.
        * Note\*: Exercise this option with caution. If an event is received without the required property, then the entire event is dropped. This is a powerful option to keep your data clean, but you could drop an existing event if it starts receiving an undefined property.

          * No - The property is optional. The event is allowed even if it is received without the event property.
      </td>
    </tr>

    <tr>
      <td>
        Data type
      </td>

      <td>
        Defines the data type of the event property.

        * String
        * Integer
        * Float
        * Boolean
        * Mixed
        * List
      </td>
    </tr>

    <tr>
      <td>
        Data type fallback
      </td>

      <td>
        The fallback action if the event property is not in the defined format.   

        * Drop event - Drops the incoming event if the data type does not match.\
          Exercise extreme caution when dropping an event. This action cannot be undone. This action has an impact on your schema because it purges all data for the dropped event. It also drops any future incoming event with the same name.
        * Drop event property - Drops the incoming event property if the data type does not match.\
          Exercise extreme caution when dropping an event property. This action cannot be undone. This action has an impact on your schema because it purges all data for the dropped event property. It also drops any future incoming event property with the same name.
        * Allow property - Allows the property even if the data type does not match.

        An error is reported for all actions. A drop will have a higher severity and allow will have a lower severity. For more information, see [Error Stream](https://docs.clevertap.com/docs/error-stream).
      </td>
    </tr>
  </tbody>
</Table>

## Add Event Property

To add a property, click the **+Property** button from the *Custom events* tab. 

<Image title="Schema_custom_event_add_new_property.gif" alt={1198} className="border" border={true} src="https://files.readme.io/76f753e-Schema_custom_event_add_new_property.gif" />

## Edit Event Property

You can edit any column. However, you can edit names only for unpublished event properties. To edit a property, click the edit icon on the property row from the *Custom events* tab. 

<Image title="Schema_Custom_Event_edit_property.png" alt={1179} className="border" border={true} src="https://files.readme.io/5378185-Schema_Custom_Event_edit_property.png" />

## Remove Event Property

You can remove an unpublished event property. To remove a property, click the ellipsis icon on the property row from the *Custom events* tab. 

<Image title="Schema_Custom_Event_remove_property.png" alt={1198} className="border" border={true} src="https://files.readme.io/fb7a752-Schema_Custom_Event_remove_property.png" />

After an event property is removed:

* The entire event property row is removed from the schema.
* If an event property comes in with the same name, it is considered as an undefined event property.

## Discard Event Property

You can discard a published event property from the schema. You can still see the event property row in the schema. However, it will be marked as discarded.  

<Image title="Schema_Custom_Event_Property_discard.png" alt={1197} className="border" border={true} src="https://files.readme.io/dc986b7-Schema_Custom_Event_Property_discard.png" />

> ❗️ Note
>
> Exercise extreme caution when discarding an event property. This action cannot be undone. This action has an impact on your schema because it purges all data for the discarded event property. It also drops any future incoming event property with the same name.

# User Properties

Go to *Settings* > *Schema* > *User Properties*.  All the user properties are listed on this page and you can also add a property from this page.

All the user properties you are working with are displayed on this page. You can edit or discard properties from this page. You can search and filter properties from this page.

![1183](https://files.readme.io/e55f895-Schema_User_Property_Main.png "Schema_User_Property_Main.png")

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Property Detail
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Property name
      </td>

      <td>
        The name of the user property.
      </td>
    </tr>

    <tr>
      <td>
        Type
      </td>

      <td>
        The type of property:

        * Defined - Properties that you have added to the schema.
        * Undefined - Properties that you have not added to the schema and are currently receiving data.
      </td>
    </tr>

    <tr>
      <td>
        Status
      </td>

      <td>
        A user property can have any of the following statuses:

        * Active - A user property that has been passed to CleverTap.
        * Inactive - A user property which has not yet been passed to CleverTap.
        * Discarded - A user property for which all past data has been dropped. Any future data that is passed for this user property with the same name will also be dropped.
      </td>
    </tr>

    <tr>
      <td>
        Data type
      </td>

      <td>
        Defines the data type of the user property.

        * String
        * Integer
        * Float
        * Boolean
        * Mixed
        * List
      </td>
    </tr>

    <tr>
      <td>
        Data type fallback
      </td>

      <td>
        * Drop user property - Drops the incoming property if the data type does not match.
        * Note\*: Exercise extreme caution when dropping a user property. This action cannot be undone. This action has an impact on your schema because it purges all data for the discarded user property. It also drops any future incoming user property with the same name.
        * Allow property - Allows the property even if the data type does not match.\
          An error is reported for all actions. A drop will have a higher severity and allow will have a lower severity. For more information, see [Error Stream](https://docs.clevertap.com/docs/error-stream).
      </td>
    </tr>

    <tr>
      <td>
        Created on
      </td>

      <td>
        The date when the user property was created.
      </td>
    </tr>
  </tbody>
</Table>

## Edit User Property

You can edit any column. However, you can edit names only for unpublished user properties. To edit a property, click the edit icon on the property row.

<Image title="Schema_edit_property_User.png" alt={1186} className="border" border={true} src="https://files.readme.io/7b3b286-Schema_edit_property_User.png" />

## Remove User Property

You can remove an unpublished property. To remove a property, click the ellipsis icon on the property row from the *User properties* page.

<Image title="Schema_User_remove_property.png" alt={1184} className="border" border={true} src="https://files.readme.io/9ca9e6e-Schema_User_remove_property.png" />

After a user property is removed:

* The entire user property row is removed from the schema.
* If a user property comes in with the same name, it is considered as an undefined user property.

## Discard User Property

You can discard a published user property from the schema. You can still see the property row in the schema. However, it will be marked as discarded.

<Image title="Schema_User_Property_discard.png" alt={1187} className="border" border={true} src="https://files.readme.io/6817bc4-Schema_User_Property_discard.png" />

> ❗️ Note
>
> Exercise extreme caution when discarding a user property. This action cannot be undone. This action has an impact on your schema because it purges data for the discarded user property. It also drops any future incoming user property with the same name.

# System Events

System events are tracked automatically. You can only change the DRP for these events. You can choose to allow CleverTap to record the push impression event.

<Image title="Schema_Main.png" alt={1185} className="border" border={true} src="https://files.readme.io/b489df7-Schema_Main.png" />

# Conversion Event

To set a conversion event, go to *Settings* > *Schema* > *Events*. Click the **Conversion event** tab.\
The conversion event helps you to track conversion. To track revenue, set the user conversion event and revenue property. This property must be a numeric value. 

<Image title="Schema_Conversion_event.png" alt={1194} className="border" border={true} src="https://files.readme.io/cc3edc1-Schema_Conversion_event.png" />

# Qualifying Event

To set a qualifying event, go to *Settings* > *Schema* > *Events*. Click the **Qualifying event** tab. This is the event that qualifies users as active if they have performed the event at least once in the defined time period.

Currently, the qualifying event is used in the [Active %](https://docs.clevertap.com/docs/trends#section-active) tab on the *Trends* page.

<Image title="Schema_Qualifying_event.png" alt={1195} className="border" border={true} src="https://files.readme.io/99c9985-Schema_Qualifying_event.png" />

# Download Schema data

You can download the data for all events and user profiles either from the CleverTap dashboard or via an API. 

## Download from dashboard

## Event data

You can download event data from the CleverTap dashboard in CSV format.

1. Click Settings > Schema > Events. The Schema/Events page appears. You can download event data either from the System events tab or the Custom event tab. 
2. Click the Download as CSV button. The Download CSV file window appears. 
3. Select to download events or events with properties.

![806](https://files.readme.io/3897ef2-Schema_download_system_events.png "Schema_download_system_events.png")

## User Profile data

You can download all event data from the CleverTap dashboard in CSV format.

1. Click Settings > Schema > User properties. The Schema/Events page appears. 
2. Click the Download as CSV button.

![805](https://files.readme.io/43134ef-Schema_download_user_properties.png "Schema_download_user_properties.png")

## Download with API

1. Use the Events API to download Event data.
2. Use the Profile user API to download user profile data.

# Considerations

There are some specific validations when creating events and properties. For more information, see [Platform Considerations](doc:platform-considerations).
