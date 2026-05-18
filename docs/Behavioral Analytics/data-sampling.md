---
title: Data Sampling
excerpt: >-
  Learn how CleverTap uses query sampling to deliver fast, reliable analysis
  results for large and complex datasets.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

CleverTap queries your event data to generate results when you run an analysis in Trends, Funnels, Flows, Cohorts, or Pivots. For most queries, the results are quick, but when queries involve large date ranges, high event volumes, multiple split-by dimensions, or complex filter combinations, the computation time can increase significantly. Without intervention, the analysis can cause slow load times or query timeouts, disrupting your analysis workflow.

The Data Sampling in Analytics 2.0 solves slow load times and query timeouts by intelligently selecting the best execution approach for each query, based on its estimated execution time. For slow queries, CleverTap automatically runs the analysis on a representative subset of your data. This sampled data returns results much faster. You are always informed when viewing sampled results, and you choose to load exact results whenever you need them.

With data sampling, you can:

* Get near-instant results for heavy queries without waiting minutes for a response.
* View how results differ when you view sampled data versus exact data.
* Switch to exact results with a single click whenever precision matters.
* Understand why a query is slow and what you can do to speed it up.
* Avoid query timeouts that previously left you with no results.

<Callout icon="📘" theme="info">
  #### Private Beta

  This feature is released in Private Beta. For more information about this feature or any queries, contact your Customer Success Manager or the [CleverTap Support](https://help.clevertap.com/hc/en-us/requests/new).
</Callout>

# Key Concepts

Before understanding how sampling works, familiarize yourself with the following terms:

| Term                 | Description                                                                                                                                                                                                                                                                                                                 |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sampled results      | Analysis results are computed on a representative subset of your data. Sampled results load significantly faster than exact results and are statistically representative, making them well-suited for exploratory analysis and trend identification.                                                                        |
| Exact results        | Analysis results computed on 100% of your data. Exact results are slower but fully accurate. Use these when you need precise numbers for decision-making, reporting, or sharing.                                                                                                                                            |
| Estimated query time | An internal estimate of how long a query will take to execute on your full dataset. The system uses this estimated time to decide whether to run sampled or exact results by default. The estimated time is computed automatically before each query run and is not directly visible, but it drives all sampling decisions. |

# Data Sampling for Faster Analytics

Every time you run an analysis, CleverTap estimates the time required for the query. Based on this estimate, the system automatically selects the most appropriate execution strategy.

The following three scenarios describe how the system behaves for each estimated query time range:

## Scenario 1: Fast Queries

For queries estimated to complete in 30 seconds or less, CleverTap runs exact results by default. No sampling is applied, and no sampling indicator is shown. The analysis loads with full data accuracy, and you do not need to take any action.

## Scenario 2: Medium Queries

For queries estimated to take between 30 seconds and 5 minutes, CleverTap automatically runs sampled results. This reduces load time while still giving you a statistically representative view of your data.

For example, a 90-day Funnels analysis with three split-by dimensions across a large user base triggers sampling. You can view results in 5-10 seconds instead of waiting 2-3 minutes.

<Callout icon="📘" theme="info">
  #### Sampled Badge Appearance

  The **Sampled** badge appears automatically when sampling is active. The tooltip for the badge shows as a persistent notification for the first three views in a session, and then transitions to an on-hover tooltip for subsequent views. This prevents the notification from becoming disruptive while ensuring you are always aware when results are sampled.
</Callout>

## Scenario 3: Heavy Queries

For queries estimated to take more than 5 minutes, CleverTap attempts to run the analysis on sampled data. If the sampled query also exceeds the timeout threshold, the analysis enters a _Query timed out_ state.

<Image align="center" border={true} caption="Query Timed Out State" src="https://files.readme.io/02ef4298dcaf40ebe5b61bff7e38720ea3d60c2a92ae4a3fa6b3999c15c94774-image.png" />

In this state, you can try viewing the sampled data if it was partially computed, or take steps to simplify the query so it can run successfully.

# Load Exact Data

When viewing sampled results and needing precise numbers, you can load exact data at any time.

To load exact data:

1. Hover over the _Sampled_ badge on the analysis result.

2. Click the **Load exact data** link shown alongside the badge. The link shows an estimated time for the exact query. For example, _Load exact data (~5 min)_.

3. Click **Load Exact Data**.

<Image align="center" border={true} caption="View Sampled Data" src="https://files.readme.io/b57991088b52dc68be90ab436f617c41249065b0b19f3292525fca56da6a5733-image.png" />

The query runs on your full dataset. Once complete, the results update to show 100% data. The **Sampled** badge is removed and does not reappear unless you modify the query and rerun it.

<Callout icon="📘" theme="info">
  #### Switching Between Sampled and Exact Results

  Once you switch to exact results, the system does not automatically revert back to sampled results. If you modify the query after loading exact data, the system re-evaluates the estimated query time for the new query configuration and applies the appropriate strategy again.
</Callout>

## Cached Results and Sampling

CleverTap caches query results to avoid recomputation for repeated queries. When a cached result is available for your query, whether the original result was sampled or exact, the system serves the cached version directly.

The _Sampled_ badge on the result indicates that the displayed data is a cached version of a previously sampled result. You can still click **Load exact data** to run a fresh, full-dataset query and overwrite the cached sampled result.

This cached results behavior ensures fast load times for repeated analyses without hiding the data mode from you.

# Best Practices for Faster Exact Data

If your query consistently triggers sampling or times out, it means the query scope is too broad for real-time exact computation.

The following adjustments may reduce query time significantly:

* **Reduce the date range**: Shorter date ranges scan less data. If you are looking at a 90-day trend, consider splitting it into three 30-day analyses. For initial exploration, start with a 7-day or 14-day window before expanding the duration.
* **Reduce split-by dimensions**: Each additional split-by dimension multiplies the number of result groups the system needs to compute. Remove split-by fields that are not critical to your current analysis question.
* **Simplify event filters**: Wherever possible, use equality conditions or pre-defined segments to optimize your query. Complex filter conditions, such as _contains_, _between_, increase computation time.
* **Use fewer events per analysis**: In Trends and Funnels, comparing multiple events together increases query complexity. Focus each analysis on the events most relevant to the question at hand. For example, instead of adding App Launch, Product Viewed, Add to Cart, Checkout Started, and Charged in a single Trends analysis, create separate analyses, one for top-of-funnel events and one for conversion events.
* **Narrow the user base with a segment filter**: Applying a segment to restrict the analysis to a smaller user population reduces the data volume scanned. For example, instead of analyzing all users, filter to a specific country, platform, or behavior segment.

# FAQs

Find answers to the following common questions about using ̉Data Sampling:

### Q. How accurate are sampled results?

Sampled results are computed on a statistically representative subset of your data. For Trend analysis, directional insights, and pattern identification, sampled results are reliable. For exact counts, totals, or metrics that require precise numbers, such as revenue figures or compliance reporting, always use exact results.

### Q. Can I always choose to run exact results, even for heavy queries?

Yes. The **Load exact data** option is always available when sampled results are shown. However, for very heavy queries, loading exact results may result in a query timeout. In these cases, simplifying the query is the recommended path.

### Q. Will my saved analyses or bookmarks remember whether my results were sampled or exact?

Bookmarks save your analysis configuration, that is, the selected events, filters, date range, and split-by settings. When you reopen a bookmark, the system re-evaluates the estimated query time for that query and applies the appropriate strategy. If the query was previously run as exact but the dataset has grown since then, it may return sampled results the next time.

### Q. If I navigate away from an analysis while exact results are loading, does the query continue?

No. If you navigate to a different analytics module or feature while exact results are being loaded, the query is stopped. You must return to the analysis and click **Load exact data** again to restart the exact query.

### Q. Can I disable sampling for my account entirely?

Sampling is enabled by default to ensure consistent performance for all users. Account-level configuration to disable sampling is not available from the dashboard. If you have specific requirements around sampling behavior for your account, contact your CleverTap Customer Success Manager.

### Q. What happens if I modify the query while viewing sampled results?

Any change to the analysis query, such as changing the date range, adding a split-by, or modifying a filter, triggers a fresh query execution. The system re-evaluates the estimated query timeout for the new configuration and applies the appropriate strategy.

### Q. Which analytics modules support data sampling?

Data sampling applies to all analytics modules in Analytics 2.0, including Trends 2.0, Funnels 2.0, Flows 2.0, Cohorts 2.0, Pivots 2.0, and Boards 2.0.
