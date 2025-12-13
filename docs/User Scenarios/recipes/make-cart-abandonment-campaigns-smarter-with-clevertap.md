---
title: Create Cart Abandonment Campaigns
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
Using CleverTap you can create highly targeted and powerful cart abandonment campaigns. You can set up a message that the user will receive while they are in the process of abandoning your cart. 
[block:callout]
{
  "type": "success",
  "body": "If someone adds an item to your cart but does not transact within 15 minutes, you can send them a notification in this workflow.",
  "title": "Cart Abandonment Campaign Example"
}
[/block]
# Step 1: Create a Funnel

Navigate to the "Funnels" section of your CleverTap Dashboard and create a funnel for the product/category you are looking to set up a campaign for. Check out this [guide](doc:funnels) to learn how to create a funnel. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0fe8c7b-funnel1.png",
        "funnel1.png",
        690,
        358,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b77a57-funnel2.png",
        "funnel2.png",
        690,
        306,
        "#eaeff6"
      ],
      "border": true
    }
  ]
}
[/block]
# Step 2: Analyze the Funnel 

Based on the example above, 41.6% of my users who added Toys to their cart, bought the toys. Of these users, 80% of them bought the toys within 10 mins

I should set up my abandoned cart trigger in CleverTap for Toys as a category with a delay of at least 10 mins. i.e. If someone adds toys to their cart and doesn't buy it within 10 mins, I should send them a notification since 80% of my users who bought toys did it within 10 minutes.

# Step 3: Create Campaign

Navigate to push campaigns ---> Live user segments ---> inaction within time.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b11b144-funnel3.png",
        "funnel3.png",
        690,
        269,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/663c26d-funnel4.png",
        "funnel4.png",
        465,
        300,
        "#f3f5f6"
      ],
      "border": true
    }
  ]
}
[/block]
You have now set up a scientific way to send cart abandonment messages!