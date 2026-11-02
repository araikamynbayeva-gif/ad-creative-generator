# Troubleshooting Guide

## Project: Ad Creative Generator

This document records technical issues encountered during the development, deployment, and testing of the Ad Creative Generator application.

It includes the problem description, possible cause, solution, and current status.

## 1. Week 3 — Initial Development

No confirmed technical issues have been recorded yet.

## 2. Week 4 — AWS Infrastructure

Issues related to Terraform, AWS services, networking, and infrastructure deployment will be documented here.

| Issue                  | Possible Cause | Solution | Status  |
| ---------------------- | -------------- | -------- | ------- |
| No issues recorded yet | —              | —        | Pending |

## 3. Week 5 — AI Integration

Issues related to Google Gemini API, Lambda, DynamoDB, and application integration will be documented here.

| Issue                  | Possible Cause | Solution | Status  |
| ---------------------- | -------------- | -------- | ------- |
| No issues recorded yet | —              | —        | Pending |

## 4. General Troubleshooting Guidelines

1. Check AWS service configuration.
2. Verify IAM permissions.
3. Check Terraform deployment logs.
4. Verify API Gateway endpoints.
5. Check Lambda execution logs in Amazon CloudWatch.
6. Verify Gemini API key configuration.
7. Check DynamoDB table settings.

## 5. Conclusion

This document will be updated throughout the project development.

All confirmed issues and their solutions will be recorded to make troubleshooting easier and improve application reliability.

## 6. Week 5 — AI Integration Issues

This section describes potential technical issues related to AI integration and cloud services.

These cases are documented as troubleshooting scenarios and will be updated with actual test results during implementation.

### 6.1 Gemini API Errors

| Problem               | Possible Cause                                   | Recommended Solution                               |
| --------------------- | ------------------------------------------------ | -------------------------------------------------- |
| JSON parsing error    | Gemini returns JSON inside a Markdown code block | Remove Markdown formatting before parsing JSON     |
| 429 Too Many Requests | Gemini API rate limit exceeded                   | Implement retry logic with exponential backoff     |
| Gemini API timeout    | The model takes too long to respond              | Reduce prompt complexity and handle timeout errors |
| Invalid API key       | Incorrect or expired API key                     | Verify the API key in Parameter Store              |

### 6.2 AWS Lambda Issues

| Problem               | Possible Cause                                | Recommended Solution                                       |
| --------------------- | --------------------------------------------- | ---------------------------------------------------------- |
| Lambda timeout        | Function execution exceeds configured timeout | Review execution time and configure an appropriate timeout |
| Cold start delay      | Lambda function has been inactive             | Send a warm-up request before the demonstration            |
| AccessDeniedException | Missing IAM permissions                       | Review Lambda execution role permissions                   |

### 6.3 Parameter Store Issues

| Problem                                   | Possible Cause                      | Recommended Solution            |
| ----------------------------------------- | ----------------------------------- | ------------------------------- |
| Access denied when retrieving a parameter | Missing ssm:GetParameter permission | Add the required IAM permission |
| SecureString decryption failure           | Missing kms:Decrypt permission      | Add the required KMS permission |

### 6.4 API Gateway Issues

| Problem        | Possible Cause                                  | Recommended Solution                                       |
| -------------- | ----------------------------------------------- | ---------------------------------------------------------- |
| HTTP 504 error | Request exceeds API Gateway integration timeout | Reduce processing time or consider asynchronous processing |
| CORS error     | Incorrect CORS configuration                    | Verify allowed origins, methods and headers                |

### 6.5 Monitoring and Prevention

The following practices help prevent recurring issues:

* Monitor Lambda execution logs in Amazon CloudWatch.
* Check Gemini API quota and request limits.
* Verify IAM permissions.
* Validate API responses before displaying results.
* Test error handling before the final demonstration.

**Note:** The scenarios above are potential issues based on the project implementation plan. Actual occurrences and confirmed solutions must be recorded separately.

