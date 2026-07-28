---
title: Field-Level at Rest Encryption
excerpt: >-
  Learn how CleverTap secures your data while it is stored in CleverTap using
  AES-256 encryption and key management.
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

Field-Level at Rest Encryption protects Personally Identifiable Information (PII) stored in CleverTap by ensuring that the data can only be decrypted using valid keys. PII includes sensitive information such as names, email addresses, phone numbers, custom user and event properties. When field-level data is encrypted at rest, this information stays protected across all stages of storage, including databases, backups, and any persistent storage systems.

CleverTap’s encryption framework utilizes strong, industry-standard algorithms such as AES-256 to secure data without limiting teams from using the platform. Users who have the required [Role-Based Access Control (RBAC)](doc:role-based-access-control) permissions can continue to work seamlessly with encrypted fields across Segments, Analytics, and Campaigns, while the underlying PII remains protected from unauthorized access.

> 📘 **Add-on Feature**
>
> This feature is available as a paid add-on. To enable Field-Level at Rest Encryption, contact your sales representative.

Field-Level at Rest Encryption helps you perform the following:

* Prevent unauthorized access across databases and backups.
* Ensure secure long-term data retention.
* Comply with global and local data protection regulations.

<Image alt="PII Encryption" align="center" border={true} src="https://files.readme.io/c53d243286ca1a376aa10208d0dcb575bebd6e10edd70fcd3a171e3b793b3119-image.png">
  PII Encryption
</Image>

> 📘 **Encryption is Irreversible**
>
> Encryption is irreversible only for event properties. You cannot revert an event property to an unencrypted state.

# Encryption Framework

CleverTap utilizes multiple layers of encryption to safeguard stored data without compromising functionality. It applies AES-256 encryption to all stored data and manages encryption keys through secure key management infrastructure. This framework ensures confidentiality, integrity, and compliance while preserving analytics and campaign operations.

## Default vs. Bring Your Own Key Encryption

By default, Clevertap encrypts field-level data at rest using the keys in its key management system. 

If you require additional security, Bring Your Own Key (BYOK) encryption enables you to use your own keys to encrypt field-level data at rest in CleverTap. 

For more information, refer to [Bring Your Own Key (BYOK) Encryption](doc:bring-your-own-key-byok-encryption).

## Eligible Data

You can mark the following properties for encryption.

* System user Properties
  * Phone 
  * Email
* Custom user properties
* Custom event properties

Custom events are also supported for encryption. Once encryption is enabled for a custom property, new incoming data is encrypted automatically, while historical data remains unencrypted.

# Encrypt Field-Level Data at Rest

CleverTap automatically encrypts all stored data using secure, industry-standard methods:

* AES-256 encryption for all databases, backups, and persistent storage  
* Secure key management through a centralized key infrastructure  
* Automated key rotation and audit logging  

These controls ensure all PII stored in CleverTap remains protected and compliant with global regulations.

## Encrypt User or Event Properties

You can encrypt user or event properties either individually or in bulk.

**Encrypt Single Property**

To encrypt an individual event property, follow the steps:

1. Go to *Settings > Schema > Events > Custom Events*.
2. Click **Properties** for the required event.
3. Click the ellipsis menu and select **Encrypt**.
4. In the confirmation dialog, click **Encrypt**.

<Image alt="Encrypt PII Values" align="center" border={true} src="https://files.readme.io/243c2b2174e002539b50012bb92c9ddea518580dfc437c609e6f298d9c489d42-2025-07-17_13-47-26_1.gif">
  Encrypt PII Values
</Image>

The following image shows the encrypted PII properties:

<Image alt="Encrypted Properties" align="center" border={true} src="https://files.readme.io/fd5aeb3c96ab14bada82f33000502147d8d8985f199ef19f2ed13844eacd08f0-image.png">
  Encrypted Properties
</Image>

## Using Encrypted Data Across Platforms

CleverTap enforces Role-Based Access Control (RBAC) for all encrypted properties. Access depends on the user's permissions. Only authorized users with RBAC permissions can view and use decrypted values in Segments, Engagements, and Analysis, as these values remain consistent across the platform.

Users who do not have decryption permissions see only the encrypted value instead of the underlying PII. When they attempt to query the property, the interface displays the encrypted property as shown in the image, and the user cannot view or filter by the actual decrypted value.

### Segments

Users without decryption permissions cannot view or query the encrypted property in the Segment Builder.

<Image alt="Encrypted Values in Segment Builder" align="center" width="70%" border={true} src="https://files.readme.io/b2295177bba75adbf5e8c668a88a6c56ba136b7d4cc4a9cd05aedf90ea96ef14-image.png">
  Encrypted Values in Segment Builder
</Image>

### Engagements

Users without decryption permissions cannot access or use the encrypted properties in Campaigns and Journeys.

<Image alt="Filter using Encrypted Values in Campaigns" align="center" border={true} src="https://files.readme.io/326e6951f04c2924380f2bb76d30cd54dc484f355ee9cc2377abcf3283a66ba0-image.png">
  Filter using Encrypted Values in Campaigns
</Image>

### Analytics

Users without decryption permissions cannot view or query the encrypted properties in Analytics or reports.

<Image alt="Query using Encrypted Values in Analytics" align="center" border={true} src="https://files.readme.io/3f77c0333db9af68ad1e1a6d62e35339ae3a6c74fa7a92ddcf8b507d78510d9e-image.png">
  Query using Encrypted Values in Analytics
</Image>

> 📘 **Viewing Encrypted Values**
>
> Only Admins can encrypt field-level data at rest, and only authorized users can view the encrypted values.
>
> The visibility of encrypted values on the *Segment* and  *Analytics* pages depends on your role. For roles without encryption access, these values remain hidden. Roles with encryption permissions can view and use the encrypted values for segmentation and analytics.

# Frequently Asked Questions

### What encryption algorithm does CleverTap use?

CleverTap uses AES-256 encryption keys for field-level data at rest.

### Can I search or segment encrypted fields?

Yes. Authorized users can search and segment encrypted fields without a performance impact.

### Can encryption be disabled later?

No. Encryption cannot be disabled or paused. Once enabled for an event property, all future incoming data is also encrypted. However, you can decrypt a user property.

### How does masking interact with encryption?

If a property is configured for both masking and encryption, encryption takes precedence. The system encrypts the value first, and masking rules apply only to authorized users who have decryption access.
