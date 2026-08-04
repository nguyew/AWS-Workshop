---
title: "Week 5 Worklog"
date: 2026-06-19
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Build a solid understanding of the AWS Shared Responsibility Model and the division of security responsibilities between AWS and customers.
* Gain practical knowledge of AWS Identity and Access Management (IAM) for managing identities and controlling access to AWS resources.
* Practice creating and managing IAM users, groups, roles, and permissions to implement secure access control.
* Learn the fundamental concepts of authentication, authorization, and encryption key management using AWS security services.
* Explore AWS services that support centralized account administration, identity management, and security governance across multiple AWS accounts.

### Tasks to be carried out this week:

| Day | Tasks                                                                                                                                                                                                                                                                                                                      | Start Date | Completion Date | Resources                                                          |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------ |
| Mon | - Learn about the AWS Shared Responsibility Model <br> - Learn about AWS IAM components: <br>  + Root Account <br>  + IAM User <br>  + IAM Group <br>  + IAM Policy <br>  + IAM Role <br> - **Hands-on Lab:** <br>  + Create IAM Groups and IAM Users <br>  + Create IAM Roles <br>  + Assume Roles                        | 15/06/2026 | 15/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Tue | - Learn about IAM authorization mechanisms <br> - Learn about IAM Conditions: <br>  + IP Address Restrictions <br>  + Time-based Access Restrictions <br> - **Hands-on Lab:** <br>  + Create EC2 Administrator User <br>  + Create RDS Administrator User <br>  + Create Administrator Group <br>  + Configure Switch Role | 16/06/2026 | 16/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Wed | - Learn about Permission Boundaries <br> - Learn about the Principle of Least Privilege <br> - **Hands-on Lab:** <br>  + Create Permission Boundary Policies <br>  + Create Restricted IAM Users <br>  + Verify Permission Restrictions                                                                                    | 17/06/2026 | 17/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Thu | - Learn about Access Keys and AWS CLI Authentication <br> - Learn about IAM Roles for Amazon EC2 <br> - Learn about Amazon Cognito: <br>  + User Pools <br>  + Identity Pools <br> - **Hands-on Lab:** <br>  + Use Access Keys <br>  + Attach IAM Roles to EC2 Instances                                                   | 18/06/2026 | 18/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Fri | - Learn about AWS Organizations <br> - Learn about Service Control Policies (SCP) <br> - Learn about AWS Identity Center (SSO) <br> - Learn about AWS KMS and Customer Managed Keys (CMK) <br> - Learn about AWS Security Hub and AWS security best practices                                                              | 19/06/2026 | 19/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |


### Week 5 Achievements:

* Develop a comprehensive understanding of the AWS Shared Responsibility Model and the security responsibilities shared between AWS and its customers.

* Gain in-depth knowledge of AWS Identity and Access Management (IAM) and its role in controlling access to AWS resources.

* Explore the fundamental components of AWS IAM, including:

  * Root Account
  * IAM User
  * IAM Group
  * IAM Policy
  * IAM Role

* Understand the Principle of Least Privilege (PoLP) and learn how to apply it to minimize unnecessary permissions while maintaining secure access.

* Learn how IAM policy evaluation works, including the precedence of Explicit Deny over Allow statements.

* Explore the use of IAM Conditions to implement fine-grained access control based on:

  * IP address restrictions
  * Time-based access policies

* Understand the concepts of Assume Role and Switch Role, and how they facilitate secure cross-account and role-based access.

* Learn how Permission Boundaries define the maximum permissions that can be granted to IAM users and roles.

* Gain an understanding of Access Keys, their role in programmatic access, and the best practices for securing them.

* Learn why assigning IAM Roles to Amazon EC2 instances is a more secure approach than storing long-term Access Keys.

* Explore the core components of Amazon Cognito, including:

  * User Pools
  * Identity Pools

* Understand how AWS Organizations enables centralized management and governance of multiple AWS accounts.

* Learn the purpose of Service Control Policies (SCPs) and how they enforce permission boundaries across AWS Organizations.

* Explore how AWS Identity Center simplifies authentication and enables Single Sign-On (SSO) across AWS accounts and applications.

* Gain knowledge of AWS Key Management Service (KMS) and learn how Customer Managed Keys (CMKs) are used to secure sensitive data.

* Understand the role of AWS Security Hub in centralizing security findings, monitoring compliance, and improving overall cloud security posture.

* Successfully complete hands-on labs involving:

  * Creating IAM Users and IAM Groups
  * Creating and assuming IAM Roles
  * Configuring administrator users for EC2 and RDS
  * Implementing IAM Conditions
  * Setting up Switch Role
  * Creating Permission Boundaries
  * Managing Access Keys
  * Attaching IAM Roles to EC2 instances

* Develop the ability to design and implement secure identity and access management (IAM) solutions by following AWS security best practices and governance principles.