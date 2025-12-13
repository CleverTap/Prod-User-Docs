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
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49681f2-Error_stream_main.png",
        "Error_stream_main.png",
        1365,
        696,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
Click any of the error to view the error detail. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fdf15f8-Error_stream_detail.png",
        "Error_stream_detail.png",
        1365,
        703,
        "#f9f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
Click the + sign next to an error to see the error trend. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/522bde6-Error_stream_trend.png",
        "Error_stream_trend.png",
        1339,
        1144,
        "#f8f8fa"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
## List of errors

[block:parameters]
{
  "data": {
    "0-0": "Mandatory event property not passed; violation handler dropped event",
    "h-0": "Error",
    "1-0": "Undefined event found and dropped",
    "2-0": "Undefined event found and accepted",
    "3-0": "Undefined event property found and event dropped",
    "4-0": "Undefined event property found and event property dropped",
    "5-0": "Undefined event property found and event property accepted",
    "6-0": "Mismatched event property data type found and event dropped",
    "8-0": "Mismatched event property data type found and event accepted",
    "9-0": "Maximum event properties for event exceeded",
    "10-0": "Maximum event limit exceeded due to undefined events",
    "11-0": "Event property defined but not used in the last three months",
    "12-0": "Unaccepted characters found in event property values",
    "13-0": "Unaccepted characters found in event property keys for undefined events",
    "14-0": "No event found in last three months",
    "15-0": "Undefined user property found and dropped",
    "16-0": "Undefined user property found and accepted",
    "17-0": "Mismatched and user property data type found and dropped",
    "18-0": "Mismatched user property data type found and accepted",
    "19-0": "Unaccepted characters found for user property values",
    "20-0": "Unaccepted characters in user profile property key",
    "21-0": "Maximum characters exceeded for user property value",
    "h-1": "Description",
    "h-2": "Possible Action",
    "0-1": "Event property was declared as mandatory for the said event in the schema. Incoming data did not have the mandatory event property. Hence event was dropped",
    "0-2": "1. Fix the incoming data from SDK/API to ensure the said event property is always passed\n2. Remove the validation for the said event from the schema",
    "1-1": "When schema was published, 'Undefined Data Handling' was set to drop event. When an event came in for the account which was not defined in the schema, it was dropped",
    "1-2": "1. If the event is valid, define the said event in the schema along with its properties. Data will start flowing in",
    "2-1": "When schema was published, 'Undefined Data Handling' was set to allow event. When an event came in for the account which was not defined in the schema, it was accepted leading to polluted data",
    "2-2": "1. If the event is not valid, discard the said event in the schema\n2. Set data handling to drop undefined events to ensure data sanity",
    "3-1": "When schema was published, 'Undefined Data Handling' was set to drop event when an undefined event property is identified. When an event property came in for the account which was not defined in the schema, the entire event was dropped",
    "3-2": "1. If the event property is valid, define the said property in the schema. Event along with the property will start flowing in",
    "4-1": "When schema was published, 'Undefined Data Handling' was set to drop the said event property when an undefined event property is identified. When an event property came in for the account which was not defined in the schema, the event property was dropped",
    "4-2": "1. If the event property is valid, define the said property in the schema. Event property will start flowing in",
    "5-1": "When schema was published, 'Undefined Data Handling' was set to accept the said event property when an undefined event property is identified. When an event property came in for the account which was not defined in the schema, the event property was accepted, leading to polluted data",
    "5-2": "1. If the event property is not valid, discard the said event property in the schema\n2. Set data handling to drop undefined event properties to ensure data sanity",
    "6-1": "In the schema, datatype for event property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to drop the event",
    "6-2": "1. Update the datatype fallback definition to allow the event\n2. Update the data coming from API/SDK to the correct data type",
    "8-1": "In the schema, datatype for event property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to allow the event",
    "8-2": "1. Update the data coming from API/SDK to the correct data type",
    "9-1": "Event property limit of 256 for the event exceeded. Properties outside the limit dropped",
    "9-2": "1. Remove unwanted properties from the event",
    "10-1": "Event limit for the project exceeded. Events outside the limit dropped",
    "10-2": "1. Remove unwanted events from the project",
    "11-1": "No instance of a defined event property in the schema found in a 90 day period",
    "11-2": "1. Validate incoming data from SDK/API to ensure event is configured correctly",
    "12-1": "Illegal characters found in the event property value",
    "12-2": "1. Remove the illegal characters from API/SDK configuration",
    "13-1": "Illegal characters found in the event property key",
    "13-2": "1. Remove the illegal characters from API/SDK configuration",
    "14-1": "No instance of a defined event in the schema found in a 90 day period",
    "14-2": "1. Validate incoming data from SDK/API to ensure event is configured correctly",
    "15-1": "When schema was published, 'Undefined Data Handling' was set to drop user property when an undefined. When a user property came in for the account which was not defined in the schema, the same was dropped",
    "15-2": "1. If the user property is not valid, discard the said event in the schema\n2. Set data handling to drop undefined user properties to ensure data sanity",
    "16-1": "When schema was published, 'Undefined Data Handling' was set to allow user property when an undefined. When a user property came in for the account which was not defined in the schema, the same was accepted",
    "16-2": "1. If the user property is not valid, discard the said user property in the schema\n2. Set data handling to drop undefined user properties to ensure data sanity",
    "7-0": "Mismatched event property data type found and event property dropped",
    "7-1": "In the schema, datatype for event property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to drop the event property",
    "7-2": "1. Update the datatype fallback definition to allow the event property\n2. Update the data coming from API/SDK to the correct data type",
    "17-1": "In the schema, datatype for user property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to drop the user property",
    "17-2": "1. Update the datatype fallback definition to allow the user property\n2. Update the data coming from API/SDK to the correct data type",
    "18-1": "In the schema, datatype for user property was defined. The incoming data did not follow the defined datatype. Datatype fallback definition was to accept the user property",
    "18-2": "1. Update the data coming from API/SDK to the correct data type",
    "19-1": "Illegal characters found in the user property value",
    "19-2": "1. Remove the illegal characters from API/SDK configuration",
    "20-1": "Illegal characters found in the user property key",
    "20-2": "1. Remove the illegal characters from API/SDK configuration",
    "21-1": "User property limit for the project exceeded. User Properties outside the limit dropped",
    "21-2": "1. Remove unwanted user properties from the project"
  },
  "cols": 3,
  "rows": 22
}
[/block]