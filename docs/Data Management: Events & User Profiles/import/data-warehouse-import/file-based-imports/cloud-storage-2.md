---
title: Cloud Storage
excerpt: Learn how to import data from Cloud Storage into CleverTap
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This section introduces integrations that enable you to bring large volumes of data from your cloud storage into CleverTap. It provides an overview of the supported sources and the associated workflows for configuring imports, mapping fields, and scheduling automated pipelines.

# Sources

This section lists the Cloud Storage that CleverTap supports for data ingestion.

<Cards>
  <Card title="Amazon S3">

  </Card>

  <Card title="Google Cloud Storage">

  </Card>

  <Card title="Microsoft Azure Blob Storage">

  </Card>
</Cards>

# Quick Start Guide for File-based Import

This section outlines the essential steps involved in setting up and executing a file-based import.

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
  <a href="https://staging.docs.user.clevertap.net/docs/create-file-based-import" class="integration-card">
    <div class="name">Set Up Import</div>
  </a>
  <a href="https://staging.docs.user.clevertap.net/docs/map-data-for-file-based-import" class="integration-card">
    <div class="name">Map Data</div>
  </a>
  <a href="https://staging.docs.user.clevertap.net/docs/map-data-for-file-based-import#perform-dry-run-recommended" class="integration-card">
    <div class="name">Perform Dry Run</div>
  </a>
  <a href="https://staging.docs.user.clevertap.net/docs/schedule-file-based-import" class="integration-card">
    <div class="name">Schedule Import</div>
  </a>
  <a href="https://staging.docs.user.clevertap.net/docs/import-listing-and-stats-for-file-based-import" class="integration-card">
    <div class="name">View Import Stats</div>
  </a>
</div>
`}</HTMLBlock>
