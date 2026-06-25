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
        - Surfaces the most popular and relevant items based on aggregate behavior across your entire user base.
        - Requires no individual user history, works for new and anonymous users from day one.
      </td>

      <td>
        Popular, Trending, Best Sellers, Popular in Category, Trending in Category, Best Sellers in Category
      </td>

      <td>
        - **ECommerce**: Send a push to new users featuring this week's most-purchased products.
        - **OTT**: Recommend trending shows to new subscribers based on what most users are currently watching.
        - **Travel**: Surface the most-booked destinations in a welcome email to users who haven't searched yet.
      </td>
    </tr>

    <tr>
      <td>
        Content-Based
      </td>

      <td>
        - Recommends items with attributes similar to a seed item, based on how items are described and categorized, not on how many users have engaged with them.
        - Works immediately for newly added items since it reads item properties, not behavioral signals.
      </td>

      <td>
        More Like This
      </td>

      <td>
        - **ECommerce**: Suggest jackets similar to one a user viewed, even if the jacket was just added to the catalog.
        - **OTT**: Recommend documentaries similar in genre, tone, and length to a film the user just finished.
        - **Travel**: Suggest beach destinations with a similar climate, price range, and trip duration to one the user explored.
      </td>
    </tr>

    <tr>
      <td>
        Hybrid
      </td>

      <td>
        - Combines item attributes with each user's recent activity, giving recent engagement greater weight and updating recommendations in real time.
        - Falls back to popular items for new or inactive users.
      </td>

      <td>
        Based on What You Viewed
      </td>

      <td>
        - **ECommerce**: Send a cart abandonment push suggesting accessories frequently bought with the item left in the cart.
        - **OTT**: Recommend episodes of a new series based on the user's most recently engaged genres, even if the series just launched.
        - **Travel**: Surface hotel upgrades for a destination the user has repeatedly viewed, combining their browsing history with property attributes.
      </td>
    </tr>
  </tbody>
</Table>

# Available Strategies

The following strategies are available to generate recommendations from your catalog:

## Popular

<Cards>
  <Card title="Popular" href="https://docs.clevertap.com/docs/popular" />

  <Card title="Popular in Category" href="https://docs.clevertap.com/docs/popular-in-category" />
</Cards>

## Trending

<Cards>

  <Card title="Trending" href="https://docs.clevertap.com/docs/docs/trending" />

  <Card title="Trending in Category" href="https://docs.clevertap.com/docs/trending-in-category" />
</Cards>

## Best Sellers

<Cards>
  <Card title="Best Sellers" href="https://docs.clevertap.com/docs/best-sellers" />

  <Card title="Best Sellers in Category" href="https://docs.clevertap.com/docs/best-sellers-in-category" />
</Cards>

## Hybrid Strategy Recommendation

<Cards>
  <Card title="Based on What You Viewed" href="https://docs.clevertap.com/docs/based-on-what-you-viewed" />
</Cards>

## Content Strategy Recommendation

<Cards>
  <Card title="More Like This" href="https://docs.clevertap.com/docs/more-like-this" />
</Cards>

# Choose Right Strategy

Pick a strategy based on where the recommendation appears and what user data you have available:

| Goal                              | Available Data            | Recommended Strategies                                              |
| --------------------------------- | ------------------------- | ------------------------------------------------------------------- |
| Drive initial discovery           | No user data required     | Popular, Trending, Best Sellers                                     |
| Surface popular or emerging items | No user data required     | Popular, Trending, Best Sellers                                     |
| Drive category-level discovery    | No user data required     | Popular in Category, Trending in Category, Best Sellers in Category |
| Personalize within a category     | Browse and view history   | Based on What You Viewed                                            |
| Keep the user exploring           | Browse and view history   | Based on What You Viewed                                            |
| Show similar items                | Catalog attributes        | More Like This                                                      |
| Drive repeat engagement           | Purchase and view history | More Like This                                                      |

Select the strategy that best matches the user's context to keep recommendations relevant and effective.
