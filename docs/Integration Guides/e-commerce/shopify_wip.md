---
title: Shopify_WIP
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
# Integrate Shopify and CleverTap

Connect your Shopify store with CleverTap by logging into your Dashboard.

1. Click the Integrate on other platforms. The integration page appears.

![1099](https://files.readme.io/4a99a91-Shopify_CT_Dashboard_menu.png "Shopify_CT_Dashboard_menu.png")

2. Select Shopify from the list. 
3. Provide your Shopify Store name and click Connect. The Shopify login page appears.

![1074](https://files.readme.io/537b9a9-Shopify_Link.png "Shopify_Link.png")

3. Enter your Shopify username and password and proceed with the suggested steps. 

![580](https://files.readme.io/41f03fc-Shopify_Store_credentials.png "Shopify_Store_credentials.png")

Once connected, CleverTap will automatically create User Profiles for your Shopify users. On Shopify checkout, the user’s name and email address will automatically be set as User Profile attributes on the CleverTap User Profile. In addition, CleverTap will automatically record the following User Events from Shopify on the CleverTap User Profile.

# Events Captured Automatically in CleverTap from Shopify

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
        Search
      </td>

      <td>
        When a search is performed.
      </td>

      <td>
        Term
      </td>
    </tr>

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
        Category\
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
        Category\
        Price\
        Currency
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

        * Product\_Id 
        * Title 
        * Quantity 
        * Vendor 

        Ship country\
        Ship region\
        Ship city\
        Email\
        Charged ID
      </td>
    </tr>
  </tbody>
</Table>
