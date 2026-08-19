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
- **Personal Access Token (PAT)**: Token authorized to access the SQL Warehouse.
- **Catalog**: The Unity Catalog for CleverTap data operations.
- **Schema**: The specific schema within the catalog for CleverTap tables.
- **Port**: HTTPS port (defaults to 443 if not specified)

  ## Configure Databricks Credentials in CleverTap

  To set up the Databricks credentials in CleverTap, perform the following steps:

1. Go to _CleverTap Dashboard_ > _Settings_ > _Partners_ > _Databricks_.

2. Click _Add Database_.

3. Enter the following details: _Host_, _HTTP Path_, _Personal Access Token (PAT)_,_Catalog_, _Schema_, and _Port_.

4. Click **Test Connection** to verify thev configuration and click **Save** to store the configuration.

After setting up the configuration, you can [import](doc:data-warehouse-import) data between Databricks and CleverTap.

</details>

# Prerequisites for Integration

If you are setting up Databricks for the first time, ensure you have the following before proceeding with the CleverTap configuration:

- CleverTap **Access** to configure Databricks.
- **Databricks Workspace Details**:
  - **Host**: Workspace domain (for example, `adb1234567890123456.17.azuredatabricks.net`). Do not include the protocol (https\://).
  - **HTTP Path**: HTTP path of the target SQL Warehouse or endpoint (for example, `/sql/1.0/warehouses/abc123def456`).
  - **Personal Access Token (PAT)**: Token authorized to access the SQL Warehouse. Ensure the token has an appropriate lifetime (recommended: 90 days or more for production).
  - **Catalog and Schema**: Unity Catalog objects where data will be read.
  - **Port**: HTTPS port used to reach Databricks. Defaults to 443 if not specified. Customers behind corporate proxies may need to consult their network administrator for the correct port.
- **Databricks Identity and Permissions**

  The identity used to generate the PAT (user or service principal) must have, at minimum:

  - **USAGE** on the selected **catalog** and **schema**.
  - **SELECT** on tables you plan to import (optionally, grant on future tables if your process creates tables later).

<Callout icon="📘" theme="info">
  **Security**

  Use a dedicated Databricks identity for CleverTap, grant least privilege, and set an expiry/rotation policy for the PAT.
</Callout>

<Callout icon="📘" theme="info">
  **IP Whitelisting**<br />To ensure seamless communication between CleverTap and your Databricks workspace, whitelist the required CleverTap IP ranges in your network and Databricks workspace settings. Refer to [CleverTap IP Ranges](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration) for the complete list.
</Callout>

# Set Up Databricks for Integration

You can set up Databricks using one of the following ways:

- For new users who need to provision Databricks resources from scratch: [Create New Databricks Setup](doc:databricks#create-new-databricks-setup)
- For users who already have configured resources in Databricks: [Use existing Databricks Credentials](doc:databricks#use-existing-databricks-credentials)

## Create New Databricks Setup

If you do not already have a Catalog, SQL Warehouse, Personal Access Token, and Schema configured in Databricks, you must create them before proceeding. These components are required to ensure CleverTap can securely access, store, and process your data.

The following table explains each Databricks component and its role in the integration:

| Field                 | Description                                                                                                                                 |
| :-------------------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| Unity Catalog         | A top-level container that organizes your data assets. It holds schemas (databases), which in turn hold tables and views.                   |
| SQL Warehouse         | A compute resource that executes SQL queries. CleverTap connects to a SQL Warehouse to read data from your catalog and schema.              |
| Personal Access Token | An authentication credential that CleverTap uses to securely connect to your Databricks workspace on behalf of a user or service principal. |
| Schema                | A logical grouping within a catalog that contains tables. CleverTap reads from tables within the schema you specify.                        |

To create each resource, perform the following steps:

1. [Create a Catalog](doc:databricks#create-catalog)
2. [Create a SQL Warehouse](doc:databricks#create-sql-warehouse)
3. [Create Personal Access Token](doc:databricks#create-personal-access-token)
4. [Create a Schema](doc:databricks#create-schema)
5. [Configure Permissions](doc:databricks#configure-permissions)

### Create Catalog

To get your Databricks data in CleverTap, you first need to create a Unity Catalog.

<Callout icon="📘" theme="info">
  **Prerequisite**

  Creating a catalog requires metastore admin privileges or the CREATE CATALOG permission. Contact your Databricks workspace administrator if you do not have this permission.
</Callout>

Follow these steps:

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

7. Set the **Lifetime** in days. For production integrations, a minimum of 90 days is recommended. The maximum lifetime for a PAT is 730 days.

8. If your workspace has scoped PATs enabled (Beta), select the following scope:

   - `sql`

   This is the only scope required. CleverTap connects via JDBC (Java Database Connectivity) to your SQL Warehouse and uses standard SQL commands (`SHOW CATALOGS`, `SHOW SCHEMAS`, `SHOW TABLES`, `DESCRIBE`, `SELECT`) for all operations, all of which are covered by the `sql` scope.

   If you do not see a scope selector, your workspace does not have the Beta enabled. Proceed without selecting a scope and the token will inherit the user's permissions.

9. Ensure the user or service principal the PAT belongs to has the following grants:

   **Unity Catalog grants**

   - `USE CATALOG` on the catalog
   - `USE SCHEMA` on the schema
   - `SELECT` on each table or view CleverTap needs to import

   **Compute access**

   - `CAN USE` on the SQL Warehouse CleverTap will connect to

   - That is the full set. We recommend creating a dedicated service principal for this integration and limiting `SELECT` grants to only the specific tables or views you want CleverTap to import, which is the cleanest approach from a least-privilege standpoint.

   <Callout icon="📘" theme="info">
     ### Note

     We recommend creating a dedicated service principal for this integration and limiting `SELECT` grants to only the specific tables or views you want CleverTap to import.
   </Callout>

10. Click **Generate**.

11. Copy the token value immediately and store it securely. **The token is displayed only once**. You will paste it in the Personal Access Token (PAT) field in CleverTap.

<Callout icon="🚧" theme="warn">
  ### **Token Expiration**

  PATs expire based on the lifetime you set during creation. When a token expires, the CleverTap connection will fail, and imports will stop. Monitor token expiration dates and regenerate tokens before they expire. Consider setting a calendar reminder.
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
  **Granular Table Permissions**

  If you prefer to grant access to specific tables rather than the entire schema, use the following command instead: `GRANT SELECT ON TABLE clevertap_catalog.clevertap_schema.table_name TO
                          clevertap_user` Repeat for each table that CleverTap needs to access.
</Callout>

If the PAT identity also needs access to the SQL Warehouse, ensure the warehouse permissions are configured:

```
-- Grant SQL Warehouse access (run from warehouse admin context)
GRANT CAN USE ON SQL WAREHOUSE clevertap_warehouse TO 'clevertap_user';
```

You can verify the grants by running:

```
SHOW GRANTS ON CATALOG clevertap_catalog;
SHOW GRANTS ON SCHEMA clevertap_catalog.clevertap_schema;
```

## Use Existing Databricks Credentials

If you already have Databricks set up, perform the following steps to find each detail on the Databricks workspace.

- [Obtain Host and HTTP Path from SQL Warehouse](doc:databricks#obtain-host-and-http-path-from-sql-warehouse)
- [Create or Retrieve a PAT](doc:databricks#create-or-retrieve-a-pat)
- [Find Existing Catalog](doc:databricks#find-existing-catalog)
- [Find Existing Schema](doc:databricks#find-existing-schema)
- [Verify Existing Permissions](doc:databricks#verify-existing-permissions)

### Obtain Host and HTTP Path from SQL Warehouse

To configure the integration, you need your Databricks Host and the HTTP Path of your SQL Warehouse. Both values are available from the same location. Follow these steps:

1. In Databricks, click **SQL** in the left sidebar.
2. Select **SQL Warehouses** from the left panel to view available warehouses.
3. Click on the target warehouse to open its details.
4. Navigate to the **Connection Details** tab.
5. Copy the Host value (for example, `adb-1234567890123456.17.azuredatabricks.net`).
6. Copy the HTTP Path value (for example, `/sql/1.0/warehouses/abc123def456`).

### Create or Retrieve a PAT

To authenticate CleverTap with Databricks, generate a Personal Access Token:

1. In Databricks, click your **username** in the top-right corner.
2. Select **Settings > Developer > Access Tokens**.
3. Click **Generate New Token**, enter a comment and lifetime, then click **Generate**.
4. Copy the token value immediately and store it securely. **The token is displayed only once.**

<Callout icon="📘" theme="info">
  **Token Rotation**

  If your organization requires periodic credential rotation, generate a new PAT before the current one expires. Update the CleverTap connection with the new token to avoid import interruptions. Refer to Databricks documentation on Personal Access Tokens for detailed guidance.
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

Ensure the user or service principal associated with your PAT has the required permissions:

```
-- Check grants on your catalog
SHOW GRANTS ON CATALOG <catalog_name>;
-- Check grants on your schema
SHOW GRANTS ON SCHEMA <catalog_name>.<schema_name>;
```

If the required permissions (USAGE and SELECT) are not present, refer to the [Configure Permissions](doc:databricks#configure-permissions) section above to grant them.

# Set Up CleverTap Dashboard for Integration

You have already prepared your Databricks environment and gathered the required values (Host, HTTP Path, Personal Access Token, Catalog, and optionally Schema and Port). In this section, you will add a Databricks connection in CleverTap, enter these parameters, validate the connection, and proceed to create an import.


<Image src="https://files.readme.io/d272d6e1260af455b54f219aa305af9d54e268051ba7a3901a686a2b2405a47a-databricks.png" align="center" caption="Connection Details for Databricks" border={true} />


## Connection Details for Databricks

To connect Databricks with CleverTap, go to _Settings > Partners > Databricks_ and select **Add Database**. To create or retrieve details from your Databricks workspace, refer to [Create a new Catalog](doc:databricks-integration#create-new-databricks-setup), [SQL Warehouse](doc:databricks#create-sql-warehouse), [Personal Access Token](doc:databricks#create-personal-access-token), and [Schema](doc:databricks#create-schema) or [Use existing Databricks credentials](doc:databricks-integration#use-existing-databricks-credentials) and configure the following:

| Field                       | Description                                                                                                                                                                                                                                                 |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Connection name             | A unique name to identify your configuration while setting up imports. Choose a descriptive name (for example, "Databricks Production" or "Databricks Analytics").                                                                                          |
| Host                        | The Databricks workspace host (domain only; do not include the protocol). For example: `adb-1234567890123456.17.azuredatabricks.net`. Refer to [Obtain Host and HTTP Path from SQL Warehouse](doc:databricks#obtain-host-and-http-path-from-sql-warehouse). |
| Port                        | HTTPS port used to reach Databricks. If a port is specified, CleverTap uses it; otherwise, the connection`defaults` to `443`.                                                                                                                               |
| HTTP Path                   | The HTTP path of the target SQL Warehouse endpoint in Databricks. For example: `/sql/1.0/warehouses/abc123def456`.                                                                                                                                          |
| Personal Access Token (PAT) | The token used by CleverTap to authenticate to Databricks. Refer to [Create or Retrieve a PAT](doc:databricks#create-or-retrieve-a-pat). Ensure the token has not expired.                                                                                  |
| Catalog                     | The Unity Catalog used for CleverTap data operations.                                                                                                                                                                                                       |
| Schema                      | The specific schema within the catalog that contains the tables used by CleverTap.                                                                                                                                                                          |

## Test and Save the Connection

After entering all connection details, complete the setup:

1. Click Test Connection to verify that the workspace, HTTP Path, token, and privileges are correct.
   1. A successful test confirms that CleverTap can reach your Databricks workspace and access the specified catalog and schema.
   2. A failed test indicates an issue with one or more parameters. Refer to the [Troubleshooting](doc:databricks#troubleshooting) section below for common errors.
2. Click Save to store the connection details.
3. After saving, navigate to the Import Connections dashboard and click [Create Import](doc:data-warehouse-import) to set up your first data import.

## Troubleshooting

If the Test Connection fails, use the following table to identify and resolve common issues:

| Symptom                          | Likely Cause                                            | Resolution                                                                              |
| :------------------------------- | :------------------------------------------------------ | :-------------------------------------------------------------------------------------- |
| Connection timeout               | Network/firewall is blocking the connection             | Ensure CleverTap IPs are whitelisted. Verify the Host value does not include https\://. |
| Authentication failed            | Invalid or expired PAT                                  | Generate a new PAT in Databricks and update the connection in CleverTap.                |
| Warehouse not found or inactive  | SQL Warehouse is stopped, or the HTTP Path is incorrect | Start the warehouse in Databricks or verify the HTTP Path from Connection Details.      |
| Catalog or schema not accessible | Missing USAGE permission                                | Grant USAGE on the catalog and schema to the PAT identity. See Configure Permissions.   |
| SELECT permission denied         | Missing SELECT permission on tables                     | Grant SELECT on the schema or specific tables. See Configure Permissions.               |

# FAQs

This section answers common questions related to managing BigQuery connections and imports within CleverTap.

### How can I delete a connection that has running imports?

Go to _Import Connections_, select the connection, click **Delete**, and review the running imports. If there are any imports in ready, scheduled, paused, or running state, it stops all these active imports associated with the connection. Once done, click **Delete** and confirm.

### How can I filter import connections?

Use the filters on _Import Connections_ to refine the list:

- **Connected On**: Filter by creation date.
- **Connected By**: Filter by the user who created the connection.

### How can I whitelist IPs for CleverTap integration?

To ensure seamless communication between CleverTap and your systems, whitelist the required IP ranges. To access the list of IPs to whitelist for import integrations, refer to [CleverTap IP Ranges](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration).

### What happens when my PAT expires?

When the Personal Access Token expires, CleverTap will no longer be able to authenticate with Databricks and all active imports will fail. To resolve this, generate a new PAT in Databricks, then update the CleverTap connection by editing it and replacing the old token with the new one.

### Can I use the same Databricks connection for multiple imports?

Yes. A single Databricks connection in CleverTap can be used to create multiple import configurations, each reading from different tables within the same catalog and schema
