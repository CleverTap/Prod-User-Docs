---
title: Microsoft Azure
excerpt: Understand how to integrate CleverTap dashboard to Microsoft Azure.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Use Microsoft Azure Blob Storage to import data from files in a container that you own and to export CleverTap data to that container. CleverTap authenticates with a SAS token that you generate for the container. This is the only supported authentication method for both import and export. With the integration, you can:

- Import user profiles and events from CSV or Parquet files stored in your Blob Storage container.
- Export profile and event data to your Blob Storage container for analysis in BI tools or storage in a data warehouse.

<Callout icon="📘" theme="info">
  ### Note

  CleverTap supports IP whitelisting for Microsoft Azure connections, either through the _Allowed IP addresses_ field on the SAS token or through the storage account firewall. CleverTap connects from fixed IP ranges, and the ranges for import and export differ. For more information about allowed IP ranges, refer to [FAQs](#faqs).
</Callout>

The setup involves the following five steps:

1. Create Storage Account.
2. Create Container and, for Import, an optional subfolder.
3. Generate SAS Token for Container.
4. Add Container and SAS Token on CleverTap Dashboard.

If you already have a storage account and container, skip to [Generate SAS Token](#generate-sas-token).

<Accordion title="Quick Start Guide for Existing Users">
  If you previously configured an Azure storage account and container and are familiar with the CleverTap dashboard, the setup requires the following details and steps.

  Have the following details ready:

  - The storage account name, which you enter as _Default endpoint_ on the CleverTap dashboard, or a custom domain mapped to your Blob Storage endpoint
  - The container name, which you enter as _Folder path_ on the CleverTap dashboard
  - (Import only, optional) The subfolder path within the container
  - A container-level SAS token, signed with the account key, with the permissions that your connection needs. For more information, refer to [Generate SAS Token](#generate-sas-token)​.
    - Import: **Read** and **List**
    - Export: **Read** and **Write**

  Then configure the connection as follows:

  1. Go to _Settings > Partners_ and select **Microsoft Azure** on the **Integrations** tab.
  2. Select the **Import Connections** or **Export Connections** tab, and then click **Add Microsoft Azure Bucket**.
  3. Enter the _Connection name_, select the _Azure Blob storage endpoint_ (**Default** or **Custom**), enter your storage account name or custom domain, and enter the _Folder path_ (your container name). For an import connection, optionally enter a _Subfolder path_.
  4. Enter the _SAS token_ that you generated for the container.
  5. Click Save to save the connection. For imports, you can test your connection before saving.

  After you save the connection, continue with [Next Steps](#next-steps).
</Accordion>

## Prerequisites for Integration

Before you set up the integration, ensure that the required Azure permissions, settings, and CleverTap access are available.

- An active Azure subscription and permissions to create a storage account and containers in a resource group. The **Contributor** role on the resource group covers these permissions.
- Permission to generate a SAS token signed with the account key. The permission requires `Microsoft.Storage/storageAccounts/listkeys/action`, which the **Contributor**, **Owner**, and **Storage Account Key Operator Service Role** roles include. Without the permission, the portal does not offer **Account key** as a signing method.
- The _Allow storage account key access_ setting enabled on the storage account. Azure enables the setting by default, but an Azure Policy or an administrator may disable it to enforce Microsoft Entra authentication. When the setting is off, Azure does not let you generate or use account-key SAS tokens. For more information, refer to Microsoft's [Prevent Shared Key authorization](https://learn.microsoft.com/azure/storage/common/shared-key-authorization-prevent) documentation.
- A CleverTap account with the Microsoft Azure partner enabled
- A globally unique storage account name and a container name that follow the naming rules in [Create Storage Account](#create-storage-account) and [Create Container](#create-container)
- The CleverTap IP ranges to allow, if your organization restricts access to Blob Storage by source IP. For more information, refer to the [FAQs](#faqs).

### Review Authentication Method

CleverTap authenticates to Azure Blob Storage with a container SAS token, which works for both import and export connections.

| Method                  | Import | Export | What you create on Azure                                                    | Credentials stored in CleverTap | Permissions in the SAS token                                      |
| ----------------------- | ------ | ------ | --------------------------------------------------------------------------- | ------------------------------- | ----------------------------------------------------------------- |
| **Container SAS token** | Yes    | Yes    | A storage account, a container, and a SAS token generated on that container | SAS token                       | Import: **Read** and **List**<br />Export: **Read** and **Write** |

<Callout icon="🚧" theme="warn">
  ### Important

  Sign the SAS token with the **Account key**, not a **User delegation key**. A user delegation SAS expires after a maximum of 7 days, so a connection that uses one stops working within a week.
</Callout>

## Set Up Microsoft Azure for Integration

Setting up Microsoft Azure for the integration involves creating a storage account and a container, optionally creating a folder for import, and generating a SAS token. If you already have a storage account and container, skip to [Generate SAS Token](#generate-sas-token).

### Create Storage Account

The storage account holds your container and provides the Blob Storage endpoint for the CleverTap connection.

1. Log in to the Azure portal, enter _Storage accounts_ in the search bar, and select **Storage accounts**.

2. Click **Create**.


   <Image src="https://files.readme.io/214a3e7-Select_Storage_Account_from_the_left_menu.gif" alt="Select Storage Account from Left Menu" align="center" caption="Select Storage Account" border={true} />


3. On the **Basics** tab, under _Project details_, select your _Subscription_, and select an existing _Resource group_ or click **Create new** to create one.

4. Under _Instance details_, enter a _Storage account name_. You enter this value as the _Default endpoint_ on the CleverTap dashboard.

   <Callout icon="📘" theme="info">
     ### Note

     Storage account names must be 3 to 24 characters, contain only lowercase letters and numbers, and be unique across all of Azure. For more information, refer to Microsoft's [storage account name](https://learn.microsoft.com/azure/storage/common/storage-account-overview#storage-account-name) rules.
   </Callout>

5. Select any _Region_. CleverTap does not require a specific region for the storage account.

6. Keep _Primary service_ as **Azure Blob Storage or Azure Data Lake Storage Gen 2**, keep _Performance_ as **Standard**, and select the _Redundancy_ that your organization requires. The default is sufficient for CleverTap.


   <Image src="https://files.readme.io/9304d54-Enter_Storage_Account_Name.png" alt="Enter Storage Account Name" align="center" caption="Enter Storage Account Name" border={true} />


7. On the **Advanced** tab, under _Security_, keep **Enable storage account key access** selected. You sign the CleverTap SAS token with the account key, and the token stops working if you later disable this setting.

8. On the **Networking** tab, keep _Public network access_ as **Enable from all networks**. If your organization requires **Enable from selected virtual networks and IP addresses**, add the CleverTap IP ranges for your connection type under _Firewall_. For more information, refer to [How do I whitelist CleverTap's IP addresses?](#how-do-i-whitelist-clevertaps-ip-addresses)

9. Keep the default settings on the **Data protection**, **Encryption**, and **Tags** tabs. If your organization requires customer-managed keys for encryption, refer to [Can I use customer-managed keys to encrypt the storage account?](#can-i-use-customer-managed-keys-to-encrypt-the-storage-account) before you select them.

10. Click **Review + create**, and after validation passes, click **Create**.

11. When the deployment completes, click **Go to resource** and note the storage account name.


    <Image src="https://files.readme.io/102207f-Storage_Account_created_successfully.png" alt="Storage Account Created Successfully" align="center" caption="Storage Account Created Successfully" border={true} />


For more information, refer to Microsoft's [Create a storage account](https://learn.microsoft.com/azure/storage/common/storage-account-create) documentation.

### Create Container

CleverTap reads from or writes to a container within your storage account.

1. Open your storage account and, from the left menu, select _Data storage > Containers_.

2. Click **+ Container**.

3. Under _Name_, enter a container name.

4. Keep _Anonymous access level_ as **Private (no anonymous access)**.

5. Click **Create**.


   <Image src="https://files.readme.io/9763f96-Create_Blob_Service_Container.gif" alt="Create a Blob Storage Container" align="center" caption="Create Container" border={true} />


6. Note the container name. You enter it in the _Folder path_ field on the CleverTap dashboard.

   <Callout icon="📘" theme="info">
     ### Note

     Container names must be 3 to 63 characters, contain only lowercase letters, numbers, and hyphens (-), begin with a letter or number, and not contain consecutive hyphens. For more information, refer to Microsoft's [container naming rules](https://learn.microsoft.com/rest/api/storageservices/naming-and-referencing-containers--blobs--and-metadata).
   </Callout>

For more information, refer to Microsoft's [Create a container](https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) documentation.

### Create Folder for Import

For an import connection, you can optionally point CleverTap at a specific folder within the container.

<Callout icon="📘" theme="info">
  ### Note

  For an export connection, you set the folder path when you create the export job, and Blob Storage creates the path when CleverTap writes the first file, so you do not need to create a folder in advance.
</Callout>

Blob Storage folders are virtual: a folder exists only while at least one blob has that folder prefix in its name.

1. Open the container from the _Containers_ list.

2. Click **Upload**.

3. Expand _Advanced_ and, under _Upload to folder_, enter the folder name, for example, `imports`.

4. Select a file to upload, such as your first CSV file, and click **Upload**.

5. Note the folder name. You enter it in the _Subfolder path_ field on the CleverTap dashboard.

If your storage account has _Hierarchical namespace_ enabled (Azure Data Lake Storage Gen2), you can instead click **+ Add Directory** inside the container to create an empty folder. For more information, refer to Microsoft's [Upload a block blob](https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob) documentation.

### Generate SAS Token

A Shared Access Signature (SAS) token grants CleverTap limited, time-bound access to the container without exposing your storage account key. You generate the token on the container so that CleverTap has no access to any other container in the account. For more information, refer to Microsoft's [Grant limited access to Azure Storage resources using shared access signatures](https://learn.microsoft.com/azure/storage/common/storage-sas-overview) documentation.

1. Open your storage account and, from the left menu, select _Data storage > Containers_.

2. On the row for your container, click the ellipsis (...) at the right end and select **Generate SAS**. The _Generate SAS_ pane opens.

3. Enter the details in the following table:


   <Image src="https://files.readme.io/6e76239-Generate_SAS_Token.png" alt="Generate SAS Popup" align="center" caption="Generate SAS" border={true} />


   | Field                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | _Signing method_             | Select **Account key**. Do not select **User delegation key**, because a user delegation SAS expires after a maximum of 7 days.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   | _Signing key_                | Select **Key 1** or **Key 2** and note which key you selected. If you later rotate that key, every SAS token signed with it stops working, and you must regenerate the tokens.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   | _Stored access policy_       | Keep **None** unless your organization uses stored access policies. If you select a policy, the token inherits the permissions and expiry of the policy, so the policy must grant the permissions that the _Permissions_ row lists. A stored access policy lets you revoke the token later without rotating the key.<br />For more information, refer to [Define a stored access policy](https://learn.microsoft.com/en-us/rest/api/storageservices/define-stored-access-policy).                                                                                                                                                                                                |
   | _Permissions_                | Required. Select only the permissions that your connection needs.<br />Import: **Read** and **List**<br />Export: **Read** and **Write**<br />Do not grant **Delete** or any other permission. If you use the same container for both import and export, generate a separate token for each connection.<br />For more information, refer to [Account SAS Permissions by Operation](https://learn.microsoft.com/en-us/rest/api/storageservices/create-account-sas#account-sas-permissions-by-operation).                                                                                                                                                                          |
   | _Start and expiry date/time_ | Leave _Start_ blank, or set it at least 15 minutes in the past, because a start time of "now" causes intermittent failures for the first few minutes due to clock differences between systems.<br />Set _Expiry_ to the longest duration that your organization's policy allows, and record the date, because imports and exports fail once the token expires.<br />If the storage account has a SAS expiration policy, that policy limits the maximum expiry.<br />For more information, refer to [Configure a SAS Expiration Policy](https://learn.microsoft.com/en-us/azure/storage/common/sas-expiration-policy?tabs=azure-portal#how-to-configure-a-sas-expiration-policy). |
   | _Allowed IP address_         | Leave blank unless your organization requires IP restrictions. If you enter a range, enter the CleverTap IP ranges for your connection type. The import and export ranges differ. For more information, refer to [How do I whitelist CleverTap's IP addresses?](#how-do-i-whitelist-clevertaps-ip-addresses)                                                                                                                                                                                                                                                                                                                                                                     |
   | _Allowed protocols_          | Keep **HTTPS only**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

4. Click **Generate SAS token and URL**.

5. Copy the value under _Blob SAS token_, which begins with `?sv=`. You enter this value on the CleverTap dashboard, and you do not need the _Blob SAS URL_.

For more information, refer to Microsoft's [Create a service SAS](https://learn.microsoft.com/rest/api/storageservices/create-service-sas) and [Configure an expiration policy for shared access signatures](https://learn.microsoft.com/azure/storage/common/sas-expiration-policy) documentation.

<Callout icon="📘" theme="info">
  ### Security Best Practice

  Save the SAS token securely. Azure does not display the token again after you leave the pane, so generate a new token if you lose it. Never share the storage account key itself. If you believe a token has leaked, rotate the signing key under _Security + networking > Access keys_, or delete the stored access policy of the token, and then generate a new token.
</Callout>

<Callout icon="🚧" theme="warn">
  ### Account Key Signing Unavailable

  If **Account key** is not offered under _Signing method_, or Azure returns "Key based authentication is not permitted on this storage account," the storage account has **Allow storage account key access** turned off. Ask your Azure administrator to enable the setting under _Settings > Configuration_, or to exempt the storage account from the Azure Policy that disables it. For more information, refer to Microsoft's [Prevent Shared Key authorization](https://learn.microsoft.com/azure/storage/common/shared-key-authorization-prevent) documentation.
</Callout>

## Configure Microsoft Azure in CleverTap

The CleverTap dashboard needs the storage account details and the SAS token to complete the connection.

### Add Container on CleverTap Dashboard

Adding the container registers the endpoint, the container name, the optional subfolder, and the SAS token for the connection.

1. On the CleverTap dashboard, go to _Settings > Partners_ and select **Microsoft Azure** on the **Integrations** tab.

2. Select the connection type:
   - For import, select the **Import Connections** tab.
   - For export, select the **Export Connections** tab.

3. Click **Add Microsoft Azure Bucket**.

4. Under _Bucket Details_, enter the details in the following table:

   | Field                         | Import | Export | Description                                                                                                                                                                                                                                                                                                                  |
   | ----------------------------- | ------ | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | _Connection name_             | Yes    | Yes    | A unique name that identifies this connection in CleverTap, for example, `events-prod-azure`.                                                                                                                                                                                                                                |
   | _Azure Blob storage endpoint_ | Yes    | Yes    | Select **Default** to connect through the standard Blob Storage endpoint of your storage account, or **Custom** to connect through a custom domain that you mapped to it.                                                                                                                                                    |
   | _Default endpoint_            | Yes    | Yes    | Visible when you select **Default**. Enter your storage account name exactly as it appears in the Azure portal, for example, `contosostorage`, not the full endpoint URL.                                                                                                                                                    |
   | _Custom endpoint_             | Yes    | Yes    | Visible when you select **Custom**. Enter the custom domain mapped to your Blob Storage endpoint. The domain must serve HTTPS. For more information, refer to Microsoft's [Map a custom domain to an Azure Blob Storage endpoint](https://learn.microsoft.com/azure/storage/blobs/storage-custom-domain-name) documentation. |
   | _Folder path_                 | Yes    | Yes    | Required. The name of the container. The name must match your container name in Azure exactly, for example, `data`.                                                                                                                                                                                                          |
   | _Subfolder path_              | Yes    | No     | Optional. A folder within the container if your import files are in a subdirectory, for example, `imports`. CleverTap reads only from this path. For export, you set the folder path when you create the export job.                                                                                                         |
   | _Preview_                     | Yes    | Yes    | Displays the resulting path that CleverTap uses. Verify the path before you proceed.                                                                                                                                                                                                                                         |
   | _SAS token_                   | Yes    | Yes    | Required. The _Blob SAS token_ that you copied in [Generate SAS Token](#generate-sas-token), in full, beginning with `?sv=`. Do not paste the _Blob SAS URL_.                                                                                                                                                                |

   <Callout icon="📘" theme="info">
     ### Field Mapping

     The CleverTap dashboard does not have fields labeled "Storage account" or "Container." Enter your storage account name under _Default endpoint_, and enter your container name under _Folder path_, for example, `data`. For import connections, use _Subfolder path_ only if CleverTap should read from a folder nested inside that container.
   </Callout>


   <Image src="https://files.readme.io/435931a76c874f22a948e44cd5f427d9a50bfff980bf02439c967aad283126a1-Azure_Configuration_on_CleverTap.png" align="center" caption="Microsoft Azure Bucket Details" border={true} />


## Verify Integration

The SAS token already carries the permissions that CleverTap needs, so you can verify the connection immediately.

- **Import**: Click **Test Connection**. CleverTap lists the container, and the subfolder if you entered one, using the SAS token. When the test succeeds, click **Save**.
- **Export**: Click **Save**. CleverTap uploads a test file to the container that you specified, and it saves the connection only if the upload succeeds.

If the test or save fails, refer to the [FAQs](#faqs).

## FAQs

### What permissions does CleverTap need?

For import, the SAS token needs **Read** (to read file contents) and **List** (to list files in the container and subfolder). For export, the SAS token needs **Read** and **Write** (to upload files). CleverTap never needs **Delete**, and it never needs the storage account key itself.

### Can I use one connection for both import and export?

No. You configure import and export connections separately under _Import Connections_ and _Export Connections_. You can point both connections at the same container, and you generate a separate SAS token for each connection with only the permissions that the connection needs.

### Does the storage account have to be in a specific region?

No. Any Azure region works.

### Can I use customer-managed keys to encrypt the storage account?

You can configure the storage account to encrypt data with a customer-managed key that you store in Azure Key Vault. You set the key on the storage account under the _Encryption_ settings. The key vault needs soft delete and purge protection enabled, and the managed identity that the storage account uses needs the **Key Vault Crypto Service Encryption User** role on the key vault. For more information, refer to Microsoft's [Configure customer-managed keys in the same tenant for an existing storage account](https://learn.microsoft.com/azure/storage/common/customer-managed-keys-configure-key-vault) documentation.

### How can I limit which files CleverTap reads from my container?

Use the _Subfolder path_ field on the import connection to point CleverTap to a specific folder within your container. CleverTap reads only from that path. Because the SAS token covers only the container, CleverTap has no access to other containers in the storage account.

### What happens when my SAS token expires?

Imports and exports that use the connection fail, and CleverTap emails the export creator with the message "Azure SAS token is expired." An export remains in the pending or running state. Generate a new SAS token in Azure, go to _Settings > Partners > Microsoft Azure_, edit the connection on the relevant tab, and replace the _SAS token_ value. For import, click **Test Connection** and then **Save**. For export, click **Save**. Record the expiry date when you generate a token so that you can replace the token before it expires.

### How do I revoke CleverTap's access?

Rotate the storage account key that signed the token under _Security + networking > Access keys_, or, if you generated the token with a stored access policy, delete that policy. Rotating the key also invalidates every other SAS token signed with it.

### How do I whitelist CleverTap's IP addresses?

CleverTap connects to Blob Storage from fixed IP ranges. You can restrict access to those ranges in two places: the _Allowed IP addresses_ field when you generate the SAS token, and the storage account firewall under _Security + networking > Networking_ when you set _Public network access_ to **Enable from selected virtual networks and IP addresses**. In either case, allow the ranges for the connection type that you use. The import and export ranges differ:

- **Export**: Refer to [CleverTap IP Ranges](https://developer.clevertap.com/docs/clevertap-ip-ranges#ip-ranges).
- **Import**: Refer to [How can I whitelist IPs for CleverTap integration?](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration) in the Import FAQs.

For the storage account firewall, refer to Microsoft's [Configure Azure Storage firewalls and virtual networks](https://learn.microsoft.com/azure/storage/common/storage-network-security) documentation.

### Can I use a storage account with hierarchical namespace (Azure Data Lake Storage Gen2) enabled?

CleverTap connects through the Blob Storage endpoint, which remains available on storage accounts with hierarchical namespace enabled, and container SAS tokens work the same way. Run a one-time export or a test import against the container, and confirm the result before you schedule recurring jobs.

### Why is Account key unavailable under Signing method?

The storage account has **Allow storage account key access** turned off, or you lack the `listkeys` permission. Ask your Azure administrator to enable the setting under _Settings > Configuration_, or to grant you the **Storage Account Key Operator Service Role**. For more information, refer to [Generate SAS Token](#generate-sas-token).

### Why does Test Connection fail for an import connection?

The _Default endpoint_ contains a URL instead of the account name, the _Folder path_ does not match the container name, the _Subfolder path_ does not exist, or the SAS token lacks **Read** or **List**, has expired, or you pasted it incompletely. Confirm that the _Default endpoint_ contains only the storage account name, confirm that the _Folder path_ matches the container name exactly, confirm that the subfolder contains at least one file, and confirm that the SAS token begins with `?sv=`, includes `sp=rl` (or a superset), and has an `se=` expiry in the future.

### Why does Save fail for an export connection when CleverTap cannot upload the test file?

The SAS token lacks **Write** or **Read**, has expired or is not yet valid, or the storage account firewall or the _Allowed IP addresses_ field of the token blocks the export IP ranges of CleverTap. Confirm that the token includes `sp=rw` (or a superset), confirm its `st=` and `se=` values, and confirm that your organization allows the export IP ranges if it restricts access by IP. For more information, refer to [How do I whitelist CleverTap's IP addresses?](#how-do-i-whitelist-clevertaps-ip-addresses)

### Why does an export stop with an "Azure SAS token is not yet valid" email?

The start time of the token is in the future, or you set it to the current time and clock skew between systems has not yet elapsed. Generate a new SAS token with _Start_ blank or at least 15 minutes in the past, and then update the connection.

### Why do imports or exports fail after an administrator rotates the storage account keys?

Rotating a storage account key invalidates every SAS token signed with that key. Generate a new SAS token signed with the current key, and update the connection. Before you rotate keys in the future, generate the replacement token with the other key and update the connection first.

### Why does a connection with a Custom endpoint fail with a certificate or connection error?

Azure Blob Storage does not serve HTTPS on a custom domain by itself, so the domain needs Azure Front Door or Azure CDN with a certificate. Serve the custom domain over HTTPS through Azure Front Door or Azure CDN, or switch the connection to the **Default** endpoint.

### Why does Azure reject requests although the SAS token is valid?

The storage account restricts _Public network access_ and the firewall omits the CleverTap IP ranges, or the _Allowed IP addresses_ field of the token omits them. Add the CleverTap IP ranges for the connection type under _Security + networking > Networking > Firewall_, or regenerate the token with the ranges under _Allowed IP addresses_. For more information, refer to [How do I whitelist CleverTap's IP addresses?](#how-do-i-whitelist-clevertaps-ip-addresses)

### Why does an import run but read no files?

The _Subfolder path_ points to a folder that contains no CSV or Parquet files, or the files are in a different folder. Verify that the path under _Preview_ matches the location where your pipeline writes the files. Blob Storage folders are virtual, so a folder with no files does not exist.

## Next Steps

After you configure the connection, you can create imports and exports that use it.

- Create an import that reads from this connection. For more information, refer to [Create Import](doc:create-file-based-import), [Map Data for Import](doc:map-data-for-file-based-import), [Schedule Import](doc:schedule-file-based-import), and [Import Listing and Stats](doc:import-listing-and-stats-for-file-based-import).
- Create an export that writes to this connection. For more information, refer to [Cloud Storage](doc:cloud-storage), [Event Exports](doc:event-exports), or [Profile Exports](doc:profile-exports).