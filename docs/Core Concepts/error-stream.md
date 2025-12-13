---
title: Error Stream
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
You can view all the errors from the Error stream page. To view errors, click Errors from the main menu. The Errors stream page appears. Select the time period for the errors from the "number of days" list. 

<Image title="Error_stream_main.png" alt={1365} className="border" border={true} src="https://files.readme.io/49681f2-Error_stream_main.png" />

Click any of the error to view the error detail. 

<Image title="Error_stream_detail.png" alt={1365} className="border" border={true} src="https://files.readme.io/fdf15f8-Error_stream_detail.png" />

Click the + sign next to an error to see the error trend. 

<Image title="Error_stream_trend.png" alt={1339} className="border" width="100%" border={true} src="https://files.readme.io/522bde6-Error_stream_trend.png" />

## List of errors

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Error
      </th>

      <th>
        Description
      </th>

      <th>
        Possible Action
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Mandatory event property not passed; violation handler dropped event
      </td>

      <td>
        Event property was declared as mandatory for the said event in the schema. Incoming data did not have the mandatory event property. Hence event was dropped
      </td>

      <td>
        1. Fix the incoming data from SDK/API to ensure the said event property is always passed
        2. Remove the validation for the said event from the schema
      </td>
    </tr>

    <tr>
      <td>
        Undefined event found and dropped
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to drop event. When an event came in for the account which was not defined in the schema, it was dropped
      </td>

      <td>
        1. If the event is valid, define the said event in the schema along with its properties. Data will start flowing in
      </td>
    </tr>

    <tr>
      <td>
        Undefined event found and accepted
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to allow event. When an event came in for the account which was not defined in the schema, it was accepted leading to polluted data
      </td>

      <td>
        1. If the event is not valid, discard the said event in the schema
        2. Set data handling to drop undefined events to ensure data sanity
      </td>
    </tr>

    <tr>
      <td>
        Undefined event property found and event dropped
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to drop event when an undefined event property is identified. When an event property came in for the account which was not defined in the schema, the entire event was dropped
      </td>

      <td>
        1. If the event property is valid, define the said property in the schema. Event along with the property will start flowing in
      </td>
    </tr>

    <tr>
      <td>
        Undefined event property found and event property dropped
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to drop the said event property when an undefined event property is identified. When an event property came in for the account which was not defined in the schema, the event property was dropped
      </td>

      <td>
        1. If the event property is valid, define the said property in the schema. Event property will start flowing in
      </td>
    </tr>

    <tr>
      <td>
        Undefined event property found and event property accepted
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to accept the said event property when an undefined event property is identified. When an event property came in for the account which was not defined in the schema, the event property was accepted, leading to polluted data
      </td>

      <td>
        1. If the event property is not valid, discard the said event property in the schema
        2. Set data handling to drop undefined event properties to ensure data sanity
      </td>
    </tr>

    <tr>
      <td>
        Mismatched event property data type found and event dropped
      </td>

      <td>
        In the schema, datatype for event property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to drop the event
      </td>

      <td>
        1. Update the datatype fallback definition to allow the event
        2. Update the data coming from API/SDK to the correct data type
      </td>
    </tr>

    <tr>
      <td>
        Mismatched event property data type found and event property dropped
      </td>

      <td>
        In the schema, datatype for event property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to drop the event property
      </td>

      <td>
        1. Update the datatype fallback definition to allow the event property
        2. Update the data coming from API/SDK to the correct data type
      </td>
    </tr>

    <tr>
      <td>
        Mismatched event property data type found and event accepted
      </td>

      <td>
        In the schema, datatype for event property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to allow the event
      </td>

      <td>
        1. Update the data coming from API/SDK to the correct data type
      </td>
    </tr>

    <tr>
      <td>
        Maximum event properties for event exceeded
      </td>

      <td>
        Event property limit of 256 for the event exceeded. Properties outside the limit dropped
      </td>

      <td>
        1. Remove unwanted properties from the event
      </td>
    </tr>

    <tr>
      <td>
        Maximum event limit exceeded due to undefined events
      </td>

      <td>
        Event limit for the project exceeded. Events outside the limit dropped
      </td>

      <td>
        1. Remove unwanted events from the project
      </td>
    </tr>

    <tr>
      <td>
        Event property defined but not used in the last three months
      </td>

      <td>
        No instance of a defined event property in the schema found in a 90 day period
      </td>

      <td>
        1. Validate incoming data from SDK/API to ensure event is configured correctly
      </td>
    </tr>

    <tr>
      <td>
        Unaccepted characters found in event property values
      </td>

      <td>
        Illegal characters found in the event property value
      </td>

      <td>
        1. Remove the illegal characters from API/SDK configuration
      </td>
    </tr>

    <tr>
      <td>
        Unaccepted characters found in event property keys for undefined events
      </td>

      <td>
        Illegal characters found in the event property key
      </td>

      <td>
        1. Remove the illegal characters from API/SDK configuration
      </td>
    </tr>

    <tr>
      <td>
        No event found in last three months
      </td>

      <td>
        No instance of a defined event in the schema found in a 90 day period
      </td>

      <td>
        1. Validate incoming data from SDK/API to ensure event is configured correctly
      </td>
    </tr>

    <tr>
      <td>
        Undefined user property found and dropped
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to drop user property when an undefined. When a user property came in for the account which was not defined in the schema, the same was dropped
      </td>

      <td>
        1. If the user property is not valid, discard the said event in the schema
        2. Set data handling to drop undefined user properties to ensure data sanity
      </td>
    </tr>

    <tr>
      <td>
        Undefined user property found and accepted
      </td>

      <td>
        When schema was published, 'Undefined Data Handling' was set to allow user property when an undefined. When a user property came in for the account which was not defined in the schema, the same was accepted
      </td>

      <td>
        1. If the user property is not valid, discard the said user property in the schema
        2. Set data handling to drop undefined user properties to ensure data sanity
      </td>
    </tr>

    <tr>
      <td>
        Mismatched and user property data type found and dropped
      </td>

      <td>
        In the schema, datatype for user property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to drop the user property
      </td>

      <td>
        1. Update the datatype fallback definition to allow the user property
        2. Update the data coming from API/SDK to the correct data type
      </td>
    </tr>

    <tr>
      <td>
        Mismatched user property data type found and accepted
      </td>

      <td>
        In the schema, datatype for user property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to accept the user property
      </td>

      <td>
        1. Update the data coming from API/SDK to the correct data type
      </td>
    </tr>

    <tr>
      <td>
        Unaccepted characters found for user property values
      </td>

      <td>
        Illegal characters found in the user property value
      </td>

      <td>
        1. Remove the illegal characters from API/SDK configuration
      </td>
    </tr>

    <tr>
      <td>
        Unaccepted characters in user profile property key
      </td>

      <td>
        Illegal characters found in the user property key
      </td>

      <td>
        1. Remove the illegal characters from API/SDK configuration
      </td>
    </tr>

    <tr>
      <td>
        Maximum characters exceeded for user property value
      </td>

      <td>
        User property limit for the project exceeded. User Properties outside the limit dropped
      </td>

      <td>
        1. Remove unwanted user properties from the project
      </td>
    </tr>
  </tbody>
</Table>
