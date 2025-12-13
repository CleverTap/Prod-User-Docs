---
title: Magento
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
Once connected, CleverTap will automatically create user profiles for your Magento users and record events automatically.

# Install the CleverTap Extension in Magento

[Download](http://static.clevertap.com/sdks/clevertap_magento.zip) and install the CleverTap extension for Magento. 

Next, specify your CleverTap Account ID in the Magento admin settings page.

Once connected, CleverTap will automatically create User Profiles for your Magento users. On Magento login or checkout, the user name and email address will automatically be set as attributes on the CleverTap User Profile. In addition, CleverTap will automatically record the following User Events from Magento on the CleverTap User Profile.

# Events Automatically Captured from Magento

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
        Category 
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
        Product name\
        Category\
        Price\
        Currency\
        ID (Product ID) 
      </td>
    </tr>

    <tr>
      <td>
        Added to Cart
      </td>

      <td>
        When a user adds a product to the shopping cart.
      </td>

      <td>
        Product Name\
        Category\
        Price\
        Currency\
        Qty 
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
        Items 

        * Category 
        * Product name 
        * Quantity 

        Country\
        Region\
        City\
        Charged ID\
        Payment mode
      </td>
    </tr>
  </tbody>
</Table>
