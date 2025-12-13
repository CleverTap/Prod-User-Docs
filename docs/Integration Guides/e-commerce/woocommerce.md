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
[block:parameters]
{
  "data": {
    "h-0": "Event Name",
    "h-1": "Description",
    "h-2": "Properties",
    "0-0": "Category Viewed",
    "1-0": "Product Viewed",
    "3-0": "Charged",
    "2-0": "Added To Cart",
    "0-1": "When a user visits the category section.",
    "1-1": "When a user views a product.",
    "2-1": "When a user adds the product to the shopping cart.",
    "3-1": "On successful completion of purchase.",
    "0-2": "Category name",
    "1-2": "Product Name \nCategory Name\nPrice \nCurrency",
    "2-2": "Product Name \nCategory Name\nAmount \nCurrency\nQuantity",
    "3-2": "Amount \nCurrency \nPayment mode\nItems \n  * Ship country\n  * Ship region \n  * Ship city \n  * Vendor \n\nCharged ID"
  },
  "cols": 3,
  "rows": 4
}
[/block]