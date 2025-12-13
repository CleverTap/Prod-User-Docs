---
title: Campaign Reports
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
You can view comprehensive reports for all campaigns you send out of CleverTap. You can use these reports to analyze campaign performance, compare performance across campaigns and understand engagement trends. 

Reports in CleverTap are available in the following formats

* Campaign list page\
  List page will give you an overview of all campaigns sent out of CleverTap, across all channels of communication. In this overview you can see things like how many times a campaign was sent out, how many engagements it received and other vital statistics.

<Image title="Campaigns_list_page.gif" alt={1236} className="border" border={true} src="https://files.readme.io/b37df2a-Campaigns_list_page.gif" />

* Campaign details page\
  Detailed report for any given campaign you have created in CleverTap. It includes all details around campaign deliveries, engagements, conversions, and errors. 

<Image title="Campagins_detail_Page.gif" alt={640} className="border" border={true} src="https://files.readme.io/b6fd5fa-Campagins_detail_Page.gif" />

> 📘 Note
>
> The calculation for errors is :\
> error rate = errors / (errors + sent)

* Email CSV report\
  You can download either a summary report of all campaigns sent out in a particular date range, or even the day-wise split. This report includes metrics like, campaign deliveries, engagements, conversions and errors. These reports once generated, are emailed to you inbox. In order to optimise dashboard performance, the data in the report is cached and you could receive data that has been generated upto 4 hours earlier. Also, it’s possible that the report be sent to you within 6 hours depending on the other activities happening at the time of requesting the report.

  * Automated daily CSV reports\
    In your CleverTap dashboard, under Settings --> Campaign reports, you can sign up for a daily campaign report which will be delivered to your inbox, once every 24 hours. This report summarizes data on all campaigns that were sent out the previous day in CleverTap.The report will be delivered at 12 midnight per your account's timezone.

  * Automated weekly CSV reports\
    In your CleverTap dashboard, under Settings --> Campaign reports, you can sign up for a weekly campaign report which will be delivered to your email inbox, once every week. You can decide the day of the week you want the report to be delivered to you. This report summarizes data on all campaigns that were sent out the previous week in CleverTap. The report will be delivered at 12 midnight per your account's timezone.

  * Campaign Reports API\
    You can use our [reports API](https://developer.clevertap.com/docs/get-campaign-report-api) to programmatically generate campaign reports for your consumption.

## Viewing Campaign Reports

You can email campaign reports from the Campaign list page.  You can check the campaigns for any errors after you open the file. 

<Image title="Campaign_Reports_Errors.gif" alt={992} className="border" width="100%" border={true} src="https://files.readme.io/9959bf8-Campaign_Reports_Errors.gif" />
