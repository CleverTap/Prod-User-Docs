---
title: File-based Imports
excerpt: 'Importing Data into CleverTap: Manual and Automated Options'
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

The File-based Import feature allows you to upload large volumes of data into CleverTap, either manually from the CleverTap dashboard or automatically from your SFTP server and cloud storage bucket.

# Sources

This section lists the file-based import sources that CleverTap supports, whether manually or automatically.

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
  <a href="https://docs.clevertap.com/docs/cloud-storage-for-file-based-imports" class="integration-card">
    <div class="name">Cloud Storages</div>
  </a>
  <a href="https://docs.clevertap.com/docs/csv-upload" class="integration-card">
    <div class="name">CSV Upload</div>
  </a>
  <a href="https://docs.clevertap.com/docs/imports-via-sftp" class="integration-card">
    <div class="name">SFTP</div>
  </a>
</div>
`}</HTMLBlock>
