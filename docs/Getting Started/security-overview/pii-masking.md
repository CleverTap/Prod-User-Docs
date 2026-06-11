---
title: PII Masking
excerpt: Learn about masking system and custom event properties in CleverTap.
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

Masking hides sensitive information from unauthorized users, such as emails, phone numbers, or payment IDs. This feature ensures that PII (Personally Identifiable Information) is visible only to users with the appropriate [role-based access](doc:role-based-access-control#data-access). It helps businesses comply with data privacy regulations such as GDPR and enforce internal data governance policies.

> 📘 Enable PII Masking
>
> To enable this feature for your account, contact your Customer Success Manager or raise a support ticket.

Masking ensures the following:

- Protection of PII
- Enforcement of internal data access policies
- Compliance with regulations (for example, GDPR, CCPA)

> 📘 Access Control
>
> - Only dashboard users with Admin access can mask custom events or user properties.
> - To use this feature, ensure that Admin roles do not have any custom roles assigned.

# Mask Event Data

CleverTap masks specific system user properties and allows users to mask custom user and event properties of their preference.

## System Properties

CleverTap pre-masks specific System User and Event properties.

The following lists all system user and event properties that are masked by default.

**System User Properties**

- Email
- Phone number
- Identity
- Name
- Gender
- DOB (Date of Birth)
- Latitude
- Longitude
- Location

**System Event Properties**

- Email
- Phone number
- Identity
- For the event **Identity Set**, the PII property `ID` is masked.
- For the event **Identity Reset**, the PII property `ID` is masked.
- For the event **Identity Error**, the PII property `ID` is masked.

For more information on System Events and properties, refer to [Events](doc:events#overview).

## Custom Properties

CleverTap supports two ways to mask custom event properties:

- Mask a Single Property
- Mask Multiple Properties in Bulk

### Mask a Single Property

Users can mask a single user or event property, such as a user name or email.

To mask a single custom event property, perform the following steps:

1. Go to _Settings_ > _Schema_ >_Events_ > _Custom events_.
2. Click the _Properties_ hyperlink for the relevant custom event.
3. Click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon next to the property name and select **Mask**.
4. In the confirmation dialog, click **Mask**.


<Image src="https://files.readme.io/4f65ed07ee09b994dc8d709d8ab217f1fe6cf1772d3600b37e2b75a4435440ab-2025-06-16_14-25-07_1.gif" alt="Mask Single Custom Property" align="center" caption="Mask Single Custom Property" border={true} />


This action masks the value of selected properties.


<Image src="https://files.readme.io/9aee73f5bf09518d23faedca071aa3f81d5a2f0b36452ac5c2d93c475bd28981-image.png" alt="Masked property queued for processing" align="center" caption="Masked Property Queued for Processing" border={true} />


Once confirmed, CleverTap masks the selected property in the background. The Admin user receives an email notification after masking a property.

### Mask Bulk Properties

Users can simultaneously mask multiple properties of a single custom event to speed up setup. To mask multiple custom event properties in bulk, perform the following steps:

1. Go to _Settings_ > _Schema_ > _Events_ > _Custom events_.
2. Click the _Properties_ hyperlink for the relevant custom event.
3. Select the properties to mask, then click the ![](https://files.readme.io/f5d0869de355db2c753f2c712fb174e07e0c4ca7c98e40ffb130035cefae64a8-2025-05-08_03-05-09.png) mask icon to mask properties in bulk.
4. In the confirmation dialog, click **Mask**.


<Image src="https://files.readme.io/9dcacf8fcbf672a377ed27003032bb9baafb53898792e39d3d1809d4f8673af7-2025-05-08_02-17-57_1.gif" alt="Mask Properties in Bulk" align="center" caption="Mask Custom Properties in Bulk" border={true} />


This action masks the values of all selected properties. Only admins can mask/unmask an event property.


<Image src="https://files.readme.io/ebad65c9d791a15ae65099da746df83b2e9071c7bb4caa370da64d75d9a71974-image.png" alt="Masked property queued for processing" align="center" caption="Masked Property Queued for Processing" border={true} />


Once the properties are masked, they are queued for processing. Within a few minutes, values for all masked properties are replaced with placeholder text as shown below:


<Image src="https://files.readme.io/cb26bd32026184d2412c586f4b51370c3fbde712b88bab03db2e9d7b0d676656-image.png" align="center" width="20% " border={true} />


> 📘
>
> **Download Restriction on PII Values**
>
> CSV downloads follow encrypted PII access permissions. Admins and users with encrypted PII access via custom roles can view the actual values.
>
> For users without encrypted PII access, certain fields are restricted during export, as follows:
>
> - **System user properties:** Encrypted fields are unavailable for selection in the CSV download confirmation pop-up.
> - **Custom user properties:** Encrypted columns are included in the CSV, but the values appear as blank.

# Unmask Event Data

To unmask a single custom event property, perform the following:

1. Go to _Settings_ > _Schema_ >_Events_ > _Custom events_.
2. Click the _Properties_ hyperlink for the relevant custom event.
3. Click the ![](https://files.readme.io/fb90f6a-Ellipsis.png) icon next to the property name and select **Unmask**.
4. In the confirmation dialog, click **Unmask**.


<Image src="https://files.readme.io/558beee8be7de5adc325a9b16e54811a7280dfd1d3862505f02e287f9bcc1a91-2025-05-28_23-18-54_1.gif" alt="Unmask Single Custom Property" align="center" caption="Unmask Single Custom Property" border={true} />


# Masked Data

- Masked values appear as obfuscated or placeholder text in the dashboard.
- Users with restricted access cannot view the actual property value. For example, a masked value of an email appears as follows:

  <Image src="https://files.readme.io/2493d16e3da5ee42311af874fad1233a6e957963bbb05909df2b430a49eda5fa-image.png" align="center" caption="View Masked Properties" border={true} />


* Admin users can view PII values in plain text or unmask them as needed, while other user roles with PII visibility access can only view the masked icon.

> 📘 Enable PII masking
>
> To enable this feature for your account, contact your Customer Success Manager or raise a support ticket.

# FAQs

### Which user roles can apply masking to event or user properties?

Only Admin users can mask or unmask custom events or user properties. Non-admin users cannot apply masking.

### Can I mask custom properties?

Yes. CleverTap allows you to mask any custom user or event properties in the dashboard.

### Can masked properties be unmasked later?

Yes, Admin users can unmask properties by:

1. Navigating to the custom event’s property list
2. Clicking the ellipsis icon next to the property
3. Selecting **Unmask** and confirming the action

### Can masking be reversed by non-admin users?

No. Only Admin users can unmask properties. Non-admin users cannot reverse or access masked values.

### Does masking affect data processing or segmentation?

Masking only affects the visibility of data on the dashboard; it does not impact how the data is ingested, stored, or used in Segments, Analytics, or Campaigns.

### Is there any notification for masking actions?

Yes. Admins receive an email notification when a property is masked or unmasked, helping maintain visibility and traceability of sensitive data actions.
