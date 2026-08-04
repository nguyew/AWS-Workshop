---
title : "Các bước chuẩn bị"
date : 2026-08-02 
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

#### IAM permissions
Gắn IAM permission policy sau vào tài khoản aws user của bạn để triển khai và dọn dẹp tài nguyên trong workshop này.
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

#### Khởi tạo tài nguyên bằng CloudFormation

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/1.png)

+ Nhấn create with new source

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/2.png)

+ Chọn load file yaml để tạo stack

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/3.png)

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/4.png)

+ Nhập tên stack và email để nhận alert từ sns alarm notification

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/5.png)

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/6.png)

+ Thêm tag

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/7.png)

![create stack](/aws_internship/images/5-Workshop/5.2-Prerequisite/8.png)

+ Sau khi xong bấm submit va đơi quá trình triển khai CloudFormation hoàn thành.

![finish](/aws_internship/images/5-Workshop/5.2-Prerequisite/10.png)

+ Các tài nguyên đã được tạo

![finish](/aws_internship/images/5-Workshop/5.2-Prerequisite/11.png)