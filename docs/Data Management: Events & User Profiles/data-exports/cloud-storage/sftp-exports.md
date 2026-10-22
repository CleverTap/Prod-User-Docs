---
title: SFTP Exports
excerpt: >-
  Learn how to configure an SFTP connection for Profile and Event exports from
  CleverTap.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The SSH File Transfer Protocol (SFTP) integration connects CleverTap to a file server that you control, so you can export profile and event data to it. With the integration, you can export data to your server for analysis in Business Intelligence (BI) tools or storage in a data warehouse.

SFTP export is useful when you want to deliver files directly to a server you already run, such as an on-premises data warehouse, an internal file share, or a partner's own server. For example, a retailer with an on-premises data warehouse that already watches a folder for incoming files can run a nightly SFTP export of purchase events straight into that folder. The data lands in the pipeline the retailer already has, so the warehouse team does not have to build a new ingestion path, and nobody has to grant CleverTap access to a cloud account just to receive the files. The server needs a public-facing address for CleverTap to reach it; see Prerequisites.

| Destination                                                                      | Auth Model                |
| -------------------------------------------------------------------------------- | ------------------------- |
| [Amazon S3](https://docs.clevertap.com/docs/aws-s3-configuration)                | IAM policy or access keys |
| [Google Cloud Platform](https://docs.clevertap.com/docs/gcp-configuration)       | Service account key       |
| [Microsoft Azure](https://docs.clevertap.com/docs/microsoft-azure-configuration) | SAS token                 |
| SFTP                                                                             | SSH key pair              |

You create an SFTP connection once, from _Settings > Partners > Connect to SFTP for Export_. Once saved, it appears as a Partner option in the _Create Export_ flow, alongside Amazon S3, Google Cloud, Microsoft Azure, Amplitude, Mixpanel, mParticle, Segment, and Snowflake.

<Callout icon="📘" theme="info">
  ### Draft Status

  This page is a draft written while Engineering builds the SFTP export feature. Items marked 🚧 below still need confirmation from Product or Engineering before this page publishes.
</Callout>

This document covers the following:

- [Prerequisites](#prerequisites)
- [Create SFTP Connection](#create-sftp-connection)
- [Configure Server Details](#configure-server-details)
- [Configure User Credentials](#configure-user-credentials)
- [Test and Save Connection](#test-and-save-connection)
- [Select SFTP as Export Destination](#select-sftp-as-export-destination)
- [Encrypt Export Files](#encrypt-export-files)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

# Prerequisites

Configuring an SFTP export destination requires access to your own SFTP server and the ability to install a public key on it.

- Your SFTP server needs a publicly resolvable hostname or a public Internet Protocol (IP) address. CleverTap doesn't support private, VPC, or internal-only hosts in this release; support for those is planned through a future tunnel or controlled-egress option. If your host isn't in public DNS, use a public IP address instead.
- CleverTap's export traffic comes from a fixed set of per-region egress IP addresses that your server or firewall needs to allowlist.
- A directory on that server where CleverTap can write export files, and a user account with write and rename permission on it.
- The ability to add a public key to that account's `authorized_keys` file.

<Callout icon="🚧" theme="warn">
  ### Export IP Range

  CleverTap's export egress IP addresses are grouped per region, but the actual list still needs to be published here. Get it from Infrastructure before this page ships.
</Callout>

# Create SFTP Connection

To create an SFTP connection, go to _Settings > Partners_ and click **Connect to SFTP for Export**.

# Configure Server Details

Under _Server Details_, add the following details:

| Field              | Description                                                                                                                                                                                                                                                                                                                                                                               |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _Connection Name_  | A unique name to identify this connection among your other export destinations.                                                                                                                                                                                                                                                                                                           |
| _Host_             | Your SFTP server's public hostname or IP address. Do not include a scheme prefix such as `sftp://`.                                                                                                                                                                                                                                                                                       |
| _Port_             | The port on which your SFTP server listens, from 1 to 65535. The default SFTP port is 22.                                                                                                                                                                                                                                                                                                 |
| _Remote Directory_ | The directory on your server where CleverTap writes export files. Required: enter `/` to write to the connection's home directory, or a sub-directory path such as `uploads` or `exports/daily`. The directory must exist, and the SFTP user needs write access to it; CleverTap creates missing sub-directories automatically, but only where the SFTP user is permitted to create them. |

The _Preview_ field shows the resulting path as you fill in these fields: `sftp://<host>:<port>/<remote-directory>`.

<Callout icon="📘" theme="info">
  ### Remote Directory Details

  On managed SFTP, such as AWS Transfer Family or Azure Blob SFTP, any directory you enter typically works without extra setup. On a self-managed server, make sure the directory already exists and is writable by the SFTP user; chrooted accounts especially may need a writable sub-directory rather than the account root, since the root is often non-writable by design.

  If the remote directory isn't writable, **Test Connection** fails up front with a clear message telling you so.
</Callout>

# Configure User Credentials

Under _User Credentials_, add the following details:

| Field                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _Username_             | The account CleverTap uses to authenticate to your server.                                                                                                                                                                                                                                                                                                                                                                          |
| _SSH Public Key_       | The key type CleverTap generates for this connection. Select RSA 2048, RSA 3072, RSA 4096, Ed25519, ECDSA nistp256, or ECDSA nistp384 from the dropdown, and click **Generate Key**. If you change the key type on an existing connection without regenerating the key pair, CleverTap rejects the mismatch.                                                                                                                        |
| _Host Key Fingerprint_ | An optional value that lets CleverTap verify it's connecting to the correct server instead of trusting it on first connect. Accepts a `SHA256:`-prefixed fingerprint, which is recommended, or a `SHA1:`- or `MD5:`-prefixed or bare colon-separated hex value, which CleverTap normalizes and stores as the canonical SHA-256 form. Leave this field blank to trust the server's key on first connection, after which it's pinned. |

<Callout icon="📘" theme="info">
  ### Key Ownership and Host Trust

  - CleverTap generates the key pair and gives you only the public key, in OpenSSH `authorized_keys` format, to install yourself. The private key never leaves CleverTap.
  - If you provide a _Host Key Fingerprint_, CleverTap verifies it at save and at every **Test Connection**, rejects a mismatch with the fingerprint the server actually presented, and never silently re-trusts a changed key; re-pin from the connection settings if your server's key legitimately changes.
</Callout>

If your server has RSA authentication disabled, choose Ed25519 or ECDSA instead. To get your server's fingerprint, run `ssh-keygen -lf` against the relevant host key file, for example `ssh-keygen -lf /etc/ssh/ssh_host_ed25519_key.pub`.

# Test and Save Connection

To confirm CleverTap can reach your server before you rely on it for exports, perform the following steps:

1. Click **Test Connection**.
2. Click **Save**.

Both steps run the same checks: connect, verify the host key, authenticate, and write a small test file to confirm permissions.

<Callout icon="📘" theme="info">
  ### Connection Test File

  **Test Connection**, and the pre-flight check CleverTap runs before every scheduled export, write a small file of about 27 bytes to your remote directory to confirm write and rename access. CleverTap uploads it under a random temporary name ending in `.part`, then renames it onto a fixed marker file named `dummy-auth-ct`, left in place and overwritten on each run. You may notice this file in your remote directory; it's harmless, safe to leave or delete, and is recreated on the next test or export.
</Callout>

Common setup errors and what they mean:

| Problem                          | What you'll see                                                                                                                                       |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Wrong username, password, or key | An authentication error naming the user, with a prompt to check the credentials or confirm the public key is installed.                               |
| Remote directory not writable    | A write-test failure naming the directory and user; if the target is the home directory, the message suggests using a writable sub-directory instead. |
| Host key mismatch                | A host-key verification error that includes the fingerprint the server actually presented.                                                            |
| Host or IP address unreachable   | A connection-check failure; details include whether the hostname couldn't be resolved or the address was rejected as private or internal.             |
| Connection refused or timed out  | A prompt to check the host, port, and that CleverTap's egress IP addresses are allowlisted.                                                           |

# Select SFTP as Export Destination

Once saved, an SFTP connection appears as a Partner option wherever you create an export, alongside your cloud storage and analytics partners.

1. Go to _Settings > Partners > Export Center_.
2. Click **Create Export**.
3. Under _Data Type_, choose _Profiles_ or _Events_, and click **Next**.
4. Under _Partner_, select your saved SFTP connection.
5. Click **Start**, then configure _Storage & File Details_, _User Identifiers_, _Data Fields & Event_, _Edit Properties & Order_, and _Schedule_ the same way you would for a cloud storage export.

Under _Sub-Folder Structure_, choose how CleverTap organizes files on your server: _Server Base Path_ (the connection name as a folder prefix, for example `Conn2/`), _Split by Data Type_, _Split by Export Run Date_, _Split by Export Unique ID_, _Split by Event Name_, or _Custom_. The _Folder Structure Preview_ shows the resulting path as you choose. Under _File Format_, choose CSV, JSON, Parquet, or XML; Parquet has its own _Gzip After Parquet_ toggle, off by default, that the other formats don't offer.

<Callout icon="📘" theme="info">
  ### Export File Behavior

  - CleverTap writes a separate file per event name rather than combining all events into one file; SFTP event exports use `eventTime` as the event-timestamp column.
  - Each file uploads under a temporary `.part` name and is renamed once complete, so a process watching the remote directory should ignore `.part` files; a retried run overwrites the same file name rather than leaving a stale partial file behind.
</Callout>

# Encrypt Export Files

You can PGP-encrypt your export files before CleverTap writes them to your SFTP server, so they're never stored in plaintext at the destination. This is optional, and you configure it per export rather than on the connection itself. If you don't enable it, export files are written in plaintext; choose deliberately if that matters to your security team.

Choose one encryption method per export:

| Method         | How it works                                                                                                                                 | Requirements                        |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |
| PGP public key | Paste your ASCII-armored public key. CleverTap encrypts to it, and you decrypt with your matching private key, which never leaves your side. | Requires the PGP-encryption add-on. |
| Password       | Supply a passphrase of at least 12 characters. CleverTap symmetrically encrypts the file, and you decrypt with the same passphrase.          | No add-on required.                 |

We recommend the public-key method where you can use it, since CleverTap never holds a secret that could decrypt your data; password mode is the option if you don't have the add-on.

CleverTap validates your public key when you save it, not when the export runs: a private key, an expired or revoked key, or a key with no encryption capability is rejected immediately with a specific error. If encryption is configured but something prevents CleverTap from encrypting at run time, the export fails rather than falling back to uploading the file in plaintext.

# FAQs

These are common questions about setting up and using SFTP exports.

## What file formats does SFTP export support?

SFTP export supports CSV, JSON, Parquet, and XML. Parquet files can optionally be gzip-compressed.

## Can I rotate or revoke the SSH key later?

Changing the key type or username on an existing connection clears the current public key, and you must click **Generate Key** again to generate a new one; CleverTap rejects a key-type change until you do. The docs team hasn't confirmed yet what happens to exports already scheduled when you do this.

## Can I connect more than one SFTP server?

Profile Exports currently caps recurring exports to one per account for other destinations. The docs team hasn't confirmed yet whether the same limit applies to SFTP.

## What happens if the connection fails mid-export?

Transient network errors, such as a refused, reset, or timed-out connection, are retried and may succeed on a later attempt. Host key mismatches, authentication failures, and permission failures are not retried; the run fails with an error that includes the underlying SFTP status code. The docs team hasn't confirmed yet how many times a transient failure retries, or where that status surfaces in the _Export Center_. [Status Alerts for Exports](https://docs.clevertap.com/docs/status-alerts-for-exports) currently lists only Amazon S3, Microsoft Azure, and Google Cloud Platform as supported partners, not SFTP; confirm whether that page will cover SFTP before this one publishes.

# Next Steps

After you create your first SFTP export, you can put it to work like any other export destination.

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
  <a href="https://docs.clevertap.com/docs/cloud-storage" class="integration-card">
    <div class="name">Cloud Storage</div>
  </a>
  <a href="https://docs.clevertap.com/docs/profile-exports" class="integration-card">
    <div class="name">Profile Exports</div>
  </a>
  <a href="https://docs.clevertap.com/docs/event-exports" class="integration-card">
    <div class="name">Event Exports</div>
  </a>
  <a href="https://docs.clevertap.com/docs/status-alerts-for-exports" class="integration-card">
    <div class="name">Status Alerts for Exports</div>
  </a>
</div>
`}</HTMLBlock>