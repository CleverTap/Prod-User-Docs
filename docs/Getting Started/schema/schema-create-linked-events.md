---
title: Schema
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Schema is a framework to maintain your data, organize, and structure it. It enforces rules to maintain data integrity so that you can avoid data quality issues later. Schema standardizes your data before you even begin using it. Since bad data leads to a high cost in effort and money, you can save a lot of manual effort on tracking your data in the long run.

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


<Image src="https://files.readme.io/a13c357-Custom_Events.png" alt="1153" align="center" width="80%" border={true} />


| Event Detail | Description                                                                                                                                                                                                                                                                                                                                                  |
| :----------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Event name   | The name of the event as it is displayed on the dashboard.                                                                                                                                                                                                                                                                                                   |
| Type         | There are two types:<ul> <li>Defined: Events that are part of your schema definition. </li> <li>Undefined: Events that are not defined in the schema but passed to CleverTap.</li> </ul>                                                                                                                                                                     |
| Status       | An event can have any of the following statuses:<ul> <li>Active: An event that has been passed to CleverTap. </li> <li>Inactive: An event that has not yet been passed to CleverTap.</li> <li>Discarded: An event for which all past data has been dropped. Any future data that is passed for the event with the same name will also be dropped.</li> </ul> |
| DRP          | Data retention policy defines the length of time that the data is retained.                                                                                                                                                                                                                                                                                  |
| This month   | The number of occurrences of the event in the current month.                                                                                                                                                                                                                                                                                                 |
| Last month   | The number of occurrences of the event in the previous month.                                                                                                                                                                                                                                                                                                |
| Count        | A count can be an event, event property, or a user property update.                                                                                                                                                                                                                                                                                          |
| Properties   | Attributes that provide additional context around the event. For more information, refer to [Event Property](https://docs.clevertap.com/docs/schema#section-event-property).                                                                                                                                                                                 |

## Add Event

You can add an event from the _Custom events_ tab.

1. Navigate to _Settings_ > _Schema Events_ > _Custom events_.
2. Click the **+Event** button to add an event.
3. Add the event name. This name must be unique in the schema.


<Image src="https://files.readme.io/6a62a19-Add_New_Event.png" alt="Add a Custom Event" align="center" border={true} />


For more information, refer to [Event Property](https://docs.clevertap.com/docs/schema#section-event-property).

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
  ### CleverTap Basic Plan Limit

  The default DRP for CleverTap Basic Plan users is one year, which cannot be changed.
</Callout>

4. Click **Save**.


<Image src="https://files.readme.io/ba7f979-SET_DRP.png" alt="388" align="center" width="80%" border={true} />


## Remove Event

You must be careful before removing an event. If you ever need to remove an event from the schema, remove it from the event row on the _Events_ page. You can only remove an inactive event from your schema; however, the effects are minimal because the event is not active. This action does not drop another event coming in with the same name.

1. Click the ellipsis menu on the event row.
2. Click **Remove**.


<Image src="https://files.readme.io/b6033f7-Custom_Events.png" alt="1153" align="center" border={true} />


After an event is removed:

- The entire event row is removed from the schema.
- If an event comes in with the same name, it is considered an undefined event.

## Discard Event

You can discard an active event from the schema. You can still see the event row in the schema; however, it will be marked as discarded.

<Callout icon="❗️" theme="error">
  ### Caution When Discarding an Event

  You can only discard an active event. Exercise extreme caution when discarding an event because this action cannot be undone. This action has an impact on your schema because it purges all data for the discarded event. It also drops any future incoming event with the same name.
</Callout>

1. Click the ellipsis menu on the event row.
2. Click **Discard**.


<Image src="https://files.readme.io/6f94655-Discard_event.png" alt="1126" align="center" border={true} />


## Define Event

The events that are passed to CleverTap but not defined are marked as undefined events. You can define these events from the event row. Defining an event marks it as a recognized event in the schema, and therefore, when the event is received, this will not cause any error.

1. Click the ellipsis menu on the event row.
2. Select _Define Event_, and a new window displays.
3. Click **Define & Save**.

## Publish Schema/Events

To publish the events, perform the following:

1. Check that you have all the required events.
2. Click the **Publish Events** button.

| Event Name         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| :----------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Property name      | The name of the property.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Type               | The type of property:<ul> <li>Defined: Properties that you have added to the schema. </li> <li>Undefined: Properties that you have not added to the schema and are currently receiving data.</li> </ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Status             | An event property can have any of the following statuses:<ul> <li>Active: An event property that has been passed to CleverTap.</li> <li>Inactive: An event property that has not yet been passed to CleverTap.</li> <li>Discarded: An event property for which all past data has been dropped. Any future data passed for this user property with the same name will also be dropped.</li> </ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Required           | This defines whether a property is mandatory for the event.<ul> <li> <p>Yes: The property is mandatory. The event is dropped if it is received without the event property.<br /> <em>Note</em>: Exercise this option with caution. If an event is received without the required property, then the entire event is dropped. This is a powerful option to keep your data clean, but you could drop an existing event if it starts receiving an undefined property.</p> </li> <li> <p>No: The property is optional. The event is allowed even if it is received without the event property.</p> </li> </ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Data type          | This defines the data type of the event property:<ul> <li>String</li> <li>Integer</li> <li>Float</li> <li>Boolean</li> <li>Mixed</li> <li>List</li> </ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Data type fallback | The fallback action if the event property is not in the defined format:<ul> <li>Drop event: This drops the incoming event if the data type does not match.<br /> <em>Note</em>: Exercise extreme caution when dropping an event. This action cannot be undone. This action has an impact on your schema because it purges all data for the dropped event. It also drops any future incoming event with the same name.</li> <li>Drop event property: This drops the incoming event property if the data type does not match.<br /> <em>Note</em>: Exercise extreme caution when dropping an event property. This action cannot be undone. This action has an impact on your schema because it purges all data for the dropped event property. It also drops any future incoming event property with the same name.</li> <li>Allow property: This allows the property even if the data type does not match.</li> </ul>An error is reported for all actions. A _drop_ will have a higher severity, and _allow_ will have a lower severity. For more information, refer to [Error Stream](https://docs.clevertap.com/docs/error-stream). |
| Created on         | The date when the user property was created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Description        | The description of the event property. You can set the description from the ellipsis menu on the event property row. The property is optional. The event is allowed even if it is received without the event property.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

<Callout icon="📘" theme="info">
  ### Effect of Changing the Data Type of an Event or User Property

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


<Image src="https://files.readme.io/9a45a27-Add_property.png" alt="1144" align="center" border={true} />


## Edit Event Property

You can edit any column; however, you can only edit names for unpublished event properties.

1. Click the edit icon on the property row from the _Custom events_ tab.
2. Edit the property name and any other appropriate property details.
3. Click the checkmark.


<Image src="https://files.readme.io/804cbdc-Edit_Event_Property.png" alt="1184" align="center" border={true} />


## Remove Event Property

You can remove an unpublished event property.

1. Click the ellipsis icon on the property row from the _Custom events_ tab.
2. Click **Remove**.

After an event property is removed:

- The entire event property row is removed from the schema.
- If an event property comes in with the same name, it is considered undefined.

## Discard Event Property

You can discard a published event property from the schema. You can still see the event property row in the schema; however, it will be marked as discarded.

1. Click the ellipsis icon on the property row from the _Custom events_ tab.
2. Click **Discard**, and a new window displays.
3. Click **Discard** again.


<Image src="https://files.readme.io/40172c7-Discard_event_property.png" alt="531" align="center" width="80%" border={true} />


<Callout icon="❗️" theme="error">
  ### Caution When Discarding an Event Property

  Exercise extreme caution when discarding an event property. This action cannot be undone. This action has an impact on your schema because it purges all data for the discarded event property. It also drops any future incoming event property with the same name.
</Callout>

# User Properties

This section shows how to manage your user properties.

1. Navigate to _Settings_ > _Schema_ > _User Properties_.  All the user properties are listed on this page.
2. Click any of the properties on the user property row to see the property details.

From this page, you can also search and filter properties.

| <p>Property Detail</p>    | <p>Description</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| :------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Property name</p>      | <p>The name of the user property.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| <p>Type</p>               | <p>The type of property:</p><ul><li>Defined: Properties that you have added to the schema.</li><li>Undefined: Properties that you have not added to the schema and are currently receiving data.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <p>Status</p>             | <p>A user property can have any of the following statuses:</p><ul><li>Active: A user property that has been passed to CleverTap.</li><li>Inactive: A user property that has not yet been passed to CleverTap.</li><li>Discarded: A user property for which all past data has been dropped. Any future data that is passed for this user property with the same name will also be dropped.</li></ul>                                                                                                                                                                                                                                                                                                                                                  |
| <p>Data type</p>          | <p>This defines the data type of the user property:</p><ul><li>String</li><li>Integer</li><li>Float</li><li>Boolean</li><li>Mixed</li><li>List</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| <p>Data type fallback</p> | <p>This includes:</p><ul><li>Drop user property: This drops the incoming property if the data type does not match.<br /><em>Note</em>: Exercise extreme caution when dropping a user property. This action cannot be undone. This action has an impact on your schema because it purges all data for the discarded user property. It also drops any future incoming user property with the same name.</li><li>Allow property: This allows the property even if the data type does not match.<br />An error is reported for all actions. A <em>drop</em> will have a higher severity and <em>allow</em> will have a lower severity. For more information, refer to <a href="https://docs.clevertap.com/docs/error-stream">Error Stream</a>.</li></ul> |
| Created on                | The date when the user property was created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## Add User Property

To add a user property from this page:

1. Click the **+Property** button.
2. Enter a property name and choose a data type.
3. Click the checkmark.


<Image src="https://files.readme.io/fc5ba43-Add_User_Property.png" alt="Add User Property" align="center" border={true} />


## Edit User Property

You can edit any column; however, you can only edit names for unpublished user properties. To edit a property, click the edit icon on the property row.

1. Click the edit icon on the property row.
2. Edit the property name and the data type.
3. Click the checkmark.


<Image src="https://files.readme.io/0afe960-Edit_User_Property.png" alt="1109" align="center" width="80%" border={true} />


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


<Image src="https://files.readme.io/d75580c-Discard_User_Property.png" alt="525" align="center" width="80%" border={true} />


<Callout icon="❗️" theme="error">
  ### Caution When Discarding a User Property

  Exercise extreme caution when discarding a user property. This action cannot be undone. This action has an impact on your schema because it purges data for the discarded user property. It also drops any future incoming user property with the same name.
</Callout>

## Create Linked Event for User Property

You can link an event with a user property. This allows you to trigger campaigns, conversions, and exits based on changes in user properties. For example, a gaming app has a user property named `Game Level` that represents a user's progress in the game. You can link an event named `Game Level Upgraded` to the `Game Level`  user property. By doing so, any change in this property to a higher level will activate a campaign. The campaign will congratulate the users and grant them a reward or a unique power corresponding to their achievement.

<Callout icon="📘" theme="info">
  ### Key Points to Remember

  - This feature is supported only for messaging channels such as Push, SMS, Email, In-App, Webhooks, and remarketing channels such as Google Ads and Facebook Audiences.
  - For In-App, CleverTap SDK v7.0.0 or higher is required.
  - User property updates via Journeys are not supported for this feature.
</Callout>

To link an event with a user property:

1. Navigate to _Settings_ > _Schema_ > _User Property_ from the CleverTap dashboard.
2. Click the ![](https://files.readme.io/01a6671-Ellipsis.png) icon and select _Create Linked Event_.
3. Enter the _Event Name_ and click **Create Event**.


<Image src="https://files.readme.io/f3777e6-Create_Linked_Event_for_User_Property.gif" alt="Create Associated Event" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### **Note**

  The linked events are raised as custom events and contribute to MAU and DP usage, similar to any other custom event.
</Callout>

### Create Linked Events in Bulk

You can select multiple user properties at a time and link a required event to it.

To create linked events in bulk:

1. Select the user properties you want to link and click the ![](https://files.readme.io/9bd94d1-Bulk_Link.png) icon.


<Image src="https://files.readme.io/6675b4f-Bulk_Link_Event.png" alt="Select User Properties in Bulk" align="center" border={true} />


2. Enter the events you want to link for each user property and click **Create**.


<Image src="https://files.readme.io/7b5b7fd-Create_Linked_Events_in_Bulk.png" alt="Create Bulk Raise Events" align="center" border={true} />


### Discard Linked Event

You can discard a linked event from the user property.

To discard linked events:

1. Click the ![](https://files.readme.io/01a6671-Ellipsis.png) icon of the user property.
2. Select _Discard Linked Event_ and click **Discard**.


<Image src="https://files.readme.io/5980787-Discard_Linked_Event.gif" alt="Discard a Linked Event" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Key Points to Remember

  The following are the key points to consider when creating linked events:

  - You can link only one event with a user property.
  - You can link events only on active properties.
  - You cannot create a linked event with the same name as a system event.
  - Discarding a linked event from the user property:
    - Delinks the event and the user property.
    - Stops receiving additional data associated with the user property.
    - Does not delete any data.
</Callout>

# System User Properties: Locale and Language

CleverTap captures and provides specific user preferences from the device's operating system as system user properties. Locale and language reflect the user's regional and language settings. These settings are configured at the OS level, enabling you to deliver localized user experiences without additional implementation or custom attributes.

For example, when a user sets up a device and selects a preferred language or region, the SDK automatically reads this information and attaches it to the user's events.  CleverTap's predefined system user properties have a `CT` prefix, for example `CT Locale` and `CT Language`.

## Captured Properties

The SDK captures the following properties on supported platforms, including Android, iOS, and React Native. Web SDK does not support these properties.

| Property      | Description                                                           |
| ------------- | --------------------------------------------------------------------- |
| `CT Locale`   | Represents the user's regional setting, for example `en_US`, `en_GB`. |
| `CT Language` | Represents the user's language preference, for example `en`, `fr`.    |

These values are captured directly from the device operating system and follow standard formats:

- Language follows ISO 639, the international standard for two-letter language codes, for example `en` for English, `fr` for French.
- Region (locale) follows ISO 3166, the international standard for two-letter country codes, for example `US` for the United States, `GB` for the United Kingdom.

CleverTap stores these values exactly as received from the OS, without any normalization or transformation. This means the casing and format of the value depend on what the OS reports, and may vary across device manufacturers or OS versions.

The locale and language values are read from the device OS on every app launch. Within a single session, the values remain fixed even if the device language is changed mid-session. The updated value is reflected only on the next app launch. CleverTap updates the user profile with these values on every event, not only when the value changes.

If the OS does not provide a value for either property, the property is absent from the user profile and is not set to null. Segments or Campaigns filtered by these properties will not match users who lack them.

## Availability

Once captured, locale and language are available across the following areas on the CleverTap dashboard:

- User Profile
- Segment Builder (User Property filters)
- Find People
- Campaign targeting (By User Property)
- Personalization (Liquid Tags)
- Advanced AI features, including Prompt-to-Segmentation, Prompt-to-Analytics, and Prompt-to-Journey

The following image shows locale and language in the _User Profile&#x20;_&#x70;age:


<Image src="https://files.readme.io/b398793e3ebd63e318acbdd8a3340dac92c160d2e24a0bd9bf87a0b108af19a8-image.png" align="center" caption="Locale and Language in User Profile" border={true} />


The following image shows locale and language in the Segment Builder:


<Image src="https://files.readme.io/848568693447f7e3cab8f83be4067e4a88dcc5126633b95554102521411edad7-image.png" align="center" caption="Locale and Language in Segment Builder" border={true} />


## Verify Capture

To confirm that locale and language are captured for a user, navigate to that user's [_User Profile_ ](doc:user-profiles)page. The `CT Locale` and `CT Language` properties appear under System Properties if the SDK has reported them. If these properties are absent, verify that the device is running a supported SDK version and that the app has been launched at least once after the SDK is initialized.

## Use Locale and Language in Campaigns

You can target users by locale or language preferences when creating campaigns. Targeting  `CT Locale` lets you reach users in a specific region regardless of their language settings. Targeting  `CT Language` lets you reach users who share a language regardless of their region. Using both together lets you narrow targeting to a specific language within a specific region.

To use a locale or a language in a campaign:

1. Create a campaign.
2. In the What section, select Add Variant, then filter by User Property.
3. Select `ct_language` or `ct_locale` from the property list.
4. Define variants of the same message in different languages or for different regions.

This allows you to send messages in different languages within a single campaign and deliver localized content based on user preferences, without maintaining separate user attributes.

For example, users with `ct_language` set to `en` receive the message in English, and users with `ct_language` set to `fr` receive the same message in French.

<Callout icon="📘" theme="info">
  ### Multi-Device Behavior

  If a user uses multiple devices with different language or locale settings, CleverTap stores the value from the most recently active device. For example, if a user switches from a device set to `en_US` to a device set to `fr_FR` and opens the app, the profile updates to reflect `fr_FR`. This means the user profile always reflects the most recent locale and language information, and campaign targeting applies the updated value going forward.
</Callout>

## Use Locale and Language in Personalization

You can use these properties in personalization with Liquid Tags:

```
{{Profile.locale}}
{{Profile.language}}
```

This allows you to display different message content based on the user's language or region. For example, you can include a region-specific offer link or render a greeting in the user's preferred language within the same message template.

# System Events

System events are tracked automatically. CleverTap enables businesses to configure system events, allowing them to monitor and analyze user actions in their applications. However, some businesses may not have an immediate need for certain system events, resulting in potentially avoidable expenses. CleverTap allows businesses to configure those unused system events, providing a seamless process to address this issue.

## Configure System Events

To configure the tracking of system events:

1. Navigate to _Settings_ > _Schema_ > _Events_ from the CleverTap dashboard.
2. Select the event that you want to configure from the _System events_ tab.
3. Click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon and select _Enable/Disable_ from the list.


<Image src="https://files.readme.io/4454bcf-UTM_Tracking_Toggle_Off.gif" alt="Turn off Toggle to Disable Tracking UTM Visited" align="center" border={true} />


Currently, you can enable or disable tracking for the following events from the CleverTap dashboard:

<details>
  <summary>Push Impression</summary>

The Push Impression event is tracked when a push notification sent from CleverTap is delivered to a user’s device. After the toggle for Push Impressions is turned on, the CleverTap SDK starts recording an event whenever a push notification sent via CleverTap is delivered to the user’s device.

The _Push Impression_ event has its own event properties and the users can configure these non-required event properties to optimize the cost.

To do so:

1. Navigate to _Settings_ > _Schema_ > _Events_ from the CleverTap dashboard.
2. Select the _Push Impressions_ event from the _System events_ tab.
3. Click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon and select _Setup push impressions_ from the list.
4. Turn ON the **Mobile Push** toggle and click **Save**. The _Push impressions tracking enables_ message displays on the screen.


<Image src="https://files.readme.io/94f4dcb-Turn_Off_Push_Impression_Tracking.gif" alt="Disable Tracking Push Impressions Event" align="center" border={true} />


### Disable Event Property Tracking

The users can disable the tracking of some of the _Push Impression_ event properties from the CleverTap dashboard. However, there are a few Push Impression event properties for which you do not have the option to disable the tracking. These are listed as follows:

| Property         | Property Description                                    | Configurable |
| :--------------- | :------------------------------------------------------ | :----------- |
| `wzrk_push_amp`  | Push amplification flag                                 | No           |
| `wzrk_pn`        | The flag to check if the Push is from CleverTap or not. | No           |
| `CT Source`      | CleverTap Source                                        | No           |
| `wzrk_id`        | The ID of the campaign.                                 | No           |
| `wzrk_pid`       | Unique push notification ID                             | No           |
| `wzrk_pivot`     | Variant                                                 | No           |
| `wzrk_acct_id`   | CleverTap Account ID                                    | No           |
| `CT App Version` | CleverTap App Version                                   | No           |
| `wzrk_dt`        | Delivery type                                           | No           |
| `wzrk_acts`      | CTA button                                              | No           |
| `wzrk_pn_h`      | RenderMax health state                                  | No           |

To disable the tracking of Push Impression event properties:

1. From the _System events_ tab, click the _Properties_ hyperlink. The Push Impressions properties list opens.


<Image src="https://files.readme.io/1dd0fc5-View_Push_Impressions_Properties.png" alt="Push Impressions Properties List" align="center" border={true} />


2. Select the configurable property, click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon, and select _Disable Property_ from the list. The _Enable property tracking_ popup opens.


<Image src="https://files.readme.io/479d1ac-Disable_a_Push_Impression_Property.gif" alt="Disable Property Tracking" align="center" border={true} />


3. Click **Disable** to confirm your action. The _Property tracking successfully disabled_ message displays on the screen. The status of the event property changes to _Active_. Once disabled, if you want to enable the tracking later, you can do so by clicking the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon and selecting **Enable Property** from the list.

<Callout icon="📘" theme="info">
  ### Key Points to Remember

  The following are some of the points to consider when configuring the _Push Impressions_ event:

  - The event property tracking feature is not available for required properties.
  - The **Status** is always _Active_ for mandatory properties.
  - The tracking of configurable properties is enabled by default for new (new users of CleverTap dashboard) or returning users (existing users who turned off push impression feature) of Push Impression feature.
  - For existing users, the tracking of event properties remains as is, however, they have the additional capability to enable/disable tracking for the same.
</Callout>

</details>

<details>
  <summary>Web Session Started</summary>

This is a web entry event similar to the App launched event. This event refers to the event triggered when a user starts a session or engages with your website. This event will be recorded in two cases:

- When a user opens a webpage.
- When a user reloads the browser after 20 minutes of inactivity.

<Callout icon="📘" theme="info">
  ### Default Behavior

  This event is disabled by default for all customers and can be configured by the customers. When enabled, it captures the unique visitors to the website in a particular session.
</Callout>

</details>

<details>
  <summary>UTM Visited</summary>

The _UTM Visited_ event is tracked when a user clicks on a link from a marketing campaign that has a UTM parameter defined on it. This event is also tracked when a CleverTap-integrated attribution platform, such as AppsFlyer or Branch, sends this information to CleverTap. This event is recorded for your marketing campaigns from external sources, such as Google Ads or Facebook.

<Callout icon="📘" theme="info">
  ### Deault Behavior

  The UTM Visited tracking is ON for new customers by default. For existing customers, the tracking of UTM Visited remains as is. However, they have the capability to enable or disable the same.
</Callout>

</details>

<Callout icon="📘" theme="info">
  ### Configuring Other System Events

  For the remaining system events, you can only change the DRP.
</Callout>

# Conversion Event

The conversion event helps track conversion.

To set a conversion event:

1. Navigate to _Settings_ > _Schema_ > _Events_.
2. Click the **Conversion event** tab.

To track revenue, set the user conversion event and revenue property. This property must be a numeric value.


<Image src="https://files.readme.io/5ba54c0-set_conversion.png" alt="1155" align="center" border={true} />


# Qualifying Event

To set a qualifying event:

1. Navigate to _Settings_ > _Schema_ > _Events_.
2. Click the **Qualifying event** tab.

This event qualifies users as active if they have performed the event at least once in the defined time.

Currently, the [active %](https://docs.clevertap.com/docs/trends#section-active) tab uses the qualifying event on the _Trends_ page.


<Image src="https://files.readme.io/5d67342-set_qualifying.png" alt="1162" align="center" border={true} />


# Download Schema Data from Dashboard

You can download the data for all events and user profiles from the CleverTap dashboard or via an API.

## Event Data

To download event data from the CleverTap dashboard in CSV format:

1. Navigate to _Settings_ > _Schema_ > _Events_. You can download event data from the _System events_ tab or the _Custom event_ tab.
2. Click the **Download as CSV** button, then the _Download CSV file_ window displays.
3. Select to download _Events_ or _Events with properties_.
4. Click **Download**.

## User Profile data

To download all event data from the CleverTap dashboard in CSV format:

1. Navigate to _Settings_ > _Schema_ > _User Properties_.
2. Click the **Download as CSV** button.

## Download with API

To download event data or user profile data with API, refer to the following:

- Use the [Events Schema API](https://developer.clevertap.com/docs/get-schema#section-get-events-schema-api) to download event data.
- Use the [User Properties Schema API](https://developer.clevertap.com/docs/get-schema#section-get-user-properties-schema-api) to download user profile data.

# Considerations

There are some specific validations when creating events and properties. For more information, refer to [Platform Considerations](doc:platform-considerations).

# FAQs

#### Q. Can we get all past behavior data for an event after discarding it?

A. No, we cannot get all past behavior data for an event after discarding it.

#### Q. Does a discarded event appear under the user profile in the user's activity?

A. No, a discarded event does not appear under the user profile in the user's activity.

#### Q. For how many days can I get the data of discarded events?

A.  You will not get any event data after discarding an event. We recommend you export that event before you delete it.

#### Q: If we disable the UTM Visited event from the schema, can it still be ingested through third-party mediums such as attribution tools like AppsFlyer or Customer Data Platforms (CDPs) like Segment?

A: When the UTM Visited event is disabled from the schema, it is dropped at the processing layer, rendering it inaccessible for ingestion from any third-party medium.

<HTMLBlock>{`
<style>
  .rm-Guides .content-body, .rm-Guides #content-head .col-xs-9 {
      max-width: 100%;
      width: 1000px;
  }
  .markdown-body summary {
  font-size: 16px;
  font-weight: bold; 
  text-transform: camelcase;
}
  
details .rdmd-table {
   margin-bottom: 20px;
}
  details[open] summary { margin-bottom: 20px;
  }
</style>
`}</HTMLBlock>

<br />
