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
You can use Single Sign-On (SSO) to access your CleverTap dashboard. You must be on a CleverTap corporate pack and use an identity provider or a custom SAML implementation in order to use SSO with CleverTap

[block:callout]
{
  "type": "info",
  "body": "You need to be an account admin to setup SSO",
  "title": "Note"
}
[/block]
# Setting up SSO configuration on CleverTap
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b022c4-image4.png",
        "image4.png",
        1999,
        978,
        "#f9fafb"
      ]
    }
  ]
}
[/block]
## Accessing Setup page
As an admin user, login to the CleverTap dashboard
Navigate to Settings > SSO
You will be directed to the SSO setup page

## Configure SAML
1.  Copy the entity id and Assertion Consumer service URL from the CleverTap and paste it in the IdP in Audience URI and Single sign on URL respectively as shown below
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/89d232f-image8.png",
        "image8.png",
        1999,
        540,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
2. Validate the Signature hash algorithm and binding to ensure they are the same in the Idp.
Signature Hash Algorithm: SHA-256
Binding: HTTP POST

3. Provide XML metadata to CleverTap. You can copy the XML metadata and paste it or upload the file.
CleverTap supports dynamic configuration which requires you to enter the IdP Metadata
This IdP Metadata is provided by your identity provider and will look similar to the screenshot shown below (in XML format)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/02c38b1-image11.png",
        "image11.png",
        1999,
        655,
        "#fafafa"
      ]
    }
  ]
}
[/block]
This IdP Metadata is provided by your identity provider and will look similar to the screenshot shown below (in XML format)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bd84fde-image2.png",
        "image2.png",
        1999,
        715,
        "#efeef0"
      ]
    }
  ]
}
[/block]
4. Set your unique domain url
A CleverTap domain, unique to your CleverTap application needs to be provided so that it can be used to authenticate your CleverTap account
Note: Please use a name which is easy to remember as this will be used by your team to login to the CleverTap account
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d6b7fc3-image12.png",
        "image12.png",
        1999,
        296,
        "#fafafb"
      ]
    }
  ]
}
[/block]
This completes your basic setup of SAML SSO. You can test the SSO setup from the CleverTap dashboard to be sure if the setup is done correctly

## Additional Settings
### Login with SSO only
Under the Settings->SSO  you can find the setting "Require all users to login using SSO"
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/849cfd8-image9.png",
        "image9.png",
        1330,
        192,
        "#fafafa"
      ]
    }
  ]
}
[/block]
If you select this option, your team members will NOT be able to login to CleverTap directly. They will be forced to login via the SSO option only.
[block:callout]
{
  "type": "warning",
  "body": "Use this option if your entire team has your domain email id and are setup on your IdP\nIf you have outsourced teams who do not have an email address in your domain, do not select this option as they will not be able to login to CleverTap\nIf you select this option, you will not be able to create a user from the CleverTap dashboard or assign a role to the user, this will have to managed via the Identity Provider."
}
[/block]
### Bind existing users
* If you already have a user setup on CleverTap and want to migrate them to SSO along with their CleverTap roles and account access, select this option
* This will give you the option to download the users list in the following
Copy these user settings and paste them in the custom attributes in your IdP(More on how to setup Custom attributes is given below)
* This will ensure that all users who are currently on CleverTap’s authentication and authorization, will be seamlessly migrated to the IdPs authentication and authorization.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/16cd66a-image3.png",
        "image3.png",
        1460,
        214,
        "#f4f5f7"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/817ce89-Screenshot_2020-03-19_at_2.44.15_PM.png",
        "Screenshot 2020-03-19 at 2.44.15 PM.png",
        912,
        738,
        "#dcdcdd"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "IdP Setup",
  "body": "Below, you will be able to see how to setup access for the following IdPs\n1. Okta\n2. OneLogin\n3. Gsuite\n\nOther IdPs follow similar instructions."
}
[/block]
# Identity Provider setup
Identity Provider (IdP) is the authority that verifies and asserts a user's identity and access to a requested resource (the "Service Provider")
Some examples of IdPs are Okta and GSuite


## Okta Setup

### Creating an Application
All IdPs allow you to create an app which you want to access using SSO
Start the setup by creating a CleverTap app in your IdP setup
Example provided below is for setting up an app with Okta
Select Platform -> Web and Sign on method -> SAML 2.0


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c851bc-image5.png",
        "image5.png",
        1604,
        944,
        "#dee7ee"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a1f27ba-image10.png",
        "image10.png",
        1999,
        1163,
        "#f9fafa"
      ]
    }
  ]
}
[/block]
### Validate settings
Also validate the Signature hash algorithm and binding to ensure they are the same in the Idp.
Signature Hash Algorithm: SHA-256
Binding: HTTP POST

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a77e184-Screenshot_2020-03-24_at_1.12.46_PM.png",
        "Screenshot 2020-03-24 at 1.12.46 PM.png",
        1508,
        992,
        "#f6f6f6"
      ]
    }
  ]
}
[/block]
### Attributes 
You will have to add some attributes for SSO to work .
Attributes for name and email are compulsory in the format given in the screenshot. 
You will need to add an attribute for each accountid you have in CleverTap .
This is so that you can select for each account what role you want to give the users access to at a granular level .
Navigate to Applications->Select your application-> General ->Configure SAML
The following attributes are Mandatory

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5932ccc-Screenshot_2020-03-12_at_3.53.39_PM.png",
        "Screenshot 2020-03-12 at 3.53.39 PM.png",
        1440,
        398,
        "#f6f7f7"
      ]
    }
  ]
}
[/block]
Now if you have 2 Accounts on Clevertap , you will need to add the 2 AcccountId's in the following way . 
You can name them as appuser.[Identifier} , here we have used appuser.MainAccRole and appuser.MaiAccRole1 as examples 
This will tell CleverTap which account a user should have access to.
Click on Next and Finish to complete the process
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8eea100-Screenshot_2020-03-12_at_3.55.31_PM.png",
        "Screenshot 2020-03-12 at 3.55.31 PM.png",
        1440,
        630,
        "#f6f6f6"
      ]
    }
  ]
}
[/block]
Now we need to define what Role should the user have for each account 
Navigate to Directory -> Profile Editor -> Hover on you app and select Profile .
Here you will need to add and define what you want to call these Attributes and what roles can these attributes get .
Click on Add attribute 
* You can name the Variable as "Your Account Name" to ensure that when assigning a name you can understand what account you are assigning the user too .
* ensure you add the Name in Variable as you did earlier for AccountID[MainAccRole and MainAccRole1 from our example].
* Click the check box for enumerated list and add all combinations of roles that you can possibly want to assign your user (you can get these combination from SSO Settings in the CleverTap Dashboard as a CSV and just copy paste 
* **It is important that you always add a attribute member "NoAccess" and provide with an empty "{}" , so that you can select this value when you do not want to give user access to this account .**
* Click Save 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e4a74f-Screenshot_2020-07-21_at_7.59.17_PM.png",
        "Screenshot 2020-07-21 at 7.59.17 PM.png",
        1444,
        1316,
        "#e2e9ee"
      ]
    }
  ]
}
[/block]
Ensure that the Attributes are mapped correctly by going to , this will ensure the correct values are passed to CleverTap 
Directory->Profile Editor -> Click on Profile(For you App) -> Mappings 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ea10dd0-Screenshot_2020-07-21_at_8.03.41_PM.png",
        "Screenshot 2020-07-21 at 8.03.41 PM.png",
        2122,
        1330,
        "#eaf0f5"
      ]
    }
  ]
}
[/block]
Now you need to assign users to your Application.
Navigate to Applications->"Select your application" -> Assignments
Select the User and what role you want to give to the user for each account, if you do not want to give user access to the account select "NoAccess" and Save.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/373db05-Screenshot_2020-03-12_at_4.16.31_PM.png",
        "Screenshot 2020-03-12 at 4.16.31 PM.png",
        1392,
        718,
        "#d6e2eb"
      ]
    }
  ]
}
[/block]
## GSuite Setup
Login to https://admin.google.com/ and login as Admin for you app

### Attributes
Navigate to Users -> Click on More -> Manage Custom Attributes-> Add Custom Attributes
1. You can give Category and description as per your naming policies , recommendation that names should be such that you can identify these custom attributes are for your CleverTap SSO setup.
2. For each account you have with CleverTap , create an equivalent entry here with the name of your account. FOR Example here our App has 2 Accounts and the account names are Account_1 and Account_2 
3. Ensure these attributes are set to "Single value"
4. Save 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c045e8f-Screenshot_2020-03-24_at_11.44.42_AM.png",
        "Screenshot 2020-03-24 at 11.44.42 AM.png",
        2798,
        1006,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
### Creating SAML App
Navigate to Apps-> SAML Apps -> Click on the "+" to create your new CleverTap SAML App
1. Add the ACS URL and Entity ID 
2. Tick the checkbox for Signed Response
3. Name ID as "Basic Information" and "Primary Email" and Name ID format as "Email"
[block:callout]
{
  "type": "info",
  "title": "Signed Response",
  "body": "Ensure the checkbox for Signed Response is selected before proceeding"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81c7366-Screenshot_2020-03-24_at_11.35.13_AM.png",
        "Screenshot 2020-03-24 at 11.35.13 AM.png",
        1740,
        1006,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
### Attribute Mapping
1.  Name and email mapping as depicted in the screen shot is compulsory.
2. For each account you have in CleverTap , you should add the AccountID and select the respective attribute created for this account in the previous step when you created Attributes.
3. Click on Save.
[block:callout]
{
  "type": "info",
  "title": "AccountID",
  "body": "Admins can find all AccountID's in the CleverTap dashboard under Settings->Account"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71265c2-Screenshot_2020-03-24_at_12.00.33_PM.png",
        "Screenshot 2020-03-24 at 12.00.33 PM.png",
        1778,
        1006,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
### IdP Metadata
Now that the setup is done , under Service Provider Details click on "Manage Certificates" .
Download the IdP Metadata .
This is the XML Metadata file that you need to upload in the CleverTap Dashboard -> Settings-> SSO Settings ->Upload XML Metadata
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55d7a57-Screenshot_2020-03-24_at_12.06.41_PM.png",
        "Screenshot 2020-03-24 at 12.06.41 PM.png",
        1778,
        1148,
        "#f4f4f4"
      ]
    }
  ]
}
[/block]
### Assigning to Users and Roles
1. Navigate to Apps-> SAML Apps 
2. Turn the App "ON for everyone"  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1eb85a-Screenshot_2020-03-24_at_12.17.02_PM.png",
        "Screenshot 2020-03-24 at 12.17.02 PM.png",
        2880,
        706,
        "#dee4f4"
      ]
    }
  ]
}
[/block]
3. Navigate to Users and Click on User you want to give Access to.
You will need to navigate to Custom Attributes and the define the role for each account for this user .
4. Take the roleMap JSON that is available in the CSV download(Dashboard->Settings->SSO) for the user-account combination and paste it in respective Attributes for each account.
5. If you do not want to give user access to the account define an empty JSON { } which will indicate that the user has No Access for this Account.


[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If you do want to give user access to an account , you need to define an empty JSON which just empty curly braces -> { }."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/12efc07-Screenshot_2020-03-24_at_12.55.03_PM.png",
        "Screenshot 2020-03-24 at 12.55.03 PM.png",
        2164,
        554,
        "#f6f8fb"
      ]
    }
  ]
}
[/block]
# Sign In using SSO
Once you have completed the setup, you can save the settings. Once you have saved the settings, your login via SSO is complete. On next login, your SSO will be activated


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/314aae0-image6.png",
        "image6.png",
        1999,
        1066,
        "#eef1fa"
      ]
    }
  ]
}
[/block]
## Login
Once your SSO is setup, you can login to CleverTap using the Log in with SSO option

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6521ec4-image1.png",
        "image1.png",
        1999,
        978,
        "#eff1fa"
      ]
    }
  ]
}
[/block]
On clicking on continue, you will be redirected to your IdP login page. Once you login from the IdP, you will be redirected back to your CleverTap dashboard