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
* AWS Pinpoint

# Integration Steps

To integrate an SMS provider, perform the following steps:

1. In the CleverTap dashboard, navigate to *Settings* > *Engage* > *Channels* > *SMS*.
2. Click **+ Add Provider**.

![1074](https://files.readme.io/6c72583-1_Add_Provider_dashbboard.png "1 Add Provider dashbboard.png")

3. Under *Provider*, select *Other (Generic)*.
4. Select GET or POST option depending on which HTTP protocol your SMS provider supports, then enter the HTTP API endpoint of the provider.
5. Under *Authentication*, select one of the following options:

* No Authentication.
* Basic Authentication: Enter the username and password.
* Auth 2.0: Enter client URL, client ID, secret key, and key-value pairs (optional).

![1372](https://files.readme.io/c6435fb-2_Under_Authentication.png "2 Under Authentication.png")

6. Select *Headers* to pass along any HTTP headers which will be added to the HTTP request sent to the API endpoint.
7. For a POST request under *Parameters*, select your request type in:

* Key-value pair: Enter your keys and values.
* JSON: Enter your entire JSON payload structure. If the service provider supports batching, you can enable the batching by specifying the key name and the number of records per batch. 

> 📘 Single Batch Limit
>
> A single batch can have a maximum of 1,000 records.

![1354](https://files.readme.io/23dd8e3-under_Parameters.png "under_Parameters.png")

# Set Up Your Message Payload

To determine the parameters your SMS provider supports, you can ask for a curl request from your SMS service provider or check the payload structure defined in the provider documentation. 

To set up your message payload, perform the following steps:

1. In the CleverTap dashboard, navigate to *Settings* > *Engage* > *Channels* > *SMS*.
2. Click on the **+ Add Provider** button.
3. Under *Provider*, select *Other (Generic)*.
4. If the provider specifies all information such as a phone number, a message body, or a template should be passed under *Headers*, then under *Headers*, enter key and value pairs.

![751](https://files.readme.io/67d5387-Screen_Shot_2018-08-30_at_4.14.49_PM.png "Screen Shot 2018-08-30 at 4.14.49 PM.png")

4. If the provider specifies all information such as a phone number, a message body, or a template should be passed under *Body*, then under *Parameters*, select the supported encoding:

* x-www-form-urlencoded: Within this format, all values are passed as key-value pairs which are used when creating campaigns.

![1454](https://files.readme.io/bd4a734-Screenshot_2021-05-12_at_4.26.41_PM.png "Screenshot 2021-05-12 at 4.26.41 PM.png")

* JSON: Within this format, the exact payload is defined in a JSON structure. This is used to define the payload structure for all outgoing requests of this particular provider.

![1302](https://files.readme.io/a8e7b8d-Screenshot_2021-05-12_at_4.35.40_PM.png "Screenshot 2021-05-12 at 4.35.40 PM.png")

## System Dynamic Replacements

You can use five dynamic replacements within the key-value pairs in the headers or parameters tabs:

* $$To: A mandatory replacement value used to signify the key where the phone number is added to the payload.
* $$Body: An optional replacement value used to signify the key where the body of the message is added to the payload. Every configuration needs to have $$Body or $$TemplateID key as a mandatory replacement.
* $$TemplateID: An optional replacement value used to signify the key where the TemplateID of the message is added to the payload. Every configuration needs to have $$TemplateID or $$Body key as a mandatory replacement. This variable is optional and only applicable for campaigns targeted to **Indian mobile numbers**. Refer to the [Regulation Impact](https://docs.clevertap.com/docs/regulation-impact#section-future-campaigns) guide to learn more.
* $$TemplateVariables: An optional replacement value used to signify the key where the template variables of the message are added to the payload. 
* $$CampaignID: An optional replacement value used to signify the key where the CleverTap campaign ID is added to the payload.

## Custom Dynamic Replacements

In addition to system dynamic replacements, any configuration can have a custom dynamic replacement which is available on the campaign creation flow as a mandatory input. 

The following is an example of a configuration to better understand the setup:

```json
{
  "hid": "$$hid", //Global Key-Value pair
  "tid": "$$TemplateID",
  "cid": "$$CampaignID",
  "type": "template",
  "msgs": [
    {
      "seq": 1,
      "to": "$$To",
      "uid": "$$uid", //Message Body Key-Value pair
      "variables": "$$TemplateVariables",
      "enc": "utf8"
    }
  ]
}
```

The entire payload has two parts:

1. Message Body Key-Value Pairs: The keys are `seq`, `to`, `uid`, `variables`, and `enc`.
2. Global Key-Value Pairs: The keys are `hid`, `tid`, `cid`, and `type`.

In this configuration, a single msg record will be set up in the key `msgs` and all the message body key-value pairs are used with a user-level personalization. On the other hand, $$hid is a custom dynamic replacement that cannot be personalized on a user level but the value can be set for each campaign.

Here is another example without batching:

```json
{
  "hid": "$$hid",//Message Body Key-Value pair
  "tid": "$$TemplateID",
  "cid": "$$CampaignID",
  "type": "template",
  "seq": 1,
  "to": "$$To",
  "uid": "$$uid",//Message Body Key-Value pair
  "variables": "$$TemplateVariables",
  "enc": "utf8"
}
```

In the example above, there is no bifurcation of the payload. Global and message key-value pairs are on the same level and therefore, no batching is possible as each record will ping the provider individually. All dynamic replacements would be available for user-level personalization.
