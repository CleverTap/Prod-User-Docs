---
title: Shopify
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

CleverTap plugin provides an easy way to integrate your Shopify stores within minutes without any code. All you need is a CleverTap account and you can have a seamless flow of events and user data from your Shopify store. You can also send personalized messages to your users through channels such as [Web Push](doc:web-push) notifications, [Web Pop-up](doc:web-pop-ups), and [Web Exit Intent](doc:web-exit-intent). 

> 📘 Note
>
> Enable the [Web Push](https://docs.clevertap.com/docs/shopify#section-enable-web-push) notifications from the CleverTap dashboard before integrating the plugin with your Shopify store.

# Setup Web Push

You can send personalized communication to your users through Web Push notifications. However, you must enable them first from the CleverTap dashboard, before integrating the plugin with your Shopify store. 

## Enable Web Push

The Web Push channel must be enabled *before* you connect the CleverTap plugin with your Shopify store.  Follow the steps to enable Web Push:

1. Navigate to *Settings > Channels > Web Push* , save the keys for Chrome and Firefox, and turn on the toggles for Web Push.

<Image title="Shopify_enable_webpush.png" alt={946} className="border" width="80%" border={true} src="https://files.readme.io/9db32c4-Shopify_enable_webpush.png" />

2. [Integrate the Shopify store](https://docs.clevertap.com/docs/shopify#section-integrate-shopify-with-clever-tap) from the CleverTap dashboard integrations page.  

## Disable Web Push

If you do not want to continue sending personalized communication with your users through Web Push notifications, you can disable them.\
To disable Web Push follow the steps:

1. Navigate to *Settings > Channels > Web Push* and turn off the toggles for Chrome and Firefox to disable Web Push.
2. Reconnect the Shopify store integration from the CleverTap dashboard integrations page. 

<Image title="Shopify_disable_webpush.png" alt={973} className="border" width="80%" border={true} src="https://files.readme.io/173f225-Shopify_disable_webpush.png" />

# Integrate Shopify with CleverTap

Connect your Shopify store with CleverTap by logging into your dashboard.

1. Click **Integrate on other platforms**. The integration page displays. 

<Image title="Shopify_CT_Dashboard_menu.png" alt={1037} className="border" border={true} src="https://files.readme.io/22dd870-Shopify_CT_Dashboard_menu.png" />

2. Select *Shopify* from the list. 
3. Provide the name for your Shopify store and click **Connect**. The Shopify login page displays. 

<Image title="Shopify_Integration_main.png" alt={1095} className="border" border={true} src="https://files.readme.io/88a8e25-Shopify_Integration_main.png" />

3. Enter your Shopify username and password and proceed with the suggested steps to install the CleverTap app. 

<Image title="Shopify_Store_credentials.png" alt={580} className="border" border={true} src="https://files.readme.io/41f03fc-Shopify_Store_credentials.png" />

Once connected, CleverTap starts receiving events and user properties of users visiting your Shopify store.

> 📘 Release Date
>
> The new Shopify plugin was released on June 25, 2021.

# Supported Events

The following table displays all the events supported by the new plugin.  

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
        * Page - The store page. For example, Index page.
        * Title - Title of the page. For example, Acme home.
        * URL - URL of the page. For example, [https://mystore.myshopify.com/](https://mystore.myshopify.com/).
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
        * Available - Availability of the product. For example, TRUE.
        * Currency - Shopify store currency. For example, INR. 
        * Handle - Product Handle. For example, nike-sneakers-shoe.
        * ID - Product ID. For example, 6744256675993.
        * Price - Product Price. For example, 2999.
        * Title - Product Title. For example, Nike Sneakers Shoe. 
        * TotalVariants - Number of variants available. For example, 3.
        * URL - URL of the product page. For example, /products/nike-sneakers-shoe.
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
        * Currency - Shopify store currency.
        * Term - Search terms used. For example, red shoe.
        * TotalItems - Number of items in search results. For example, 1.
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
        * Currency - Shopify store currency. For example, INR.
        * Image - URL of the product image. For example, [https://cdn.shopify.com/s/files/products/RedT-shirt.jpg](https://cdn.shopify.com/s/files/products/RedT-shirt.jpg).
        * Price - Product Price. For example, 2999.
        * ProductId - Product ID. For example, 6744249139353.
        * ProductType - Type of the product. For example, T-shirts.
        * Quantity - Product Quantity. For example, 1.
        * Title - Product Title. For example, Red T-shirt.
        * URL - Product URL. For example, /products/red-t-shirt-1?variant=39972529471641.
        * VariantId - Variant ID. For example, 39972529471641.
        * VariantTitle - Variant Title. For example, Nike Sneakers Shoe.
        * Vendor - Vendor name. For example, Acme stores.
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
        * Currency - Shopify store currency. For example, INR.
        * Image - URL of the product image. For example, [https://cdn.shopify.com/s/files/products/RedT-shirt.jpg](https://cdn.shopify.com/s/files/products/RedT-shirt.jpg).
        * Price - Product Price. For example, 2999.
        * ProductId - Product ID. For example, 6744249139353.
        * ProductType - Type of the product. For example, T-shirts.
        * Quantity - Product Quantity. For example, 1.
        * Title - Product Title. For example, Red T-shirt.
        * URL - Product URL. For example, /products/red-t-shirt-1?variant=39972529471641.
        * VariantId - Variant ID. For example, 39972529471641.
        * VariantTitle - Variant Title. For example, Nike Sneakers Shoe.
        * Vendor - Vendor name. For example, Acme stores.
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
        * Email - Customer's email address. For example, [jack@acme.com](mailto:jack@acme.com).
        * Name - Customer's name. For example, John Doe 
        * FirstName - Customer's first name. For example, John. 
        * LastName - Customer's last name. For example, Doe.
        * ID - Customer ID. For example, 5204453556377.
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
        * Email - Customer's email address. For example, [jack@acme.com](mailto:jack@acme.com).
        * Name - Customer's name. For example, John Doe 
        * FirstName - Customer's first name. For example, John. 
        * LastName - Customer's last name. For example, Doe.
        * ID - Customer ID. For example, 5204453556377.
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

    <tr>
      <td>
        Checkout
      </td>

      <td>
        When a customer checks out items.
      </td>

      <td>
        * TotalItems - Number of items in the cart. For example, 5. 
        * Currency - Shopify store currency. For example, INR.
      </td>
    </tr>

    <tr>
      <td>
        Charged
      </td>

      <td>
        When a customer successfully completes the purchase .
      </td>

      <td>
        * Items - List of items charged with individual item properties such as Title, Vendor, quantity, price, productID and so on. For example, Items | 6612076593358|Running. Shoe|1|Acme, where  Product ID -  6612076593358,\
          Product Title - Running Shoe,\
          Quantity - 1, and\
          Vendor - Acme.
        * TotalItems - Total number of Items charged. For example, 3.
        * Currency - Shopify store currency. For example, INR.
      </td>
    </tr>
  </tbody>
</Table>

# Supported User Properties

The following table displays all the user properties supported by the plugin.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        User Property
      </th>

      <th>
        Property Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Name
      </td>

      <td>
        The customer's name. For example, Jack.
      </td>
    </tr>

    <tr>
      <td>
        Phone
      </td>

      <td>
        The customer's mobile number. For example, 97650000.
      </td>
    </tr>

    <tr>
      <td>
        Email
      </td>

      <td>
        The customer's email address. For example, [jack@acme.com](mailto:jack@acme.com).
      </td>
    </tr>

    <tr>
      <td>
        Identity
      </td>

      <td>
        The customer's  CleverTap ID. For example, 3645910.
      </td>
    </tr>

    <tr>
      <td>
        Tags
      </td>

      <td>
        The list of tags associated with the customer. For example, Gold customer.
      </td>
    </tr>

    <tr>
      <td>
        City
      </td>

      <td>
        The customer's city. For example, Mumbai.
      </td>
    </tr>

    <tr>
      <td>
        Accepts Marketing
      </td>

      <td>
        This property returns the value as *true* if the customer accepts marketing. If the customer does not accept then returns the value as *false*.
      </td>
    </tr>

    <tr>
      <td>
        Has Account
      </td>

      <td>
        This property returns the value as *true* if the email associated with the customer is linked to a customer account. The property returns the value as false if the email is not linked to the customer account.
      </td>
    </tr>

    <tr>
      <td>
        Orders Count
      </td>

      <td>
        The total number of orders from a customer.
      </td>
    </tr>

    <tr>
      <td>
        Tax Exempt
      </td>

      <td>
        Whether or not the customer is exempt from taxes.
      </td>
    </tr>

    <tr>
      <td>
        Total Spent
      </td>

      <td>
        Total amount spent on all orders. For example, 5400.
      </td>
    </tr>

    <tr>
      <td>
        Shopify Id
      </td>

      <td>
        The Shopify ID of the customer.  For example, 29873645910.
      </td>
    </tr>

    <tr>
      <td>
        First Name
      </td>

      <td>
        The customer's first name.
      </td>
    </tr>

    <tr>
      <td>
        LastName
      </td>

      <td>
        The customer's first name.
      </td>
    </tr>
  </tbody>
</Table>

# Create Web Campaigns

The CleverTap Shopify plugin provides support for web channels such as [Web Push](doc:web-push) , [Web Pop-up](doc:web-pop-ups) , and [Web Exit Intent](doc:web-exit-intent) without the need for any manual code integration.

To create a Web campaign:

1. From the dashboard, navigate to *Campaigns*.
2. Click **+ Campaign**.
3. Create a [Web Push](doc:web-push) , [Web Pop-up](doc:web-pop-ups) , or [Web Exit Intent](doc:web-exit-intent) campaign to engage your users.

# Migrate from Previous Plugin

The new version of the Shopify plugin was released on June 25, 2021. The previous version of this plugin supports events such as Search, Category Viewed, Product Viewed, Added to Cart, and Charged. This version also provides support for  [Web Pop-up](doc:web-pop-ups) and [Web Exit Intent](doc:web-exit-intent) channels.

If you want to upgrade to the latest version of the plugin, please reach out to your *Customer Success* personnel or raise a support ticket from the dashboard.

# FAQs

### Q. Does my current billing plan include integration with the Shopify plugin?

Yes. This Shopify plugin is available for all CleverTap billing plans.

### Q. I have already installed CleverTap’s Shopify plugin. How can I migrate to the new Shopify Plugin released by CleverTap on June 25, 2021?

Please reach out to your *Customer Success* personnel or raise a support ticket from the dashboard.

### Q. I have a Shopify web store and a mobile app. How do I target users who have performed an event on my Shopify store?

Follow the steps:

1. Select that the event (for example added to cart) in the CleverTap segment builder.
2. Filter by event property CT Source equal to Shopify.

![1005](https://files.readme.io/f955291-shopify_segment_identify.png "shopify_segment_identify.png")
