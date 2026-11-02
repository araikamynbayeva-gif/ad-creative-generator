# AWS Cost Analysis

## 1. Overview

This document describes the estimated cloud infrastructure costs of the Ad Creative Generator project.

The application uses AWS serverless services and Google Gemini API to generate advertising content.

The main objective is to keep infrastructure costs as low as possible while maintaining application functionality.

**AWS Region:** us-east-1 (US East - N. Virginia)

## 2. AWS Services and Pricing

The project uses the following AWS services:

| AWS Service                         | Project Usage                            | Main Cost Factors                         |
| ----------------------------------- | ---------------------------------------- | ----------------------------------------- |
| Amazon S3                           | Stores frontend files                    | Storage, requests, data transfer          |
| Amazon CloudFront                   | Delivers frontend content                | Data transfer and HTTP/HTTPS requests     |
| Amazon API Gateway                  | Receives application requests            | Number of API calls and data transfer     |
| AWS Lambda                          | Processes user requests and calls Gemini | Number of requests and execution duration |
| Amazon DynamoDB                     | Stores generation history                | Read/write requests and data storage      |
| AWS Systems Manager Parameter Store | Stores the Gemini API key                | Parameter type and API usage              |

## 3. Free Tier Considerations

AWS provides different Free Tier benefits depending on the account creation date and selected account plan.

The project will use eligible free allowances and AWS credits where available.

| Service            | Free Usage Considerations                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| AWS Lambda         | Includes 1 million requests and 400,000 GB-seconds per month under its free allowance.                                 |
| Amazon API Gateway | Eligible new customers can receive 1 million REST API calls or 1 million HTTP API calls per month for up to 12 months. |
| Amazon S3          | Free usage depends on account eligibility and the applicable offer.                                                    |
| Amazon CloudFront  | Eligible usage allowances depend on the selected pricing plan.                                                         |
| Amazon DynamoDB    | Free allowance includes 25 RCUs, 25 WCUs and 25 GB of storage for eligible Standard tables.                            |

**Important:** Free Tier eligibility and limits must be checked in the AWS Billing and Cost Management console.

New AWS customers joining from July 15, 2025 may receive up to $200 in AWS credits.

## 4. Estimated Project Usage

The project is designed for academic demonstration and a small number of users.

Expected usage:

* A few hundred advertising generation requests during the semester.
* Small frontend files stored in S3.
* Short Lambda execution times.
* Small text records stored in DynamoDB.
* Limited frontend traffic through CloudFront.

The expected workload is relatively small compared with typical production applications.

However, actual costs depend on account eligibility, service configuration, execution duration, and total usage.

## 5. Cost Optimization Strategies

The following strategies help reduce AWS expenses:

1. Use AWS Lambda instead of maintaining continuously running servers.
2. Store only necessary application data in DynamoDB.
3. Keep frontend files small to reduce storage and transfer usage.
4. Use CloudFront caching for static content.
5. Avoid unnecessary NAT Gateway deployment.
6. Use AWS Systems Manager Parameter Store Standard parameters where appropriate.
7. Monitor AWS usage through Billing and Cost Management.
8. Configure AWS Budget alerts to receive notifications about unexpected costs.
9. Delete unused AWS resources after testing.

## 6. External AI Service Costs

The project uses Google Gemini API for advertising text generation.

Gemini API has its own pricing and usage limits, separate from AWS billing.

The actual cost depends on the selected model, input tokens, output tokens, and applicable free quota.

The team will monitor Gemini API usage to avoid exceeding its available quota.

## 7. Potential Additional Costs

Some AWS resources may introduce additional expenses:

| Resource        | Potential Cost                                        |
| --------------- | ----------------------------------------------------- |
| NAT Gateway     | Hourly usage and data processing                      |
| CloudWatch Logs | Log ingestion and storage beyond free allowances      |
| DynamoDB        | Additional reads, writes and storage                  |
| API Gateway     | Requests exceeding eligible free allowances           |
| Lambda          | Requests and execution time exceeding free allowances |
| S3              | Additional storage and requests                       |

These resources should be monitored during development and testing.

## 8. Cost Monitoring

The team will use AWS Billing and Cost Management to monitor infrastructure expenses.

Recommended monitoring actions:

* Check monthly AWS costs.
* Monitor Free Tier usage.
* Configure AWS Budgets.
* Review unexpected charges.
* Remove unused resources.

## 9. Conclusion

The Ad Creative Generator is designed to operate with a low-cost serverless architecture.

AWS Lambda, API Gateway, S3, CloudFront, and DynamoDB provide the required functionality without maintaining dedicated servers.

By monitoring usage, applying eligible free allowances, and avoiding unnecessary infrastructure components, the project aims to minimize cloud expenses during academic development and demonstration.

Actual monthly costs will be verified after deployment.
