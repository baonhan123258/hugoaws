---
title : "Prerequisites"
date: 2025-06-18
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

## Tổng quan Chuẩn bị

Để hoàn thành workshop này, bạn cần chuẩn bị đầy đủ tài khoản **AWS**, môi trường làm việc, và kiến thức nền tảng phù hợp. Mục này sẽ hướng dẫn chi tiết từng bước chuẩn bị.

## 1. Tài khoản AWS

### Yêu cầu tài khoản:
- **Tài khoản AWS** đã xác thực (nên có Free Tier)
- **Thẻ tín dụng** dùng xác thực (không bị trừ phí nếu dùng trong Free Tier)
- **Email hợp lệ** để nhận thông báo từ **AWS**

### Miễn phí Free Tier:
Workshop này thiết kế để chạy **trong Free Tier** (nếu dùng đúng hướng dẫn):

| Dịch vụ               | Free Tier                  | Dùng cho workshop         |
|-----------------------|---------------------------|---------------------------|
| **Elastic Beanstalk** | 750 giờ/tháng EC2 t2.micro| ~1-2 giờ                  |
| **S3**                | 5GB storage, 20,000 GET   | < 500MB                   |
| **RDS**               | 750 giờ/tháng db.t2.micro | < 1 giờ (test)            |
| **CloudWatch**        | 10 custom metrics, 5GB logs| < 1GB logs               |
| **Route53**           | Không free, chỉ phí domain (nếu dùng) | Tùy chọn         |

{{% notice info %}}
**Dự kiến chi phí**: $0 nếu dùng Free Tier, < $1 nếu vượt giới hạn hoặc dùng domain riêng.
{{% /notice %}}

### Phân quyền IAM

Nên tạo user riêng với quyền sau:

#### **Quyền tối thiểu:**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    { "Effect": "Allow", "Action": [
        "elasticbeanstalk:*",
        "ec2:*",
        "s3:*",
        "rds:*",
        "cloudwatch:*",
        "iam:PassRole"
    ], "Resource": "*" }
  ]
}
