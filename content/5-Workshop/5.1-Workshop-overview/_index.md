---
title : "Introduction"
date : 2026-08-01 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---

#### Introduction to Splitly

* **Splitly** is a group expense management and bill-splitting platform that helps users track shared expenses, calculate the amounts to be paid among members, and manage transaction history in a transparent manner.

* The system is built using a modern web architecture, including a **React + Vite** frontend, a **Node.js/Express** backend, and a **MongoDB Atlas** database. The application is deployed on AWS to take advantage of the scalability, security, and monitoring capabilities of the cloud computing platform.

* **Amazon EC2** is used to deploy the backend API and frontend application, **Amazon S3** is used to store invoice and receipt files, and **Amazon CloudWatch** supports log collection and system status monitoring. Meanwhile, **Amazon VPC** and **Security Groups** provide secure network connectivity between the system components.

#### System Overview

The Splitly system consists of the following main components:

* **Frontend Application**

  * Built with React and Vite.
  * Provides a user interface for managing groups, expenses, and settlement statuses.

* **Backend Application**

  * Uses Node.js and Express to provide REST APIs.
  * Handles business logic such as group creation, expense management, settlement calculation, and user authentication.

* **Database**

  * Uses MongoDB Atlas to store user information, group data, transactions, and payment history.

* **Cloud Storage**

  * Amazon S3 is used to store images, electronic invoices, and receipt files uploaded by users.

* **Monitoring & Security**

  * Amazon CloudWatch is used to collect logs and monitor the operational status of the system.
  * Amazon VPC, Security Groups, and AWS IAM help control network connectivity and access permissions for AWS resources.

The upgraded architecture improves Splitly's **performance**, **security**, and **scalability** by separating the frontend and backend.

+ The frontend is stored in **Amazon S3** and distributed through **Amazon CloudFront**.
+ **Amazon Route 53** provides domain name management.
+ **AWS Certificate Manager** provides SSL/TLS certificates for secure HTTPS connections.
+ **AWS WAF** helps protect the application from suspicious and malicious web requests.
+ The backend continues to run on **Amazon EC2** and connects to **MongoDB Atlas**.

This architecture provides a foundation for scaling the backend and integrating additional AWS services in the future without requiring major changes to the entire system.