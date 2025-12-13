---
title: API Campaigns
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
## Overview

Customers can create API campaigns from the dashboard by using the 'API Campaign' under campaign type
This allows you to create API based campaigns using a campaign id as the input to the API

Once the campaign is created, you can view the stats of the campaign via the dashboard


## Creating an API campaign
**Step 1: **Select the channel you want to create the campaign for. You can create message API campaigns for all channels except Facebook and Google remarketing channels
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/755590b-Screenshot_2019-03-22_at_3.00.16_PM.png",
        "Screenshot 2019-03-22 at 3.00.16 PM.png",
        1103,
        635,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 2: ** Select the 'API Campaign' type from the 'campaign type

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6b8983a-Screenshot_2019-03-22_at_3.01.44_PM.png",
        "Screenshot 2019-03-22 at 3.01.44 PM.png",
        892,
        585,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 3: ** Give a name to the campaign
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70e8daa-Screenshot_2019-03-22_at_4.27.16_PM.png",
        "Screenshot 2019-03-22 at 4.27.16 PM.png",
        524,
        205,
        "#e4e6ee"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 4: ** You will get the campaign id. Copy this campaign id for using in the API
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b66728f-Screenshot_2019-03-22_at_4.27.56_PM.png",
        "Screenshot 2019-03-22 at 4.27.56 PM.png",
        520,
        214,
        "#e8ebef"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 5: **  Use the campaign id in the Message Identity API. Check our [dev docs here](https://developer.clevertap.com/docs/create-campaign-api#section-create-campaign-api-target-users-by-their-identities) for more details
[block:code]
{
  "codes": [
    {
      "code": "{\n    \"to\": {\n        \"Identity\": [],\n        \"objectId\": [\n            \"-fb4e33e76476409c9541bb102e655bee\"\n        ]\n    },\n    \"respect_frequency_caps\": false,\n    \"campaign_id\": 1000000043, //this is where you add the campaign id\n    \"content\": {\n        \"title\": \"Test\",\n        \"body\": \"Test\",\n        \"platform_specific\": {\n            \"ios\": {\n                \"deep_link\": \"\",\n                \"sound_file\": \"\",\n                \"category\": \"\",\n                \"badge_count\": 0,\n                \"key\": \"\",\n                \"mediaType\": \"image\",\n                \"mediaUrl\": \"https://image.com/image.jpg\"\n            },\n            \"android\": {\n                \"background_image\": \"https://image.com/image.jpg\",\n                \"default_sound\": false,\n                \"deep_link\": \"\",\n                \"large_icon\": \"\",\n                \"key\": \"\",\n                \"wzrk_cid\": \"\"\n            }\n        }\n    }\n}",
      "language": "text",
      "name": "Message Identity API"
    }
  ]
}
[/block]
**Step 6: **  Once the campaign is sent, check the stats by searching for the campaign id
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0dc36e2-Screenshot_2019-03-22_at_4.50.26_PM.png",
        "Screenshot 2019-03-22 at 4.50.26 PM.png",
        1358,
        335,
        "#f3f6f7"
      ],
      "border": true
    }
  ]
}
[/block]