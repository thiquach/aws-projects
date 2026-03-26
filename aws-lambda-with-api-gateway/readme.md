# AWS Lambda with API Gateway (Serverless API)

This project demonstrates how to build a simple serverless API where an AWS Lambda function is invoked via HTTP requests through Amazon API Gateway.

## Architecture

* Amazon API Gateway (REST API) exposes an HTTP endpoint
* Incoming requests are routed to an AWS Lambda function
* The Lambda function processes the request and returns a response
* Logs and execution details are captured in Amazon CloudWatch

## Flow

Client → API Gateway (GET /hello) → Lambda → Response ("Hello from Lambda!")

## Implementation Steps

1. Created an AWS Lambda function that returns "Hello from Lambda!"
2. Configured a REST API in Amazon API Gateway
3. Defined a resource and GET method, and integrated it with the Lambda function
4. Deployed the API Gateway to a stage (e.g. dev)
5. Invoked the API Gateway endpoint to trigger the lambda function
6. Verified the response returned "Hello from Lambda!" successfully

## Security Considerations

* Lambda execution role follows the principle of least privilege
* API Gateway is configured with permissions to invoke the Lambda function
* Logging is enabled for monitoring and debugging

## IAM Policy

Lambda execution role includes:
CloudWatch logging permissions
API Gateway is granted permission to invoke the Lambda function 

## Observability

Request and execution logs are available in Amazon CloudWatch
Used to:
Verify API requests
Debug errors
Monitor Lambda performance


## Key Learnings

* How to build event-driven architectures using API Gateway and Lambda
* Applying IAM roles and permissions for API Gateway to invoke HelloWorld lambda function correctly
* Using CloudWatch for monitoring and debugging

## References
https://docs.aws.amazon.com/lambda/
https://docs.aws.amazon.com/lambda/latest/dg/example_cross_LambdaAPIGateway_section.html
https://docs.aws.amazon.com/apigateway/