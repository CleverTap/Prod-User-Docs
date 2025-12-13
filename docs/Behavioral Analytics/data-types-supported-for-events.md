---
title: Data Types Supported for Events
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
@DOCS: SINCE THIS IS TOO SHORT OF A HACKATHON DOC, SUNIL WILL CONFIRM WHICH (DEV) DOC TO MOVE THIS TO.
[block:api-header]
{
  "title": "Overview"
}
[/block]
CleverTap only supports primitive JavA data types, including:
  * String
  * Integer
  * Float
  * Boolean
  * List
  * Mixed

If you are using a list or an array, this instance will be dropped as the properties where the data type is incorrect. Charged is a special event where the data can be passed in an array.