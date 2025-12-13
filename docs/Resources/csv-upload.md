---
title: CSV Upload
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
With our CSV Upload feature, you can bulk create new [user profiles](doc:user-profiles) in CleverTap by uploading a CSV file with a list of user profiles. You can also use this feature to add or update information for existing user profiles.
[block:callout]
{
  "type": "success",
  "title": "",
  "body": "Only [Admins, Creators, and Approvers](doc:managing-dashboard-access) can use the CSV Upload feature."
}
[/block]
#CSV Upload Steps

Login to your CleverTap account, and then click on the Settings button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7832992-csv1.png",
        "csv1.png",
        1375,
        155,
        "#dbdbe0"
      ],
      "border": true
    }
  ]
}
[/block]
Click on the CSV Uploads button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae44cca-csv2.png",
        "csv2.png",
        1380,
        660,
        "#dfdfe6"
      ],
      "border": true
    }
  ]
}
[/block]
Click on the Import new profiles from CSV button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0496ce7-csv3.png",
        "csv3.png",
        1374,
        206,
        "#d6dbde"
      ],
      "border": true
    }
  ]
}
[/block]
Select the CSV file from your computer, and then click the Upload button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e57290-csv4.png",
        "csv4.png",
        814,
        615,
        "#f4f4f6"
      ],
      "border": true
    }
  ]
}
[/block]
Provide a name for the upload. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e03e7a-csv5.png",
        "csv5.png",
        503,
        173,
        "#eaf0f6"
      ],
      "border": true
    }
  ]
}
[/block]
Your CSV upload will now be processed in near real-time. Once the CSV upload is done processing, the status for that upload will change to completed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af12944-csv6.png",
        "csv6.png",
        1371,
        307,
        "#d9dde0"
      ],
      "border": true
    }
  ]
}
[/block]
#Notes
## General
  * If a new user profile is uploaded, a new user profile is created on the account.
  * If an existing user profile is uploaded, the old user profile is updated with new values.
  * If a user profile property is added that was not present before, a property is created on the user profile.
  * You can upload multiple CSV files at a time, even while existing files are currently processing.
  * Customers can preview up to 15 rows of the file before uploading.
  * Once the upload is completed, the information will be shown for the upload including the Upload Name, Uploaded On date, Uploaded By person, Status of upload, No of Errors (count of rows that were not uploaded due to an error), and No of Records. 

## CSV File Format
  * To see the expected CSV format, please download this [example file](https://s3-eu-west-1.amazonaws.com/eu1-dashboard-uploads3bucket-j4m0n5829hvh/csv-upload/sample-upload-csv.csv).
  * If the file is not a CSV or the file does not comply with CSV standards, the upload will not be allowed.
  * [identity](doc:user-profiles) is a mandatory column in the CSV. 
[block:callout]
{
  "type": "warning",
  "body": "Check that the 'identity' key is always lower case."
}
[/block]
  * You can upload a CSV with a file size of up to 50MB.

## Date Format
* We support uploading date formats based on the following types. All other formats will be treated as a String.
  * dd/MM/yyyy HH:mm:ss
  * MM/dd/yyyy HH:mm:ss
  * yyyy/dd/MM HH:mm:ss
  * yyyy/MM/dd HH:mm:ss
  * dd MMM yyyy HH:mm:ss
  * Unix time 
* If hh:mm:ss are not added, we will default the time to 12:00:00.
* Dates are supported in a 24 hour format.
* If you are uploading a date, the header should mention the name of the property followed by the date format in angular brackets. This format is case sensitive. Please use the exact case as mentioned above. For example, Purchase Date <dd/MM/yyyy hh:MM:ss>.