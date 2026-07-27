---
title: Generic WhatsApp
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

CleverTap supports any WhatsApp provider via integration. CleverTap has recently made its WhatsApp API and standard callback formats accessible to WhatsApp service providers globally. Now, BSPs and customers are no longer required to rely on CleverTap to build the native WhatsApp integration. Instead, they can utilize these APIs to build the integration themselves independently.

<Callout icon="📘" theme="info">
  ### For CleverTap Customers

  This feature is helpful to customers in the following ways:

  - Customers can build middleware between CleverTap and BSP and create their own endpoint. They can start using WhatsApp functionality in CleverTap with the BSP of their choice.
  - Customers can request their BSPs to build the CleverTap integration. This will allow customers to use the provider with CleverTap without any development.
</Callout>

<Callout icon="📘" theme="info">
  ### For WhatsApp BSPs

  Providers who wish to pursue the partnership must follow the integration steps outlined in this document and send an email to [integrations@clevertap.com](mailto:integrations@clevertap.com) or [partner-integrations@clevertap.com](mailto:partner-integrations@clevertap.com) to include their names in the supported provider's list.
</Callout>

## Supported Business Service Providers

The following Business Service Providers have built ready-to-use WhatsApp integration with CleverTap using CleverTap's generic integration.

- [Exotel](https://docs.clevertap.com/docs/exotel-whatsapp)
- [Haptik](https://docs.clevertap.com/docs/haptik)
- [Kaleyra](https://docs.clevertap.com/docs/kaleyra)

You can use this generic API documentation for other providers to establish an integration between CleverTap and your business service provider. Alternatively, you can ask your provider to create a ready-to-use integration with CleverTap based on this documentation.

## Partner Acceptance Criteria

Any WhatsApp partner can integrate with our open APIs. However, to become a supported partner with CleverTap, they must share the following with CleverTap:

- Production API endpoint for sending Template and Freeform notifications via a single endpoint.
- Production API credentials for two test accounts so the CleverTap team can test the integration.
- Providers must provide dashboard access so the CleverTap team can create or share approved templates to test the campaign flow.
- Providers must add CleverTap's callback URL to the test accounts. This helps CleverTap check whether the callbacks are received in the correct format.
- Providers are required to publish a CleverTap integration guide in their user documentation. This will enable CleverTap to cross-reference the integration guide from our documents.
- Partners must provide the contact details of their dedicated support and product team so that CleverTap can contact them in case of any issues.
- Providers must support a minimum of 1500 concurrent API requests for each customer using the integration.
- Partners must test integration with a few customers at scale.
- Partners are responsible for maintaining the integration and proactively resolving any issues.

# Test Partner Integration

Partners must test their integration in the CleverTap sandbox environment to validate message delivery, callbacks, and two-way communication. The following steps outline the required configuration and testing flow.

- Any partner can request access to the CleverTap sandbox account by writing to our partnership teams.
- Partners must develop the middleware connecting CleverTap and their platform. This should enable partners to receive message payloads (both freeform and template messages) from CleverTap and send the Delivery Receipts (DLRs) and Incoming Message Opt-Out (IMO)Callback per the payload structure published by CleverTap.
- Partners must save their messaging endpoints in the CleverTap sandbox account and configure CleverTap DLR and incoming message [callback URLs](https://docs.clevertap.com/docs/generic-whatsapp#2-set-up-clevertap-callbacks-with-provider) at their end. This requires that partners accept our endpoint [validation payload](https://docs.clevertap.com/docs/generic-whatsapp#validation-payload-1) and return a \[200 OK] success API response.
- Partners must [save the template](https://docs.clevertap.com/docs/haptik#adding-message-template) and send a test notification to ensure template messages are delivered to the end user.
- Once the messaging endpoints and templates have been saved and tested successfully, the partner can [create a WhatsApp campaign](https://docs.clevertap.com/docs/create-message-whatsapp).  The campaigns must target a large user base to scale-test the integration.
- Once the Campaign has been published and completed successfully, check the [WhatsApp campaign stats](https://docs.clevertap.com/docs/whatsapp-stats) and ensure the following:
  - Sent, Delivered, and Viewed counts are captured successfully and match your platform count.
  - The campaign error count is per expectation, and errors are categorized correctly.
- Test campaigns for different combinations of templates, such as media headers, footers, CTA, quick replies, and so on. This test is required to ensure that all templates are working as expected.
- Once the campaign has been tested successfully, go to [conversations](https://docs.clevertap.com/docs/conversations) and check whether incoming responses are being shown correctly for all the users who are replying.
- Respond to users from [agent chat](https://docs.clevertap.com/docs/conversations#role-based-access-agent-role) with different combinations ( text, media, location, documents, and so on) and check whether the messages are being delivered to end users correctly.
- Similarly, to the previous step, send different types of messages from end-user devices on WhatsApp and check whether all messages are being captured and shown in CleverTap conversations.

# Troubleshooting and FAQs for Generic Integration

These are some of the frequent issues that partners usually face when testing the integration.

## Q. Provider setting is not being saved in the CleverTap dashboard

Whenever a provider setting is saved in the CleverTap dashboard, we send out a [dummy messaging payload](https://docs.clevertap.com/docs/generic-whatsapp#validation-payload-1) to verify that your endpoint is up and returning a success response. If we do not receive the expected success response within one second, we display an error showing the API request and response received from your endpoint.

![](https://files.readme.io/3cda454-image.png) Failed API response

Partners can use the request shown in the above pop-up in Postman to debug the issue further.

## Q. Why am I unable to save the templates in the CleverTap dashboard?

CleverTap validates the Template that is saved in the dashboard by trying to deliver the Template message to a dummy number. This is required to ensure that customers don't save the incorrect templates and run into issues later when creating an actual campaign. To validate the Templates, we send the payload according to the template saved to the message endpoint which is saved in provider settings. If we receive the success response from the partner's endpoint within a second, we save the templates else, we display an error showing the request body and the API response.


<Image src="https://files.readme.io/29696e4-image.png" align="center" border={true} />


Partners can use the request body in Postman to debug the issue in detail at their end.

## Q. Why is the Template Message not being delivered to the end user ?

CleverTap is only responsible for sending the messaging payloads to the partners. Final delivery is owned by partners. Check the messaging payload received at the partner's end & ask them to resolve the issue. Having mentioned this, there could be many issues for messaging not delivering to end users, such as Template mismatch, Template deleted, or paused by META, and so on. To eliminate this issue as a possible cause, try different templates.<br />If none of the templates are being delivered, then this might happen because of integration issues. Partners can get the template payload by[ testing the templates](https://docs.clevertap.com/docs/haptik#testing-a-message-template) and comparing the payload to find the mismatch and resolve the issue.

## Q. Getting lots of generic miscellaneous errors in the campaign

Generic miscellaneous errors in the campaign come primarily for three reasons.

- We received the error code **2004** in response to the messaging API request.
- We received the error code **1009** in the status callback.
- Messaging API requests timed out because we didn't receive the API success response within the defined timeout limits(one second). This usually happens when Partner's API endpoint cannot support the concurrency limit at which CleverTap sends the messaging requests.

## Q. Why is the incoming response not recorded?

Two issues can cause this:

- The phone number used to send the WhatsApp message has never been targeted via CleverTap's WhatsApp campaigns. Create a sample campaign for the number that sends incoming messages.
- Incoming message callbacks are not coming in expected callback formats. Test with our [sample payload](https://docs.clevertap.com/docs/generic-whatsapp#api-payload-for-template-message).

## Q. Why is the WhatsApp campaign not live?

Check that the account is not dormant. A dormant account is an account that does not receive any data for more than 15 days. [Upload a sample event](https://developer.clevertap.com/docs/upload-events-api#overview) to resume using the account.

CleverTap marks an account as dormant if the account does not receive any data in 15 days.  Campaigns will not go live in the dormant account because there is no data to target. To activate the account, partners must [Upload a sample event](https://developer.clevertap.com/docs/upload-events-api#overview).

## Q. Why don't I have access to WhatsApp campaigns & conversations?

Enable the WhatsApp Connect Add-on and contact us at [partner-integrations@clevertap.com](mailto:partner-integrations@clevertap.com).

## Q. Why don't I have access to campaigns creation?

Before creating a campaign to target users, you must have a few users already added to your CleverTap project. If there are no users added to your project, you will see the following screen when you try to access the campaigns:

![](https://files.readme.io/602a7cf-image.png)  Campaigns First Time Screen

There are multiple ways to add users to a CleverTap project.

1. **Via CSV upload**: CSV uploads are easy way to add test users in a CleverTap Project. The following are the conditions for updating the flags:

   1. The objectId or identity must be the first column in the uploaded CSV file.
   2. The Phone column is mandatory, and phone numbers must have the country code. For example, +14155551234.

      Following is a table that displays the CSV columns:

      | Identity                                            | Email              | Phone        | MSG-whatsapp | MSG-sms |
      | :-------------------------------------------------- | :----------------- | :----------- | :----------- | :------ |
      | [john.doe@johndoe.com](mailto:john.doe@johndoe.com) |                    | +14155551234 | TRUE         | TRUE    |
      | 14155551235                                         |                    |              | TRUE         | TRUE    |
      | 14155551234                                         |                    | +14155551234 | TRUE         | TRUE    |
      | 234853412                                           | [mary@gmail.com]() | +14155551234 | TRUE         | TRUE    |
2. **Via User upload APIs** CleverTap offers APIs that enable you to send the values of subscription flags programmatically. This method is useful for automating the subscription management process and integrating CleverTap with your existing systems. For more information, see [upload user profiles](https://developer.clevertap.com/docs/upload-user-profiles-api). Following is an example of subscribing a user for WhatsApp messaging:

   **Base URLs**<br />Here is an example base URL for an account in the India region:<br />[https://in1.api.clevertap.com/1/upload](https://in1.api.clevertap.com/1/upload)

   | Region                  | API Endpoint           |
   | :---------------------- | :--------------------- |
   | India                   | in1.api.clevertap.com  |
   | Singapore               | sg1.api.clevertap.com  |
   | United States           | us1.api.clevertap.com  |
   | Indonesia               | aps3.api.clevertap.com |
   | Middle East (UAE)       | mec1.api.clevertap.com |
   | Europe (default region) | api.clevertap.com      |

   **Headers**

   The API headers are used while processing the API request. The following headers are required when you use CleverTap APIs:

   The X-CleverTap-Account-Id and X-CleverTap-Passcode authenticate the request.

   | Header                 | Description                                             | Type   | Example Value                         |
   | :--------------------- | :------------------------------------------------------ | :----- | :------------------------------------ |
   | X-CleverTap-Account-Id | Your CleverTap Account ID                               | string | "X-CleverTap-Account-Id: ACCOUNT\_ID" |
   | X-CleverTap-Passcode   | Your CleverTap Account Passcode.                        | string | "X-CleverTap-Passcode: PASSCODE"      |
   | Content-Type           | Request content-type is always set to application/json. | string | "Content-Type: application/json"      |

   Refer to the [API Authentication](https://developer.clevertap.com/docs/authentication) to obtain the header values. To understand the common queries and concerns related to CleverTap APIs, refer to [API FAQs](https://developer.clevertap.com/docs/api-faqs).

   **Sample JSON Payload**

Following is a sample JSON payload to upload a user profile:

```json JSON
{
  "d": [
    {
      "identity": "1189549",       
      "type": "profile",
      "profileData": {
        "Name": "Jack Montana",
        "Email": "jack@gmail.com",
        "Phone": "+14155551234",
        "Gender": "M",
        "MSG-sms": true,
        "MSG-email":true,//called when email must be subscribed  
        "MSG-whatsapp": true,
       "Customer Type": "internal test user"
      }
    }
  ]
}
```

To know more about user upload APIs, refer to [Upload User Profiles](https://developer.clevertap.com/docs/upload-user-profiles-api).

# Integration Steps for CleverTap Customers using Generic Integration

CleverTap Customers must get endpoint and authentication details from their WhatsApp providers before starting the integrations.

<Callout icon="📘" theme="info">
  ### Note

  1. BSPs might have a dedicated endpoint (different from their standard endpoint) for CleverTap integration. Given this, you must get the API details for CleverTap integration from your provider.
  2. Please note that your WhatsApp providers are responsible for final message delivery and sending DLR and IMOs back to Clevertap. In case of any issue with these, You will have to ask your providers to resolve these issues.
</Callout>

This process involves the following steps:

1. [Set Up WhatsApp Provider In CleverTap Dashboard](doc:generic-whatsapp#1-set-up-whatsapp-provider-in-clevertap-dashboard)
2. [Set Up CleverTap Callbacks with Provider](doc:generic-whatsapp#2-set-up-clevertap-callbacks-with-provider)
3. [Adding Message Template](doc:generic-whatsapp#3-adding-message-template)
4. [Create a Campaign](doc:generic-whatsapp#4-create-a-campaign)
5. [Creating a Journey](doc:generic-whatsapp#5-creating-a-journey)

## 1. Set Up WhatsApp Provider In CleverTap Dashboard

To configure the CleverTap dashboard:

1. Navigate to _Settings_ > _Channels_ > _WhatsApp_> _WhatsApp Connect_ from the CleverTap dashboard.
2. Click **+ Add Provider** and select Generic (Other) from the dropdown.


<Image src="https://files.readme.io/29282ee-Whatsapp_Common_Provider_Setup.png" border={true} />


Add a WhatsApp Provider

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

3. Enter the following details:

   | Field                        | Description                                                                                                                                                 |
   | :--------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | Provider                     | Select _Other (Generic)_ from the dropdown list.                                                                                                            |
   | Nickname                     | Enter the nickname \<10-digit phone number> for easy reference.                                                                                             |
   | Mobile Number                | Enter your phone number onboarded to WhatsApp API by your BSP.                                                                                              |
   | Request Type                 | Ensure the Request Type is _Post_.                                                                                                                          |
   | HTTP Endpoint                | Enter HTTP Endpoint as provided by your BSP.                                                                                                                |
   | Authentication               | Select _Basic Authentication_ and enter the _Username_ and _Password_ for the user.                                                                         |
   | Delivery Report Callback URL | This URL is generated automatically. Share the URL with your BSP account manager. It is your BSP's responsibility to integrate this URL in their dashboard. |
   | Inbound Message Callback URL | This URL is generated automatically. Share the URL with your BSP account manager. It is your BSP's responsibility to integrate this URL in their dashboard. |

4. (Optional) Select _Mark this as default_ to make this service provider the default provider to send a WhatsApp message.

5. (Optional) Select _Set auto-reply for users not tracked on CleverTap_ to automatically reply to users who message on WhatsApp but are not tracked on the CleverTap dashboard.

6. (Optional) You can set the _Maximum Concurrent API requests_ anywhere between 30 to 1000 requests. Consider your requirements and the provider's limitations to define this value.

7. Send a Test WhatsApp notification:

![](https://files.readme.io/c384922-sendtest.png "Send a Test WhatsApp Message")  Send a Test WhatsApp Message

8. Click **Save** to save the details.

## 2. Set Up CleverTap Callbacks with Provider

You can find the Callback URLs on the CleverTap dashboard under the Provider _Setup_ page. Naviagte to _Settings_ > _Channels_ > _WhatsApp_ .

To set up the CleverTap callbacks, share the following with your BSP account manager:

- Delivery Report Callback URL
- Inbound Message Callback URL
- The WhatsApp phone number that will be used in CleverTap

![](https://files.readme.io/b61e35f-Whatsapp_provider_credentials.png)  Callback URLs

## 3. Adding Message Template

To create WhatsApp campaigns, you must have pre-approved WhatsApp message templates saved in the CleverTap dashboard. To add the message templates:

1. Navigate to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ >_Provider Nickname_ from the CleverTap dashboard.
2. Select the _Templates_ option, and click **+Template**.

For more information, refer to adding a [generic message template](https://docs.clevertap.com/docs/haptik#adding-message-template)

### Import Templates

The Import Template functionality allows importing WhatsApp message templates from a vendor into CleverTap without manually recreating them. This eliminates the need to duplicate template content field by field and helps reduce errors caused by formatting mismatches.

The import will be successful only if the vendor supports template import functionality. In such cases, the vendor will provide the required API endpoint, authentication credentials, and additional configuration details such as import limits and click-tracking domains.

Imported templates must follow [Meta’s template import format](https://developers.facebook.com/docs/whatsapp/business-management-api/message-templates/#best-practices-for-marketing-templates). To set up the import, configure the following fields:

1. Navigate to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ >_+ Provider Configuration_ from the CleverTap dashboard.

2. Select _Generic (other)_ from the list, and then select the **Template import setup** check box.
   ![](https://files.readme.io/3687cd7cbba725b02a5dbe0753dc02dc11ebd53d4801e4df53197a75e2e0c0ec-2025-07-20_18-18-40.png)  Import Template

3. Select _Request Type_: Select **GET** from the _Request Type_ list. This is the supported method for importing templates via an external endpoint.

4. Specify _HTTP Endpoint_: Enter the _HTTP endpoint_ URL provided by the vendor. This is the URL to which CleverTap will send the **GET** request to fetch the templates for import.  CleverTap expects the vendor to return a response that matches this structure exactly. The following is an example of the request and response formats:

   **API Call Example**:

   ```json
   curl --location 'https://vendor-api.XXXX.com/templates/import?limit=50' \
   --header 'Authorization: Bearer  ********************'
   ```

   **Second Request**: If the number of templates exceeds the defined limit, CleverTap uses the `after` cursor returned in the first response to fetch the next batch of templates. This ensures all available templates are retrieved in sequential pages.

   ```json
   curl --location 'https://vendor-api.XXXX.com/templates/import?limit=500&after=MgZDZD"' \
   --header 'Authorization: Bearer  ********************'
   ```

   **Expected Response for Basic Template**:

   ```json
   {
     "data": [
       {
         "name": "dashboard_track_order",
         "message_send_ttl_seconds": 30,
         "previous_category": "MARKETING",
         "parameter_format": "POSITIONAL",
         "components": [
           {
             "type": "BODY",
             "text": "Hey {{1}}, Your order is out for delivery. Track your order here",
             "example": {
               "body_text": [
                 ["Sample"]
               ]
             }
           },
           {
             "type": "BUTTONS",
             "buttons": [
               {
                 "type": "URL",
                 "text": "Track Order",
                 "url": "https://XXXX/{{1}}",
                 "example": ["https://XXXX/test"]
               }
             ]
           }
         ],
         "language": "en",
         "status": "APPROVED",
         "category": "UTILITY",
         "id": "83383905XXXX"
       }
     ],
     "paging": {
       "cursors": {
         "before": "MAZDZD",
         "after": "MgZDZD"
       },
       "next": "https://vendor-api.XXXX.com/templates/import?limit=500&after=MgZDZD"
     }
   }
   ```

   **Expected Response for LTO Templates**:

   ```json
   {
     "data": [
       {
         "name": "lto_template_import",
         "message_send_ttl_seconds": 86400,
         "parameter_format": "POSITIONAL",
         "components": [
           {
             "type": "HEADER",
             "format": "VIDEO",
             "example": {
               "header_handle": [
                 "https://XXXXXX/v/t61.29466-34/XXXX.mp4"
               ]
             }
           },
           {
             "type": "BODY",
             "text": "Celebrate Diwali with a sparkle!\nHey {{1}},\nOur exclusive Diwali Sale is here for a limited time—enjoy massive discounts on your favorite products. Don't miss your chance to brighten up your celebrations and save big. Shop now before the best deals disappear. Explore the Diwali magic with us—tap to unlock your special offer.",
             "example": {
               "body_text": [
                 ["sample"]
               ]
             }
           },
           {
             "type": "LIMITED_TIME_OFFER",
             "limited_time_offer": {
               "text": "Buy Now",
               "has_expiration": true
             }
           },
           {
             "type": "BUTTONS",
             "buttons": [
               {
                 "type": "COPY_CODE",
                 "text": "Copy offer code",
                 "example": ["HAPPYDIWALI"]
               },
               {
                 "type": "URL",
                 "text": "Dynamic Button",
                 "url": "https://XXXX/{{1}}",
                 "example": ["https://XXXX/test"]
               },
               {
                 "type": "URL",
                 "text": "Click tracking",
                 "url": "https://XXXX/{{1}}",
                 "example": ["https://XXXX/test"]
               },
               {
                 "type": "PHONE_NUMBER",
                 "text": "Call us",
                 "phone_number": "+91XXXXXXX"
               },
               {
                 "type": "QUICK_REPLY",
                 "text": "Show More"
               },
               {
                 "type": "QUICK_REPLY",
                 "text": "Coupon Code"
               },
               {
                 "type": "QUICK_REPLY",
                 "text": "STOP"
               }
             ]
           }
         ],
         "language": "en",
         "status": "APPROVED",
         "category": "MARKETING",
         "id": "27152845XXXX"
       }
     ],
     "paging": {
       "cursors": {
         "before": "MAZDZD",
         "after": "MgZDZD"
       },
       "next": "https://vendor-api.XXXX.com/templates/import?limit=500&after=MgZDZD"
     }
   }
   ```

   **Expected Response for Carousel Template**

   ```json
   {
     "data": [
       {
               "name": "carousel_test_01",
               "message_send_ttl_seconds": 54000,
               "parameter_format": "POSITIONAL",
               "components": [
                   {
                       "type": "BODY",
                       "text": "hello {{1}}, Welcome to CleverTap",
                       "example": {
                           "body_text": [
                               [
                                   "Deepa"
                               ]
                           ]
                       }
                   },
                   {
                       "type": "CAROUSEL",
                       "cards": [
                           {
                               "components": [
                                   {
                                       "type": "HEADER",
                                       "format": "VIDEO",
                                       "example": {
                                           "header_handle": [
                                               "https://XXXXXX/v/t61.29466-34/XXXX.mp4"
                                           ]
                                       }
                                   },
                                   {
                                       "type": "BODY",
                                       "text": "dsd"
                                   },
                                   {
                                       "type": "BUTTONS",
                                       "buttons": [
                                           {
                                               "type": "URL",
                                               "text": "dsds",
                                               "url": "http://www.example.com/"
                                           }
                                       ]
                                   }
                               ]
                           },
                           {
                               "components": [
                                   {
                                       "type": "HEADER",
                                       "format": "VIDEO",
                                       "example": {
                                           "header_handle": [
                                               "https://XXXXXX/v/t61.29466-34/XXXX.mp4"
                                           ]
                                       }
                                   },
                                   {
                                       "type": "BODY",
                                       "text": "dsd"
                                   },
                                   {
                                       "type": "BUTTONS",
                                       "buttons": [
                                           {
                                               "type": "URL",
                                               "text": "dsds",
                                               "url": "http://www.example.com/"
                                           }
                                       ]
                                   }
                               ]
                           }
                       ]
                   }
               ],
               "language": "bg",
               "status": "APPROVED",
               "category": "MARKETING",
               "id": "1498361544XXXXXX"
           }
     ],
     "paging": {
       "cursors": {
         "before": "MAZDZD",
         "after": "MgZDZD"
       },
       "next": "https://vendor-api.XXXX.com/templates/import?limit=500&after=MgZDZD"
     }
   }
   ```

5. Specify _Import Limits & Pagination_: Define the number of templates to retrieve in each request (recommended: 50 to 500) and configure how pagination is handled. Vendors may use page numbers, cursors, or tokens to return additional results. These values are provided by the vendor and must be configured accurately to ensure full template retrieval.

6. Configure _Authentication_ (optional): Add the appropriate authentication headers if the vendor’s API requires authorization. CleverTap supports Basic Authentication and custom header-based tokens. For more details on authentication methods (including _Basic Authentication_), refer to the [Set Up Webhooks documentation](https://docs.clevertap.com/docs/setup-webhooks#basic-authentication).

7. Set _Track Clicks_ (optional): This field enables click tracking on imported templates that contain buttons using a click-tracking domain. Since Meta does not natively support click tracking, vendors may implement it by using a dynamic button configured with a custom tracking domain.

   If the vendor supports click tracking through such a solution, provide the relevant domain in this field. During import, CleverTap will identify templates containing this domain and tag the associated buttons for click tracking. For more information, refer to the [Click Tracking section in WhatsApp Stats](https://docs.clevertap.com/docs/whatsapp-stats#clicked).

8. Once the configuration is complete and saved, navigate to the _Templates_ tab.

<Callout icon="📘" theme="info">
  ### **Note**

  For any button type other than one using CleverTap Click Tracking, the vendor must pass the _Notification Clicked_ event for CleverTap to track the click. If the event is not passed, CleverTap does not attribute the click to that button, and the click is excluded from the _Clicked_ stat on the [WhatsApp Stats page](https://docs.clevertap.com/docs/whatsapp-stats#clicked).
</Callout>

## 4. Create a Campaign

To create a WhatsApp campaign using your BSP as the provider, refer to [Create a WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign) for detailed instructions. If your users reply to notifications sent from CleverTap, incoming messages appear under the _Conversation_ section of the dashboard. Businesses can reply to incoming messages by selecting the chat.

## 5. Creating a Journey

To create a WhatsApp journey using Infobip as the provider, refer to [Create a WhatsApp Journey](doc:engagement-nodes-whatsapp) for detailed instructions.

# Generic WhatsApp Integration Terminology

## Messaging API Endpoint

BSPs are requested to create an endpoint where CleverTap can send the notification payload for campaigns and free-form messages. Customers must ask BSPs to share the API endpoint that can accept the CleverTap Payload to save the provider in CleverTap Dashboard.

## API Authentication

The CleverTap's REST API supports basic authentication or custom headers for authentication. Providers must share these credentials with customers so that customers can save these credentials with an endpoint.

## IMO(Incoming Message) & DLR (Status) Callbacks

CleverTap creates unique DLR callbacks for each customer. WhatsApp providers/customers have to configure the [DLR and IMO](https://docs.clevertap.com/docs/generic-whatsapp#message-status-callbacks) callbacks at their end to send the Messages status and incoming messages to CleverTap. Status and incoming messages will only be captured if these are sent in CleverTap's expected payload structure.

## Template Message Payload

CleverTap has published the [Template Message payload formats](https://docs.clevertap.com/docs/generic-whatsapp#api-payload-for-template-message) that will be sent to messaging endpoint whenever a template message is sent from CleverTap Dashboard.

## Freeform Message Payload

CleverTap has published the [Freeform Messsage payload formats](https://docs.clevertap.com/docs/generic-whatsapp#api-payload-for-freeform-message) that will be sent to messaging endpoint whenever a freeform message is sent from CleverTap Dashboard.

## Validation Payload

CleverTap sends a [dummy message payload API endpoint](https://docs.clevertap.com/docs/generic-whatsapp#validation-payload-1), and credentials are configured in the CleverTap dashboard. This is required since at the time of saving provider in CleverTap doesn't have templates to test the credentials.

## API Concurrency

By default, CleverTap hits the generic messaging API endpoint at 1500 concurrency ie. 1500 concurrent messaging requests are sent to messaging endpoint whenever a campaign is created in the CleverTap dashboard.

# Messaging & Callback Payloads

## Messaging API Specification

CleverTap sends outbound message payloads into two categories:

- Templates messages: These are preapproved messages templates needed to initiate a conversation with conversation.
- Freeform messages: These are free text messages that can be sent to end user in response to their incoming messages.

CleverTap sends either of the payloads depending on the type of message sent by the dashboard user. CleverTap sends  the`isTemplate` key to helping BSPs understand whether this is a templatized message or a freeform message.

<Callout icon="📘" theme="info">
  ### Single Endpoint

  CleverTap does not support different endpoints for different types of messages, so BSPs must provide just one endpoint to process freeform and template messages.
</Callout>

### API Payload for Template Message

CleverTap sends this payload for sending the template message notification.<br />The outgoing template message payload can be broken down into the following three sections:

- User & notification information
- Template information includes template name, namespace, template language, and so on.
- Content information

<Callout icon="📘" theme="info">
  ### Payload Essentials

  The message payload is encoded into UTF-8 (Unicode Transformation Format) before being sent to the provider's endpoint.

  Values with $$ ($$To,$$BusinessWabaNumber) are dynamic values and change for each request.

  CleverTap does not support templates with contacts currently, so contact objects are not sent with payload.

  CleverTap does not support Name, Address, or URL key in location object.

  `msg_id` is a unique parameter for each message sent from CleverTap and must be present in callbacks sent by BSP to CleverTap.
</Callout>

#### Payload Description for Template Message

| Parameter                 | Description                                                               | Data Type | Example Values                                                                     |
| :------------------------ | :------------------------------------------------------------------------ | :-------- | :--------------------------------------------------------------------------------- |
| payloadVersion            | Version of the payload being used.                                        | Float     | 0.1                                                                                |
| to                        | Recipient's phone number                                                  | String    | "919876543210", "+919876543210"                                                    |
| wabaNumber                | WhatsApp Business Account number                                          | String    | "1234567890"                                                                       |
| isTemplate                | Indicates if the message is a template                                    | Boolean   | TRUE                                                                               |
| msgId                     | Unique identifier for the message                                         | String    | "i\|campaignID\|batchID\|j\|campaign\_variant"                                     |
| template.namespace        | Identifier for the template in CleverTap Dashboard                        | String    | "my\_template\_namespace"                                                          |
| template.languageCode     | Language and locale code for the template                                 | String    | "en\_US"                                                                           |
| components.type           | Type of component, like header, body, button, and so on.                  | String    | "header", "body", "button"                                                         |
| header.type               | Type of header like text, video, image, file, location                    | String    | "text", "video", "image", "file", "location"                                       |
| header.text.text          | Text content for text header                                              | String    | "Hello, World!"                                                                    |
| header.video.mediaURL     | URL to the video media file                                               | String    | [http://example.com/video.mp4](http://example.com/video.mp4)                       |
| header.image.mediaURL     | URL to the image media file                                               | String    | [http://example.com/image.jpg](http://example.com/image.jpg)                       |
| header.file.mediaURL      | URL to the file media                                                     | String    | [http://example.com/document.pdf](http://example.com/document.pdf)                 |
| header.file.filename      | Filename for the file                                                     | String    | "document.pdf"                                                                     |
| header.location.longitude | Longitude for location header                                             | String    | "74.0060"                                                                          |
| header.location.latitude  | Latitude for location header                                              | String    | "40.7128"                                                                          |
| header.location.name      | Name for the location                                                     | String    | "Central Park"                                                                     |
| header.location.address   | Address for the location                                                  | String    | "New York, NY 10024"                                                               |
| body.text                 | Body text of the message                                                  | String    | "Your order is ready for pickup."                                                  |
| footer                    | Footer text for the message                                               | String    | "Thank you for choosing us!"                                                       |
| button.subType            | Specific type of button like dynamicUrl, staticUrl, quickReply, callPhone | String    | "dynamicUrl", "staticUrl"                                                          |
| button.buttonText         | Text displayed on the button                                              | String    | "Click Here", "Copy Offer Code"                                                    |
| button.index              | Position of the button                                                    | Integer   | 1, 2                                                                               |
| button.parameters         | Parameters for the button, like URL suffix, phone number, and so on.      | Array     | Depends on button.type                                                             |
| customProps               | Custom key-value pairs defined at the time of creating campaigns          | Array     | \[<br />{<br />"key1": "Value1"<br />},<br />{<br />"Key2": "Value2"<br />}<br />] |

#### Payload Samples for Template Message

```json Text Template with Footer
{
"payloadVersion":0.1,
"to": "919999999999",
"wabaNumber": "91999999XXXX",
"isTemplate": true,
"msgId": "25596363|1639561857|20220227|25596363",
"template": {
             "namespace": "Namespace:sample",
             "languageCode":"en(uk)"
                         
                         },
"components": [

{
 "type": "body",
 "body": {
 "text":"This is sample body",
  "parameters": [
               {
                  "type": "text",
                   "text": "Sample"
               }
           ]}},
  {
  "type": "footer",
  "footertext":"this is footer"
        
       }
]}
```
```json Image Template with  Dynamic URL CTA buttons
{
    "payloadVersion": 0.1,
    "to": "919999999999",
    "wabaNumber": "919999999999",
    "isTemplate": true,
    "msgId": "i|campaignID|batchID|j",
    "template": {
        "namespace": "Namespace:sample",
        "languageCode": "en"
    },
    "components": [
        {
            "type": "header",
            "header": {
                "type": "image",
                "image": {
                    "mediaURL": "httpa://www.example.com/image.png"
                }
            }
        },
        {
            "type": "body",
            "body": {
                "text": "This is sample body",
                "parameters": [
                    {
                        "type": "text",
                        "text": "sample"
                    }
                ]
            }
        },
        {
            "type": "button",
            "index": 0,
            "subType": "dynamicUrl",
            "buttonText": "Sample CTA TEXT",
            "parameters": [
                {
                    "type": "text",
                    "text": "https://www.example.com"
                }
            ]
        }
    ]
}
```
```json Simple Text Template
{
    "payloadVersion": 0.1,
    "to": "+9199XXXXXXX", 
    "wabaNumber": "+91999999999",
     "isTemplate": true,
    "msgId": "1|2|3|4|5",
    "template": {
        "namespace": "Sample_Template",// Template name saved in CleverTap Dashboard
        "languageCode": "en(UK)"
    },
    "components": [
        
        {
            "type": "body",
            "body": {
                "text": "Hey User, This is Body",
                "parameters": [
                    {
                        "type": "text",
                        "text": "user"
                    }
                ]
            }
        }
    ]
}
```
```json Media Template
{
    "payloadVersion": 0.1,
    "to": "+9199XXXXXXX", 
    "wabaNumber": "+91999999999",
     "isTemplate": true,
    "msgId": "1|2|3|4|5",
    "template": {
        "namespace": "Sample_Template",// Template name saved in CleverTap Dashboard
        "languageCode": "en(UK)"
    },
    "components": [
    {
    "type": "header",
    "header": {
                "type": "image",
                "image": {
                    "mediaURL": "example.com/image.png"
                }
            }
        
        {
            "type": "body",
            "body": {
                "text": "Hey User, This is Body",
                "parameters": [
                    {
                        "type": "text",
                        "text": "user" 
                    }
                ]
            }
        },
        { 
            "type": "button",
            "index": 0,
            "subType": "dynamicUrl",
            "buttonText": "Check-out cart",
            "parameters": [
                {
                    "type": "text",
                    "text": "cart"
                }
            ]
        },
        {
            "type": "button",
            "index": 0,
            "subType": "callPhone",
            "buttonText": "Call support",
            "parameters": [
                {
                    "type": "text",
                    "text": "+91994876856"
                }
            ]
        }
    ]
}
```
```json Limited Time Offer Template
{
  "payloadVersion": 0.1,
  "wabaNumber": "919999999999",
  "to": "+919999999244",
  "isTemplate": true,
  "template": {
    "namespace": "Test_template",
    "languageCode": "en"
  },
  "components": [
    {
      "type": "header",
      "header": {
        "type": "image",
        "image": {
          "mediaURL": "https://hatrabbits.com/wp-content/uploads/2017/01/random.jpg"
        }
      }
    },
    {
      "type": "body",
      "body": {
        "text": "Hey 0, Welcome to CleverTap.",
        "parameters": [
          {
            "type": "text",
            "text": "0"
          }
        ]
      }
    },
    {
      "type": "limited_time_offer",
      "text": "Buy 1 Get 1 Free",
      "parameters": [
        {
          "type": "limited_time_offer",
          "limited_time_offer": {
            "expiration_time_ms": 1712081380237
          }
        }
      ]
    },
    {
      "type": "button",
      "index": 0,
      "buttonText": "Copy offer code",
      "subType": "copy_code",
      "parameters": [
        {
          "type": "coupon_code",
          "coupon_code": "SAMPLECODE"
        }
      ]
    },
    {
      "type": "button",
      "index": 1,
      "buttonText": "Check Out Now",
      "subType": "dynamicUrl",
      "parameters": [
        {
          "type": "text",
          "text": "0"
        }
      ]
    },
    {
      "type": "button",
      "index": 2,
      "buttonText": "Call support",
      "subType": "callPhone",
      "parameters": [
        {
          "type": "text",
          "text": "+91999999999"
        }
      ]
    },
    {
      "type": "button",
      "index": 3,
      "buttonText": "Yes",
      "subType": "quickReply"
    },
    {
      "type": "button",
      "index": 4,
      "buttonText": "No",
      "subType": "quickReply"
    },
    {
      "type": "button",
      "index": 5,
      "buttonText": "Show More",
      "subType": "quickReply"
    }
  ],
  "msgId": "0|0|0|0"
}
```
```json Multi Button Templates
{
  "payloadVersion": 0.1,
  "wabaNumber": "9407178156",
  "to": "+9198574656",
  "isTemplate": true,
  "template": {
    "namespace": "Test_Template",
    "languageCode": "en"
  },
  "components": [
    {
      "type": "header",
      "header": {
        "type": "file",
        "file": {
          "mediaURL": "http://www.clevertap.com/~offer/pdf/new_offer.pdf",
          "filename": "New_offer"
        }
      }
    },
    {
      "type": "body",
      "body": {
        "text": "Hey 0, This is a test template",
        "parameters": [
          {
            "type": "text",
            "text": "0"
          }
        ]
      }
    },
    {
      "type": "footer",
      "footer": "Please reply \"stop\" to optout"
    },
    {
      "type": "button",
      "index": 0,
      "buttonText": "Copy offer code",
      "subType": "copy_code",
      "parameters": [
        {
          "type": "coupon_code",
          "coupon_code": "SAMPLECODE"
        }
      ]
    },
    {
      "type": "button",
      "index": 1,
      "buttonText": "Visit App",
      "subType": "dynamicUrl",
      "parameters": [
        {
          "type": "text",
          "text": "https://www.clevertap.com/{{1}}"
        }
      ]
    },
    {
      "type": "button",
      "index": 2,
      "buttonText": "Check Out Now",
      "subType": "staticUrl",
      "parameters": [
        {
          "type": "text",
          "text": "https://www.clevertap.com"
        }
      ]
    },
    {
      "type": "button",
      "index": 3,
      "buttonText": "Show more",
      "subType": "quickReply"
    },
    {
      "type": "button",
      "index": 4,
      "buttonText": "Not Now",
      "subType": "quickReply"
    },
    {
      "type": "button",
      "index": 5,
      "buttonText": "STOP",
      "subType": "quickReply"
    }
  ],
  "msgId": "0|0|0|0"
}
```
```json Carousel Template
{
    "payloadVersion": 0.1,
    "wabaNumber": "+919930079420",
    "to": "+91999645754",
    "isTemplate": true,
    "template": {
      "namespace": "carousel_test_1",
      "languageCode": "en"
    },
    "components": [
      {
        "type": "body",
        "body": {
          "text": "hello main body 0",
          "parameters": [
            {
              "type": "text",
              "text": "0"
            }
          ]
        }
      },
      {
        "type": "carousel",
        "cards": [
          {
            "components": [
              {
                "type": "header",
                "header": {
                  "type": "image",
                  "image": {
                    "mediaURL": "https://hatrabbits.com/wp-content/uploads/2017/01/random.jpg"
                  }
                }
              },
              {
                "type": "body",
                "body": {
                  "text": "Hello card1 0, how are you?? 1",
                  "parameters": [
                    {
                      "type": "text",
                      "text": "0"
                    },
                    {
                      "type": "text",
                      "text": "1"
                    }
                  ]
                }
              },
              {
                "type": "button",
                "index": 0,
                "buttonText": "Shop Now",
                "subType": "dynamicUrl",
                "parameters": [
                  {
                    "type": "text",
                    "text": "wa/5xu5auQ"
                  }
                ]
              },
              {
                "type": "button",
                "index": 1,
                "buttonText": "Dynamic",
                "subType": "dynamicUrl",
                "parameters": [
                  {
                    "type": "text",
                    "text": "0"
                  }
                ]
              }
            ]
          },
          {
            "components": [
              {
                "type": "header",
                "header": {
                  "type": "image",
                  "image": {
                    "mediaURL": "https://hatrabbits.com/wp-content/uploads/2017/01/random.jpg"
                  }
                }
              },
              {
                "type": "body",
                "body": {
                  "text": "Hello card2 0, how are you?? 1",
                  "parameters": [
                    {
                      "type": "text",
                      "text": "0"
                    },
                    {
                      "type": "text",
                      "text": "1"
                    }
                  ]
                }
              },
              {
                "type": "button",
                "index": 0,
                "buttonText": "Shop Now",
                "subType": "staticUrl",
                "parameters": [
                  {
                    "type": "text",
                    "text": "https://www.clevertap.com"
                  }
                ]
              },
              {
                "type": "button",
                "index": 1,
                "buttonText": "Dynamic",
                "subType": "dynamicUrl",
                "parameters": [
                  {
                    "type": "text",
                    "text": "0"
                  }
                ]
              }
            ]
          }
        ]
      }
    ],
    "msgId": "0|0|0|0"
  }
```
```json Template with Custom Key-Value
{
  "payloadVersion": 0.1,
  "wabaNumber": "9407178156",
  "to": "7658734869",
  "isTemplate": true,
  "template": {
    "namespace": "sample_template",
    "languageCode": "en"
  },
  "components": [
    {
      "type": "header",
      "header": {
        "type": "file",
        "file": {
          "mediaURL": "https://d1510fwumr3byl.cloudfront.net/dist/1400000001/i/f90291d5c12140b1b36a9047c407ad75.pdf?v=1724156050",
          "filename": "OctoberCM2"
        }
      }
    },
    {
      "type": "body",
      "body": {
        "text": "Hey User, This test templates",
        "parameters": [
          {
            "type": "text",
            "text": "User"
          }
        ]
      }
    },
    {
      "type": "footer",
      "footer": "Please reply \"stop\" to optout"
    },
    {
      "type": "button",
      "index": 0,
      "buttonText": "Copy offer code",
      "subType": "copy_code",
      "parameters": [
        {
          "type": "coupon_code",
          "coupon_code": "BLACKFRIDAY20"
        }
      ]
    },
    {
      "type": "button",
      "index": 1,
      "buttonText": "Visit App",
      "subType": "staticUrl",
      "parameters": [
        {
          "type": "text",
          "text": "https://www.clevertap.com"
        }
      ]
    },
    {
      "type": "button",
      "index": 2,
      "buttonText": "Check Out Now",
      "subType": "staticUrl",
      "parameters": [
        {
          "type": "text",
          "text": "https://www.clevertap.com"
        }
      ]
    },
    {
      "type": "button",
      "index": 3,
      "buttonText": "Show more",
      "subType": "quickReply"
    },
    {
      "type": "button",
      "index": 4,
      "buttonText": "Not Now",
      "subType": "quickReply"
    },
    {
      "type": "button",
      "index": 5,
      "buttonText": "STOP",
      "subType": "quickReply"
    },
    {
      "customProps": [
        {
          "Key1": "$$Value1"
        },
        {
          "key2": "$$Value2"
        }
      ]
    }
  ],
  "msgId": "0|0|0|0"
}
```

## API Payload for Freeform Message

CleverTap will send this payload for sending the Freeform message notification.<br />Freeform message API payload has the user information about the targetted users, media URLs, and text.

<Callout icon="📘" theme="info">
  ### Payload Essentials

  - Values with $$ (for example $$To,$$BusinessWabaNumber) are dynamic values and change for each request.

    - Dynamic Reply Button, interactive lists, and product catalog, contacts, and locations are not currently supported in the CleverTap platform. This is why these objects are not mentioned in the payload.

    - CleverTap does not support Name, Address, or URL key in location object.

    - `msg_id` is a unique parameter for each message sent from CleverTap and must be present in callbacks sent by BSP to CleverTap.
</Callout>

#### Payload Description for Freeform Message

| Parameter        | Description                                                                              | Example Value                                                       |              |            |          |
| :--------------- | :--------------------------------------------------------------------------------------- | :------------------------------------------------------------------ | :----------- | :--------- | :------- |
| to               | Targeted user’s phone number                                                             | 9199XXXXXXXX                                                        |              |            |          |
| "payloadversion" | Version of the payload being sent to CleverTap                                           | 0.1                                                                 |              |            |          |
| wabaNumber       | Business’s WABA number                                                                   | 9189XXXXXXXX                                                        |              |            |          |
| isTemplate       | Used to highlight the whether the payload being sent is for templates or freeform        | true/false                                                          |              |            |          |
| msgId            | Unique identifier for message being sent and expected to be present in callback payloads | 25596363\\                                                          | 1639561857\\ | 20220227\\ | 25596363 |
| audio.mediaURL   | Media URL of the file                                                                    | [www.example.com/audio.mp3](http://www.example.com/audio.mp3)       |              |            |          |
| file.mediaURL    | Media URL of the file                                                                    | [www.example.com/document.pdf](http://www.example.com/document.pdf) |              |            |          |
| file.caption     | Message body                                                                             | “This is message body”                                              |              |            |          |
| file.filename    | Title of the file                                                                        | “sample\_document.pdf”                                              |              |            |          |
| image.mediaURL   | Media URL of the file                                                                    | [www.example.com/image.png](http://www.example.com/image.png)       |              |            |          |
| image.caption    | Message body                                                                             | “This is message body”                                              |              |            |          |
| video.mediaURL   | Media URL of the file                                                                    | [www.example.com/video.mp4](http://www.example.com/video.mp4)       |              |            |          |
| video.caption    | Message body                                                                             | “This is message body”                                              |              |            |          |

#### Payload Samples For Freeform Message

```json Message Template with Audio
{
"payloadVersion":0.1,
"to": "919999999999",
“msg_id”:"25596363|1639561857|20220227|25596363",
"wabaNumber": "91999999XXXX",
"type": "audio",
"isTemplate": false,
"audio": {
        "mediaURL": "www.example.com/audio.mp3"
        }
        }
```
```json Message Template with Image
{
"payloadVersion":0.1,
"to": "919999999999",
"wabaNumber": "91999999XXXX",
“msg_id”:"25596363|1639561857|20220227|25596363",
"type": "image",
"isTemplate": false,
"image": {"mediaURL": "www.example.com/image.png","caption": "This is body"} }
```
```json Message with documents
{
"payloadVersion":0.1,
"to": "919999999999",
"wabaNumber": "91999999XXXX",
“msg_id”:"25596363|1639561857|20220227|25596363",
"type": "file",
"isTemplate": false,
"file": {
          "mediaURL": "www.example.com/document.pdf",
           "caption": "This is body",
          "filename": "sample.pdf"
          } }
```

## Expected API Response

### Validation Payload

CleverTap sends the following payload to validate the Messaging endpoint and API credentials saved in the dashboard. We expect success response within a second to save the endpoint.

```json
{
    "body": {
        "payloadVersion": 0.1,
        "wabaNumber": "9199XXXXXXXX",
        "to": "9189XXXXXXXX",
        "isTemplate": true,
        "template": {
            "namespace": "whatsapp:hsm:technology:generic:verify",
            "languageCode": "en"
        },
        "components": [
            {
                "type": "body",
                "body": {
                    "text": "1 code: 2.Valid for 3 minutes.",
                    "parameters": [
                        {
                            "type": "text",
                            "text": "1"
                        },
                        {
                            "type": "text",
                            "text": "2"
                        },
                        {
                            "type": "text",
                            "text": "3"
                        }
                    ]
                }
            }
        ],
        "msgId": "0|0|0|0"
    }
}
```

If the format is incorrect, we throw an error showing the API request and response we received from the endpoint.

### Error Objects

CleverTap expects partners to return any of the following responses depending on whether the request was successful. CleverTap will read the response body if the API request status code is _200 OK_, so notification processing-related errors and codes can be sent in the response body. Read the following for expected error codes:

<Callout icon="📘" theme="info">
  ### Error Object

  The error object for the following error code needs to be specified only if there are errors in the send message API request:

  - 2000 → Invalid credentials
  - 2001 → Invalid template parameters
  - 2002 → Invalid phone number
  - 2003 → Phone number not subscribed
  - 2004 → Other
</Callout>

### HTTPS Codes

```Text 200 Successful API call
{ 
  "status": "success | failure",
}
```
```Text Code 200
{ 
  "status": "failure",
   "error" : {
              "code" : 2000,
              "message" : "Invalid Credentials"
              }
}
```
```Text Code 500
{
"status": "failure",
"error" : {
"message" : "Unable to process the request"
          }
}
```
```Text Code 429
{ "message" : "Too many requests to process"}
```
```Text Code 403
{ "message" : "Bad Request"}
```

## WhatsApp Callbacks

CleverTap automatically creates unique callback URLs for each customer. These callback URLs are available under the _Provider_ setup section. BSPs are expected to add these callbacks at their end and forward the incoming messages to CleverTap’s callback URL in the specified format. CleverTap creates separate callback URLs for message status and incoming messages. Both these callbacks must be configured at the BSP's end.

### Callback Authentication

CleverTap creates unique callback URLs for each customer and does not need any authentication. CleverTap accepts the callbacks if the callbacks are sent in the expected format.

### Incoming Message Callbacks

BSPs must add  CleverTap's incoming message callback URL at their end and forward the incoming message in the following format.

#### Payload Description for Incoming Message Callbacks

| Parameter          | Description                                                | Example Value                                                 |              |            |          |
| :----------------- | :--------------------------------------------------------- | :------------------------------------------------------------ | :----------- | :--------- | :------- |
| from               | Source number for incoming message                         | “9199XXXXXXXX”                                                |              |            |          |
| payloadVersion     | version of the callback payload being sent to CleverTap    | “0.1“                                                         |              |            |          |
| wabaNumber         | Destination business WABA number to which message was sent | “9199XXXXXXXX”                                                |              |            |          |
| timestamp          | Timestamp when the message was sent                        | “1647441774”                                                  |              |            |          |
| type               | Type of incoming message                                   | “text/audio/video/image”                                      |              |            |          |
| context.id         | `Msg_id` of the message to which the user has responded    | 25596363\\                                                    | 1639561857\\ | 20220227\\ | 25596363 |
| text.body          | Text received from end user                                | “Hey, This is message”                                        |              |            |          |
| location.lattitude | Latitude of the location shared                            | 2.457476548                                                   |              |            |          |
| location.Longitude | Longitude of the location shared                           | 1.565867657                                                   |              |            |          |
| location.name      | Name of the location shared                                | Joe’s House                                                   |              |            |          |
| location.address   | Address of the location shared                             | 102, Parker street, USA                                       |              |            |          |
| location.url       | Address URL                                                | [www.example.com](http://www.example.com)                     |              |            |          |
| image.mediaURL     | Media File URL                                             | [www.example.com/image.png](http://www.example.com/image.png) |              |            |          |
| image.mimetype     | Media file mime type                                       | .png/.jpeg                                                    |              |            |          |
| image.caption      | Image caption                                              | “This is caption”                                             |              |            |          |
| file.mediaURL      | Media File URL                                             | [www.example.com/file.pdf](http://www.example.com/file.pdf)   |              |            |          |
| file.mimetype      | Media file mime type                                       | .pdf                                                          |              |            |          |
| file.caption       | Image caption                                              | “This is caption”                                             |              |            |          |
| audio.mediaURL     | Media File URL                                             | [www.example.com/audio.mp3](http://www.example.com/audio.mp3) |              |            |          |
| video.mimetype     | Media file mime type                                       | .mp3                                                          |              |            |          |
| video.mediaURL     | Media File URL                                             | [www.example.com/image.png](http://www.example.com/image.png) |              |            |          |
| video.mimetype     | Media file mime type                                       | .mp4                                                          |              |            |          |
| video.caption      | Image caption                                              | “This is caption”                                             |              |            |          |

#### Sample Payload for Incoming Message Callbacks

```Text Incoming message with Text
{
    "payloadVersion": "0.1",
    "from": "919999999999",
    "wabaNumber": "9199999998888",
    "timestamp": "1647441774",
    "type": "text",
    "context": {
        "id": "25596363|1639561857|20220227|25596363"
    },
    "text": {
        "body": "$$incomingMessage"
    }
}
```
```json Incoming message with Document
{
              "payloadVersion":"0.1",
              "from": "919999999999",
              "wabaNumber": "9199999998888",
              "timestamp": "1647441774",
              "type": "file",
              "context": {
              "id": "25596363|1639561857|20220227|25596363"
              },
"document": {
            "mediaURL": "www.example.com/document.pdf",
             "caption": "This is body",
             "mimeType": ".pdf"
          } 
}
```
```json Incoming message with location
{
"payloadversion":"0.1",
"from": "919999999999",
"wabaNumber": "9199999998888",
"timestamp": "1647441774",
"type": "location",
"context": {
              "id": "25596363|1639561857|20220227|25596363"
              },
"location": {
            "address": "107, baker street",
            "latitude": "2.457476548",
            "longitude": "2.457476548",
            "name": "Johns office", //optional
            "url": "www.johnsoffice.com" // optional
            }
}
```
```Text Incoming message with Image
{
    "payloadVersion": "0.1",
    "from": "+91XXXXXXXXXX",
    "wabaNumber": "+91XXXXXXXXXX",
    "timestamp": "1647441774",
    "type": "image",
    "context": {
        "id": "25596363|1639561857|20220227|25596363"
    },
    "image": {
        "mediaURL": "www.example.com/image.png",
        "mimeType": "image/jpeg",
        "caption": "This is body"
    }
}
```
```Text Incoming message with Audio
{
    "payloadVersion": "0.1",
    "from": "+91XXXXXXXXXX",
    "wabaNumber": "+91XXXXXXXXXX",
    "timestamp": "1647441774",
    "type": "voice",
    "context": {
        "id": "25596363|1639561857|20220227|25596363"
    },
    "audio": {
        "mediaURL": "www.example.com/audio.mp3",
        "mimeType": "audio/mpeg"
    }
}
```
```Text Incoming message with Video
{
    "payloadVersion": "0.1",
    "from": "+91XXXXXXXXXX",
    "wabaNumber": "+91XXXXXXXXXX",
    "timestamp": "1647441774",
    "type": "video",
    "context": {
        "id": "25596363|1639561857|20220227|25596363"
    },
    "video": {
        "mediaURL": "www.example.com/video.mp4",
        "mimeType": "video/mp4",
        "caption": "This is body"
    }
}
```
```Text Incoming message with Button
{
    "payloadVersion": "0.1",
    "from": "+91XXXXXXXXXX",
    "wabaNumber": "+91XXXXXXXXXX",
    "timestamp": "1647441774",
    "type": "button",
    "context": {
        "id": "25596363|1639561857|20220227|25596363"
    },
    "button": {
        "payload": "CONFIRM_ORDER",
        "text": "Confirm Order"
    }
}
```

### Message Status Callbacks

BSPs must add  CleverTap's message status callback URL at their end and forward the message statuses (DLR callback) in the following format. CleverTap uses these callbacks to populate the campaign statistics.

<Callout icon="📘" theme="info">
  ### Provider Click Tracking

  Click-tracking data is accessible only when the **Provider Click Tracking** button is utilized in the campaign templates.
</Callout>

```json Sent Status Callback
{
    "payloadVersion": $$paypoadVersion,
    "statuses": [
        {
            "msgId": "$$customMessageID",
            "status": "sent",
            "timestamp": "$$timestamp", //Event timestamp
        }
    ]
}
```
```json Delivered Status Callback
{
    "payloadVersion": $$paypoadVersion,
    "statuses": [
        {
            "msgId": "$$customMessageID",
            "status": "delivered",
            "timestamp": "$$timestamp", //Event timestamp
        }
    ]
}
```
```json Read Status Callback
{
    "payloadVersion": $$paypoadVersion,
    "statuses": [
        {
            "msgId": "$$customMessageID",
            "status": "read",
            "timestamp": "$$timestamp", //Event timestamp
        }
    ]
}
```
```json Failed Status Callback
{
    "payloadVersion": $$paypoadVersion,
    "statuses": [
        {
            "msgId": "$$customMessageID",
            "status": "failed",
            "timestamp": "$$timestamp", //Event timestamp
            "error": {
                "code": "$$errorcode",
                "title": "$$errordescription"
            }
        }
    ]
}
```
```json Clicked Status Callback
{
    "payloadVersion": "0.1",
    "statuses": [
        {
            "msgId": "4930004|1731583253|20241114|4930004",
            "status": "Clicked"
            "url": "www.google.com/19nov",
            "shortUrl": "https://bit.ly/3Oj42219",
            "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.82 Safari/537.36"
        }
    ]
}
```

#### Payload Description for Message Status Callbacks

| Parameter                | Description                                                                              | Example Value                                       |              |            |          |
| :----------------------- | :--------------------------------------------------------------------------------------- | :-------------------------------------------------- | :----------- | :--------- | :------- |
| payloadversion           | Version of the payload being sent to CleverTap                                           | 0.1                                                 |              |            |          |
| statuses\[X].status      | Notification status                                                                      | “sent/delivered/read/failed/clicked”                |              |            |          |
| statuses\[X].timestamp   | Timestamp of the event                                                                   | “1647441774”                                        |              |            |          |
| statuses\[X].msgId       | Unique identifier for message being sent and expected to be present in callback payloads | 25596363\\                                          | 1639561857\\ | 20220227\\ | 25596363 |
| statuses\[X].error.code  | Failure Error code                                                                       | 1001                                                |              |            |          |
| statuses\[X].error.title | Description of error                                                                     | Message specified does not match with any template. |              |            |          |

#### Sample Payload for Message Status Callbacks

```json Successful Delivery Payload
{
"payloadVersion":"0.1",
"statuses": [{
               "msgId": "25596363|1639561857|20220227|25596363", // same as outbound message ID
               "status": "delivered",
               "timestamp": "1647441774", //Event timestamp
               }]
               }
```
```json Failure Delivery Payload
{"payloadVersion":"0.1",
"statuses": [{
               "msgId": "25596363|1639561857|20220227|25596363",
               "status": "failed",
               "timestamp": "1647441774", //Event timestamp
               "error": {
               "code": 1004,
               "title": "Invalid phone number."
               }}]

}
```
```curl Generic Click Callback Payload
{
    "payloadVersion": "0.1",
    "statuses": [
        {
            "msgId": "4930004|1731583253|20241114|4930004",
            "status": "Clicked",
            "ts": 1435322805,
            "url": "www.google.com/19nov",
            "shortUrl": "https://bit.ly/3Oj42219",
            "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.82 Safari/537.36"
        }
    ]
}
```

### Callback Error Codes

<Callout icon="🚧" theme="warn">
  ### Callback Error Codes

  Listed below are the expected callback error codes:

  - 1000 → Invalid credentials
  - 1001  → Invalid template parameters
  - 1002 → Invalid phone number
  - 1003 → The phone number is no longer active
  - 1004 → Too many send requests to phone numbers
  - 1005 → The phone number is temporarily unavailable or not in the provider network
  - 1006 → Phone number is blacklisted
  - 1007 → User device can’t receive the message
  - 1008 → This message is sent outside of the WhatsApp chat window
  - 1009 →  Other
  - 1010 → WhatsApp Message Blocked by Meta
</Callout>

# Creating/Uploading User Base

You can upload a CSV file to upload a set of internal users by going to _Settings_ > _CSV uploads_. The following is the sample CSV format for uploading user data.

| Identity                                              | Name     | Email | Phone              | Gender | MSG-WhatsApp | Upload Name   |
| :---------------------------------------------------- | :------- | :---- | :----------------- | :----- | :----------- | :------------ |
| [johndoe@clevertap.com](mailto:johndoe@clevertap.com) | John Doe |       | +9199\*\*\*\*\*420 | M      | TRUE         | Sample Upload |

## Accepted Message Formats

CleverTap currently has limitations on the types of WhatsApp messages supported on the dashboard. We are working on adding support for the new message types as soon as possible but for the time being, only the following message types are supported.

**Freeform Messages**<br />This message type supports the following format:

- Simple text
- Audio
- Video
- Images
- Document

**Template messages**<br />The elements of the Template message include a header, footer, simple text, and buttons.<br />The header section supports the following formats:

- Text
- Image
- Videos
- Locations
- Audios
- Documents

# FAQs

**Q. My WhatsApp provider has shared the API credentials with me. Can I save the provider in the CleverTap dashboard and start creating WhatsApp campaigns?**

**Ans:** Ensure that your WhatsApp service provider is there in the list of integrated partners. If yes, ensure that you are using the custom API endpoint that your partner has created for CleverTap integration.
