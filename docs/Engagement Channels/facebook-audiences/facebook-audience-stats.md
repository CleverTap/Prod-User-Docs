---
title: Facebook Audiences Stats
excerpt: >-
  Understand the statistical information available for Facebook Audiences
  campaigns.
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

This guide explains the statistics available for Facebook remarketing campaigns in CleverTap. These statistics help you evaluate campaign performance, understand audience behavior, and make data-driven decisions to optimize your targeting and conversions.

## View Campaign Stats

After a campaign is live, you can view the performance statistics by navigating to the _Campaigns_ page and selecting the Facebook campaign you want to analyze.

You will see the following statistics: **Sent**, **Audience Size (Old)**, **Audience Size (Current)**, and **Conversions**.

### Campaign Stats Summary

The following table provides a quick overview of key metrics related to your Facebook campaign.

| Metric                      | Description                                                                                                    |
| --------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Sent**                    | Number of users exported to Facebook as part of the campaign audience.                                         |
| **Audience Size (Old)**     | Audience size at the time the campaign launched. Serves as the baseline.                                       |
| **Audience Size (Current)** | Current audience size in Facebook Ads Manager. May change due to user updates or removals.                     |
| **Conversions**             | Number of users who performed the campaign's goal event after seeing the ad.                                   |
| **Users Added**             | Number of users added to the audience during campaign creation.                                                |
| **Users Removed**           | Number of users removed due to profile changes, exclusions, or opt-outs during campaign creation.              |
| **Errors**                  | Issues encountered during campaign processing or audience sync (for example, API failures, permission errors). |

Following is a detailed explanation of each statistic to help you better interpret campaign performance, troubleshoot issues, and understand how your audience is evolving over time.

### Sent

Indicates the number of users sent from CleverTap to Facebook as part of the campaign audience. This helps you understand how many users the campaign attempted to reach.

### Audience Size (Old)

Displays the size of the remarketing audience at the time the campaign was launched. This acts as a baseline to measure how the audience has changed over time.

### Audience Size (Current)

Shows the current size of the audience in Facebook Ads Manager. This number may vary based on changes made to the audience via other campaigns or updates to user data.

Scenarios that can impact audience size:

* **Audience Not Found**: The linked audience no longer exists in your Facebook Ads account. This can happen if it was deleted by a team member or through Facebook directly. Contact your account manager if needed.
* **Couldn’t Fetch Audience Size**: CleverTap retrieves this value from Facebook each time you open the campaign. Sometimes Facebook's APIs may not respond. You can refresh the page or try again later.
* **Audience Size is 0**:

  * If the uploaded audience has not yet been matched in Facebook Ads Manager, the count may not appear for 24–48 hours.
  * If the matched user count is below 1000, Facebook hides the number to comply with data privacy policies.

### Audience Preview Summary

While creating the campaign, CleverTap displays a snapshot of the audience being prepared for export. This helps you understand how many users are being included or excluded before the campaign goes live.

* **Users Added**: Number of users who match the campaign criteria and will be added to the Facebook custom audience.

* **Users Removed**: Number of users who were previously part of the audience but are now excluded due to updated segmentation logic, profile changes, or opt-out status.

* **Errors**: Indicates any issues that occurred while syncing audience data with Facebook, such as permission errors, invalid tokens, or data format mismatches. Refer to the error logs for more details.

### Conversions

Represents the number of users who completed a desired action—such as a purchase or sign-up—after interacting with the Facebook ad. This helps determine the campaign’s success in driving business outcomes.

## Analyze Campaign Performance

In addition to the basic stats, you can also use the following performance insights available on the campaign details page.

### Message Trend

Displays a trend line showing how many messages were **Sent**, **Viewed**, or **Clicked** over time. You can view this data daily, weekly, or monthly to track engagement patterns throughout the campaign.

This insight can help you identify high-performing time windows. For example, if you observe higher click rates on specific days of the week, you can optimize your campaign schedule to focus on those periods for better performance.

### Conversion Performance

Shows the uplift in conversions generated by the campaign by comparing the target group against a control group. This allows you to understand how much of the conversion activity can be attributed directly to the campaign.

* **Target Group Conversions**: Users who were part of the campaign and converted.
* **Control Group Conversions**: Similar users who were not part of the campaign and converted independently.

### Revenue Performance

It displays the revenue generated from the target group compared to the control group. This helps understand the campaign’s financial impact and calculate the return on investment (ROI).

### Users Conversion Funnel

Visualizes the number of users at each stage of the funnel—from Sent to Converted. This helps identify where users drop off and where the conversion journey can be optimized.

## Facebook Integration Errors

The following errors may occur while creating or managing Facebook campaigns in CleverTap. Each error requires a different resolution.

| Errors                                              | Description                                                                                                                                                                                   |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Invalid Parameter**                               | The campaign contains an invalid parameter. Please review and update.                                                                                                                         |
| **Invalid Facebook Data**                           | The campaign contains an invalid parameter. Please review and update.                                                                                                                         |
| **Facebook Permission Denied**                      | The application does not have permission to perform the requested action. Ensure the correct permissions are granted.                                                                         |
| **Custom Audience Terms Not Accepted**              | Accept Facebook's Custom Audience Terms to create or edit audiences or ad sets.                                                                                                               |
| **Application Limit Reached**                       | The application has reached its usage limit. Please wait for some time before retrying.                                                                                                       |
| **Missing Account Permissions**                     | This application lacks the necessary permissions due to incomplete authorization. Disconnect and reconnect your ad account with full permissions.                                             |
| **Facebook Audience Update Failed**                 | Facebook failed to update the custom audience. Please try again.                                                                                                                              |
| **Invalid Facebook Access Token**                   | The access token provided is invalid or expired. Please verify the token and reconnect.                                                                                                       |
| **Invalid Access Token**                            | The access token is invalid. Please verify and try again.                                                                                                                                     |
| **Audience Size Too Low**                           | The audience size is too low to proceed. Reducing users further may prevent the ad from being delivered.                                                                                      |
| **Failed to Create Custom Audience**                | The system encountered an issue while creating the custom audience. Please try again.                                                                                                         |
| **Restricted from Using Facebook Products**         | Advertising permissions have been revoked. You can no longer run ads or manage advertising assets. Learn more via [Facebook’s help center](https://en-gb.facebook.com/business/help/support). |
| **Invalid Custom Audience ID**                      | The specified custom audience ID is invalid. Ensure the ID is correct or recreate the audience.                                                                                               |
| **Facebook Unknown Error**                          | An unexpected error occurred. Please try again later.                                                                                                                                         |
| **Facebook Custom Audience Data Validation Failed** | Facebook rejected the audience data due to validation failure. Please review the data format and structure.                                                                                   |
| **Facebook Max Audience Size Reached**              | The audience has reached the maximum size allowed by Facebook. Remove users or create a new audience to continue.                                                                             |