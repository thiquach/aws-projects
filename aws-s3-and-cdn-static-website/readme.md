# AWS S3 and CloudFront Static Website Hosting

This project demonstrates how to host a simple static website using Amazon S3 and CloudFront

## Architecture
- Static website assets stored in an Amazon S3 bucket (private)
- Amazon CloudFront distribution configured with S3 as the origin
- Origin access configured so only CloudFront can access S3 content
- End users access the website via the CloudFront distribution URL

## Steps implemented
1. Created an S3 bucket to store static website assets
2. Uploaded HTML, CSS, and image files
3. Configured the bucket to **block public access**
4. Created a CloudFront distribution
5. Set the S3 bucket as the origin for CloudFront
6. Configured **Origin Access Control (OAC)** to restrict direct S3 access
7. Updated S3 bucket policy to allow access only from CloudFront
8. Enabled HTTPS delivery via CloudFront
9. Verified the website via the CloudFront distribution endpoint

## Bucket Policy
See bucket-policy.json

## Website Endpoint
https://sudoku-time-202603231426.s3.us-east-1.amazonaws.com/index.html

## References
https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html
https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html