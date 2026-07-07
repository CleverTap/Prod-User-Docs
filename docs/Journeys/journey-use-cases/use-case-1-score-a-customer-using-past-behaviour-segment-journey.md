---
title: 'Use Case 1: Score a Customer Using Past Behaviour Segment Journey'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

Identifying a user's engagement within an app, such as user activity, time spent, frequency of app usage, etc, can be challenging. However, at CleverTap, we suggest you utilize a Past Behaviour Segment (PBS) Journey to identify certain user behavior, assign the users a score based on their activity, and segment them later. It enables you to assess the user's engagement within the product and run targeted Push, In-app, Email, and Web campaigns.

## Sample Use Case

Create your Journey with several hierarchies of engagement nodes to identify four distinct user cohorts S1, S2, S3, and S4, where S1 users are your most valuable customers, and so on. You can later save these users as a segment and send personalized campaigns.

### Create a PBS Journey

1. **Set Up the Journey**: Set up a recurring Past Behaviour Segment Journey. Set the entry criteria and time for the users to enter the Journey.

   **Score Refresh Frequency**: You can modify the frequency of updating the user score weekly, biweekly, monthly, quarterly, or any frequency you like. To do so, you can modify the entry criterion in the Journey Setup using the _Recurring entry_ or _Multiple dates_, and _Allow users to re-enter the journey_ option.


<Image src="https://files.readme.io/98d8e88-RecurringEntry.png" align="center" width="50% " border={true} />


2. **Create Journey Paths**: Create the Journey paths like a tree structure where all the nodes are mutually exclusive and collectively exhaustive. It ensures that no users are stuck along the Journey path. You can build highly complex Journey paths because there are no constraints on the tree structure.

   The following example shows a Journey with a sequence of PBS nodes that identify the user's performance of a certain event, followed by an _Update User Profile_ node and a _Force Exit_ node. If the user moves along a path and fulfills the criteria, the user property is updated, and the user is forced to exit. The user property value can be a string (S1, S2, S3, and so on.) or a score calculated from the backend.


<Image src="https://files.readme.io/e8e78d3-ScoreCustomer.jpg" alt="Scoring Customers Using Past Behaviour Journey " align="center" width="90% " border={true} />


In the above example, users who accomplish Events A, B1, and C1 on the first path will have their user property updated to S1. For example,

- A = Users who launched the app
- B1 = Users who charged for a specific number of times
- C1 = Users who added to the cart a specific number of times.


<Image src="https://files.readme.io/2d8b083-UserScoreLevel1.jpg" align="center" width="90% " border={true} />


Similarly, based on the events users complete, the user property is updated as follows:

- The user property of users who move via the second path is updated to S2.
- The user property of users who move via the third path is updated to S3.
- The user property of users who move via the fourth path is updated to S4.

From the _Find People_ section, you may then retrieve the user property updates and constantly refresh the scores for the users.

<Callout icon="📘" theme="info">
  ### Note

  You can also compute user scores using your own correlation analysis.
</Callout>

3. **Publish and Monitor**: You can now publish the Journey and monitor the Journey performance.

### Save the User Segment

To find the users having user property as S1:

1. Go to _Segment_ > _Find People_.
2. Under _Display common properties such as_, enter the following details:


<Image src="https://files.readme.io/16ad7c9-FindS1Users.jpg" align="center" border={true} />


3. To save the resultant users into a segment, Click **Save segment**.
4. Enter the segment name as _S1 Users_ and click **Create**.

You can now use the saved segment to send a campaign.

### Run a Campaign for the User Segment

After you save the segment, create a Push campaign to target the S1 users.

On the Push Notification campaign editor, under the _Who_ section, you must specify your campaign's target audience. Ensure you select _S1 Users_ as the segment. Create your message, then schedule it and publish the campaign.

For more information about creating a Push message, refer to the [Create Push Message](doc:create-message-push) document.

Campaign provides users with a more personalised and engaging experience, resulting in improved retention rates and increased customer loyalty.
