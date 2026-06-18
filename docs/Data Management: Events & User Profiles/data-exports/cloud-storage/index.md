---
title: Cloud Storage
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

This section introduces the export methods that deliver CleverTap data directly to your cloud storage locations. This page provides an overview of the supported storage partners and export types so you can choose the correct approach for receiving profile or event data in your preferred cloud environment.

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
  <a href="https://docs.clevertap.com/docs/data-export-to-aws-s3" class="integration-card">
   <div class="name">Amazon S3</div>
  </a>
	<a href="https://docs.clevertap.com/docs/data-export-to-gcp" class="integration-card">
  <div class="name">Google Cloud Platform (GCP)</div>
  </a>
	<a href="https://docs.clevertap.com/docs/microsoft-azure" class="integration-card">
  <div class="name">Microsoft Azure</div>
  </a>
</div>
`}</HTMLBlock>

> 📘 Profile and User Exports (Legacy) vs. Profile Exports
>
> CleverTap supports two distinct export flows, depending on your data requirements and integration needs:
>
> - [**Profile and User Exports (Legacy)**](doc:profile-and-events-legacy): Supports exporting both events and user profiles.
> - [**Profile Exports**](doc:profile-exports): The newer, enhanced export flow that supports exporting user profiles only with improved flexibility and structure.

<br />
