---
title: Generic SMS
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
  "title": "Overview"
}
[/block]
CleverTap supports any SMS provider via an HTTP integration. The SMS provider should support receiving messages via the HTTP protocol.

We have tested the integration steps below with these providers:
  * BulkSMS
  * Exotel
  * MSG91
  * Nimbus
  * Plivo
  * SMSINDIAHUB
  * TextLocal

# Integration Steps

To integrate an SMS provider, perform the following steps:
1. In the CleverTap dashboard, navigate to *Settings* > *Engage* > *Channels* > *SMS*.
2. Click on the **+ Add Provider** button.
3. Under *Provider*, select *Other (Generic)*.
4. Select GET or POST option depending on which HTTP protocol your SMS provider supports, then enter the HTTP API endpoint of the provider.
5. Under *Authentication*, if your provider supports the basic authentication scheme, then select *Basic Authentication* and enter the username and password.
6. Under *Headers*, you can pass along any HTTP headers which will be added to the HTTP request sent to the API endpoint.
7. Under *Parameters*, select your POST request in the x-www-form-urlencoded format or in a raw format.

# Set Up Your Message Payload

To determine the parameters your SMS provider supports, you can ask for a curl request from your SMS service provider. Perform the following steps:
1. In the CleverTap dashboard, navigate to *Settings* > *Engage* > *Channels* > *SMS*.
2. Click on the **+ Add Provider** button.
3. Under *Provider*, select *Other (Generic)*.
4. Under *Headers*, enter key and value pairs.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/67d5387-Screen_Shot_2018-08-30_at_4.14.49_PM.png",
        "Screen Shot 2018-08-30 at 4.14.49 PM.png",
        751,
        559,
        "#fbfcfc"
      ]
    }
  ]
}
[/block]
Use the "$$To" and "$$Body" parameters in the API endpoint, headers, or the parameter values to denote the user’s mobile number and SMS message respectively. These values will be replaced with actual values when the message is delivered to the endpoint.

In case the parameters passed in the headers do not work for the GET type request, you can pass the parameters in the endpoint. 

For example: http://<yoursmsserviceprovider.com>/rest?method=sms&mobile_no=$$To&content=$$Body&access_token=xyz&sender=EXPL&userid=<userid>&password=<password>
[block:callout]
{
  "type": "warning",
  "body": "Both $$To and the $$Body parameters are case-sensitive.",
  "title": "Casing"
}
[/block]
For example, SMS service provider A requires the following parameters:
* method
* access_token
* mobile_no
* content
* sender
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d005bd0-Screen_Shot_2018-08-30_at_4.40.12_PM.png",
        "Screen Shot 2018-08-30 at 4.40.12 PM.png",
        735,
        671,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The parameters required might vary from one service provider to another.",
  "title": "Required Parameters"
}
[/block]