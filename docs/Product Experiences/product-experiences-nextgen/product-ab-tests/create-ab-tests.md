---
title: Create A/B Tests
excerpt: >-
  Learn how you can create and manage your A/B Tests and optimize your app's
  user experience.
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

To help you start with A/B Testing on CleverTap, this document describes the fundamentals of creating and managing an A/B test.

# Key Terminologies for A/B Tests

Before we create an A/B Test, it is essential to understand the following terminologies:

### Sticky Target

A sticky target refers to a specific and unchanging group of users within the A/B test. Let us consider an example to understand this better. Consider a subscription platform that wants to conduct an A/B test for a new feature for their Premium Plan users. They have a substantial number of users on the Free plan, and they want to exclude data from these users as they cannot utilize the new feature.

For this, they can set up a target segment using the user property _Subscription Status_ set to _Premium_ to achieve this. Subsequently, if they want to exclude users from the A/B Test who initially entered as Premium users but did not renew and switched to the free version, they must clear the _Sticky Target_ option. This action ensures that users who were initially on the Premium Plan but later switched to the Free Plan are not included in the test group.

<Image align="center" alt="Sticky Target" border={true} caption="Sticky Target" src="https://files.readme.io/eff2d38-sticky.png" />

### Goals

The Goals field allows you to define the objective of your A/B Test. Setting up goals helps you measure the success of different test variations and understand how well they perform in terms of driving user engagement, conversions, or other desired outcomes.

<Image align="center" alt="Define Goal Event" border={true} caption="Define Goal Event" src="https://files.readme.io/5fe6c73-Goals.png" />

#### Filter Goal Event

You can further refine and narrow down the scope of the users for whom you want to measure the goal achievement using the _Filters_ as shown in the above image.

You can further filter your goal event based on a particular property or also add an Aggregate event property to get additional metrics in the Results. The Aggregate by event property represents the numerical value obtained as a result of the average or sum of an event property for the target audience.

You can select up to **five** events that you may want to establish as the objective for your A/B Test. You can further select up to **three** event properties to narrow down the events that are counted towards your goal.

For example, the business wants to find out the total aggregate amount for the purchase amount greater than $25 (see the following image).

<Image align="center" alt="Filter Selected Events" border={true} caption="Filter Selected Events" src="https://files.readme.io/d62cbb1-Filter_Selected_Events.png" />

### Exposure

Exposure enables you to specify the percentage of your audience that will be exposed to your A/B Test. For instance, you can test the variant on a smaller segment, such as 10% of the total audience.

When performing A/B Tests, it is essential to consider how many people you want to include and how quickly you want to see the results. As a [best practice](doc:ab-test-best-practices), it is recommended to start the test with a smaller audience and then slowly include more people to roll out the winning variant to everyone (100%).

By default, all users who fit the criteria for the test are included in the A/B test. However, if you want to start with a smaller group of people, you can specify the percentage under the _Exposure_ field before starting the test.

<Image align="center" alt="Set Exposure" border={true} caption="Set Exposure" src="https://files.readme.io/1393a07-Exposure.png" />

> 🚧 Exposure
>
> Once an A/B test begins, audience size can only be increased, not reduced. Adjustments in the Exposure impact only new users, not those already in the test. Therefore, it is recommended to start the test with a smaller audience and then slowly include more people.

### Distribution

The distribution indicates the percentage of users that are distributed between the control group and other variants. The distribution is done based on the weights assigned to each of them. Based on the weights, the variant percentages are calculated dynamically and presented visually to illustrate how each variant contributes to the A/B Test.

Upon initiating the experiment, users are initially distributed equally between the control group and variant A, with a default weight distribution of 1:1. If additional variants B and C are introduced, each is assigned an equal weight of 1. Consequently, every variant includes an equal number of users, resulting in a distribution of 25% for each variant.

> 🚧 Variant Distribution
>
> Changes to the distribution are not permitted after an experiment is published and is either running or paused.

# Create A/B Test

To create a new A/B Test for variables:

1. Click **Create A/B Test** from the _A/B Tests_ page.

2. Define the custom name for your A/B Test.

3. Under the Goals field, select your event _Goal_. Select the event filters under _Filter_ to narrow down the target audience for whom you want to measure the goal achievement. For example, consider a business willing to analyze impactful revenue-generating purchases. They can achieve this by filtering the _Purchase_  event based on the _Order Value_ property.

<Image align="center" alt="Create AB test for product experiences" border={true} caption="Create AB Test" src="https://files.readme.io/317f2bdc5e3c49c0150cd8c2d8e9e11e1fd9bdd11725c1ed5c0ee2d6b6937db1-image.png" />

4. (Optional) Enter the _Description_ for your A/B Test to add contextual information (up to 1024 characters) about your test.
5. Select the target segment for your A/B Test from the Segment dropdown. You can select previously saved segments or create a new one. If you want to target all your users at once, you also have the option to select the _All Users_ segment, as shown below.
6. Define the percentage (0-100%) of eligible users from the selected segments who will be exposed to the experiment under the _Exposure_ field. The default exposure value is 100%.
7. Select _[Sticky Target](doc:create-ab-tests#sticky-target)_  to retain variant values for users who initially met the experiment criteria and later became ineligible. This retention lasts for the entire duration of the experiment. ().
8. Define the [distribution](doc:create-ab-tests#distribution) between the _Control group_ and the additional _Variants_ by assigning weights.
9. Select the variables you want to experiment with for the A/B Test. It allows you to change the values of those variables for different variants.  
   Consider a scenario where a variable representing a Call to Action (CTA) possesses a blue color in Variant A. You can generate an additional variant for that variable, this time featuring a red color.

<Image align="center" alt="Add Variables for A/B Test" border={true} caption="Add Variables for A/B Test" src="https://files.readme.io/f4c841847bd87dd733954101e2732a1335fdec3d9ade0335c47f44f6604d28d1-image.png" />

> 📘 Note
>
> The variables available for conducting the A/B Tests are the ones defined in the Remote Configuration, along with their override segments. You can conduct an A/B Test either for all the override segments or for a particular override segment.

10. From the _Scheduling_ section, toggle to schedule the A/B Tests. You can select the start and end date for the test. You can also select if the A/B test must pause or finish after the selected date.

<Image align="center" alt="Schedule an A/B Test" border={true} caption="Schedule an A/B Test" src="https://files.readme.io/ce8662b4e98bc0df50798d7d6cabbecef3285d562106afdde2f266d04c610113-image.png" width="50% " />

10. Click **Publish Now** from the top right corner. The users now start qualifying and entering the A/B Test.

You can monitor the metrics for each variant from the Results section and declare the winner variant accordingly. Refer to [A/B Test Results](doc:ab-test-results) to learn how to analyze and conclude your A/B Tests.

# Manage A/B Tests

The following table represents the list of actions permitted after an A/B Test is published:

| Sr. No. | Actions                        | Permitted? (Yes/No) |
| :------ | :----------------------------- | :------------------ |
| 1       | Change the experiment name     | Yes                 |
| 2       | Change experiment description  | Yes                 |
| 3       | Add or Remove Goals            | Yes                 |
| 4       | Increase Exposure              | Yes                 |
| 5       | Add or Remove segment          | No                  |
| 6       | Decrease exposure percentage   | No                  |
| 7       | Change Distribution percentage | No                  |
| 8       | Adding a new variant           | No                  |
| 9       | Remove variant                 | No                  |
| 10      | Add new variables              | No                  |
| 11      | Edit Variables values          | No                  |

You can also either pause a particular A/B Test or finish it after declaring the winner variant based on the metrics displayed under the _Results_ section.

## Pause A/B Test

To pause the A/B Test:

1. Go to the required A/B Test.
2. Click the ellipsis icon from the top right corner and click **Pause** (refer to the following figure).

<Image align="center" alt="Pause or finish your A/B Test" border={true} caption="Pause or Finish your A/B Test" src="https://files.readme.io/73fd896574bdf27f3e61a12cab93b415eb4ed08d456ceb7cb976af47801b7f7b-image.png" />

Pausing the test prevents new users from joining the experiment. However, users who have already entered the test continue to experience the variant they were assigned. So, the test remains active for existing users, but no new users become a part of it until you resume the test.

## Finish A/B Test

After collecting substantial information, you can analyze the metrics, declare the winner variant and finish your A/B Test. The following scenarios arise based on the winner variant you declare:

* **Scenario 1: Declaring Control Group as the winner variant.**  
  In this case, no changes are made to the variables present under the _Remote Config_. The test concludes, and all users receive the default experience.

  <Image align="center" alt="Rollout Control Group" border={true} caption="Rollout Control Group" src="https://files.readme.io/1a05b81-scenario_1_AB_Test.png" />
* **Scenario 2: Declaring any variant as the winner with the target segment as_All Users_.**  
  In this case, CleverTap automatically applies the winning variant variables and values to the Remote Config. These new variable values supersede the existing ones, impacting all users.

  <Image align="center" alt="Rollout Winning Variant" border={true} caption="Rollout Winning Variant" src="https://files.readme.io/a3cca06-Scenario_2_AB_Test.png" />

  > 🚧 Declaring a Winner Variant for a Custom Target Segment
  >
  > * Declaring a winning variant for a custom target segment is not supported at the moment. Consequently, the automated rollout of the victorious variant to the Remote Config is unavailable.
  > * If an A/B test with a custom target segment concludes as winner, the behavior defaults to Scenario 1. In this scenario, the Control Group is declared as the winner, and the Remote Config state remains unchanged.

<Image align="center" alt="Finish A/B Test" border={true} caption="Finish A/B Test" src="https://files.readme.io/90dd707-Scenario_3_AB_Test.png" />

> 🚧 Finish A/B Test
>
> If there is an ongoing draft for a variable in use within your A/B Test on the Remote Config page, you cannot finish the A/B Test. You must first _Publish_ or _Discard_ the draft from the _Remote Config_ page to be able to finish the A/B Test.
