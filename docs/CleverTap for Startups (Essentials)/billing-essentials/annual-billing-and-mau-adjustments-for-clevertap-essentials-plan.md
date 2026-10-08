---
title: Annual Billing and MAU Adjustments for CleverTap Essentials Plan
excerpt: >-
  Understand how billing is adjusted with time and MAU usage in the CleverTap
  Essentials Annual Plan.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The CleverTap Essentials Plan provides flexible billing through pro-rata adjustments and upgrades to Monthly Active Users (MAUs). In the CleverTap Essentials Annual Plan, if you upgrade or downgrade your MAU tier during the billing cycle, charges are adjusted based on the elapsed time and the actual number of MAUs used. This ensures that your billing accurately reflects your usage rather than charging the full amount upfront. This document outlines the billing calculations for the annual plan, focusing on pro-rata billing and MAU adjustments across various scenarios.

# MAU Upgrades

When you upgrade your MAU tier under an annual billing plan, CleverTap calculates a prorated charge for the remaining months in your current annual cycle. You get an adjusted MAU limit for the remaining months based on your existing usage. The adjustment of the new MAU limit for the rest of the year considers whether you have underused or overused your previous limit:

* **Under-Utilization**: If you have underused your MAUs, the unused MAUs are carried forward, increasing your new MAU limit.
* **Over-Utilization**: If you exceed your MAUs, the new limit after an upgrade is reduced to account for the overage, lowering your available MAUs.

# Example Billing Calculation

The following examples demonstrate how billing is adjusted for both over-utilization and under-utilization of MAUs before upgrading your plan.

Consider you are on an annual plan with the following details:

* **Billing Cycle**: January 1, 2024 to December 31, 2024
* **Total Billable Users Limit**: 60,000 MAUs (5,000 MAU/month)

Now, you upgrade your plan to a higher tier of 20,000 MAUs/month at ₹20,000/month, where your **Plan Upgrade Date** is April 11, 2024. In this scenario, you will be charged for the remaining 9 months as shown below:

**Pro Rated Amount**:  ₹20,000/month x 9 months - 30% Discount = ₹54,000

## Revised MAU Limits

Your new MAU limit for the remaining months depends on whether you overutilize or underutilize the purchased MAUs before the planned upgrade. The following scenarios explain the MAU calculations for overutilization and underutilization of MAUs before the plan upgrade.

### Scenario 1: MAU Over-Utilization Before Plan Upgrade

Consider that you consumed 70,000 MAUs, exceeding your annual MAU limit by 10,000 MAUs, before upgrading the plan.

In this scenario, the calculation for the remaining billable users and the adjusted limit after the upgrade is as follows:

| Parameter                                     | Calculation                                            |
| :-------------------------------------------- | :----------------------------------------------------- |
| Remaining Billable Users as of March 31, 2024 | \-10,000 MAUs                                          |
| Additional Billable Users (Purchased)         | 20,000 MAUs/month x 9 months = 1,80,000 MAUs           |
| Total Billable Users Limit (Post-Upgrade)     | 60,000 (original) + 180,000 (added) = 2,40,000 MAUs    |
| Revised Billable Users (Post-Upgrade)         | \-10,000 (remaining) + 180,000 (added) = 1,70,000 MAUs |

### Scenario 2: MAUs Under-Utilized Before Plan Upgrade

Now, consider that you only used 50,000 MAUs before upgrading, leaving 10,000 MAUs unused from the annual MAU limit. 

In this scenario, the calculation for the remaining billable users and the adjusted limit after the upgrade is as follows:

| Parameter                                     | Calculation                                            |
| :-------------------------------------------- | :----------------------------------------------------- |
| Remaining Billable Users as of March 31, 2024 | \+10,000 MAUs                                          |
| Additional Billable Users (Purchased)         | 20,000 MAUs/month x 9 months = 1,80,000 MAUs           |
| Total Billable Users Limit (Post-Upgrade)     | 60,000 (original) + 180,000 (added) = 2,40,000 MAUs    |
| Revised Billable Users (Post-Upgrade)         | \+10,000 (remaining) + 180,000 (added) = 1,90,000 MAUs |

> 📘 MAU Upgrade in the First Month of Annual Billing Cycle
>
> If you upgrade your MAU tier within the first month of your annual billing cycle, CleverTap does the following: 
>
> * Recalculates the billing amount based on the new tier.
> * Resets the total Billable Users limit for the entire 12-month period, excluding the days spent, and
> * Adjusts the previously paid amount against the new billing amount.
