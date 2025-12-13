---
title: Create Campaigns using Recommendations_New UI_ Filter by Catalog
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
Once the recommendations have been published, you can use them in your engagement workflow by creating personalized and contextual recommendations for your user base.

#Access Recommendations Within a Campaign
During the campaign creating in the *What* section, access recommendations with the following steps:

1. Type the @ symbol to personalize your message. 
2. Click **+ Create** under *Recommendation Content*.
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
#Create Recommendation Content
 To create recommendation content, perform the following steps:

1. Select a recommendation from a list of recommendations that have already been published and the event that you want to trigger the recommendation. For example, watching *Game of Thrones* is an event. 
[block:callout]
{
  "type": "info",
  "title": "Event Selection",
  "body": "You can only select events that are mapped to the catalog on which the chosen recommendation is running. <<@dk need to make this clearer>>> ,<<BACK LINK TO CREATING RECOMMENDATIONS>>"
}
[/block]
2. (Optional) Filter recommendations by event, by catalog, or by location: 

a. Filter by event

  * Click **+ Filter by event**. 
  * Select whether you want to include or exclude an event and categories.The event can be watched *The Vampire Diaries*. Add more vampire shows to show relevant recommendations.
  * Add more events if required. 
[block:callout]
{
  "type": "info",
  "title": "How the Filter by Event Works",
  "body": "The filter by event takes precedence over recommended items and selected events matching. It provides the capability to include and exclude all recommended items when an item in the product catalog column matches a defined event property.\n\n<<GIVE AN EXAMPLE AND DONT SAY IT TAKES PRECEDENCE, IT FILTERS OUT RESULTANT RECOMMENDED ITEMS FOR THE USER>>"
}
[/block]
b. Filter by Catalog 
 * Click **+ Filter by Catalog**.
  * Select a  catalog column. The catalog column maybe all the shows have an approval rating of greater than 4. 
  * Add more catalog columns, if required. For example, exclude all shows with the column value *teen vampires*. 
[block:callout]
{
  "type": "info",
  "title": "How the Filter by Catalog Works",
  "body": "You can choose to filter out recommended items, based on Catalog Column values. \nFor example, exclude items that have a rating lesser than 4."
}
[/block]
c. Filter by Location
  
* Click **+ Filter by Location**. 
  * Select a product location catalog and a radius. The location can be the state of Hawaii. You know that the people in Hawaii prefer vampire shows.
  * Add more locations, if required.
[block:callout]
{
  "type": "info",
  "title": "How the Filter by Location Works",
  "body": "The filter by location takes precedence over the location of the recommended items which are fetched from the location catalog. Items in a defined range are looked up with the associated product location catalog and matched with the user's last known location to be included in the filter."
}
[/block]
The resulting recommendations will be all the vampire shows that are pure blood-sucking vampires with no romance. 

3. Decide the sequence of items to be served up to the user out of the list of items that can be recommended (For example, serve up the first item from the list of recommended items).
4. Click **Apply**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b4e62b-recommendations_filter_by_property.png",
        "recommendations_filter_by_property.png",
        858,
        758,
        "#f8f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
#Choose the Fields to Personalize your Message
Now that you have created a recommendation, use the following steps to finalize your content:

1. Choose the particular fields from the catalog that you want to use in your personalized message.
2. Enter your content in the title and message.

When the campaign is sent out, the fields will be replaced and the message will contain the personalized fields for each product. 
[block:callout]
{
  "type": "success",
  "body": "You can send out a recommended video to the user with the video name and thumbnail image based on the last videos a user has watched.",
  "title": "Video Example"
}
[/block]

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
3. Send a test campaign to yourself to see the look and feel of the campaign. The test message will show the first item in the recommendation list.
4. Once you are done testing, publish the campaign.
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
  "title": "Email Campaigns with Recommendations"
}
[/block]
You can create email campaigns with recommended content by invoking recommendations within the email messages. Beyond this part, all the steps are the same as the generic ones described in the sections above. 

You can create emails using:
* New email with rich media
* Templates
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dbc2a30-Email_templates.png",
        "Email templates.png",
        1597,
        808,
        "#eaebed"
      ],
      "border": true
    }
  ]
}
[/block]
## Recommendations using a New Email with Rich Media

You can create personalized recommendations using a new email with media with the steps below.

### Link with Recommendations

You can add recommendations within links with the following steps:

1. Click on the link icon to add a link to your email message.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b7f404-Link_icon.png",
        "Link icon.png",
        1591,
        340,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
2. Type the @ symbol to personalize the link using recommendations in the display text and the URL fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4eb166-Link_pop-up.png",
        "Link pop-up.png",
        690,
        474,
        "#e1e1e2"
      ],
      "border": true
    }
  ]
}
[/block]
### Image with Recommendations

You can also add recommendations within images with the following steps:

1. Click on the image icon to add an image to your email message.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/59ca530-Link_icon.png",
        "Link icon.png",
        1591,
        340,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
2. Type the @ symbol to personalize the link using recommendations in the URL and the alternative text fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/441a81b-Image_pop-up.png",
        "Image pop-up.png",
        648,
        633,
        "#f6f6f8"
      ],
      "border": true
    }
  ]
}
[/block]
The remainder of the steps is the same as any other campaigns as explained in the sections above.

## Recommendations in Template Emails

You can create personalized recommendations using template emails with the steps below.

### Links, Images, Deeplinks, and Custom HTML with Recommendations

You can add recommendations within links, images, deeplinks, and custom HTML with the following steps:

1. Drag and drop the *Dynamic Content* block into the content box in the center of the email body.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b7ced3f-Dynamic_Content_button.png",
        "Dynamic Content button.png",
        1610,
        757,
        "#f5f7fc"
      ],
      "border": true
    }
  ]
}
[/block]
2. Click on the new content box to display the menu on the right.
3. Click on the **Add options** button to access the dynamic content options. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8927951-Dynamic_Content_-_Add_options.png",
        "Dynamic Content - Add options.png",
        1611,
        613,
        "#f5f7fa"
      ],
      "border": true
    }
  ]
}
[/block]
4. When the window pop-up displays, select one of the following options:
  * Image
  * Deeplink
  * Text
  * Custom HTML
[block:callout]
{
  "type": "info",
  "title": "Option Name Required",
  "body": "When you create a dynamic block, the option name is mandatory. Also, these dynamic blocks can be re-used if required."
}
[/block]
#### Image with Recommendations

Type the @ symbol to personalize the image content using recommendations in the URL, alternative text, and target URL fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/356b302-Image_content_recommendation.png",
        "Image content recommendation.png",
        643,
        491,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
#### Deeplink with Recommendations
Type the @ symbol to personalize the deeplink content using recommendations in the display text and URL fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/95a2a74-Deeplink_content_recommendation.png",
        "Deeplink content recommendation.png",
        644,
        490,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
#### Text with Recommendations
Type the @ symbol to personalize the text content using recommendations in the text field.
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
Type the @ symbol to personalize the custom HTML content using recommendations in the custom HTML code box.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/12adce3-Custom_HTML_content_recommendation.png",
        "Custom HTML content recommendation.png",
        638,
        427,
        "#f7f8fa"
      ]
    }
  ]
}
[/block]
### Existing Text Content Type in the Template Containing Deeplinks with Recommendations

You can access recommendations within the existing text content type with the following steps:

1. Drag and drop the *Text* block into the content box in the center of the email body.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e16e2d8-Dynamic_Content_button.png",
        "Dynamic Content button.png",
        1610,
        757,
        "#f5f7fc"
      ],
      "border": true
    }
  ]
}
[/block]
2. Click on the content box to display the menu.
3. Click **More** > **Personalized Deeplink**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/307d55f-Personalized_deeplink.png",
        "Personalized deeplink.png",
        1607,
        441,
        "#e9ecee"
      ],
      "border": true
    }
  ]
}
[/block]
3. Type the @ symbol to personalize the deelink content using recommendations in the display text and URL fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8551529-Deeplink_popup_content_recommendation.png",
        "Deeplink popup content recommendation.png",
        644,
        316,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]