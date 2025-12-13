---
title: Data Export to AWS S3_WIP hackathon
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
REVIEW EXISTING LIVE PAGE AND ASSESS WHAT INFO CAN BE INCORPORATED FROM THE HACKATHON COPY.

Data Export to AWS S3\
Overview\
The data export feature provides the capability to bulk export your CleverTap event data to your AWS S3 bucket. You can use this for analysis in BI tools or for storage in your data warehouse for analysis in the future.

Initiate an Export\
To initiate an export:\
Navigate to Settings > Partners > Exports > Activity Log.\
Click + Create Export.
























Setup Steps







































Create an AWS S3 Bucket\
Depending on your CleverTap account settings, we host your data in Europe (EU), United States (US), Singapore (SG), or India (IN).

Once you create an account in the same region as your CleverTap data hosting region, the next step is to create your S3 bucket in that same region.

Region Example\
If your CleverTap account uses AWS EU (Ireland), then you will have to create an S3 bucket in the AWS EU (Ireland) region.

Log in to your AWS account, then search for S3 in the AWS services box. Click S3 in the search results.

[https://files.readme.io/f30c5a0-s3-1.png](https://files.readme.io/f30c5a0-s3-1.png)

Click the Create bucket button.

Enter a bucket name, region, and other settings you may need to configure.

Complete your setup by selecting your logging, versioning, and encryption preferences. For this integration, you do not need to make any modifications to the default settings; however, you should check your internal organization's policies to see if you need to modify any of these settings.

Click Next.

Click Next.\
Click the Create bucket button.\
The bucket you just created should now show up in your S3 console. Note the name of your new bucket since you will need it for the next step below.\
[https://files.readme.io/928170d-s3-7.png](https://files.readme.io/928170d-s3-7.png)

Create an API Key for Your S3 Bucket\
This step demonstrates how to create an AWS API key that has write access to the bucket we created in the previous step above. CleverTap uses this API key to export data to your S3 bucket.

Click on your account name on the top right of the AWS console.

Click My Security Credentials.

Click the Next:Tags button.


2. Tags is optional - Please check your company policies\ &lt;rest is same till Data Exports&gt;\
   Choose Export Frequency\
   One time: Single export for the export type selected. You can export data up to the last 60 days.\
   Recurring: Setup a recurring export which exports all the new events/user profiles captured in the last window.\
    You can export new events as frequently as every four hours and up to once every 24 hours.\
    You can export new profiles once every 24 hours.\
   Note :If there is a scheduled recurring profile export, you must stop it to run a one-time profile export as running a recurring export and a one time profile export can cause discrepancies in the data which is exported.\ &lt;rest is same till below&gt;\
   JSON file format\
   \{\
      "ts":20210507125550,\
      "eventName":"Added To Cart",\
      "profile":\{\
         "all\_identities":[  
            "manasa+new@clevertap.com"  
         ],\
         "platform":"Android",\
         "email":"[manasa+new@clevertap.com](mailto:manasa+new@clevertap.com)",\
         "push\_token":"fcm:e5xjXdEkK-E:APA91bE0u5HrasaUqSDU5ValCtkeYxHxoWKV6hH-LYJyBj8JQYLaWxLFD5DW8-cy-pd2PbPdB8G4iDNsIB9A1NSfd9p\_o4nVWCoHSDqBYCWFZyAetua40LEigiWWvtvsxt6POuT1bjNw"\
      },\
      "deviceInfo":\{\
         "make":"google",\
         "model":"Android SDK built for x86",\
         "appVersion":"2.4.2.2",\
         "sdkVersion":"30803",\
         "osVersion":"8.0.0",\
         "browser":"MobileApp",\
         "dpi":420,\
         "dimensions":\{\
            "width":65,\
            "height":108,\
            "unit":"mm"\
         }\
      },\
      "eventProps":\{\
         "CT Source":"Mobile",\
         "ct\_app\_version":"2.4.2.2",\
         "Product name":"Nautica Chronograph Watch",\
         "ct\_os\_version":"8.0.0",\
         "Vendor":"An Asgardian",\
         "ct\_network\_carrier":"Android",\
         "ct\_sdk\_version":30803,\
         "CT Session Id":1620372146\
      }\
   }

XML File Format
























































    



20210507123714





    










Added To Cart












    









        















manasa+new@clevertap.com

















        









Android











        






manasa+new@clevertap.com








        











fcm:e5xjXdEkK-E:APA91bE0u5HrasaUqSDU5ValCtkeYxHxoWKV6hH-LYJyBj8JQYLaWxLFD5DW8-cy-pd2PbPdB8G4iDNsIB9A1NSfd9p_o4nVWCoHSDqBYCWFZyAetua40LEigiWWvtvsxt6POuT1bjNw

        





google







        






Android SDK built for x86








        











2.4.2.2













        











30803













        










8.0.0












        










MobileApp










        




420






        












            






65








            







108









            





mm







        













    













    












        







            




CT Source






            






Mobile








        








        







            




ct_app_version






            






2.4.2.2








        








        







            




Product name






            






Columbia Black Shirt








        








        







            




ct_os_version






            






8.0.0








        








        







            




Vendor






            






The Wizard of Oz








        








        







            




ct_network_carrier






            






Android








        








        







            




ct_sdk_version






            






30803








        








        







            




CT Session Id






            






1620371228








        








    























CSV File Format

Amazon EventBridge

How to establish the integration\
Establishing AWS integration is a 2 step process\
Part I: Configuring CleverTap event source\
Login to your CleverTap account\
Navigate to Settings -> Partners -> Exports\
Click on the AWS Amazon icon\
Copy your AWS account information: Click Copy to copy your AWS account number to your clipboard.

Paste the AWS account ID that you copied in above in the AWS Account ID field.\
In the AWS region drop-down box, select the AWS region to receive events.\
Click Save Credentials. The event source name appears in AWS EventBridge. It may take a couple of minutes for the settings to be saved.\
Once the credentials are saved, the option is shown to create a campaign from the same page. 


Part II: Associating event source to designated event bus in AWS console\
To establish an event connection to Amazon EventBridge, your CleverTap event source needs to be associated with the event bus in Amazon EventBridge. The CleverTap event source created in Part I above appears in the Amazon EventBridge > Partner events sources. You can then select the event source name and associate it with an event bus.\
Once a connection is established, you can set your rules and targets for Amazon EventBridge to redirect events to an AWS service. For more details, see the Amazon EventBridge documentation.

Sending via Campaigns

Event properties shall not be available for past behavior segmentation

GCP

This feature can be configured to export data for all events or specific types of events that you select. You also have the option to set up automatic recurring exports ranging from every 4 hours to every 24 hours.\
It can also be used to export all the user profiles as a one time or recurring exports for every 24 hours. 