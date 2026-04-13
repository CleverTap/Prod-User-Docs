---
title: Data Warehouse
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

The Data Warehouse section introduces the integrations that enable you to bring large volumes of data from your warehouse into CleverTap. It also provides an overview of the supported warehouse partners and the associated workflows for configuring imports, mapping fields, and scheduling automated data pipelines.

# Prerequisites

Before you begin, ensure you have the following:

* A data warehouse account integrated with CleverTap.
* Necessary permissions to create and manage imports.
* Access to the data warehouse database with correctly configured data.

# Data Warehouse Sources

This section lists the data warehouse platforms that CleverTap supports for data ingestion.

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
  padding: 1.5rem 1rem; /* add top & bottom padding */
  min-height: 64px; /* ensures consistent tile height */
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
<a href="https://docs.clevertap.com/docs/amazon-redshift" class="integration-card">
  <div class="name">Amazon Redshift</div>
<a href="https://docs.clevertap.com/docs/bigquery" class="integration-card">
  <div class="name">BigQuery</div>
  </a>
<a href="https://docs.clevertap.com/docs/databricks" class="integration-card">
    <div class="name">Databricks</div></a>
  </a>
	<a href="https://docs.clevertap.com/docs/microsoft-fabric" class="integration-card">
    <div class="name">Microsoft Fabric</div> 
  <a href="https://docs.clevertap.com/docs/snowflake" class="integration-card">
    <div class="name">Snowflake</div>
  </a>
</div>
`}</HTMLBlock>

# Quick Start Guide for Data Warehouse Import

This section outlines the essential steps involved in setting up and executing a Data Warehouse Import.

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
  padding: 1.5rem 1rem; /* add top & bottom padding */
  min-height: 64px; /* ensures consistent tile height */
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
  <a href="https://docs.clevertap.com/docs/create-import" class="integration-card">
    <div class="name">Set Up Import</div>
  </a>
  <a href="https://docs.clevertap.com/docs/map-data-for-import" class="integration-card">
    <div class="name">Map Data</div>
  </a>
<a href="https://docs.clevertap.com/docs/schedule-import" class="integration-card">
    <div class="name">Schedule Import</div>
  </a>
  <a href="https://docs.clevertap.com/docs/import-listing-and-stats" class="integration-card">
    <div class="name">Import Listing and Stats</div>
  </a>
</div>
`}</HTMLBlock>
