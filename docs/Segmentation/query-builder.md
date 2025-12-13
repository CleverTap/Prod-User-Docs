---
title: Query Builder
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
@DOCS: HACKATHON DOC RELATED TO https://wizrocket.atlassian.net/browse/CLEVER-9329.
[block:api-header]
{
  "title": "Overview"
}
[/block]
The query builder is at the core of segmentation in CleverTap. Using this tool marketers can segment their users logically based on their interests or certain events at a particular time.

#Build a Query
To build a query, perform the following steps:
1. From the dashboard, navigate to *Segments* > *Find People*.
2. Select the appropriate interest, event, and/or property below:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d50a5e-Screenshot_2021-07-12_at_8.19.15_PM.png",
        "Screenshot 2021-07-12 at 8.19.15 PM.png",
        1790,
        1364,
        "#fbfbfd"
      ],
      "border": true
    }
  ]
}
[/block]
##Users Who Like
Segment users by their interests (powered by our AI tools).

##Users Who Did
Segment users by the event they performed.

You can choose *All (AND)*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/520889d-Users_who_did_AND.png",
        "Users who did AND.png",
        1010,
        397,
        "#fdfdfd"
      ]
    }
  ]
}
[/block]
You can choose *Any (OR)*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/144c88c-Users_who_did_OR.png",
        "Users who did OR.png",
        990,
        324,
        "#fcfdfd"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "There is an *And/Or* condition in the *Users who did* section but not in the *Did not do* section because *And* and *Or* conditions both mean *And* in the *Did not do* section.",
  "title": "And/Or Conditions"
}
[/block]
##Users Who Did Not Do
Segment users by the event they have not performed yet.

##Display Common Properties
Segment users by selecting common properties across them.

3. Click **View details**.

#Examples
Below are a few scenarios that showcase how one can leverage the query builder to get granular data for effective targeting.

1. Users who performed the charged event in the last 30 days.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/57d1736-Screenshot_2021-07-12_at_4.15.49_PM.png",
        "Screenshot 2021-07-12 at 4.15.49 PM.png",
        1656,
        874,
        "#fcfdfd"
      ],
      "border": true
    }
  ]
}
[/block]
2. Users who were sent an email notification at least five times in the last 30 days.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f7a7d2b-Screenshot_2021-07-12_at_4.29.02_PM.png",
        "Screenshot 2021-07-12 at 4.29.02 PM.png",
        1618,
        884,
        "#fcfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
3. Users who added to cart and charged (both) today.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0939347-Screenshot_2021-07-12_at_4.49.27_PM.png",
        "Screenshot 2021-07-12 at 4.49.27 PM.png",
        1576,
        1196,
        "#fdfdfd"
      ],
      "border": true
    }
  ]
}
[/block]
4. Users who have the most product views in the watches category in the last 30 days.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/074371e-Screenshot_2021-07-12_at_4.49.27_PM.png",
        "Screenshot 2021-07-12 at 4.49.27 PM.png",
        1576,
        1196,
        "#fdfdfd"
      ],
      "border": true
    }
  ]
}
[/block]
5. All gold customers using iOS.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2da40e-Screenshot_2021-07-12_at_5.56.52_PM.png",
        "Screenshot 2021-07-12 at 5.56.52 PM.png",
        1658,
        582,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
6. Users who launched the app for the first time between 9 AM to 12 PM today.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e93ca4-Screenshot_2021-07-12_at_6.02.28_PM.png",
        "Screenshot 2021-07-12 at 6.02.28 PM.png",
        1596,
        934,
        "#fcfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
7. Users who did not add to cart or purchase in the last 30 days.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6eb280-Screenshot_2021-07-12_at_6.19.58_PM.png",
        "Screenshot 2021-07-12 at 6.19.58 PM.png",
        1640,
        900,
        "#fdfdfd"
      ],
      "border": true
    }
  ]
}
[/block]
8. Users who are between the age group of 18-40, and have purchased an item under T-shirts, shoes, or shirts at least once in the last 30 days.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c8c51a8-Screenshot_2021-07-12_at_7.56.40_PM.png",
        "Screenshot 2021-07-12 at 7.56.40 PM.png",
        1748,
        1424,
        "#fdfdfd"
      ],
      "border": true
    }
  ]
}
[/block]