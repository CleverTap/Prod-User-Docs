---
title: Single Sign On (SSO)
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
## Overview

You can use Single Sign-On (SSO) to access your CleverTap dashboard. You must be on a CleverTap for Enterprises plan and use an identity provider or a custom SAML implementation in order to use SSO with CleverTap.

> 📘 Account Admin User
>
> You need to be an account admin to set up an SSO.

# Set Up SSO Configuration on CleverTap

<Image title="SSO_setup.png" alt={1151} className="border" border={true} src="https://files.readme.io/f060048-SSO_setup.png" />

## Access Setup Page

As an admin user, from the CleverTap dashboard, navigate to *Organization* > *SSO*. You will be directed to the SSO setup page.

## Configure SAML

To configure SAML, perform the following steps:

1. Copy the entity ID and Assertion Consumer service URL from the CleverTap and paste it in the IdP in Audience URI and Single sign-on URL respectively as shown below.

<Image title="image8.png" alt={1999} className="border" border={true} src="https://files.readme.io/89d232f-image8.png" />

2. Validate the Signature hash algorithm and binding to ensure they are the same in the Idp.

* Signature Hash Algorithm: SHA-256
* Binding: HTTP POST

3. Provide XML metadata to CleverTap. You can copy the XML MetaData and paste it or upload the file.

CleverTap supports dynamic configuration which requires you to enter the IdP MetaData. This IdP MetaData is provided by your identity provider and will look similar to the screenshot shown below in XML format.

<Image title="image11.png" alt={1999} className="border" border={true} src="https://files.readme.io/02c38b1-image11.png" />

This IdP MetaData is provided by your identity provider and will look similar to the screenshot shown below in XML format.

<Image title="image2.png" alt={1999} className="border" border={true} src="https://files.readme.io/bd84fde-image2.png" />

4. Set your unique domain URL.\
   A CleverTap domain, unique to your CleverTap application needs to be provided so that it can be used to authenticate your CleverTap account.

> 📘 Name Selection
>
> Please use an easy name to remember as this will be used by your team to log in to the CleverTap account.

<Image title="image12.png" alt={1999} className="border" border={true} src="https://files.readme.io/d6b7fc3-image12.png" />

This completes your basic setup of SAML SSO. You can test the SSO setup from the CleverTap dashboard to be sure if the setup is done correctly.

## Additional Settings

This section covers additional settings.

### Login with SSO only

Under the *Settings* > *SSO*,  you can find the setting *Require all users to login using SSO*.

<Image title="image9.png" alt={1330} className="border" border={true} src="https://files.readme.io/849cfd8-image9.png" />

If you select this option, your team members will not be able to log in to CleverTap directly. They will be forced to log in via the SSO option only.

> 🚧 Authentication Settings Considerations
>
> Use this option if your entire team has your domain email id and is set up on your IdP.
>
> If you have outsourced teams who do not have an email address in your domain, do not select this option as they will not be able to log in to CleverTap.
>
> If you select this option, you will not be able to create a user from the CleverTap dashboard or assign a role to the user, this will have to manage via the Identity Provider.

### Bind Existing Users

Some things to consider:

* If you already have a user setup on CleverTap and want to migrate them to SSO along with their CleverTap roles and account access, select this option.
* This gives you the option to download the users list by copying these user settings and paste them in the custom attributes in your IdP (More on how to set up custom attributes is given below).
* This ensures that all users who are currently on CleverTap’s authentication and authorization will be seamlessly migrated to the IdPs authentication and authorization.

<Image title="image3.png" alt={1460} className="border" border={true} src="https://files.readme.io/16cd66a-image3.png" />

<Image title="Screenshot 2020-03-19 at 2.44.15 PM.png" alt={912} className="border" border={true} src="https://files.readme.io/817ce89-Screenshot_2020-03-19_at_2.44.15_PM.png" />

> 📘 IdP Setup
>
> Below, you will be able to see how to set up access for the following IdPs:
>
> 1. Okta
> 2. OneLogin
> 3. Gsuite
>
> Other IdPs follow similar instructions.

# Identity Provider Set Up

Identity Provider (IdP) is the authority that verifies and asserts a user's identity and access to a requested resource (the "Service Provider").

Some examples of IdPs are Okta and GSuite.

## Okta Setup

This section covers the Okta setup.

### Create an Application

All IdPs allow you to create an app that you want to access using SSO. Start the setup by creating a CleverTap app in your IdP setup.

The example below is for setting up an app with Okta.

Under *Platform*, select *Web* and under *Sign on method*, select *SAML 2.0*.

<Image title="image5.png" alt={1604} className="border" border={true} src="https://files.readme.io/2c851bc-image5.png" />

<Image title="image10.png" alt={1999} className="border" border={true} src="https://files.readme.io/a1f27ba-image10.png" />

### Validate Settings

Validate the Signature hash algorithm and binding to ensure they are the same in the IdP:

* Signature Hash Algorithm: SHA-256
* Binding: HTTP POST

<Image title="Screenshot 2020-03-24 at 1.12.46 PM.png" alt={1508} className="border" border={true} src="https://files.readme.io/a77e184-Screenshot_2020-03-24_at_1.12.46_PM.png" />

### Attributes

You have to add some attributes for SSO to work. Attributes for name and email are compulsory in the format given in the screenshot. You need to add an attribute for each accountid you have in CleverTap.

You can then select for each account what role you want to give the users access to at a granular level.

Navigate to *Applications* > Select your application > General > Configure SAML.

The following attributes are mandatory.

<Image title="Screenshot 2020-03-12 at 3.53.39 PM.png" alt={1440} className="border" border={true} src="https://files.readme.io/5932ccc-Screenshot_2020-03-12_at_3.53.39_PM.png" />

Now if you have two accounts on Clevertap, you need to add the two AcccountId's in the following way:\
You can name them as appuser.\[Identifier}. As examples, we have used appuser.MainAccRole and appuser.MaiAccRole1.

This tells CleverTap which account a user should have access to. Click on **Next** and **Finish** to complete the process.

<Image title="Screenshot 2020-03-12 at 3.55.31 PM.png" alt={1440} className="border" border={true} src="https://files.readme.io/8eea100-Screenshot_2020-03-12_at_3.55.31_PM.png" />

Now, we need to define what role the user shoud have for each account.

1. Navigate to *Directory* > *Profile Editor*.
2. Hover on your app and select *Profile*.
3. Add and define what you want to call these attributes and what roles these attributes can get.
4. Click on **Add attribute**.
5. Name the *Variable* as "Your Account Name" to ensure that when assigning a name you can understand what account you are assigning the user to.
6. Ensure you add the Name in Variable as you did earlier for AccountID as MainAccRole and MainAccRole1 from our previous examples above.
7. Click the checkbox for an enumerated list and add all combinations of roles that you can possibly want to assign your user (you can get these combinations from the SSO Settings in the CleverTap dashboard as a CSV and copy-paste. 

> 📘 No Access
>
> It is important that you always add an attribute member "NoAccess" and provide it with an empty "\{}", so that you can select this value when you do not want to give the user access to this account.

8. Click **Save**. 

<Image title="Screenshot 2020-07-21 at 7.59.17 PM.png" alt={1444} className="border" border={true} src="https://files.readme.io/5e4a74f-Screenshot_2020-07-21_at_7.59.17_PM.png" />

To ensure the correct values are passed to CleverTap, map the attributes correct by performing the following steps:

1. Navigate to *Directory* > *Profile Editor*.
2. Click on **Profile** (For your App) > *Mappings*. 

<Image title="Screenshot 2020-07-21 at 8.03.41 PM.png" alt={2122} className="border" border={true} src="https://files.readme.io/ea10dd0-Screenshot_2020-07-21_at_8.03.41_PM.png" />

Now, you need to assign users to your application:

1. Navigate to *Applications* > Select your application > *Assignments*.
2. Select the user and what role you want to give to the user for each account. If you do not want to give the user access to the account, select *noaccess*.
3. Click **Save**.

<Image title="Screenshot 2020-03-12 at 4.16.31 PM.png" alt={1392} className="border" border={true} src="https://files.readme.io/373db05-Screenshot_2020-03-12_at_4.16.31_PM.png" />

## GSuite Setup

Log in to [https://admin.google.com/](https://admin.google.com/) and login as Admin for your app.

### Attributes

Navigate to *Users* > Click on **More** > Manage Custom Attributes > Add Custom Attributes.

1. You can give a category and description as per your naming policies, a recommendation is that names should be such that you can identify these custom attributes are for your CleverTap SSO setup.
2. For each account you have with CleverTap, create an equivalent entry here with the name of your account. For example, our app has two accounts and the account names are Account\_1 and Account\_2. 
3. Ensure these attributes are set to *Single value*.
4. Click **Save**. 

<Image title="Screenshot 2020-03-24 at 11.44.42 AM.png" alt={2798} className="border" border={true} src="https://files.readme.io/c045e8f-Screenshot_2020-03-24_at_11.44.42_AM.png" />

### Create an SAML App

To create an SAML app, perform the following steps:

1. Navigate to *Apps* > *SAML Apps*.
2. Click on the **+** sign to create your new CleverTap SAML App.
3. Add the ACS URL and Entity ID. 
4. Select the checkbox for Signed Response.
5. Name ID as *Basic Information* and *Primary Email* and Name ID format as *Email*. 

> 📘 Signed Response
>
> Ensure the checkbox for Signed Response is selected before proceeding.

<Image title="Screenshot 2020-03-24 at 11.35.13 AM.png" alt={1740} className="border" border={true} src="https://files.readme.io/81c7366-Screenshot_2020-03-24_at_11.35.13_AM.png" />

### Attribute Mapping

To map attributes, perform the following steps:

1. Name and email mapping as depicted in the screenshot are compulsory.
2. For each account you have in CleverTap, you should add the AccountID and select the respective attribute created for this account in the previous step when you created Attributes.
3. Click **Save**.

> 📘 AccountID
>
> Admins can find all AccountID's in the CleverTap dashboard under *Settings* > *Account*.

<Image title="Screenshot 2020-03-24 at 12.00.33 PM.png" alt={1778} className="border" border={true} src="https://files.readme.io/71265c2-Screenshot_2020-03-24_at_12.00.33_PM.png" />

### IdP Metadata

Now that the setup is done, under *Service Provider Details*:

1. Click **Manage Certificates**.
2. Download the IdP Metadata.

This is the XML Metadata file that you need to upload from the CleverTap dashboard by navigating to *Settings* > *SSO Settings* > *Upload XML Metadata*.

<Image title="Screenshot 2020-03-24 at 12.06.41 PM.png" alt={1778} className="border" border={true} src="https://files.readme.io/55d7a57-Screenshot_2020-03-24_at_12.06.41_PM.png" />

### Assign to Users and Roles

To assign to user and roles, perform the following steps:

1. Navigate to *Apps* > *SAML Apps*. 
2. Turn the app *ON for everyone*.  

<Image title="Screenshot 2020-03-24 at 12.17.02 PM.png" alt={2880} className="border" border={true} src="https://files.readme.io/b1eb85a-Screenshot_2020-03-24_at_12.17.02_PM.png" />

3. Navigate to *Users* and click on a user you want to give access to. You need to navigate to *Custom Attributes* and define the role for each account for this user.
4. Take the roleMap JSON that is available in the CSV download (Dashboard > Settings > SSO) for the user-account combination and paste it into the respective attributes for each account.
5. If you do not want to give user access to the account, define an empty JSON \{ } which indicates that the user has no access for this account.

> 📘 Restrict User Access
>
> If you do want to give users access to an account, you need to define an empty JSON which just empty curly braces such as \{ }.

![2164](https://files.readme.io/12efc07-Screenshot_2020-03-24_at_12.55.03_PM.png "Screenshot 2020-03-24 at 12.55.03 PM.png")

# Sign In Using SSO

Once you have completed the setup, you can save the settings. Once you have saved the settings, your login via SSO is complete. On the next login, your SSO will be activated.

<Image title="image6.png" alt={1999} className="border" border={true} src="https://files.readme.io/314aae0-image6.png" />

## Login

Once your SSO is setup, you can log in to CleverTap using the login with the SSO option.

<Image title="image1.png" alt={1999} className="border" border={true} src="https://files.readme.io/6521ec4-image1.png" />

Once you click on **Continue**, you will be redirected to your IdP login page. Once you log in from the IdP, you will be redirected back to your CleverTap dashboard.
