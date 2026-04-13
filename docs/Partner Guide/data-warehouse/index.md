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

CleverTap’s data warehouse integration enables you to seamlessly import data into CleverTap for customer engagement and export engagement data from CleverTap to data warehouses for analytics and reporting. This helps you unify customer data, activate advanced insights, and connect marketing performance with business outcomes.

By integrating CleverTap with your data warehouse, you can use the data warehouse as the system of record for analytics and governance while leveraging CleverTap to deliver personalized, cross-channel customer experiences that improve engagement, retention, and revenue.

# Import Data into CleverTap

Importing data from your data warehouse into CleverTap helps you activate centralized, analytics-ready customer data for segmentation, personalization, and campaign orchestration. Use this when insights (for example, customer tiers or predictive scores) are generated in BI or data science workflows and need to drive engagement.

## Key Benefits

The following sections are the benefits of integrating CleverTap with a data warehouse partner for both importing and exporting data. These capabilities help you maintain a centralized data strategy while enabling targeted engagement and comprehensive analytics.

* **Warehouse as Single Source of Truth**

  Use your data warehouse as the primary source of customer and business data, and import only engagement-ready data into CleverTap. This ensures consistent definitions across analytics, reporting, and marketing execution while reducing data duplication.

* **Unified Customer Profiles**

  Enrich CleverTap user profiles with attributes, transactional history, and analytical outputs stored in your data warehouse to maintain a consistent customer view across systems.

* **Advanced Segmentation Using Warehouse Data**

  Create audience segments in CleverTap using historical, aggregated, or model-driven data from the warehouse to enable more precise targeting.

* **Activation of Business and Analytical Insights**

  Use BI and Machine Learning Insights by importing data, such as customer tiers, propensity scores, or lifecycle states generated in the warehouse as inputs for campaigns and journeys in CleverTap.

## Supported Warehouse Imports

CleverTap supports importing data from the following data warehouses. Use the linked documentation to configure warehouse connections, create import jobs, and manage data ingestion into CleverTap. Each supported warehouse enables you to import user attributes, events, and analytical data according to your integration and data model requirements.

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
  </a>
<a href="https://docs.clevertap.com/docs/bigquery" class="integration-card">
    <div class="name">BigQuery</div>
  </a>
<a href="https://docs.clevertap.com/docs/databricks" class="integration-card">
    <div class="name">Databricks</div>
<a href="https://docs.clevertap.com/docs/microsoft-fabric" class="integration-card">
    <div class="name">Microsoft Fabric</div>  
<a href="https://docs.clevertap.com/docs/snowflake" class="integration-card">
    <div class="name">Snowflake</div>
  </a>
</div>
`}</HTMLBlock>

### Quick Start Guide for Imports

The following steps provide a high-level flow for importing data from a data warehouse into CleverTap. Each step links to detailed documentation to help you configure the import, map data correctly, schedule runs, and monitor import activity.

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

# Export Data from CleverTap

Exporting CleverTap data to a data warehouse enables deeper analysis of engagement, behavioral, and campaign performance alongside business metrics such as revenue, retention, and support outcomes. Use this for long-term reporting, attribution, and cross-team analytics access.

## Key Benefits

* **Centralized Engagement and Campaign Data**

  Export CleverTap user events, profile updates, and campaign interactions into your data warehouse to unify engagement data with CRM, revenue, and support datasets for holistic analysis.

* **Deeper Analysis and Reporting**

  Combine CleverTap campaign and engagement data with downstream business outcomes stored in your data warehouse to measure lifecycle impact and improve attribution and ROI accuracy.

* **Consistent and Warehouse-Ready Structured Data**

  Export data in a consistent, predictable structure optimized for ingestion, transformation, and scalable analytics workflows in your data warehouse.

* **Cross-Team Data Accessibility**

  Make CleverTap engagement data available to analytics, data science, and reporting teams directly from the data warehouse, without requiring access to the CleverTap dashboard.

## Supported Warehouse Exports

CleverTap supports exporting data to the following data warehouses. Use the linked documentation to configure export connections, create export jobs, and manage how data is sent from CleverTap. Each supported warehouse enables you to export engagement, campaign, and system event data tailored to your reporting and analytics requirements.

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
<a href="https://docs.clevertap.com/docs/bigquery-export" class="integration-card">
    <div class="name">BigQuery</div>
	<a href="https://docs.clevertap.com/docs/snowflake-export" class="integration-card">
    <div class="name">Snowflake</div>
  </a>
  </a>
</div>
`}</HTMLBlock>

<br />
