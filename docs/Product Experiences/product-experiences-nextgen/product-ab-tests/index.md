---
title: Product A/B Tests
excerpt: Learn how to leverage A/B Testing to optimize your app's user experience.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Introduction

A/B tests help compare users who get the regular app experience (Control Group) with one or more groups who get different experiences (groups A, B, C, etc.). It helps identify the more effective changes for your app.

A/B testing enables you to experiment with new features or changes in a select user group. This approach minimizes the risk of receiving adverse feedback from your entire user base in case of a mishap. You can monitor how well your experiments perform within a small set of users and then make improvements before releasing the modifications to everyone.

For example, you can test your app for a better Click-Through Rate (CTR). You can experiment by trying out different variants of CTA. Here, the button in one app variant reads as "Buy Now," and the same in another variant reads as "Hurry!".

You can run this test for a few weeks and identify the CTA that delivers a higher CTR. You can roll out these changes partially (say, 10 percent of the segment). If the results are satisfactory, you can declare the variant generating the highest CTR as a winner variant. You can then roll out the feature to all the users.

# Variant Distribution

CleverTap uses a deterministic hashing mechanism to assign each user to a variant. CleverTap combines the A/B test ID with a user identifier to calculate a fixed number for that user, and then uses that number to select a variant. Because the same inputs always produce the same number, a user receives a consistent variant for the same A/B test.

## User Identifiers Used for Assignment

The identifier that CleverTap uses depends on whether the user is identified or anonymous:

* **Identified users**: CleverTap bases the allocation on the user's identity. The same user receives the same variant on every device.
* **Anonymous users**: CleverTap bases the allocation on the device ID. The same anonymous user may see different variants on different devices.

## Variant Allocation Ranges

CleverTap distributes users across variants based on the percentage (weight) configured for each variant. These percentages apply to the users included in the A/B test, not to your entire audience. For example, an A/B test has the following variants, listed in this order:

* Control: 50%
* Variant A: 30%
* Variant B: 20%

CleverTap converts these percentages into the following allocation ranges between 0 and 1, following the order of the variants in the A/B test:

* Control: 0.00 to less than 0.50
* Variant A: 0.50 to less than 0.80
* Variant B: 0.80 to less than 1.00


<Image src="https://files.readme.io/0c5bb2ee9a2a9bd7fcfbac9839ae73e111e9b1ef40fc9b600b516cddcb738404-image.png" alt="A number line from 0 to 1 divided into three ranges: Control from 0.00 to less than 0.50, Variant A from 0.50 to less than 0.80, and Variant B from 0.80 to less than 1.00." align="center" caption="Allocation Ranges" border={true} />


## Assigned Value

Each user receives a consistent assigned value between 0 and 1. The range that contains this value determines the user's variant. CleverTap generates the assigned value from the A/B test ID and the user identifier. Because the same inputs always produce the same value, the user's allocation remains consistent for that A/B test.

The following table shows how three users are assigned to variants:

| User   | Assigned Value | Range Check             | Variant   |
| ------ | -------------- | ----------------------- | --------- |
| User 1 | 0.12           | Below 0.50              | Control   |
| User 2 | 0.67           | From 0.50 to below 0.80 | Variant A |
| User 3 | 0.93           | From 0.80 to below 1.00 | Variant B |

The assignment is effectively random across your audience, but fixed for each individual user. This gives you a reliable basis for comparing variant performance.

## Sticky Target

The _Sticky Target_ setting controls whether users stay in an A/B test after they leave the targeted group. It is selected by default.

* When selected, users remain in the A/B test after they leave the targeted group.
* When cleared, users exit the A/B test after they leave the targeted group.

You can configure this setting in the _Target_ section when you create the A/B test. You cannot change it after the A/B test starts.

For more information about creating A/B tests, refer to [Create A/B Tests](https://docs.clevertap.com/docs/create-ab-tests).

# A/B Tests Dashboard

The A/B Tests dashboard displays all your ongoing and previous A/B tests. It shows you whether the test is active or inactive and provides details such as its *Name*, *Status*, and *Created Time*, along with the names of the creators and the last person who edited the test.

You can locate your A/B tests by their Name or ID.

<Image alt="A/B Test Dashboard" align="center" border={true} src="https://files.readme.io/57e8f49-B_Tests_1.png">
  A/B Test Dashboard
</Image>