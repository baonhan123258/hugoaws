---
title : "Các bước chuẩn bị"
date: 2025-06-18
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

## Tổng quan Chuẩn bị

Để hoàn thành tốt workshop **triển khai web bán điện thoại PHP lên AWS Elastic Beanstalk**, bạn cần chuẩn bị trước một số điều kiện tiên quyết về tài khoản AWS, thiết bị, môi trường làm việc, cũng như kiến thức nền tảng về Cloud, PHP và các thao tác AWS cơ bản. Phần này sẽ hướng dẫn **chi tiết, từng bước** từ đăng ký tài khoản, thiết lập môi trường, đến các kiến thức bạn cần nắm vững trước khi bắt đầu.

---

## 1. Đăng ký và chuẩn bị tài khoản AWS

### 1.1. Yêu cầu về tài khoản:

- **Tài khoản AWS** đã đăng ký và xác thực email, số điện thoại
- **Thẻ tín dụng/ghi nợ** hợp lệ (bắt buộc để kích hoạt Free Tier, AWS chỉ trừ $1 kiểm tra)
- **Email cá nhân** dùng nhận thông báo (nên dùng Gmail/Outlook)
- **Không dùng tài khoản Root để thực hành**, hãy tạo user IAM cho workshop

### 1.2. Free Tier – Miễn phí dịch vụ AWS

AWS cung cấp **gói miễn phí Free Tier** với thời lượng lớn cho các dịch vụ chủ lực như:

| Dịch vụ               | Miễn phí Free Tier                  | Dự kiến sử dụng cho workshop   |
|-----------------------|-------------------------------------|-------------------------------|
| **Elastic Beanstalk** | 750 giờ EC2 t2.micro/tháng          | 1-2 giờ deploy/demo           |
| **S3**                | 5GB storage, 20,000 GET, 2,000 PUT  | < 500MB, vài chục request     |
| **RDS**               | 750 giờ db.t2.micro/tháng           | < 1 giờ test DB               |
| **CloudWatch**        | 10 custom metrics, 5GB log          | < 100MB log                   |
| **Route53**           | Không free, phí domain riêng         | Tùy chọn nếu gắn domain       |

> **Lưu ý:** Luôn chủ động kiểm tra chi phí tại Billing Dashboard. Nếu chỉ làm theo hướng dẫn và xóa resource sau khi thực hành, bạn không bị mất phí.

{{% notice info %}}
**Ước tính chi phí**: $0 nếu dùng trong Free Tier, tối đa ~$1 nếu vượt nhẹ giới hạn hoặc dùng domain.
{{% /notice %}}

### 1.3. Hướng dẫn tạo IAM user

Để bảo mật và dễ quản lý, bạn **không nên dùng tài khoản Root** khi deploy thực tế:

- Vào **IAM** trong AWS Console
- Chọn **Users → Add user**
- Đặt tên, chọn **Programmatic access** & **AWS Management Console access**
- Gán quyền **AdministratorAccess** (hoặc custom policy đủ quyền bên dưới)
- Ghi lại Access Key, Secret Key nếu dùng CLI
- Đăng nhập bằng user mới

#### **Quyền tối thiểu cần thiết (IAM Policy):**
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
