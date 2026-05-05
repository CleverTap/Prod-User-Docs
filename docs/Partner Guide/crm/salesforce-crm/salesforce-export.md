---
title: Salesforce Export
excerpt: >-
  Learn how to push engagement data, campaign responses, and survey results from
  CleverTap into Salesforce CRM in real time using OAuth 2.0-secured webhooks.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Integrate CleverTap with Salesforce CRM to export user profile data, event properties, and campaign responses in real time via a secure webhook. The webhook uses the OAuth 2.0 Client Credentials flow to authenticate with Salesforce and delivers data directly to a custom Apex REST endpoint, enabling CRM enrichment and workflow automation from CleverTap campaigns.

The integration is divided into two parts:

1. **Salesforce Dashboard Setup**: Create the External Client App, custom object, and Apex REST class.
2. **CleverTap Dashboard Setup**: Configure the OAuth 2.0 webhook provider and launch a webhook campaign.

# Use Cases

* **Log NPS and Survey Responses**

  Send Net Promoter Score feedback and in-app survey responses from CleverTap into Salesforce for customer success tracking and case creation.
* **Send Leads from Campaigns**

  Export lead details captured through CleverTap forms or campaigns into Salesforce for timely follow-up by your sales team.
* **Sync Event and Product Feedback**

  Capture user responses to webinars, product launches, or promotional events, and send them to Salesforce to trigger workflows or update lifecycle stages.
* **Enrich CRM with Behavioral Data**

  Add product usage metrics, feature interaction logs, and event-level insights to Salesforce user profiles for segmentation and targeted outreach.

# Prerequisites

Before configuring the integration, ensure you have the following:

### Salesforce

* A valid Salesforce account on Enterprise, Unlimited, or Performance edition with API access enabled.
* Permission to access Object Manager, App Manager, Flow Builder, and Apex Classes.
* Permission to [create an External Client App in Salesforce](https://help.salesforce.com/s/articleView?id=xcloud.create_a_local_external_client_app.htm\&type=5).
* Familiarity with the [OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm).

### CleverTap

Access to add Webhook providers and create campaigns on the CleverTap dashboard

<Callout icon="📘" theme="info">
  #### Connected Apps Retiring in Salesforce

  Salesforce is retiring Connected Apps in favor of External Client Apps.
</Callout>

# Set Up Salesforce Dashboard

Configure Salesforce to receive data from CleverTap by performing the following three steps in order:

1. [Create External Client App](doc:salesforce-export#create-external-client-app).
2. [Create Custom Object](doc:salesforce-export#create-custom-object).
3. [Create Apex REST Class](doc:salesforce-export#create-apex-rest-class).

## Create External Client App

The External Client App generates the OAuth Client ID and Client Secret that CleverTap uses to obtain an OAuth access token as follows:

1. From the Salesforce dashboard, open _Setup_.
2. Go to _Platform Tools_ > _Apps_ > _External Client Apps_ > _Settings_.
3. Toggle ON the _Allow access to External Client App consumer secrets via REST API_ and _Allow creation of connected apps_ options. 

   <Image align="center" border={true} caption="Create External Client App" src="https://files.readme.io/5b0f4947967e9da2b5045a7999778a1e743dead6a3e3f73d9e21530701eb7ad1-Create_External_Client_App.webp" />
4. Go to External Client App Manager and click New External Client App.
   1. Enter the following details:

      <Image align="center" border={true} caption="Basic Information - External Client App" src="https://files.readme.io/579c668b82880ea87d2563eff5ce1166139d2aafef3a9509410b3d9a3e0013a5-Basic_Information_-_External_Client_App.webp" />

      <Image align="center" border={true} caption="App Settings & OAuth Scopes - External Client App" src="https://files.readme.io/037264b4a6156f8cec0eea5e7e1c096c704336e687808d226105d6014a0799ac-App_Settings__OAuth_Scopes_-_External_Client_App.png" />

      <Image align="center" border={true} caption="Flow Settings & Security - External Client App" src="https://files.readme.io/995c6577c748b4c454998ba7f1a3152ca26673a9c955c390368e11bfece8de97-Flow_Enablement__Security_-_External_Client_App.png" />

      <Table align={["left","left","left"]}>
        <thead>
          <tr>
            <th>
              Section
            </th>

            <th>
              Field
            </th>

            <th>
              Description
            </th>
          </tr>
        </thead>

        <tbody>
          <tr>
            <td>
              Basic Information
            </td>

            <td>
              External Client App Name
            </td>

            <td>
              Enter a descriptive name for the app (for example, `CleverTap Exports`).
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              API Name
            </td>

            <td>
              Use the auto-generated value or specify a custom name if required.
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              Contact Email
            </td>

            <td>
              Enter a valid email address for integration-related notifications.
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              Distribution State
            </td>

            <td>
              Keep it Local.
            </td>
          </tr>

          <tr>
            <td>
              API (Enable OAuth Settings)
            </td>

            <td>
              Enable OAuth
            </td>

            <td>
              Select this option to configure OAuth 2.0 authentication for the app.
            </td>
          </tr>

          <tr>
            <td>
              App Settings
            </td>

            <td>
              Callback URL
            </td>

            <td>
              Use [https://\<instanceURL>/services/oauth2/callback](https://\<instanceURL>/services/oauth2/callback) as a placeholder

              For instanceURL, look at your browser URL when logged into Salesforce. It will look like [https://\<your-domain>.my.salesforce.com/](https://\<your-domain>.my.salesforce.com/).Your instance URL is: [https://\<your-domain>.my.salesforce.com](https://\<your-domain>.my.salesforce.com).

              So the callback endpoint will be: [https://\<your-domain>.my.salesforce.com/services/oauth2/callback](https://\<your-domain>.my.salesforce.com/services/oauth2/callback)
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              OAuth Scopes
            </td>

            <td>
              Select _Manage user data via APIs (api)_ and click **Add** to authorize API permissions. It grants access to all REST API endpoints, including your custom class.
            </td>
          </tr>

          <tr>
            <td>
              Flow Enablement
            </td>

            <td>
              Enable Client Credentials Flow
            </td>

            <td>
              Select this option to allow OAuth token generation via client credentials.
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              Enable Token Exchange Flow
            </td>

            <td>
              Select this option to support token exchange as part of the OAuth flow.
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              Require a secret for Token Exchange Flow
            </td>

            <td>
              Enable to ensure the client secret is required for token exchange
            </td>
          </tr>

          <tr>
            <td>
              Security
            </td>

            <td>
              Require a secret for Web Server Flow
            </td>

            <td>
              Enable secure Web Server OAuth flow with a client secret.
            </td>
          </tr>

          <tr>
            <td>

            </td>

            <td>
              Require a secret for the Refresh Token Flow
            </td>

            <td>
              Enforce the use of client secret when refreshing tokens.
            </td>
          </tr>

          <tr>
            <td>
              Other Options
            </td>

            <td>
              All remaining settings, such as digital signatures, refresh token rotation, Issue JSON Web Token (JWT)-based access tokens for named users, and so on
            </td>

            <td>
              Leave these disabled unless specifically required by your Salesforce org.
            </td>
          </tr>
        </tbody>
      </Table>
5. Save the app, then open _Policies_ and configure the following:

   <Image align="center" border={true} caption="Configure OAuth Policies & App Authorization" src="https://files.readme.io/084c8f1d93cbab1a3abb330e2219e1432290bc6ae32de5dfbfd4fd5ee65dbade-Configure_OAuth_Policies__App_Authorization.png" />

   * **OAuth Policies**
     * Select the Enable _Client Credentials Flow_ option.
     * Under _Run As_, enter the username of the Salesforce user whose permissions will be used when CleverTap writes data. This user must have API access and write permission on the target custom object.
     * Select the Enable _Token Exchange Flow_ option.
   * **App Authorization**
     * Refresh Token Policy: Select Expire refresh token after a specific time and set validity to 2 hours.
     * IP Relaxation: Set to Relax IP restrictions.
6. Navigate back to _Settings_ > _OAuth Settings_ and click **Consumer Key Secret** to retrieve your Client ID and Client Secret. Copy and save them securely, as you will need them while configuring the webhook in CleverTap.

   <Image align="center" border={true} caption="Copy and Save Client ID and Client Secret" src="https://files.readme.io/51f2edb1036c86ad0498d887105c7e655e32adaf2be7ee7d0504a8b0cb46eedb-Copy_and_Save_Client_ID_and_Client_Secret.png" />

<Callout icon="📘" theme="info">
  #### Note

  External Client Apps do not support the legacy `grant_type=password` flow. For Apex REST API access, the `api` scope alone is sufficient.
</Callout>

## Create Custom Object

Create a custom object in Salesforce to store the data CleverTap will send. The example below creates an object for NPS feedback; adapt field names to your use case.

1. Go to _Setup_ > _Object Manager_.
2. Click **Create** and select Custom Object.
3. (Optional) Enable _Launch New Custom Tab Wizard after saving this custom object_ to create a tab for viewing records.
4. Click **Save**.
5. Copy the full **API Name** from the object details page, as you will need it when writing the Apex class. In a namespaced org, this will include the `CleverTap__` prefix (for example, `CleverTap__CleverTap_NPS__c`).
6. Copy **API Name** (including the `CleverTap__ prefix and __c` suffix) for each field as you will reference these in the Apex class.
7. Under _Fields & Relationships_, click **+ New Field** to add relevant data fields. For example,
   * Field Label: `userId`, Data Type: Text
   * Field Label: `npsScore`, Data Type: Number
   * Field Label: `timestamp`, Data Type: Date/Time
8. Copy the Field Names, as we will need them while creating the Apex class.

   <Image align="center" border={true} caption="Add New Field - Fields & Relationships" src="https://files.readme.io/9de60e1b0cf6e88b67f4d35158f1f81617662443bb92de8aec9042cb6ac8cfee-Add_New_Field_-_Fields__Relationships.png" />

<Callout icon="📘" theme="info">
  #### Note

  After creating the object, ensure the appropriate [permissions](https://help.salesforce.com/s/articleView?id=ind.modeler_vscode_configure_permissions_on_display_card.htm) and [tab visibility](https://help.salesforce.com/s/articleView?id=ind.modeler_vscode_set_tab_page.htm) are configured for the profiles that will access it.
</Callout>

## Create Apex REST Class

The Apex REST class exposes a POST endpoint that receives the CleverTap webhook payload and writes it to the custom object. Custom Apex classes provide full control over payload parsing, validation, and transformation before storage. To create an Apex REST class, perform the following steps:

1. Go to _Setup_ > _Apex Classes_ and click **New**.
2. Paste the following example code (adapt field names to match your custom object):
   ```java
   @RestResource(urlMapping='/InsertNPSFeedback')
   global with sharing class InsertNPSFeedback {

       global class NPSRequest {
           public String userId;
           public Integer npsScore;
           public String timestamp;
       }

       @HttpPost
       global static String doPost() {
           try {
               NPSRequest input = (NPSRequest) JSON.deserialize(
                   RestContext.request.requestBody.toString(), NPSRequest.class
               );

               // CleverTap__CleverTap_NPS__c is the API name from the custom object.
               // Field API names (CleverTap__userId__c, etc.) include the namespace prefix.
               CleverTap__CleverTap_NPS__c record = new CleverTap__CleverTap_NPS__c(
                   Name = 'NPS-' + input.userId,
                   CleverTap__userId__c = input.userId,
                   CleverTap__npsScore__c = input.npsScore,
                   CleverTap__timestamp__c = String.isNotBlank(input.timestamp)
                       ? DateTime.valueOf(input.timestamp.replace('T', ' '))
                       : DateTime.now()
               );

               insert record;
               return 'Success';
           } catch (Exception e) {
               return 'Error: ' + e.getMessage();
           }
       }
   }
   ```
   <br />
3. Click **Save** to compile and activate the class.

   After saving, note the URL mapping from the `@RestResource(urlMapping='/...')` annotation and your org's namespace prefix. In this example, the URL mapping is `/InsertNPSFeedback`, and the namespace is `CleverTap`, producing the final destination URL:

   ```http
   https://<your-domain>.my.salesforce.com/services/apexrest/CleverTap/InsertNPSFeedback
   ```

   <br />

<Callout icon="🚧" theme="warn">
  #### Important

  The namespace prefix must be included in the URL path when calling an Apex REST class deployed as part of a managed package. Missing the namespace will result in a 404 Not Found response.
</Callout>

# Set Up CleverTap Dashboard

Configure the webhook provider and campaign in CleverTap:

1. [Configure OAuth 2.0 Webhook Provider](doc:salesforce-export#configure-oauth-20-webhook-provider).
2. [Create Webhook Campaign](doc:salesforce-export#create-webhook-campaign).

## Configure OAuth 2.0 Webhook Provider

To configure OAuth 2.0 Webhook Provider, perform the following steps:

1. From the CleverTap dashboard, go to _Settings_ > _Channels_ > _Webhook_.
2. Click **+ Add Webhook**.
3. Enter a name for your webhook (for example, NPS data to Salesforce CRM).
4. Set the HTTP Method to POST.
5. Enter the following endpoint in the Destination URL field and replace `your-domain`, `namespace_prefix`, and `InsertNPSFeedback` based on what you received while creating a Custom Apex class:
   ```http
   https://<your-domain>.my.salesforce.com/services/apexrest/namespace_prefix/InsertNPSFeedback
   ```
6. Under Authentication Type, select _OAuth 2.0_ from the dropdown.
7. Under Grant Type, select _Client Credentials_.
8. Enter the Client ID and Client Secret received under the [Create an External Client App](https://wizrocket.atlassian.net/wiki/spaces/PM/pages/edit-v2/6630211592#Create-an-External-Client-App) section.
9. In the Access Token URL, enter the following URL and replace `your-domain` with the actual value:
   <br />
   ```http
   https://<your-domain>.my.salesforce.com/services/oauth2/token
   ```
10. Set _Client Authentication type_ as _Send bearer authentication in header_.
11. Click **Generate Token**. CleverTap requests a new access token from Salesforce using the configured values. If the token is returned successfully, proceed to the mapping step.

    <Image align="center" border={true} caption="Create Webhook" src="https://files.readme.io/10ecce4b37c553d1c0a6944d52f50ba66f239927273529807ceca94b7e100374-Create_Webhook_Template.png" width="65% " />

    1. After successful token generation, map the returned _Access Token_ and _Expiry_ fields, as shown below, to finalize the configuration, then click **Save**.

       <Image align="center" border={true} caption="Generate Token Response" src="https://files.readme.io/10bee5a2efc3735f836a0e22a55c8d1364d86949e7c527ca1bae6d685a4e0a18-Generated_Token_Response.png" width="75% " />

       | Key               | Value        |
       | :---------------- | :----------- |
       | Access Token      | access_token |
       | Expiry            | issued_at    |
       | Expiry Unity Time | Unix Epoch   |

<Callout icon="📘" theme="info">
  #### Note

  CleverTap automatically refreshes the access token before it expires using the stored Client ID and Client Secret. No manual token management is required.
</Callout>

## Create Webhook Campaign

Configure a campaign that sends user-specific data to Salesforce through the webhook provider.

1. Go to Campaigns and click **+ Campaign**.
2. Select _Webhook_ as the messaging channel.
3. Define your audience (segment, event trigger, journey entry, or one-time audience) under the _Who_ section.
4. In the _When_ step, configure the trigger or schedule for the campaign.
5. Under the What section:

   1. Select your Salesforce webhook (for example, **NPS data to Salesforce CRM**) as the provider.
   2. Under Webhook Content, set the format to JSON.
   3. Select Custom Body and define the request payload to match the structure expected by your Apex REST class. Use the `{{}}` and `@` buttons (or manually type `{{ }}`) to insert dynamic profile fields and event properties.

   ```javascript
   {
     "userId": "{{ Profile.Identity | default: \"0\" }}",
     "npsScore": {{ Event["User Rating"] | default: "0" }}
   }
   ```

   <Image align="center" border={true} caption="Example Payload" src="https://files.readme.io/2ececaede10ffa1c35ac055d3446f06e0da551d3a0dd97f3ce3e1e117f4af96d-Example_Payload.png" width="75% " />

   <br />
6. Click **Preview** to test the payload against sample user data and then click **Publish**.

# Verify Integration

After the campaign is published and qualifying users are processed, verify that data is reaching Salesforce:

1. In Salesforce, go to the _CleverTap NPS_ tab (or whichever custom object you configured).
2. Confirm that new records are being created with the expected field values.
3. Click any record to verify that field values match the payload sent by CleverTap.

If records are not appearing, refer to Troubleshooting.

# Troubleshooting

| Issue                                         | Cause                                                                                              | Resolution                                                                                                                                                          |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Token generation fails with "invalid_client"  | Client ID or Client Secret is incorrect, or the External Client App has not been authorized.       | Regenerate Consumer Key and Secret from the External Client App. Ensure that a Run As user is set under _Policies_ > _OAuth Policies_.                              |
| Token generation fails with "no valid scopes" | OAuth scopes are missing, or the Run As user is not configured.                                    | Add the **Manage user data via APIs (api)** scope and ensure that a Run As user is configured in the Client Credentials Flow policy.                                |
| Webhook returns 404 Not Found                 | Namespace prefix missing from the destination URL.                                                 | Ensure the URL includes the CleverTap namespace: `/services/apexrest/CleverTap/InsertNPSFeedback`.                                                                  |
| Webhook returns 401 Unauthorized              | Access token expired, or Run As user lacks permissions.                                            | Regenerate the token in CleverTap. Ensure that a Run As user has API access and write permission on the target custom object.                                       |
| Webhook returns 500 error                     | Apex class is throwing an exception (for example, invalid field reference or field type mismatch). | Check **Setup > Environments > Logs > Debug Logs** for the Run As user. Verify that field API names and data types match between the payload and the custom object. |
| Records are not appearing in Salesforce       | Apex class catches the exception and returns `Error: ...` as a 200 response.                       | Open the campaign delivery report in CleverTap and inspect the response body for error messages.                                                                    |
| `grant_type=password` does not work           | External Client Apps do not support the legacy password grant.                                     | Use the Client Credentials flow as documented above.                                                                                                                |

# FAQs

### How often does CleverTap refresh the OAuth token?

CleverTap automatically refreshes the access token before it expires using the Client ID and Client Secret stored with the webhook provider. The refresh happens transparently; no manual intervention is required.

### Can I route data to multiple custom objects from one CleverTap account?

Yes. Create a separate Apex REST class and webhook provider for each custom object. Each webhook can be used in separate campaigns. Alternatively, create a single Apex REST class that inspects a payload field (such as `recordType`) and inserts into different objects based on the value.

### Does the webhook retry on failure?

Yes. CleverTap automatically retries failed webhook deliveries with exponential backoff. Persistent failures are logged in the campaign delivery report and the webhook error logs.

### What happens if the Salesforce org is down?

Failed requests are retried by CleverTap. If retries are exhausted, the delivery is marked as failed in the campaign report. No user data is lost in CleverTap itself; the source record remains available for subsequent campaigns.

<br />
