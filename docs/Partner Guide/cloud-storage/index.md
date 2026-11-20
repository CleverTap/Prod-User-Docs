---
title: Cloud Storage
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---


# Overview

CleverTap integrates with major cloud storage platforms to support both data import and export. You can bring customer data into CleverTap from files stored in your cloud bucket, or export CleverTap profile and event data directly to your preferred storage destination. This page covers the supported partners and links to setup, configuration, and data management documentation for each flow.

## Key Benefits

The following are the key benefits of connecting CleverTap with cloud storage.

- **No Live Database Connection Required**<br />Import data directly from CSV files stored in your cloud bucket or export CleverTap data to your storage destination without setting up or maintaining a direct database connection.

- **Works with Any Data Pipeline**<br />Cloud storage integration is compatible with any workflow that can read from or write to a cloud bucket. Whether your data comes from an ETL tool, a batch process, or a custom script, it can move seamlessly between your systems and CleverTap.

- **Historical and Batch Data Ingestion**<br />Import historical records, perform one-time data migrations, or run periodic bulk updates to keep CleverTap user profiles and events in sync with your source systems.

- **Automated File Pickup**<br />Configure recurring import schedules to automatically detect and process new files from your storage bucket based on file name and timestamp patterns, without manual intervention.

- **Flexible Export Options**<br />Export CleverTap user profiles and event data to your cloud storage bucket on a scheduled basis. Choose from enhanced Profile Exports or the Legacy Profile and Events export flow depending on your data requirements.

## Import

Connect your cloud storage bucket to CleverTap to import customer data from CSV files. Select your storage provider below to configure the connection.

<HTMLBlock>{`
<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1rem;
    padding: 0 1rem;
    max-width: 100%;
    margin: 0 auto;
  }
  .integration-card {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 1.5rem 1rem;
    min-height: 64px;
    background: #fff;
    border-radius: 12px;
    border: 1px solid rgba(0, 0, 0, 0.08);
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.2s ease-in-out;
    text-decoration: none;
  }
  .integration-card:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  }
  .name {
    font-size: 1rem;
    font-weight: 600;
    color: #2b2e33;
  }
</style>
<div class="grid">
  <a href="doc:aws-s3-configuration" class="integration-card">
    <div class="name">Amazon S3</div>
  </a>
  <a href="doc:gcp-configuration" class="integration-card">
    <div class="name">Google Cloud Platform</div>
  </a>
  <a href="doc:microsoft-azure-configuration" class="integration-card">
    <div class="name">Microsoft Azure</div>
  </a>
</div>
`}</HTMLBlock>

### Set Up File-Based Import

Once your storage connection is configured, use the following steps to set up and manage your import jobs in CleverTap.

<HTMLBlock>{`
<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1rem;
    padding: 0 1rem;
    max-width: 100%;
    margin: 0 auto;
  }
  .integration-card {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 1.5rem 1rem;
    min-height: 64px;
    background: #fff;
    border-radius: 12px;
    border: 1px solid rgba(0, 0, 0, 0.08);
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.2s ease-in-out;
    text-decoration: none;
  }
  .integration-card:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  }
  .name {
    font-size: 1rem;
    font-weight: 600;
    color: #2b2e33;
  }
</style>
<div class="grid">
  <a href="doc:create-file-based-import" class="integration-card">
    <div class="name">Configure Import</div>
  </a>
  <a href="doc:map-data-for-file-based-import" class="integration-card">
    <div class="name">Map Data</div>
  </a>
  <a href="doc:map-data-for-file-based-import#perform-dry-run-recommended" class="integration-card">
    <div class="name">Perform Dry Run</div>
  </a>
  <a href="doc:schedule-file-based-import" class="integration-card">
    <div class="name">Schedule Import</div>
  </a>
  <a href="doc:import-listing-and-stats-for-file-based-import" class="integration-card">
    <div class="name">Import Listing and Stats</div>
  </a>
</div>
`}</HTMLBlock>

## Export

Export CleverTap user profiles and event data to your cloud storage bucket. Select your storage provider below to configure the connection.

<HTMLBlock>{`
<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1rem;
    padding: 0 1rem;
    max-width: 100%;
    margin: 0 auto;
  }
  .integration-card {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 1.5rem 1rem;
    min-height: 64px;
    background: #fff;
    border-radius: 12px;
    border: 1px solid rgba(0, 0, 0, 0.08);
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.2s ease-in-out;
    text-decoration: none;
  }
  .integration-card:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  }
  .name {
    font-size: 1rem;
    font-weight: 600;
    color: #2b2e33;
  }
</style>
<div class="grid">
  <a href="doc:aws-s3-configuration" class="integration-card">
    <div class="name">Amazon S3</div>
  </a>
  <a href="doc:gcp-configuration" class="integration-card">
    <div class="name">Google Cloud Platform</div>
  </a>
  <a href="doc:microsoft-azure-configuration" class="integration-card">
    <div class="name">Microsoft Azure</div>
  </a>
  <a href="doc:amazon-eventbridge" class="integration-card">
    <div class="name">Amazon EventBridge</div>
  </a>
</div>
`}</HTMLBlock>

### Configure Data Export

Once your storage connection is configured, use the following docs to set up and manage your exports from CleverTap.

<HTMLBlock>{`
<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1rem;
    padding: 0 1rem;
    max-width: 100%;
    margin: 0 auto;
  }
  .integration-card {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 1.5rem 1rem;
    min-height: 64px;
    background: #fff;
    border-radius: 12px;
    border: 1px solid rgba(0, 0, 0, 0.08);
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.2s ease-in-out;
    text-decoration: none;
  }
  .integration-card:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  }
  .name {
    font-size: 1rem;
    font-weight: 600;
    color: #2b2e33;
  }
</style>
<div class="grid">
  <a href="https://docs.clevertap.com/docs/event-export" class="integration-card">
    <div class="name">Event Exports</div>
  </a>
  <a href="doc:profile-exports" class="integration-card">
    <div class="name">Profile Exports</div>
  </a>
  <a href="doc:event-and-profile-exports" class="integration-card">
    <div class="name">Profile and Events (Legacy)</div>
  </a>
</div>
`}</HTMLBlock>

<Callout icon="📘" theme="info">
  ### Profile Exports vs. Profile and Events (Legacy)

  CleverTap supports two export flows depending on your data requirements:

  - [**Profile Exports**](doc:profile-exports): The enhanced export flow that supports exporting user profiles with improved flexibility and structure.
  - [**Profile and Events (Legacy)**](doc:event-and-profile-exports): Supports exporting both events and user profiles.
</Callout>

<br />