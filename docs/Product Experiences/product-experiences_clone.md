---
title: Product Experiences_Clone
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
With Product Experiences, you can change the behavior and appearance of your app remotely without an update. This helps you to deliver in-app personalization experience to your app users and test their response. You can use Product Config to modify app behavior and Feature Flags to add or remove features from your app without performing an app store deployment.

#Introduction

You can remotely configure your app with Product Experiences. The configuration can be anything, including the look and feel of the app, and the workflow for users.

Feature Flags - You can enable or disable a feature in your app with a simple toggle. 

For example, you want to want to enable dark mode on your app. However, you want the following additional options:
  * You want to test it first on iPhone users who live in New York. 
  * You must also be capable of disabling the feature if it needs more work. 

You can create a Feature Flag for this improvement and test the response to your app.  

Product Config - Assume the App allows users to play baseball on their phones. You want to change the following - 

  * The Fans Jerseys based on location
  * Stadium Background based on location
  * The speed of the ball based on the level of the game
  * The bounce of the ball based on the level of the game

You can send all these changes in a Product Config and make the necessary changes to the app. 

#Set up

To run a Product Config or a Feature Flag, you must create Keys and Segments for your app. 

##Create Keys
These are the keys that you have defined in your app code. You can map these keys from the CleverTap dashboard and control the configuration of your app. 

###To create Keys:

1. Go to Product Experiences >  Setup > Keys
2. Click +Key to create a new key. 
[block:callout]
{
  "type": "info",
  "body": "The name of the key defined here must match the name of the key defined in the app. This name cannot be changed later. You can add up to 500 keys.",
  "title": "Note"
}
[/block]
3. Add the Key definition. 

Let us add some sample values:

####**Sample 1:**
You want to activate or deactivate the dark mode based on the Keys. These values are set in your app. Let us assume that the key value True means activate the feature, False means deactivate the feature. The default value that the app is expecting for this key is ``False``.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc4fb4f-Product_exp_Key_Create.png",
        "Product_exp_Key_Create.png",
        776,
        652,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
####**Sample 2:**
You can enable or change every aspect of the app. This example key can be used in a product config to change the ball speed in a baseball game based on the game level of the player.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e543475-Product_Exp_PC_Key_Create1.png",
        "Product_Exp_PC_Key_Create1.png",
        840,
        860,
        "#c4c5c6"
      ],
      "sizing": "full",
      "caption": "JSON key to change ball speed"
    }
  ]
}
[/block]
This example key can be used in a product config to change the fans Jerseys and the stadium background in a baseball game. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f87e7d7-Product_Exp_PC_Key_Create2.png",
        "Product_Exp_PC_Key_Create2.png",
        845,
        866,
        "#c5c6c7"
      ],
      "sizing": "full",
      "caption": "JSON key to change background"
    }
  ]
}
[/block]
4. Click Save. The key is now listed on the Manage Keys page. 


### Edit/Archive Keys

1. Go to Product Experiences >  Setup > Keys. The Keys page appears. 
2. Click the ellipsis menu to edit or archive a key. Only the default value and description can be edited after saving a key.

You can view all the archived keys by selecting the Archived Keys box at the bottom of the key's list.  If a key is used in a Product Config or Feature Flag then it cannot be archived. 

##Create Segments

The segments are the target users that will receive app changes. 

To define the segments:

1. Go to Product Experiences >  Setup > Segments
2. Click the +Segment button to create a new segment.
3. Name the segment.
4. Create a segment by users who performed and/or did not perform an event.  You can also create segments for user properties such a demographics, geography, and so on. For our example, create a segment of iPhone users living in New York. 
5. Save the segment. 
6. Follow steps 1 to 5 to create another segment for users in Miami.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/483d933-ProductExp_Segment_Create.png",
        "ProductExp_Segment_Create.png",
        1182,
        1256,
        "#f2efe8"
      ],
      "sizing": "full"
    }
  ]
}
[/block]
##Edit/Clone a Segment

1. Go to Product Experiences >  Setup > Segments. The Segments page appears. 
2. Click the ellipsis menu to edit or clone a segment. For example, you may want to edit the city and create another user segment. 

#Feature Flags

You can have canary releases using Feature Flags. You can remotely turn on or turn off features on your app. 

 Let us view the previous example. You want to want to enable dark mode on your app. However, you want the following additional options:
* You must be able to target iPhone users.  
* You want to test it on 20% of New York users and 30 % of Miami users before you roll it out to all users. 
* You must also be capable of disabling the feature if it needs more work. 

Feature Flags can enable or disable a feature with a simple toggle. You can also test the feature on your users before you make it available to everyone. Your users will now have seamless access to the feature and add to a better experience. 

##Create Feature Flags

1. To create a Feature Flag, click Product Experiences > Feature Flags.  The Feature Flags page appears. 
2. Click the +Feature Flag button to create a new Feature Flag. The create a Feature Flag page appears. 
3. Enter the name and description for your Feature Flag. For example, we create a "Dark Mode" Feature Flag.
4. Select the Segments and Keys for your Feature Flag. The Keys are the keys that you have assigned in your app for each feature and the Segments are the group of users that will receive this feature. For example, we select the "iPhone users in New York" and "iPhone users in Miami" segment.  We select the key called "Change Mode" key.  For more information on creating keys, see [Keys](https://docs.clevertap.com/docs/product-config#section-create-keys)
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "A Feature Flag can have only boolean values, that is, true or false. A key can only be used in one Feature Flag."
}
[/block]
5. Under Key value and priority, add the set the Key value for each segment. 
6. Toggle the selected segment and define the percent of users that will receive this change. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1062938-ProductExp_Feature_Flag_Create.png",
        "ProductExp_Feature_Flag_Create.png",
        507,
        1323,
        "#f6f6f9"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
6. Publish your Feature Flag or schedule it to be published at a later date. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88c5406-ProductExp_feature_flag_schedule.png",
        "ProductExp_feature_flag_schedule.png",
        698,
        556,
        "#f5f6fa"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
##Edit/Archive Feature Flags

[block:callout]
{
  "type": "info",
  "body": "Any changes to a Feature Flag are saved in a new version. You can always revert to an earlier version.",
  "title": "Note"
}
[/block]
##View Statistics

The stats will show you the distribution and value of the key stats for your Feature Flag. To view stats for a Feature Flag:

To view Feature Flag Stats:
1. Click Product Experiences > Feature Flags.  The Feature Flag page appears. 
2. Click the Feature Flag from the list and scroll down to view the stats. 

You can view the following information:
1. You can see a trend of the total number of keys delivered for all segments or a particular segment from the first chart.
2. In the second box, you can further break it down to get a count of each type of key value-wise
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be9202d-ProductExp_Feature_Flags_Stats.png",
        "ProductExp_Feature_Flags_Stats.png",
        723,
        675,
        "#fcfcfd"
      ]
    }
  ]
}
[/block]
##Feature Flag Version

A new version is created every time you edit a Feature Flag. If the current feature is not working for some reason, you can always revert to an older version of Feature Flag:

1. Click Product Experiences > Feature Flag.  The Feature Flag page appears. 
2. Click the ellipsis menu to edit a Feature Flag.  The versions appear on the right side.
3. Click the required version number and Publish it. The selected version becomes active and the current version becomes inactive. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/85516bd-ProductExp_feature_flag_versioning.png",
        "ProductExp_feature_flag_versioning.png",
        1169,
        1282,
        "#f7f8f9"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
#Product Config

##Create Product Config
You can have multiple members of your team create Product Config with multiple keys and segments. You can then group these keys. 

1. To create a Product Config, click Product Experiences > Product Config.  The Product Config page appears. 
2. Click the +Product Config button to create a new Product Config. The create a Product Config page appears. 
3. Enter the name and description for your Product Config. For our example, let us name the Product config as "Game Config".
4. Select the Segments and Keys for your Product Config group. The Keys are the keys that you have assigned in your app for each element or feature and the Segments are the group of users that will receive this feature. In our example, we select the "iPhone users in New York"  and "iPhone users in Miami" as Segments and "Game Config" as the Product Config Key. For more information on creating keys, see [Keys](https://docs.clevertap.com/docs/product-config#section-create-keys)
[block:callout]
{
  "type": "info",
  "body": "A key can only be used in one Product Config.",
  "title": "Note"
}
[/block]
5. Add the value and set the priority for your Product Config keys. Drag the <img src="https://files.readme.io/b3f4cdd-Move_icon.png" height="30px" width="30px" > icon up or down to change segment priority. 
6. Publish your Product Config or schedule it to be published at a later date. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f4bc285-ProductExp_Product_Config_Create.png",
        "ProductExp_Product_Config_Create.png",
        780,
        1351,
        "#f5f6f9"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
##Edit/Archive Product Config

1. To edit a Product Config, click Product Experiences > Product Config.  The Product Config page appears. 
2. Click the ellipsis menu to edit or archive a Product Config.  
[block:callout]
{
  "type": "info",
  "body": "Any changes to a Product Config are saved in a new version. You can always revert to an earlier version.",
  "title": "Note"
}
[/block]

## View Statistics

The stats will show you the distribution and value of the key stats for your Product Config. To view stats for a Product Config:

To view Product Config Stats:
1. Click Product Experiences > Product Config.  The Product Config page appears. 
2. Click the Product config from the list and scroll down to view the stats. 

You can view the following information:
1. You can see a trend of the total number of keys delivered for all segments or a particular segment from the first chart.
2. In the second box, you can further break it down to get the count of each type of key value wise.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f5d39be-Product_Exp_Keys_Stats.png",
        "Product_Exp_Keys_Stats.png",
        720,
        834,
        "#fafbfd"
      ],
      "sizing": "full"
    }
  ]
}
[/block]
## Product Config Version

A new version is created every time you edit a Product Config. If the current config is not working for some reason, you can always revert to an older version of Product Config:

1. Click Product Experiences > Product Config.  The Product Config page appears. 
2. Click the ellipsis menu to edit a Product Config.  The versions appear on the right side.
3. Click the required version number and Publish. The selected version becomes active and the current version becomes inactive. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a44674-ProductExp_product_config_versioning.png",
        "ProductExp_product_config_versioning.png",
        1163,
        1307,
        "#f6f7f9"
      ],
      "sizing": "full"
    }
  ]
}
[/block]