---
title: Annotations in Analytics
excerpt: >-
  Learn how to add contextual notes directly to trend charts to capture the
  story behind your data.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

When a chart in Analytics shows a sudden spike or dip, the chart itself rarely tells you why. The context usually lives somewhere else, such as a Slack thread, a marketing calendar, or the memory of whoever ran the campaign that week. A few weeks later, that context is gone.

An annotation is a note attached to a specific date, or a range of dates, on a Trends chart. Once added, it appears as a small marker below the trendline for everyone in your account. Hover over the marker to read the note. Annotations persist across sessions, so a note added today is still there for a teammate who opens the same chart next quarter.

Annotations help across roles in the following ways:

- A performance marketer marks the day a campaign went live, so a spike in conversions is self-explanatory.
- A data analyst marks the date range of a data pipeline incident so a dip in event volume is not mistaken for a real drop in user activity.
- A product manager scans the chart, sees every annotation at a glance, and clicks into one to read the full note.

# Annotations Access Controls

Annotations are public within your CleverTap account. There are no private annotations, so treat every note as something the whole team will eventually read.

The following table shows who can perform each action:

| Action                                   | Account Admin       | Annotation Creator        | Other Members  |
| ---------------------------------------- | ------------------- | ------------------------- | -------------- |
| View annotations on a chart              | Yes                 | Yes                       | Yes            |
| Create a single annotation               | Yes                 | Yes                       | Yes            |
| Bulk upload annotations using a CSV file | Yes                 | Yes                       | Yes            |
| Edit an annotation                       | Yes, any annotation | Yes, own annotations only | No             |
| Delete an annotation                     | Yes, any annotation | Yes, own annotations only | No             |
| Open the Manage Annotations page         | Yes                 | Yes                       | Yes, read only |

<Callout icon="📘" theme="info">
  ### Note

  You can create a maximum of 10,000 anntations per account.
</Callout>

# Creating Annotations

Every annotation is created for a trendline, and the annotation creation asks you to make two independent choices. Understanding these two choices removes most of the confusion around creating annotations. The following are the two fields:

- [Entry Type](doc:annotations-in-analytics#entry-type)
- [Date Selection](doc:annotations-in-analytics#date-selection)

### **Entry Type**

The _Entry Type_ field means how many annotations you are creating right now. You can select from the following options for the Entry Types:

- **Single**: You fill in a form and create one annotation.
- **Bulk**: You upload a CSV file and create many annotations in one upload, for example, an entire quarterly promotions calendar.

### **Date Selection**

The _Date Selection_ field means how long this one event lasted. You can select from the following options for the Date Selection:

- **Specific date**: The event occurred on a single day, such as an app release.
- **Date range**: The event spanned multiple days, such as a three-day sale.

The two choices are independent of each other. A single annotation can use a date range, and a bulk CSV file can contain a mix of specific date and date range rows.

The following table shows how a few common e-commerce events map to these choices:

| Event                                            | Entry Type | Date Selection                            |
| ------------------------------------------------ | ---------- | ----------------------------------------- |
| One app release on September 19                  | Single     | Specific date                             |
| One flash sale from October 3 to October 5       | Single     | Date range                                |
| The full festive quarter calendar with 15 events | Bulk       | Mixed, decided row by row in the CSV file |

## Annotation Options

The _Add Annotation_ window contains the following fields:

| Field                   | Required                   | Description                                                                                                                                            |
| ----------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Entry type              | Yes                        | Select **Single** to create one annotation with the form, or **Bulk** to upload a CSV file.                                                            |
| Name                    | Yes                        | A short, specific name for the event, up to 30 characters. This is what appears on the chart marker and in lists, so make it recognizable at a glance. |
| Description             | No                         | Additional context (up to 70 characters). Use it to capture the reason behind the event, not a repeat of the name.                                     |
| Date selection          | Yes                        | Choose **Specific date** for a single day, or **Date range** for a period spanning more than one day.                                                  |
| Date                    | Yes, for **Specific date** | The day the event occurred. If you open the _Add Annotations_ modal by clicking a point on the chart, this is filled in for you.                       |
| Start date and End date | Yes, for **Date range**    | The first and last day of the event. The end date must fall on or after the start date, and within 365 days of it.                                     |

# Create a Single Annotation

Consider an example in which you manage an online fashion store and run a _Weekly Flash Sale_ during July 29 to August 5, resulting in a visible spike in the _Charged_ trend.

To annotate it:

1. Open the _Charged_ trend in _Analytics_ > _Trends_, then click the data point for July 28.
2. Click **Add annotation**.
3. Select **Single** under _Entry type_.
4. Enter a name for the annotation, for example, _Weekly Flash Sale_.
5. Enter a description, for example Weekly Sale (July 28 to August 5).
6. Select **Date range** in the _Date selection_, and select the duration from July 28 to August 6 because the sale spanned for nearly 9 days.
7. Select **Add**.


<Image src="https://files.readme.io/8780df6b93178df176e90768f59b5039e65ad64755a4f1ca4b3fa20d687a58a4-2026-08-25_12-12-12_1.gif" align="center" border={true} />


The annotation immediately appears on the chart. Anyone who opens this chart later and hovers over the annotation sees the sale name and description, so the spike explains itself.

If the sale has lasted only for one day, for example, a One Day Stock Clearance Sale, you could instead keep the **Specific date** selected in step 6 and enter a specific date for the annotation.

<Callout icon="🚧" theme="warn">
  ### Note

  A _Date range_ annotation can span a maximum of 365 days. The date picker does not stop you from selecting a longer range while you are choosing dates. Instead, you will see an error message when you select **Add** if the range you picked exceeds 365 days.
</Callout>

# Create a Bulk Annotation

If you already keep a marketing or release calendar in a spreadsheet, upload it as a batch of annotations instead of creating each one by hand.

To create bulk upload annotations:

1. Open the _Charged_ trend in _Analytics_ > _Trends_.
2. Click **Add Annotation** from any of the entry points described earlier.
3. Click **Bulk** under _Entry type_.
4. Select **Sample CSV** to download a template with the correct column headers and an example row.
5. Fill in your file using the column structure described in the _Sample CSV_ file.
6. Drag your file into the upload area, or select it from your computer.
7. Select **Add**.


<Image src="https://files.readme.io/b940c4c2712c2a0ecb06e29ac0a6387a5870affd8725704bc6ce57ba993ce419-2026-08-25_12-40-49_1.gif" align="center" caption="Create Bulk Annotations" border={true} />


On success, a confirmation message appears, and all the annotations from your file are added.

<Callout icon="📘" theme="info">
  ### What Happens If a Row Has an Error

  The upload is all or nothing, meaning if even one row fails validation, none of the rows in the file are added. You will see the number of rows that failed along with a **Download error report** link. The report lists the row number, the column, and the reason for each failure, so you can fix your file and upload it again.&#x20;

  Also, duplicate rows, meaning the same name and date appearing more than once, are allowed. Bulk uploads are intentionally permissive. If you upload duplicates by mistake, remove them from the Manage Annotations page.
</Callout>

## CSV File Structure

Your file must be a CSV, encoded in UTF-8, no larger than 2 MB, and no more than 5,000 rows. The following is the CSV file structure for bulk annotations:

| Column      | Required | Format                    | Notes                                                                                                                         |
| ----------- | -------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| name        | Yes      | Text, up to 30 characters | The name shown on the marker and in lists.                                                                                    |
| start_date  | Yes      | YYYY-MM-DD                | Use the ISO date format, for example, 2026-11-08.                                                                             |
| end_date    | No       | YYYY-MM-DD                | Leave blank to create a specific date annotation. If present, it must fall on or after start_date, and within 365 days of it. |
| description | No       | Text, up to 70 characters | If your description contains a comma, wrap the whole value in quotation marks.                                                |

Continuing the fashion store example, suppose you want to load the entire festive quarter at once. Save the following as `festive_quarter_calendar.csv`:

```csv
name,start_date,end_date,description
Diwali Sale,2026-11-08,2026-11-12,20% off across all categories
iOS App v4.2 Release,2026-09-19,,Introduces the new referral flow
Server Maintenance Window,2026-08-14,,"Checkout was unavailable for 3 hours"
Flash Sale Weekend,2026-10-03,2026-10-05,40% off on new arrivals
```

In the above examples, the _Diwali Sale_ and _Flash Sale Weekend_ rows include an `end_date`, so they become date range annotations. The _iOS App v4.2 Release_ and _Server Maintenance Window_ rows leave `end_date` blank, so they become specific date annotations.

# View Annotations on a Chart

Annotations appear as small numbered markers in a row just below the trendline, aligned to the date they belong to.

Hover over a marker to view a popover with the date, the annotation name, and the description.


<Image src="https://files.readme.io/b0349e4ad83a5eb4e1b8b9d5302fd8939b6560b870867cc43d9cdd58fe411ec7-2026-08-25_11-50-27_1.gif" align="center" caption="View an Annotation Marker" border={true} />


## Annotations Tab

Every Trends chart has an **Annotations** tab next to the _Table_ and _Root Cause Analysis_ tabs. It lists every annotation whose date or date range falls within the chart's current date filter.

Select a marker to jump to the **Annotations** tab below the chart, with that entry ready for you to read. If a data point has more than one annotations than all the annotations in that data point show the count of annotations, and clicking on it takes you to the Annotations tab, where every annotation for that date appears.


<Image src="https://files.readme.io/9832dfbf12b9b5ef7fa7f74e5c7cc189da5da60eaa8ca2d15355184cf6752b84-2026-08-25_11-57-53_1.gif" align="center" caption="View All Annotation Markers" border={true} />


## Date Range Annotations on the Chart

A date range annotation appears as two markers, one at the start date and one at the end date. Nothing is drawn on the days in between, so the annotation row stays uncluttered even for a long range. Both markers open the same annotation, and the popover for either one shows the complete date range.

For example, the below screenshot shows the annotation markers of the start and end date for the Weekly Flash Sale during July 28, 2026, to August 5, 2026.


<Image src="https://files.readme.io/b5818f4d92d2c7f4ad7d5141746e966de5aff70ddd1640cbfb94b19ddb27cf96-image.png" align="center" caption="View Annotation Markers for a Date Range Annotation" border={true} />


## View Annotations at Different Chart Granularities

Trends charts can be viewed by Day, Week, or Month. Annotations always keep their true dates, and the chart groups markers to match whichever granularity you are viewing.

| Granularity | What you see                                                                                                                   |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Day         | One marker per day.                                                                                                            |
| Week        | All annotations that fall within a week are grouped into a single marker for that week, with the total count shown.            |
| Month       | All annotations that fall within a calendar month are grouped into a single marker for that month, with the total count shown. |


<Image src="https://files.readme.io/e8f96b0d6b226bb00056396370a005adf77ee38b6ca9942fb3771019c0d48eda-2026-08-25_12-07-49_1.gif" align="center" caption="View Annotations at Different Chart Granularities" border={true} />


# Manage Annotations

Manage Annotations is a central page under _Settings_ where you can search, review, edit, and delete every annotation in your account, regardless of who created it or whether it was added one at a time or through a bulk upload.

To open the Manage Annotations page, go to _Settings_ > _Manage Annotations_ from the CleverTap dashboard.


<Image src="https://files.readme.io/b8363fe3bd61220ec3d5d9eaf2155e75e8f07eec71972135178e39e7ad815c66-image.png" align="center" caption="Manage Annotations" border={true} />


The page lists the following columns for every annotation:

| Column      | What it shows                                                                 |
| ----------- | ----------------------------------------------------------------------------- |
| Name        | The annotation name you enter at the time of creating an annotation.          |
| Description | The full or truncated description of the annotation, depending on its length. |
| Date        | The single date, or the start and end dates for a range.                      |
| Created By  | The email address of the person who created the annotation.                   |
| Created On  | The date the annotation was added.                                            |

## Edit an Annotation

If you created an annotation, or you are an Account Admin, you will see edit and delete controls on its row. Other account members can view the row, but will not see any controls on it.

To edit an annotation:

1. Go to _Settings > Annotations_.
2. Find the annotation using the search bar or by sorting the table.
3. Select the edit control on its row.
4. Update the name, description, or dates as required.
5. Save your changes.


<Image src="https://files.readme.io/833d605b355e798fdc676ba4a2349cfaeb7a15b4fa52b9a89846e412b0f5b7a9-2026-08-25_11-32-45_1.gif" align="center" caption="Edit an Annotation" border={true} />


## Delete an Annotation

To delete an annotation:

1. Go to _Settings_ > _Manage Annotations&#x20;_&#x66;rom the CleverTap dashboard.
2. Find the annotation you want to remove.
3. Click the **Delete** icon on its row.
4. Confirm the deletion.


<Image src="https://files.readme.io/a9df431c78a237473fb10897db61190711e485609a3ecd209a987dbed6523d87-2026-08-25_11-36-26_1.gif" align="center" caption="Delete an Annotation" border={true} />


<Callout icon="🚧" theme="warn">
  ### Deleting Cannot Be Undone

  Deleting an annotation permanently removes it from every chart, for every user in the account. There is currently no way to recover it. If you only need to correct a detail, edit the annotation instead.
</Callout>

# Best Practices

Follow these best practices to keep your annotations useful, easy to scan, and trustworthy for everyone in the account:

- Keep annotation names short and specific. A name like _iOS App v4.2 Release_ is more useful at a glance than _App Update_.
- Use the description field to capture the reason behind the event, not a repeat of the name.
- Choose **Specific date** unless the event genuinely spans multiple days. A specific date annotation is easier to scan on a busy chart.
- Add annotations as events happen, while the context is fresh, rather than reconstructing them later.
- For a recurring calendar of campaigns, releases, and holidays, prepare a CSV file once and reuse the same structure every quarter.
- Before deleting an annotation, remember it disappears from every chart for every user. Edit it instead if you only need to correct a detail.

# Troubleshooting

The following are common issues you might encounter while working with annotations, along with their resolutions:

### **I cannot edit or delete an annotation**

Only the person who created it and Account Admins can edit or delete an annotation. If an annotation needs a correction, contact its creator or your Account Admin.

### **My CSV upload was rejected.**

The upload only succeeds if every row passes validation. Select **Download error report** to see exactly which rows failed and why, correct your file, and upload it again. Common causes are a missing name or `start_date`, a date not in the `YYYY-MM-DD` format, and an `end_date` that falls before the `start_date` or more than 365 days after it.

### **An annotation I expect to see is missing from the chart.**

Check that the chart's date filter includes the annotation's date or date range. Annotations only render for dates within the currently selected range.

### **The chart looks cluttered with too many markers.**

Switch the chart to Week or Month view to group nearby annotations into a single marker, or open the Annotations tab for a clean list instead of relying on the chart markers.

# Frequently Asked Questions

Find answers to the following common questions about using Annotations:

### Who can see the annotations I create?

Anyone with access to Analytics in your account can see any annotation, along with your name and the date you created it. There is currently no way to make an annotation private.

### What is the difference between Single and Bulk entry types?

The entry type controls how many annotations you create at once. Single creates one annotation using the form. Bulk creates many annotations from a CSV file at once. It is a separate choice from the date selection, which controls whether one annotation covers a single day or a range of days.

### What is the difference between a specific date and a date range annotation?

A specific date annotation applies to a single day and appears as a single marker. A date range annotation spans two or more days and renders as two markers, one on the start date and one on the end date, with nothing drawn on the days in between.

### Is there a limit to how many annotations I can add?

There is no limit for a single date. Your account as a whole can hold up to 10,000 annotations before you will need to clean up older ones from the Manage Annotations page.

### Can I add annotations to funnels, cohorts, or retention charts?

Not in this release. Annotations are currently available on Trends charts only.

### Does a bulk upload check for duplicate annotations?

No. If your CSV file contains the same name and date more than once, all of those rows are added. Review your file before uploading, or clean up duplicates afterward from the Manage Annotations page.

### If I delete an annotation, can I get it back?

No. Deleting an annotation is permanent and removes it from every chart for every user. If you are not certain, edit the annotation instead.

<br />
