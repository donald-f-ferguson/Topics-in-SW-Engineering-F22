# E6156 Topics in SW Engineering (F22) - Cloud Computing: Sprint 2

## Introduction

The [lecture slides from 04-NOV-2022](https://github.com/donald-f-ferguson/Topics-in-SW-Engineering-F22/blob/main/Lectures/08-Lecture-Cool-Stuff/08-Lecture-Cool-Stuff.pdf)
provide an overview of concepts teams will implement in Sprint 2. This README provides additional detail
and guidance.

Sprint 2 has several deliverables:

- The project should call/use a cloud API in its implementation. The professor's sample project uses:
  - [Smarty.com](https://www.smarty.com/) to validate and correct mailing addresses.
  - The [API](https://canvas.instructure.com/doc/api/) to Columbia's CourseWorks, which is based on the Canvas LMS.


- The project must implement login using an OAuth2/OpenID service. The professor's sample project uses
[Google Identity Services.](https://developers.google.com/identity/gsi/web/guides/overview)


- Notification:
  - One of the microservices must emit an event to an SNS topic for resource creation or update. 
  - The project must implement a Lambda function that subscribes to an event and performs an action when an SNS
event triggers the Lambda function.
  - The professor's sample project:
    - Emits an SNS event when a REST API call creates or updates a student resource.
    - The lambda function processes the event and send a Slack message using a webhook.


- Middleware: The microservices implementing event notification and login must use the middleware pattern to drive
the authentication and notification functions.


- Service composition:
  - Sprint 1 built 3 core/atomic microservices.
  - The sprint 2 project must implement a [composite microservice](https://medium.com/microservices-in-practice/microservices-layered-architecture-88a7fc38d3f1) that uses the core microservices. 
  - The professors sample project's: 
    - Implements a microservice that support CRUD for all aspects of a student. For example, for create,
      - The body is a JSON object containing basic student information, contact information, class project, etc.
      - The composite service composes/choreographs/orchestrate the core/atomic services.


- Continuous Integration/Continuous Development:
  - We will eventually use containers for deploying the composite service.  For sprint 2, simply deploy the microservice
using EC2.
  - You will add GitHub actions to automate deployment/redeployment of the composite microservice when a developer
commits and pushes code to the repository.


## Task Specific Information

TBD