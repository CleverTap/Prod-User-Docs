---
title: SMS Gateway Center
excerpt: SMS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[SMS Gateway Center](https://www.smsgateway.center/) is a leading enterprise communication platform that enables businesses to send transactional, promotional, and OTP messages at scale. Integrating SMS Gateway Center with CleverTap allows you to send SMS notifications directly from CleverTap’s engagement dashboard.

This integration supports GET-based message delivery, [DLT-compliant routing](https://docs.clevertap.com/docs/sms-regulations#understand-dlt), and custom sender configuration for campaign tracking.

Businesses integrate SMS Gateway Center with CleverTap to:

* **Send Transactional Messages**: Deliver OTPs, verification codes, and real-time alerts.
* **Run Promotional Campaigns**: Send targeted offers and marketing messages to specific user segments.
* **Automate User Engagement**: Schedule reminders, feedback requests, and reactivation messages.

Integrating SMS Gateway Center with CleverTap combines intelligent audience targeting with robust SMS delivery.

# Prerequisites for Integration

Before integrating, check the following:

* You have an active SMS Gateway Center account with sufficient SMS credits and a valid paid subscription.
* You have an active CleverTap account with SMS channel access enabled.
* You have completed DLT registration with approved Entity ID, Sender ID, and Template IDs for all transactional or promotional SMS messages.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and continuously improved by SMS Gateway Center. For any questions or issues, contact [SMS Gateway Center](mailto:neha@smsgatewaycenter.com) or visit the [SMS Gateway Center Support Portal](https://www.smsgateway.center/) for support and resolution.
</Callout>

# Integrate SMS Gateway Center with CleverTap

To integrate SMS Gateway Center with CleverTap, perform the following steps:

1. [Find Details of SMS Gateway Center](doc:sms-gateway-center#find-details-of-sms-gateway-center)
2. [Set Up CleverTap Dashboard](doc:sms-gateway-center#set-up-clevertap-dashboard)
3. [Send Test SMS](doc:sms-gateway-center#send-test-sms)

## Find SMS Gateway Center Details

Before configuring CleverTap, gather the required DLT and message template details from your SMS Gateway Center account.

As per the DLT mandate, ensure the following details are configured in your SMS Gateway Center panel under _Settings_ > _DLT Configuration_:

* _Entity ID_: The unique ID assigned to your business by the DLT platform.
* _Sender ID_: The 6-character sender code from which SMS messages will be sent.
* _Template ID_: The unique ID for each approved transactional or promotional message template.
* _Template Details_: Upload the DLT-approved message templates you plan to send to customers.

Once these details are verified, proceed to configure CleverTap to connect with SMS Gateway Center.

## Set Up CleverTap Dashboard

Once your SMS Gateway Center account is ready, set up the CleverTap dashboard to connect and authenticate the SMS provider.

1. Go to _Settings_ > _Engage_ > _Channels_ > _SMS_ in the CleverTap dashboard.
2. Click **+ Add Provider**. The Add SMS provider page opens.

<Image align="center" alt="Add Provider" border={true} caption="Add Provider" src="https://files.readme.io/8ca98feff96deb7a4d4b6c4a0576f0b108f3d696f98dfbaa9b61faca58641cf2-image.png" width="65% " />

3. Under **Provider**, select _Other (Generic)_ and enter the following details:

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
        **Nickname**
      </td>

      <td>
        Enter a name such as `SMSGatewayCenter_SMS`.
      </td>
    </tr>

    <tr>
      <td>
        **Request Type**
      </td>

      <td>
        Select `GET`.
      </td>
    </tr>

    <tr>
      <td>
        **HTTP Endpoint**
      </td>

      <td>
        Paste the following URL:

        ```http Template URL
        https://www.smsgateway.center/SMSApi/rest/send?userId=YOURUSERNAME&password=YOURPASSWORD&senderId=YOURSENDERNAME&dltEntityId=123xxxxxxxxxx&sendMethod=simpleMsg&msgType=TEXT&msg=$$Body&mobile=$$To&duplicateCheck=true&dltTemplateId=$$templateid&format=json
        ```

        **Note**: Replace `YOURUSERNAME`, `YOURPASSWORD`, `YOURSENDERNAME`, and `dltEntityId` with your actual SMS Gateway Center credentials.
        The parameters `$$To` and `$$Body` are **case-sensitive** and dynamically replaced by CleverTap during execution.
      </td>
    </tr>
  </tbody>
</Table>

5. (Optional) Enable _Set as Default_ to make SMS Gateway Center your default SMS provider.
6. Click **Save**. A pop-up opens, prompting you to [Send Test SMS](doc:sms-gateway-center#send-test-sms).

## Send Test SMS

Sending a test SMS helps confirm that your SMS Gateway Center integration is working correctly before launching a live campaign. This ensures that the API endpoint is correctly configured, that authentication is valid, and that messages can be delivered.

To verify that the integration works:

1. Click the **Send Test SMS** hyperlink before creating SMS campaigns and journeys.
2. Enter the following details:
   * _Country Code and Mobile Number_: Enter the country code and mobile number to which you want to send the message.
   * _Message_: Enter sample text, such as `This is a test message powered by SMS Gateway Center.`

<Image align="center" alt="Send a Test SMS" border={true} caption="Send a Test SMS" src="https://files.readme.io/a9dcdc9f35c2840955e0d5157a13c6303ab148544cc3500577d7c5532d0a106f-image.png" width="65% " />

3. Click **Send Test**.

If the configuration is correct, the test message will be delivered, and SMS Gateway Center will return a DLR update. If there is an error (for example, incorrect credentials or endpoint), CleverTap will display a failure notification.

# Verify Successful Integration

Your integration is successful when the following conditions are met:

* The test SMS is delivered to the recipient’s number.
* CleverTap logs show no authentication or delivery errors.
* The message appears in your SMS Gateway Center delivery reports.

Once verified, you can build and publish [SMS Campaigns](doc:create-message-sms) or set up [Journeys](doc:journeys) using SMS Gateway Center as your default SMS provider.
