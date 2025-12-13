---
title: Find People
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
DOCS NOTE: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE IS UNPUBLISHED (OR DELETED): https://docs.clevertap.com/docs/find-people
[block:api-header]
{
  "title": "Overview"
}
[/block]
The *Find People* view provides the capability to segment your users by actions taken, actions not taken, or user profile properties that match a set of criteria you have defined.

#Create a Segment View Using Find People
With the *Find People* view, you can view your users based on:
  * Interest
  * Past behavior
  * Common properties

To create a segment using *Find People*, perform the following steps:
1. From the dashboard, navigate to *Segments* > *Find People*.
2. Select the appropriate interest, event, and/or property.
3. Click **View details**.

[block:callout]
{
  "type": "info",
  "body": "You can also search users by identity such as email, user ID, and CleverTap ID.",
  "title": "Search By Identity"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "You can bookmark queries that you run to find people with different parameters. This section only shows your bookmarks but not those from your colleagues.",
  "title": "Bookmarked Segments"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3a3f44b-Find_People1.png",
        "Find People1.png",
        1200,
        890,
        "#fafbfc"
      ]
    }
  ]
}
[/block]
4. Click **Save segment** or **Save segment as a bookmark** to use it at a later time.

#View a Segment 
The new segment shows detailed engagement statistics, demographic, device, and location information for those users. Inside your user segments, you can drill down into individual user profiles to view their detailed user profile and activity data.

The following explains the various actions you can take by section:
* *Reachability*:
  * To download this set of users, click the download icon under the total user count.
  * To create run targeted push, in-app, email, and web campaigns for these user segments, click **Create campaign**.
* *Sample people*: To drill down into individual user profiles to see their detailed user profile and activity data, click on any user profile.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/94a4712-Save_segment_or_bookmark.png",
        "Save segment or bookmark.png",
        1435,
        805,
        "#f3f5fb"
      ]
    }
  ]
}
[/block]
##Use Cases 
You can use the *Find People* view to create any of the following segments:
* Search all users who added an item to cart but did not complete the purchase transaction (a charged event).
* Find all male users who searched for a product with the keyword, shoe, and added a shoe to cart, but did not complete the purchase transaction.
* If you want to offer discounts to all the users who have expressed interest by adding a product to the cart in the past 30 days; however, you want to save your engagement dollars by excluding power users from this segment.

#Sample Profiles
To view sample profiles, create a segment view, then click any sample user to view the user details. For more information, refer to [Create a Segment View Using Find People](https://docs.clevertap.com/docs/find-people-1#section-create-a-segment-view-using-find-people).

##Profile Details
The profile details are as follows: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1aa23d7-Segments_Find_users_Profiles.png",
        "Segments_Find_users_Profiles.png",
        1251,
        667,
        "#eaebee"
      ],
      "border": true
    }
  ]
}
[/block]
##Activity Details
The activity details are as follows: 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f6139e-Segments_Find_users_Activity.png",
        "Segments_Find_users_Activity.png",
        1254,
        665,
        "#f2f3f5"
      ],
      "border": true
    }
  ]
}
[/block]


#FAQ
###Can I update User Profile properties over the course of business?
Yes, you can sync-up updates to profile properties via an API upload.