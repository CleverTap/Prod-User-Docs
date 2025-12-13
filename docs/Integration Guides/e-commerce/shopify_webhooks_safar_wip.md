---
title: Shopify_Webhooks_Safari_WIP
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
CleverTap plugin provides an easy way to integrate your Shopify stores within minutes without any code. All you need is a CleverTap account and you can have a seamless flow of events and user data from your Shopify store. You can also send personalized messages to your users through channels such as [Web Push](doc:web-push) notifications, [Web Pop-up](doc:web-pop-ups), and [Web Exit Intent](doc:web-exit-intent). 


[block:callout]
{
  "type": "info",
  "body": "Enable the [Web Push](https://docs.clevertap.com/docs/shopify#section-enable-web-push) notifications from the CleverTap dashboard before integrating the plugin with your Shopify store.",
  "title": "Note"
}
[/block]
# Setup Web Push

You can send personalized communication to your users through Web Push notifications. However, you must enable them first from the CleverTap dashboard, before integrating the plugin with your Shopify store. 

## Enable Web Push
The Web Push channel must be enabled *before* you connect the CleverTap plugin with your Shopify store.  Follow the steps to enable Web Push:
1. Navigate to *Settings > Channels > Web Push *, save the keys for Chrome, Firefox, and turn on the toggles for Web Push.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9db32c4-Shopify_enable_webpush.png",
        "Shopify_enable_webpush.png",
        946,
        1150,
        "#fafafc"
      ],
      "sizing": "80",
      "border": true
    }
  ]
}
[/block]
2. [Integrate the Shopify store](https://docs.clevertap.com/docs/shopify#section-integrate-shopify-with-clever-tap) from the CleverTap dashboard integrations page.  

## Disable Web Push
If you do not want to continue sending personalized communication with your users through Web Push notifications, you can disable them. 
To disable Web Push follow the steps:

1. Navigate to *Settings > Channels > Web Push *and turn off the toggles for Chrome and Firefox to disable Web Push.
2. Reconnect the Shopify store integration from the CleverTap dashboard integrations page. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/173f225-Shopify_disable_webpush.png",
        "Shopify_disable_webpush.png",
        973,
        1220,
        "#fafafc"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]

# Integrate Shopify with CleverTap

Connect your Shopify store with CleverTap by logging into your dashboard.

1. Click **Integrate on other platforms**. The integration page displays. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/22dd870-Shopify_CT_Dashboard_menu.png",
        "Shopify_CT_Dashboard_menu.png",
        1037,
        551,
        "#e4e3eb"
      ],
      "border": true
    }
  ]
}
[/block]
2. Select *Shopify* from the list. 
3. Provide the name for your Shopify store and click **Connect**. The Shopify login page displays. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88a8e25-Shopify_Integration_main.png",
        "Shopify_Integration_main.png",
        1095,
        837,
        "#f2f7f5"
      ],
      "border": true
    }
  ]
}
[/block]
3. Enter your Shopify username and password and proceed with the suggested steps to install the CleverTap app. 
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
      ],
      "border": true
    }
  ]
}
[/block]
Once connected, CleverTap starts receiving events and user properties of users visiting your Shopify store.

[block:callout]
{
  "type": "info",
  "title": "Release Date",
  "body": "The new Shopify plugin was released on June 25, 2021."
}
[/block]

# Supported Events

The following table displays all the events supported by the new plugin.  
[block:parameters]
{
  "data": {
    "h-0": "Event Name",
    "h-1": "Description",
    "h-2": "Properties",
    "1-0": "Product Viewed",
    "3-0": "Added To Cart",
    "1-1": "When the user views a product",
    "3-1": "When a product is added to cart",
    "1-2": "* Available - Availability of the product. For example, TRUE.\n* Currency - Shopify store currency. For example, INR. \n* Handle - Product Handle. For example, nike-sneakers-shoe.\n* ID - Product ID. For example, 6744256675993.\n* Price - Product Price. For example, 2999.\n* Title - Product Title. For example, Nike Sneakers Shoe. \n* TotalVariants - Number of variants available. For example, 3.\n* URL - URL of the product page. For example, /products/nike-sneakers-shoe.",
    "3-2": "* Currency - Shopify store currency. For example, INR.\n* Image - URL of the product image. For example, https://cdn.shopify.com/s/files/products/RedT-shirt.jpg.\n* Price - Product Price. For example, 2999.\n* ProductId - Product ID. For example, 6744249139353.\n* ProductType - Type of the product. For example, T-shirts.\n* Quantity - Product Quantity. For example, 1.\n* Title - Product Title. For example, Red T-shirt.\n* URL - Product URL. For example, /products/red-t-shirt-1?variant=39972529471641.\n* VariantId - Variant ID. For example, 39972529471641.\n* VariantTitle - Variant Title. For example, Nike Sneakers Shoe.\n* Vendor - Vendor name. For example, Acme stores.",
    "0-0": "Page Browse",
    "0-2": "* Page - The store page. For example, Index page.\n* Title - Title of the page. For example, Acme home.\n* URL - URL of the page. For example, https://mystore.myshopify.com/.",
    "4-0": "Removed from Cart",
    "4-2": "* Currency - Shopify store currency. For example, INR.\n* Image - URL of the product image. For example, https://cdn.shopify.com/s/files/products/RedT-shirt.jpg.\n* Price - Product Price. For example, 2999.\n* ProductId - Product ID. For example, 6744249139353.\n * ProductType - Type of the product. For example, T-shirts.\n* Quantity - Product Quantity. For example, 1.\n* Title - Product Title. For example, Red T-shirt.\n* URL - Product URL. For example, /products/red-t-shirt-1?variant=39972529471641.\n* VariantId - Variant ID. For example, 39972529471641.\n* VariantTitle - Variant Title. For example, Nike Sneakers Shoe.\n* Vendor - Vendor name. For example, Acme stores.",
    "4-1": "When a product is removed from cart",
    "5-0": "Customer Registered",
    "5-2": "* Email - Customer's email address. For example, jack@acme.com.\n* Name - Customer's name. For example, John Doe \n* FirstName - Customer's first name. For example, John. \n* LastName - Customer's last name. For example, Doe.\n* ID - Customer ID. For example, 5204453556377.",
    "6-0": "Customer Logged In",
    "6-2": "* Email - Customer's email address. For example, jack@acme.com.\n* Name - Customer's name. For example, John Doe \n* FirstName - Customer's first name. For example, John. \n* LastName - Customer's last name. For example, Doe.\n* ID - Customer ID. For example, 5204453556377.",
    "0-1": "This event is recorded when the user visits a page",
    "2-0": "Searched Product",
    "2-1": "When a product is searched",
    "2-2": "* Currency - Shopify store currency.\n* Term - Search terms used. For example, red shoe.\n* TotalItems - Number of items in search results. For example, 1.",
    "5-1": "When a customer registers on the Shopify store",
    "6-1": "When a customer logs in to the Shopify store.",
    "7-0": "Customer Logged Out",
    "7-1": "When a customer logs out of the Shopify store.",
    "7-2": "None.",
    "8-0": "Checkout",
    "8-1": "When a customer checks out items.",
    "8-2": "* TotalItems - Number of items in the cart. For example, 5. \n* Currency - Shopify store currency. For example, INR.",
    "9-0": "Charged",
    "9-1": "When a customer successfully completes the purchase .",
    "9-2": "* Items - List of items charged with individual item properties such as Title, Vendor, quantity, price, productID and so on. For example, Items | 6612076593358|Running. Shoe|1|Acme, where  Product ID -  6612076593358,\nProduct Title - Running Shoe,\nQuantity - 1, and \nVendor - Acme.\n* TotalItems - Total number of Items charged. For example, 3.\n* Currency - Shopify store currency. For example, INR."
  },
  "cols": 3,
  "rows": 10
}
[/block]

# Supported User Properties

The following table displays all the user properties supported by the plugin.
[block:parameters]
{
  "data": {
    "h-0": "User Property",
    "h-1": "Property Description",
    "h-2": "Property Description",
    "0-0": "Name",
    "1-0": "Phone",
    "2-0": "Email",
    "3-0": "Identity",
    "4-0": "Tags",
    "5-0": "City",
    "6-0": "Accepts Marketing",
    "7-0": "Has Account",
    "8-0": "Orders Count",
    "9-0": "Tax Exempt",
    "10-0": "Total Spent",
    "11-0": "Shopify Id",
    "12-0": "First Name",
    "13-0": "LastName",
    "0-2": "The customer's name. For example, Jack.",
    "1-2": "The customer's mobile number. For example, 97650000",
    "2-2": "The customer's email address. For example,",
    "3-2": "The customer's  CleverTap Id. For example, 3645910.",
    "12-2": "The customer's",
    "13-2": "The customer's",
    "4-2": "The list of tags associated with the customer. For example, VIP. <<@soumya, what does this tag mean VIP?>>",
    "5-2": "The customer's city. For example, Mumbai.",
    "0-1": "The customer's name. For example, Jack.",
    "1-1": "The customer's mobile number. For example, 97650000.",
    "2-1": "The customer's email address. For example, jack@acme.com.",
    "3-1": "The customer's  CleverTap ID. For example, 3645910.",
    "4-1": "The list of tags associated with the customer. For example, Gold customer.",
    "5-1": "The customer's city. For example, Mumbai.",
    "6-1": "This property returns the value as *true* if the customer accepts marketing. If the customer does not accept then returns the value as *false*.",
    "7-1": "This property returns the value as *true* if the email associated with the customer is linked to a customer account. The property returns the value as false if the email is not linked to the customer account.",
    "8-1": "The total number of orders from a customer.",
    "9-1": "Whether or not the customer is exempt from taxes.",
    "10-1": "Total amount spent on all orders. For example, 5400.",
    "11-1": "The Shopify ID of the customer.  For example, 29873645910.",
    "12-1": "The customer's first name.",
    "13-1": "The customer's first name."
  },
  "cols": 2,
  "rows": 14
}
[/block]

# Setup Shopify Webhook

Follow these steps to configure each event through Shopify webhooks.

1. Go to the Shopify admin panel in your store. 
2. Go to *Settings > Notifications*. 
3. Scroll down to the *Webhooks* section.
4. Click **Create Webhook**. The *Add webhook* window appears.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/06a6309-Shopify_webhook.png",
        "Shopify_webhook.png",
        435,
        273,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]
5. Select the [supported event](https://docs.clevertap.com/docs/shopify_webhooks#section-webhook-supported-events) from the list.
6. Enter the CleverTap endpoint URL. For example, *https://api.clevertap.com/shopify/m/<Account ID>* 
7.  Click Save.

## Webhook Supported Events

The following events are supported via the Shopify webhook:
  * Checkout Created
  * Checkout Updated
  * Checkout Deleted 
  * Customer Created
  * Customer Updated
  * Draft Order Created
  * Draft Order Updated
  * Fulfillment Created 
  * Fulfillment Updated
  * Order Cancelled 
  * Order Created
  * Order Fulfilled
  * Charged
  * Order Partially Fulfilled
  * Order Updated


[block:callout]
{
  "type": "info",
  "body": "The Checkout Created, Checkout Updated, Checkout Deleted and Charged events are available automatically via webhooks for all Shopify plugin installs/reinstalls after 27th September 2021. There is no need to subscribe to these events manually.",
  "title": "Checkout and Order events"
}
[/block]
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
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f955291-shopify_segment_identify.png",
        "shopify_segment_identify.png",
        1005,
        813,
        "#fafafb"
      ]
    }
  ]
}
[/block]