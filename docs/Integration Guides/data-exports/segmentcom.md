---
title: Segment
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
[block:api-header]
{
  "title": "Introduction"
}
[/block]
Segment is a Customer Data Infrastructure (CDI) service provider, that provides a service that simplifies collecting and using data from the users of your digital properties (websites, apps, etc). With Segment, you can collect, transform, send, and archive your first-party customer data.

CleverTap has built an integration with Segment where we provide
1. Integrated SDK 
2. API integration
3. Export to Segment

[block:api-header]
{
  "title": "API integration"
}
[/block]
Passing your Segment data into CleverTap can be achieved by the API integration.
Details about this integration are provided [here](https://segment.com/docs/connections/destinations/catalog/clevertap/#identify) 
[block:callout]
{
  "type": "warning",
  "title": "Transformation of User and Event Properties when using Segment HTTP API",
  "body": "Segment transforms user property and event property names when passing data to partners like CleverTap in the following scenario.\n1. Send data to Segment from your servers using the [Segments HTTP API](https://segment.com/docs/connections/sources/catalog/libraries/server/http-api/), if this data is.\n2. Send data to CleverTap using the [Server Side CleverTap destination](https://segment.com/docs/connections/destinations/catalog/clevertap/#server-side)\n3. In this case, all event and user property names will be converted from '*sentence case*' to '*snake_case*'\nExample : \nData passed from sever -> Segment\n - \"Industry Of Traits\":\" Hello World\" \nData passed from Segment -> CleverTap\n - \"industry_of_traits\": \"Hello World\"\n\nIf the same data is being passed from multiple destinations to CleverTap, this will lead to the creation of 2 keys for every event and user property. We recommend using CleverTap's own API's to ensure data integrity.\nMore information on the CleverTap API's  [here](https://developer.clevertap.com/docs/api-overview)"
}
[/block]

[block:api-header]
{
  "title": "Export to Segment"
}
[/block]
CleverTap also provides a way in which you can export your data into your Segment account
Below are the steps to achieve it

## 1. Connect your Segment Account
To be able to send data from CleverTap into Segment, you will need to provide the credentials of your Segment account. This can be done by going into Settings -> Partner Data Exports -> Segment
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5ea9f35-Screenshot_2020-01-13_at_8.06.36_PM.png",
        "Screenshot 2020-01-13 at 8.06.36 PM.png",
        2428,
        920,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
Enter the Segment write key in the field provided and save the credentials


## 2. Initiate export
You can initiate an export from CleverTap into Segment by going into Campaigns -> Create Campaign -> Partner Channels -> Segment 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc567cd-Screenshot_2020-01-13_at_8.08.13_PM.png",
        "Screenshot 2020-01-13 at 8.08.13 PM.png",
        2264,
        1492,
        "#f8f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
You can create either a Past Behavior Segment export or an Action export.

You can use all the capabilities of the campaign like scheduling it for later, recurring, etc. to leverage the power of sending you CleverTap data into Segment