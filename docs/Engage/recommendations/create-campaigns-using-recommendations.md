---
title: Create Campaigns using Recommendations
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
Once the recommendations have been published, you can use them in your engagement workflow

The real power of the feature is to be able to create highly personalized and contextual recommendations for your user base.

#Step 1 Access recommendations within a campaign
As you create the content (or the 'what') within the campaign, you can type in '@' to personalize your message. 
Here, along with the profile/event personalization, you will see "+ Create" within the section "Recommendation content"
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c66c66-Create.png",
        "+Create.png",
        667,
        549,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
#Step 2 Create recommendation content
* Here, you can pick from the recommendations which have already been published
* Next, choose the event that you wish to trigger the recommendation. 
* The most recent (latest) event property will be used to trigger the recommendation. E.g. Recommend an item to the user based on the item that the user last charged. 
* Here, you will be able to select only those events you mapped to the catalog on which the chosen recommendation is running.
* You can decide the sequence of item to be served up to the user out of the list of items that can be recommended. E.g. Serve up the 1st item from the list of recommended items.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc02164-Recco_content.png",
        "Recco content.png",
        660,
        331,
        "#f7f8fa"
      ],
      "border": false
    }
  ]
}
[/block]
#Step 3 Choose the fields to personalize your message
* Once you've created a recommendation, you can choose the particular fields from the catalog that you wish to use in your personalized message.
* When the campaign is sent out, the fields will be replaced and the message will contain the personalized fields for each product. 
* E.g. You can send out a recommended video to the user with the video name and thumbnail image based on the last videos s/he watched.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a93d41a-Reco_catalog_field_name.png",
        "Reco catalog field name.png",
        475,
        460,
        "#f6f6f7"
      ],
      "border": true
    }
  ]
}
[/block]
You can 'send a test' campaign to yourself to see the look and feel of the campaign. The test message will show the first item in the recommendation list

You can now publish the campaign
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d118f5-Screenshot_2019-03-01_at_5.28.45_PM.png",
        "Screenshot 2019-03-01 at 5.28.45 PM.png",
        328,
        628,
        "#bac1ce"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Email campaigns with recommendations"
}
[/block]
You can create email campaigns with recommended content. The steps to invoke recommendations within the email messages are explained below. Beyond these, all the steps are the same as the generic ones described in the sections above. 

You can create emails using:

* Custom HTML
* Templates
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d20eaea-Recommendation_Email_1.png",
        "Recommendation_Email_1.png",
        1437,
        789,
        "#b4b4b9"
      ],
      "border": true
    }
  ]
}
[/block]
## Recommendations in custom HTML emails

You can create personalized recommendations within custom HTML emails in the following manner:

### Link with recommendations

You can add recommendations within links in the following way:

Step 1: Add a link to your email message
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e2c4b1d-Recommendation_Email_2.png",
        "Recommendation Email_2.png",
        1367,
        353,
        "#f2f3f6"
      ],
      "border": true
    }
  ]
}
[/block]
Step 2: Personalize the links using recommendations

You can access the recommendations within the 'Display text' and 'URL' fields.You can personalize communication to your users using these fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d977220-Recommendation_Email_3_copy.png",
        "Recommendation Email_3_copy.png",
        671,
        416,
        "#fafafc"
      ],
      "border": true
    }
  ]
}
[/block]
### Image with recommendations

Step 1: Add an image to your email message
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d39974-Recommendation_Email_4.png",
        "Recommendation Email_4.png",
        1358,
        334,
        "#f2f2f5"
      ],
      "border": true
    }
  ]
}
[/block]
Step 2: Personalize the image using recommendations

You can access the recommendations within the 'URL', 'Alternative Text' and 'Target URL' fields. You can personalize communication to your users using these fields. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4b797ac-Recommendation_Email_5_copy.png",
        "Recommendation Email_5 copy.png",
        678,
        580,
        "#eceef1"
      ],
      "border": true
    }
  ]
}
[/block]
The steps further are the same as any other campaigns, as explained in the sections above

## Recommendations in template emails

You can create personalized recommendations using template emails in the following manner:

### Links, images, deeplinks and custom HTML with recommendations

Step 1: Create a 'dynamic content' block.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aaeda02-Recommendation_Email_6_copy.png",
        "Recommendation Email_6 copy.png",
        1361,
        698,
        "#f1f4fa"
      ],
      "border": true
    }
  ]
}
[/block]
Step 2: Access the dynamic block

Click on the 'Add Options' button to access the dynamic block. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3dac299-Recommendation_Email_7.png",
        "Recommendation Email_7.png",
        1358,
        571,
        "#f1f1f7"
      ],
      "border": true
    }
  ]
}
[/block]
Once you click on the 'Add Options' button, you'll be presented with options to add one of the following:
* Image
* Deeplink
* Text
* Custom HTML

[block:callout]
{
  "type": "info",
  "title": "Option Name",
  "body": "When you create a dynamic block, the option name is mandatory. And, these dynamic blocks can be re-used if required."
}
[/block]
#### Image with recommendations
You can access the recommendations within the 'URL', 'Alternative Text' and 'Target URL' fields. You can personalize communication to your users using these fields.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d22686a-Recommendation_Email_8.png",
        "Recommendation Email_8.png",
        663,
        610,
        "#f8f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
#### Deeplink with recommendations
You can access the recommendations within the 'Display Text' and 'URL' fields. You can personalize communication to your users using these fields.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eea246f-Recommendation_Email_9.png",
        "Recommendation Email_9.png",
        670,
        522,
        "#f4f5f8"
      ],
      "border": true
    }
  ]
}
[/block]
#### Text with recommendations
You can access the recommendations within the text field.You can personalize communication to your users using these fields.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6089f59-Recommendation_Email_10_copy1.png",
        "Recommendation Email_10 copy1.png",
        671,
        375,
        "#f6f7fb"
      ],
      "border": true
    }
  ]
}
[/block]
#### Custom HTML with recommendations
You can access the recommendations within custom HTML code.You can personalize communication to your users using this field. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0bae152-Recommendation_Email_11_copy.png",
        "Recommendation Email_11 copy.png",
        676,
        413,
        "#f6f7fb"
      ]
    }
  ]
}
[/block]
### Existing text content type in the template containing deeplinks with recommendations

You can access recommendations within the existing text content type using the following steps:

Step 1: Create a text block
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a38c53f-Recommendation_Email_12_copy.png",
        "Recommendation Email_12 copy.png",
        1369,
        696,
        "#f2f4fa"
      ],
      "border": true
    }
  ]
}
[/block]
Step 2: Access the 'Personalized Deeplink' item
Access the 'Personalized Deeplink' button within the ribbon menu of the text block
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/df8383c-Recommendation_Email_13_copy.png",
        "Recommendation Email_13 copy.png",
        1365,
        404,
        "#e3e4e8"
      ],
      "border": true
    }
  ]
}
[/block]
Step 3: Create text containing a deeplink with recommendations
You can access the recommendations within the 'Display Text' and 'URL' fields.You can personalize communication to your users using these fields. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/569c891-Recommendation_Email_14_copy.png",
        "Recommendation Email_14 copy.png",
        671,
        374,
        "#eef0f5"
      ],
      "border": true
    }
  ]
}
[/block]