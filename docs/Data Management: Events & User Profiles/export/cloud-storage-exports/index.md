---
title: Cloud Storage
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
# Overview

This section introduces the export methods that deliver CleverTap data directly to your cloud storage. This page provides an overview of the supported storage partners and export types so you can choose the correct approach for receiving profile or event data in your preferred cloud environment.

CleverTap supports exporting raw event and profile data to leading cloud storage platforms. These exports let you move data into your existing data lakes, warehouses, or BI tools, maintain independent backups for compliance and audits, and analyze further using raw user and event data. Exports can be scheduled or triggered as one-time deliveries and are available in standard file formats, including JSON, CSV, XML, and Parquet.

## Supported Storage Partners

This section outlines the storage platforms supported for file-based exports.

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
  .icon {
    width: 24px;
    height: 24px;
    stroke: #2b2e33;
    flex-shrink: 0;
  }
  .name {
    font-size: 1rem;
    font-weight: 600;
    color: #2b2e33;
  }
</style>
<div class="grid">
  <a href="https://docs.clevertap.com/docs/aws-s3-configuration" class="integration-card">
   <div class="name">Amazon S3</div>
  </a>
	<a href="https://docs.clevertap.com/docs/gcp-configuration" class="integration-card">
  <div class="name">Google Cloud Platform (GCP)</div>
  </a>
	<a href="https://docs.clevertap.com/docs/microsoft-azure-configuration" class="integration-card">
  <div class="name">Microsoft Azure</div>
  </a>
</div>
`}</HTMLBlock>

## Export Types

CleverTap offers separate export flows for events and profiles, plus a legacy combined flow that remains fully available. Choose the one that matches your data needs. Failure notifications work the same way across all flows, documented under Status Alerts for Exports.

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
	<a href="https://docs.clevertap.com/docs/profile-exports" class="integration-card">
  <div class="name">Profile Exports</div>
  </a>
	<a href="https://docs.clevertap.com/docs/event-and-profile-exports" class="integration-card">
  <div class="name">Profile and Events (Legacy)</div>
  </a>
</div>
`}</HTMLBlock>

The following table provides details related to different export types:

| Export Type                                                                              | Description                                                                                                                                                                                                                                                                                                                           |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Event Exports](https://docs.clevertap.com/docs/event-export)                           | Event Exports lets you ship event data out as CSV, JSON, XML, or Parquet with full control over folder structure, file naming, identity selection, user properties and which events and properties are included. Run them one-time (up to 365 days back) or on a recurring 4/8/12/24-hour schedule with optional historical backfill. |
| [Profile Exports](https://docs.clevertap.com/docs/profile-exports)                       | Profile Exports lets you ship profile data out as CSV, JSON, XML, or Parquet with full control over folder structure, file naming, identity selection, and which properties are included. Run them one-time (complete dump) or on a recurring (24-hour) schedule.                                                                     |
| [Profile and Events (Legacy)](https://docs.clevertap.com/docs/event-and-profile-exports) | Legacy event and profile exports let you ship events or profile data out as CSV, JSON, XML, or Parquet file format.                                                                                                                                                                                                                   |

<Callout icon="📘" theme="info">
  ### New Flows vs. Legacy

  [Event Exports](https://docs.clevertap.com/docs/event-export) and [Profile Exports](https://docs.clevertap.com/docs/profile-exports) are the current recommended flows for exporting data from CleverTap. Older [Profile and Events (Legacy)](https://docs.clevertap.com/docs/event-and-profile-exports) exports will be keep running and If you prefer the older flow or need legacy event exports specifically, you can still switch to it at any time. However, it is important to note that the legacy export will eventually be deprecated, so it is advisable to start migrating to the new methods as soon as possible.
</Callout>

<Callout icon="📘" theme="info">
  ### Export Alerts

  CleverTap monitors your exports and send alerts on emails or send Webhook for different conditions. For details, see [Status Alerts for Exports](https://docs.clevertap.com/docs/status-alerts-for-exports).
</Callout>

<br />