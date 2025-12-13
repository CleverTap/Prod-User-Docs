---
title: Generic SMS_WIP
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
## Overview

CleverTap supports any SMS provider via an HTTP integration. The SMS provider should support receiving messages via the HTTP protocol.

We have tested the integration steps with the following providers:

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
2. Click **+ Add Provider**.

![1074](https://files.readme.io/6c72583-1_Add_Provider_dashbboard.png "1 Add Provider dashbboard.png")

3. Under *Provider*, select *Other (Generic)*.
4. Select GET or POST option depending on which HTTP protocol your SMS provider supports, then enter the HTTP API endpoint of the provider.
5. Under *Authentication*, select one of the following options:

* No Authentication
* Basic Authentication: Enter the username and password.
* Auth 2.0: Enter client URL, client ID, and secret key.

**\_\_** DK TO PROVIDE NEW CLEAN SCREENSHOT BELOW **\_\_**

![450](https://files.readme.io/ff457fe-Auth_2.0.png "Auth 2.0.png")

6. Select *Headers* to pass along any HTTP headers which will be added to the HTTP request sent to the API endpoint.
7. For a POST request under *Parameters*, select your request type in:

* Key-value pair: Enter your keys and values.
* JSON: Enter your entire JSON payload structure. If batching is needed, enter a parameter name and number of times for a single payload. 

> 📘 Payload Limit
>
> A single payload limit is 1,000.

**\_\_** DK TO PROVIDE NEW CLEAN SCREENSHOT BELOW **\_\_**

![1732](https://files.readme.io/a4c1f0b-Parameters_batch.png "Parameters batch.png")

# Set Up Your Message Payload

To determine the parameters your SMS provider supports, you can ask for a curl request from your SMS service provider. Perform the following steps:

1. In the CleverTap dashboard, navigate to *Settings* > *Engage* > *Channels* > *SMS*.
2. Click on the **+ Add Provider** button.
3. Under *Provider*, select *Other (Generic)*.
4. Under *Headers*, enter key and value pairs.

![751](https://files.readme.io/67d5387-Screen_Shot_2018-08-30_at_4.14.49_PM.png "Screen Shot 2018-08-30 at 4.14.49 PM.png")

Use the "$$To" and "$$Body" parameters in the API endpoint, headers, or the parameter values to denote the user’s mobile number and SMS message respectively. These values will be replaced with actual values when the message is delivered to the endpoint.


In case the parameters passed in the headers do not work for the GET type request, you can pass the parameters in the endpoint. 

For example: http://&lt;yoursmsserviceprovider.com>/rest?method=sms\&mobile\_no=$$To\&content=$$Body\&access\_token=xyz\&sender=EXPL\&userid=&lt;userid>&\password=&lt;password>

> 🚧 Casing
>
> Both $$To and the $$Body parameters are case-sensitive.

For example, SMS service provider A requires the following parameters:

* method
* access\_token
* mobile\_no
* content
* sender

![735](https://files.readme.io/d005bd0-Screen_Shot_2018-08-30_at_4.40.12_PM.png "Screen Shot 2018-08-30 at 4.40.12 PM.png")

> 📘 Required Parameters
>
> The parameters required might vary from one service provider to another.