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
[block:parameters]
{
  "data": {
    "h-0": "Event Name",
    "h-1": "Description",
    "h-2": "Properties",
    "0-0": "Category Viewed",
    "1-0": "Product Viewed",
    "2-0": "Added to Cart",
    "3-0": "Charged",
    "0-1": "When a user visits the category section.",
    "1-1": "When a user views a product.",
    "2-1": "When a user adds a product to the shopping cart.",
    "3-1": "On successful completion of purchase.",
    "0-2": "Category ",
    "1-2": "Product name \nCategory \nPrice \nCurrency \nID (Product ID) ",
    "2-2": "Product Name \nCategory \nPrice \nCurrency \nQty ",
    "3-2": "Amount \nCurrency \nItems \n  * Category \n  * Product name \n  * Quantity \n\nCountry \nRegion \nCity \nCharged ID \nPayment mode"
  },
  "cols": 3,
  "rows": 4
}
[/block]