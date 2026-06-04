---
title: Release Notes
excerpt: >-
  Explore CleverTap’s newest capabilities, designed to optimize engagement and
  retention at scale.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Stay updated with CleverTap's latest feature releases, cutting-edge feature enhancements, and performance enhancements to help you optimize your experience.

View previous updates in [What's New: 2025](https://docs.clevertap.com/docs/release-notes-2025).

<ClickableTilesForWhatsNew />

# Release Type Legend

<TypesOfRelease />

<HTMLBlock>{`
<style>
  .filters {
    margin-top: 40px;
  }

  .filters h1 {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 16px;
  }

  .filter-box {
    background-color: #f8f9fc;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 24px 32px;
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.04);
  }

  .filter-options {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px 32px;
  }

  .filter-option {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 14px;
    font-weight: 500;
  }

  .filter-option img {
    width: 20px;
    height: 20px;
  }
</style>

<div class="filters">
  <h1>Filter By Feature</h1>
  <div class="filter-box">
    <div class="filter-options">
      <label class="filter-option">
        <input type="checkbox" id="filter-security-project-settings" />
        <span class="security-project-settings">
          <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" />
          Security & Project Settings
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-data-and-integrations" />
        <span class="data-and-integrations">
          <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="Data & Integrations" />
          Data & Integrations
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-analytics" />
        <span class="analytics">
          <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" />
          Analytics
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-segments" />
        <span class="segments">
          <img src="https://files.readme.io/04fe24c1114cef41af4a4e0224cab88f5be4c31160eca491d67942c689cb79c0-Segmentation.svg" alt="Segments" />
          Segments
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-campaigns" />
        <span class="campaigns">
          <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" />
          Campaigns
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-journeys" />
        <span class="journeys">
          <img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" />
          Journeys
        </span>
      </label>

			<label class="filter-option">
        <input type="checkbox" id="filter-promotions" />
        <span class="promotions">
          <img src="https://files.readme.io/c65a9fbb8af21c3a8f01c546faa2089d52a3bf54c2efecc740879b1ea681242e-Property_1Selected.svg" alt="Promotions" />
          Promotions
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-conversations" />
        <span class="conversations">
          <img src="https://files.readme.io/ae95d26dd8714ac2522e7a2b39166d95ace62433496df35d5dcc4d90414527bd-Conversations.svg" alt="Conversations" />
          Conversations
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-product-experiences" />
        <span class="product-experiences">
          <img src="https://files.readme.io/d7de531a1060998537a4e71a078198cf28076d99e1aed3e3c1bdcb5509e29d95-Product_experiences.svg" alt="Product Experiences" />
          Product Experiences
        </span>
      </label>

      <label class="filter-option">
        <input type="checkbox" id="filter-content-manager" />
        <span class="content-manager">
          <img src="https://files.readme.io/0ed57ff4730974458d74d2a34ec4cf285aa5e84f59075a6b32550b9d1fd60ae8-Content_Manager.svg" alt="Content Manager" />
          Content Manager
        </span>
      </label>
    </div>
  </div>
</div>
`}</HTMLBlock>

# 2026

## May 

<HTMLBlock>{`
<div class="release-note article" data-category="promotions" id="configurable-point-redemption-strategies-for-loyalty-wallets">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#configurable-point-redemption-strategies-for-loyalty-wallets"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/c65a9fbb8af21c3a8f01c546faa2089d52a3bf54c2efecc740879b1ea681242e-Property_1Selected.svg" alt="Promotions" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Configurable Point Redemption Strategies for Loyalty Wallets</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>You can now configure how loyalty points are consumed during redemption and expiry directly at the Global Loyalty Wallet level. This gives your brand greater control over point liability management and allows loyalty programs to align redemption behavior with your business and customer experience goals.</p>
    <p>With Point Redemption Strategies, you can:</p>
    <p>
      <ul>
        <li>Select Expiry FIFO to redeem points closest to expiry first, regardless of when they were earned, helping minimize point expiry liability.</li>
        <li>Select Issuance FIFO to redeem the oldest earned points first, regardless of expiry date, providing a more intuitive customer experience.</li>
        <li>Rely on built-in tie-breaker rules to ensure deterministic, predictable point consumption across large volumes of point credits.</li>
        <li>Apply the chosen strategy at the wallet level during Global Loyalty Wallet creation, with no impact on existing wallets or historical transactions.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/create-loyalty-wallet#point-consumption-strategies" target="_blank">Points Redemption Strategies</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="promotions" id="advanced-filters-in-wallet-transaction-api">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#advanced-filters-in-wallet-transaction-api"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/c65a9fbb8af21c3a8f01c546faa2089d52a3bf54c2efecc740879b1ea681242e-Property_1Selected.svg" alt="Promotions" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Advanced Filters in Wallet Transaction API</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>You can now use advanced filters and pagination in the Wallet Transaction API to retrieve and manage loyalty wallet transaction history more efficiently. This enhancement helps you build scalable transaction experiences while improving API performance and frontend flexibility.</p>
    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Filter transactions using transaction type, transaction source, sale channel, campaign ID, order ID, location ID, and date ranges.</li>
        <li>Combine multiple filters to retrieve more precise transaction records.</li>
        <li>Fetch transactions within custom time windows using epoch-based timestamps.</li>
        <li>Retrieve paginated transaction history with metadata such as current page, total pages, and total records, and hasNext support.</li>
        <li>Maintain existing integrations without requiring API version upgrades or breaking changes.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://developer.clevertap.com/docs/get-wallet-transactions" target="_blank">Wallet Transaction API</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="data-and-integrations" id="salesforce-crm-connector">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#salesforce-crm-connector"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="data-and-integrations" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Salesforce CRM Connector</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now supports native imports directly from <a href="https://appexchange.salesforce.com/appxListingDetail?listingId=6d0bd1f7-9c5c-484d-87cd-cfc0c68827ca" target="_blank">Salesforce CRM Connector</a>. Pull standard and custom object data including leads, contacts, opportunities, and cases into CleverTap profiles, ready for Segmentation, Journeys, and Campaigns.</p>

    <p>With the Salesforce CRM Connector, you can:</p>

    <p>
      <ul>
        <li>Sync 17+ standard Salesforce objects such as Lead, Contact, or Order, and any custom object via a one-time record-triggered flow into CleverTap profiles and events.</li>
        <li>Choose real-time delivery or batch delivery on a 5 to 60 minute cadence, with automatic retry up to five attempts and deduplication.</li>
        <li>Use field-level filters to control which records sync, and run a one-time Historical Sync to backfill records created before the integration was set up.</li>
        <li>Monitor every sync attempt from the native Event Logs in Salesforce showing request, response, and status per record.</li>
<li>Push engagement data, campaign responses, and survey results from CleverTap back into Salesforce custom objects via OAuth 2.0-secured webhooks.</li>
<li>Route different objects to different CleverTap projects or regions using multi-connection support.</li>
      </ul>
    </p>
<p><img src="https://files.readme.io/3fe1e38403ab24b3ae2f3d46c4e54bc7500e6429c992e3ac725108086d48abb6-image_78.png" alt="Salesforce CRM Connector."> </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/salesforce-crm" target="_blank"> Salesforce CRM Connector.</a></p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="analytics" id="boards-20">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#boards-20"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Boards 2.0</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge beta">BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Boards 2.0 now includes enhancements that make your dashboards more flexible, easier to customize, and simpler to share.</p>
    <p>With these enhancements, you can:</p>
<p>
      <ul>
        <li>Filter any board by segment to focus insights on a specific audience.</li>
        <li>Rename tiles and legends to make boards easier to read without additional context.</li>
        <li>Add trends, funnels, flows, pivots, and cohorts as charts or tables directly on the board.</li>
        <li>Clone any tile with a single click to iterate on existing analysis without starting over.</li>
        <li>Export tiles as images, PDFs, or CSVs for use in decks, documents, and offline analysis..</li>
        <li>Add note tiles to include context, ownership information, or instructions directly on the board.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/boards-v2" target="_blank">Boards 2.0</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="data-and-integrations" id="data-warehouse-imports">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#data-warehouse-imports"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="data-and-integrations" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Data Warehouse Imports</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now supports native imports directly from your data warehouse. Pull user attributes and events from Snowflake, BigQuery, Databricks, Amazon Redshift, or Microsoft Fabric straight into CleverTap profiles, ready for Segmentation, Journeys, and Campaigns.</p>

    <p>With Data Warehouse Imports, you can:</p>

    <p>
      <ul>
        <li>Connect to Snowflake, BigQuery, Databricks, Amazon Redshift, or Microsoft Fabric using secure standard authentication or private key configuration, then query data using custom SQL or a simple table picker.</li>
        <li>Map warehouse columns to CleverTap user attributes or events visually with data type selection (String, Number, Boolean, Date), and validate the exact profile that will be created before going live.</li>
        <li>Schedule imports on repeat intervals, custom day-of-week or month schedules, or trigger them manually. After the first full import, only new or updated records sync on subsequent run.</li>
        <li>Monitor all imports from a single dashboard with run history, success and error counts, and one-click Run, Pause, and Stop controls. Receive email and dashboard alerts for successes, failures, and anomalies.</li>
<li>Manage access with Admin, Approver, Creator, and Member roles, backed by full audit logs for every configuration change.</li>
      </ul>
    </p>
<p><img src="https://files.readme.io/62d3677e93f585e247a28238e66d00345491608dc8edda862bf8d74e0222c31c-datawarehouse_1_2.png" alt="Data Warehouse Imports."> </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/data-warehouse-import" target="_blank">Data Warehouse Imports.</a></p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="analytics" id="funnels-20">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#funnels-20"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Funnels 2.0</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge beta">BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Funnels 2.0 now includes enhancements to make conversion analysis more flexible and actionable. These updates improve how you visualize, measure, and export funnel data across product and growth use cases.</p>
    <p>With these enhancements, you can:</p>
<p>
      <ul>
        <li>View funnels in a vertical bar chart by default, with a toggle to switch to the horizontal view.</li>
        <li>Analyze both frequency-based metrics and value-based event properties to measure engagement, revenue, or consumption.</li>
        <li>Switch between Median and Average elapsed time using a new dropdown in the chart UI.</li>
        <li>View second-level time granularity between steps</li>
        <li>Carry over chart configurations (view, metric, and display selections) when saving a funnel to a board.</li>
        <li>Export richer CSVs that include window, mode, order, average time, and median time.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/funnels-v2" target="_blank">Funnels 2.0</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="product-experiences" id="Multiple-Campaigns-Native-Display">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#Multiple-Campaigns-Native-Display"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img
        src="https://files.readme.io/d7de531a1060998537a4e71a078198cf28076d99e1aed3e3c1bdcb5509e29d95-Product_experiences.svg"
        alt="Product Experiences"
        class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Multiple Campaigns with a Single Event in Native Display</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>
  <div class="release-note-body">
    <p>You can now run multiple App Native Display campaigns from a single user event, making it easier to build multi-promotion layouts, dynamic carousels, and multi-slot screens without additional event instrumentation.</p>
    <p>With this enhancement, you can:</p>
    <ul>
      <li><strong>Fill multiple screen slots at once:</strong> A single trigger, such as Notification Viewed, can now simultaneously serve several promotions, each targeted to the right segment.</li>
      <li><strong>Control which campaigns appear first:</strong> Set campaign-level priority to decide the order in which promotions are displayed to users.</li>
      <li><strong>Build richer in-app experiences:</strong> Power carousels, multi-banner layouts, and personalised screen sections without coordinating multiple events.</li>
      <li><strong>Keep existing campaigns running as-is:</strong> Apps that have not updated to the new SDK continue to work without any changes.</li>
    </ul>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/create-message-native-display#native-display-priority" target="_blank">Native Display Priority</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="data-and-integrations" id="truecaller-clevertaps-new-enagagement-channel">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#truecaller-clevertaps-new-enagagement-channel"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="data-and-integrations" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Truecaller, CleverTap's New Enagagement Channel</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>You can now deliver verified, branded call-screen experiences directly from CleverTap campaigns and journeys using the Truecaller Integration.</p>

    <p>With Truecaller integration, you can:</p>

    <p>
      <ul>
        <li>Deliver branded call-screen experiences, including business name, logo, and contextual message, to build trust at the moment of contact.</li>
        <li>Run outbound call campaigns, post-call pop-ups, missed-call recovery, and sticky messages as part of cross-channel journeys.</li>
        <li>Use Liquid personalization, segment logic, and goal-event tracking as you do in every other CleverTap channel.</li>
        <li>Configure the integration in approximately 10 minutes using a webhook with no engineering dependencies.</li>
      </ul>
    </p>
<p><img src="https://files.readme.io/fa5769c216eb32c4e10cfd3bdb5f01a6ed9f1ef13fa5ba21384d84d283250286-Truecaller_CT_Integration.png" alt="Truecaller Integration"> </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/truecaller" target="_blank">Truecaller</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="promotions" id="custom-rewards">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#custom-rewards"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/c65a9fbb8af21c3a8f01c546faa2089d52a3bf54c2efecc740879b1ea681242e-Property_1Selected.svg" alt="Promotions" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Custom Rewards</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>Custom Rewards is now available for all Promo customers. It enables you to go beyond traditional coupons and points to deliver high-value rewards through Promo Campaigns. </p>
    <p>With Custom Rewards, you can:</p>
    <p>
      <ul>
        <li>Manage any external reward catalog on CleverTap to distribute personalized rewards and run loyalty campaigns beyond traditional reward types.</li>
        <li>Automate reward distribution for existing reward engines, including coupons, real money wallets, and other systems, without manual orchestration.</li>
        <li>Track and reconcile reward delivery using reward delivery metrics.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href=" https://docs.clevertap.com/docs/custom-rewards" target="_blank">Custom Rewards</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

## April

<HTMLBlock>{`
<div class="release-note article" data-category="product-experiences" id="inaction-segmentation-for-in-app-campaigns">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#inaction-segmentation-for-in-app-campaigns"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/d7de531a1060998537a4e71a078198cf28076d99e1aed3e3c1bdcb5509e29d95-Product_experiences.svg" alt="Product Experiences" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Inaction Segmentation for In-App Campaigns</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>

  <div class="release-note-body">
    <p>You can now trigger In-App campaigns based on user inaction within a defined time window. This enhancement extends Inaction Segmentation beyond push and email, to deliver real-time engagement while users are active in your app.</p>
    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Target users who do not complete key actions during active sessions.</li>
        <li>Reduce drop-offs by engaging users when they delay action.</li>
        <li>Deliver timely nudges to improve conversion and progression.</li>
      </ul>
    </p>
    <p>This feature is available to select customers. Minimum SDK requirements: Android v7.8.0 or later and iOS v7.5.0 or later.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/create-message-inapp#deliver-action-based-messages" target="_blank">Deliver Action Based Messages in In-App</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="new-in-frequency-limits-advanced-frequency-limits">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#new-in-frequency-limits-advanced-frequency-limits"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img
        src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg"
        alt="Frequency Limits"
        class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Advanced Frequency Limits</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>
  <div class="release-note-body">
    <p>Advanced Frequency Limits is now available, providing a centralized system to control how often users are contacted across campaigns, channels, and lifecycle stages. As users qualify for multiple campaigns simultaneously, Advanced Frequency Limits helps prevent overlapping or excessive messaging through granular, user-level communication controls.</p>
    <p>With Advanced Frequency Limits, you can:</p>
    <p>
      <ul>
        <li>Define total messages per user across all campaigns using the Global Limits option.</li>
        <li>Apply channel-level caps within an overall limit.</li>
        <li>Apply different limits for onboarding, engagement, retention, and reactivation stages.</li>
        <li>Exempt transactional and high-priority communications from frequency limits.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/advanced-frequency-caps" target="_blank">Messaging Frequency Caps</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="auto-campaign-archival">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#auto-campaign-archival"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Auto Campaign Archival</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>Auto Campaign Archival is now available to keep your campaign listing fast, clean, and easy to navigate.</p>
    <p>Campaigns in a Completed or Stopped state will now be automatically archived after 6 months (180 days). The archival runs on a rolling basis, and moves older campaigns to the Archived section while keeping your active workspace optimized.</p>
    <p>With Auto Campaign Archival, you can:</p>
    <ul>
      <li>Search faster and load campaign listings more quickly.</li>
      <li>Navigate your workspace with less clutter.</li>
      <li>Access archived campaigns at any time, as all actions remain available.</li>
    </ul>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/enhanced-campaign-list-page#archive-campaigns" target="_blank">Campaign Overview</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="product-experiences" id="advanced-web-pop-up-builder">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#advanced-web-pop-up-builder"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/d7de531a1060998537a4e71a078198cf28076d99e1aed3e3c1bdcb5509e29d95-Product_experiences.svg" alt="Product Experiences" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Advanced Web Pop-up Builder</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>

  <div class="release-note-body">
    <p>Advanced Web Pop-up Builder is now available, enabling you to create and launch web campaigns faster with greater flexibility. You can design fully customized pop-ups, preview them in real time, and deploy without relying on engineering or design teams.</p>
    <p>With Advanced Web Pop-up Builder, you can:</p>
    <p>
      <ul>
        <li>Create flexible layouts with full control over fonts, colors, and spacing.</li>
        <li>Design rich experiences using animations, image stacking, and custom backgrounds.</li>
        <li>Preview campaigns across devices before publishing.</li>
        <li>Launch, A/B test, and update content independently.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/advanced-in-app-builder-v2" target="_blank">Advanced Web Pop-up Builder</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="journeys" id="cross-project-cloning-for-engagements">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#cross-project-cloning-for-engagements"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" /></div>
    <h3 class="release-note-heading">Cross-Project Cloning for Engagements</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>Cloning engagements across projects is now available for all CleverTap customers. You can now clone campaigns and journeys across CleverTap projects, allowing teams to move faster without rebuilding engagement logic from scratch. Cross-Project Cloning lets you reuse proven campaigns and journeys across test, production, and multiple business-unit projects, directly from the Campaigns or Journeys list page.</p>
    <p>This enhancement is especially useful during onboarding (you can copy engagement from the test project to production) and for scaling successful engagement workflows across regions or lines of business.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/copy-engagements-across-projects" target="_blank">Copy Engagement Across Projects</a>.
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="Web-Inbox-Launch">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#Web-Inbox-Launch"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img
        src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg"
        alt="Campaigns"
        class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Web Inbox</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>You can now use <b>Web Inbox</b> to control how messages are delivered and
    displayed to users. This channel helps reduce message fatigue while enabling
    more effective, time-sensitive communication.</p>
    <p>With this enhancement, you can:</p>
    <ul>
      <li>Set global or campaign-level frequency caps to control how often users
      see messages</li>
      <li>Configure flexible time-to-live settings, with durations as low as
      one hour</li>
      <li>Limit the number of messages displayed in the inbox to maintain a
      clean user experience</li>
      <li>Deliver high-urgency campaigns while maintaining a streamlined inbox
      experience</li>
    </ul>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/web-inbox"
    target="_blank">Web Inbox</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

## March

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="controlled-message-delivery-and-display-with-web-inbox">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#controlled-message-delivery-and-display-with-web-inbox"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Controlled Message Delivery and Display with Web Inbox</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>

  <div class="release-note-body">
    <p>You can now control how messages are delivered in Web Inbox and displayed to users. This enhancement helps reduce message fatigue while enabling more effective, time-sensitive communication.</p>
    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Set global or campaign-level frequency caps to control how often users see messages.</li>
        <li>Configure time-to-live settings, with durations as short as one hour.</li>
        <li>Limit the number of messages displayed in the inbox to maintain a clean user experience.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/web-inbox-create-message#delivery-preferences" target="_blank">Create Message with Web Inbox</a> and <a href="https://developer.clevertap.com/docs/web-inbox" target="_blank">Setting up Web Inbox</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="data-and-integrations" id="snowflake-export">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#snowflake-export"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="data-and-integrations" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Snowflake Export</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>You can now export CleverTap data directly to to Snowflake for deeper analysis, long-term reporting, attribution, and cross-team analytics workflows.</p>

    <p>With this integration, you can:</p>

    <p>
      <ul>
        <li>Move CleverTap data into Snowflake directly, without relying on intermediate cloud storage steps or fragmented downstream pipelines, reducing engineering dependency and operational overhead.</li>
        <li>Control exports by selecting event scope, configuring export cadence, and setting identifier priority based on your use case, to match your team's analytical requirements.</li>
        <li>Query CleverTap engagement data alongside internal business datasets faster, with standardized table creation and schema that reduce ambiguity for data consumers across teams.</li>
        <li>Manage exports with built-in notifications, tracking, and auditability, to support reliable, enterprise-ready workflows.</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/snowflake-export" target="_blank">Snowflake Export.</a></p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="collapsed-media-control-in-text-over-image-push-template">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#collapsed-media-control-in-text-over-image-push-template"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img
        src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg"
        alt="Campaigns"
        class="release-note-heading-icon"
      />
    </div>
    <h3 class="release-note-heading">Collapsed Media Control in Text over Image Push Template</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>
  <div class="release-note-body">
    <p>You can now configure how media appears in the collapsed view of Text over Image push notifications directly from the dashboard. This simplifies setup and helps maintain a more consistent experience across SDK versions.</p>

    <p>With this enhancement, you can:</p>
    <ul>
      <li>Configure the collapsed view to use the same or a different image as the expanded view.</li>
      <li>Display media only in expanded view or add a large icon in collapsed view.</li>
      <li>Combine a large icon and image (for SDK v2.3.0 and above) for richer notification layouts.</li>
    </ul>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/collapsed-media-support-large-icon-and-collapsed-image" target="_blank">Collapsed Media Support (Large Icon and Collapsed Image)</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="data-and-integrations" id="revamped-facebook-audience-export">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#revamped-facebook-audience-export"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="data-and-integrations" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Revamped Facebook Audience Export</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>You can now use the revamped Facebook Audience Export to gain more flexibility and control over how you manage and activate audiences for your Facebook campaigns.</p>

    <p>With this enhancement, you can:</p>

    <p>
      <ul>
        <li>Link multiple Facebook Ads accounts within CleverTap to manage audiences across accounts more efficiently.</li>
        <li>Export audiences with improved default user property mapping for better accuracy.</li>
        <li>Manage audience workflows more reliably with key bug fixes and stability improvements.</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/setup-facebook-audiences" target="_blank">Facebook Audience Export.</a></p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="ai-generated-descriptions-for-data-schema">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#ai-generated-descriptions-for-data-schema"><i class="fa-light fa-anchor"></i></a>
    </div>

    <div>
 <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings"/>
    </div>
  <h3 class="release-note-heading">AI-Generated Descriptions for Data Schema</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
</div>

<div class="release-note-body">
    <p>You can now generate clear, consistent descriptions for your data schema using AI. This helps you better understand and manage schema elements while enabling stronger AI-driven insights across the platform.</p>

    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Generate descriptions automatically when creating or updating schema elements.</li>
        <li>Accept, edit, or dismiss AI-generated descriptions.</li>
        <li>Maintain consistency across user properties, custom events, and event properties.</li>
        <li>Leverage enriched schema data to enable deeper insights across segmentation, analytics, and journeys.</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/schema#ai-generated-descriptions-for-custom-events" target="_blank">Schema</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="improved-limits-in-campaigns-and-journeys">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#improved-limits-in-campaigns-and-journeys"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
   <h3 class="release-note-heading">Improved Limits in Campaigns and Journeys</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>

  <div class="release-note-body">
    <p>You can now cap the total number of times a user ever receives a specific Campaign or Journey message. This new lifetime limit option is available alongside existing choices to send every time or at intervals.</p>

    <p>Enhanced Limits help marketers reduce message fatigue, enforce governance, and protect customer experience by preventing over-saturation of onboarding, promotional, or reminder messages.</p>
    
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/notification-delivery-options#limits-for-engagements"target="_blank">Limits for Engagements</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="segments" id="cleverai-predictions-agent">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#cleverai-predictions-agent"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
     <img src="https://files.readme.io/04fe24c1114cef41af4a4e0224cab88f5be4c31160eca491d67942c689cb79c0-Segmentation.svg" alt="Segments" />
    </div>
    <h3 class="release-note-heading">CleverAI Predictions Agent</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>

  <div class="release-note-body">
    <p>You can now use CleverAI Predictions Agent to anticipate user behavior and take proactive action. It predicts conversions, churn, uninstalls, and other key outcomes in real time, so you can engage users before opportunities are lost. You also get visibility into the factors driving each prediction, enabling more informed decision-making.</p>

    <p>With CleverAI Predictions Agent, you can:</p>
    <p>
      <ul>
        <li>Build dynamic segments that update continuously based on behavior.</li>
        <li>Understand what drives each prediction with explainable insights.</li>
        <li>Target users precisely using predictive and behavioral filters.</li>
        <li>Measure campaign impact across different likelihood segments.</li>
        <li>Plan and execute engagements with greater confidence.</li>
      </ul>
    </p>

  <p>For more information, refer to <a href="https://docs.clevertap.com/docs/predictions" target="_blank">CleverAI Predictions Agent.</p>

  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="content-manager" id="event-reminder-personalization-content-blocks">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#event-reminder-personalization-content-blocks"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/0ed57ff4730974458d74d2a34ec4cf285aa5e84f59075a6b32550b9d1fd60ae8-Content_Manager.svg" alt="Content Manager" /></div>
    <div><h3>Event and Reminder Personalization Support in Content Blocks</h3></div>

    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
   <p>You can now use Event and Reminder personalization inside Content Blocks, making it easier to reuse dynamic email content across multiple campaigns.</p>
    <p>Previously, updating reused HTML required editing each campaign individually. With this enhancement, Content Blocks now support Event and Reminder personalization syntax in addition to existing user property personalization. Any updates made to a Content Block automatically reflect across all campaigns where it is used.</p>
    <p>With this update, you can:</p> 
    <p>
      <ul>
        <li> Reuse dynamic email content across multiple campaigns.</li>
        <li> Update content once and apply changes instantly. </li>
 <li> Add Event and Reminder personalization directly in Content Blocks using HTML syntax. </li>
    </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/content-blocks" target="_blank">Content Blocks</a>.</p>

  </div>
  <hr>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="nested-objects-in-user-properties">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#nested-objects-in-user-properties"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
   <h3 class="release-note-heading">Nested Objects in User Properties</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>

  <div class="release-note-body">
    <p>You can now use Nested Objects in User Properties for ingesting via SDK, profile updates, and campaign personalization. This enhancement expands how nested user data can be managed and referenced across CleverTap, enabling richer data structures and more flexible campaign personalization.</p>

    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Enable apps to send structured nested profile data directly through SDK integrations.</li>
        <li>Use pre-built profile update functions such as setMultiValues, addMultiValues, and removeMultiValues for multi-value properties.</li>
        <li>Update numeric values using profileIncrementValue and profileDecrementValue.</li>
        <li>Recognize date objects in nested fields, which appear as date pickers on the dashboard.</li>
        <li>Ensure backward compatibility by using existing user property ingestion and usage patterns.</li>
      </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/nested-objects-in-user-properties"target="_blank">Nested Objects in User Properties</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="journeys" id="improved-conditional-split-for-smarter-journey-routing">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#improved-conditional-split-for-smarter-journey-routing"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" /></div>
    <h3 class="release-note-heading">Improved Conditional Split for Smarter Journey Routing</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>Conditional Split now supports more flexible routing and improved journey discoverability, helping you build advanced decisioning logic and manage journeys more efficiently.</p>
    <p>The enhancements include: <ul><li><b>Routing Users with User Buckets User Property</b>: Split users across different paths using User Buckets, enabling split logic based on predefined user segments.</li><li><b>Filtering Journeys by Conditional Split</b>: Quickly find journeys that use Conditional Split directly from the Journeys list page to audit and manage them easily.</li><li><b>Routing Users with Preferred Channel User Property</b>: Branch journeys using Preferred Channel, routing users to Push, Email, SMS, or WhatsApp based on their AI-determined best-performing channel. The Preferred Channel feature is currently released in Private Beta. To enable this feature, contact your Customer Success Manager.</li><li><b>Using Nested User Properties</b>: Use nested user properties when defining Conditional Split conditions to create more advanced routing logic.</li></ul></p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/conditional-split-node" target="_blank">Conditional Split Node</a>.
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="multi-value-arrays-in-custom-event-properties">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#multi-value-arrays-in-custom-event-properties"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Multi-Value Arrays for Custom Event Properties</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>

  <div class="release-note-body">
    <p>You can now send multiple values within a single custom event property using Multi-Value arrays. This helps in modelling richer event data without sending multiple events.</p>

    <p>With a Multi-Value array, you can:</p>
    <p>
      <ul>
        <li>Capture multiple values within a single event property</li>
        <li>Segment audiences using contains and does not contain operators in NextGen Segment Builder</li>
        <li>Personalize campaigns and journeys using Liquid Tags and conditional messaging</li>
        <li>Include up to 100 values per event property</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/events#multi-value-array-for-custom-event-properties" target="_blank">Multi-Value Arrays for Custom Event Properties</a> and <a href="https://developer.clevertap.com/docs/events#adding-multi-value-arrays-to-custom-event-properties" target="_blank">Adding Multi-Value Arrays to Custom Event Properties</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

## February

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="cta-click-and-ctr-insights-for-in-app-messages-and-web-pop-ups">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#cta-click-and-ctr-insights-for-in-app-messages-and-web-pop-ups"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">CTA Click and CTR Insights for In-App Messages and Web Pop-ups</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>

  <div class="release-note-body">
    <p>The Click and CTR reporting for In-App Messages and Web Pop-ups is now enhanced to provide more accurate insights into user engagement. Click and CTR metrics now exclude dismiss and close button interactions, and performance is reported at a CTA level across campaigns.</p>

    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Identify which CTAs drive actual user engagement</li>
        <li>Avoid inflated CTR caused by dismiss actions</li>
        <li>Compare CTA performance within a single message</li>
      </ul>
    </p>

    <p>This enhancement does not apply to Ratings, Lead Generation, or Custom HTML templates.</p>

    <p>Clicks on the close button from February 2, 2026 onward are excluded, which may result in a visible drop in CTR trends.</p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/in-app-campaign-stats?utm_source=vision#view-in-app-campaign-stats" target="_blank">In-App Stats</a> and <a href="https://docs.clevertap.com/docs/web-popup-stats?utm_source=vision#viewing-web-pop-up-campaign-stats" target="_blank">Web Pop-up Stats</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="nested-objects-in-custom-event-properties">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#nested-objects-in-custom-event-properties"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Nested Objects in Custom Event Properties</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>

  <div class="release-note-body">
    <p>You can now model complex event data using Nested Objects in Custom Event Properties, eliminating the need to flatten structured JSON into multiple fields. This simplifies event ingestion while improving targeting accuracy and personalization.</p>

    <p>With Nested Objects in custom event properties, you can:</p>
    <p>
      <ul>
        <li>Store structured entities such as subscriptions, cart items, booking details, and transaction metadata.</li>
        <li>Build precise segments using nested properties in the Segment Builder.</li>
        <li>Personalize campaigns dynamically using Liquid Tags.</li>
        <li>Support up to three levels of nesting.</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/nested-objects-for-user-properties-and-custom-event-properties" target="_blank">Nested Objects</a> and <a href="https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis" target="_blank">Ingesting Nested Objects via CleverTap APIs</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="estimated-reach-for-live-campaigns">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#estimated-reach-for-live-campaigns"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Estimated Reach for Live Campaigns</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>

  <div class="release-note-body">
    <p>You can now view Estimated Reach while configuring Live channel campaigns that include at least one past behavior condition. This gives you visibility into the projected audience size before launch, helping you refine targeting and plan campaigns more effectively.</p>

    <p>Estimated Reach is calculated only for audiences with historical event or property filters (Mini Who criteria) and is not displayed for real-time-only audiences.</p>

    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Preview audience size before activating Live channel campaigns</li>
        <li>Validate historical filters using Mini Who criteria</li>
        <li>Refine segments based on projected campaign scale</li>
        <li>Plan campaigns with greater transparency and confidence</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/create-message-inapp#calculate-estimated-reach" target="_blank">In-App</a>.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="analytics" id="pivots-20">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#pivots-20"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Pivots 2.0</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Pivots 2.0 introduces a redesigned analytics experience that helps teams explore user behavior through interactive tables and visualizations. It enables you to break down large volumes of event data across events, segments, properties, and time to quickly identify patterns, trends, and outliers, without writing complex queries. Pivots 2.0 makes your analysis faster and more intuitive, helping you move from raw data to actionable insights with greater clarity and confidence.</p>
    <p>With Pivots 2.0, you can:</p>
<p>
      <ul>
        <li>Build flexible pivot analyses to explore user behavior across multiple dimensions and time ranges.</li>
        <li>Analyze both frequency-based metrics and value-based event properties to measure engagement, revenue, or consumption.</li>
        <li>Compare metrics using interactive tables, heatmaps, and charts to spot trends and anomalies at a glance.</li>
        <li>Export pivot analysis results in CSV format for offline analysis, reporting, or sharing with external systems.</li>
<li>Bookmark frequently used analyses to revisit key insights without rebuilding queries.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/pivots-v2" target="_blank">Pivots 2.0</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="analytics" id="cohorts-20">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#cohorts-20"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Cohorts 2.0</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Cohorts 2.0 introduces a redesigned approach to analyze user behavior over time. It helps you group users into time-based cohorts and tracks retention, frequency, and re-engagement across days, weeks, or months. This makes it easier to understand long-term engagement, identify drop-off points, and evaluate lifecycle performance so you can optimize retention strategies with greater confidence.</p>
    <p>With Cohorts 2.0, you can:</p>
<p>
      <ul>
        <li>Build flexible cohort analyses using configurable start and return events to define user lifecycle stages.</li>
        <li>Measure different engagement patterns with multiple analysis types, including exact-day retention, cumulative retention, and return frequency.</li>
        <li>Compare retention behavior across segments, properties, and regions to identify high and low-performing cohorts.</li>
        <li>Analyze both retention rates and value-based metrics, such as total events, events per user, or aggregated event properties.</li>
<li>Visualize cohort performance using detailed cohort tables and interactive trend lines for clearer comparisons over time.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/cohorts-v2" target="_blank">Cohorts 2.0</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="analytics" id="advanced-formula-based-measurement-in-trends-20">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#advanced-formula-based-measurement-in-trends-20"><i class="fa-light fa-anchor"></i></a>
    </div>

    <div>
      <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" class="release-note-heading-icon" />
    </div>

    <h3 class="release-note-heading">Advanced Formula-Based Measurement in Trends 2.0</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">BETA</div>
  </div>

  <div class="release-note-body">
    <p>Trends 2.0 now offers powerful formula-based measurement, allowing you to create custom business metrics directly within your trend analysis. Beyond standard measures like Total Events, Unique Users, and Average Per User, you can combine event and property-level functions using mathematical expressions to track derived KPIs over time. 
</p>
    <p>With the Formula option, you can:</p>

    <p>
      <ul>
        <li>Build custom metrics such as revenue per user, conversion ratios, or value per event.</li>
        <li>Combine functions like TOTALS, UNIQUES, and PROPSUM using mathematical operators.</li>
        <li>Compare up to four formulas in a single chart for side-by-side KPI analysis.</li>
        <li>Use clear Y-axis titles to present stakeholder-friendly metrics.</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/trends-v2#formula" target="_blank">Formula</a>.</p>
  </div>

  <hr />
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="journeys" id="journey-tracking-with-multiple-campaign-ids">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#journey-tracking-with-multiple-campaign-ids"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" /></div>
    <h3 class="release-note-heading">Journey Tracking with Multiple Campaign IDs</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>When multiple paths converge at a journey engagement node, the node now displays all associated campaign IDs. This ensures accurate analytics, user discovery, and reporting across Analytics, Find People, and user downloads.</p>
    <p>With this enhancement, you can: <ul><li>Analyze users reached through specific journey paths. </li><li>Search for users using campaign-based filters in Find People.</li><li>Download user lists for reporting.</li><li>Reconcile Journey node statistics with Analytics data.</li></ul></p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/engagement-stats" target="_blank">Engagement Stats</a>.
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="api-encryption">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#api-encryption"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">API Encryption</h3>
<div class="badge new-feature">NEW FEATURE</div>
  </div>

  <div class="release-note-body">
    <p>You can now secure sensitive API data with payload-level Encryption. This feature encrypts API request and response payloads end-to-end using Hybrid Public Key Encryption (HPKE), adding an extra layer of protection beyond HTTPS/TLS, without changing existing APIs, schemas, limits, or response formats.</p>

    <p>With API Encryption, you can:</p>
    <p>
      <ul>
        <li>Encrypt API requests and responses end-to-end while in transit to prevent exposure of sensitive PII.</li>
        <li>Adopt encryption incrementally with header-based, per-request control and zero downtime.</li>
        <li>Retain full ownership of private keys, which never leave your environment.</li>
        <li>Meet security and regulatory requirements for compliance-driven industries.</li>
      </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/api-encryption" target="_blank">API Encryption</a> and <a href=\"https://developer.clevertap.com/docs/api-encryption" target=\"_blank\"> API Encryption - Reference.</p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

## January

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="delivery-delay-for-in-app-messages">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#delivery-delay-for-in-app-messages"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Delivery Delay for In-App Messages</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>You can now delay displaying In-App messages using delivery preferences. Instead of showing messages immediately at app launch, you can delay delivery by up to 20 minutes, to ensure messages appear at the right moment.</p>
    <p>This enhancement helps reduce disruption and improve engagement for the In-App messages without requiring any developer effort. This feature is now available on Android SDK v7.7.1+ and iOS SDK v7.4.0+ for select customers.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/create-message-inapp#in-app-delay" target="_blank">In-App Delay</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="product-experiences" id="product-experiences-a/b-test-updates">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#product-experiences-a/b-test-updates"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/d7de531a1060998537a4e71a078198cf28076d99e1aed3e3c1bdcb5509e29d95-Product_experiences.svg" alt="Product Experiences" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Product Experiences A/B Test Updates</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>A/B testing in Product Experiences can now help you perform more accurate and flexible pre-launch validations. With this enhancement, teams can now test A/B variants at the device level and run multiple A/B tests simultaneously before publishing A/B Tests.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/device-previews-for-ab-tests" target="_blank">Device Previews for A/B Tests</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="personalized-cta-button-text-for-in-app-messages">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#personalized-cta-button-text-for-in-app-messages"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Personalized CTA Button Text for In-App Messages</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>You can now personalize CTA button text across all In-App message templates using user preferences and Liquid Tags. This ensures CTAs adapt to each user’s context and attributes.</p>
    <p>With this enhancement, you can increase engagement and drive better conversions through more relevant and localized CTAs.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/preview-and-send-in-app" target="_blank">Inline Personalization in In-Apps</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="rich-media-support-for-the-advanced-in-app-builder-and-web-pop-ups">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#rich-media-support-for-the-advanced-in-app-builder-and-web-pop-ups"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Rich Media Support for the Advanced In-App Builder and Web Pop-ups</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>In-Apps created with the Advanced In-App Builder now support rich media formats, such as videos, GIFs, and images, allowing you to create more dynamic and immersive In-App experiences. Web Pop-ups also support embedding rich media. You can now upload and embed media alongside text and buttons directly within the builder, without additional setup.</p>
    <p>This enhancement empowers teams to craft visually engaging content that drives user interaction and brand engagement.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/advanced-in-app-builder" target="_blank">Advanced In-App Builder</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="preview-and-test-all-in-app-message-templates">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#preview-and-test-all-in-app-message-templates"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Preview and Test All In-App Message Templates</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>You can now preview and test all In-App message templates, including messages built using Advanced In-App Builder and Custom HTML, directly from the CleverTap dashboard. Instead of sending test messages, you can now preview personalized messages using user or event properties, or enter custom values to view exactly how messages render. This enhancement ensures faster validation, fewer personalization errors, and a consistent preview experience across all In-App templates.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/preview-and-send-in-app" target="_blank">Preview and Test In-App Messages</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-and-project-settings" id="scim-support-for-automated-user-lifecycle-management">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#scim-support-for-automated-user-lifecycle-management"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img 
src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" />
    </div>
    <h3 class="release-note-heading">SCIM Support for Automated User Lifecycle Management</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>

  <div class="release-note-body">

    <p>You can now automate user provisioning and de-provisioning in CleverTap with SCIM (System for Cross-domain Identity Management). SCIM simplifies onboarding, offboarding, and lifecycle management by ensuring that users always have the right access. CleverTap supports SCIM configuration via both APIs and Identity Providers (IdPs), giving you flexibility based on your IT and security setup.
</p>

    <p>With SCIM, you can:</p>
    <p>
      <ul>
        <li>Provision users automatically into CleverTap as soon as they are added to your identity system.</li>
        <li>Revoke access immediately when users leave, critical for BFSI and regulated environments.</li>
        <li>Keep user roles, access levels, and statuses always in sync with your corporate directory.</li>
        <li>Reduce human error, support audits, and align with enterprise access governance policies.</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://developer.clevertap.com/docs/scim-user-provisioning-using-api" target="_blank">SCIM User Provisioning using API</a> and <a href=\"https://developer.clevertap.com/docs/scim-user-provisioning-using-idp" target=\"_blank\"> SCIM User Provisioning using IdP.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="promotions" id="promo-campaign-analytics">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#promo-campaign-analytics"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/c65a9fbb8af21c3a8f01c546faa2089d52a3bf54c2efecc740879b1ea681242e-Property_1Selected.svg" alt="Promotions" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Promo Campaign Analytics</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge beta">BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Introducing Promo Campaign Analytics, a powerful new way to measure the performance of your Promo Campaigns across rewards, engagement, and errors. This helps you evaluate campaign effectiveness, identify high-performing reward types, and optimize ROI through improved visibility into user engagement and system performance. Promo Analytics provides you with complete visibility into what’s working, what’s failing, and why, enabling you to optimize campaign performance with confidence.</p>
    <p>With Promo Campaign Analytics, you can:</p>
    <p>
      <ul>
        <li>Track Rewards Distributed, Points/Coupons/Vouchers issued, and Redemptions through clear KPIs.</li>
        <li>Visualize time-based trends using interactive charts aggregated by day, week, or month.</li>
        <li>View reward-type–specific metrics for Loyalty Points, Coupons (Discount & Cashback), Partner Vouchers, and Custom Rewards.</li>
        <li>Identify errors in reward distributions across all reward types.</li>
<li>Understand failures caused by limits, configuration issues, exhausted codes, or system errors.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href=" https://docs.clevertap.com/docs/promo-campaign-stats" target="_blank">Promo Campaign Analytics</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="journeys" id="cross-project-cloning-for-engagements">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#cross-project-cloning-for-engagements"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" /></div>
    <h3 class="release-note-heading">Cross-Project Cloning for Engagements</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>You can now clone campaigns and journeys across CleverTap projects, allowing teams to move faster without rebuilding engagement logic from scratch. Cross-Project Cloning lets you reuse proven campaigns and journeys across test, production, and multiple business-unit projects, directly from the Campaigns or Journeys list page.</p>
    <p>This enhancement is especially useful during onboarding (you can copy engagement from the test project to production) and for scaling successful engagement workflows across regions or lines of business.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/copy-engagements-across-projects" target="_blank">Copy Engagement Across Projects</a>.
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="data-and-integrations" id="profile-export-for-cloud-storage">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#profile-export-for-cloud-storage"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/bf86621cc6be2995b3a9323ccfcaae0e172d6da76b2bfedc7983c5be75eb179d-Partners_Icon_Outlined.svg" alt="data-and-integrations" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Profile Export for Cloud Storage</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>Introducing Profile Export for S3, GCP, and Azure, an upgrade that improves how profile data is exported from CleverTap to cloud storage destinations. This enhancement provides you with greater control over the export structure and schema, helping to keep data lakes organized and downstream pipelines stable.</p>
    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li>Keep exports organized and easy to consume with custom subfolders, your own file naming, and Parquet output (with no additional compression), ensuring clean storage and predictable ingestion.</li>
        <li>Match exports to your audience and identity strategy with flexible identifier selection (Email, Phone, CleverTap ID, or a custom identity property). You can also include Communication Preferences, with the option to export Subscription Groups alongside other preference flags, reducing downstream remapping and errors.</li>
        <li>Protect downstream pipelines from unexpected changes by selecting the exact profile properties you want to export, renaming and ordering them for consistency, and enabling schema locking to prevent newly added properties from disrupting existing flows.</li>
        <li>Automate daily delivery with recurring exports (every 24 hours) and choose whether each run is incremental or a full dataset refresh, based on the requirements of your team.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/profile-exports" target="_blank">Profile Exports.</a></p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="redesign-of-campaign-listing-page">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#redesign-of-campaign-listing-page"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Redesign of Campaign Listing Page</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>

  <div class="release-note-body">
    <p>
      You can now experience the redesigned Campaign Listing page, built for faster performance and improved usability.
      This enhancement streamlines campaign management and brings key insights to the forefront.
    </p>

    <p>With this enhancement, you can:</p>

    <ul>
      <li>Experience faster page load times for a smoother workflow.</li>
      <li>Configure columns by adding, removing, or reordering fields to suit your view.</li>
      <li>View campaign channels and engagement rate formulas upfront for quick insights.</li>
      <li>Filter Bulletin and API campaigns separately for better navigation.</li>
      <li>Adjust stats duration easily with advanced filtering options.</li>
    </ul>

    <p>
      For more information, refer to
      <a href="https://docs.clevertap.com/docs/enhanced-campaign-list-page" target="_blank">Campaign Overview</a>.
    </p>
  </div>

  <hr/>
</div>
`}</HTMLBlock>

# 2025

## December

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="branded-domains-for-email-tracking">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#branded-domains-for-email-tracking"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Branded Domains for Email Tracking</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>You can now use your custom domain for email link tracking and open-tracking pixel. This ensures all tracked links reflect your brand instead of a default CleverTap domain. </p>
    <p>This feature helps with the following:</p>
    <p>
      <ul>
        <li>Improves deliverability by aligning tracking domains with your SPF/DKIM authentication.</li>
        <li>Tracks email opens and clicks more reliably using branded links.</li>
        <li>Keeps campaigns running with automatic fallback if a custom domain becomes unverified.</li>
<li>Manages branded domains centrally from a single place in your dashboard.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/branded-domain" target="_blank">Branded Domains</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="template-import-for-whatsApp-connect-providers">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#template-import-for-whatsApp-connect-providers"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
   </div>
    <h3 class="release-note-heading">Template Import for WhatsApp Connect Providers</h3>
<div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge beta">BETA</div>
  </div>
  <div class="release-note-body">
    <p>You can now import WhatsApp message templates directly from your WhatsApp Connect providers into CleverTap, eliminating the need to recreate templates manually. This enhancement helps reduce setup time and prevents configuration errors when managing WhatsApp templates at scale.</p>

    <p>With this update, you can:</p>
    <p>
      <ul>
        <li>Import templates seamlessly from supported WhatsApp Connect providers during provider setup. Templates are fetched directly from the vendor using their template import API, with all required fields populated automatically.</li>
        <li>Ensure consistency and compliance by importing templates that follow Meta’s approved template format, reducing the risk of formatting or field mismatches.</li>
<li>Accelerate onboarding and scaling by leveraging vendor-provided API endpoints, authentication details, import limits, and click-tracking configuration.</li>
      </ul>
    </p>
<p>For more information, refer to<a href="https://docs.clevertap.com/docs/generic-whatsapp#import-templates" target="_blank">WhatsApp Message Templates.</a></p>

  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="whatsapp-template-cloning-and-enhanced-editing">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#whatsapp-template-cloning-and-enhanced-editing"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
   </div>
    <h3 class="release-note-heading">WhatsApp Template Cloning and Enhanced Editing</h3>
<div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge beta">BETA</div>
  </div>
  <div class="release-note-body">
    <p>You can now create and manage WhatsApp Direct message templates faster with new cloning and rich editing options. These enhancements help you maintain consistency across WhatsApp Business Accounts (WABAs) and reduce time spent recreating or reformatting templates.</p>

    <p>With these enhancements, you can:</p>
    <p>
      <ul>
        <li>Clone templates easily by duplicating any existing template within the same or another WABA configured with WhatsApp Direct. All fields are pre-filled, so you can rename, edit content, and resubmit for approval without rebuilding the template.</li>
        <li>Edit templates with rich formatting using bold, italics, strikethrough, and emojis to create clear, expressive messages aligned with WhatsApp formatting rules.</li>
      </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/whatsapp-message-templates" target="_blank">WhatsApp Message Templates.</a></p>

  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="pii-tokenization">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#pii-tokenization"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">PII Tokenization</h3>
<div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>You can now protect sensitive user data by ensuring that Personally Identifiable Information (PII) never enters CleverTap’s environment. Instead of sending identifiers such as email addresses or phone numbers, you send tokens that map securely to your own vault. CleverTap then processes only tokens for Segments, Engagements, and Analytics, keeping all personal data fully within your control.</p>
<p>With PII Tokenization, you can:</p>
    <p>
      <ul>
        <li><strong>Protect Sensitive Data:</strong> Replace PII with tokens to comply with data privacy and residency regulations.</li>
        <li><strong>Choose Your Vault Model:</strong> Use CleverTap Vault or bring your own for flexibility.</li>
        <li><strong>Simplify Integration:</strong> Generate and manage tokens using the Vault API for seamless client-side setup.</li>
        <li><strong>Control Dispatch Models:</strong> Run the Dispatcher On-Prem (no PII leaves your environment) or Off-Prem (secure, token-only resolution at send time).</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/pii-tokenization" target="_blank">PII Tokenization</a>.</p>
</div>
<hr/>
</div>
`}</HTMLBlock>

## November

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="automated-audit-log-exports-for-siem">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#automated-audit-log-exports-for-siem"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Automated Audit Log Exports for SIEM</h3>
<div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
     <p>You can now securely export audit logs from CleverTap to your own cloud storage providers, including AWS S3, Google Cloud Storage, or Microsoft Azure Blob Storage. This self-serve feature allows you to easily manage, store, and retain audit data within your own cloud environment.</p>
    <p>With SIEM Export, you can:</p>
<p>
  <ul>
    <li><strong>Automate Secure Delivery:</strong> Receive exports every 4 hours in JSON (UTF-8) format.</li>
    <li><strong>Ensure Continuous Visibility:</strong> Monitor all account activities in real time to strengthen compliance and security posture.</li>
    <li><strong>Maintain Full Data Control:</strong> Store audit logs directly within your organization’s cloud to manage retention and governance.</li>
    <li><strong>Integrate Seamlessly with SIEM Tools:</strong> Combine CleverTap’s audit data with broader operational insights across your systems.</li>
  </ul>
</p>

<p>For more information, refer to <a href="https://docs.clevertap.com/docs/automated-audit-log-exports-for-siem" target="_blank">Automated Audit Log Exports for SIEM</a>.</p>
</div>
<hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="whatsapp-flows-for-whatsapp-direct">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#whatsapp-flows-for-whatsapp-direct"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">WhatsApp Flows for WhatsApp Direct</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Introducing WhatsApp Flows, a form-based experience that lets your users complete tasks such as booking a ticket or placing an order without leaving WhatsApp. CleverTap handles orchestration, analytics, and automation. Flows are created at the WhatsApp Business Account level and appear as a call-to-action button in your message. Tapping the button opens a guided, structured journey that follows Meta’s Flows specification.</p>
    <p>With WhatsApp Flows, you can:</p>
<p>
      <ul>
        <li><strong>Choose Your Setup</strong>: Use static flows, a CleverTap endpoint with customer relay, or your own endpoint for full control.</li>
        <li><strong>
Protect Data End to End</strong>: Keep payloads encrypted on the device and decrypt or re-encrypt according to the selected setup.</li>
        <li><strong>Capture Outcomes in CleverTap</strong>: Record Flow events for reporting and update profile attributes for personalization and segmentation.</li>
        <li><strong>Use Templates Seamlessly</strong>: Attach a Flow to a WhatsApp template, personalize message content, and publish in campaigns.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/whatsapp-flows" target="_blank">WhatsApp Flows.</a></p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="preferred-channel-for-engagement">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#preferred-channel-for-engagement"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
     <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" />
    </div>
    <h3 class="release-note-heading">Preferred Channel for Engagement</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>

  <div class="release-note-body">
    <p>You can now deliver messages through the channel each user is most likely to engage with. Powered by CleverAI, Preferred Channel analyzes engagement data across Push, Email, SMS, and WhatsApp over the past 90 days to predict and select the best-performing communication channel for every user.</p>

    <p>With Preferred Channel, you can:</p>

    <p>
      <ul>
        <li><strong>Leverage AI-Powered Channel Prediction</strong>: Identify the most effective communication channel for each user based on engagement history.</li>
        <li><strong>Integrate Seamlessly Across CleverTap</strong>: Use the new Preferred Channel user property in Segmentation, Campaigns, Journeys, and Analytics.</li>
        <li><strong>Boost Conversions and Reduce Noise</strong>: Focus on the channels that drive real engagement and results.</li>
        <li><strong>Automate Channel Selection</strong>: Let CleverAI optimize delivery so you can focus on content and strategy.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/preferred-channel" target="_blank">Preferred Channel</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="journeys" id="conditional-split-in-journeys">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#conditional-split-in-journeys"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" /></div>
    <h3 class="release-note-heading">Conditional Split in Journeys</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>You can now use Conditional Split, a new controller node that enables you to branch users based on user properties, event properties, or both. This helps teams make faster decisions, reduce journey complexity, and drive higher conversions through more targeted, personalized paths.</p>
    <p>With Conditional Split, you can:<ul><li>Route users by user or event properties for instant, context-aware decisions.</li><li>Use AND/OR operators to create precise, multi-condition logic.</li><li>Ensure unmatched users continue through a fallback path.</li><li>Chain up to three Nested Splits to design richer, multi-layer workflows.</li>View Path Stats to understand how users are distributed across each branch.</li></ul></p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/conditional-split-node" target="_blank">Conditional Split Node</a>.
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="field-level-at-rest-encryption-for-user-and-event-properties">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#field-level-at-rest-encryption-for-user-and-event-properties"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Field-Level at Rest Encryption for User and Event Properties</h3>
<div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
     <p>CleverTap now supports Field-Level at Rest Encryption, enabling you to encrypt user and event properties for stronger data protection. This capability extends beyond the existing volume-level encryption, providing granular control over how sensitive data, including system and user properties, is secured within the platform.</p>
    <p>With this capability, you can:</p>
    <p>
      <ul>
        <li><strong>Protect Sensitive Fields:</strong> Selectively encrypt both user and event properties while keeping the rest of your data accessible for Analytics.</li>
        <li><strong>Choose Your Key Strategy:</strong> Use CleverTap-managed keys or Bring Your Own Keys (BYOK) encryption through AWS KMS.</li>
        <li><strong>Enable Encryption Easily:</strong> Apply encryption to the properties directly from the Schema page.</li>
        <li><strong>Maintain Platform Compatibility:</strong> Ensure that encrypted fields continue to work seamlessly across Segments, Campaigns, and Analytics for authorized users.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/field-level-at-rest-encryption" target="_blank">Field-Level at Rest Encryption</a>.</p>
</div>
<hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="bring-your-own-key-byok-for-encryption">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#bring-your-own-key-byok-for-encryption"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Bring Your Own Key (BYOK) for Encryption</h3>
<div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now supports Bring Your Own Key (BYOK), enabling you to use your organization’s own AWS KMS–managed encryption keys for securing data across the platform.</p>
    <p>With this capability, you can:</p>
    <p>
      <ul>
        <li><strong>Enforce Customer-Controlled Encryption:</strong> Protect data during file uploads using your keys within AWS KMS.</li>

       <li><strong>Meet Enterprise Compliance Requirements:</strong> Maintain strict governance, auditability, and alignment with regulated industry standards.</li>

 <li><strong>Enable Seamless Key Rotation:</strong> Update CleverTap encryption to align with your KMS rotation callbacks, without impacting ongoing services.</li>

<li><strong>Ensure Secure Integration:</strong> Retrieve keys securely over HTTPS on TLS 1.2. CleverTap never stores or persists customer keys; only metadata, such as key name and version, is stored.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/bring-your-own-key-byok-encryption" target="_blank">BYOK Encryption</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-and-project-settings" id="teams-structured-collaboration-with-enhanced-governance">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#teams-structured-collaboration-with-enhanced-governance"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Security & Project Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Teams: Structured Collaboration with Enhanced Governance</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>
  <div class="release-note-body">
    <p>Introducing Teams, a new way to organize and secure collaboration within CleverTap. Teams let you group users and information according to your organization’s structure, ensuring each team accesses only relevant data. This improves visibility, control, and data governance across large operations.</p>
    <p>With Teams, you can:</p>
    <p>
      <ul>
        <li>View and manage only the campaigns, templates, and data owned by your team.</li>
        <li>Define teams, assign users, and configure event-level access aligned with your business hierarchy.</li>
        <li>Work within a clean, focused team view and switch between teams seamlessly.</li>
        <li>Use API support for Campaign, Custom List Segment, and Email Template APIs.</li>
      </ul>
    </p>
    <p>Teams prevent cross-team data overlap, ensuring integrity, security, and operational efficiency across your organization.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/teams-setup" target="_blank">Teams Setup</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="content-manager" id="bulk-upload-for-geofences">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#bulk-upload-for-geofences"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/0ed57ff4730974458d74d2a34ec4cf285aa5e84f59075a6b32550b9d1fd60ae8-Content_Manager.svg" alt="Content Manager" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Bulk Upload for Geofences</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>
  <div class="release-note-body">
    <p>You can now add multiple geo clusters and fences simultaneously using CSV or JSON files, enabling faster and more efficient setup of large-scale, location-based campaigns. Previously, each cluster and fence had to be added manually — a time-consuming process for campaigns involving hundreds of store locations or regions.</p>
    <p>With Bulk Upload, you can manage up to 10,000 radius-based geofences effortlessly, streamlining campaign setup for multi-location businesses.</p>
    <p>Key benefits include:</p>
    <p>
      <ul>
        <li>Faster setup: Upload multiple clusters and fences in a single step.</li>
        <li>Operational efficiency: Eliminate repetitive manual entry and reduce errors.</li>
        <li>Scalable targeting: Seamlessly manage large-scale, region-based campaigns.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/geofencing-campaign-1#bulk-upload" target="_blank">Bulk Upload</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="rcs-business-messaging-with-generic-provider-support">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#rcs-business-messaging-with-generic-provider-support"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">RCS Business Messaging with Generic Provider Support</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>You can now connect CleverTap with your preferred RCS provider through a simple configuration, keeping all orchestration, analytics, and automation in one place.</p>
    <p>With this feature, you can:</p>
    <p>
      <ul>
        <li>Bring your own RCS provider with a generic configuration.</li>
        <li>Drive engagement with rich media and two-way interactions that trigger campaigns and journeys.</li>
        <li>Maximize reach with automatic SMS fallback and dedicated RCS metrics for delivery, view, and click.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/generic-rcs" target="_blank">Generic RCS</a> and<a href="https://developer.clevertap.com/docs/generic-rcs-api" target="_blank"> Generic RCS API</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="journeys" id="edit-a-journey">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#edit-a-journey"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div><img src="https://files.readme.io/51dc269788d03bb7bc0482fbc020414bedd96b6c778ac37b71884095493b93c8-Journeys.svg" alt="Journeys" /></div>
    <h3 class="release-note-heading">Edit a Journey</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>You can now edit a journey even after it is published. You can make any changes, from updating entry criteria and adjusting wait times to tweaking messages or removing nodes.</p>
    <p>Every edit is tracked through version control. You can view the history of changes, compare performance across versions, and see how each update impacts engagement. This feature gives your team the flexibility to fix errors, test new strategies, and refine targeting in real-time, ensuring a seamless user experience.</p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/edit-a-journey" target="_blank">Edit a Journey</a>.
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="end-to-end-pii-encryption-in-transit-for-sdks">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#end-to-end-pii-encryption-in-transit-for-sdks"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">End-to-End PII Encryption in Transit for SDKs</h3>
<div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now offers enhanced encryption of all PII and sensitive data in transit between SDKs and backend servers.</p>

    <p>With this enhancement, you can:</p>
    <p>
      <ul>
        <li><strong>Ensure Secure Data Exchange:</strong> Encrypt all PII data transmitted from SDKs using AES-256 encryption, safeguarding against Man in the Middle attacks.</li>
        <li><strong>Prevent Network-Level Threats:</strong> Protect all SDK communication from man-in-the-middle (MITM) and data interception attempts, maintaining confidentiality throughout transmission.</li>
        <li><strong>Maintain Compliance Readiness:</strong> Meet financial-grade encryption standards and align with industry standards and enterprise security mandates, supporting fintech and other data-sensitive use cases.</li>
        <li><strong>Simplify Implementation:</strong> Manage encryption and decryption within the SDK, ensuring seamless, cross-platform protection across Android, iOS, Web, Cordova, Flutter, and React Native.</li>
      </ul>
    </p>
  <p>For more information, refer to <a href="https://developer.clevertap.com/docs/android-advanced-features#encryption-in-transit" target="_blank">Android</a>,
    <a href="https://developer.clevertap.com/docs/advanced-options-ios#encryption-of-pii-data" target="_blank">iOS</a>, <a href="https://developer.clevertap.com/docs/advanced-configurations#encryption-of-pii-data" target="_blank">Web</a>, <a href="https://developer.clevertap.com/docs/cordova-advance-features#encryption-for-pii-data" target="_blank"> Cordova</a>,<a href="https://developer.clevertap.com/docs/flutter-advanced-features#encryption-for-pii-data" target="_blank"> Flutter</a>, and <a href="https://developer.clevertap.com/docs/react-native-advanced-features#encryption-for-pii-data" target="_blank"> React Native</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

## October

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="improved-notification-controls-for-android-push">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#improved-notification-controls-for-android-push"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
   </div>
    <h3 class="release-note-heading">Improved Notification Controls for Android Push</h3>
<div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge beta">BETA</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now offers enhanced control over Android push notifications, so you can customize how they appear, persist, and are dismissed. You can now deliver timely, high-priority messages that remain visible and reach users when they matter most.</p>

    <p>With these Notification controls, you can:</p>
    <p>
      <ul>
        <li><strong>Define Notification Behavior:</strong> Choose between Regular notifications, which are cleared when users tap “clear all”, and Sticky notifications that remain visible even after a bulk clear. Use Sticky notifications to ensure critical alerts or reminders remain visible to users.</li>
        <li><strong>Customize Notification Dismissal:</strong> Decide whether notifications should be dismissed manually by users or automatically after a set duration (up to 24 hours), ideal for limited-time offers, flash sales, or event reminders with precision.</li>
      </ul>
    </p>
    <p>These updates are available from Android version 14 and above, for Android SDK v7.6.0, and Push Templates SDK v2.2.0 and above.</p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/push-editor#notification-behavior" target="_blank">Notification Behavior</a> and<a href="https://docs.clevertap.com/docs/push-editor#dismiss-notification" target="_blank"> Dismiss Notification</a>.</p>

  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="nested-objects-in-custom-user-properties">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#nested-objects-in-custom-user-properties"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Nested Objects in Custom User Properties</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>Introducing Nested Objects in Custom User Properties, a powerful feature that simplifies how you represent and ingest complex user data in CleverTap. Define rich, structured entities such as insurance policies, subscriptions, or shopping carts using a JSON  eliminating the need to flatten data or manage multiple attributes across systems.</p>
    <p>With Nested Objects, you can:</p>
    <p>
      <ul>
        <li>Model structured user data natively within CleverTap, preserving relationships between entities.</li>
        <li>Build granular, condition-based segments using nested attributes (for example, filter users with a policy missing a beneficiary email).</li>
        <li>Simplify engineering workflows through direct JSON ingestion without additional data transformation.</li>
        <li>Visualize and filter nested data within Segment builder, unlocking deeper insights for marketers and analysts.</li>
      </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/nested-objects" target="_blank">Nested Objects</a> and<a href="https://developer.clevertap.com/docs/ingesting-nested-objects-via-clevertap-apis" target="_blank"> Ingesting Nested Objects via CleverTap APIs</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="secure-file-uploads-through-sftp-encryption">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#secure-file-uploads-through-sftp-encryption"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Secure File Uploads through SFTP Encryption</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now supports encrypted file uploads via SFTP, ensuring that all data ingested through the SFTP pipeline remains secure and compliant with data protection standards. You can safely transfer sensitive customer data using end-to-end PGP encryption and manage encryption keys flexibly.</p>
    <p>With SFTP Encryption, you can:</p>
    <p>
      <ul>
        <li>Protect all file transfers using PGP encryption.</li>
        <li>Choose between CleverTap-managed or customer-managed encryption keys.</li>
        <li>Continue using your existing ingestion workflows without disruption.</li>
        <li>Strengthen compliance and audit readiness for enterprise-grade security.</li>
      </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/file-upload-encryption" target="_blank">File Upload Encryption</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="role-based-channel-level-access-for-campaigns-and-journeys">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#role-based-channel-level-access-for-campaigns-and-journeys"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" />
    </div>
    <h3 class="release-note-heading">Role-Based Channel-Level Access for Campaigns and Journeys</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>Role-Based Channel-Level Access enables admins to precisely control who can view or manage each messaging channel within Campaigns and Journeys. With channel-specific permissions defined by Admins, users can only see and work on the channels they are responsible for, such as Push, Email, SMS, Web Push, or App Inbox, and so on. </p> <p>The following key features are included in this release:
</p>
    <ul>
      <li><strong>Granular Permissions</strong>: Assign channel-level read or write access within Campaigns and Journeys.</li>
      <li> <strong>Governance at Scale</strong>: Prevent accidental edits by limiting control to authorized users.</li>
      <li> <strong>Multi-Team Support</strong>: Allow business units to manage their own channels independently.</li>
    </ul>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/role-based-access-control-advance-governance#engagement-permissions" target="_blank">Engagement Permissions</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="role-based-privileges-for-global-campaign-and-throttle-limits">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#role-based-privileges-for-global-campaign-and-throttle-limits"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Role-Based Privileges for Global Campaign and Throttle Limits</h3>
    <div class="badge new-feature">NEW FEATURE</div>
  </div>
  <div class="release-note-body">
    <p>We have added a new layer of governance to help teams manage communication frequency and scale, with role-based control over <strong>Global Campaign Limits</strong> and <strong>Global Throttle Limits</strong>.</p>
    <p>Admins can now define who can override Campaign and Throttle Limit settings based on user roles. With this feature, you can prevent over-communication, enable fine-grained control, extend support to Journeys, and retain backward compatibility.</p>
    
    For more information, refer to the <a href="https://docs.clevertap.com/docs/role-based-access-control-advanced-governance-limits" target="_blank">Setup Roles</a> and <a href="https://docs.clevertap.com/docs/campaign-permissions" target="_blank">Campaign Permissions</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="custom-conversion-window">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#custom-conversion-window"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">Custom Conversion Window</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>
  <div class="release-note-body">
    <p>Introducing Custom Conversion Window, an enhancement to Campaigns and Journeys that gives marketers precise control over conversion tracking. You can now define custom conversion durations, from 1 minute to 5 months, instead of being limited to fixed options like 7 or 14 days. This enhancement brings greater flexibility, accuracy, and consistency, helping marketers align conversion measurement with real user behavior.</p>
    <p>With Custom Conversion Window, you can:</p>
    <p>
      <ul>
        <li>Track conversions accurately by aligning the window with your business cycle (for example, 10 days for e-commerce purchases, 72 hours for flash sales).</li>
        <li>Improve ROI accuracy by removing undercounting or overcounting from preset durations.</li>
        <li>Maintain consistency across reports and dashboards with unified data tracking.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/create-message-push" target="_blank">Create Message</a> and<a href="https://docs.clevertap.com/docs/push-campaign-stats" target="_blank"> Stats</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<div class="release-note article" data-category="analytics" id="ai-powered-nps-feedback-analysis">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#ai-powered-nps-feedback-analysis">
        <i class="fa-light fa-anchor" />
      </a>
    </div>

    <div>
      <img src="https://files.readme.io/f57aa9f8ef374b2652d21d86c7251de0e10d2f8661a4828202bcced4cb299d5f-Analytics.svg" alt="Analytics" class="release-note-heading-icon" />
    </div>

    <h3 class="release-note-heading">AI-Powered NPS Feedback Analysis</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div>
  </div>

  <div class="release-note-body">
    <p>The NPS Board now offers AI-powered insights that transform raw feedback into actionable sentiment analysis. Beyond numeric scores, you can instantly understand what customers feel and why, helping your teams act faster on key feedback themes.</p>
    <p>With this enhancement, you can:</p>

    <p>
      <ul>
        <li>Generate instant AI summaries of NPS responses, highlighting key insights.</li>
        <li>Identify key themes with positive, negative, or neutral sentiment indicators.</li>
        <li>Visualize frequently mentioned terms using an AI-generated word cloud.</li>
        <li>Track sentiment trends over time using daily, weekly, or monthly intervals..</li>
      </ul>
    </p>

    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/nps-board-1" target="_blank">NPS Board</a>.</p>
  </div>

  <hr />
</div>

<HTMLBlock>{`
<div class="release-note article" data-category="security-project-settings" id="end-to-end-encryption-for-cpaas-communication">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#end-to-end-encryption-for-cpaas-communication"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/01053ed2e833c5e6bb242a86b84f304b7499ff0b0a26f422c3cc846d70530658-Settings.svg" alt="Settings" />
    </div>
    <h3 class="release-note-heading">End-to-End Encryption for CPaaS Communication</h3>
    <div class="badge new-feature">NEW FEATURE</div>
    <div class="badge ga">GA</div>
  </div>
  <div class="release-note-body">
    <p>CleverTap now supports end-to-end encryption for all CPaaS communications over Email and SMS via the Generic HTTP API configuration. This feature ensures every payload and callback is encrypted using AES-256, securing PII data such as email addresses and phone numbers.</p>
<p>With CPaaS Encryption, you can:</p>
    <p>
      <ul>
        <li>Protect outbound and inbound data with end-to-end encryption.</li>
        <li>Meet enterprise security and compliance requirements, and now meet BFSI-grade compliance requirements while maintaining performance and scalability.</li>
        <li>Enable encryption with a single toggle in the provider setup under Generic HTTP API configuration, supporting both CleverTap-managed and customer-managed keys (BYOK).</li>
        <li>Scale seamlessly across providers via the Generic HTTP API.</li>
        <li>Manage key versioning and rotation without service disruption.</li>
      </ul>
    </p>
<p>For more information, refer to <a href="https://docs.clevertap.com/docs/cpaas-encryptions" target="_blank">CPaaS Encryption</a>.</p>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="promotions" id="new-in-promotions-custom-rewards">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#new-in-promotions-custom-rewards"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/c65a9fbb8af21c3a8f01c546faa2089d52a3bf54c2efecc740879b1ea681242e-Property_1Selected.svg" alt="Promotions" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">New in Promotions: Custom Rewards</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
    <div class="badge private-beta">PRIVATE BETA</div> 
  </div>
  <div class="release-note-body">
    <p>Introducing Custom Rewards, a significant expansion of CleverTap’s Promo capabilities.
You can now create, host, and manage your own rewards within CleverTap promo and distribute it to tailored user segments through Promo campaigns. From physical and digital rewards (branded merchandise or OTT subscriptions) to self-managed wallets hosted on your end (real-money cashback or loyalty credits) you can do a webhook-based fulfillment to your systems.</p>
    <p>With Custom Rewards, you can:</p>
    <p>
      <ul>
        <li>Orchestrate personalized reward campaigns at scale by offering cashback in your hosted wallet for repeat buyers or issuing gift vouchers to users who achieve a milestone.</li>
        <li>Support diverse engagement use cases such as loyalty programs, event-based rewards, or promotional credits, without relying on fixed, built-in reward types.</li>
        <li>Simplify reward orchestration with a centralized catalog for all reward types, reducing operational complexity for marketing teams.</li>
      </ul>
    </p>
    <p>For more information, refer to <a href="https://docs.clevertap.com/docs/custom-rewards" target="_blank">Custom Rewards</a>.</p>
</div>
  <hr/>
</div>
`}</HTMLBlock>

<HTMLBlock>{`
<div class="release-note article" data-category="campaigns" id="in-app-messages-improvements">
  <div class="release-note-header">
    <div class="anchor-link-icon">
      <a href="#in-app-messages-improvements"><i class="fa-light fa-anchor"></i></a>
    </div>
    <div>
      <img src="https://files.readme.io/370216d2a5ec47fd419bc47a95762d51295730db345b40f825b3de7115e6e667-Campaigns.svg" alt="Campaigns" class="release-note-heading-icon"/>
    </div>
    <h3 class="release-note-heading">In-App Messages Improvements</h3>
    <div class="badge enhancement">ENHANCEMENT</div>
  </div>

  <div class="release-note-body">
    <p>CleverTap’s enhanced In-App Messages empower marketers to create fully customizable, interactive, and high-converting campaigns without requiring code. These updates simplify campaign creation, lower time-to-market, and deliver delightful In-App experiences that drive engagement and conversions.</p>

    <p>The following features are now available based on your plan:</p>

    <ul>
      <li><b>Advanced In-App Builder:</b> Build visually rich In-App messages using a no-code, drag-and-drop editor with animations, flexible layouts, and layered elements. For more information, refer to <a href="https://docs.clevertap.com/docs/advanced-in-app-builder" target="_blank">Advanced In-App Builder</a>.</li>

      <li><b>Gamified Experiences:</b> Use pre-built “Spin the Wheel” and “Scratch Card” templates in the Custom HTML Builder to create engaging, reward-based campaigns. For more information, refer to <a href="https://docs.clevertap.com/docs/advanced-in-app-builder" target="_blank">In-App Gamification Templates</a>.</li>

      <li><b>Custom Code Templates:</b> Create native In-App templates and define custom actions, such as “granting coins” or “navigating to premium”, that marketers can trigger directly from the dashboard. For more information, refer to the Custom Code Templates for <a href="https://developer.clevertap.com/docs/ios-custom-code-in-app-templates" target="_blank">iOS</a>, <a href="https://developer.clevertap.com/docs/android-custom-code-in-app-templates" target="_blank">Android</a>, <a href="https://developer.clevertap.com/docs/react-native-custom-code-in-app-templates" target="_blank">React Native</a>, <a href="https://developer.clevertap.com/docs/flutter-custom-code-in-app-templates" target="_blank">Flutter</a>, and <a href="https://developer.clevertap.com/docs/cordova-custom-code-in-app-templates" target="_blank">Cordova</a>.</li>

      <li><b>Native Prompt Triggers:</b> Allows you to display OS-level prompts such as app rating requests or push pre-permissions within In-App campaigns. For more information on how to render native prompts, refer to <a href="https://docs.clevertap.com/docs/advanced-in-app-builder" target="_blank">Advanced In-App Builder</a>, <a href="https://docs.clevertap.com/docs/register-for-push" target="_blank">Push Primer</a>, <a href="https://docs.clevertap.com/docs/app-rating-primer" target="_blank">App Rating Primer</a>, and <a href="https://docs.clevertap.com/docs/app-functions#use-app-functions" target="_blank">App Functions</a>.</li>
    </ul>
  </div>
  <hr/>
</div>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<style>
  nav#hub-sidebar { display: none; }
  
  #content-head h1 {
    font-weight: 500 !important;
    font-size: 35px !important;
  }
  
   .rm-Guides .content-body, .rm-Guides #content-head .col-xs-9 {
      max-width: 100%;
      width: 1000px;
  }
  
  .release-heading-container {
    display: flex;
    align-items: center;
    gap: 5px;
  }
  
  .release-note-heading{
  }
  
  .release-note-body img{
    border: 1px solid rgb(0,0,0,0.2)
  }
  
  .filters h3 {
  margin-bottom: 12px;
  font-size: 20px;
}

.filter-options {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  align-items: center;
}

.filter-option {
  flex: 0 0 calc(33.33% - 14px);
  color: #4A4C4C;
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 16px;
  white-space: nowrap;
}

  .filter-option:hover{
  	cursor:pointer;
    color:#191919;
  }

.filter-option img {
  width: 16px;
  height: 16px;
  color:#4A4C4C;
}

 .filter-option img:hover {
  fill:red;
}

.content-manager {
	display: flex;
  align-items: center;
  gap: 8px;
}

.badges {
  display: flex;
  gap: 4px;
  flex-wrap: wrap;
  align-items: center;
}
  
.badge {
    font-size: 12px;
    font-weight: 700;
    color: white;
  	padding:0px 4px;
    border-radius: 5px;
    display: inline-block;
		min-width: max-content
}
  
  .anchor-link-icon {
  margin-left: -23px;
  opacity: 0;
  transition: opacity 0.3s ease;
}

/* Show the anchor icon on hover */
.release-note-header:hover .anchor-link-icon {
  opacity: 1;
}
 
 .anchor-link-icon{
  	margin-left:-23px;
  }
.anchor-link-icon-inline {
  display: flex;
  align-items: center;
  font-size: 1.2em;
}
  
.release-note-header{
  display:flex;
  gap:8px;
  align-items: center;
 }
  
.private-beta {
    background-color: #B0B0B0;
}
  
.beta {
    background-color: #9E9E9E;
}
  
.new-feature {
    background-color: #4CAF50;
}
  
.enhancement {
    background-color: #2962FF;
}
  
.update {
    background-color: #673AB7;
}
  
/* Hide all articles by default */
.article {
  display: none;
}

/* Show all articles if no filters are checked */
body:not(:has(.filters input:checked)) .article {
  display: block;
}
  
* .rm-Guides a.suggestEdits {
    display: none;
  }

/* Show matching articles */
  body:has(#filter-campaigns:checked) .article[data-category="campaigns"],
	body:has(#filter-promotions:checked) .article[data-category="promotions"],
	body:has(#filter-conversations:checked) .article[data-category="conversations"],
	body:has(#filter-analytics:checked) .article[data-category="analytics"],
	body:has(#filter-segments:checked) .article[data-category="segments"],
	body:has(#filter-journeys:checked) .article[data-category="journeys"],
	body:has(#filter-data-and-integrations:checked) .article[data-category="data-and-integrations"],
	body:has(#filter-product-experiences:checked) .article[data-category="product-experiences"],
	body:has(#filter-content-manager:checked) .article[data-category="content-manager"],
	body:has(#filter-security-project-settings:checked) .article[data-category="security-project-settings"]{
  display: block;
}
  
</style>
`}</HTMLBlock>
