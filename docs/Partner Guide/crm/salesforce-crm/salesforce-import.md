---
title: Salesforce Import
excerpt: >-
  Learn how to sync both standard and custom Salesforce objects with CleverTap
  to enrich user profiles, enable precise segmentation, and power lifecycle
  campaigns, either in real time or on your preferred schedule.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Connecting your Salesforce CRM to CleverTap lets you bring CRM records into CleverTap to:

- Build a unified view of each customer that combines CRM data with app/web behavior.
- Segment users by CRM attributes (lead status, deal stage, subscription tier, and so on).
- Trigger CleverTap Journeys and Campaigns from CRM events (a new Opportunity, a closed Case, a renewed Subscription).
- Backfill historical CRM records so segmentation works from day one. &#x20;

<Callout icon="📘" theme="info">
  #### Salesforce Add-on

  Salesforce Import is available as an Add-On. To enable this add-on for your project, contact your Account Executive or Customer Success Manager. For trial, you can download the application from the AppExchange and use it for 30 days.
</Callout>

The integration is delivered through the [CleverTap-managed Package](https://appexchange.salesforce.com/appxListingDetail?listingId=6d0bd1f7-9c5c-484d-87cd-cfc0c68827ca\&tab=e) (namespace: CleverTap), which you install in your Salesforce org from the AppExchange.


<Image src="https://files.readme.io/c937c5bd9e25824da3fd3070b5956b22e4416ad1946bb2a9fc78b313c9e963ab-salesforce-import-clevertap.png" align="center" caption="Salesforce Import Workflow" border={true} />


# &#x20;CleverTap-Managed Package

The following table shows the components present inside the CleverTap-managed Package:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Component
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Pre-built Apex Triggers
      </td>

      <td>
        Fires automatically on standard objects. They are ready to use upon installation. For more information about supported standard objects, refer to [Supported Objects for Import](doc:salesforce-import#supported-objects-for-import).
      </td>
    </tr>

    <tr>
      <td>
        Invocable Apex Action "Send Custom Object to CleverTap"
      </td>

      <td>
        Lets you sync any custom object via a Record-Triggered Flow that you create once.
      </td>
    </tr>

    <tr>
      <td>
        CleverTap Settings tab
      </td>

      <td>
        Serves as the native Salesforce UI for creating connections, mapping fields, setting filters, and choosing a delivery mode.
      </td>
    </tr>

    <tr>
      <td>
        CleverTap Event Logs tab
      </td>

      <td>
        Provides a per-record log of every sync attempt, including the request payload and the CleverTap response, for monitoring and troubleshooting.
      </td>
    </tr>

    <tr>
      <td>
        Batch Drainer (Scheduled Apex)
      </td>

      <td>
        - Optional.
        - Queues records in Salesforce and sends them on a cadence you pick (5 to 60 minutes) instead of one callout per change.
      </td>
    </tr>
  </tbody>
</Table>

# Supported Objects for Import

The import flow supports the following standard objects out of the box, along with any custom objects in your Salesforce org:

- **Standard Objects with Prebuilt Triggers**: Lead, Contact, Account, Opportunity, Case, Campaign, Event, Task, Campaign Member, Service Appointment, Quote, Contract, Order, Product, Price Book, Asset, and Opportunity Product.
- **Custom Objects**: Any custom object in your org is supported. They appear in the Source Entity dropdown with a `[Custom]` prefix and require a one-time Record-Triggered Flow setup.
- **Objects excluded from Source Entity Dropdown**:
  - Custom Settings
  - Custom Metadata Types (objects ending in `__mdt`)
  - Platform Events (objects ending in `__e`)
  - Big Objects (objects ending in `__b`)
  - External Objects (objects ending in `__x`)
  - The internal objects of the package (`Config__c`, `Event__c`, `Sync_Configuration__c`, `Sync_Queue__c`, `Mapping__c`, `CleverTap_Passcode__c`)

# Prerequisites

Before configuring the integration, ensure you have the following:

### Salesforce

- A valid Salesforce account on Enterprise, Unlimited, or Performance edition with API access enabled.
- Permission to access Object Manager, App Manager, Flow Builder, and Apex Classes.
- The CleverTap-managed package is installed from AppExchange (namespace: CleverTap).
- The CleverTap Integration Access permission set is assigned to users configuring the integration.

### CleverTap

- Admin access to the CleverTap dashboard.
- Find the following details from your CleverTap dashboard under Settings > Project:


  <Image src="https://files.readme.io/b1d94d561559ff350ae681e993d74ca58e10450f17b2864d3d222d96f02a6625-image.png" alt="CleverTap Project Details" align="center" caption="CleverTap Project Details" border={true} />


  | Field        | Description                                                                                                                                                                             |
  | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
  | Account ID   | CleverTap Project ID.                                                                                                                                                                   |
  | API Passcode | Project's API passcode. For more information, refer to [Account Passcode](https://developer.clevertap.com/docs/concepts#passcode) in CleverTap docs.                                    |
  | Region       | The data center hosting your account (for example, `in1`, `us1`, `eu1`, `sg1`). For more information, refer to [API Endpoints](https://developer.clevertap.com/docs/idc#api) by region. |

<br />

# Import Standard Objects

The following are the key steps to import data from Salesforce to CleverTap:

1. [Connect Salesforce to CleverTap Account](doc:salesforce-import#connect-salesforce-to-clevertap-account).
2. [Configure Sync for Either Profiles or Events](doc:salesforce-import#configure-sync-for-profiles-or-events).
3. (Optional) [Select Delivery Mode](doc:salesforce-import#select-delivery-mode) and [Add Filter to Control Volume](doc:salesforce-import#configure-field-level-filters).
4. [Create Record-Triggered Flow for Custom Objects](doc:salesforce-import#create-record-triggered-flow).
5. [Verify Imported Records in CleverTap](doc:salesforce-import#verify-imported-records-in-clevertap).

## Connect Salesforce to CleverTap Account

The CleverTap _Settings_ tab shows the Connections list. Each connection points to one CleverTap project. To connect Salesforce to the CleverTap account, perform the following steps:

1. In Salesforce, open the App Launcher and search for "CleverTap".

2. Select _CleverTap_ from the results.

3. Open the CleverTap _Settings_ tab and click **Add New Connection**.

4. Enter the following integration details: Region, Connection Name, Account ID, API Passcode.


   <Image src="https://files.readme.io/0efa1a4bb21e4986d16a5366efd72f39ef0e867286f4beadd4d5744f95e5124d-Add_New_Connection.svg" align="center" caption="Add New Connection on Salesforce Dashboard" border={true} />


5. Click **Save**. The connection now appears in the Connections list. You can either delete, edit, or map a Field.


   <Image src="https://files.readme.io/8eaf10de7da9a079882953bc9757f64988844d717868adaa6365b2d35fce737b-CleverTap_Settings_Tab_on_Salesforce_Dashboard.png" align="center" border={true} />


<Callout icon="📘" theme="info">
  #### Multiple Salesforce Connections

  You can add multiple connections. This is useful when you want to route different Salesforce data to different CleverTap projects. For example, one connection per region or business unit.
</Callout>

## Configure Sync for Profiles or Events

To import data from Salesforce, perform the following steps:

1. In CleverTap Settings, click **Map Field** for the relevant connection.
2. Click **Add New Sync** and enter the  following details:


   <Image src="https://files.readme.io/d0a50f9c0b67f8d06a72784f82b4883d95c00f4086088457c7025ef22be9e4ad-Salesforce_sync.svg" align="center" caption="Add New Sync" border={true} />


   <Table align={["left","left"]}>
     <thead>
       <tr>
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
           Sync Name
         </td>

         <td>
           Enter the name for your sync, for example, Lead Profile Sync.
         </td>
       </tr>

       <tr>
         <td>
           Sync Type
         </td>

         <td>
           Select _salesforce_to_clevertap_.
         </td>
       </tr>

       <tr>
         <td>
           Source Entity
         </td>

         <td>
           Select the Salesforce object, for example, Lead.
         </td>
       </tr>

       <tr>
         <td>
           Target Entity
         </td>

         <td>
           Available options:

           - **Profiles**: Select Profiles to push Salesforce records into CleverTap as user profile records. This helps build a richer customer view for more effective segmentation and engagement.
           - **Event**: Select Event to capture an activity at a point in time, for example, an Opportunity created, a Case closed, a subscription renewed, and record it against the user profile in CleverTap. You should select _Event_ when you want to trigger a campaign from something that happened in Salesforce, or when you are doing lifecycle analytics.
         </td>
       </tr>

       <tr>
         <td>
           Status
         </td>

         <td>
           Select _Active_.
         </td>
       </tr>
     </tbody>
   </Table>
3. (Optional) Configure the [Delivery Mode](doc:salesforce-import#select-delivery-mode) and [Filter](doc:salesforce-import#configure-field-level-filters). To start with, you can keep the defaults as is.
   1. Click **Next**. The field mapping screen opens.


      <Image src="https://files.readme.io/950026f9544ad56c96151b918b0c6e6329845a551163209315b8b4b3a21b5f5d-Field_Mapping.svg" align="center" caption="Map Fields for Sync" border={true} />


      <Table align={["left","left"]}>
        <thead>
          <tr>
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
              Customer ID
            </td>

            <td>
              This is the identifier CleverTap uses to look up or create the profile. Map it to a stable, unique field, for example, `Lead.Email`. Avoid mutable fields such as phone numbers or the Salesforce record ID.

              For more information, refer to [Best Practices for Identity Mapping](doc:salesforce-import#best-practices).
            </td>
          </tr>

          <tr>
            <td>
              Event Name
            </td>

            <td>
              For Event import, an additional Event Name field must be mapped. It can be either a static string, such as Opportunity Created, or a mapped field. If you do not map it, the package uses a sensible default (`sf_opportunity` for Opportunity, `sf_activity_event` for Event, and so on).
            </td>
          </tr>

          <tr>
            <td>
              Additional Fields
            </td>

            <td>
              - For profiles import, map any other Salesforce fields you want to map in CleverTap (for example, FirstName, LastName, LeadSource, Status, Company).
              - For event import, map the event properties you want to track. For an Opportunity event, the fields are typically Amount, StageName, CloseDate, and so on.

              **Note**: Event mappings are additive. Every field you map here becomes an event property in CleverTap, which marketers can then segment or personalize.
            </td>
          </tr>
        </tbody>
      </Table>
4. Click **Save**. The sync becomes live immediately. Any record change received by the Apex trigger is now evaluated by the filter and routed through the selected delivery mode.

<Callout icon="📘" theme="info">
  #### Note

  You can create multiple sync configurations for the same source entity. For example, one sync can send Lead updates as profile updates, while another sends Lead status changes as events. If overlapping active configurations are detected, the package alerts you so you can review and disable any unintended ones.
</Callout>

## Select Delivery Mode

Every sync configuration runs in one of two modes. You set this on the sync basics screen, before field mapping.


<Image src="https://files.readme.io/bbba5a300657af7a861ba8e39de27cfef7650a52bc3a91bceb3ed1de1c65333c-choose-delivery-mode-clevertap.png" align="center" caption="Choose Delivery Mode" border={true} />


- **Real-Time**: Default. Every record change triggers an immediate HTTP callout to CleverTap. This is the right default for most use cases. Changes appear in CleverTap within seconds. Select this option if the data drives a live Journey or Campaign trigger.
  - Pros: Lowest latency. The marketing team can respond to CRM activity in real time.
  - Cons: One callout per record change. High-volume orgs that update thousands of Leads per hour can come close to the Salesforce daily callout limit (100K on Enterprise, 200K on Unlimited).
- **Batch**: Select this option if you are running profile enrichment, segmentation backfills, or anything that does not need to land in CleverTap within seconds. Changes are queued inside Salesforce (in a staging table called `Sync_Queue__c`) and drained on a schedule you pick. One scheduled job collects all pending rows for each sync and sends them to CleverTap in one callout per record.
  - Pros: Predictable throughput. Best for high volume. Failed records retry automatically up to **5 times**.
  - Cons: Data lags by your selected cadence. Uses scheduled Apex slots. For more information, refer to [Configure Batch Drainer Schedule](doc:salesforce-import#configure-batch-drainer-schedule). When you select this option, the following fields appear:
  - **Batch Size**: The number of records sent in a single drainer call. The default value is **100**, and the maximum is **1000**.
  - Batch Frequency Minutes: Indicates how often the drainer runs. You can select from the following options: 5, 10, 15, 20, 30, or 60.

## Configure Field-Level Filters

Filters let you sync only the records that matter. Set per sync configuration. The following are the available field-level filter options:


<Image src="https://files.readme.io/5e0e0cf94a60ecae681822e421aef1231a9d79c9c00656d5b27a10ab4235b7d9-Filter_Modes_-_What_Gets_Synced.png" align="center" caption="Filter Modes" border={true} />


- **None**: Default. Syncs every change.
- **Specific Fields Changed**: Sync only fires when one of your watched fields actually changes. Pick the fields from a dual-listbox.

  For example, `Watched fields` = `Status`, `Email`. A Lead whose `Description` gets edited will not fire a sync. A Lead whose `Status` changes from `Open` to `Qualified` does.
- **Condition Based**: Sync only fires when the record matches a condition you write. Supports the following operators:

  | Operator             | Meaning            | Example                                       |
  | :------------------- | :----------------- | :-------------------------------------------- |
  | `=`                  | equals             | `Status = 'Qualified'`                        |
  | `!=`                 | not equals         | `Country != 'USA'`                            |
  | `>`, `<`, `>=`, `<=` | numeric comparison | `AnnualRevenue >= 1000000`                    |
  | `AND`, `OR`          | compound           | `Status = 'Qualified' AND LeadSource != null` |
  | `null`               | null check         | `LeadSource != null`                          |

  - String values must be wrapped in single quotes: Status = 'Qualified'.
  - Numbers are unquoted: NumberOfEmployees > 50.

  The package validates the expression live as you type and blocks you from clicking Next if the expression is malformed (unbalanced quotes, unknown field name, trailing AND, and so on). Use the Show available fields button next to the editor to see the valid field names on the source object.<br />You can use this with both Standard and Custom objects. Condition evaluation only needs the current record values, so it works fine in both the Trigger path and the Flow-invocable path.
- **Field and Condition**: Both conditions must be met: at least one watched field must change, and the defined condition must evaluate to true.

  For example:

  Watched fields: `Status`, `LeadSource` Condition: Status = `Qualified`

  **Sync fires when**:

  - `Status` changes to `Qualified` (watched field changed + condition now matches)
  - `LeadSource` changes for a Lead that is already `Qualified` (watched field changed + condition continues to match)

  **Sync does NOT fire when**:

  - `Description` changes on a Qualified Lead (no watched field changed)
  - `Status` changes to `Open` (watched field changed, but condition no longer matches) <br />

  <Callout icon="📘" theme="info">
    #### Note

    If you need to sync records only when a specific field changes on a custom object, move this check to the Flow’s Entry Conditions instead of relying on the CleverTap package filter.

    In Flow Builder, configure the Entry Conditions of the trigger as follows:

    `ISCHANGED({!$Record.Status__c}) || ISNEW()`

    This ensures the Flow runs only when the field changes (or on record creation), preventing the invocable action from being triggered unnecessarily. As a result, the CleverTap package processes only the relevant record updates.
  </Callout>

## Configure Batch Drainer Schedule

When you pick Batch as the delivery mode, the package queues records in Salesforce and drains them at a scheduled interval. To configure the Batch Drainer Schedule, perform the following steps:

1. Go to _CleverTap Settings_  > Batch Scheduler.
2. Select the action you want to perform:


   <Image src="https://files.readme.io/fa9b4adea9d177d35c48931540876a186251d7f3511a82ff0c5cab2601a85031-Batch_Drain_Schedule.svg" align="center" caption="Configure Batch Drain Schedule" border={true} />


   | Field         | Description                                                                                                |
   | :------------ | :--------------------------------------------------------------------------------------------------------- |
   | Schedule      | Starts the drainer at the current cadence. Visible when no drainer is running.                             |
   | Reschedule    | Stops the current drainer and re-creates it at the new cadence. Visible when a drainer is running.         |
   | Unschedule    | Stops the drainer. Pending records stay in the queue and resume draining the next time you click Schedule. |
   | Run Drain Now | Fires the drainer once immediately, without waiting for the next scheduled drain. Useful for testing.      |

### Batch Scheduler

The following table lists the components present under the _Batch Scheduler_ section:

| Component        | Description                                                                                                                                       |
| :--------------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| Status           | Can be `Scheduled` or `Not Scheduled`                                                                                                             |
| Cadence          | The intervals at which the scheduler runs. For example, every 15 minutes.                                                                         |
| Next run         | When the drainer fires next (Local Time).                                                                                                         |
| Pending in queue | The number of records waiting to be sent. A badge in orange if the value is more than 0.                                                          |
| N scheduled jobs | Number of cron jobs the package created. For more information, refer to [Multiple Scheduled Jobs](doc:salesforce-import#multiple-scheduled-jobs). |

### Multiple Scheduled Jobs

Multiple scheduled jobs are created for a single cadence due to the Salesforce platform limitation. Salesforce requires a fixed-minute value in Apex cron expressions and does not support shorthand intervals such as “every 5 minutes” (for example, \*/5). To achieve sub-hourly schedules, the system creates one job per minute interval.

For example, for a 5-minute cadence, it creates 12 jobs (one for each 5-minute slot in an hour). Similarly, for a 15-minute cadence, it creates 4 jobs.

All these jobs run the same process and together deliver the desired frequency.

#### Impact

Scheduled jobs count toward Salesforce’s limit of 100 scheduled Apex jobs per org.

| Cadence | Jobs Scheduled |
| ------- | -------------- |
| 5 min   | 12 jobs        |
| 10 min  | 6 jobs         |
| 15 min  | 4 jobs         |
| 60 min  | 1 job          |

#### Choosing Right Cadence

| Use Case                            | Recommended Cadence | Jobs Scheduled |
| ----------------------------------- | ------------------- | -------------- |
| Near real-time updates              | 5 min               | 12             |
| Low latency with lower resource use | 10 min              | 6              |
| Standard operations                 | 15 min              | 4              |
| Periodic refresh                    | 60 min              | 1              |

**Start with a 15-minute cadence. It offers a good balance between data freshness, system load, and job usage.**

# Import Custom Objects

Custom objects extend Salesforce beyond the standard data model. As the package cannot include triggers for objects that do not exist at build time, syncing custom objects requires you to set up a Record-Triggered Flow that calls an invocable Apex action (one-time setup per object).

To import custom objects from Salesforce to CleverTap, perform the following steps:

1. Configure Sync.
2. [Create Record-Triggered Flow](doc:salesforce-import#create-record-triggered-flow).
3. [Verify Custom Object Filter](doc:salesforce-import#verify-custom-object-sync).

## Prerequisites

In addition to the usual requirements, the following are prerequisites for importing custom objects:

- The custom object exists in your org (for example, `Property_Lead__c`).
- The fields you want to sync already exist on it.
- Access to Flow Builder in Setup.

## Configure Sync

To configure the sync, perform the following steps:

1. Go to _CleverTapSettings_ and click **Map Field** for the relevant connection.
2. Click **Add New Sync** and enter the following details:
   - Source Entity: Choose your custom object. Custom objects show with a \[Custom] prefix in the dropdown.
   - Target Entity: Select Profile or Event.
3. Click **Next**, configure the following field mappings and click **Save**:
   - Customer ID: This field must map to a unique identifier field on your custom object.
   - Event Name: Mapping for this field is required only if the _Target Entity_ is an event. It can have a static value or be mapped from a field.
   - Additional Fields: Map any custom fields to CleverTap properties.

## Create Record-Triggered Flow

To create Record-Triggered Flow, perform the following steps:

1. Go to _Setup_ from the Salesforce dashboard, then search for _Flows_ in Quick Find.
2. Click **New**, select _Record-Triggered Flow_ and click **Create**.
3. Configure the following Trigger:

   | Field                 | Description                              |
   | :-------------------- | :--------------------------------------- |
   | Object                | Your custom object.                      |
   | Trigger the Flow When | Select _A record is created or updated_. |
   | Optimize the Flow For | Select _Actions and Related Records_.    |
4. Click **Done**.
5. Add CleverTap Sync action:
   1. Click `+` and select _Action_.
   2. Search for _Send Custom Object to CleverTap_ and configure the inputs:


      <Image src="https://files.readme.io/7d9afa27b53641da272b5c0e611619985712fb5a62022c74cafb6c169c256fa1-Salesforce_Setup.svg" align="center" caption="Configure Inputs for CleverTap Sync Action" border={true} />


      - **Record ID**: Set to `{!$Record.Id}` (the ID of the triggering record). If the visual picker doesn't show it, click the toggle to switch to manual entry and type `{!$Record.Id}` literally.

        <Callout icon="📘" theme="info">
          #### Important

          Do NOT pick `Owner ID`, `Created By ID`, or any other relationship field here. The Record ID must be the ID of the custom object record itself. If `{!$Record.Id}`  does not appear in the visual picker, click the toggle icon to switch to manual entry mode and type `{!$Record.Id}`.
        </Callout>
      - **Object API Name**: Enter the API name of your custom object as plain text, for example `CleverTap__Property_Lead__c`. This must be a static string, not a field reference.

        <Callout icon="📘" theme="info">
          #### Important

          In a namespaced org (which yours is, because the package is installed), custom objects you create carry the `CleverTap__` namespace prefix. A custom object named Property Lead has the API name `CleverTap__Property_Lead__c`, not `Property_Lead__c`. Verify the exact API name in _Setup_ > _Object Manager_ > _\[Your Object]_ > _Details_.
        </Callout>
   3. Give the action a label (for example, "Sync to CleverTap"), then click **Done**.
6. Click **Save**, give the flow a name (for example, _Sync Property Lead to CleverTap_), and then click **Activate**.

## Verify Custom Object Sync

To verify the custom object sync, perform the following steps:

1. Open the custom object tab (for example, Property Leads) and create a new record.
2. Open the CleverTap Event Logs tab.
3. Find the log entry for the new record.
4. Click the row dropdown, then select _View Details_ to view the request and response. A status of Success means the record reached CleverTap.

You can verify the same on the CleverTap dashboard under _Segments_ > _Find People_ . Search the profile by the identity value you mapped.

<Callout icon="📘" theme="info">
  #### Points to Remember for Custom Object Filter

  The Flow-invocable path does not give the Apex action access to `Trigger.oldMap`. Flows pass only the current record, not the prior state. As a result, filter modes behave differently for custom objects:

  | Filter Mode             | Behavior                                                                        |
  | :---------------------- | :------------------------------------------------------------------------------ |
  | None                    | Works as expected.                                                              |
  | Specific Fields Changed | Not supported. Changes cannot be detected, so all updates are synced            |
  | Condition Based         | Works as expected. Evaluates current record values only.                        |
  | Field And Condition     | Condition works, but field-change check does not. Behaves like Condition Based. |
</Callout>

# Verify Imported Records in CleverTap

After a record is created or updated in Salesforce and a matching sync is active, verify that the data reached CleverTap.

1. On the Salesforce dashboard, open the _CleverTap Event Logs_ tab.
2. Find the row for the record you are verifying.
3. Click the dropdown and select _View Details_. The following panel displays:
   - Status: Success or Failure
   - Response: The body CleverTap returned.
   - Request: The payload sent (so you can confirm the field mapping resolved correctly).
4. Copy the identity value of the record (the `Identity` mapping, typically the Email).
5. From the CleverTap dashboard, go to _Segments_ > _Find People_ and search the profile by Identity.
6. Paste the identity value into the input field.
7. Click **Find**. If the sync is successful, the matching profile appears with the attributes you mapped. For event syncs, check the _Activity_ tab.

# Historical Sync

Historical sync backfills previously captured Salesforce records into CleverTap. Use this once, right after you set up a new sync, to seed CleverTap with records that existed before the integration was live.

<Callout icon="📘" theme="info">
  #### Note

  Historical sync processes all existing records of the selected object that match the filter. On large objects this can take a while, test with a narrow filter first (for example, `CreatedDate = LAST_N_DAYS:7`) before doing the full backfill.
</Callout>

To trigger historical sync, perform the following steps:

1. Go to CleverTap Settings.
2. Under _Integration Sync List_, find the sync you want to backfill.
3. Click the dropdown next to the sync name and select _Historical Sync_. Historical sync is supported for both standard and custom objects, provided the sync configuration exists and is Active.

You can see the results:

- **On Salesforce dashboard**: CleverTap Events Logs. It displays the per-record success/failure.
- **On CleverTap dashboard**: Segments > Find People. It displays the records available for segmentation immediately.

# Event Logs & Monitoring

The _CleverTap Event Logs_ tab is your single source of truth for sync activity. Every sync attempt (Real-Time or Batch) produces a log row. Each row displays the following details:

| Column       | Description                                                                   |
| :----------- | :---------------------------------------------------------------------------- |
| Record       | The Salesforce record the log is for.                                         |
| Type         | The source entity, for example, Lead, Contact, your custom object, and so on. |
| Status       | `Success` or `Failure`.                                                       |
| Created Date | When the sync was attempted.                                                  |

You can view the following details by clicking the dropdown and selecting **View Details**.

- Request body: The JSON payload that was sent to CleverTap. Confirms that your field mappings produced the values you expect.
- Response body: What CleverTap returned. On failure, this usually tells you exactly what went wrong (invalid identity, unknown event property, rate-limit error, and so on).

# Error Responses

## Common Failure Responses

The following are the common failure responses:

| Response              | Description                                                | Resolution                                                                                        |
| :-------------------- | :--------------------------------------------------------- | :------------------------------------------------------------------------------------------------ |
| `Invalid identity`    | Customer ID mapping produced an empty or invalid value.    | Verify the mapping points to a populated, stable field.                                           |
| `Rate limit exceeded` | You are sending more than CleverTap's project rate allows. | Switch the sync to Batch mode, or lower the cadence.                                              |
| `Unknown event name`  | Event Name mapping produced an empty value.                | In the sync, set Event Name as a static string, or map it to a non-null field.                    |
| Network error         | Transient.                                                 | Record will retry on the next drainer tick (Batch mode) or on the next record change (Real-Time). |

# Best Practices

### Identity mapping

Accurate user attribution depends on consistent identity across syncs. Follow these rules when mapping Customer ID:

- **For Profile Imports**: Use the record's Email field (Lead.Email, Contact.Email) wherever possible. Emails are usually unique and stable. Avoid mutable fields like phone numbers, and avoid Salesforce record IDs — the same human has different IDs as a Lead versus a Contact, and your CleverTap profile would split.
- **For Event Imports**: Use the same identity field you used for the profile. If Lead profiles sync on Lead.Email, Opportunity events should also be attributed to Email (typically via the related Contact.Email), so events land on the right profile.
- **For Custom Objects**: Apply the same principle. Pick one stable, unique field per object and reuse it across the profile sync and any event syncs on that object.

CleverTap recommends having one identity field per person across profile and event sync. Also, before a full historical backfill, run a test sync with a narrow filter (for example, 10 records) and confirm the profiles appear correctly in CleverTap. You must write down your org's identity strategy somewhere your marketing, analytics, and CRM teams can find it.

### Avoid Duplicate Syncs for Same Object

If you create two Active Sync configurations for the same source entity, each record change will be sent twice. The package displays a warning when you save the second configuration and identifies the overlap. To resolve this, deactivate the unwanted configuration or use separate target entities (for example, one for profiles and one for events) so they can work together without duplicating data.

### Real-Time vs. Batch

A simple rule of thumb:

- For a Live campaign trigger, you can select Real-Time.
- For Profile enrichment/analytics/backfill, select Batch and start with a 15-minute cadence.
- In the case of Mixed needs for the same object, you can configure the following two syncs: Real-Time for the marketing-critical fields, and Batch for everything else.

### Filters to Save API Volume

If a sync fires on every record update (including noise such as Description updates), you end up consuming API volume. A simple Specific Fields Changed filter on the handful of fields that marketing actually cares about (Status, LeadSource, Email) can cut callout volume by 10x on an active org with no loss of information.

# Troubleshooting

### Records Not Syncing At All

| Issue                                                 | Cause                                                        | Resolution                                                                                           |
| :---------------------------------------------------- | :----------------------------------------------------------- | :--------------------------------------------------------------------------------------------------- |
| No event log appears after creating a record          | Your Record-Triggered Flow (custom object) is not activated. | Open the flow in Flow Builder and click **Activate**.                                                |
| No event log appears after updating a standard object | The sync is `Inactive`.                                      | Go to CleverTap Settings > Integration Sync List and check the _Status_ column.                      |
| No event log appears, even though the sync is Active  | The filter is rejecting the record.                          | Temporarily set Filter Mode to `None` and try again to isolate.                                      |
| The event log shows `failed` for every record         | The connection credentials or region are incorrect.          | Edit the Connection and verify Account ID, API Passcode, and Region against the CleverTap dashboard. |

### Custom Object-Specific

| Symptom                                                    | Cause                                                          | Resolution                                                                                                                                                                                         |
| :--------------------------------------------------------- | :------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| No event log appears after creating a record               | The Record-Triggered Flow is not activated.                    | Open the flow in Flow Builder and click **Activate**.                                                                                                                                              |
| No active sync configuration found                         | The sync for this custom object does not exist or is Inactive. | In CleverTap Settings, verify that the sync exists with Status `Active` and Source Entity matches the custom object's API name exactly.                                                            |
| Missing required input parameter: recordId                 | The Flow Record ID input is mapped to the wrong field.         | Edit the Flow action and set Record ID to `{!$Record.Id}` (not `Owner ID` or any relationship field).                                                                                              |
| Object API Name shows "bad value for restricted picklist"  | You're on an older version of the package.                     | Install the latest package version, the Source Entity field is unrestricted in current versions.                                                                                                   |
| Custom object doesn't appear in the Source Entity dropdown | Browser cache, or the object doesn't meet criteria.            | Hard-refresh the browser (Cmd+Shift+R or Ctrl+Shift+R). Ensure the object is accessible and queryable, and is not a Custom Setting, Metadata Type, Platform Event, Big Object, or External Object. |
| Error: "SOQL error on field name"                          | A custom field API name is misspelt in the sync mapping.       | Verify the field API name under _Setup_ > _Object Manager_ > _\[Your Object]_ > _Fields & Relationships_.                                                                                          |

### Batch/Scheduler

| Symptom                                                  | Cause                                                                                 | Resolution                                                                                                                                                                           |
| :------------------------------------------------------- | :------------------------------------------------------------------------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Pending queue count keeps growing and never drains       | No drainer is scheduled.                                                              | Go to CleverTap Settings > Batch Scheduler and click **Schedule**.                                                                                                                   |
| The queue drains, but records keep re-entering the queue | Trigger firing twice per record change (Lead Assignment Rules, workflows, and so on). | This is expected behavior, and the dedup-at-enqueue logic prevents duplicate sends. Check the actual CleverTap event count rather than the queue fire count.                         |
| Records marked `Failed` after 5 attempts                 | Configuration error or persistent CleverTap API issue.                                | Click **View Details** on the log entry to see the exact error. Fix the cause, then either delete the `failed` rows (they will not retry automatically) or re-enqueue them manually. |
| "Scheduled Apex limit exceeded" error when scheduling    | Your org has too many other scheduled jobs.                                           | Pick a longer cadence (60 min uses 1 slot vs 12 for a 5-min cadence), or reduce other unrelated scheduled Apex.                                                                      |

### Filter/Validation

| Symptom                                                   | Cause                                                  | Resolution                                                                                                                                                                                 |
| :-------------------------------------------------------- | :----------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "Next" button stays greyed out on the sync form           | Filter expression is invalid.                          | Check the inline error message under the expression editor. Common causes: unbalanced quotes, unknown field name, trailing `AND`/`OR`.                                                     |
| Specific Fields Changed does not affect the custom object | Flow-invocable path has no access to `Trigger.oldMap`. | Move the field-change check to the Flow Entry Conditions using `ISCHANGED()`. For more information, refer to [Verify Custom Object Sync](doc:salesforce-import#verify-custom-object-sync). |

# FAQs

The following are some of the frequently asked questions for Salesforce Import:

### What is historical data import?

Historical import backfills previously captured Salesforce records into CleverTap, making CRM data created before the integration was set up available for segmentation, analysis, and engagement. Works for both standard and custom objects.

### Can I create multiple sync configurations for the same Salesforce object?

Yes. The following are some of the use cases where you can create multiple sync configurations for the same Salesforce object:

- Push the same object to multiple CleverTap accounts (different regions or business units).
- Separate profile and event syncs from the same object (one profile-target, one event-target).
- Use different field mappings for different CleverTap use cases.

Each sync configuration operates independently, with its own mapping, target entity, connection, delivery mode, and filters. If you create overlapping active configurations, a warning is displayed so you can review and adjust if needed.

### How does Dedupe at enqueue work?

In Salesforce, it is common for triggers to fire multiple times during a single record creation. This happens because features such as Lead Assignment Rules, workflows, duplicate rules, and before-save Flows often perform an immediate follow-up update after the initial insert.

As a result, a newly created record may trigger:

- Once on insert
- Again, on the subsequent update, this is how Batch mode handles it.

To prevent duplicate sends, Batch mode deduplicates records at enqueue time. If a record already has a Pending queue entry for a given sync configuration, additional enqueue attempts are ignored.

For example, there are three new Leads, which means there will be three queue entries and three events in CleverTap (even if each trigger fires multiple times). Real-Time mode does not include this deduplication, as the callout happens synchronously within the trigger. If you see duplicate events in Real-Time mode, it likely means your org has automation that updates records immediately after insert.

To address this:

- Accept the duplicate behavior, or
- Add a Specific Fields Changed filter, or
- Switch the sync to Batch mode for built-in deduplication

### How do I sync custom objects?

Custom object sync requires two setup steps:

1. **Configure the sync** in CleverTap Settings, selecting your custom object from the Source Entity dropdown.
2. **Create a Record-Triggered Flow** in Salesforce that invokes the **Send Custom Object to CleverTap** action.

For more information, refer to [Import Custom Objects](doc:salesforce-import#import-custom-objects).

### Why don't custom objects sync automatically like Leads and Contacts?

Standard objects have pre-built Apex triggers included in the managed package. These fire automatically on create or update. Custom objects are created after the managed package is installed, and a managed package cannot include triggers for objects that do not yet exist. The invocable Apex action + Record-Triggered Flow combo achieves the same result; it is a one-time setup per custom object.

### What types of custom objects are supported?

Any standard custom data object. Automatically excluded: Custom Settings, Custom Metadata Types (`__mdt`), Platform Events (`__e`), Big Objects (`__b`), External Objects (`__x`), and internal package objects.

### What is the API name format for custom objects in a namespaced org?

When the CleverTap managed package is installed, custom objects you create carry the `CleverTap__ namespace` prefix. A custom object named Property Lead has the API name `CleverTap__Property_Lead__c`. Verify the exact name in Setup > Object Manager > \[Your Object] > Details > API Name.

### What happens when a sync fails?

Failed syncs land in CleverTap Event Logs with the CleverTap API response. Click **View Details** to see the request payload and the response body. In Batch mode, failures auto-retry up to 5 times before being marked Failed; in Real-Time mode, there is no automatic retry.

### Can I deactivate a sync without deleting it?

Yes. Go to _CleverTap Settings_ > _Integration Sync List_, click the dropdown next to the sync name, and select _Deactivate Sync_. The mapping is preserved, and you can reactivate it later.

### Does Real-Time mode have duplicate protection like Batch mode does?

No. Real-Time fires the callout synchronously inside the trigger; there is no queue to dedup against. If your org has automation that updates records right after insert (Assignment Rules, workflows, flows), Real-Time mode will see each trigger fire and make a callout for each. Use the Specific Fields Changed or Condition-Based filter to cut the noise, or switch to Batch mode, which does dedup.

### Why does Batch mode create so many scheduled jobs?

Salesforce's Apex scheduler rejects any "every N minutes" shorthand in cron expressions. To achieve sub-hourly cadence, the package creates one scheduled job per fire-minute (12 jobs for a 5-min cadence, 4 for a 15-min cadence, and so on). They all run the same code. For more information about how it affects your org's scheduled Apex limit, refer to [Configure Batch Drainer Schedule](doc:salesforce-import#configure-batch-drainer-schedule).

### How do I reduce callout volume on a high-traffic Salesforce org?

Three levers, in order of effectiveness:

- Add a Specific Fields Changed filter on the fields marketing actually cares about.
- Switch to Batch mode at 15 or 30-minute cadence.
- Use a Condition-Based filter to cut out records that aren't relevant to CleverTap at all (e.g. Status != 'Closed Lost').

### Can I edit a sync after it's live?

Yes, click **Edit** on the sync row. You can change filters, delivery mode, and mappings. Changes take effect immediately for all new record changes after save.
