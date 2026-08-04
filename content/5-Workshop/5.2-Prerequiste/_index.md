---
title : "Prerequiste"
date : 2026-08-02 
weight : 2 
chapter : false
pre : " <b> 5.2. </b> "
---

#### IAM permissions
Add the following IAM permission policy to your user account to deploy and cleanup this workshop.
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "DeployCoreInfrastructure",
            "Effect": "Allow",
            "Action": [
                "cloudformation:*",
                "ec2:*",
                "s3:*",
                "cloudwatch:*",
                "logs:*",
                "sns:*"
            ],
            "Resource": "*"
        },
        {
            "Sid": "ManageEC2InstanceProfileRole",
            "Effect": "Allow",
            "Action": [
                "iam:CreateRole",
                "iam:DeleteRole",
                "iam:PutRolePolicy",
                "iam:DeleteRolePolicy",
                "iam:AttachRolePolicy",
                "iam:DetachRolePolicy",
                "iam:GetRole",
                "iam:ListRoles",
                "iam:CreateInstanceProfile",
                "iam:DeleteInstanceProfile",
                "iam:AddRoleToInstanceProfile",
                "iam:RemoveRoleFromInstanceProfile",
                "iam:GetInstanceProfile"
            ],
            "Resource": "*"
        },
        {
            "Sid": "RestrictPassRoleToEC2Only",
            "Effect": "Allow",
            "Action": "iam:PassRole",
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "iam:PassedToService": "ec2.amazonaws.com"
                }
            }
        }
    ]
}


```

#### Provision resources using CloudFormation

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/1.png)

* Click **Create with new source**.

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/2.png)

* Select and upload the YAML file to create the stack.

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/3.png)

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/4.png)

* Enter the stack name and email address to receive alarm notifications from Amazon SNS.

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/5.png)

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/6.png)

* Add tags to the stack.

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/7.png)

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/8.png)

* After completing the configuration, click **Submit** and wait for the CloudFormation deployment process to finish.

![finish](/aws_internship/images/5-Workshop/5.2-Prerequisite/10.png)

* The resources have been successfully created.

![finish](/aws_internship/images/5-Workshop/5.2-Prerequisite/11.png)