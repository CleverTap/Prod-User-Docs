---
title: User Bucket
excerpt: >-
  Understand User Bucket numbers in CleverTap and how they are used for
  segmenting and testing campaign effectiveness.
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

When a new user profile is created in CleverTap, a random bucket number between 0 and 999 is automatically assigned. This unique system user property allows you to create uniformly distributed segments of random users, effective for testing the long-term impact of various campaigns on groups of users over time. By evaluating the results from these segments over multiple campaigns, you can determine whether to retain the same bucket numbers for future campaigns or adjust your strategy based on the insights gained. This approach ensures a balanced assessment of your campaign's effectiveness over time, enabling continuous optimization and improvement.

# Use Cases

Here are some use cases where CleverTap's random bucket number assignment can be helpful:

* **Phased Feature Rollout**: Gradually release new features to random user segments. Assess user feedback and performance before a full-scale release, minimizing risk and ensuring quality.
* **Campaign Optimization**: A company wants to test the impact of different promotional offers on user engagement. They would create segments based on random bucket numbers (for example, 0-100, 101-200) and apply different offers to each segment. Then, they can compare engagement metrics to determine which offer performs best.
* **Personalization Strategies**: A retailer wants to test various personalized recommendations to improve sales. The retailer would segment users using bucket numbers and deliver different recommendation algorithms to each segment. The retailer would then measure the effectiveness of each algorithm in terms of conversion rates and sales.
* **Cross-Channel Campaign Testing**: A company is running a multi-channel marketing campaign and wants to evaluate the impact of each channel. They would randomly segment users and expose each segment to different channels (for example, email, push notifications, social media). They would then measure the effectiveness of each channel in driving conversions and engagement.

Thus, you gain actionable insights into what works best by applying distinct strategies to these segments and measuring their performance. These insights guide future decisions and strategy adjustments, allowing you to refine and enhance your campaigns based on experimental data and user behavior.

# Segment Users Based on User Buckets

When creating a segment, add the User Bucket filter. Then, you can specify a number or range of numbers to include in your segment.  
For example, create a segment of users who _Added to Cart_ but did not do a _Charged_ event in the _last 30 days_ and belong to user buckets from 0 to 100.

<Image align="center" alt="Segmenting on Random Bucket Users" border={true} caption="Segmenting on Random Bucket Users" src="https://files.readme.io/d3ef701-Random_User_Buckets.png" />

You can now include these types of segments if you want to run multiple variants of your campaigns. After running these campaigns for the required period, you can use the campaign statistics to decide whether to continue using the same bucket numbers or adjust your segmentation to optimize performance.

> 📘 Note
>
> Because the assignment is random, the performance of a particular segment in one campaign does not predict how it will perform in future campaigns. Due to the random nature of the buckets, each campaign could yield different results.

# FAQs

Find answers to the following common questions about using ̉User Buckets:

### Is the User Bucket feature the same as A/B Testing or Control Groups?

No, while all three tools assist with testing and experimentation, they serve different purposes and are utilized at various stages of your campaign planning in CleverTap.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Concept
      </th>

      <th>
        When It’s Used
      </th>

      <th>
        What It Does
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **User  Bucket**
      </td>

      <td>
        **Before campaign creation (During segmentation )**
      </td>

      <td>
        Each user is automatically assigned a random number from 0 to 999 upon profile creation. This number remains the same and helps create balanced segments for long-term tests.
      </td>
    </tr>

    <tr>
      <td>
        **A/B Test**
      </td>

      <td>
        **During campaign creation**
      </td>

      <td>
        Splits your campaign audience into different versions (A and B) to test different creatives, messages, or strategies. CleverTap automatically distributes users and tracks performance for each variant.  
        For example, out of 10,000 users, 5,000 get Variant A and 5,000 get Variant B.
      </td>
    </tr>

    <tr>
      <td>
        **Control Group**
      </td>

      <td>
        **During campaign creation**
      </td>

      <td>
        Holds back a percentage of users from receiving the campaign, so you can compare results against users not exposed to the campaign and measure the actual lift or impact.  
        For example, out of 10000 users, 1000 (10%) are held back.
      </td>
    </tr>
  </tbody>
</Table>

User Buckets help define _who_ gets included in a test group before campaign creation, while A/B Testing and Control Groups determine _how_ the test is carried out during the campaign setup.

### How does User Bucket work in practice?

Consider the example of having 500,000 users in your app.

You create a segment using the rule: User Bucket between 1 and 20. This rule creates a random segment of 10,000 users.

As the User Buckets are evenly distributed from 0 to 999, selecting a range such as 1 to 20 pulls about 2% of your total users, which is ideal for running controlled tests on a smaller group.

### Are User Buckets permanent?

Yes, User Buckets are permanent. Each user is assigned a bucket number upon profile creation, which remains consistent throughout the user's Journey.
