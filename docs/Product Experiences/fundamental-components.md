---
title: Fundamental Components
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
DOCS NOTE: BEFORE PUBLISHING, UNPUBLISH THE EXISTING PAGE: https://docs.clevertap.com/docs/product-experiences-setup
[block:api-header]
{
  "title": "Overview"
}
[/block]
The fundamental components to enable product experiences include keys, segments, and goals for your app. 

#Create Keys
These are the keys that you have defined in your app code. You can map these keys from the CleverTap dashboard and control the configuration of your app. Keys can be used for product config, feature flags, and A/B tests.

To create keys, perform the following steps::

1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Keys*.
2. Click **+ Key** to create a new key. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6445539-Plus_Key.png",
        "Plus Key.png",
        1405,
        664,
        "#f8f8fa"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The defined key name must match the defined key name in the app. This name cannot be changed later. You can add up to 500 keys.",
  "title": "Key Name"
}
[/block]
3. Add the key description. 

Using the following sample values, you can now activate or deactivate the dark mode based on the keys. The default value that the app is expecting for this key is ``3``.  These values are set in your app. In this example, we assume that the key-value ``3`` means to activate the feature and ``4`` means to deactivate the feature. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0eef333-Key_details.png",
        "Key details.png",
        1090,
        644,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]
4. Click **Save**. The ``dark_mode`` key is now listed on the *Manage Keys* page. 

## Edit or Archive Keys

To edit and archive keys, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Keys*.
2. Click the ellipsis menu to edit or archive a key. After saving a key, you can only edit the default value and description.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18b0577-Edit_or_archive.png",
        "Edit or archive.png",
        1400,
        657,
        "#f8f8fa"
      ]
    }
  ]
}
[/block]
You can view all the archived keys by selecting the *Show archived Keys* box at the bottom of the keys' list. If a key is used in a product config or feature flag, then it cannot be archived. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/25d9045-Show_archived_keys.png",
        "Show archived keys.png",
        1402,
        380,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]
#Create Segments

The segments are the target users who will receive app changes. These segments can be used for product config, feature flags, and A/B tests.

To create a segment, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Segments*.
2. Click **+ Segment** to create a new segment.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09372d9-Plus_segment.png",
        "Plus segment.png",
        1398,
        484,
        "#f7f8fa"
      ]
    }
  ]
}
[/block]
3. Name the segment.
4. Create a segment by users who performed and/or did not perform an event. You can also create segments for user properties such as demographics, geography, and so on. 
5. Click **Save**.

The following example shows a segment of iPhone users living in New York City. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ec855d-Segment_details.png",
        "Segment details.png",
        1475,
        812,
        "#f2eee6"
      ],
      "sizing": "full"
    }
  ]
}
[/block]
##Edit or Clone Segments

To edit and clone a segment, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Segments*.
2. Click the ellipsis menu to edit or clone a segment. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa65d0f-Edit_or_clone_a_segment.png",
        "Edit or clone a segment.png",
        1394,
        478,
        "#f7f8fa"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "success",
  "body": "As an example, you may want to edit the city and create another user segment for Miami.",
  "title": "City Example"
}
[/block]
#Create Goals

Goals are used to evaluate the performance of an A/B test. It is an event and when a user performs this event, it is considered as a conversion. 

To create a goal, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Goals*.
2. Click **+ Goal** to create a new goal.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bfa62dd-Plus_goal.png",
        "Plus goal.png",
        1393,
        374,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]
3. Name the goal.
4. Select the events you want to track.
5. Click **Save Goal**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/28e4de1-Create_a_new_goal.png",
        "Create a new goal.png",
        1400,
        547,
        "#fafbfc"
      ]
    }
  ]
}
[/block]
##Archive Goals 

To archive a goal, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Goals*.
2. Click the archive icon. A new window displays confirming your action.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a913b0-Archive.png",
        "Archive.png",
        1404,
        376,
        "#f8f8fa"
      ]
    }
  ]
}
[/block]
3. Click **Archive**.

You can view all the archived goals by selecting the *Show archived goals* box at the bottom of the goals' list. If a goal is used in a product experience, then it cannot be archived.


#Mutually Exclusive A/B Tests

This is a global setting that is only applicable to A/B tests. You can choose to exclude your segment from all other experiments. It applies only to the new experiments that are created after this setting is enabled. For example, if it is set as disabled at a global level, you will have to enable it on each subsequent test. The users who qualify for this A/B test are unique and they are not shared across any other experiment. 

To enable this feature, perform the following steps:
1. From the dashboard, navigate to *Product Experiences* >  *Setup* > *Settings*.
2. Turn on the *Mutually exclusive A/B tests* toggle. These users will only be included in one A/B test at a time. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/463bdd2-AB_Settings_mutually_exclusive_users.png",
        "AB_Settings_mutually_exclusive_users.png",
        870,
        255,
        "#fafafb"
      ]
    }
  ]
}
[/block]

#Video Tutorial
For further information, you can watch the following video on product configs and feature flags:
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FtfHhsvWvPxk%3Flist%3DPLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DtfHhsvWvPxk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FtfHhsvWvPxk%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=tfHhsvWvPxk&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=6",
  "title": "Product Demo: Product Configs & Feature Flags",
  "favicon": "https://www.youtube.com/s/desktop/404f9720/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/tfHhsvWvPxk/hqdefault.jpg"
}
[/block]