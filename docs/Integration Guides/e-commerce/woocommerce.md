---
title: WooCommerce
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
# Install the Plugin

* Download the [CleverTap plugin for WooCommerce](http://static.clevertap.com/sdks/clevertap_woocommerce.zip).
* Unzip the plugin and put it in web/wp-content/plugins directory.
* Specify your CleverTap Account ID in the admin settings page.

Once connected, CleverTap will automatically create User Profiles for your WooCommerce users. On WooCommerce login or checkout, the user’s name and email address will automatically be set as attributes on the CleverTap User Profile. In additon, CleverTap will automatically record the following User Events from WooCommerce on the CleverTap User Profile.

# Events Captured Automatically in CleverTap from WooCommerce

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
        Category Viewed
      </td>

      <td>
        When a user visits the category section.
      </td>

      <td>
        Category name
      </td>
    </tr>

    <tr>
      <td>
        Product Viewed
      </td>

      <td>
        When a user views a product.
      </td>

      <td>
        Product Name\
        Category Name\
        Price\
        Currency
      </td>
    </tr>

    <tr>
      <td>
        Added To Cart
      </td>

      <td>
        When a user adds the product to the shopping cart.
      </td>

      <td>
        Product Name\
        Category Name\
        Amount\
        Currency\
        Quantity
      </td>
    </tr>

    <tr>
      <td>
        Charged
      </td>

      <td>
        On successful completion of purchase.
      </td>

      <td>
        Amount\
        Currency\
        Payment mode\
        Items 

        * Ship country
        * Ship region 
        * Ship city 
        * Vendor 

        Charged ID
      </td>
    </tr>
  </tbody>
</Table>
