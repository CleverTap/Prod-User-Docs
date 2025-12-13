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

Customers can create API campaigns from the dashboard by using the 'API Campaign' under campaign type\
This allows you to create API based campaigns using a campaign id as the input to the API

Once the campaign is created, you can view the stats of the campaign via the dashboard

## Creating an API campaign

**Step 1:** Select the channel you want to create the campaign for. You can create message API campaigns for all channels except Facebook and Google remarketing channels

<Image title="Screenshot 2019-03-22 at 3.00.16 PM.png" alt={1103} className="border" border={true} src="https://files.readme.io/755590b-Screenshot_2019-03-22_at_3.00.16_PM.png" />

**Step 2:** Select the 'API Campaign' type from the 'campaign type

<Image title="Screenshot 2019-03-22 at 3.01.44 PM.png" alt={892} className="border" border={true} src="https://files.readme.io/6b8983a-Screenshot_2019-03-22_at_3.01.44_PM.png" />

**Step 3:** Give a name to the campaign

<Image title="Screenshot 2019-03-22 at 4.27.16 PM.png" alt={524} className="border" border={true} src="https://files.readme.io/70e8daa-Screenshot_2019-03-22_at_4.27.16_PM.png" />

**Step 4:** You will get the campaign id. Copy this campaign id for using in the API

<Image title="Screenshot 2019-03-22 at 4.27.56 PM.png" alt={520} className="border" border={true} src="https://files.readme.io/b66728f-Screenshot_2019-03-22_at_4.27.56_PM.png" />

**Step 5:**  Use the campaign id in the Message Identity API. Check our [dev docs here](https://developer.clevertap.com/docs/create-campaign-api#section-create-campaign-api-target-users-by-their-identities) for more details

```text Message Identity API
{
    "to": {
        "Identity": [],
        "objectId": [
            "-fb4e33e76476409c9541bb102e655bee"
        ]
    },
    "respect_frequency_caps": false,
    "campaign_id": 1000000043, //this is where you add the campaign id
    "content": {
        "title": "Test",
        "body": "Test",
        "platform_specific": {
            "ios": {
                "deep_link": "",
                "sound_file": "",
                "category": "",
                "badge_count": 0,
                "key": "",
                "mediaType": "image",
                "mediaUrl": "https://image.com/image.jpg"
            },
            "android": {
                "background_image": "https://image.com/image.jpg",
                "default_sound": false,
                "deep_link": "",
                "large_icon": "",
                "key": "",
                "wzrk_cid": ""
            }
        }
    }
}
```

**Step 6:**  Once the campaign is sent, check the stats by searching for the campaign id

<Image title="Screenshot 2019-03-22 at 4.50.26 PM.png" alt={1358} className="border" border={true} src="https://files.readme.io/0dc36e2-Screenshot_2019-03-22_at_4.50.26_PM.png" />
