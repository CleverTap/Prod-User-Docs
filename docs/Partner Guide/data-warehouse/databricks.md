---
title: Databricks
excerpt: >-
  Learn how configuring Databricks with CleverTap enables data sync for
  personalized engagement and growth.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Configuring Databricks with CleverTap enables seamless data import, ensuring synchronization and access to relevant information for analysis, personalized engagement, and data-driven growth.

CleverTap supports the following authentication methods for connecting to Databricks:

- **Personal Access Token (PAT)**: Authenticates using a long-lived token generated for a Databricks user or service principal.
- **OAuth (Machine-to-Machine)**: Authenticates as a Databricks service principal using a Client ID and Client Secret. CleverTap automatically exchanges these credentials for short-lived OAuth access tokens. CleverTap recommends using OAuth for production integrations.

# Quick Start Guide for Existing Users

<details>
  <summary>Expand for quick setup if you have previously configured a Databricks workspace and are familiar with the CleverTap dashboard. If you are setting up Databricks for the first time, skip to Prerequisites for Integration below.</summary>

  <hr />

## Prerequisites

Before you begin, ensure you have the following details:

- **Connection Name**: A unique name to identify this configuration in CleverTap.
- **Host**: Databricks workspace domain (found under _SQL_ > _Warehouses_ > _Connection Details_).
- **HTTP Path**: HTTP path of the target SQL Warehouse (found under _SQL_ > _Warehouses_ >
  _Connection Details_).
- **Authentication Credentials**: One of the following, based on the authentication method you select:
  - **Personal Access Token (PAT)**: Token authorized to access the SQL Warehouse.
  - **OAuth Client ID and Client Secret**: Credentials of a Databricks service principal authorized to access the SQL Warehouse.
- **Catalog**: The Unity Catalog for CleverTap data operations.
- **Schema**: The specific schema within the catalog for CleverTap tables.
- **Port**: HTTPS port (defaults to 443 if not specified)

## Configure Databricks Credentials in CleverTap

To set up the Databricks credentials in CleverTap, perform the following steps:

1. Go to _CleverTap Dashboard_ > _Settings_ > _Partners_ > _Databricks_.

2. Click **Add Database**.

3. Enter the following details: _Host_, _HTTP Path_, _Personal Access Token (PAT)_, _Catalog_, _Schema_, and _Port_.

4. Under Authentication, select one of the following methods:
   - **PAT**: Enter the Personal Access Token (PAT).
   - **OAuth**: Enter the Client ID and Client Secret of the service principal.

5. Click **Test Connection** to verify the configuration, then click **Save** to store it.

After configuring it, you can [import](doc:data-warehouse-import) data between Databricks and CleverTap.

</details>

# Prerequisites for Integration

If you are setting up Databricks for the first time, ensure you have the following before proceeding with the CleverTap configuration:

- CleverTap **Access** to configure Databricks.
- **Databricks Workspace Details**:
  - **Host**: Workspace domain (for example, `adb1234567890123456.17.azuredatabricks.net`). Do not include the protocol (https\://).
  - **HTTP Path**: HTTP path of the target SQL Warehouse or endpoint (for example, `/sql/1.0/warehouses/abc123def456`).
  - **Authentication Credentials**: Depending on the authentication methods you select:
    - **Personal Access Token (PAT)**: Token authorized to access the SQL Warehouse. Ensure the token has an appropriate lifetime (recommended: 365 days or more for production).
    - **OAuth Client ID and Client Secret**: Credentials generated for a Databricks service principal authorized to access the SQL Warehouse. Verify if the OAuth secret has an appropriate lifetime (recommended: 365 days or more for production; maximum: 730 days).
- **Catalog and Schema**: Unity Catalog objects where data will be read.
  - **Port**: HTTPS port used to reach Databricks. Defaults to 443 if not specified. Customers behind corporate proxies may need to consult their network administrator for the correct port.
- **Databricks Identity and Permissions**

  The identity used to generate the PAT (user or service principal) must have, at a minimum:

  - **USE CATALOG** on the selected catalog and **USE SCHEMA** on the selected schema.
  - **SELECT** on tables you plan to import (optionally, grant on future tables if your process creates tables later).
  - **CAN USE** on the SQL Warehouse.

<Callout icon="📘" theme="info">
  #### Security

  Use a dedicated Databricks identity for CleverTap, grant least privilege, and set an expiry/rotation policy for the credential. For production integrations, we recommend OAuth with a dedicated service principal: access tokens are short-lived, and the integration is not tied to an individual user account.
</Callout>

<Callout icon="📘" theme="info">
  #### IP Whitelisting

  To ensure seamless communication between CleverTap and your Databricks workspace, whitelist the required CleverTap IP ranges in your network and Databricks workspace settings. Refer to [CleverTap IP Ranges](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration) for the complete list.
</Callout>

# Set Up Databricks for Integration

You can set up Databricks using one of the following ways:

- For new users who need to provision Databricks resources from scratch: [Create New Databricks Setup](doc:databricks#create-new-databricks-setup)
- For users who already have configured resources in Databricks: [Use existing Databricks Credentials](doc:databricks#use-existing-databricks-credentials)

## Create New Databricks Setup

If you do not already have a Catalog, SQL Warehouse, Personal Access Token, and Schema configured in Databricks, you must create them before proceeding. These components are required to ensure CleverTap can securely access, store, and process your data.

The following table explains each Databricks component and its role in the integration:

| Field                              | Description                                                                                                                                                                                                                                 |
| :--------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Unity Catalog                      | A top-level container that organizes your data assets. It holds schemas (databases), which in turn hold tables and views.                                                                                                                   |
| SQL Warehouse                      | A compute resource that executes SQL queries. CleverTap connects to a SQL Warehouse to read data from your catalog and schema.                                                                                                              |
| Personal Access Token              | An authentication credential that CleverTap uses to securely connect to your Databricks workspace on behalf of a user or service principal. Required only if you use PAT authentication.                                                    |
| Service Principal and OAuth Secret | A Databricks-managed identity for automated workloads, along with a Client ID and Client Secret generated for it. CleverTap exchanges these credentials for short-lived OAuth access tokens. Required only if you use OAuth authentication. |
| Schema                             | A logical grouping within a catalog that contains tables. CleverTap reads from tables within the schema you specify.                                                                                                                        |

To create each resource, perform the following steps:

1. [Create Catalog](doc:databricks#create-catalog)
2. [Create SQL Warehouse](doc:databricks#create-sql-warehouse)
3. [Create Personal Access Token](doc:databricks#create-personal-access-token) OR

   [Create Service Principal and OAuth Secret](doc:databricks#create-service-principal-and-oauth-secret)
4. [Create a Schema](doc:databricks#create-schema)
5. [Configure Permissions](doc:databricks#configure-permissions)

### Create Catalog

To get your Databricks data in CleverTap, you first need to create a Unity Catalog.

<Callout icon="📘" theme="info">
  #### **Prerequisite**

  Creating a catalog requires metastore admin privileges or the CREATE CATALOG permission. If you do not have permission, contact your Databricks workspace administrator.
</Callout>

To create a Unity catalog, perform the following steps:

1. Open a SQL editor in your Databricks workspace with Unity Catalog enabled.
2. Run the following SQL command to create a catalog:
3. ```sql SQL
   -- Create a new catalog for CleverTap data storage
   CREATE CATALOG IF NOT EXISTS clevertap_catalog;

   -- Verify catalog creation
   SHOW CATALOGS;
   ```

**Expected Output**

```sql SQL
+--------------------+
| catalog_name |
+--------------------+
| clevertap_catalog |
+--------------------+
```

### Create SQL Warehouse

CleverTap executes queries through a Databricks SQL Warehouse. Create a dedicated warehouse for CleverTap to avoid contention with other workloads.

To create a SQL Warehouse via the Databricks UI, perform the following steps:

1. In Databricks, navigate to **SQL** in the left sidebar.
2. Click **SQL Warehouses** and then click **Create**.
3. Configure the warehouse with the following recommended settings:
   1. **Name**: Enter a descriptive name (for example, `clevertap_warehouse`).
   2. **Size**: Select **Small** (sufficient for most CleverTap import workloads).
   3. **Auto Stop**: Set to **10 minutes** to control costs when idle.
   4. **Auto Resume**: Enable to automatically start the warehouse when a query arrives.
4. Click **Create**.
5. After the warehouse is created, navigate to the **Connection Details** tab.
6. Copy the **Host** and **HTTP Path** values. You will need these when configuring CleverTap.

<Callout icon="📘" theme="info">
  ### Note

  Enable Auto Stop to control costs. Databricks charges on a per-second billing model, so setting Auto Stop to 10 minutes ensures the warehouse does not run when idle. Ensure the PAT identity has USE permission on this warehouse.
</Callout>

### Create Personal Access Token

Create or identify the Databricks identity you will use with CleverTap, then generate a Personal Access Token (PAT). To generate a PAT, perform the following steps:

1. In Databricks, click your **username** in the top-right corner of the workspace.

2. Select **Settings** from the dropdown menu.

3. Under **User**, select **Developer**.

4. In the **Access Tokens** section, click **Manage**.

5. Click **Generate New Token**.

6. Enter an optional **Comment** (for example, `CleverTap Integration`) to identify the token.

7. Set the **Lifetime** in days. For production integrations, a minimum of 365 days is recommended. The maximum lifetime for a PAT is 730 days.

8. Select scope: `sql`

   This is the only scope required. CleverTap connects via JDBC (Java Database Connectivity) to your SQL Warehouse and uses standard SQL commands (SHOW CATALOGS, SHOW SCHEMAS, SHOW TABLES, DESCRIBE, SELECT) for all operations, all of which are covered by the sql scope.

9. Ensure the user or service principal the PAT belongs to has the following grants:

   - **Unity Catalog grants**
     - `USE CATALOG` on the catalog
     - `USE SCHEMA` on the schema
     - `SELECT` on each table or view, CleverTap needs to import
   - **Compute access**

     `CAN USE` on the SQL Warehouse, CleverTap will connect to

   <Callout icon="📘" theme="info">
     #### Note

     CleverTap recommends creating a dedicated service principal for this integration and limiting `SELECT` grants to only the specific tables or views you want CleverTap to import.
   </Callout>

10. Click **Generate**.

11. Copy the token value immediately and store it securely. **The token is displayed only once**. You will paste it in the Personal Access Token (PAT) field in CleverTap.

<Callout icon="🚧" theme="warn">
  #### **Token Expiration**

  PATs expire based on the lifetime you set during creation. When a token expires, the CleverTap connection will fail, and imports will stop. Monitor token expiration dates and regenerate tokens before they expire. Consider setting a calendar reminder.
</Callout>

### Create Service Principal and OAuth Secret

With OAuth (Machine-to-Machine), CleverTap authenticates a Databricks service principal using a Client ID and Client Secret, and automatically exchanges these credentials for short-lived OAuth access tokens. To set this up, perform the following steps:

1. **Create Service Principal**
   1. In Databricks, click the username in the top-right corner of the workspace and select _Settings_ from the dropdown menu.
   2. Click **Identity and access**, and click **Manage** next to Service principals.
   3. Click **Add service principal**, and then click **Add new**.
   4. Enter a descriptive name (for example, clevertap-integration) and click **Add**.
2. **Generate OAuth Secret**

   1. From the _Service principals_ page, click the service principal you created.
   2. Select the _Secrets_ tab.
   3. Under OAuth secrets, click **Generate secret**.
   4. Set the secret lifetime in days. For production integrations, we recommend a minimum of 365 days. The maximum lifetime for an OAuth secret is 730 days.
      <Callout icon="🚧" theme="warn">
        #### OAuth Secret Expiration

        OAuth Secret expires based on the lifetime you set during creation. When it expires, the CleverTap connection fails, and imports stop. Monitor secret expiration dates and generate a new secret before the current one expires. Consider setting a calendar reminder.
      </Callout>
   5. Click **Generate**.
   6. Copy the displayed Client ID and Secret immediately and store them securely. The secret is displayed only once. Paste these values into the Client ID and Client Secret fields in CleverTap.
      <Callout icon="📘" theme="info">
        #### Client ID

        The Client ID is the same as the Application ID (a UUID) of the Service Principal. You can view it at any time on the _Service Principal&#x20;_&#x70;age. The secret cannot be viewed again after creation; if it is lost, generate a new secret. Each service principal can have up to five OAuth secrets.&#x20;
      </Callout>
3. **Grant Required Permissions to Service Principal**

   Verify if the Service Principal has the following grants:

   - **Unity Catalog grants**
     - USE CATALOG on the catalog
     - USE SCHEMA on the schema
     - SELECT on each table or view that CleverTap needs to import
   - **Compute access**

     - CAN USE on the SQL Warehouse CleverTap will connect to
     - Refer to Configure Permissions below for the SQL commands. When granting privileges to a service principal, reference it by its Application ID.

     <Callout icon="📘" theme="info">
       #### Microsoft Entra ID Service Principal (Azure)

       On Azure Databricks, if your service principal is Microsoft Entra ID managed, you must still generate the OAuth secret in Databricks as described above. A client secret created in Microsoft Entra ID is not the same secret and cannot be used in CleverTap.
     </Callout>

### Create Schema

After creating the catalog, you must create a schema to organize CleverTap-related objects. To do so, perform the following steps:

1. Ensure you are using the correct catalog context:

   ```sql SQL
   -- Switch to the CleverTap catalog
   USE CATALOG clevertap_catalog;
   ```

2. Execute the following SQL command to create a schema:

   ```sql SQL
   -- Create a new schema for CleverTap data
   CREATE SCHEMA IF NOT EXISTS clevertap_schema;

   -- Verify schema creation
   SHOW SCHEMAS;
   ```

**Expected Output**

```sql SQL
+--------------------+
| schema_name |
+--------------------+
| clevertap_schema |
+--------------------+
```

## Configure Permissions

To ensure the PAT identity (user or service principal) can access the resources created above, grant the required permissions. This step is essential for CleverTap to read data from your Databricks workspace.

Run the following SQL commands, replacing `clevertap_user` with your actual user or service principal name:

```
-- Grant catalog-level access
GRANT USAGE ON CATALOG clevertap_catalog TO 'clevertap_user';

-- Grant schema-level access
GRANT USAGE ON SCHEMA clevertap_catalog.clevertap_schema TO 'clevertap_user';

-- Grant read access on all existing tables in the schema
GRANT SELECT ON SCHEMA clevertap_catalog.clevertap_schema TO 'clevertap_user';
```

<Callout icon="📘" theme="info">
  #### **Granular Table Permissions**

  If you prefer to grant access to specific tables rather than the entire schema, use the following command instead:&#x20;

  `GRANT SELECT ON TABLE clevertap_catalog.clevertap_schema.table_name TO clevertap_user`&#x20;

  Repeat for each table that CleverTap needs to access.
</Callout>

If the identity also needs access to the SQL Warehouse, grant CAN USE from the warehouse permissions settings:

1. In Databricks, navigate to SQL Warehouses and click the target warehouse.
2. Click **Permissions**.
3. Add the user or service principal and select **Can use**.

You can verify the grants by running:

```
SHOW GRANTS ON CATALOG clevertap_catalog;
SHOW GRANTS ON SCHEMA clevertap_catalog.clevertap_schema;
```

## Use Existing Databricks Credentials

If you already have Databricks set up, follow these steps to find each detail in the Databricks workspace.

- [Obtain Host and HTTP Path from SQL Warehouse](doc:databricks#obtain-host-and-http-path-from-sql-warehouse)
- [Create or Retrieve a PAT](doc:databricks#create-or-retrieve-a-pat)
- [Create or Retrieve OAuth Credentials](doc:databricks#create-or-retrieve-oauth-credentials)
- [Find Existing Catalog](doc:databricks#find-existing-catalog)
- [Find Existing Schema](doc:databricks#find-existing-schema)
- [Verify Existing Permissions](doc:databricks#verify-existing-permissions)

### Obtain Host and HTTP Path from SQL Warehouse

To configure the integration, you need your Databricks Host and the HTTP Path of your SQL Warehouse. Both values are available from the same location. Follow these steps:

1. In Databricks, click **SQL** in the left sidebar.
2. Select **SQL Warehouses** from the left panel to view available warehouses.
3. Click on the target warehouse to open its details.
4. Navigate to the **Connection Details** tab.
5. Copy the Host value (for example, [`adb1234567890123456.17.azuredatabricks.net`]()).
6. Copy the HTTP Path value (for example, `/sql/1.0/warehouses/abc123def456`).

### Create or Retrieve a PAT

To authenticate CleverTap with Databricks, generate a Personal Access Token:

1. In Databricks, click your **username** in the top-right corner.
2. Select **Settings > Developer > Access Tokens**.
3. Click **Generate New Token**, enter a comment and lifetime, then click **Generate**.
4. Copy the token value immediately and store it securely. **The token is displayed only once.**

<Callout icon="📘" theme="info">
  #### **Token Rotation**

  If your organization requires periodic credential rotation, generate a new PAT before the current one expires. Update the CleverTap connection with the new token to avoid import interruptions. For detailed guidance, refer to Databricks documentation on Personal Access Tokens&#x20;
</Callout>

### Create or Retrieve OAuth Credentials

This section is required only if you use OAuth authentication. To retrieve the Client ID and generate a Client Secret for an existing service principal, perform the following steps:

1. In Databricks, click the username in the top-right corner, then select _Settings_ > _Identity_ and access.
2. Next to Service principals, click **Manage** and select the target service principal. If you do not have one, refer to Create a Service Principal and OAuth Secret.
3. Copy the service principal's Application ID. This is the Client ID.
4. Select the _Secrets_ tab and click Generate secret if you do not have an active secret. Existing secret values cannot be retrieved after creation.
5. Copy the secret value immediately and store it securely. The secret is displayed only once.

<Callout icon="📘" theme="info">
  #### Secret Rotation

  If your organization requires periodic credential rotation, generate a new OAuth secret before the current one expires. Update the CleverTap connection with the new Client Secret to avoid import interruptions. The Client ID does not change. For detailed guidance, refer to [Databricks documentation on OAuth for Service Principal](https://docs.databricks.com/aws/en/dev-tools/auth/oauth-m2m).
</Callout>

### Find Existing Catalog

If you need to check for existing catalogs in your workspace:

1. In Databricks, open **Data Explorer** from the left sidebar.
2. Review the list under **Catalogs** to identify the catalog to use with CleverTap.
3. Alternatively, run the following SQL command:

```sql SQL
SHOW CATALOGS;
```

### Find Existing Schema

To find existing schemas in a specific catalog, perform the following steps:

1. In **Data Explorer**, select the desired catalog.
2. Select **Schemas** to view all available schemas within that catalog.
3. Alternatively, run the following SQL command, replacing `<catalog_name>` with your catalog:

```sql SQL
SHOW SCHEMAS IN CATALOG <catalog_name>;
```

### Verify Existing Permissions

Ensure the user or service principal associated with your PAT or OAuth credentials has the required permissions:

```
-- Check grants on your catalog
SHOW GRANTS ON CATALOG <catalog_name>;
-- Check grants on your schema
SHOW GRANTS ON SCHEMA <catalog_name>.<schema_name>;
```

If the required permissions (USAGE and SELECT) are not present, refer to the [Configure Permissions](doc:databricks#configure-permissions) section above to grant them.

# Set Up CleverTap Dashboard for Integration

You have already prepared your Databricks environment and gathered the required values (Host, HTTP Path, Personal Access Token, Catalog, and optionally Schema and Port). In this section, you will add a Databricks connection in CleverTap, enter these parameters, validate the connection, and proceed to create an import.


<Image src="https://files.readme.io/fc990eb9c46874f7f344de3ac6f97f58f5df435e60b199adfcdd74ede5d325aa-Integrate_Databricks_Dashboard.png" align="center" caption="Connection Details for Databricks" border={true} />


## Connection Details for Databricks

To connect Databricks with CleverTap, go to _Settings > Partners > Databricks_ and select **Add Database**. To create or retrieve details from your Databricks workspace, refer to [Create a new Catalog](doc:databricks-integration#create-new-databricks-setup), [SQL Warehouse](doc:databricks#create-sql-warehouse), [Personal Access Token](doc:databricks#create-personal-access-token), and [Schema](doc:databricks#create-schema) or [Use existing Databricks credentials](doc:databricks-integration#use-existing-databricks-credentials) and configure the following:

| Field                       | Description                                                                                                                                                                                                                                                                  |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Connection name             | A unique name to identify your configuration while setting up imports. Choose a descriptive name (for example, "Databricks Production" or "Databricks Analytics").                                                                                                           |
| Host                        | The Databricks workspace host (domain only; do not include the protocol). For example: `adb-1234567890123456.17.azuredatabricks.net`. Refer to [Obtain Host and HTTP Path from SQL Warehouse](doc:databricks#obtain-host-and-http-path-from-sql-warehouse).                  |
| Port                        | HTTPS port used to reach Databricks. If a port is specified, CleverTap uses it; otherwise, the connection defaults to `443`.                                                                                                                                                 |
| HTTP Path                   | The HTTP path of the target SQL Warehouse endpoint in Databricks. For example: `/sql/1.0/warehouses/abc123def456`.                                                                                                                                                           |
| Authentication              | The method CleverTap uses to authenticate with Databricks. Select _PAT_ to authenticate with a Personal Access Token, or _OAuth_ to authenticate as a service principal using a Client ID and Client Secret. The credential fields displayed below depend on this selection. |
| Personal Access Token (PAT) | The token used by CleverTap to authenticate to Databricks. Refer to [Create or Retrieve a PAT](doc:databricks#create-or-retrieve-a-pat). Ensure the token has not expired.                                                                                                   |
| Client ID                   | Displayed when Authentication is set to OAuth. The Application ID (UUID) of the Databricks service principal. For more information, refer to [Create or Retrieve OAuth Credentials](doc:databricks#create-or-retrieve-oauth-credentials).                                    |
| Client secret               | Displayed when Authentication is set to OAuth. An active OAuth secret generated for the service principal. Refer to [Create or Retrieve OAuth Credentials.](doc:databricks#create-service-principal-and-oauth-secret) Ensure the secret has not expired.                     |
| Catalog                     | The Unity Catalog used for CleverTap data operations.                                                                                                                                                                                                                        |
| Schema                      | The specific schema within the catalog that contains the tables used by CleverTap.                                                                                                                                                                                           |

## Test and Save Connection

After entering all connection details, complete the setup:

1. Click **Test Connection** to verify that the workspace, HTTP Path, credentials, and privileges are correct.
   1. A successful test confirms that CleverTap can reach your Databricks workspace and access the specified catalog and schema.
   2. A failed test indicates an issue with one or more parameters. Refer to the [Troubleshooting](doc:databricks#troubleshooting) section below for common errors.
2. Click **Save** to store the connection details.
3. After saving, go to the _Import Connections_ dashboard and click [**Create Import**](doc:data-warehouse-import) to set up your first data import.

## Troubleshooting

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
        Network/firewall is blocking the connection
      </td>

      <td>
        Ensure CleverTap IPs are whitelisted. Verify the Host value does not include https\://.
      </td>
    </tr>

    <tr>
      <td>
        Authentication failed
      </td>

      <td>
        Depending on the authentication method you select:

        - Invalid or expired PAT
        - Invalid Client ID, or an invalid or expired Client Secret
      </td>

      <td>
        - Generate a new PAT in Databricks and update the connection in CleverTap.
        - Verify that the Client ID matches the Application ID of the Service Principal. Generate a new OAuth secret in Databricks and update the connection in CleverTap.
      </td>
    </tr>

    <tr>
      <td>
        Warehouse not found or inactive
      </td>

      <td>
        SQL Warehouse is stopped, or the HTTP Path is incorrect
      </td>

      <td>
        Start the warehouse in Databricks or verify the HTTP Path from Connection Details.
      </td>
    </tr>

    <tr>
      <td>
        Catalog or schema not accessible
      </td>

      <td>
        Missing USAGE permission
      </td>

      <td>
        Grant USAGE on the catalog and schema to the PAT identity. See Configure Permissions.
      </td>
    </tr>

    <tr>
      <td>
        SELECT permission denied
      </td>

      <td>
        Missing SELECT permission on tables
      </td>

      <td>
        Grant SELECT on the schema or specific tables. See Configure Permissions.
      </td>
    </tr>
  </tbody>
</Table>

# FAQs

This section answers common questions about managing Databricks connections and imports in CleverTap.

### Should I use PAT or OAuth authentication?

For production integrations, CleverTap recommends using OAuth. CleverTap exchanges the Client ID and Client Secret of the Service Principal for short-lived access tokens, and the connection is tied to a dedicated service principal rather than an individual user account. PAT remains fully supported and is a simpler option for trials and quick evaluations.

### How can I delete a connection that has running imports?

Go to _Import Connections_, select the connection, click **Delete**, and review the running imports. If there are any imports in ready, scheduled, paused, or running state, it stops all these active imports associated with the connection. Once done, click **Delete** and confirm.

### How can I filter import connections?

Use the filters on _Import Connections_ to refine the list:

- **Connected On**: Filter by creation date.
- **Connected By**: Filter by the user who created the connection.

### How can I whitelist IPs for CleverTap integration?

To ensure seamless communication between CleverTap and your systems, whitelist the required IP ranges. To access the list of IPs to whitelist for import integrations, refer to [CleverTap IP Ranges](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration).

### What happens when my PAT expires?

When the Personal Access Token expires, CleverTap will no longer be able to authenticate with Databricks, and all active imports will fail. To resolve this, generate a new PAT in Databricks, then update the CleverTap connection by editing it and replacing the old token with the new one.

### Can I use the same Databricks connection for multiple imports?

Yes. A single Databricks connection in CleverTap can be used to create multiple import configurations, each reading from different tables within the same catalog and schema
