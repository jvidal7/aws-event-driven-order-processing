# aws-event-driven-order-processing
Serverless event-driven order processing system on AWS using API Gateway, Lambda, DynamoDB, SQS, EventBridge Pipes, DLQ, CloudWatch, and SNS.

# Event-Driven Order Processing System on AWS

---

## Overview of Project

### Scenario

A growing e-commerce company processes hundreds of customer orders each day. Every order requires several backend actions, including storing the order, validating business rules, processing tasks in the background, retrying failed requests, and notifying the team when problems occur.

The current environment relies on a **single backend server** to manage the entire workflow. As order volume grows, this design introduces several challenges:

- Performance decreases during periods of high traffic
- Failed orders are difficult to identify and troubleshoot
- A single failure can affect the entire request
- Failed processing does not automatically retry
- High-value orders are not handled separately
- The team does not receive automatic alerts when failures occur

The goal of this project is to replace this tightly coupled design with a **serverless, event-driven architecture** where services can operate independently, failures can be isolated, and the system can scale with demand.

---

### My Role as the Cloud Engineer

As the Cloud Engineer, I will design and implement the AWS infrastructure required to modernize the order processing workflow.

The new solution will support:

- Fast customer order submission
- Asynchronous background processing
- Automatic retry handling
- Dead-letter queue processing
- Event-based routing
- Dedicated handling for high-value orders
- Monitoring and failure notifications

This project demonstrates how AWS managed services can be combined to create a scalable and resilient backend for modern e-commerce applications.

---

### Solution

I will build a **serverless, event-driven order processing system using AWS managed services**.

Customer orders will enter the environment through **Amazon API Gateway** and be processed by **AWS Lambda** before being stored in **Amazon DynamoDB**.

**DynamoDB Streams** will detect new order activity and trigger downstream processing. **Amazon SQS** will provide asynchronous message handling, retries, and reliable background processing.

Worker Lambda functions will process orders and update their status, while **Amazon EventBridge Pipes** will identify and route high-value orders through a separate processing path.

Orders that repeatedly fail will be moved to a **Dead-Letter Queue (DLQ)** for investigation. **Amazon CloudWatch** and **Amazon SNS** will provide monitoring and real-time failure notifications.

The final architecture will provide a scalable and reliable order processing system without requiring traditional servers to manage.

---

### About the Project

In this project, I will:

- Build a **frontend order submission application**
- Store orders and track their status in **Amazon DynamoDB**
- Use **Amazon SQS** for asynchronous processing and retries
- Build worker **AWS Lambda** functions to process orders and enforce business rules
- Route high-value orders using **Amazon EventBridge Pipes**
- Configure a **Dead-Letter Queue (DLQ)** for failed messages
- Configure **Amazon CloudWatch Alarms**
- Configure **Amazon SNS** for real-time failure notifications

By the end of this project, I will have a fully operational distributed order processing workflow built with AWS managed services.

---

## Steps To Be Performed 👩‍💻

1. Build the Order Ingestion Layer using **DynamoDB, Lambda, API Gateway, and the frontend**
2. Trigger downstream processing using **DynamoDB Streams**
3. Add **Amazon SQS** for retries and resilient background processing
4. Route high-value orders using **Amazon EventBridge Pipes**
5. Add **Dead-Letter Queue handling**
6. Configure **alerts and observability**

---

## Services Used 🛠

- **Amazon API Gateway** - Provides the order submission endpoint
- **AWS Lambda** - Runs business logic and background workers
- **Amazon DynamoDB** - Stores order information and processing status
- **DynamoDB Streams** - Generates real-time events from database changes
- **Amazon SQS** - Provides queueing, retries, and asynchronous processing
- **Dead-Letter Queue (DLQ)** - Isolates messages that repeatedly fail
- **Amazon EventBridge Pipes** - Filters and routes high-value order events
- **Amazon SNS** - Sends failure notifications
- **Amazon CloudWatch** - Provides metrics, monitoring, and alarms

---

## ➡️ Architectural Diagram

The following diagram shows the architecture for the event-driven order processing system.

![Event-Driven Order Processing Architecture](./images/Event-Driven-Order-architecture-diagram.jpg)

---

## ➡️ Final Results

At the end of this project, I will have a fully functional AWS order processing system that includes:

- **Event-driven order processing with real-time validation**
- **Automatic retry handling**
- **Separate routing for high-value orders**
- **DLQ-based fault isolation**
- **CloudWatch monitoring and SNS alerting**

---
