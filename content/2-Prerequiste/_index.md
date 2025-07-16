---
title : "Prerequisites"
date: 2025-06-18
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

## Preparation Overview

To complete this workshop, you’ll need a valid **AWS account**, a working environment, and some foundational knowledge. This section will guide you through the necessary preparations step by step.

## 1. AWS Account

### Account Requirements:
- A **verified AWS account** (preferably with Free Tier eligibility)
- A **credit/debit card** for account verification (no charges if staying within the Free Tier)
- A **valid email address** to receive notifications from **AWS**

### Free Tier Benefits:
This workshop is designed to run **within the Free Tier** (if you follow the instructions correctly):

| Service              | Free Tier Offering             | Workshop Usage            |
|----------------------|-------------------------------|---------------------------|
| **Elastic Beanstalk**| 750 hrs/month of EC2 t2.micro  | ~1–2 hours                |
| **S3**               | 5GB storage, 20,000 GET reqs   | < 500MB                   |
| **RDS**              | 750 hrs/month of db.t2.micro   | < 1 hour (for testing)    |
| **CloudWatch**       | 10 custom metrics, 5GB logs    | < 1GB logs                |
| **Route 53**         | No free tier, domain cost only (if used) | Optional         |

{{% notice info %}}
**Estimated Cost**: $0 if you stay within the Free Tier; < $1 if limits are exceeded or if a custom domain is used.
{{% /notice %}}

### IAM Permissions

It’s recommended to create a separate IAM user with the following permissions:

#### **Minimal Required Permissions:**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "elasticbeanstalk:*",
        "ec2:*",
        "s3:*",
        "rds:*",
        "cloudwatch:*",
        "iam:PassRole"
      ],
      "Resource": "*"
    }
  ]
}
