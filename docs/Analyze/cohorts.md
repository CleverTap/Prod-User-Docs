---
title: Cohorts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

Cohort analysis is a way of grouping users who are similar (based on who or what they have done), and tracking their behavior over time. 

Cohorts let you isolate a group of users who have performed a certain event, and determine how long it takes for them to come back and perform a second event.

Cohorts are a powerful way to understand how people are using your applications and are commonly used to measure user retention and churn. You can use cohort analysis to answer questions like:

* What is my 4th week retention like for new users?
* How many repeat buyers does my ecommerce application have?
* How soon do new users uninstall my music application if they aren’t creating playlists?

You can also use cohorts for more nuanced use-cases that involve different segments. One such use-case of cohorts is to validate hypotheses. For example, if you are a video application, you would have a Hypothesis in mind “People return to watch videos in my applications because of the recommendations section of my application”. 

You can easily use cohorts to validate this hypothesis.

Your “First event” & “Return event” would both be “video watched”. As this would help answer - How many people who watched videos, came back to watch videos on my application. 

You will view this cohort 2 segments of users. In the advanced filter you will first view your Video watched → Video watched cohort for people who have used the recommendations feature, then you will compare it to people who haven’t used the recommendations feature.

# Creating a Cohort

To create a cohort, select your desired first event & its properties, this is the event that people must perform to qualify for your analysis. Select your return event and its properties, which is the event that people who have performed your first event, must return to perform. 

<Image title="image1.png" alt={903} className="border" border={true} src="https://files.readme.io/41d91ad-image1.png" />

<Image title="image3.png" alt={905} className="border" border={true} src="https://files.readme.io/5c737fb-image3.png" />

**Comparing Cohorts By**\
While creating your cohort, you choose to compare your analysis by: 

* Geography - user's last known country, region, and city.
* Session details - UTM source/medium/campaign & session source/referrer for the “First event”.
* Technographics - browser/device/os.

## Advanced Filtering

Advanced filters allow you to restrict your analysis to a specific segment of users. Create a segment based on any combination of past behaviors in combination with any set of user properties. 

> 👍 Advanced filters is a general feature available for all analytics features and most campaigns. Read more in the [Segmentation guide](doc:segments).

# Reading Cohort Results

The cohort result first gives you an overview of your result in the form of a trend graph. This graph plots the total % of users who came back to perform your return event, after performing your desired first event.

<Image title="image2.png" alt={1213} className="border" border={true} src="https://files.readme.io/dcfa132-image2.png" />

The Y-axis shows the % of users that came back to perform your return event & the X-axis shows you the time frame in which the return event was performed. 

You can also see the details of the trend view in a tabular form in this analysis. The tabular view helps you track the performance of each cohort, and also easily compare it to other cohorts. 

For example, in the image below, you can see that in the cohort of Aug 20, a total of 44,431 users launched the application in week 0 (the week of Aug 20). In Week 1, 12.2%  of these users returned to perform the “Charged” event.

<Image title="image5.png" alt={1214} className="border" border={true} src="https://files.readme.io/a12b589-image5.png" />

**Comparing Cohorts**\
In the default view, you see a trend for “all cohorts”, this is the average progression of all users across cohorts, over time. You can choose to compare the performance of one or more cohorts with each other.

<Image title="image4.png" alt={1211} className="border" border={true} src="https://files.readme.io/0fca254-image4.png" />

# Bookmarks

You can bookmark any funnel, cohort or event query and save it to quickly retrieve later. Bookmarks are specific to each logged in user. No other dashboard users will see the bookmarks you save. 

Bookmarks are convenient for recalling a specific analysis that you want to see frequently. For example, you can bookmark you important conversion funnels and view them each day or week to see how they are changing over time.
