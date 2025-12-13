---
title: Include/Exclude Segments
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

You can simplify complex queries by including or excluding the existing user segments. Create segments with complex conditions once and then reuse them in different scenarios. 

You can create powerful segmentation that is valid for a variety of scenarios. 

![715](https://files.readme.io/30d054b-0fd3c96-Find_people_include_exclude_segments.png "0fd3c96-Find_people_include_exclude_segments.png")

# Include Segments

There may be instances when you want to include some users based on specific criteria. 

For example, if you run a ride-hailing app, you want to nudge your users to enroll for a monthly pass as soon as they open the app. The parameters for these users can be the following:

* The users must be power users, and
* The users have booked more than five rides in a month, and
* They belong to select cities in the country

Now, you can create a segment with these criteria called *Power Users* and can use it again later rather than creating a complex query each time. 

The following is a campaign query for a ride-hailing app that includes the *Power Users* segment.

@PM: NEED HELP WITH THE NEW UI SCREENSHOT

<Image title="include_segments_campaign.png" alt={1067} className="border" width="100%" border={true} src="https://files.readme.io/f9f341a-include_segments_campaign.png" />

@DOCS: THE HYPERLINK BELOW MAY NEED TO BE CHANGED LATER SINCE THE NEW SEGMENT DOC WILL BE [https://docs.clevertap.com/docs/segments\_20](https://docs.clevertap.com/docs/segments_20)

> 📘 Considerations
>
> Some things to consider:  
>
> * You can include and exclude segments in the same query. It is considered as an *AND* condition between the two segments.
> * The include and exclude segments are currently unavailable for bulletins and A/B testing.
> * The segments available for including or excluding users can only be for the [past behavior behavior segment](https://docs.clevertap.com/docs/segments#section-past-behavior-segments) type.

# Exclude Segments

There may be instances when you want to exclude some users based on specific criteria. 

For example, you want to offer discounts to all the users who have expressed interest by adding the product to the cart in the past 30 days; however, you want to save your engagement dollars by excluding the power users. 

The parameters for these power users can be the following:

* Users who have charged three times in the past three months, and 
* Users who have launched the app 15 times in the past month, and
* Users who rated a product 10 times in the past year

Now, you can create a segment with these criteria called *Power Users* and use it again later rather than creating a complex query each time. You can save all these parameters in a segment called *Power Users* and exclude them from the discount message. 

The following is a campaign query for an e-commerce app that excludes the *Power Users* segment.

@PM: NEED HELP WITH THE NEW UI SCREENSHOT

<Image title="exclude_segments_campaign.png" alt={1050} className="border" width="100%" border={true} src="https://files.readme.io/2fb7f6a-exclude_segments_campaign.png" />

# FAQs

### Q. Why can I not find my segment in the include/exclude list while setting up a query?

This may happen because you have saved more than 1,000 segments. All new segments that are created after crossing 1,000 saved segments will not show up in this include/exclude segment filter.

### Q. I have less than 1,000 saved segments but I still do not see my segment in the include/exclude filter. Why is that?

There could be another reason that you are trying to look for a live action segment in the include/exclude segment filter. Note that this functionality works only for past behavior segments.

### Q. My colleague have bookmarked some segments on the *Find People* view, so that I can use them to run queries and create segments in the future. But I am not able to find those bookmarks. What can I do?

Bookmarked segments are saved at a user level and not at an organization level. So, these will ony show up on that person’s profile who actually created and saved those segment queries. You will have to create those segment queries and bookmark them for your own future use.

### Q. I am trying to create a segment of all users who did a particular event (for example, charged) less than or equal to three times in the last 30 days. I also want all those users who have not transacted to be included as part of this segment. How can I do that?

When you choose the event under users who did (charged) and set a filter by a count of less than or equals to three, you will have to select the checkbox underneath that will include people who did not do this event in the selected timeframe.

@PM: FOR THE QUESTION ABOVE, I THINK IT'D BE BENEFICIAL TO SHOW THE SCREENSHOT WITH THE CHECKBOX. IF YOU AGREE, CAN YOU PLEASE PROVIDE? IF NOT, FEEL FREE TO COMMENT. THANKS.
