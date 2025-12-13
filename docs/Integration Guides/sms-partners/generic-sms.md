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
CleverTap supports any SMS provider via an HTTP integration. The SMS provider should support receiving messages via the HTTP protocol.

We have tested the integration steps below with these providers:
  * MSG91
  * TextLocal
  * Plivo
  * Nimbus
  * BulkSMS
  * SMSINDIAHUB
  * Exotel

# Integration Steps

  * In the CleverTap Dashboard, navigate to Settings and click on Integrate SMS.
  * Select Generic.
  * Select either GET or POST option depending which HTTP protocol your SMS provider supports.
  * Enter the HTTP API endpoint of the provider.
  * Authentication – If your provider supports the Basic Authentication scheme, then select Basic Authentication and enter the Username and Password.
  * Headers – You can pass along any HTTP headers, they’ll be added to the HTTP request sent to the API endpoint.
  * Parameters – You can send your POST request either in the x-www-form-urlencoded format, or in the raw format.

# Set Up Your Message Payload

To determine the parameters your SMS provider supports, you can ask for a curl request from your SMS service provider. On the basis on parameters passed in the curl request, add the parameters in CleverTap Dashboard settings > SMS > Select Generic > Headers as key value pairs.


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
Use the "$$To" and "$$Body" parameters either in the API Endpoint, Headers or the Parameter values to denote the user’s mobile number and SMS message respectively. They’ll be replaced with actual values when the message is delivered to the endpoint.

In case the parameters passed in the headers don't work for GET type request, you can pass the parameters in the endpoint. 
For example: http://<yoursmsserviceprovider.com>/rest?method=sms&mobile_no=$$To&content=$$Body&access_token=xyz&sender=EXPL&userid=<userid>&password=<password>
[block:callout]
{
  "type": "warning",
  "body": "Both $$To and the $$Body parameters are case-sensitive."
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
  "body": "* The parameters required might vary from one service providers to others."
}
[/block]