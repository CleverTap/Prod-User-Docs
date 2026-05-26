---
title: Microsoft Fabric
excerpt: >-
  Learn how configuring Microsoft Fabric enables data sync for personalized
  engagement and growth.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Configuring Microsoft Fabric with CleverTap enables seamless data import, ensuring synchronization and access to relevant information for analysis, personalized engagement, and data-driven growth.

# Quick Start Guide for Existing Users

<Accordion title="Expand for quick setup if you have previously configured a Microsoft Fabric workspace and are familiar with the CleverTap dashboard. If you are setting up Microsoft Fabric for the first time, skip to Prerequisites for Integration below.">
  ## Prerequisites

  Before you begin, ensure you have the following details:

  * Connection Nickname
  * Host (SQL Connection String Endpoint)
  * Port (default: `1433`)
  * Client ID
  * Tenant ID
  * Client Secret
  * Database
  * Schema (optional): If not specified, the `dbo` schema is used by default.

  ## Configure Microsoft Fabric Credentials in CleverTap

  To set up the Microsoft Fabric credentials in CleverTap, perform the following steps:

  1. Go to *CleverTap Dashboard* > *Settings* > *Partners* > *Microsoft Fabric*.
  2. Enter the following details: **Connection Nickname**, **Host**, **Port**, **Client ID**, **Tenant ID**, **Client Secret**, **Database**, and **Schema**.
  3. Click **Test Connection** and then **Save**.

  After setting up the configuration, you can [import](doc:data-warehouse-import#quick-start-guide-for-data-warehouse-import) data from Microsoft Fabric into CleverTap.
</Accordion>

# Prerequisites for Integration

If you are setting up Microsoft Fabric for the first time, ensure you have the following before proceeding with the CleverTap configuration:

* **CleverTap Access** to configure Microsoft Fabric.
* **Microsoft Fabric Workspace Details**:
  * An active Azure account with access to the Microsoft Fabric portal.
  * A provisioned Fabric Warehouse or Lakehouse SQL analytics endpoint.
  * The workspace must be publicly accessible or have appropriate network configurations to allow CleverTap to connect.
* **Microsoft Entra ID (Azure AD) Credentials**:
  * Use a dedicated Microsoft Entra app registration for CleverTap, grant least privilege, and set an expiry/rotation policy for the client secret.
  * Configure the Microsoft Entra app registration as a service principal.
  * The service principal, associated with the Client ID, must have at a minimum:
    * Membership in a Fabric Workspace with a Contributor (or higher) role
    * `CONNECT`privilege on the target database
    * `SELECT` permission on tables you plan to import.
  * Authentication Method: Client ID, Tenant ID, and Client Secret.

<Callout icon="📘" theme="info">
  #### IP Whitelisting

  Ensure CleverTap IP addresses are added to your Redshift cluster's security group inbound rules. To access the list of IPs to whitelist, refer to [CleverTap IP Ranges for Import](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration).
</Callout>

# Set Up Microsoft Fabric for Integration

You can set up Microsoft Fabric using one of the following ways:

* For new users who need to provision Fabric resources from scratch: [Create New Microsoft Fabric Setup](doc:microsoft-fabric#create-new-microsoft-fabric-setup)
* For users who already have configured resources in Microsoft Fabric: [Use Existing Microsoft Fabric Credentials](doc:microsoft-fabric#use-existing-microsoft-fabric-credentials).

## Create New Microsoft Fabric Setup

If you do not already have a Fabric Warehouse or Lakehouse, Microsoft Entra App Registration, and Schema configured, you must create them before proceeding. These components are required to ensure CleverTap can securely access, store, and process your data.

To create each resource, perform the following steps:

1. [Create Warehouse](doc:microsoft-fabric#create-warehouse)
2. [Register App in Microsoft Entra ID](doc:microsoft-fabric#register-app-in-microsoft-entra-id)
3. [Create Client Secret](doc:microsoft-fabric#create-client-secret)
4. [Create Schema (Optional)](doc:microsoft-fabric#create-schema-optional)
5. [Configure Permissions](doc:microsoft-fabric#configure-permissions)

### Create Warehouse

To store data for CleverTap integration, you first need to create a Fabric Warehouse. CleverTap reads data through the Warehouse's SQL analytics endpoint. Follow these steps:

<Callout icon="📘" theme="info">
  #### Prerequisite

  Creating a Warehouse requires access to a Microsoft Fabric workspace with a Fabric capacity (F64 or higher) or a Power BI Premium capacity (P1 or higher). Contact your Fabric administrator if you do not have this access.
</Callout>

1. Log in to the [Microsoft Fabric portal](https://app.fabric.microsoft.com).
2. Navigate to your target **Workspace** from the left sidebar.
3. Click **+ New Item** and select **Warehouse** under the _Data Warehouse_ section.
4. Enter a descriptive _Name_ (for example, `clevertap_warehouse`). This name will be pasted in the _Database_ field on the CleverTap dashboard.
5. Click **Create**.

To obtain the **Host** value:

1. In your Workspace, locate the Warehouse you just created.
2. Click the three dots (**…**) next to the Warehouse name and select **Copy SQL connection string**.
3. The connection string contains the Host value in the following format:

```
abc1def2ghij3klmn.datawarehouse.fabric.microsoft.com,1433
```

Copy only the server name portion (without the port number or protocol) as shown below:

```
abc1def2ghij3klmn.datawarehouse.fabric.microsoft.com
```

You will need this when configuring CleverTap.

<Callout icon="📘" theme="info">
  #### Note

  You can also use a Lakehouse SQL analytics endpoint instead of a Warehouse. Every Lakehouse in Fabric automatically provisions a SQL analytics endpoint. To find its connection string, select the Lakehouse SQL analytics endpoint item in your workspace and navigate to _Settings_ > _SQL endpoint_.
</Callout>

### Register App in Microsoft Entra ID

To manage access securely, create a dedicated app registration in Microsoft Entra ID (formerly Azure Active Directory). This provides the Client ID and Tenant ID that CleverTap uses to authenticate via service principal.

To register an app, perform the following steps:

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Search for and select **Microsoft Entra ID** from the top search bar.
3. In the left menu, select **App registrations**.
4. Click **+ New registration** at the top of the page.
5. Configure the registration:
   * **Name**: Enter a descriptive name (for example, `CleverTap Fabric Integration`).
   * **Supported account types**: Select **Accounts in this organizational directory only (Single tenant)**.
   * **Redirect URI**: Leave blank (not required for this integration).
6. Click **Register**.
7. On the app's **Overview** page, copy and securely store the following values:
   * **Application (client) ID**: The **Client ID** you will enter in CleverTap.
   * **Directory (tenant) ID**: The **Tenant ID** you will enter in CleverTap.

### Create Client Secret

After registering the app, generate a client secret that CleverTap will use to authenticate. To generate a client secret, perform the following steps:

1. In the Azure portal, navigate to your app registration (_Microsoft Entra ID_ > _App registrations_ > _your app_).
2. In the left menu, select **Certificates & secrets**.
3. Under the **Client secrets** tab, click **+ New client secret**.
4. Enter a **Description** (for example, `CleverTap Integration`) to identify the secret.
5. Set the **Expires** duration. For production integrations, a minimum of 6 months is recommended.
6. Click **Add**.
7. Copy the **Value** of the client secret immediately and store it securely. The secret value is displayed only once.

<Callout icon="⚠️" theme="warning">
  #### Secret Expiration

  Client secrets expire based on the duration you set during creation. When a secret expires, the CleverTap connection will fail and imports will stop. Monitor secret expiration dates and regenerate secrets before they expire.
</Callout>

### Create Schema (Optional)

Microsoft Fabric Warehouses include a default `dbo` schema. If you want to organize CleverTap-related tables under a separate schema, you can create one. To do so, perform the following steps:

1. Open your Warehouse in the Microsoft Fabric portal.
2. Click **New SQL query** from the top toolbar.
3. Run the following SQL command to create a schema:

```sql
-- Create a new schema for CleverTap data
CREATE SCHEMA IF NOT EXISTS clevertap_schema;

-- Verify schema creation
SELECT name FROM sys.schemas ORDER BY name;
```

<Callout icon="📘" theme="info">
  #### Default Schema

  If you do not create a custom schema, CleverTap will read from the default `dbo` schema. Specify the schema name during the CleverTap connection setup.
</Callout>

### Configure Permissions

To ensure the service principal (app registration) can access your Fabric data, you must grant the required permissions. This step is essential for CleverTap to read data from your Microsoft Fabric workspace.

**Step 1: Enable Service Principals in Fabric Admin Portal**

1. Sign in to the [Fabric Admin portal](https://app.fabric.microsoft.com/admin-portal).
2. Navigate to **Tenant settings**.
3. Locate **Service principals can use Fabric APIs** and enable it for the security group containing your service principal.
4. Ensure **Users can access data stored in OneLake with apps external to Fabric** is also enabled under **OneLake settings**.

**Step 2: Add Service Principal to Workspace**

1. In the Microsoft Fabric portal, navigate to your target Workspace.
2. Click **Manage access**.
3. Click **+ Add people or groups**.
4. Search for your app registration name (for example, `CleverTap Fabric Integration`).
5. Assign the **Contributor** role (minimum required for data read access).
6. Click **Add**.

**Step 3: Grant Database-Level Permissions (if required)**

If granular table-level permissions are needed, run the following SQL commands in your Warehouse:

```sql
-- Grant CONNECT access to the service principal
GRANT CONNECT TO [<service_principal_name>];

-- Grant SELECT access on a specific schema
GRANT SELECT ON SCHEMA::dbo TO [<service_principal_name>];
```

<Callout icon="📘" theme="info">
  #### Granular Table Permissions

  If you prefer to grant access to specific tables rather than the entire schema, use the following command instead:

  ```sql
  GRANT SELECT ON [dbo].[table_name] TO [<service_principal_name>];
  ```

  Repeat for each table that CleverTap needs to access.
</Callout>

## Use Existing Microsoft Fabric Credentials

If you already have Microsoft Fabric set up, perform the following steps to find each detail in the Azure portal and Fabric portal.

* [Obtain the Host (SQL Connection String Endpoint)](doc:microsoft-fabric#obtain-the-host-sql-connection-string-endpoint)
* [Find Existing Port](doc:microsoft-fabric#find-existing-port)
* [Find Client ID and Tenant ID](doc:microsoft-fabric#find-client-id-and-tenant-id)
* [Create or Retrieve a Client Secret](doc:microsoft-fabric#create-or-retrieve-a-client-secret)
* [Find Existing Database Name](doc:microsoft-fabric#find-existing-database-name)
* [Find Existing Schema](doc:microsoft-fabric#find-existing-schema)
* [Verify Existing Permissions](doc:microsoft-fabric#verify-existing-permissions)

### Obtain the Host (SQL Connection String Endpoint)

The Host is the SQL connection string endpoint that CleverTap uses to connect to your Microsoft Fabric instance. To locate the endpoint, perform the following steps:

1. In the [Microsoft Fabric portal](https://app.fabric.microsoft.com), navigate to your Workspace.
2. Locate the target Warehouse or Lakehouse SQL analytics endpoint in the item list.
3. Click the three dots (**…**) next to the item name and select **Copy SQL connection string**.
4. The copied value follows this format:

```
abc1def2ghij3klmn.datawarehouse.fabric.microsoft.com,1433
```

The **Host** is the server name that appears before the comma and port number. For example:

```
abc1def2ghij3klmn.datawarehouse.fabric.microsoft.com
```

Alternatively, open your Warehouse or Lakehouse in the Fabric portal, click the **Settings** gear icon, and navigate to the **SQL endpoint** page to copy the connection string.

<Callout icon="📘" theme="info">
  #### Important

  Always use the Microsoft Fabric SQL connection string endpoint. Do not include the protocol (`https://`) or the port number in the Host value, as this may cause connection failures.
</Callout>

### Find Existing Port

The Port is the TCP port number that your Microsoft Fabric workspace listens on for incoming connections:

1. The port is appended to the SQL connection string, following the server name after a comma.
2. Alternatively, the port is visible in the **SQL endpoint** page under your Warehouse or Lakehouse settings.

The default port for Microsoft Fabric is `1433`. If you did not modify the port, use `1433`.

<Callout icon="📘" theme="info">
  #### Default Port

  If no port is explicitly configured, CleverTap defaults to port `1433` for Microsoft Fabric connections.
</Callout>

### Find Client ID and Tenant ID

The Client ID and Tenant ID are obtained from your Microsoft Entra ID app registration. To find these values, perform the following steps:

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Navigate to **Microsoft Entra ID** > **App registrations**.
3. Select your app registration from the list (for example, `CleverTap Fabric Integration`).
4. On the **Overview** page, locate:
   * **Application (client) ID** — this is the **Client ID**.
   * **Directory (tenant) ID** — this is the **Tenant ID**.
5. Copy both values.

### Create or Retrieve a Client Secret

To authenticate CleverTap with Microsoft Fabric, you need an active client secret for your app registration:

1. In the Azure portal, navigate to **Microsoft Entra ID** > **App registrations** > your app.
2. Select **Certificates & secrets** from the left menu.
3. Under **Client secrets**, check if an active (non-expired) secret exists.
4. If you need a new secret, click **+ New client secret**, enter a description and expiry, then click **Add**.
5. Copy the secret **Value** immediately and store it securely. The value is displayed only once.

<Callout icon="📘" theme="info">
  #### Secret Rotation

  If your organization requires periodic credential rotation, generate a new client secret before the current one expires. Update the CleverTap connection with the new secret to avoid import interruptions. For detailed guidance, refer to Microsoft Entra documentation on [App Registration Secrets](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).
</Callout>

### Find Existing Database Name

The database name identifies the specific Warehouse or Lakehouse SQL analytics endpoint within your Fabric workspace:

1. In the [Microsoft Fabric portal](https://app.fabric.microsoft.com), navigate to your Workspace.
2. Look for items of type **Warehouse** or **SQL analytics endpoint** in the item list.
3. The item name is your **Database** value.

Alternatively, when you copy the SQL connection string from **Settings** > **SQL endpoint**, the `Initial Catalog` parameter contains the database name.

### Find Existing Schema

To find existing schemas in your Fabric Warehouse, perform the following steps:

1. Open your Warehouse in the [Microsoft Fabric portal](https://app.fabric.microsoft.com).
2. In the **Object Explorer** panel, expand the database node to view schemas.
3. The default schema is `dbo`. Any custom schemas will also be listed.

Alternatively, run the following SQL query:

```sql
-- List all schemas in the current database
SELECT name FROM sys.schemas ORDER BY name;
```

<Callout icon="📘" theme="info">
  #### Default Schema

  By default, every Fabric Warehouse includes a `dbo` schema. If you have not created a custom schema, you can use `dbo`.
</Callout>

### Verify Existing Permissions

The service principal associated with your app registration must have the required permissions to authenticate with your Fabric workspace:

* If you have created a dedicated app registration for CleverTap (as described in [Register App in Microsoft Entra ID](doc:microsoft-fabric#register-app-in-microsoft-entra-id)), confirm it has at minimum **Contributor** role access to the Workspace via **Manage access**.
* Verify database-level permissions by running:

```sql
-- Check current permissions for the service principal
SELECT dp.name, dp.type_desc, perm.permission_name, perm.state_desc
FROM sys.database_permissions perm
JOIN sys.database_principals dp ON perm.grantee_principal_id = dp.principal_id
WHERE dp.name = '<service_principal_name>';
```

* If the required permissions (`CONNECT` and `SELECT`) are not present, refer to [Configure Permissions](doc:microsoft-fabric#configure-permissions) above to grant them.

# Set Up CleverTap Dashboard for Integration

To connect Microsoft Fabric with CleverTap, go to _Settings_ > _Partners_ > _Microsoft Fabric_ from the CleverTap dashboard, select **Add Database**, and configure the following fields.

## Connection Details

Enter the _Connection Details_ in the integration setup form. To create or retrieve details from your Microsoft Fabric account, refer to [Create New Microsoft Fabric Setup](doc:microsoft-fabric#create-new-microsoft-fabric-setup) or [Use Existing Microsoft Fabric Credentials](doc:microsoft-fabric#use-existing-microsoft-fabric-credentials).

<Image align="center" border={true} caption="Connection Details" src="[placeholder-for-fabric-dashboard-screenshot]" />

| Field               | Description                                                                                                                                                                                                |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Connection Nickname | A unique, user-defined name to identify this Microsoft Fabric connection within CleverTap. This name is used when setting up imports. For example, `Fabric Production - US East`.                          |
| Host                | The SQL connection string endpoint of your Fabric Warehouse or Lakehouse, excluding the port number and protocol. It typically follows the format: `abc1def2ghij3klmn.datawarehouse.fabric.microsoft.com`. |
| Port                | The TCP port number your Microsoft Fabric workspace uses for connections. Default: `1433`. If left blank, CleverTap uses `1433` automatically.                                                             |
| Client ID           | The Application (Client) ID from your Microsoft Entra app registration that CleverTap uses to authenticate via service principal.                                                                          |
| Tenant ID           | The Directory (Tenant) ID of your Microsoft Entra ID tenant.                                                                                                                                               |
| Client Secret       | The client secret value generated for your app registration. Used alongside the Client ID to authenticate CleverTap to your Fabric workspace.                                                              |
| Database            | The name of the Fabric Warehouse or Lakehouse SQL analytics endpoint containing the data you want to integrate with CleverTap.                                                                             |
| Schema              | The specific schema within the database that contains the tables for import. Use `dbo` if no custom schema has been created.                                                                               |

## Test and Save Connection

After entering all the details, click **Test Connection** or **Save**:

* **Test Connection**: Verifies if the database credentials and network setup are correct. A successful test confirms the connection, while a failure prompts you to review your settings.
* **Save**: Saves the connection details, enabling you to proceed with the data import process.

# Troubleshooting

If the Test Connection fails, use the following table to identify and resolve common issues:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Symptom
      </th>

      <th>
        Likely Cause
      </th>

      <th>
        Resolution
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Connection timeout
      </td>

      <td>
        The network or firewall is blocking the connection
      </td>

      <td>
        * Ensure CleverTap IPs are whitelisted in your network and Fabric workspace settings.
        * Verify the Host value does not include `https://` or the port number.
        * Confirm TCP port 1433 (or your custom port) is open.
      </td>
    </tr>

    <tr>
      <td>
        Authentication failure
      </td>

      <td>
        Invalid Client ID, Tenant ID, or expired client secret
      </td>

      <td>
        * Verify the Client ID and Tenant ID in the Azure portal under your app registration's Overview page.
        * Generate a new client secret if the current one has expired, and update the CleverTap connection.
      </td>
    </tr>

    <tr>
      <td>
        Database not found
      </td>

      <td>
        Incorrect Database name or Warehouse is paused
      </td>

      <td>
        * Verify the Warehouse or Lakehouse name in the Fabric portal.
        * Ensure the Warehouse is running.
      </td>
    </tr>

    <tr>
      <td>
        Schema or table not found
      </td>

      <td>
        Incorrect schema name or missing privileges
      </td>

      <td>
        * Confirm the Schema name is spelled correctly and exists within the specified Database.
        * Grant `SELECT` privileges on the schema or required tables to the service principal.
      </td>
    </tr>

    <tr>
      <td>
        Service principal not authorized
      </td>

      <td>
        Service principal not added to Fabric Workspace or Fabric APIs not enabled
      </td>

      <td>
        * Add the service principal to the Workspace with the Contributor role via **Manage access**.
        * Ensure **Service principals can use Fabric APIs** is enabled in the Fabric Admin portal under **Tenant settings**.
      </td>
    </tr>

    <tr>
      <td>
        SELECT permission denied
      </td>

      <td>
        Missing SELECT permission on tables or schema
      </td>

      <td>
        * Grant `SELECT` on the schema or specific tables to the service principal. For more information, refer to [Configure Permissions](doc:microsoft-fabric#configure-permissions).
      </td>
    </tr>
  </tbody>
</Table>

# FAQs

This section addresses common questions about managing Microsoft Fabric connections and imports in CleverTap.

### What is the default port for Microsoft Fabric?

The default port for Microsoft Fabric is `1433`. This is the standard TDS (Tabular Data Stream) port. If you did not change the port during setup, use this value. CleverTap also defaults to `1433` if no port is specified.

### How do I whitelist CleverTap IPs for my Microsoft Fabric workspace?

Add the CleverTap IP addresses to your network and Fabric workspace settings to allow inbound traffic on port 1433 (or your custom port). For the list of IPs, refer to [CleverTap IP Ranges](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration).

### Can I use a Lakehouse instead of a Warehouse?

Yes. Every Lakehouse in Microsoft Fabric automatically provisions a SQL analytics endpoint. Use the SQL analytics endpoint connection string as the **Host** and the Lakehouse name as the **Database** value. The SQL analytics endpoint provides read-only T-SQL access to your Lakehouse Delta tables.

### How can I find my schema if I have not created one?

Every Fabric Warehouse includes a default `dbo` schema. If you have not created a custom schema, enter `dbo` as the Schema value.

### What happens when my client secret expires?

When the client secret expires, CleverTap will no longer be able to authenticate with Microsoft Fabric, and all active imports will fail. To resolve this, generate a new client secret in the Azure portal on your app registration's **Certificates & secrets** page, then update the connection in CleverTap by editing it and replacing the expired credential.

### Can I use the same Microsoft Fabric connection for multiple imports?

Yes. A single Microsoft Fabric connection in CleverTap can be used to create multiple import configurations, each reading from different tables within the same database and schema.

### What permissions does the service principal need?

At minimum, the service principal needs Contributor role membership in the Fabric Workspace and `CONNECT` + `SELECT` privileges on the target database and tables. Service principals must also be enabled in the Fabric Admin portal under **Tenant settings** > **Service principals can use Fabric APIs**.

# Next Steps

<Cards>
  <Card title="Import Data to CleverTap" href="https://docs.clevertap.com/docs/data-warehouse#quick-start-guide-for-imports" />
</Cards>
