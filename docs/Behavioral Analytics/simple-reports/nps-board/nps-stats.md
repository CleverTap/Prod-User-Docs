---
title: NPS Stats
excerpt: Learn how to understand the stats on NPS board.
deprecated: false
hidden: true
metadata:
  robots: index
---
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
