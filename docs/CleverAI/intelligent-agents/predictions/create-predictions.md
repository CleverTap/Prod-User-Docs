---
title: Create Predictions
excerpt: >-
  Learn how to create a prediction in CleverTap with this quick step-by-step
  guide.
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

This document provides a comprehensive guide to creating predictions within CleverTap. By following these instructions, users can set up predictions tailored to their business needs and enhance engagement strategies through data-driven insights.

# Start a System Prediction

Starting a system prediction in CleverTap is a quick and straightforward process. Follow the steps below to activate a prediction within a minute:

1. Navigate to _Predictions_ from the CleverTap dashboard. The _Predictions_ page opens.
2. From the list of available system predictions, hover over the prediction you want to start.
3. Click the ![](https://files.readme.io/431b58361bec0ba934b0e2e4cd2b6249cb6dba7654242c31ef96ad3ae0b13192-Ellipsis_Icon_Predictions.png) icon displayed against the prediction name and click **Start**.
4. Click **Next** > **Next** > **Setup** to start the prediction.

The following example shows how to start the _Conversions_ system prediction:

<Image align="center" alt="Activating the Uninstalls System Prediction" border={true} caption="Activating the Uninstalls System Prediction" src="https://files.readme.io/8b24406417577076f6a6f784999a5540782b1feeb64b4204b6696a03b6444a0b-2024-12-10_19-50-29_2.gif" />

Once started, the system begins processing user data to generate prediction results. This may take some time, and the prediction activates once processing is complete.

# Create a Custom Prediction

The following are the key steps for creating any prediction:

1. Go to the _Predictions_ section from the CleverTap dashboard.
2. Click _Create Prediction_. The _Create Custom Prediction_ pop-up opens.
3. [Add Basic Details](doc:create-predictions#add-basic-details) and click **Next**.
4. [Set a Goal](doc:create-predictions#set-a-goal) and click **Next**.
5. Click **Add Rule** to [define the target audience](doc:create-predictions#define-a-target).
6. Click **Create**.

## Add Basic Details

The first step in creating a prediction is to provide key identifying information that will help you organize and manage your predictions efficiently. This information includes:

* **Prediction Name**: The name you assign to your prediction. Choose a clear, descriptive name for your prediction that allows you and your team to easily understand its purpose. **This name is going to appear as a custom User Property to indicate each user's Prediction Likelihood.**
* **Description**: A brief summary of the prediction's purpose and goals. The description offers additional context, outlining the prediction's objectives and highlighting any specific details that differentiate it from others. This is particularly useful when you have multiple predictions with similar goals but slight variations in filters or criteria.

<Image align="center" alt="Add Basic Details" border={true} caption="Add Basic Details" src="https://files.readme.io/8f69bf0d381625550ac60df82f58156197487957f9e00052b462dced6aeae086-Add_Basic_Details.png" />

## Set a Goal

Setting up a goal is a crucial step in the prediction process as it defines the specific outcome you want to anticipate. This involves the following two key components:

* **Select Goal Event**: The goal event is the specific user action that your prediction aims to anticipate. This action might include completing a purchase, signing up for a service, or reaching a milestone. By defining the goal event, you direct the prediction model to estimate the likelihood of users performing this action within the set timeframe. For example, in a travel booking app, a goal event might be Booked a Vacation Package, which tracks users who finalize their purchase of a vacation package. You can **add up to three goal events** for a Prediction.
* **Enter Prediction Period**: The prediction period specifies the time frame during which you expect the goal event to occur. This period provides context for your prediction, enabling you to plan and implement timely strategies. For instance, if the prediction period is set to _30 days_, the model will project which users are likely to book a vacation package within the next _30 days_. This helps you tailor your marketing efforts, such as offering targeted promotions or sending reminders, to drive user engagement during this period.

<Image align="center" alt="Set a Goal" border={true} caption="Set a Goal" src="https://files.readme.io/c151e575d4cfd6c55ccb2c2d32e76c304320ac02121ddd1346a853bc8a9410d7-Set_a_Goal.png" />

## Define a Target

The target segment determines which users the prediction model should analyze and for whom you want to set the Likelihood. This segment can be based on User Property, Behavior, or Interest. You can further define the target segment using filters such as their activity or purchase history to narrow down the audience. For example, you can target a segment of users who have viewed products but have not made a purchase in the last 30 days.

<Image align="center" alt="Define a Target" border={true} caption="Define a Target" src="https://files.readme.io/c895b90308b46a8013067790eb3a79e3a1e3f5e4c7585ae0dd8619b58e4b63c9-Define_a_Target.png" />

By selecting this target group, you ensure the prediction focuses on users who have shown interest but have not completed a purchase, predicting their likelihood of buying soon.

After creating a prediction, you will find it on the _Predictions_ page. The system may take up to 24 hours to process user data and deliver actionable insights.

> 📘 Active Prediction Limit
>
> You can have a maximum of **five active predictions** at a time, including both System and Custom Predictions.

# Operations

You can perform a range of actions for your predictions directly from the _Predictions_ page. Each of them is explained as follows:

## Search Prediction

You can search predictions by their _Name_ from the _Predictions_ page.

<Image align="center" alt="Search Predictions" border={true} caption="Search Predictions" src="https://files.readme.io/24c0330575a29a4f540e46e6fe52ccb50ae8f15b7af8dad2a54f52b11c7c4167-Search_Predictions.png" />

## Filter Predictions

You can filter out predictions based on the following fields by clicking  _Filters_  from the extreme right corner:

* **Prediction Type**: Indicates the type of prediction i.e. _System_ or _Custom_.
* **Created By**: Indicates the name of the user who created the prediction.
* **Prediction Status**: Indicates the status of the predictions i.e. _Available, Processing, Active, Stopped_.

<Image align="center" alt="Filter Predictions" border={true} caption="Filter Predictions" src="https://files.readme.io/abd034f9bd30c5e825fd0f4d5d6f5c43a05509bb0a9c65d278e03693c959bae1-Filter_Predictions.png" />

## Edit or Clone Prediction

This operation helps to edit or clone an already existing prediction. To edit or clone a prediction directly from the _Predictions_ page:

1. Click the ![](https://files.readme.io/431b58361bec0ba934b0e2e4cd2b6249cb6dba7654242c31ef96ad3ae0b13192-Ellipsis_Icon_Predictions.png) icon displayed against the prediction name and click **Edit** or **Clone**. The Edit or Clone Custom Prediction popup opens.
2. Make the necessary edits and click **Edit** or **Clone**.

<Image align="center" alt="Edit/Clone Custom Predictions" border={true} caption="Edit/Clone Custom Predictions" src="https://files.readme.io/9c1b5570c65fd4de01aacd55f306276908372b1877990ba44871b4aa69d09eb0-2024-12-12_15-16-34_1.gif" />

> 📘 Editing System Predictions
>
> CleverTap has specific limitations when editing System Predictions. You can not modify certain key details such as the **Target Segment**, **Name**, or **Description** for most system predictions. However, other options may vary by prediction type. Below are the editable and fixed fields for each system prediction:
>
> * **Conversion**: You can modify the **Goal** and **Prediction Period**.
> * **Retention**: Only the **Target Segment** can be edited.
> * **Uninstalls**: Only the **Target Segment** can be edited.
> * **New User Retention**: No fields can be edited for this prediction.