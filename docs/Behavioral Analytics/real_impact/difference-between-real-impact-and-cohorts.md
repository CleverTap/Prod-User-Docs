---
title: Difference Between Real Impact and Cohorts
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
@DOCS NOTES: REAL IMPACT SECTION CAME DIRECTLY FROM THE EXISTING USER DOC https://docs.clevertap.com/docs/real_impact#section-overview 


[block:api-header]
{
  "title": "Overview"
}
[/block]
This section covers the difference between real impact and cohorts.

#Real Impact
Real impact provides the capability to:
  * Visualize the boost in performance in your target segments as compared to users who have not received any campaigns.
  * Estimate what percentage of users have churned in the target group by contrasting it with control groups.
  * Calculate the segment-wise impact of essential business metrics and know which segments have been performing better compared to others.

#Cohorts
When you create cohorts, it shows you the total percentage of users who came back to perform your return event after performing your desired first event. Cohort analysis is a subset of behavioral analytics that takes the data from a given eCommerce platform, web application, or online game, and rather than looking at all users as one unit, it breaks them into related groups for analysis. 

These related groups or cohorts usually share common characteristics or experiences within a defined time span. 

Cohort analysis is a tool to measure user engagement over time. It helps to know whether user engagement is actually getting better over time or is only appearing to improve because of growth.

#Example
The following example explains how the calculations for cohorts and retention inside real impact are done and why are they different.

if you select January 1 to January 31 in retention in real impact, it checks whether the user has done an app launch and returned to do another app launch within the same period in January. It also checks for a second occurrence.

However, if you run a cohort from January 1 to March 31 with a monthly frequency, you will see 100% for month 0 (January) because in cohorts, we consider a conversion even if an app launched is done once. It does not check for a second occurrence if both the events are same. 

Month 1 (February) will calculate the first events done in January and the second events done in February. In the end, the results will differ for real impact and cohorts.