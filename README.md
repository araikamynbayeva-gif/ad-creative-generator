# Ad Creative Generator

### A brief goes in, ready ad copy comes out.

Ad Creative Generator is a cloud-based AI application that automatically creates advertising content based on user input.

Users provide information about their product, target audience, campaign goal, tone, and platform. The application uses Google Gemini API to generate several advertising text variations.

## 1. Project Objectives

* Automate advertising content creation.
* Generate multiple advertising text variations.
* Save generated content for future reference.
* Provide a simple and user-friendly interface.
* Use cloud services to build a scalable application.

## 2. Technology Stack

| Technology        | Purpose                             |
| ----------------- | ----------------------------------- |
| AWS S3            | Static frontend hosting             |
| AWS CloudFront    | Content delivery and HTTPS          |
| AWS API Gateway   | API request management              |
| AWS Lambda        | Backend processing                  |
| AWS DynamoDB      | Data storage and generation history |
| Google Gemini API | AI text generation                  |
| Terraform         | Infrastructure as Code              |

**AWS Region:** us-east-1

## 3. System Architecture

The application follows a serverless architecture.

Main request flow:

1. User opens the application in a browser.
2. CloudFront delivers the frontend stored in S3.
3. The browser sends a request to API Gateway.
4. API Gateway invokes AWS Lambda.
5. Lambda prepares a prompt and communicates with Gemini API.
6. Generated content is saved in DynamoDB.
7. Results are returned to the frontend.

## 4. Project Structure

```text
ad-creative-generator/
│
├── docs/
│   ├── architecture.md
│   ├── troubleshooting.md
│   └── cost.md
│
├── terraform/
│
├── src/
│   ├── frontend/
│   ├── backend/
│   └── prompt/
│
├── README.md
└── .gitignore
```

*Note: Some directories and files will be added during development.*

## 5. Team Responsibilities

| Role   | Responsibility                  |
| ------ | ------------------------------- |
| Role 1 | Infrastructure and Terraform    |
| Role 2 | Backend and AI Integration      |
| Role 3 | Frontend Development            |
| Role 4 | Documentation and Demonstration |

## 6. Documentation

Project documentation is available in the `docs/` directory.

* `architecture.md` — System architecture and API documentation.
* `troubleshooting.md` — Technical problems and solutions.
* `cost.md` — AWS cost analysis.

## 7. Project Status

The project is currently in the development stage.

Completed:

* Project concept and technology stack selection.
* Initial system architecture.
* Initial documentation.

Planned:

* AWS infrastructure deployment.
* Backend and frontend development.
* Gemini API integration.
* Application testing.
* Final demonstration.

## 8. Team Project

This project is developed as part of the FCT 3305 Cloud Technologies course.
