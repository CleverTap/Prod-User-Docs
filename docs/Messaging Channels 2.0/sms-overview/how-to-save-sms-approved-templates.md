---
title: How to Save SMS Approved Templates
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
[block:api-header]
{
  "title": "Overview"
}
[/block]

The Template ID that you have to use in the campaign, has to be entered in the message key-value pair of the WHAT section of the campaign. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a24f264-Template_ID.png",
        "Template ID.png",
        496,
        184,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]
The value that you will enter here is the one that is being accepted by your service provider for passing the Template ID. The Template ID parameter that you put in the endpoint URL.
Check with the service provider which key they accept for Template ID and accordingly add that key and then the Template ID value in the message section.