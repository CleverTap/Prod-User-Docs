---
title: A/B Test Results
excerpt: Learn how to analyze your A/B Test results to conclude your experiments.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# A/B Test Results

The A/B Test Results feature provides valuable insights from your experiments, aiding data-driven decision-making. It offers comprehensive analysis, intuitive visualization, statistical significance assessment, and variant distributed reporting. This helps users uncover insights leading to product enhancement, improved user engagement, and overall success of the A/B test.

It utilizes advanced filtration methods to ensure accurate data assessment. It includes only data captured during the user's participation in the test, excluding any data from instances where the user enters and leaves the AB test multiple times (unless the test is marked as '[Sticky](doc:create-ab-tests#sticky-target)'). This ensures that all the available metric data available on the Results page is clean and based on user behavior.

You can view the A/B Test Results for a particular period by selecting the time range from the Calendar widget in the top right corner. This helps segment and analyze data based on when events or observations occurred for the defined timeframe. You can view results for a short interval, such as a day, a week, or a month, or a longer span, such as a year or multiple years. You define the timeframe to analyze your A/B Test as follows:

<Image alt="Calendar Widget" border={true} src="https://files.readme.io/93adf9f-in-app_calendar.png" className="border" /> Define the Time Frame using the Calendar Widget

You can further categorize your data based on platform attributes such as Operating system) and User Properties using the _Group by_ option (refer to the following image):

<Image alt="Group by OS Name" border={true} src="https://files.readme.io/6727cb2-group_by_os.png" className="border" /> Group by OS Name

This helps in getting a granular view of users, allowing you to make data-driven decisions across distinct operating systems or users with different properties.

Also, hovering over the Users icon adjacent to the _Results_ tab offers a high-level breakdown of actual users entering the A/B test across different Variants and the Control group (see the following image).

<Image alt="Total users entering across the variants" border={true} src="https://files.readme.io/d2fa8eb-total_users.png" className="border" /> Total users entering across the variants

Now, the available metrics in the A/B test can be categorized into Common and Goal metrics.

## Common Metrics

Common metrics are accessible for every A/B test, regardless of whether you have chosen specific Event-based Goals. The common metrics include:

* **Unique Users**: This refers to the count of individual users who have interacted with a website, application, or service during a specific period. Each user is counted only once, regardless of how often they visit or use the platform within that timeframe.
* **Returning Users**: This refers to the individuals who have visited or interacted with a website, application, or service more than once during a specific period. They are distinguished from Unique Users who have engaged with the platform on multiple occasions.
* **First-time Users**: This refers to the individuals who visit or interact with a website, application, or service for the first time during a specific period. These users are new to the platform and have not engaged with it before within the defined timeframe.
* **Sessions**: This refers to the individual visits or interactions a user has with a website, application, or service during a particular timeframe. A session starts when a user accesses the app and ends after a period of inactivity or when the user leaves the app.  
  Tracking sessions are a great way to measure engagement for certain apps, such as video or music streaming, news, etc. You must enable session tracking from the CleverTap dashboard to track user sessions. To enable session tracking, navigate to _Settings_ > _Session analytics_ and toggle ON the [session tracking](doc:session-analytics#session-dashboard).

<Image alt="Common Metrics View" border={true} src="https://files.readme.io/129222c-common_metrics.png" className="border" />  Common Metrics View

Listed below are some key session metrics, along with their formulas and definitions:

| Metric                          | Formula                                                                         | Definition                                                                                                       |
| :------------------------------ | :------------------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------- |
| Returning Users                 | 100 x [(Total Unique Users) - (Total First-time users)] / (Total Unique Users)  | The percentage of users returning to your application or website.                                                |
| Total Sessions                  | Total occurrences of **"Session Concluded"** event                              | The total number of user sessions.                                                                               |
| Total Session Length            | Sum of values for the event property  _length_ of the _Session Concluded_ event | Calculated using the event property _length_ of the _Session Concluded_ event. The total length of all sessions. |
| Average Session Length          | (Total Session Length) / (Total Sessions )                                      | The average length of a session.                                                                                 |
| Average Session Length per User | (Total Session Length) / (Total Unique Users )                                  | The average length of a user session in your application/website.                                                |
| Average Sessions per User       | (Total Session ) / (Total Unique Users )                                        | The average number of sessions for a user.                                                                       |

## Goal metrics

Goal metrics are specific to the event and properties selected in the A/B test Goals. You can find these from the _Metrics_ dropdown on the left.

<Image alt="Goal Metrics" border={true} src="https://files.readme.io/2492c9f-goal_event.png" className="border" />  Goal Metrics

Listed below are some key goal metrics, along with their formulas and definitions:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Metric
      </th>

      <th>
        Formula
      </th>

      <th>
        Definition
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Total \<Goal event> occurrences
      </td>

      <td>
        Total occurrences of \<Goal event>
      </td>

      <td>
        The total number of times the goal event was triggered.
      </td>
    </tr>

    <tr>
      <td>
        Unique profile who triggered \<Goal event>
      </td>

      <td>
        Number of Users who triggered \<Goal event>
      </td>

      <td>
        Total number of users who triggered the goal event.
      </td>
    </tr>

    <tr>
      <td>
        Percent of Users who triggered \<Goal Event>
      </td>

      <td>
        Percent of users who triggered the \<Goal Event> =  
        100 x [(Users Who Triggered X Event) / (Total  Users)]
      </td>

      <td>
        The percentage of users in your app that triggered the goal event.
      </td>
    </tr>

    <tr>
      <td>
        Average occurrences of \<Goal event> per Unique User
      </td>

      <td>
        (Total occurrences of \<GoalEvent> / Total Unique Users)
      </td>

      <td>
        The average number of times a user triggers this event.
      </td>
    </tr>

    <tr>
      <td>
        Average occurrences of \<Goal event> per Session
      </td>

      <td>
        (Total occurrences of \<GoalEvent> / Total Sessions)
      </td>

      <td>
        The average number of times the goal event is triggered in a session.
      </td>
    </tr>

    <tr>
      <td>
        Total sum of \<Event Property> values
      </td>

      <td>
        (Total sum of \<Event Property> values)
      </td>

      <td>
        Total sum of all aggregate event property values associated with the goal event.
      </td>
    </tr>

    <tr>
      <td>
        Average of \<Event Property> values
      </td>

      <td>
        (Total sum of \<Event Property> values / Total Event occurrences)
      </td>

      <td>
        The average value of each occurrence of this event.
      </td>
    </tr>

    <tr>
      <td>
        Average of \<Event Property> values per unique user
      </td>

      <td>
        (Total sum of \<Event Property> values / Unique Users)
      </td>

      <td>
        The average of \<Event Property> values of the goal event per user.
      </td>
    </tr>
  </tbody>
</Table>

After you select the event metric of your choice from the dropdown, you can view its data in graphical and tabular format. Let us consider a sample test where an e-commerce business wants to analyze the sales. In this case, you add an event **Charged** as a Goal with aggregate property `value`. The following image shows the set of available metrics for the  **Charged** event:

<Image align="center" alt="Graphical view for the Coins Earned Event" border={true} src="https://files.readme.io/2174557-Goal_event_metrics.png" className="border" />

Graphical Data View of Charged Event

<Image align="center" alt="Tabular view for the Coins Earned Event" border={true} src="https://files.readme.io/6a71eb5-tabular_view.png" className="border" />

Tabular data view for the Charged Event

## All Time Performance

For a limited set of metrics (_Percent of users who triggered_ the \<Event>), you can see the _All Time Performance_ section.

This feature calculates data throughout the entire duration of the A/B Test, irrespective of the time frame selected at the top of the page. Based on all the data, each variant is analyzed to identify if it is statistically significant, and an **indicator** is displayed next to the variants that helps:

* Validate the reliability of the results.
* Assess whether any observed differences between the control and variant groups are not merely attributable to random chance.
* Provides you confidence in the decision-making process.

> 📘 Note
>
> CleverTap uses a two-tailed Welch's t-test with a default setting of 95% confidence interval to identify the statistically significant variant.

<Image align="center" alt="All Time Performance View for Limited Set of Metrics" border={true} src="https://files.readme.io/53b013d-All_Time_Performance_Section.png" className="border" />

All Time Performance Section for a Limited Set of Metrics

## Export A/B Test Results

You can export A/B test results from the CleverTap dashboard to your own tools, such as spreadsheets, BI dashboards, or data warehouses. This export can contain data for a single test or across multiple tests, and deliver them by email or to a cloud storage partner. You can export the results once or set up a recurring subscription.

There are two types of reports available:

* Overview: Contains experiment metadata, including variant definitions, traffic allocation, winner, start and end time, and status
* Stats: Contains per-goal, per-variant conversion counts aggregated by day. It shows the numbers that power the lift and the statistical significance.

### A/B Test Export Results Details

#### Overview Report

The Overview report includes the following fields for each experiment:

| Field                   | Description                                                |
| :---------------------- | :--------------------------------------------------------- |
| Experiment ID           | Unique identifier for the experiment                       |
| Experiment Name         | Name as set in the dashboard                               |
| Status                  | Current status: Draft, Running, Stopped, or Finished       |
| Type                    | Experiment type: Visual Editor or Dynamic Variables        |
| Start Time              | When the experiment began collecting data                  |
| Created By / Updated By | Account user who created or last updated the experiment    |
| Sample %                | Percentage of eligible users included in the test          |
| Variant Names           | Name of each variant, including the Control                |
| Variant Count           | Total number of variants                                   |
| Goal Names              | Name of each tracked goal                                  |
| Winner Name             | Set when the experiment is marked as finished              |
| OS Filter               | Target operating system, if the experiment was OS-specific |
| Audience Segment        | Targeting segment applied to the experiment                |

#### Stats Report

The Stats report includes the following fields, aggregated daily per variant and goal:

| Field               | Description                                                                    |
| :------------------ | :----------------------------------------------------------------------------- |
| Date                | The day the stats were recorded (YYYY-MM-DD)                                   |
| Goal Name           | The conversion goal being measured                                             |
| Variant Name        | The variant being measured                                                     |
| Total Users Exposed | Number of users who entered the experiment on that day                         |
| Conversions         | Number of goal completions for that variant on that day                        |
| Revenue             | Aggregated revenue across variants, included when the goal is Revenue per User |

> 📘 Note
>
> Stats exports contain aggregated counts only. There are no individual user data or profile identifiers included.

### Set Up Export

Select one or more tests using the checkboxes, then click the **Export Reports** button.

<Image align="center" alt="Accessing Exports from the A/B Tests Listing Page" caption="Accessing Exports from the A/B Tests Listing Page" src="https://files.readme.io/e71b6bf0f82206c76a7901360eeb9ec8e70858936390a012c5e6d9c0c90a53c6-image.png" />

It opens the _A/B Test Reports_ panel, which has two tabs: _Setup_ and _Subscriptions_.

#### Setup Tab

Use the Setup tab to configure a new export.

<Image align="center" alt="A/B Test Reports — Setup Tab" border={true} caption="A/B Test Reports — Setup Tab" src="https://files.readme.io/3e0b0c6f3c974bcbf6ebe7474b31ff9f87b932a3ea94dbff956d39654b033398-image.png" width="50% " />

The setup tab has the following selections:

| Field                 | Options                                              | Description                                                                                                                                                                                                   |
| :-------------------- | :--------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _Report name_         | Free text                                            | A label to identify this export in your Subscriptions list                                                                                                                                                    |
| _Create a report for_ | _Selected Tests_ or _All tests with filters applied_ | Choose whether to export only the tests you selected or all tests currently visible in the listing                                                                                                            |
| _Data to include_     | Overview, Stats                                      | Select one or both report types to include in the export                                                                                                                                                      |
| _Split data by_       | Day, OS, Variant type                                | Determines how the Stats data is sliced. **Day** produces one row per day; **OS** segments by operating system; **Variant type** pivots data by variant                                                       |
| _Report frequency_    | _One Time_ or _Recurring_                            | **One Time** generates the export immediately. **Recurring** re-runs it automatically on a daily or weekly cadence. Recurring exports run once per day at a fixed time in your account's configured timezone. |
| _Delivery method_     | _Email_ or _Partners_                                | See [Delivery Options](#delivery-options) below                                                                                                                                                               |

Click **Save** to create the subscription.

##### Delivery Method

You can either set the delivery method to Email or Partners.

###### Email

The generated report is sent to the email address associated with your CleverTap account login. Depending on file size, the file is either attached directly or included as a download link.

###### Partners (Cloud Storage)

You can deliver exports directly to a cloud storage destination. Configure your credentials first in _Settings > Partners_, then select the partner during export setup.

The following are the supported partners:

| Partner                  | Configuration required                                                   |
| :----------------------- | :----------------------------------------------------------------------- |
| **AWS S3**               | Bucket name, region, and IAM credentials or role ARN                     |
| **Google Cloud Storage** | Bucket name and service account key                                      |
| **Azure Blob Storage**   | Storage account name, container name, and connection string or SAS token |
| **Snowflake**            | Account URL, database, schema, table, and credentials                    |

#### Subscriptions Tab

The Subscriptions tab lists all the recurring exports that you set up. Each entry shows the subscription name, data type, split-by setting, and delivery partner.

<Image align="center" alt="A/B Test Reports - Subscriptions Tab" border={true} caption="A/B Test Reports - Subscriptions Tab" src="https://files.readme.io/b787307843f6ad5ae6adde319be95dc935b2514ccf229f23b05734ff8dd146ce-image.png" width="50% " />

From this tab, you can do the following:

* _Search_ for a subscription by name using the search bar.
* _Edit_ a subscription by clicking its row and updating any field.
* _Delete_ a subscription to stop future runs. Files already delivered to your destination are not removed.

### Known Limits and Behavior

| Limit / Behavior                               | Detail                                                                                                                                                                                |
| :--------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Draft experiments**                          | Exports for experiments in Draft status return empty stats, as the experiment has not yet started collecting data                                                                     |
| **No events recorded**                         | If an experiment has no recorded exposure events yet, the export completes with empty stats rows                                                                                      |
| **Revenue goal aggregation**                   | Revenue goals are aggregated across the full experiment window. A month-by-month breakdown is not available in the export                                                             |
| **Recurring exports after an experiment ends** | Recurring subscriptions continue running after an experiment is stopped or finished, exporting the final state of stats. Delete the subscription manually when it is no longer needed |

## FAQ

#### Q. How far back does the stats data go?

Stats are stored from the day the experiment was created (or the start time, whichever is later). All historical daily buckets are included in each full export.

#### Q. Why is my export showing 0 conversions for a variant?

Check the following

* The experiment is in `RUNNING` or `DONE` status
* The goal event is being tracked in CleverTap, and
* The export ran after the experiment had collected sufficient data.

#### Q: Can I export multiple experiments in one file?

Yes. The "All A/B Tests" option in the subscription form creates a combined export. Each experiment appears as a separate block of rows, with the Experiment ID column identifying which rows belong to which experiment.

#### Q. Can I get real-time stats, not just daily?

The current export engine generates daily aggregates. Intra-day stats are not yet supported. However, the _A/B test Results_ tab on the dashboard does reflect near-real-time data.

#### Q. What happens to recurring exports when an experiment is stopped?

The recurring subscription continues to run and exports the final state of the experiment stats. You can manually delete the subscription once you no longer need updates.
