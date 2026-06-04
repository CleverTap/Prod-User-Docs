---
title: Recommendation Strategies
excerpt: >-
  Learn how to choose and apply the right recommendation strategy to deliver
  relevant items across different user touchpoints.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

A Recommendation Strategy defines how CleverTap selects and ranks items for each user. Each strategy uses a different approach: some surface items with high engagement across all users, others personalize based on an individual's browsing or purchase history, and others identify items with similar attributes. Choosing the right strategy determines whether a recommendation feels relevant or generic.

# Recommendation Algorithms

CleverTap recommendation strategies are built on three underlying algorithms. Each algorithm determines how items are selected and ranked.

The following table lists the algorithms and the CleverTap recommendation strategies they power:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Algorithm
      </th>

      <th>
        Description
      </th>

      <th>
        Strategies Powered
      </th>

      <th>
        Examples by Vertical
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Rule-Based
      </td>

      <td>
        * Surfaces the most popular and relevant items based on aggregate behavior across your entire user base.
        * Requires no individual user history, works for new and anonymous users from day one.
      </td>

      <td>
        Popular, Trending, Best Sellers, Popular in Category, Trending in Category, Best Sellers in Category, Last-Minute Add-ons, Last-Minute Add-ons in Category
      </td>

      <td>
        * **ECommerce**: Send a push to new users featuring this week's most-purchased products.
        * **OTT**: Recommend trending shows to new subscribers based on what most users are currently watching.
        * **Travel**: Surface the most-booked destinations in a welcome email to users who haven't searched yet.
      </td>
    </tr>

    <tr>
      <td>
        Content-Based
      </td>

      <td>
        * Recommends items with attributes similar to a seed item, based on how items are described and categorized, not on how many users have engaged with them.
        * Works immediately for newly added items since it reads item properties, not behavioral signals.
      </td>

      <td>
        More Like These, Similar to What You Viewed, Premium Alternatives
      </td>

      <td>
        * **ECommerce**: Suggest jackets similar to one a user viewed, even if the jacket was just added to the catalog.
        * **OTT**: Recommend documentaries similar in genre, tone, and length to a film the user just finished.
        * **Travel**: Suggest beach destinations with a similar climate, price range, and trip duration to one the user explored.
      </td>
    </tr>

    <tr>
      <td>
        Hybrid
      </td>

      <td>
        * Combines item attributes with each user's recent activity, giving recent engagement greater weight and updating recommendations in real time.
        * Falls back to popular items for new or inactive users.
      </td>

      <td>
        Based on What You Viewed, Because You Viewed, Frequently Bought Together, Frequently Viewed Together
      </td>

      <td>
        * **ECommerce**: Send a cart abandonment push suggesting accessories frequently bought with the item left in the cart.
        * **OTT**: Recommend episodes of a new series based on the user's most recently engaged genres, even if the series just launched.
        * **Travel**: Surface hotel upgrades for a destination the user has repeatedly viewed, combining their browsing history with property attributes.
      </td>
    </tr>
  </tbody>
</Table>

# Available Strategies

The following strategies are available to generate recommendations from your catalog:

<Cards>
  <Card title="Popular" href="https://docs.clevertap.com/docs/popular" />

  <Card title="Popular in Category" href="https://docs.clevertap.com/docs/popular-in-category" />

  <Card title="Trending" href="/docs/trending" />

  <Card title="Trending in Category" href="https://docs.clevertap.com/docs/trending-in-category" />

  <Card title="Best Sellers" href="https://docs.clevertap.com/docs/best-sellers" />

  <Card title="Best Sellers in Category" href="https://docs.clevertap.com/docs/best-sellers-in-category" />

  <Card title="Based on What You Viewed" href="https://docs.clevertap.com/docs/based-on-what-you-viewed" />

  <Card title="Frequently Bought Together" href="https://docs.clevertap.com/docs/frequently-bought-together" />

  <Card title="More Like This" href="https://docs.clevertap.com/docs/more-like-this" />
</Cards>

# Choose Right Strategy

Pick a strategy based on where the recommendation appears and what user data you have available:

| Context                       | Available Data                  | Goal                              | Recommended Strategies                                                                               |
| ----------------------------- | ------------------------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- |
| New or anonymous user         | No user data required           | Drive initial discovery           | Popular, Trending, Best Sellers                                                                      |
| Homepage/Discovery Surface    | No user data required           | Surface popular or emerging items | Popular, Trending, Best Sellers                                                                      |
| Category page                 | No user data required           | Drive category-level discovery    | Popular in Category, Trending in Category, Best Sellers in Category, Last-Minute Add-ons in Category |
| Category page                 | Browse and view history         | Personalize within a category     | Based on What You Viewed, Because You Viewed                                                         |
| Product detail page           | Browse and view history         | Keep the user exploring           | Based on What You Viewed, Because You Viewed, Frequently Viewed Together                             |
| Product detail page           | Catalog attributes              | Show similar items                | More Like These, Similar to What You Viewed                                                          |
| Product detail page           | Catalog attributes + price tier | Upsell to a better option         | Premium Alternatives                                                                                 |
| Cart and checkout             | Current cart + purchase history | Increase basket size              | Frequently Bought Together, Last-Minute Add-ons, Last-Minute Add-ons in Category                     |
| Cart and checkout             | Catalog attributes + price tier | Upsell at the point of decision   | Premium Alternatives                                                                                 |
| Post-purchase / re-engagement | Purchase and view history       | Drive repeat engagement           | Frequently Bought Together, Because You Viewed, More Like These                                      |

Select the strategy that best matches the user's context to keep recommendations relevant and effective.

<Callout icon="📘" theme="info">
  #### Tip

  Behavioral strategies that rely on engagement and purchase signals require sufficient historical data to produce meaningful results. If data is limited, start with catalog-based strategies such as Popular, Trending, or Best Sellers.
</Callout>
