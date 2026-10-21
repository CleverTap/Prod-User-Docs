---
title: Branded Domain
excerpt: >-
  Learn how to configure system and custom domains to generate branded tracking
  links to boost engagement.
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

Branded Domains in CleverTap help you apply your brand to tracking across Email, SMS, WhatsApp, and RCS campaigns.

- **For SMS, WhatsApp, and RCS campaigns**: It is used to generate short, branded, trackable links.&#x20;
- **For Email campaigns**: It is used to brand links and open-tracking pixels using a custom domain.&#x20;

Using branded domains improves user trust and can boost engagement rates.

<Callout icon="far fa-circle-info" theme="info">
  #### Private Beta

  This feature is currently released in Private Beta. If you want to access the feature, contact your Customer Success Manager.
</Callout>

# Domain Types

CleverTap supports two types of branded domains:

| Domain | Description                                                                                                                                                                                                                                                                                    | Supported Channels  |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| System | CleverTap provides a system domain based on your region, for example, `ct3.io`. You choose a custom prefix/path called the Adjoiner for easy integration without the need for DNS configuration. It allows you to define the URL structure (Branded URL Schema) and customize 404 error pages. | WhatsApp, SMS & RCS |
| Custom | Enables you to use your own domain for complete control over your branding and tracking. To use a custom domain, you need to configure DNS records with your domain provider for proper verification and campaign tracking.                                                                    | Email, SMS          |

<Callout icon="far fa-circle-info" theme="info">
  #### Domain Limit

  You can add up to 5 unique custom domains per account per channel.
</Callout>

<Tabs>
  <Tab title="WhatsApp/SMS & RCS">
    # System Domain

    Use this domain to get branded links without DNS configuration.

    ## Add System Domain

    You can create a system domain to quickly start using branded links in your WhatsApp/SMS & RCS campaigns without DNS configuration. To add a system domain, enter the following details:

    1. Go to Settings > Set Up > Branded Domain.

    2. Click **Add Domain** and select the channel.


       <Image src="https://files.readme.io/c84de5b794ccd9918cd5e05612ebe2551f456e4838e76da5c53e07877c4c0990-Select_Channel.png" align="center" caption="Select Channel for Adding Branded Domain" border={true} />


    3. Select Domain Type as _System_.

    4. Enter the following details:


       <Image src="https://files.readme.io/e3b88c267d2ff3601ff7e683443c73d9339f2eabce70810a1a9ad7c3522277ed-Add_Domain.png" align="center" caption="Add System Domain" border={true} />


       <Table>
         <thead>
           <tr>
             <th>
               Field
             </th>

             <th>
               Description
             </th>
           </tr>
         </thead>

         <tbody>
           <tr>
             <td>
               Nickname
             </td>

             <td>
               Enter a name to identify the domain (for example, "Marketing").
             </td>
           </tr>

           <tr>
             <td>
               Channel
             </td>

             <td>
               Displays the channel for which the branded domain is being created.
             </td>
           </tr>

           <tr>
             <td>
               Domain Type
             </td>

             <td>
               - A CleverTap-provided system domain that can be customized with your brand prefix.&#x20;
               - No DNS setup required.&#x20;
               - This is available only for WhatsApp/SMS & RCS channels.
             </td>
           </tr>

           <tr>
             <td>
               Domain
             </td>

             <td>
               The base domain used for branding and tracking. When adding a system domain, this is auto-filled based on your account region. For more information, refer to Domain and Account Region Mapping for WhatsApp/SMS & RCS below the table.
             </td>
           </tr>

           <tr>
             <td>
               Branded URL Schema
             </td>

             <td>
               Defines the structure of the branded tracking URL. This is available for WhatsApp/SMS & RCS channels and is required to add a system domain.<br />URL Structure: domain/adjoiner/Shortkey, for example, [ct3.io/clevertap/abc123](ct3.io/clevertap/abc123 "ct3.io/clevertap/abc123")<br />This includes the following:&#x20;

               - Domain: The domain entered above is prepopulated here.&#x20;
               - Adjoiner: A brand-specific path separator that connects the Domain and Shortkey, helping personalize and group URLs. The Adjoiner can only contain lowercase letters, numbers, and hyphens. It must not start or end with a hyphen, and cannot contain special characters.&#x20;
               - Shortkey: A unique, auto-generated code added to the branded domain, helping track clicks on links within campaigns. &#x20;
             </td>
           </tr>

           <tr>
             <td>
               Error Page
             </td>

             <td>
               The page users see if a tracking link is invalid or has expired. You can use CleverTap's system error page or provide a custom URL to maintain brand consistency even in error scenarios. Click Preview Error Page to view and verify the error before the domain becomes active.
             </td>
           </tr>
         </tbody>
       </Table>

    5. Click **Save**. The status is set to **Active** immediately.

    #### Domain and Account Region Mapping for WhatsApp/SMS & RCS

    | Dashboard URL                                                                               | Region      | System Domain             | Example URL                                    |
    | ------------------------------------------------------------------------------------------- | ----------- | ------------------------- | ---------------------------------------------- |
    | [eu1.dashboard.clevertap.com](eu1.dashboard.clevertap.com "eu1.dashboard.clevertap.com")    | EU          | [ct1.io](ct1.io "ct1.io") | [ct1.io/25AlJz](ct1.io/25AlJz "ct1.io/25AlJz") |
    | [in1.dashboard.clevertap.com](in1.dashboard.clevertap.com "in1.dashboard.clevertap.com")    | IN          | [ct3.io](ct3.io "ct3.io") | [ct3.io/52KlAz](ct3.io/52KlAz "ct3.io/52KlAz") |
    | [sg1.dashboard.clevertap.com](sg1.dashboard.clevertap.com "sg1.dashboard.clevertap.com")    | SG          | [ct4.io](ct4.io "ct4.io") | [ct4.io/25ZlAz](ct4.io/25ZlAz "ct4.io/25ZlAz") |
    | [us1.dashboard.clevertap.com](us1.dashboard.clevertap.com "us1.dashboard.clevertap.com")    | US          | [ct5.io](ct5.io "ct5.io") | [ct5.io/52ZlKa](ct5.io/52ZlKa "ct5.io/52ZlKa") |
    | [mec1.dashboard.clevertap.com](mec1.dashboard.clevertap.com "mec1.dashboard.clevertap.com") | Middle East | [ct8.io](ct8.io "ct8.io") | [ct8.io/25ZaJz](ct8.io/25ZaJz "ct8.io/25ZaJz") |
    | [aps3.dashboard.clevertap.com](aps3.dashboard.clevertap.com "aps3.dashboard.clevertap.com") | Indonesia   | [ct9.io](ct9.io "ct9.io") | [ct9.io/52KJz](ct9.io/52KJz "ct9.io/52KJz")    |

    ## Best Practices for System Domain

    - Choose a short and meaningful Adjoiner that clearly represents your brand or campaign type.
    - Use lowercase letters and hyphens (-) if needed (for example, /clevertap/, /new-user/, /sale2024/).
    - Keep it concise: Aim for 5–8 characters in the Adjoiner (excluding the slashes) to avoid long URLs in campaigns.
    - Avoid vague terms such as /track/ or /link/; use something unique to your brand.

    # Custom Domain

    Use this option to use your own subdomain for SMS without managing infrastructure. This option allows you to fully control the branding and tracking for your campaigns.

    <Callout icon="📘" theme="info">
      #### Custom Domain

      You can add up to 5 unique custom domains per account per channel.
    </Callout>

    ## Add Custom Domain

    To add a custom domain for SMS, perform the following steps:

    1. Click **Add Domain** and select the channel.
    2. Enter the following details: <br />


       <Image src="https://files.readme.io/fb051da68dc04341c6220f6b4ef0114236e618b7b38f4d2a645aa06476488b3c-Add_Custom_Domain_for_WhatsApp_SMS_and_RCS.png" align="center" caption="Add Custom Domain for WhatsApp/SMS & RCS" border={true} />


       | Field              | Description                                                                                              |
       | ------------------ | -------------------------------------------------------------------------------------------------------- |
       | Nickname           | Enter a name to identify the domain (for example, "Marketing").                                          |
       | Channel            | The channel this branded domain will be used for.                                                        |
       | Domain Type        | Your own subdomain (for example, links.yourbrand.com) that requires DNS configuration.                   |
       | Domain             | Enter your own subdomain to be used for branding and tracking.                                           |
       | Branded URL Schema | Defines the structure of the branded tracking URL. It defines the structure of the branded tracking URL. |
    3. Click **Save & Generate DNS&#x20;**&#x61;fter adding all the details. The domain status is set to **Pending Verification** immediately, and DNS Records are generated to add them to your Domain provider dashboard. The generated records include two CNAME records and one TXT record.

    ## Best Practices for Custom Domain

    - Use a subdomain such as links., click., or promo. (for example,links.yourbrand.com, click.yourbrand.com).
    - Keep the Subdomain short, relevant, and easy to remember.
    - Avoid complex words, long phrases, or special characters in the Subdomain name.
  </Tab>

  <Tab title="Email">
    # Custom Domain

    When setting up a custom domain for Email, you must choose between the following two _Domain Management_ options:

    - CleverTap-Managed
    - Self-Managed

    ## CleverTap-Managed Custom Domain

    CleverTap handles all infrastructure setup and ongoing maintenance. This is the default option.

    | Aspect                      | CleverTap-managed                                                                    |
    | --------------------------- | ------------------------------------------------------------------------------------ |
    | **CloudFront Distribution** | CleverTap owns, provisions, configures, and manages the AWS CloudFront distribution. |
    | **SSL Certificates**        | CleverTap manages SSL certificate provisioning, configuration, and renewals.         |
    | **DNS Configuration**       | Requires 3 DNS records (2 CNAME + 1 TXT) for verification and tracking.              |

    ### Add Domain

    Use your own domain (for example, sales.yourbrand.com) for maximum brand visibility. This option allows you to fully control the branding and tracking for your campaigns.

    1. Go to Settings > Set Up > Branded Domain.

    2. Click **Add Domain** and select Email channel.


       <Image src="https://files.readme.io/e4811a9c0c78b043c2f24a8feee9d72dc4f75b0616506194ec740a3f138bf969-Select_Channel.png" align="center" caption="Select Channel for Adding Custom Domain" border={true} />


    3. Select Domain Type as _Custom_.

    4. Verify Domain Management is set to CleverTap (this is the default for Email).

    5. Enter the following details:


       <Image src="https://files.readme.io/ea128bbb0d7aac2fc6fdfe61bf246cfae999a8f7309a8e1c95aa8cc654eaf354-CNAME_and_TXT_Records.png" align="center" caption="Add CleverTap-Managed Custom Domain" border={true} />


       | Field             | Description                                                                                     |
       | ----------------- | ----------------------------------------------------------------------------------------------- |
       | Nickname          | Enter a name to identify the domain (for example, "Marketing").                                 |
       | Domain Management | Selecting CleverTap indicates that CleverTap manages the infrastructure of your branded domain. |
       | Domain            | Enter your own domain to be used for branding and tracking.                                     |

    6. Click **Save & Generate DNS**.

    DNS Records are generated, and the domain status is set to **Pending Verification** immediately. CleverTap generates one CNAME record and one TXT record.

    ### Verify CleverTap-Managed Custom Domain

    Verify the DNS records generated so the domain becomes active and available for use.

    To do so, perform the following steps:

    1. Go to the domain provider dashboard and configure the following DNS records. When configuring DNS records with your domain provider, enter only the prefix part in the Name field. The prefix is the part that precedes the main domain. For example, if the CNAME is `_c58ebcb5c******5f03bb6b174349.track.yourdomain.com`, enter `_c58ebcb5c******5f03bb6b174349.track` in the Name field.
    2. Once your DNS records are saved, go back to the Branded Domain page on the CleverTap dashboard.
    3. Click the ![](https://files.readme.io/36be013543cabc562d762f02fd1eebc007f2caad03f95519a37dfff4f6e4c7ed-Refresh_icon.png) icon next to your domain to refresh the domain verification status on the CleverTap dashboard. DNS verification may take up to 24 hours to complete. If verification fails, check your DNS configuration with your domain provider to ensure it is accurate. For more information, refer to [FAQs](doc:branded-domain#faqs)​.&#x20;

    <Callout icon="far fa-circle-info" theme="info">
      #### Link Branding Verification

      DNS verification can take up to 48 hours after your domain is set to ACTIVE. To check if verification is complete, go to _Branded Domains_ and click ![](https://files.readme.io/36be013543cabc562d762f02fd1eebc007f2caad03f95519a37dfff4f6e4c7ed-Refresh_icon.png) icon next to your domain to verify your domain and refresh the status on the CleverTap dashboard.
    </Callout>

    ### Set Up Link Branding (CleverTap-Managed)

    This section covers link branding-specific configuration after your domain is verified and ACTIVE.

    To set up Link Branding, perform the following steps:

    1. Go to _Settings_ > Setup > Branded Domains. The Branded Domains page opens.
    2. Verify that the status of your domain shows ACTIVE
    3. (Optional) Set your domain as the default. When a domain is set as default, all new email campaigns automatically use this domain for link branding. You can still override this on individual campaigns.
    4. Go to _Campaigns_ and compose an Email campaign.
    5. Go to _Sender Details_ and fill in the required fields.
    6. Select Link Branding and select your domain from the dropdown. If you set it as default in _Step 3_, it will be pre-selected.&#x20;
    7. Preview your campaign to verify that branded links are generated:
       1. Click Preview & Test and send a test campaign.
       2. Hover over a link present in the test campaign to see the full URL, or right-click and select _Copy Link Address_ to inspect it.
       3. Verify it shows your branded domain. The link will begin with [`https://track.yourbrand.com/r`](https://track.yourbrand.com/r)`?...` .
       4. Click the link to verify that the redirect works properly and points to the destination URL.

    ## Self-Managed Custom Domain

    If you already have a CloudFront distribution configured for your custom domain, you must use the Self-Managed option. This is because AWS CloudFront does not allow multiple distributions for the same custom domain.

    With this, you maintain complete control over the CloudFront infrastructure and SSL certificates, while CleverTap handles link-tracking verification.&#x20;

    <Callout icon="far fa-circle-info" theme="info">
      #### Important

      You must ensure your CloudFront distribution is properly configured to point to CleverTap's tracking infrastructure.&#x20;
    </Callout>

    ### Add Custom Domain

    &#x20;Use your own domain (for example, `sales.yourbrand.com`) for maximum brand visibility. This option allows you to fully control the branding and tracking for your campaigns.

    To add a self-managed custom domain, perform the following steps:

    1. Go to _Settings_ > _Setup_ > _Branded Domain_.

    2. Click **Add Domain** and select Email channel.


       <Image src="https://files.readme.io/e4811a9c0c78b043c2f24a8feee9d72dc4f75b0616506194ec740a3f138bf969-Select_Channel.png" align="center" caption="Select Channel for Adding Custom Domain" border={true} />


    3. Select Domain Type as _Custom_.

    4. Select Domain Management as _Self_.

    5. Enter the following details:


       <Image src="https://files.readme.io/213b6688f92893080b0390f1ed0c715a61d8a61c053235b668d6a430789899ec-Add_Self-Managed_Custom_Domain.png" align="center" caption="Add Self-Managed Custom Domain" border={true} />


       | Field             | Description                                                                                                                                                                     |
       | :---------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
       | Nickname          | Provide a name to identify the domain (for example, "Marketing").                                                                                                               |
       | Channel           | The channel this branded domain will be used for.                                                                                                                               |
       | Domain Type       | Your own domain (for example, links.yourbrand.com) that requires DNS configuration.                                                                                             |
       | Domain Management | Selecting Self indicates you manage the infrastructure for your branded domain. For more information, refer to [Verify Custom Domain](doc:branded-domain#step-6-verify-domain). |
       | Domain            | Enter your own domain to be used for branding and tracking                                                                                                                      |

    6. Click **Save & Generate DNS**.

    DNS Records are generated, and the domain status is set to **Pending Verification** immediately. DNS records include a single TXT record.&#x20;

    ### Set Up Self-Managed Domain

    The following steps must be completed by your team to set up your self-managed domain:

    #### Step 1: Add TXT Record to DNS

    Add the TXT record generated by CleverTap to your domain’s DNS provider. This verifies domain ownership with CleverTap.

    1. Go to your domain provider dashboard
    2. Copy and add the TXT record shown in the DNS records section of the CleverTap dashboard.

    #### Step 2: Create S3 Bucket for `.well-known` Files

    Host your app's`apple-app-site-association` and `assetlinks.json` files at both the root path and `/.well-known/` path.

    1. Create an S3 bucket in your AWS account
    2. Upload the following files:
       - `/apple-app-site-association` (at bucket root)
       - `/.well-known/apple-app-site-association`
       - `/assetlinks.json` (at bucket root)
       - `/.well-known/assetlinks.json`&#x20;
    3. Set Content-Type to `application/json` for all files
    4. Configure the bucket for private access with Origin Access Control (OAC); CloudFront will access it securely.

    #### Step 3: Request ACM Certificate

    Request a public SSL certificate for your custom domain.

    1. Go to _AWS Certificate Manager_ in the `us-east-1` region (required for CloudFront).
    2. Request a public certificate for your custom domain (for example, links.yourbrand.com).
    3. Choose DNS validation.
    4. Add the required DNS CNAME record to your domain provider.
    5. Wait for the certificate to be issued (typically a few minutes).
    6. Note the certificate ARN for use in CloudFront.

    #### Step 4: Create CloudFront Distribution

    Create a CloudFront distribution with two origins and three cache behaviors.

    **Create Two Origins**

    - **Origin 1 - CleverTap Tracking**:
      - Origin Domain: To identify the region-specific origin domain, refer to the following table:
        | Dashboard URL                | Region | Origin Host                                                                |
        | ---------------------------- | ------ | -------------------------------------------------------------------------- |
        | eu1.dashboard.clevertap.com  | EU     | [wizrocketmail.net](wizrocketmail.net "wizrocketmail.net")                 |
        | in1.dashboard.clevertap.com  | IN     | [in1.wizrocketmail.net](in1.wizrocketmail.net "in1.wizrocketmail.net")     |
        | sg1.dashboard.clevertap.com  | SG     | [sg1.wizrocketmail.net](sg1.wizrocketmail.net "sg1.wizrocketmail.net")     |
        | us1.dashboard.clevertap.com  | US     | [us1.wizrocketmail.net](us1.wizrocketmail.net "us1.wizrocketmail.net")     |
        | mec1.dashboard.clevertap.com | APS    | [aps3.wizrocketmail.net](aps3.wizrocketmail.net "aps3.wizrocketmail.net")  |
        | aps3.dashboard.clevertap.com | MEC    | [mec1.wizrocketmail.net](mec1.wizrocketmail.net "mec1.wizrocketmail.net")​ |
      - Origin protocol: HTTPS only
      - Origin SSL protocols: TLSv1.2 minimum
    - **Origin 2 - S3 Bucket**
      - Origin domain: Your S3 bucket
      - Origin Access Control: Enable OAC for secure access
      - Protocol: HTTPS only

    **Configure Cache Behavior**

    You are required to configure the following three cache behaviors in the same order:

    1. Behavior 1 - AASA File:
       - Path pattern: `/.well-known/*`
       - Origin: S3 bucket origin
       - Cache policy: CachingOptimized
       - Allowed HTTP methods: GET, HEAD
       - Viewer protocol policy: Redirect HTTP to HTTPS
    2. Behavior 2 - Legacy iOS Path:
       - Path pattern: `/apple-app-site-association`
       - Origin: S3 bucket origin
       - Cache policy: CachingOptimized
       - Allowed HTTP methods: GET, HEAD
       - Viewer protocol policy: Redirect HTTP to HTTPS
    3. Behavior 3 - Default (Tracking):
       - Path pattern: `*` (matches all traffic)
       - Origin: CleverTap origin
       - Cache policy: CachingDisabled&#x20;
         <Callout icon="📘" theme="info">
           #### Important

           Ensure cache policy is set to `CachingDisabled` . If CloudFront caches the tracking response, subsequent users are served the cached response without reaching CleverTap, so their clicks/opens will not be recorded.&#x20;
         </Callout>
       - Origin request policy: AllViewer (ID: 216adef6-5c7f-47e4-b989-5492eafa07d3)
         - Forwards all headers, including Host (critical for account identification)
         - Forwards all query strings
       - Allowed HTTP methods: GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE
       - Viewer protocol policy: Redirect HTTP to HTTPS

    #### Step 5: Set Alternate Domain Name (CNAME)

    1. In CloudFront distribution settings, add your custom domain as an Alternate Domain Name (CNAME)
    2. Attach the ACM certificate created in Step 3.
    3. Save and wait for the distribution to deploy (status shows “Deployed”).

    #### Step 6: Verify Domain

    1. Once your CloudFront distribution is deployed (status shows "Deployed") and your TXT record is configured, go back to the _Branded Domain_ page on the CleverTap dashboard
    2. Click the verification icon next to your domain. DNS verification may take up to 48 hours to complete. The verification checks only the TXT record; ensure your CloudFront distribution is properly configured separately. CleverTap re-checks verification every 3 hours

    <Callout icon="📘" theme="info">
      #### DNS Verification&#x20;

      DNS verification can take up to 48 hours after your domain is set to ACTIVE. To check if verification is complete, go to _Branded Domain_ from the CleverTap dashboard.
    </Callout>

    If verification fails:

    - Verify your TXT record is correctly configured with your DNS provider
    - Ensure your CloudFront distribution is deployed and accessible

    <Callout icon="🚧" theme="warn">
      #### DNS Conflict

      Your custom domain should only be used for CleverTap tracking. Do not use this domain in any other tool, service, or CDN distribution. Multiple CNAME records pointing to different services for the same custom domain will cause DNS conflicts and break tracking.&#x20;
    </Callout>

    #### Step 7: Update DNS CNAME

    1. Go to your domain provider dashboard
    2. Create a CNAME record pointing your custom domain to your CloudFront distribution:
       - Name: Your custom domain (for example, `links.yourbrand.com`)
       - Value: Your CloudFront distribution domain (for example, `d1234abcdef.cloudfront.net`)
    3. Save the record.

    <Callout icon="📘" theme="info">
      #### Self-Manged Domain Configuration

      Unlike CleverTap-managed custom domains, self-managed domains do not require<br />CNAME records generated by CleverTap. Instead, you manage the CNAME record<br />in your AWS account pointing your custom domain to your CloudFront distribution.<br />You only need to configure CleverTap's TXT record for domain verification.
    </Callout>

    ### Set Up Link Branding for Self-Managed Domain&#x20;

    This section covers the link branding-specific configuration after your self-managed domain is verified and Active.&#x20;

    To set up Link Branding, perform the following steps:

    1. Go to _Settings_ > _Set Up_ > _Branded Domains_. The Branded Domains page opens.
    2. Verify that your domain status is ACTIVE.
    3. (Optional) Set your self-managed domain as the default. When a domain is set as default, all new email campaigns automatically use this domain for link branding. You can still override this on individual campaigns.
    4. Go to Campaigns and compose an Email campaign.
    5. Go to _Sender Details_ and fill in details such as From Name, From Email address, Subject, and so on.
    6. Select _Link Branding_ and select your self-managed domain from the dropdown. If you set it as the default in _Step 3_, it will be pre-selected.
    7. Verify Click Tracking is enabled (required for link branding). The links for product pages, CTAs, preference centers, or other destinations added in the campaign message, CleverTap automatically wraps all links with tracking code and applies your branded domain
    8. Preview your campaign to verify that branded links are generated:
       1. Click Preview & Test and send a test campaign.
       2. Hover over a link present in the test campaign to see the full URL, or right-click and select _Copy Link Address_ to inspect it.
       3. Verify it shows your branded domain. The link will begin with [`https://track.yourbrand.com/r`](https://track.yourbrand.com/r)`?...` .
       4. Click the link to verify that the redirect works properly and points to the destination URL.

    Now, when you send an email with a from address where the domain matches your branded link domain, CleverTap automatically applies that domain to all links in the email. When the user clicks a branded link (for example, track.yourbrand.com/r?e=\<encrypted_payload>):

    - The request reaches your CloudFront distribution. CloudFront matches the path (for example, /r or /t) and forwards to CleverTap's regional email redirect host (for example, wizrocketmail.net).
    - CleverTap's server receives the request, decrypts the payload, and records the click/open event. CleverTap responds with a redirect to the final destination URL.

    * CloudFront passes the response directly back without caching. User's browser follows the redirect to the final destination. All tracking data is recorded in CleverTap analytics and visible in the campaign report.

    ## Best Practices **For Self-Managed Domain**

    * CloudFront Configuration:
      * Use appropriate cache TTL settings (Time To Live) for tracking links.
      * Configure cache behaviors to handle both tracked links and error pages.
      * Enable compression for smaller payload sizes.
      * Use HTTPS-only for secure tracking.
    * SSL/TLS Certificate Management:
      * Use a valid, non-expired SSL certificate from a trusted Certificate Authority.
      * Renew certificates before expiration to avoid service interruptions.
      * Consider using auto-renewal services to prevent certificate expiration issues.
    * Monitoring and Maintenance:
      * Monitor CloudFront metrics for unusual activity.
      * Set up CloudFront access logs to track domain usage.
      * Regularly review and update cache behaviors as needed.
      * Test the domain periodically to ensure proper functioning.
    * DNS Configuration:
      * Copy the exact TXT record from your CleverTap dashboard; do not modify the value. Use the copy option to avoid any errors.
      * Allow up to 24 hours for DNS propagation before verifying
      * Do not use this domain in other tools/services (avoid DNS conflicts)
      * (Optional) Verify DNS is correctly configured by executing this command: `nslookup -type=TXT _clevertap-verify.track.yourbrand.com`&#x20;

    <Callout icon="📘" theme="info">
      #### Tip: Buy New Short Domain for Campaigns

      If your existing domain is long or complex, consider purchasing a new, short domain for marketing messages. Ideally, the domain must be 5–8 characters long and phonetically similar to your brand name. This improves:

      * Link trustworthiness
      * User recall and voice-based sharing (for example, over phone or radio)
      * Visual clarity in messages and notifications

      **Examples**:

      * If your brand name is long (for example, **ExampleStore**), consider short domain options like **exstr.in**, **exsto.co**, or **exst.co**.
      * For multi-word brand names (for example, **Example Food Market**), you could use shortened versions such as **exfdmr.com**, **efmkt.in**, or **xfmk.co**.
    </Callout>
  </Tab>
</Tabs>

# Manage Branded Domains

The Domain Listing page allows you to view and manage all your configured domains. You can easily edit domain settings, view DNS records, and make any necessary updates to check if your domains are correctly set up and functioning.

Go to _Settings_ > _Set Up_ > _Branded Domains_. You can see a list of all your domains (system or custom), including the following details:

<Image align="center" border={true} caption="Branded Domains Page" src="https://files.readme.io/2fbb49c4e3a18c0744338f8f2db30ae4f28a3babf5c0f3eb1289f175dc099f41-Branded_Domain_Listing_Page.png" />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        _Nickname_
      </td>

      <td>
        A user-defined name to help you identify the domain (for example, "Sales Campaign").
      </td>
    </tr>

    <tr>
      <td>
        _Domain URL_
      </td>

      <td>
        Displays the full URL of the branded domain being used for tracking links in the case of WhatsApp/SMS & RCS campaigns (for example, `ct3.io/clevertap/abc123`). Displays the branded domain being used for email campaigns (for example,  `track.yourdomain.com`).
      </td>
    </tr>

    <tr>
      <td>
        Managed By
      </td>

      <td>
        Indicates who manages the domain infrastructure: **CleverTap** (CleverTap-managed) or **Self** (self-managed).
      </td>
    </tr>

    <tr>
      <td>
        _Created By_
      </td>

      <td>
        The email address of the user who created the domain.
      </td>
    </tr>

    <tr>
      <td>
        _Status_
      </td>

      <td>
        The current status of the domain. It can be: <ul><li>**Active**: Domain is verified and ready to be used in campaigns.</li><li>**Pending Verification**: Domain is awaiting DNS verification and cannot be used until verified.</li><li>**Failed**: Domain verification failed due to incorrect or missing DNS records.</li></ul><br /><br />For Self-Managed Domains:

        - Verify that your CloudFront distribution is properly configured and actively serving traffic.
        - Ensure the TXT record is configured with your DNS provider and your CloudFront distribution is set up.
        - Ensure the TXT record is correctly configured. If the TXT record is correct, verify your CloudFront setup.
      </td>
    </tr>

    <tr>
      <td>
        _Last Updated On_
      </td>

      <td>
        The timestamp when the domain settings were last updated.
      </td>
    </tr>
  </tbody>
</Table>

After adding the domain, you can perform the following operations by hovering over it:

<Image align="center" border={true} caption="Manage Branded Domains" src="https://files.readme.io/a4ad7fef6b3c58d079a57876f5c3d45be43447b1298499d715bdf28d0e2dbafd-Manage_Branded_Domains.gif" />

* **Set as Default**: You can set one verified domain as the default for WhatsApp, SMS, and RCS, and a different verified domain as the default for Email. This domain is automatically used for links in SMS, WhatsApp, RCS, and Email campaigns (including template buttons). You can override it per campaign when creating new ones.

* **Edit**: You can change the domain nickname. Additionally, for WhatsApp/SMS & RCS campaigns, you can set a custom 404 error page (except for system defaults).&#x20;

* **Verify Domain**: You can manually verify the domain by checking the status. If the verification fails, you can click the ![](https://files.readme.io/af7a9009c220dbcfb129f0528f3669b976d0d7f0de86557dca6e52c1444d6aed-Refresh_icon.png) icon next to the domain to retry after making the necessary corrections.

* **View DNS Records**: You can access and review the DNS settings associated with your domain. For CleverTap-managed domains, this includes details such as CNAME and TXT records. For self-managed domains, this displays only the TXT record; your CloudFront configuration is managed separately in your AWS account. By viewing these records, you can ensure that the domain is correctly configured with your DNS provider for seamless integration and functionality.

# Common Best Practices

The following are some of the common best practices for using a branded domain:

- Keep the domain short, relevant, and easy to remember.
- Avoid complex words, long phrases, or special characters in the domain name.
- Ensure you configure DNS records exactly as shown after setup to avoid delays in verification.&#x20;

# FAQs

### Q. Can I switch between path-based and query-based adjoiners?

No, you must choose one format per domain: either **path-based** (`/yourbrand/`) or **query-based** (`?key=yourbrand`). You cannot mix both formats in a single domain configuration.

### Q. What happens if my custom domain becomes unverified?

If a branded domain used for Email moves from Active to Pending Verification or Failed:

* CleverTap sends an email alert to inform you of the status change.
* CleverTap automatically falls back to the system domain for email click and open tracking.
* Email campaigns continue to send without interruption.

Once the domain is verified again, it can be reused in future campaigns.

### Q. Will old campaigns use the new branded domain?

No. Campaigns created before you set up a branded domain will continue using the **System Domain** unless you manually edit or recreate them with the new branded domain.

### Q. I configured the DNS records, but my domain has still not been verified. What should I do?

Check the following:

* **DNS records** are entered exactly as shown in the CleverTap dashboard.
* You have entered only the required prefix in the **Key** field (for example, short, not short.clevertap.com).
* Wait up to 24 hours, then try refreshing again.

### Q. When will a link preview be shown for my branded domain link?

A link preview is generated when the messaging platform (such as SMS, WhatsApp, or RCS) scans the URL included in your message and detects the required Open Graph metadata on the destination page. The following tags must be present and properly configured in the page’s HTML:

* `<meta property="og:title" content="...">`
* `<meta property="og:description" content="...">`
* `<meta property="og:image" content="...">`

If these tags are available and valid, the platform may display a visual preview containing a title, description, and image. A preview may not be shown in the following cases:

* The Open Graph tags are missing or incorrectly implemented.
* The domain is blocked by `robots.txt` or firewalls.
* The page is inaccessible to external crawlers.

To verify that your Open Graph metadata is implemented correctly, use a metadata testing tool or an Open Graph debugger.

### Q. How do link previews work on iOS devices, and why might they not appear?

iOS devices running iOS 10 or later support link previews in the native Messages app. These previews may still appear for SMS-based messages, but several conditions must be met for reliable rendering.

**Preview Requirements**

* Only one link should be included in the message. Messages with multiple links will not generate a preview.
* The link must be the final element in the message. No text, punctuation, or symbols should follow the link.
* The domain must be served over HTTPS and use a valid SSL certificate. Self-signed, expired, or incomplete certificates will block preview generation.
* The recipient must tap _Tap to Load Preview_ for metadata to be fetched.

**iOS-specific Behaviors and Limitations**

* iOS delays metadata fetching until after the message is delivered, and in some cases, until the user interacts with the message.
* Devices may display cached metadata even after updates to the page’s Open Graph tags.
* Certain third-party messaging apps may block previews by default, unless they are explicitly enabled in the settings.

These constraints can lead to inconsistent preview rendering on iOS devices, even when metadata is correctly configured.

### Q. Who is responsible for CloudFront and SSL certificates with a self-managed domain?

With a self-managed domain, you are fully responsible for:

- Setting up and configuring the CloudFront distribution.
- Configuring cache behaviors and origin settings.
- Managing and renewing SSL certificates.
- Ensuring the distribution remains active and properly configured.
- Monitoring CloudFront and troubleshooting issues.
- CleverTap is responsible only for link-tracking verification and TXT record validation.

### **Q. Can I switch from CleverTap-Managed to Self-Managed Domain?**

Direct Migration is not currently possible. But you can create a new domain in parallel:

1. Create a new self-managed domain with a different domain
2. Set up your CloudFront distribution and SSL certificate for the new domain.
3. Update campaigns to use the new domain.
4. Once verified and tested, delete the old CleverTap-managed domain.

Contact your Customer Success Manager for assistance with domain transitions.

### Q. What happens if my self-managed domain's CloudFront distribution goes down?

If your CloudFront distribution becomes unavailable:

- Tracking links will not function properly.
- Campaign links may return errors or fail to redirect.
- Email click and open tracking may be affected.

Ensure you have monitoring and alerting in place to quickly identify and resolve any issues.

<br />