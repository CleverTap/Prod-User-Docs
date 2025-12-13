---
title: Product Config
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
DOCS NOTE: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE IS UNPUBLISHED AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES: [https://docs.clevertap.com/docs/product-experiences](https://docs.clevertap.com/docs/product-experiences)

## Overview

Using a product config provides the capability to modify app behavior and feature flags to add or remove features from your app without performing an app store deployment. You can remotely configure your app with product config. The configuration can be anything, including the look and feel of the app and the workflow for users.

# Example

For example, if you want to want to enable dark mode on your app, you would want the following additional options for your experiment:

* You want to test it first on iPhone users who live in New York. 
* You must also be capable of disabling the feature if it needs more work. 

You can create a product config for this improvement and test the response to your app.  Before using product config, you must complete the necessary setup. For more information, refer to [Fundamental Components](https://docs.clevertap.com/docs/fundamental-components). 

# Use Cases

Product configs empower product and engineering teams to create personalized experiences in the app for different user segments based on user properties or their past behavior.

## Maximizing Clicks and Conversions through Content Layout

In this use case, the goal is to improve conversions. One hypothesis to test is which content layout will work best. In this experiment, variant A displays the content below the fold while variant B displays the content above the fold. 

## Different Content to Different User Segments

In this use case, the goal is to increase user engagement on the app by showing relevant cards. One test is to create different user segments to display different content to different types of users based on the user's location, the most preferred watched category, or the favorite category.

# Create a Product Config

You can have multiple members of your team create product config with multiple keys and segments. You can then group these keys. 

To create a product config, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Product Config*. 
2. Click **+ Product Config** to create a new product config. 

![1408](https://files.readme.io/7d0fb9d-Plus_Product_Config.png "Plus Product Config.png")


3. Enter the name and description for your product config. For our example, name the product config as *dark mode*. 
4. Select the *Segments* and *Keys* for your product config group. The keys are the keys that you have assigned in your app for each element or feature and the segments are the group of users who will receive this feature. 

For example, select the iPhone users in New York and iPhone users in Miami as segments and "Dark\_Key" as the product config key. For more information on creating keys, refer to [Keys](https://docs.clevertap.com/docs/product-experiences#section-create-keys).

> 📘 One per Product Config
>
> A key can only be used in one product config.

5. Add the value and set the priority for your product config keys. Drag the <img src="https://files.readme.io/b3f4cdd-Move_icon.png" height="30px" width="30px" /> icon up or down to change segment priority. 
6. Publish your product config or schedule it to a later date. 

<Image title="ProductExp_Product_Config_Create.png" alt={777} className="border" width="100%" border={true} src="https://files.readme.io/fc9b178-ProductExp_Product_Config_Create.png" />

# Edit or Archive a Product Config

To edit or archive a product config, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Product Config*. 
2. Click the ellipsis menu to edit or archive a product config.  

![1401](https://files.readme.io/0bfd11e-Edit_and_Archive_a_Product_Config.png "Edit and Archive a Product Config.png")

> 📘 Product Config Changes
>
> Any changes to a product config are saved in a new version. You can always revert to an earlier version.

# View Statistics

The stats show you the distribution and value of the key stats for your product config. To view product config stats, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Product Config*.  
2. Click the product config from the list and scroll down to view the stats. 

You can view the following information:

* You can see a trend of the total number of keys delivered for all segments or a particular segment from the first chart.
* In the second box, you can further break it down to get the count of each type of key value.

<Image title="Product_Exp_Keys_Stats.png" alt={720} width="100%" src="https://files.readme.io/f5d39be-Product_Exp_Keys_Stats.png" />

# Product Config Version
A new version is created every time you edit a product config. If the current config is not working for some reason, you can always revert to an older version of the product config.

To revert to an older version, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Product Config*. 
2. Click the ellipsis menu to edit a product config. 

![1401](https://files.readme.io/9c315b3-Edit_and_Archive_a_Product_Config.png "Edit and Archive a Product Config.png")

3. Click the required version number on the right side, then click **Publish Version**. The selected version becomes active and the current version becomes inactive. 

<Image title="Edit version.png" alt={1157} width="100%" src="https://files.readme.io/322b14e-Edit_version.png" />