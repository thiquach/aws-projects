# Invoke a AWS Lambda Function from a S3 File Upload Trigger

This project demonstrates how to build an event-driven workflow where an AWS Lambda function is triggered by file uploads to an Amazon S3 bucket.

## Architecture

* A private Amazon S3 bucket ready to store an uploaded object
* S3 is configured to send ObjectCreated event notifications
* An AWS Lambda function is triggered upon file upload to S3
* The Lambda function:

  * Extracts the bucket name and object key from the event
  * Retrieves object metadata (e.g. content type) using S3 API
  * Logs relevant details about the object's content type to Amazon CloudWatch

## Flow

Upload File → S3 Bucket → Lambda Trigger → Process Metadata → CloudWatch Logs

## Implementation Steps

1. Created a private S3 bucket and prepared a file for upload
2. Created an AWS Lambda function in the same region as the S3 bucket
3. Implemented the Lambda handler (`lambdaS3Trigger.py`) to process S3 events
4. Configured S3 event notifications to trigger the Lambda function on object creation
5. Assigned an IAM role to Lambda with permissions to read from S3
6. Uploaded files to S3 to trigger the Lambda function
7. Verified execution via Lambda monitoring and CloudWatch logs

## Security Considerations

* S3 bucket remains private (no public access)
* Lambda execution role follows least privilege principle
* Permissions limited to:

  * `s3:GetObject`
  * CloudWatch logging

## IAM Policy

See lambda-execution-role-resource-based-policy.json

## Observability

* Logs are captured in Amazon CloudWatch
* Useful for:

  * Debugging event payloads
  * Verifying object metadata retrieval
  * Monitoring Lambda execution

## Key Learnings

* How to build event-driven architectures using S3 and Lambda
* Configuring S3 event notifications
* Parsing S3 event payloads in Lambda
* Applying IAM roles and permissions correctly
* Using CloudWatch for monitoring and debugging

## References
https://docs.aws.amazon.com/lambda/
https://docs.aws.amazon.com/lambda/latest/dg/example_serverless_S3_Lambda_section.html
https://docs.aws.amazon.com/AmazonS3/latest/userguide/EventNotifications.html