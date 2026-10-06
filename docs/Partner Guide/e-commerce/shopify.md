---
title: Shopify
excerpt: Learn how to integrate your Shopify store with CleverTap.
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

CleverTap plugin provides an easy way to integrate your Shopify stores within minutes without any code. All you need is a CleverTap account and you can have a seamless flow of events and user data from your Shopify store. You can also send personalized messages to your users through channels such as [Web Push](doc:web-push) notifications, [Web Pop-up](doc:web-pop-ups), [Web Exit Intent](doc:web-exit-intent), and [Web Native Display](https://docs.clevertap.com/docs/web-native-display).

# Video Tutorial - Integrating Shopify Store with CleverTap

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/1tlxbIKZMm3pdrBujijGXQ/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

<br />

# Integrate Shopify

You can install the [CleverTap App](https://apps.shopify.com/clevertapapp) from the [Shopify App Store](https://help.shopify.com/en/manual/apps/installing-apps).  Login to the CleverTap dashboard and follow the steps to complete the integration:

Follow the steps to locate the Shopify plugin on the CleverTap dashboard:

1. Login to your CleverTap account.
2. Open _Settings_ >  _Project_ > _Shopify_.


<Image src="https://files.readme.io/0c97c60-Shopify_start_screen.jpg" alt="Locate the Shopify Plugin" align="center" caption="Locate the Shopify Plugin" border={true} />


3. The _Shopify_ window displays. Click **Integrate Store** button to start the integration.

The integration includes the following steps:

1. [Install and Connect App](https://docs.clevertap.com/docs/shopify#install-and-connect-app)
2. [Advanced Customization ](https://docs.clevertap.com/docs/shopify#advanced-customization)
   * [Configure Web Push](https://docs.clevertap.com/docs/shopify#configure-web-push)
   * [Customize Profile Properties](https://docs.clevertap.com/docs/shopify#profile-properties)
   * [Customize Events](https://docs.clevertap.com/docs/shopify#events)
3. [Enable App Embed](https://docs.clevertap.com/docs/shopify#enable-app-embed-status)

## Install and Connect App

If you have already installed the app from the Shopify App Store,  _App Installed_ is displayed next to your store name. However, if you are installing the app for the first time, you can install it from the Shopify dashboard.

Follow the steps below to install the CleverTap app:

1. Click the _Install CleverTap on Shopify dashboard_ link.


<Image src="https://files.readme.io/5cf4728-Shopify_click_link.jpg" alt="Install from CleverTap " align="center" width="60% " caption="Install from CleverTap" border={true} />


2. The link opens the _Shopify App Store_  page. Check that you are logged in to the store and click **Install**.


<Image src="https://files.readme.io/0f34d65-Shopify_app_store_install.jpg" alt="Install CleverTap App from Shopify Store" align="center" caption="Install CleverTap App" border={true} />


3. You can now connect your store from the CleverTap dashboard and click **Continue**.


<Image src="https://files.readme.io/81362ad-Shopify_store_name.jpg" alt="Enter Shopify Store Name" align="center" width="50% " caption="Enter Shopify Store Name" border={true} />


4. Enter your credentials if you are not logged in to your Shopify store and continue the process.

Your store is now connected to your CleverTap account.

## Import Existing Shopify Data into CleverTap

CleverTap's Historical Data Import feature helps synchronize existing Shopify user and transaction data by allowing you to upload all your historical data directly to CleverTap.


<Image src="https://files.readme.io/168b91fb5bc61e6b3694c0576351543a680b886f74698f3fa7735c18c968826a-historical_.png" alt="Historical Data Import" align="center" caption="Historical Data Import" border={true} />


You can upload the following types of data:

* **Profile Data**: Includes user information such as name, email, phone number, and so on. This is mapped as Profile Properties on the CleverTap dashboard. Refer to the [sample profile data file](https://docs.google.com/spreadsheets/d/11e16DkoSHT_zeYgaa2E_hJjHVO9U4VSzoR4nXb_xXAY/edit?usp=sharing).
* **Purchase Data**: Includes transaction data such as order data. This is mapped as Charged Event on the CleverTap dashboard. Refer to the [sample purchase data file](https://docs.google.com/spreadsheets/d/1gyycrJlx6NgaftxJMJpKXig3mI8fYSTFz9Honp9Ltzs/edit?usp=sharing).

To upload your Shopify website data on CleverTap, follow the steps below:

1. Download a CSV file from your Shopify dashboard. This file can either be a **Profile CSV** with user data or a **Charged Event CSV**  with transaction data.


<Image src="https://files.readme.io/f64dcd8c88237e5388b979d14e2d5cb8bb93985d7261e40d43661766b6c9539b-Shopify_Admin_Panel.png" alt="Shopify Dashboard" align="center" caption="Shopify Dashboard" border={true} />


2. To upload the CSV file to CleverTap, go to _Settings_ > _Project_ and click **Shopify**.
3. Select the upload option: **Profiles** or **Charged Events**. The system starts processing the uploaded file immediately.


<Image src="https://files.readme.io/9601297b3d90c605de105f3841df3c2bf91147152d447faacb905c89e6cb0e63-Historical_data_import.png" alt="Historical Data Import" align="center" caption="Historical Data Import" border={true} />


4. Track the status of your upload at any time. Statuses include:

* **Pending**: The file has been received and is waiting to be processed.
* **Processing**: The system is validating and ingesting the data.
* **Importing**: The data is actively being ingested and merged into your CleverTap project.
* **Merged**: All rows are processed and added to your CleverTap project.
* **Merged with Errors**: The file is processed and merged, but some rows contain issues. You can check the error details, fix the data, and re-upload the CSV.
* **Failed**: The upload has failed due to formatting or validation issues.
* **Paused**: Processing has been paused manually, or there may be a system interruption.

5. After processing, you will receive an email with a CSV file attached only for rows that encountered errors. This file includes an additional column indicating the reason for failure. In case of errors, fix the failed rows and re-upload only the affected rows. Multiple uploads are supported if required.
   Once your data is merged, you can create campaigns, run analytics, and fully utilize the CleverTap platform. Profiles and events can be found in your CleverTap dashboard for further engagement.

<Callout icon="📘" theme="info">
  ### Note

  * Events containing any error columns will be silently ignored and dropped.
  * Ensure every user record has at least one valid identity field. The value must be under **1024 characters**. If this condition is not met, the following error will occur: `Identity value cannot be null or set at least one of identity / fbId / gpId / objectId under 1024 chars to identify the user`.
  * The maximum file size for historical backfill uploads is 5 GB.
  * The following four columns are mandatory for a Charged file upload:
    * Name
    * Email
    * Id
    * Phone
  * Profile and Purchase data must be uploaded as two separate files.
  * If your mobile number is used as an identity, always search it in the CSV using the full international format. For example: `+91XXXXXXXXXX`.
</Callout>

## Advanced Customization

After your store is connected and installed, you can start customizing it per your requirements. You can configure the web push for your store and also customize the event data received from your Shopify store.

### Configure Web Push

You can send personalized communication to your users through Web Push notifications. However, you must enable them first from the CleverTap dashboard.

Check that Web Push is configured for your store. If not configured, you must  [configure the Web Push](https://docs.clevertap.com/docs/setup-web-push)  from the CleverTap dashboard.

After the Web Push is configured, enable the notification prompts. Click _Web Push configuration_  and toggle ON  _Send notification permission prompt_  to enable CleverTap Web Push notifications.


<Image src="https://files.readme.io/b28da80-Shopify_enable_web_pus.jpg" alt="Integrate with Web Push" align="center" width="50%" caption="Enable Web Push" border={true} />


### Customize Event Data

Event data customization includes event and profile data. You can choose to receive only the required data and opt out of receiving any data that is not required.

#### Profile Properties

CleverTap allows you to select only the required Profile properties. To select the Profile properties, follow the steps listed below:

1. Go to  _Settings_ >  _Project_ > _Shopify_ > Advanced Customization > Event Data Customization.
2. Click _Edit_.
3. Click the _Profile properties_ list and select the required properties.
4. Click **Apply**.


<Image src="https://files.readme.io/a7ef3be-Shopify_profile_properties.jpg" alt="Select required profile properties" align="center" width="70% " caption="Select the Required Profile Properties" border={true} />


The following table displays all the user properties supported by the Shopify plugin:

| User Property           | Property Description                                                                                                                                                                                             |
| :---------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Email                   | The customer's email address. For example, [jack@acme.com](mailto:jack@acme.com).                                                                                                                                |
| Phone                   | The customer's mobile number. For example, 97650000.                                                                                                                                                             |
| Tags                    | The list of tags associated with the customer. For example, Gold customer.                                                                                                                                       |
| City                    | The customer's city. For example, Mumbai.                                                                                                                                                                        |
| Orders Count            | The total number of orders from a customer.                                                                                                                                                                      |
| Total Spent             | Total amount spent on all orders. For example, 5400.                                                                                                                                                             |
| Shopify ID              | The Shopify ID of the customer.  For example, 29873645910.                                                                                                                                                       |
| First Name              | The customer's first name.                                                                                                                                                                                       |
| LastName                | The customer's first name.                                                                                                                                                                                       |
| Last Order ID           | The order ID of the last order placed by the customer.                                                                                                                                                           |
| Has Account             | This property returns the value as _true_ if the email associated with the customer is linked to a customer account. The property returns the value as false if the email is not linked to the customer account. |
| Tax Exempt              | Whether or not the customer is exempt from taxes.                                                                                                                                                                |
| Email Marketing Consent | Records the consent status of the customer for receiving marketing communication through Email.                                                                                                                  |
| SMS Marketing Consent   | Records the consent status of the customer for receiving marketing communication through SMS.                                                                                                                    |
| Note                    | A note left by the customer to the merchant, either in their cart or during checkout.                                                                                                                            |
| Currency                | The currency of purchase.                                                                                                                                                                                        |

#### Events

CleverTap receives events from the following two sources:

* _Shopify Webhook_ :  After you integrate your store, CleverTap subscribes to the selected Webhook events for your Shopify store.
* _Web SDK_ :These are the [supported events](https://docs.clevertap.com/docs/shopify-copy#web-push-configuration) that CleverTap Web SDK captures from your Shopify store.

Select the events you want to receive from the Shopify Webhook and the Web SDK.


<Image src="https://files.readme.io/be06cd1-Shopify_receive_events.jpg" alt="Receive Events from SDK" align="center" width="50%" caption="Receive Events from CleverTap SDK and Shopify Webhook" border={true} />


You can also select to _Receive data for Charged_ event or opt-out. Select either of the following events that you want CleverTap to record as a _Charged_ event:

* **Order Paid** : This event is passed to CleverTap by the Shopify webhook when an order is paid.
* **Order Created** : This event is passed to CleverTap by the Shopify webhook when an order is created.

##### Web SDK Supported Events

The following table displays all the events supported by the CleverTap Web SDK:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Event Name
      </th>

      <th>
        Description
      </th>

      <th>
        Properties
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Page Browse
      </td>

      <td>
        This event is recorded when the user visits a page
      </td>

      <td>
        - Page – The store page. For example, Index page.
        - Title – Title of the page. For example, Acme home.
        - URL – URL of the page. For example, [https://mystore.myshopify.com/](https://mystore.myshopify.com/)
      </td>
    </tr>

    <tr>
      <td>
        Product Viewed
      </td>

      <td>
        When the user views a product
      </td>

      <td>
        - **Available** – Availability of the product. For example, TRUE.
        - **Currency** – Shopify store currency. For example, INR.
        - **Handle** – Product Handle. For example, nike-sneakers-shoe.
        - **ID** – Product ID. For example, 6744256675993.
        - **Price** – Product Price. For example, 2999.
        - **Title** – Product Title. For example, Nike Sneakers Shoe.
        - **TotalVariants** – Number of variants available. For example, 3.
        - **URL** – URL of the product page. For example, /products/nike-sneakers-shoe.
      </td>
    </tr>

    <tr>
      <td>
        Searched Product
      </td>

      <td>
        When a product is searched
      </td>

      <td>
        - **Term** – Search terms used. For example, red shoe.

        * **TotalItems** – Number of items in search results. For example, 1.
      </td>
    </tr>

    <tr>
      <td>
        Added To Cart
      </td>

      <td>
        When a product is added to cart
      </td>

      <td>
        - **Currency** – Shopify store currency. For example, INR.
        - **Image** – URL of the product image. For example, [https://cdn.shopify.com/s/files/products/RedT-shirt.jpg](https://cdn.shopify.com/s/files/products/RedT-shirt.jpg).
        - **Price** – Product Price. For example, 2999.
        - **ProductId** – Product ID. For example, 6744249139353.
        - **ProductType** – Type of the product. For example, T-shirts.
        - **Quantity** – Product Quantity. For example, 1.
        - **Title** – Product Title. For example, Red T-shirt.
        - **URL** – Product URL. For example, /products/red-t-shirt-1?variant=39972529471641.
        - **VariantId** – Variant ID. For example, 39972529471641.
        - **VariantTitle** – Variant Title. For example, Nike Sneakers Shoe.
        - **Vendor** – Vendor name. For example, Acme stores.
      </td>
    </tr>

    <tr>
      <td>
        Removed from Cart
      </td>

      <td>
        When a product is removed from cart
      </td>

      <td>
        - **Currency** – Shopify store currency. For example, INR.
        - **Image** – URL of the product image. For example, [https://cdn.shopify.com/s/files/products/RedT-shirt.jpg](https://cdn.shopify.com/s/files/products/RedT-shirt.jpg).
        - **Price** – Product Price. For example, 2999.
        - **ProductId** – Product ID. For example, 6744249139353.
        - **ProductType** – Type of the product. For example, T-shirts.
        - **Quantity** – Product Quantity. For example, 1.
        - **Title** – Product Title. For example, Red T-shirt.
        - **URL** – Product URL. For example, /products/red-t-shirt-1?variant=39972529471641.
        - **VariantId** – Variant ID. For example, 39972529471641.
        - **VariantTitle** – Variant Title. For example, Nike Sneakers Shoe.
        - **Vendor** – Vendor name. For example, Acme stores.
      </td>
    </tr>

    <tr>
      <td>
        Customer Registered
      </td>

      <td>
        When a customer registers on the Shopify store
      </td>

      <td>
        - **Email** – Customer's email address. For example, [jack@acme.com](mailto:jack@acme.com).
        - **ID** – Customer ID. For example, 5204453556377.
      </td>
    </tr>

    <tr>
      <td>
        Customer Logged In
      </td>

      <td>
        When a customer logs in to the Shopify store.
      </td>

      <td>
        - **Email** – Customer's email address. For example, [jack@acme.com](mailto:jack@acme.com).
        - **ID** – Customer ID. For example, 52044535566377.
      </td>
    </tr>

    <tr>
      <td>
        Customer Logged Out
      </td>

      <td>
        When a customer logs out of the Shopify store.
      </td>

      <td>
        None.
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  #### Note

  The Charged and Checkout events are received through Shopify Webhooks. Therefore, these events are be received at CleverTap only for the users who have logged in.
</Callout>

#### Webhooks for Updating Profile Properties

The following Shopify webhooks update the corresponding customer profile properties in CleverTap. These webhooks do not create events in CleverTap.

| Webhooks to Subscribe                           | Profile property           |
| ----------------------------------------------- | -------------------------- |
| **CUSTOMER_EMAIL_MARKETING_CONSENT_UPDATED**    | Email Marketing Consent    |
| **CUSTOMER_MARKETING_CONSENT_UPDATED**          | SMS Marketing Consent      |
| **CUSTOMER_WHATSAPP_MARKETING_CONSENT_UPDATED** | WhatsApp Marketing Consent |
| **CUSTOMER_TAGS_ADDED**                         | Tags                       |
| **CUSTOMER_TAGS_REMOVED**                       | Tags                       |

<Callout icon="📘" theme="info">
  #### Customer Purchasing Summary

  The `CUSTOMER_PURCHASING_SUMMARY` webhook updates the Total Spent, Orders Count, and Last Order ID profile properties and also raises an event in CleverTap.
</Callout>

#### Webhook Supported Events

The following events are supported via the Shopify Webhook:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Events
      </th>

      <th>
        Event Properties
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        - **CUSTOMERS_CREATE**
        - **CUSTOMERS_UPDATE**
      </td>

      <td>
        - customer id
        - customer email
        - customer created at
        - customer updated at
        - customer first name
        - customer last name
        - customer phone
      </td>
    </tr>

    <tr>
      <td>
        - **FULFILLMENTS_CREATE**
        - **FULFILLMENTS_UPDATE**
      </td>

      <td>
        - id
        - order id
        - status
        - Created At
        - Updated At
        - email
        - service
        - tracking company
        - shipment status
        - location id
        - tracking number
        - tracking url
        - name
        - destination first name
        - destination last name
        - destination address1
        - destination phone
        - destination city
        - destination zip
        - destination province
        - destination country
        - destination address2
        - destination company
        - destination latitude
        - destination longitude
        - destination name
        - destination country code
        - destination province code
      </td>
    </tr>

    <tr>
      <td>
        - **CHECKOUTS_CREATE**
        - **CHECKOUTS_UPDATE**
        - **CHECKOUTS_DELETE**
      </td>

      <td>
        - email
        - buyer_accepts_marketing
        - Created At
        - Updated At
        - user id
        - location id
        - device id
        - phone
        - customer locale
        - name
        - source
        - abandoned checkout url
        - source name
        - total price
        - subtotal price
        - Currency
        - gateway
        - billing address zip
        - billing address province
        - billing address country
        - billing address city
        - billing address province code
        - billing address country code
        - ship address zip
        - ship address province
        - ship address country
        - ship address city
        - ship address province code
        - ship address country code
        - default address zip
        - default address province
        - default address country
        - default address city
        - default address province code
        - default address country code
      </td>
    </tr>

    <tr>
      <td>
        - **DRAFT_ORDERS_CREATE**
        - **DRAFT_ORDERS_UPDATE**
      </td>

      <td>
        Same as **CHECKOUTS_CREATE**, <br />**CHECKOUTS_UPDATE** and **CHECKOUTS_DELETE**
      </td>
    </tr>

    <tr>
      <td>
        - **ORDERS_CREATE**
        - **ORDERS_UPDATED**
        - **ORDERS_CANCELLED**
        - **ORDERS_FULFILLED**
        - **ORDERS_PARTIALLY_FULFILLED**
      </td>

      <td>
        - number
        - closed at
        - token
        - gateway
        - test
        - total weight
        - total tax
        - taxes included
        - financial status
        - confirmed
        - total discounts
        - total line items price
        - cart token
        - buyer accepts marketing
        - name
        - referring site
        - landing site
        - cancelled at
        - cancel reason
        - total price usd
        - checkout token
        - reference
        - source identifier
        - source url
        - processed at
        - device_id
        - app id
        - browser ip
        - landing site ref
        - order number
        - processing method
        - checkout id
        - source name
        - fulfilment status
        - contact email
        - order status url
        - presentment currency
        - total line items amount
        - total line items currency
        - total discount amount
        - total discount currency
        - total shipping amount
        - total shipping currency
        - Total Price amount
        - Total Price currency
        - Total Tax amount
        - Total Tax currency
      </td>
    </tr>

    <tr>
      <td>
        **ORDERS_PAID**
      </td>

      <td>
        - Amount
        - Currency
        - email
        - Ship_country
        - Ship_region
        - Ship_city
        - Items
        - Checkout ID
        - Charged ID
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  #### Note

  - All the above-listed Webhook events are captured only for logged-in users.
  - Items will be a part of event properties if ORDERS_PAID is selected as charged.
  - If a checkout webhook (CHECKOUTS_CREATE/UPDATE/DELETE) has an associated `customer` object, the full customer property set is prepended to the payload: customer id, email, accepts marketing, created at, updated at, first name, last name, orders count, total spent, phone, tags. If no `customer` object is present (e.g., guest checkout), these are omitted.
  - The block (Amount, Currency, email, Ship_country/region/city, Items, Checkout token, Charged ID) is not exclusive to `ORDERS_PAID` — it's appended to every order webhook variant, triggered by whichever event is configured as "Charged" in the dashboard, not the ORDERS_PAID topic specifically.
  - The checkout token stored in the Order webhook is mapped to the corresponding Checkout webhook, linking the Order event to the Checkout event.
</Callout>

### Catalog Sync

The _Catalog Sync_ feature simplifies catalog management by automating product data sync between customers' Shopify and CleverTap accounts. This integration ensures up-to-date catalogs are readily available for personalization across marketing channels like Email and WhatsApp, eliminating manual uploads.

To do this, enable the _Catalog Sync_ option in the _Advanced Customization_ section of the Shopify Integration page.


<Image src="https://files.readme.io/ae483bc6e383a109bd3bdac8268039910b12796d4215290ce302ef24d9509685-image.png" alt="Catalog Sync Feature for Shopify" align="center" caption="Catalog Sync Feature for Shopify" border={true} />


To enable Catalog Sync in your dashboard:

1. Go to the Shopify Integration page within CleverTap.
2. Click the _Advanced Customization_ section.
3. Toggle on the _Catalog Sync_ feature.

## Enable App Embed Status

The _App Embed_ status displays as _Enabled_ if enabled already.

The _App Embed_ status informs you if it is active. By default, app embed blocks are deactivated after an app is installed. However, if the _App Embed_ status is _Disabled_ , merchants must activate app embed blocks in the theme editor, from their Shopify theme settings. Refer to this detailed document on [App embeds](https://shopify.dev/apps/online-store/theme-app-extensions/extensions-framework#app-embed-blocks) to learn more.

To enable _CleverTap-Shopify App Embed_ on your Shopify store:

1. Navigate to your Shopify store's theme settings page using the following URL:<br />https\://\<Your-Shopify-store-name>.myshopify.com/admin/themes/current/editor?context=apps\&activateAppId=2566991a-cd89-49d8-997d-74717582b9ed/app-embed.
2. Toggle ON the _Clevertap-Shopify_ App embed and click  **Save** at the top right corner.


<Image src="https://files.readme.io/22c77b8-CT_shopify_app_embed.png" alt="2846" align="center" caption="Toggle ON CleverTap-Shopify" border={true} />


To check if the _CleverTap-Shopify_ App embed is enabled:

1. Navigate to your Shopify store,  right-click and, select _Inspect_.
2. Navigate to _Sources_ tab and select _Page_.
3. Search for the _clevertap-shopify.js_ file in the _extensions_ folder under _cdn.Shopify.com_. Refer to the following image:


<Image src="https://files.readme.io/4f64635-shopify_app_ambed.png" alt="2262" align="center" caption="Verify if CleverTap-Shopify App Embed is Enabled" border={true} />


# Cart Abandonment Use Case

Cart personalization allows businesses to send dynamic cart abandonment emails displaying all the products users have left in their cart without making a purchase. Events such as _Add to Cart_ store the most recent product added to the cart. This limitation prevents a real-time view of all the products in the cart, making it difficult to run campaigns that fully reflect the user’s cart activity.

CleverTap uses a combination of User Properties and Catalog Personalization to achieve the card abandonment use case:

* User Properties: Stores variant IDs in an array format when users add items to their cart. These properties update dynamically when items are added or removed during checkout.
* Catalogs: These contain additional product details, such as product name, image URL, and price, and are synced in the CleverTap dashboard using the Shopify Catalog Sync feature.

This approach enables businesses to create dynamic campaigns that accurately reflect the state of the user’s cart. By combining user properties with catalogs and advanced personalization techniques like liquid tags, CleverTap enhances the effectiveness of cart abandonment campaigns, delivering an effortless shopping experience.

<Callout icon="📘" theme="info">
  ### Note

  Cart Personalization works only if the _Added to Cart, Charged_, and _Removed from Cart_ events are sourced through the CleverTap Shopify plugin. Custom implementations of these events are not supported.
</Callout>

***

## Live Action Email Campaign

Learn how to create personalized cart abandonment emails using CleverTap's Live Action Email campaigns.

### Scenario

A user visits an e-commerce store and adds multiple items to their shopping cart. However, the user leaves the website without making a purchase.

### Objective

Using Cart Personalization, you can:

* Encourage users to complete their purchases by sending tailored, timely reminders via Email.
* Recover potential lost revenue.
* Provide a personalized and seamless shopping experience for the users.

### Steps to Implement Cart Abandonment Campaigns

To set up an Email campaign, follow these steps on the CleverTap Dashboard:

1. **Toggle th&#x65;_&#x43;atalog Sync_ feature:**
   Toggle the [Catalog Sync](doc:shopify#catalog-sync) feature to automatically sync product data between customers' Shopify and CleverTap accounts.

2. **Toggle th&#x65;_&#x43;art Tracking_ feature:**<br />This feature ensures that the variant IDs from the users' cart are stored in their CleverTap profile. For example, when a user adds a product to their cart, the variant ID will be saved as a user property in an array format in the user's profile, under the _shopify_cart_ids_. Similarly, when a user removes a product from the cart, the variant ID will be removed automatically. To enable Cart Tracking in your dashboard:
   1. Go to the Shopify Integration page within CleverTap.
   2. Click the **Advanced Customization** section.
   3. Toggle on the _Cart Tracking_ feature.


<Image src="https://files.readme.io/c0fefb62ad253596f3f2d1c62bda2548d16a27d2ac2bf70bf655af213b44096a-Screenshot_2024-12-05_at_12.46.43_PM.png" alt="Cart Sync Toggle" align="center" caption="Cart Sync Toggle" border={true} />


3. **Create the Campaign:**

Define the campaign as an inaction campaign targeting users who added products to the cart but did not complete a checkout action within 15 minutes.


<Image src="https://files.readme.io/adf624ca6ddb47cb4b9e46c437ecfff5dafd548a710f3c2aa9bb60e51ac05c08-Screenshot_2024-12-05_at_11.27.46_AM.png" alt="Inaction Campaign" align="center" width="60% " caption="Inaction Campaign" border={true} />


For more information, refer to [Create an Email Campaign](doc:create-message-email).

4. **Mapping the campaign with Catalog:**
   1. Go to _What_ section of the campaign editor and click on _Personalization_.
   2. From the _Catalog_ tab, select _shopify-catalog_.
   3. Select the _shopify_cart_ids_ user property and map it to the _Identity_ column in the catalog.


<Image src="https://files.readme.io/ec0aefb4bb66864d8dbcdc65e7631e30176716400cb2ba588cbdcba56a8f8b8d-2025-02-17_19-02-10.png" alt="Mapping the Catalog" align="center" caption="Mapping the Catalog" border={true} />


5. **Set U&#x70;_&#x50;ersonalization_ with Liquid Tags:**
   1. In the _What_ section of the email body editor, drag a _Text_ field into the email body.
   2. Click on **More** and select the _Customize with Liquid tags_ option.
   3. Use Liquid Tags to dynamically fetch the  product details (name, image, price, etc.) from the catalog's CSV file.


<Image src="https://files.readme.io/17734120560e5e20a2df3dfd1126e1d61124115cdf586a37fd88937874a783a0-Image_4.jpeg" alt="Liquid Tags" align="center" caption="Liquid Tags" border={true} />


For example, you can use HTML tags to create a table and `For loop` in Liquid tags to traverse the Catalog. The `For loop` will run until it covers all the Variant IDs in the Profile property.

<Callout icon="ℹ️" theme="info">
  ### Key Considerations

  If a user empties the cart without performing the Charged event, the `For loop` in the liquid tags will not run. Consequently, the Email will be delivered without product data, as the user remains eligible for the campaign despite having no variant IDs. Therefore, ensure that the email templates are designed to handle scenarios where the product table does not render, maintaining a professional appearance.
</Callout>

6. **Apply Frequency Caps:**

To prevent multiple emails on every _Add to Cart_ event trigger for a single user, apply a frequency cap within the campaign to send only one email per cart addition.

7. **Test the Email to ensure correctness:**

You can test the campaign to ensure personalized rendering of product details from the products left in your cart.


<Image src="https://files.readme.io/0f42d963a2e2370541c1d499465a3e1afae88f8176d11faa7f961bb7ed5a875e-Image_5.jpeg" alt="Final look of the Email" align="center" caption="Final View of the Email" border={true} />


CleverTap's cart abandonment campaigns allow businesses to recover revenue by re-engaging users with personalized messages, thus driving conversions.

# Create Web Campaigns

The CleverTap Shopify plugin provides support for web channels such as [Web Push](doc:web-push) , [Web Pop-up](doc:web-pop-ups) , and [Web Exit Intent](doc:web-exit-intent) without the need for any manual code integration.

To create a Web campaign:

1. From the dashboard, navigate to _Campaigns_.
2. Click **+ Campaign**.
3. Create a [Web Push](doc:web-push) , [Web Pop-up](doc:web-pop-ups) , or [Web Exit Intent](doc:web-exit-intent) campaign to engage your users.

# FAQs

### Q. Does my current billing plan include integration with the Shopify plugin?

Yes. This Shopify plugin is available for all CleverTap billing plans.

### Q. I have a Shopify web store and a mobile app. How do I target users who have performed an event on my Shopify store?

To target the users who have performed the event on your store:

1. Select the event (for example, added to cart) in the CleverTap segment builder.
2. Filter by event property _CT Source_ equal to _Shopify_.


<Image src="https://files.readme.io/f955291-shopify_segment_identify.png" alt="1005" align="center" caption="Filtering Shopify Users from Find People Page" border={true} />


### Q. I see a warning _Shopify installation seems to have a few missing files_ displayed at the end of the Project page. How do I resolve this warning?

CleverTap recommends reinstalling the plugin by clicking **Reinstall**.

### Q. Will this plugin work for Shopify Plus customers?

Yes. This Plugin works for Shopify Plus customers too.
