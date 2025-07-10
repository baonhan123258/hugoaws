## What is AWS Elastic Beanstalk?

Elastic Beanstalk là một dịch vụ PaaS của AWS giúp triển khai ứng dụng PHP (cũng như Node.js, Python, Java...) lên cloud một cách dễ dàng mà không phải quản lý hạ tầng server.

### Key Features:
- Không cần quản lý server
- Tự động scaling
- Tích hợp monitoring
- Hỗ trợ nhiều môi trường
- Dễ dàng rollback

---

## Deployment Architecture

### Main Components:

#### 1. Elastic Beanstalk Environment
- Tự động tạo EC2, Load Balancer, Auto Scaling, Security Groups
- Hỗ trợ đa nền tảng

#### 2. Amazon S3
- Lưu trữ source code khi deploy
- Lưu trữ hình ảnh sản phẩm, tài nguyên tĩnh

#### 3. Amazon RDS (khuyến nghị cho database production)
- Quản lý database MySQL/PostgreSQL
- Dễ backup, scale

#### 4. Amazon CloudWatch
- Giám sát log, metric, cảnh báo

---
