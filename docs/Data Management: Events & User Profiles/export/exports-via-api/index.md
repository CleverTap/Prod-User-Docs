---
title: API
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

The API section introduces the programmatic methods for retrieving data from CleverTap. This document provides an overview of the available data retrieval APIs, allowing you to select the correct endpoints for accessing events, profiles, and message delivery results.

These API resources help you access CleverTap data programmatically and integrate events, profiles, and message insights into your analytics and operational workflows.

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
  <a href="https://staging.docs.user.clevertap.net/docs/imports-via-api" class="integration-card">
    <div class="name">Get Events</div>
  </a>
  <a href="https://staging.docs.user.clevertap.net/docs/csv-upload" class="integration-card">
    <div class="name">Get User Profiles</div>
  </a>
</div>
`}</HTMLBlock>
