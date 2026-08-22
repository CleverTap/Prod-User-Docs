---
title: Journeys
excerpt: >-
  Lean how Journeys help you automate personalized, goal-driven user engagement
  across channels.
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

With Journeys, you can craft seamless, automated omnichannel messaging experiences for your users using our intuitive Journey canvas. It is designed to guide users through a series of touchpoints, wherein each messaging channel delivers the most relevant content at the most relevant time, driving them toward your desired conversion. 

For example, you can automate welcome messages after signup, send timely reminders for incomplete actions, or celebrate user achievements with rewards. By aligning your communication with each milestone, Journeys helps you create meaningful interactions that drive conversions and foster long-term loyalty (refer to the following illustration). 

<Image alt="Sample Use Case for Journeys" align="center" border={true} src="https://files.readme.io/665c16d8bdae138658c422930d9c47976afd2834134822b30a40089135a958b0-Product_Orchestration_Fold_1.gif">
  Sample Use Case for Journeys
</Image>

You can always update the What section of a live journey, such as message content or service provider settings. For changes beyond these, such as updating the entry criteria that determine which users qualify for the journey, rearranging nodes to adjust the communication flow, or modifying goals, you must create a new draft version of the journey. This lets you optimize journeys safely without disrupting users in the current version. For more information, refer to [Editing in Journeys](doc:edit-a-journey).

# Journey Overview Video Tutorial

Discover the video tutorial for the Journey overview and a sample use case.

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/xzFcsnwtrKVCMDKstOv9yw/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

# Advantages of Journey

The following are the advantages of CleverTap Journey:

* **Automates and enhances user engagement experiences within the app**: By automating engagement workflows, apps can trigger in-app messages, such as personalized offers, when a user adds an item to their cart but does not complete the purchase. This ensures timely and relevant communication.
* **Delivers personalized and omnichannel messaging experiences**: For example, a user browsing shoes on an e-commerce portal could receive an email with tailored recommendations, followed by a push notification with a discount code if they don’t act on the email.
* **Increases user retention**: By sending regular updates, such as reminders for unused loyalty points or upcoming app-exclusive events, you can keep users engaged and encourage them to revisit the app frequently.
* **Experimentation using[IntelliNODE](doc:intellinode)**: By using the IntelliNODE feature, businesses can A/B test different journey paths for the users. For example, testing whether offering a 10% discount versus free shipping leads to better conversion rates for abandoned cart recoveries.
* **Flexible Editing and Continuous Optimization**: For active journeys, minor changes such as updating message content or provider settings can be made without disrupting the user movement within the same version. For structural edits, such as changing entry criteria, node paths, or goals, you must create a new version, ensuring active users are not affected while optimizing the journey. For example, a retention team wants to improve reactivation rates for dormant users. In the current journey, users receive a single push notification after seven days of inactivity. The team creates a new version that introduces an additional email touchpoint on day five and adjusts the messaging sequence. This allows you to test the new journey without affecting users in the existing journey, and compare the results to determine which version drives better engagement.

A truly effective journey reaches users across multiple touchpoints. By leveraging [Omnichannel Marketing](https://clevertap.com/blog/omnichannel-marketing-guide/), you can create personalized and consistent experiences across channels such as Email, Push, SMS, and more.

# Resources

<HTMLBlock>{`
<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1rem;
    padding: 0 1rem;
    max-width: 100%;
    margin: 0 auto;
  }

  .integration-card {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  padding: 1.5rem 1rem; /* add top & bottom padding */
  min-height: 64px; /* ensures consistent tile height */
  background: #fff;
  border-radius: 12px;
  border: 1px solid rgba(0, 0, 0, 0.08);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
  transition: box-shadow 0.2s ease-in-out;
  text-decoration: none;
}

  .integration-card:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  }

  .icon {
    width: 24px;
    height: 24px;
    stroke: #2b2e33;
    flex-shrink: 0;
  }

  .name {
    font-size: 1rem;
    font-weight: 600;
    color: #2b2e33;
  }
</style>

<div class="grid">

  <a href="https://docs.clevertap.com/docs/journey-list-edit-a-journey" class="integration-card">
    <div class="name">Journey List</div>
  </a>
  <a href="https://docs.clevertap.com/docs/journey-states-edit-a-journey" class="integration-card">
    <div class="name">Journey States</div>
  </a>
 <a href="https://docs.clevertap.com/docs/create-a-journey-edit-a-journey" class="integration-card">
    <div class="name">Create a Journey</div>
  </a>
<a href="https://docs.clevertap.com/docs/edit-a-journey" class="integration-card">
    <div class="name">Edit a Journey</div>
  </a>
<a href="https://docs.clevertap.com/docs/journey-performance-edit-a-journey" class="integration-card">
  <div class="name">Journey Performance</div>
</a>
<a href="https://docs.clevertap.com/docs/viewing-journey-reports-edit-a-journey" class="integration-card">
  <div class="name">View Journey Reports</div>
  </a>
<a href="https://docs.clevertap.com/docs/editing-journeys-faqs" class="integration-card">
  <div class="name">Editing Journey: FAQs</div>
  </a>
</div>
`}</HTMLBlock>
