---
title: CSV uploads (profiles only)
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

CSV Uploads\
Use Case / How-to:\
A. How-to unsubscribe a user from Emails manually using a CSV file:\
Let’s say that you have a list of email addresses or identities from your service provider and you would like to manually unsubscribe them from the Email communication channel.

At CleverTap, the communication preferences are analysed by the following DND flags:\
MSG-push\
MSG-sms\
MSG-email\
MSG-whatsapp\
These communication preferences can be visible here under a user profile:

To unsubscribe a user from email communication channel, set their MSG-email flag to false:\
Create a sample CSV with an identity column, containing email addresses, followed by MSG-email columns, set the flags as false against the identity of the user, a sample file is available on your dashboard under Settings-> CSV uploads.\
Sample:\
identity, MSG-email\
123,false\
456,false

Similarly, if you would like to resubscribe a user manually, the flag can be set to true.\
B. How-to segment a set of users and target them via campaigns using a CSV file:\
If you want to target a set of users, you have to upload a CSV with user property ' user\_set\_1' for these users and then just include these users for the campaign by mentioning this set in: ' Display common properties as' --> ' User Properties' --> ' user\_set\_1' --> Exists.\
You can also assign values to these user properties to achieve the same results. For example, for\
user set 1, the user property ' user\_set\_1' with value ' 1' is uploaded. You can address these users in a similar way by ' Display common properties as' --> ' User Properties' --> ' user\_set\_1' --> equals --> '1'.


Troubleshooting:\
If CSV shows all/partial failed records, please re-verify the CSV format you have created and try matching it with the sample CSV.\
Ensure that identity is the first header and no header is left blank.\
Ensure that all the values under the identity header are entered without any blank values. If any value in the identity header is left blank, that row will fall under error.\
Ensure the prohibited characters are not added: percent (%), greater than sign (>), less than sign (\<), exclamation point (!), pipe (|), ampersand (&), dot(.), colon( : ), semi-colon(;), dollar sign($), single quote('), double quote("), backslash( \ ), and hash(#).\
FAQs:\
Q: I uploaded the one CSV file with users and segmented them based on a user property but at the time of creating the campaign, the number of users showing very less.

A: While calculating campaign reach in the ‘who’ section, we exclude all those users who are not reachable on the specified channel selected or fall under campaign frequency caps. Example, if you estimated the reach on push notifications, all the users that do not have a mobile token will be excluded.

Q: I uploaded a CSV file and all the records were successfully uploaded, however I can only see a few records under find people.\
A: Please check if the CSV file has duplicate identities. When the file is being processed these are counted as individual records but since the same identity would map to the same profile, the upload happens again for the second record and the resultant output on the Find People is fewer profiles than the number of records in the file uploaded.\
Another reason for this could be the time to process the CSV after a successful upload. Depending on the size of data and the time of upload, this affects the overall incoming data from the apps (SDK) and thus it takes some time to upload and process. If you have campaigns planned on a certain CSV, we strongly recommend you to upload the CSV a day prior to the campaign scheduled, preferably during evening/ night.

Q: Can we automate a CSV upload?\
A: Yes, you can use our python script to upload CSV. You will be able to see profile/events, however the CSV will not be visible under Settings > CSV Uploads on the dashboard 


Q: Can we upload blank values for some profiles, if that information is unavailable?\
A: Yes, any value (except the rows under identity header) can be left blank if the information is unavailable, we will process the remaining data for that profile.

Q: Can we upload events via a CSV upload from the dashboard?\
A: No, uploading events via CSV uploads is not possible directly from the dashboard, you can approach SFTP or our python script for this.
























Date Format
We support uploading date formats based on the following types. All other formats will be treated as a String.
dd/MM/yyyy HH:mm:ss 
MM/dd/yyyy HH:mm:ss
yyyy/dd/MM HH:mm:ss
yyyy/MM/dd HH:mm:ss
dd MMM yyyy HH:mm:ss
Unix time
