---
title: Precomputed Segments
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
Precomputed segments are past behavior segments that are computed every three hours which  provide the capability to optimize your mobile push campaigns for speed of delivery. Using precomputed segments, you can send campaigns with minimal lag so that you can reach out to your users immediately.

#Create Precomputed Segments
Any past behavior segment can be made a precomputed segment. To make a Past Behavior Segment precomputed, go to the segment details page of the said segment and mark it as 'Precomputed'

To create a precomputed segment, perform the following steps:
1. From the dashboard, navigate to *Segments* > *Segments*.
2. Select a past behavior segment.
3. Click **Mark Precomputed**.


  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a09711-Screenshot_2019-01-04_at_5.20.06_PM.png",
        "Screenshot 2019-01-04 at 5.20.06 PM.png",
        1233,
        734,
        "#f3f5f8"
      ],
      "border": true
    }
  ]
}
[/block]
#Segment Limits
Some segment limits include:
  * As an enterprise customer, you are allowed to create up to 20 precomputed segments.
  * You can unmark a precomputed segment from the segment details page itself.
  * Once you unmark a precomputed segment, all campaigns running now and in the future will run at a regular pace.
[block:callout]
{
  "type": "warning",
  "title": "SMS and Email Campaigns",
  "body": "While CleverTap ensures fast delivery of all campaign channels that uses precomputed segments for SMS and email campaigns, the speed of delivery is dependent on your gateway provider."
}
[/block]
#How Precomputed Segments Work
Here are some details as to how the precomputed segments work:
  * Precomputed segments are past behavior segments that are calculated every three hours starting at 12:00 AM (local time).
  * When a campaign is created on the precomputed segment, the time it takes to compute the list of users who are qualified to be a part of a campaign is reduced to nearly zero.
  * Since this list of users is already available immediately on campaign creation, the campaign is delivered at a faster rate.
[block:callout]
{
  "type": "info",
  "body": "Using precomputed segments will not include people who have qualified for the segment in the last three hours (i.e., since the time the segment was last precomputed).",
  "title": "Who Is Not Included"
}
[/block]
#When to Use Precomputed Segments
When sending campaigns that require you to have a competitive advantage for fast delivery, we recommend using precomputed segments.

##Use Cases
There could be situations where you want to reach out to users immediately without waiting for a new segment to be computed before you send a campaign.

Some use cases include:
  * Breaking news: As soon as important news breaks and you want to send a push notification to your user base, we recommend that you use precomputed segments. 
  * Score updates: As soon as an important event occurs in a match and you want to reach your customers with a push notification. you may use precomputed segments.

No matter your use case, once you have defined a segment, the system will continue to automatically compute this segment every three hours. This lets you send out notifications without any delays to stay in touch with your users.
[block:callout]
{
  "type": "info",
  "title": "Delivery Speed",
  "body": "After marking a segment as precomputed, the delivery speed increases over time. You will see the fastest delivery rates after three hours of marking the segment as precomputed."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Using Precomputed Segments in Journeys",
  "body": "Since journeys is an orchestration platform, precomputed segments are not applicable when creating journeys."
}
[/block]
#FAQs
###Why am I not able to see the *Mark Precomputed* option on my segment?
Precomputed segments are only available with past behavior segments. You might have chosen a different segment type.

###How often does the system refresh data on precomputed segments?
The system computes precomputed segments every three hours.

###Why am I not able to create goals for my segment?
Maximize or minimize goals can only be created for past behavior segments. You might have chosen a different segment type.

###I am not able to add new goals despite using past behavior segments. What is the issue?
You can track five active goals at a time. In case you want to track more than five goals at a time, please contact your CleverTap sales rep or email us at sales@clevertap.com.

###What is the maximum file size for a custom list upload? What can I do if I have a very large file size?
The file size limit for a custom list upload is 50 MB. You can use our API upload option to upload a custom list file of up to 5 GB.