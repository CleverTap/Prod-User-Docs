---
title: Replace Catalogs
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

If your catalog has new products that you want to add, you can choose to replace an existing catalog rather than uploading a new one. The entire catalog gets replaced with the new one, so ensure that you add the previous catalog products as well, if applicable.

# Replace a Catalog

To replace a catalog, perform the following steps:

1. From the dashboard, navigate to *Settings* > *Catalogs*. 
2. From the available catalogs, select the one to replace.
3. Click **Replace Catalog** and upload the new catalog from your system.

Once you upload the catalog, the new catalog gets validated on the dashboard. The dashboard status displays the status *Replacing catalog* which means that the new catalog is still not in effect. Until replaced, any campaigns will be sent with the previously uploaded catalog.

![1038](https://files.readme.io/a6a55ce-Screenshot_2021-07-22_at_1.18.47_PM.png "Screenshot 2021-07-22 at 1.18.47 PM.png")

4. After the catalog is successfully validated, click **Replace And Save**.

![1922](https://files.readme.io/daa92a1-Screenshot_2021-07-22_at_1.32.01_PM.png "Screenshot 2021-07-22 at 1.32.01 PM.png")

> 📘 Upload Catalog API Consideration
>
> If you are using the [upload catalog API](https://developer.clevertap.com/docs/catalog-api-endpoints) to upload a catalog, add the key “replace”:”true” if you want to replace a catalog.
