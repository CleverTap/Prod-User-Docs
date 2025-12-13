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
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4a99a91-Shopify_CT_Dashboard_menu.png",
        "Shopify_CT_Dashboard_menu.png",
        1099,
        586,
        "#e5e4ec"
      ]
    }
  ]
}
[/block]
2. Select Shopify from the list. 
3. Provide your Shopify Store name and click Connect. The Shopify login page appears.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/537b9a9-Shopify_Link.png",
        "Shopify_Link.png",
        1074,
        840,
        "#f2f7f5"
      ]
    }
  ]
}
[/block]
3. Enter your Shopify username and password and proceed with the suggested steps. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/41f03fc-Shopify_Store_credentials.png",
        "Shopify_Store_credentials.png",
        580,
        404,
        "#f8f8fb"
      ]
    }
  ]
}
[/block]
Once connected, CleverTap will automatically create User Profiles for your Shopify users. On Shopify checkout, the user’s name and email address will automatically be set as User Profile attributes on the CleverTap User Profile. In addition, CleverTap will automatically record the following User Events from Shopify on the CleverTap User Profile.

# Events Captured Automatically in CleverTap from Shopify
[block:parameters]
{
  "data": {
    "h-0": "Event Name",
    "h-1": "Description",
    "h-2": "Properties",
    "0-0": "Search",
    "1-0": "Category Viewed",
    "2-0": "Product Viewed",
    "4-0": "Charged",
    "3-0": "Added To Cart",
    "0-1": "When a search is performed.",
    "1-1": "When a user visits the category section.",
    "2-1": "When a user views a product.",
    "3-1": "When a user adds the product to the shopping cart.",
    "4-1": "On successful completion of purchase.",
    "0-2": "Term",
    "1-2": "Category name",
    "2-2": "Product Name \nCategory \nPrice \nCurrency",
    "3-2": "Product Name \nCategory \nPrice \nCurrency",
    "4-2": "Amount \nCurrency \nItems \n  * Product_Id \n  * Title \n  * Quantity \n  * Vendor \n\nShip country \nShip region \nShip city \nEmail \nCharged ID"
  },
  "cols": 3,
  "rows": 5
}
[/block]