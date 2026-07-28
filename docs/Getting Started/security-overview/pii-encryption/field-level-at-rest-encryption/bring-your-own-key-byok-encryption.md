---
title: Bring Your Own Key (BYOK) Encryption
excerpt: >-
  Secure your CleverTap data with Bring Your Own Key (BYOK) encryption,
  providing you with full control over key management and ensuring compliance.
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

CleverTap’s Bring Your Own Key (BYOK) encryption allows customers to manage their own encryption keys for securing personally identifiable information (PII) stored in CleverTap.

This feature handles all key lifecycle operations, including generation, storage, rotation, and versioning, by integrating directly with the customer’s Key Management Service (KMS). This approach ensures customers retain control of their encryption keys, meet data governance and privacy requirements, and benefit from automated key rotation and version management that align with enterprise security standards.

# Prerequisites

Before configuring BYOK, check that the following conditions are met:

* The PII Encryption feature is enabled, as this is a paid add-on.
* Customer KMS credentials and permissions for key generation and retrieval are available.

# BYOK Architecture

CleverTap’s BYOK encryption relies on a dedicated key management system that manages keys generated in customer vaults.

## Core Functions

The key management system performs the following functions in the BYOK workflow:

* **Key Generation:** Generates encryption keys in the customer KMS. Each key has a name, version reference, and rotation frequency.
* **Key Storage:** Optionally stores encrypted keys locally for a configurable Time-To-Live (TTL) period to reduce KMS request costs. The stored record includes the encrypted key.
* **Key Rotation:** Supports both scheduled and manual rotations. Rotation frequency can be configured (for example, 365 days by default). Force rotation can be triggered on demand.
* **Key Versioning:** Maintains key versions locally.
* **Key Validation:** Validates the latest key version through various checks before making it available to internal services.

# Setup

The BYOK setup involves several steps to ensure CleverTap has access to the keys managed by the customer's KMS.

1. Customer shares their AWS KMS ARN credentials.
2. Customer provisions an IAM policy to grant CleverTap servers access to their KMS.
3. CleverTap generates the encryption key in the customer KMS.
4. CleverTap fetches the key from the customer KMS to encrypt data.

# FAQs

Find answers to common questions about integrating and managing BYOK in CleverTap’s backend systems.

### How does key versioning work?

Each time a key rotates, a new encrypted key record is generated and stored locally with an incremented version number. Older versions remain stored for audit purposes.

### What is stored locally for each key?

Each record contains the encrypted key body (the actual secret in encrypted form), the initialization vector (IV, a random value used in encryption), version number, and rotation metadata (information about when and how the key was changed).

### Can rotation be scheduled for shorter intervals?

Yes. The rotation frequency can be configured in the customer KMS during key creation or modified later.
