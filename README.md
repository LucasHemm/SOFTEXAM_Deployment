# SOFTExam_Deployment


## Table of Contents

- [SOFTExam\_Deployment](#softexam_deployment)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Services](#services)
    - [List of Microservices](#list-of-microservices)
    - [Back and Frontend](#back-and-frontend)
    - [External services:](#external-services)
  - [Metrics](#metrics)
  - [Docker Compose](#docker-compose)
    - [Overview](#overview)
    - [Dockerhub](#dockerhub)

## Introduction
welcome to the **SOFTExam_Deployment** repository! This repository is part of the MTOGO project. This repository is responsible for deploying the microservices and dependencies such as DB's for the MTOGO project locally, using docker compose. The project consists of 7 microservices with a back and frontend, and this repository is responsible for deploying them all.


## Services

The **MTOGO** project is composed of the following microservices:

### List of Microservices

- **SOFT1Exam_Customer**: Manages customers.
- **SOFT1Exam_Notification**: Manages notifications.
- **SOFT1Exam_OrderAndFeedback**: Manages orders and feedback.
- **SOFT1Exam_Restaurant**: Manages restaurants.
- **SOFT1Exam_Payment**: Handles payment processing.
- **SOFT1Exam_Agent**: Manages agents.
- **SOFT1Exam_User**: Manages user accounts and authentication.

Each of the microservices will have their own independent database, prometheus metrics, and grafana dashboards.

### Back and Frontend

In addition to the microservices, the project also includes the following services:
- **SOFTExam_MTOGO_Backend**: Core backend services that coordinate between all microservices.
- **SOFTExam_MTOGO_Frontend**: Provides the user interface for the application.

### External services:

- **RabbitMQ**: Message broker used for communication between microservices.
- **SendGrid**: Email service used for sending notifications.



## Metrics
Each of the services have a corresponding prometheus metrics configuration, in the repository.


## Docker Compose

### Overview

To run this project, you can use Docker Compose to deploy the services locally. 

```yaml
docker-compose up --build
```
To access the frontend, navigate to the following URL:
```yaml
http://localhost:8087
```
The ports below can be changed depending on which specific service you would like to access. Currently they are set to target the backend.

To access the Swagger UI and endpoints in the backend, navigate to the following URL:
```
http://localhost:8087/swagger/index.html
```

See performance metrics for the backend at:
```
http://localhost:8087/metrics
```
Or use the backend prometheus UI at:
```
http://localhost:9097
```
And the backend grafana UI at:
```
http://localhost:3007
```

### Dockerhub
All the images for the microservices and back and front end can be found on Docker Hub at:
```
https://hub.docker.com/u/lucashemcph
```







