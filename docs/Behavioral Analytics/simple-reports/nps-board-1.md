---
title: NPS Board
excerpt: >-
  Discover how the NPS Board uses AI-powered insights to streamline feedback
  analysis and uncover meaningful trends.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Net Promoter Score (NPS) is a widely used metric for measuring customer loyalty and satisfaction. It is based on a single question that asks customers how likely they are to recommend your product or service to others on a scale of 0 to 10.

By aggregating NPS scores over time, businesses can gauge overall customer sentiment and identify opportunities to improve areas such as product experience, customer support, and service delivery—ultimately strengthening customer loyalty.

CleverTap’s NPS dashboard gives you a clear and comprehensive view of your customers’ NPS feedback. To access it, go to _Dashboard_ > _Boards_ > _NPS_.

# NPS Insights

NPS Insights is an enhancement to CleverTap’s Net Promoter Score (NPS) dashboard. It combines quantitative data (such as NPS scores and response volumes) with qualitative insights (including AI summaries, sentiment analysis, and theme clustering).

In addition to standard NPS metrics, NPS Insights applies AI-powered analysis to free-text responses, helping you quickly interpret customer feedback. This gives marketers and product teams a more complete view of customer satisfaction and the key factors influencing it.

<Callout icon="📘" theme="info">
  ### Private Beta

  Currently, this feature is released in Private Beta. If you want access to this feature, contact your Account Manager.
</Callout>

To view NPS Insights:

1. Go to _Dashboard > Boards > NPS_. Select the **Stats** tab.
2. Apply view filters if required. The following filters are available:
   - **Segment:** Select All users or a specific segment
   - **Period:** Select a custom date range
   - **Campaign:** Select a specific campaign
3. Once selected, the filtered insights view is shown under the _AI Insights_ tab.
4. Click _See detailed insights_ to redirect to the AI insights page.
5. To export data, click the download icon.


<Image src="https://files.readme.io/23620d714ca78b6c891e895e525bf2d97fdeec85c6bf5e01a11654f91dcafe95-nps.png" alt="AI Insights" align="center" border={true} />


## AI Insights

Select the **AI insights** tab to view the detailed analysis of all user reviews. Click _See detailed insights_ to redirect to the AI insights page. Refer to the following _AI Insights_ tabs:

- [AI Generated Summary](https://docs.clevertap.com/docs/nps-board-1#ai-generated-summary)
- [Key Themes](https://docs.clevertap.com/docs/nps-board-1#key-themes)
- [Comments](https://docs.clevertap.com/docs/nps-board-1#comments)
- [Trend](https://docs.clevertap.com/docs/nps-board-1#trend)
- [Smart Word Cloud](https://docs.clevertap.com/docs/nps-board-1#smart-word-cloud)

### AI Generated Summary

You can view the AI Summary for a quick overview of the comments. This summary automatically summarizes large volumes of comments into key takeaways, which helps marketers avoid manually scanning every response.

### Key Themes

CleverTap groups user comments into recurring topics such as _User Experience_, _Billing_, or _Onboarding_. It also provides counts to highlight common pain points or strengths. Under _Key Themes_, you can hover over each theme to get a % breakdown of comments, based on negative and positive sentiment per theme.


<Image src="https://files.readme.io/67e5237aa9584225d53f0f7affc0cad7a246e8e45b020171ef3ecfd5bedea2b3-theme.png" alt="Hover over comments" align="center" border={true} />


You can apply filters to display only comments for a selected key theme by clicking on a theme. This is especially useful for deep dives into user concerns.


<Image src="https://files.readme.io/94b79f14724f68332b85fd7a420a95806bdc3173d099f901cf0b7abf48db6fbe-themes.png" alt="See detailed insights" align="center" border={true} />


### Comments

You can sort the comments based on chronology or ratings, in an ascending or descending order.


<Image src="https://files.readme.io/a195e309cb677ccad5f68822dc0143eaf2f95354a6bbd6e0b5ded713f54ca883-recency_sort.png" alt="Sort comments by recency or ratings" align="center" border={true} />


You can filter the user comments based on their key sentiments: Positive, Negative, or Neutral.


<Image src="https://files.readme.io/ae434aebafdd98ae49523ce5a68a00532dd4a6f3c9a1ab531cc07aadf3cec33e-comment_sort.png" alt="Sort comments by key sentiments" align="center" border={true} />


### Trend

Sentiment trends provide an aggregate view of positive, neutral, and negative sentiment across all comments. Click the dropdown to see a daily, weekly, or monthly trend chart.


<Image src="https://files.readme.io/eb9606c2341e40532205d935f8487451eed6cc935dd16bd6d00669ca49d64423-trend_.png" alt="Trend" align="center" border={true} />


### Smart Word Cloud

Smart Word Cloud helps with the visualization of the most frequently used words in user comments. It helps quickly identify trending topics and provides actionable insights for deeper analysis.


<Image src="https://files.readme.io/e1e15d19daff48f0c73947c13a3ab8e1e25f89c97a0b39f5d022e7255cfcd721-wordcloud.png" alt="Smart Word Cloud" align="center" border={true} />


# NPS Board - Stats

The **NPS board** in CleverTap provides a comprehensive overview of customer feedback collected through Net Promoter Score surveys. It combines key quantitative metrics with trend visualizations to help you measure and track user sentiment over time.

The NPS board in CleverTap displays the following data points:

- **Overall NPS Score:** Calculated using customer responses.
- **Total Responses Received:** Number of users who submitted feedback.
- **NPS Buckets:** Categorized breakdown of Detractors, Passives, and Promoters.
- **NPS Score Trend:** Visual representation of how the score changes over time.
- **NPS Buckets Trend:** Distribution of Detractors, Passives, and Promoters over a selected time period (daily, weekly, or monthly).
- **Ratings Distribution:** Bar chart of user ratings on a scale of 0–10.
- **Total Responses Trend:** Trend line showing submission volumes across time periods.

At a high level, the NPS feedback is categorized into three buckets - Detractors, Passive, and Promoters.

- **Detractors (0–6):** Unhappy customers likely to churn or share negative feedback.
- **Passives (7–8):** Neutral customers who are satisfied but not enthusiastic.
- **Promoters (9–10):** Loyal customers who are highly likely to recommend your product.

The overall _NPS score_  is calculated as the difference between the percentages of Promoters and Detractors (NPS = % of Promoters - % of Detractors). For example, for a standard NPS question, "How likely are you to recommend us on a scale from 0 to 10?” If 70% of respondents are Promoters and 10% are Detractors, then you have an NPS of 60. You can refine your view using filters for **campaigns**, **segments**, or **date ranges** to analyze performance for specific cohorts or time periods.

The following chart illustrates how feedback is distributed across Detractors, Passives, and Promoters:


<Image src="https://files.readme.io/26cc12a4de0658533f440282dc7f7b18262a0438c3cca5ea33ae1962d543193f-NPS.png" alt="View NPS for All Users" align="center" border={true} />


The NPS board also provides:

- NPS Score Trend over a specific period (daily, weekly, monthly).


<Image src="https://files.readme.io/cf9f8d5131071d67a1262a9cd5030b14d622f6e04b7c12ebf82628ecc7aca0db-NPS_Score_Trend.png" alt="NPS Score Trend" align="center" border={true} />


- NPS Buckets Trend for Detractors, Passives, and Promoters over a specific period (daily, weekly, monthly).


<Image src="https://files.readme.io/3661267261c9769cf6f7c90b35230e26906661644135535db6e7fc2159e96e26-NPS_Buckets_Trend.png" alt="NPS Comparison" align="center" border={true} />


- A bar graph view of the _Ratings Distribution_  for the selected duration


<Image src="https://files.readme.io/485b6983f98b7c434a231edab53e5beff79f0a8fdfe33c00814a92884f803b03-Ratings_Distribution.png" alt="NPS Comparison" align="center" border={true} />


Additionally, you can view the trend chart for Total Responses Received daily, weekly, and monthly.


<Image src="https://files.readme.io/4b3d3b90036564e49232ed96b04a91eac546756a4e4022ebe2f555031b027d55-Total_Responses_Received_Trend.png" alt="1744" align="center" border={true} />


To understand event-related information in detail, refer to [Analysing User Ratings in Analytics](https://docs.clevertap.com/docs/user-ratings).

# FAQs

### How is the AI summary generated?

CleverTap uses NLP models to detect recurring patterns, sentiments, and themes in comments.

### Can I export comments and insights?

Yes. The comments table and filters support export to CSV/Excel. Click the download icon to export data.
