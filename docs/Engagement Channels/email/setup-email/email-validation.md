---
title: Email Validation
excerpt: >-
  Understand how to validate your email lists from within the CleverTap
  dashboard and improve deliverability and campaign performance.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Email Validation is a native CleverTap feature that lets you verify the quality and deliverability of email addresses in your user base, directly from the dashboard, without any third-party tool. You can validate email lists by uploading a CSV file or selecting a saved CleverTap segment. CleverTap runs each address through a series of checks, including syntax, domain, mailbox existence, spam trap detection, and more, and returns a categorized report you can act on immediately.

Sending to a list with stale or unverified email addresses hurts deliverability, increases bounce rates, and can damage your sender reputation with ISPs such as Gmail and Yahoo.

Email Validation helps you:

- Improve inbox placement by removing undeliverable or risky addresses.
- Protect your sender reputation by suppressing spam traps and invalid emails.
- Reduce campaign costs by not sending to addresses that will never receive your emails.
- Reduce bounce rates for your email campaigns.
- Keep your user data clean and actionable over time.

# How Email Validation Works

Start by creating a validation job. Provide a name, select your source (CSV file or saved CleverTap segment), and submit the job.

Once submitted, CleverTap automatically processes each email address through multiple validation checks, including syntax verification, domain validation, mailbox reachability, spam trap detection, and more. You can track the progress in real time from the listing page.

After the job is complete, review the validation report. Each email address is categorized as Valid, Invalid, Risky, Spam Trap, Disposable, or Not Validated, along with an overall summary of results for your list.

Based on these results, you can take immediate action. For example, you can unsubscribe problematic addresses from the email channel or update the `Email Validation Status` user property to ensure validation data is reflected in your segments and campaigns. You can also download the complete report as a CSV file at any time for further analysis.


<Image src="https://files.readme.io/2bf1a4716da48c2a9b639369e114afd6da80413aacd20fe2734497a306496f0a-Email_Validation.png" align="center" caption="Email Validation Workflow" border={true} />


## Email Validation Credits

Email Validation uses a credit-based model. Each email address processed in a validation job consumes one credit. This is how the validation credits are consumed:

- One credit is deducted per email address processed during a validation run.
- Credits are consumed regardless of the validation result (Valid, Invalid, Risky, and so on). If you stop a validation before it completes, credits are charged only for addresses processed up to that point.
- Re-running a validation on the same list consumes new credits.
- Overage charges are applied if you exceed the credit limit.

Your remaining quota is displayed directly on the Create Validation page. You can also view detailed usage history and billing calculations under _Billing_ > _My Plan_ > _Email Validations_. If you exceed your monthly credit limit, overage charges apply to all validations beyond the limit

# Prerequisites

Before running your first validation, ensure you have sufficient validation credits available. For more information, refer to [Email Validation Credits](doc:email-validation#email-validation-credits).

# Create Validation

Each validation run is a discrete job that processes a list of email addresses and generates a report. To create a validation, perform the following steps:

1. Go to _Settings_ > _Channels_ > _Email_ and click **Validate Emails**.
2. Enter a _Validation name_. Choose a name that helps you identify the list or purpose later. For example, Q2 Re-engagement List, Imported Users – April 2026, and so on.
3. (Optional) Add a Description to provide more context about the validation.
4. Select Email source:

   - **CSV**: Before you begin, upload your CSV file to the CSV Uploads section. Once uploaded, it will appear in the list of available CSVs when creating a validation, and you can select it. For more information, refer to [CSV Uploads](https://staging.docs.dev.clevertap.net/docs/).
   - **Segment**: Search for and select a saved CleverTap segment from the dropdown. The current user count for the segment at the time of validation is shown.


   <Image src="https://files.readme.io/6d7bc3876d0dc114d747fcdedf327d0d8726c2a49f6d9b33f9d3e76b2c8a8f57-Create_Validation.png" align="center" caption="Create Validation" border={true} />


   You can review the email count by clicking **View Email ID Count**. This count indicates the number of credits that will be consumed.
5. Click **Validate**. The validation is queued and is now being processed. You are redirected to the validation listing page, where you can monitor its progress.

# Validation Status

After submitting a validation request, you can track its progress on the _Email Validation_ listing page. Each validation displays its current status.

| Status      | Description                                                                                                                     |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------ |
| In Progress | The validation is actively processing email addresses.                                                                          |
| Completed   | All email addresses have been validated. The full report is available.                                                          |
| Failed      | The validation could not be completed due to an error. No credits are charged for failed validations.                           |
| Stopped     | You manually stopped the validation before it completed. Credits are charged for records processed up to the point of stoppage. |

# Validation Report

Once validation is _complete_ or manually stopped, the full report is available. Select _View report_ from the Email Validation page to view the validation report for any validation that has been completed.


<Image src="https://files.readme.io/b1735f0e2cd9def852d7b6df8bafee0376f57a7668939b0b081de08a9819707c-View_Validation_Report.png" align="center" caption="View Validation Report" border={true} />


The Email Validation Report provides a breakdown of your list by category, and lets you take action directly from two options:

- Unsubscribe from the email channel
- Update the email validation status property


<Image src="https://files.readme.io/65da5b39523d806be8f87a358bef79408d68a12e002afcd43e08cd6e9d3fe752-Validation_Report.png" align="center" caption="Validation Report" border={true} />


The summary panel at the top shows a count of email addresses across each category. Each address in the report is then assigned one of the following categories based on the validation checks performed:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Category
      </th>

      <th>
        Description
      </th>

      <th>
        Recommended Action
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Valid
      </td>

      <td>
        The email address is correctly formatted, the domain exists, and the mailbox is confirmed as active and able to receive email.
      </td>

      <td>
        No action required
      </td>
    </tr>

    <tr>
      <td>
        Invalid
      </td>

      <td>
        The email address is undeliverable. This includes syntax errors, non-existent domains, or mailboxes that permanently reject email.
      </td>

      <td>
        Unsubscribe or update `Email Validation Status` property to prevent sending email campaigns to such users.
      </td>
    </tr>

    <tr>
      <td>
        Risky
      </td>

      <td>
        The email address is deliverable but may have a higher risk of bounce or spam complaints (for example, catch-all domains or low engagement).
      </td>

      <td>
        Review before sending. Consider suppressing for high-volume campaigns.
      </td>
    </tr>

    <tr>
      <td>
        Disposable
      </td>

      <td>
        A temporary or single-use email address, typically created to bypass registration requirements. These rarely result in meaningful engagement.
      </td>

      <td>
        Unsubscribe to remove from the active audience.
      </td>
    </tr>

    <tr>
      <td>
        Spam Trap
      </td>

      <td>
        An email address used by ISPs and anti-spam organizations to identify senders with poor list hygiene. Sending to spam traps can severely damage your sender reputation.
      </td>

      <td>
        Unsubscribe immediately.
      </td>
    </tr>

    <tr>
      <td>
        Not Validated
      </td>

      <td>
        - The validation check could not determine the status of this address, often because mail servers do not respond to verification probes (grey-listed servers).
        - CleverTap internal error while processing
        - If you stop the validation in between.
      </td>

      <td>
        - Avoid sending to large volumes of such addresses.
        - Reach out to support if the issue persists.
        - If needed, download and reupload the list for non-validated ones.
      </td>
    </tr>
  </tbody>
</Table>

## Unsubscribe From Email Channel

After reviewing the validation report, you can unsubscribe selected email categories from the email campaigns by clicking **Apply Changes**.

Unsubscribing from this screen cannot be undone. Once applied, this action permanently unsubscribes the affected user profiles from email communication. Before clicking Apply Changes, review your selection.


<Image src="https://files.readme.io/022bf6afb0167fadc4fdef329e265063f43a4b46c50294ae9068cd16c6724d97-Unsubscribe_Selected_Email_Categories.png" align="center" caption="Unsubscribe Selected Email Categories from Email Campaigns" border={true} />


## Update `Email Validation Status` User Property

Selecting this option updates the `Email Validation Status` property on the user profile for which the email addresses are verified in the report. This allows you to segment users by validation result and create targeted campaigns or exclusion lists.


<Image src="https://files.readme.io/cbe2293dd02a78a95334d78fbd6c7189bf8d1d80e8ae7ede42f8bd0d333fc8a8-Segment_Users_Basis_Email_Validation_Property.png" align="center" caption="Segment Users Using Email Validation Status User Property" border={true} />


<br />

<br />
