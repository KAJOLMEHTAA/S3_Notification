# Notify Users when any Object is uploaded to S3 Bucket

## Introduction:

In this article we will send automated emails to user when an object is uploaded in S3 bucket using S3, SES and lambda function.
We have a secured bucket location in AWS S3 where customers are able to easily upload their diagnostic and other files to us. 
Instead of us having to poll the AWS S3 bucket manually for new uploads, we wanted a way to be notified by email every time a file landed.

Following are the steps:
1. Create a Lambda Function
2. Add Create object setting notification for S3 Bucket
3. Verify email addresses in SES
