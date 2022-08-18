# Notify Users when any Object is uploaded to S3 Bucket

## Introduction:

In this article we will send automated emails to user when an object is uploaded in S3 bucket using S3, SES and lambda function.
We have a secured bucket location in AWS S3 where customers are able to easily upload their diagnostic and other files to us. 
Instead of us having to poll the AWS S3 bucket manually for new uploads, we wanted a way to be notified by email every time a file landed.

Following are the steps:
1. Create a Lambda Function
2. Add Create object setting notification for S3 Bucket
3. Verify email addresses in SES

## Step-by-Step Explanation:

1. Create a Lambda function-
      * Open Lambda Console, Create Function
      * Enter the function Name, Select Python 3.9, create a IAM role with following policies and attach the same to the Lambda function.         AmazonS3FullAccess, AmazonSESFullAccess and CloudWatchLogsFullAccess
      * Click on Create Function, will redirect to the Function page with Basic Lambda Code, copy the below Lambda code and paste it in the console
      * [Refer this File](https://github.com/KAJOLMEHTAA/S3_Notification/blob/main/s3_notification.py)
      
2. Add Create object setting notification for S3 Bucket-
      * Open Amazon S3 Service. Select the Bucket been used for the notification.
      * Hover to the "Properties" Section, Scroll down to "Event notifications". Create Event Notification with All Object Create Events(s3:ObjectCreated:*) and Destination as Lambda Function and copy paste the lambda function ARN.
      * Save changes, S3 bucket configuration is done.
      
3. Verify email addresses in SES-
      * Open Amazon SES Service, hiver to the Verified Identities.
      * Create Identity, Select Email Address and add the email address you want to verify.
      * You will receive a Mail, to respective mail id's. Verify it.
  
## Useful Links
https://mrrishisingh.medium.com/email-s3-objects-as-attachment-7a534e78601c 
