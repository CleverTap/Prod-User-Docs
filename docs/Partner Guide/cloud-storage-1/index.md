---
title: Cloud Storage
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

CleverTap integrates with major cloud storage platforms to support both data import and export. You can bring customer data into CleverTap from files stored in your cloud bucket, or export CleverTap profile and event data directly to your preferred storage destination. &#x20;

# Supported Partners

Select your storage provider below to configure the connection to import or export data.

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
  <a href="https://docs.clevertap.com/docs/amazon-eventbridge" class="integration-card">
    <div class="name">Amazon EventBridge</div>
  </a>
  <a href="aws-s3-configuration" class="integration-card">
    <div class="name">Amazon S3</div>
  </a>
  <a href="https://docs.clevertap.com/docs/gcp-configuration" class="integration-card">
    <div class="name">Google Cloud Platform</div>
  </a>
  <a href="https://docs.clevertap.com/docs/microsoft-azure-configuration" class="integration-card">
    <div class="name">Microsoft Azure</div>
  </a>
</div>
`}</HTMLBlock>