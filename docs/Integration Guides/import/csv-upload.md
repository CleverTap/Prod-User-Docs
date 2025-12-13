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

> 📘 CSV Upload Users
>
> Only [Admins, Creators, and Approvers](doc:managing-dashboard-access) can use the CSV Upload feature.

# CSV Upload Steps

Login to your CleverTap account, and then click Setting> CSV Uploads.

<Image title="CSV_Upload_Main.png" alt={1198} className="border" border={true} src="https://files.readme.io/156a515-CSV_Upload_Main.png" />

Click the "Import new profiles from CSV"  button. 

Select the CSV file from your computer, preview, and then click the Upload button.

<Image title="CSV_Upload_Sample_file_preview.png" alt={827} className="border" border={true} src="https://files.readme.io/ea12605-CSV_Upload_Sample_file_preview.png" />

Provide a name for the upload. 

<Image title="CSV_Upload_Sample_file_preview_Name.png" alt={962} className="border" border={true} src="https://files.readme.io/a4dc642-CSV_Upload_Sample_file_preview_Name.png" />

Your CSV upload will now be processed in near real-time. Once the CSV upload is done processing, the status for that upload will change to completed.

<Image title="CSV_Upload_Main_Final.png" alt={1198} className="border" border={true} src="https://files.readme.io/88b4bae-CSV_Upload_Main_Final.png" />

# Notes

## General

* If a new user profile is uploaded, a new user profile is created on the account.
* If an existing user profile is uploaded, the old user profile is updated with new values.
* If a user profile property is added that was not present before, a property is created on the user profile.
* You can upload multiple CSV files at a time, even while existing files are currently processing.
* Customers can preview up to 15 rows of the file before uploading.
* The phone number must have only digits. For example, 01 123 111 0123. It must not contain any string values.
* Once the upload is completed, the information will be shown for the upload including the Upload Name, Uploaded On date, Uploaded By person, Status of upload, No of Errors (count of rows that were not uploaded due to an error), and No of Records. 

## CSV File Format

* To see the expected CSV format, please download this [example file](https://s3-eu-west-1.amazonaws.com/eu1-dashboard-uploads3bucket-j4m0n5829hvh/csv-upload/sample-upload-csv.csv).
* If the file is not a CSV or the file does not comply with CSV standards, the upload will not be allowed.
* [identity](doc:user-profiles) is a mandatory column in the CSV. 

> 🚧
>
> Check that the 'identity' key is always lower case.

* You can upload a CSV with a file size of up to 50MB.

Following is a sample format for the upload file:

![1510](https://files.readme.io/2e166c6-sample_upload_CSV.png "sample_upload_CSV.png")

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
* If you are uploading a date, the header should mention the name of the property followed by the date format in angular brackets. This format is case-sensitive. Be sure to use the exact case as mentioned above. 

> 👍 Date Format Example
>
> A purchase date example is: \<dd/MM/yyyy HH:mm:ss>.
