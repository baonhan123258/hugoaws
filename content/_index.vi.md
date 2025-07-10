---
title : "Triển khai Website Bán Điện Thoại PHP với AWS Elastic Beanstalk"
date:  2025-06-18
weight : 1 
chapter : false
---

# Workshop: Deploy Website Bán Điện Thoại PHP trên AWS Elastic Beanstalk

### Tổng quan

Workshop này hướng dẫn bạn từng bước triển khai **website bán điện thoại viết bằng PHP** lên AWS, sử dụng các dịch vụ cloud thực tế nhất gồm Elastic Beanstalk, RDS, S3, CloudFront, Route 53, CloudWatch...  
Bạn sẽ học cách chuẩn hóa code, upload source, cấu hình domain, SSL, tối ưu ảnh, giám sát log và tối ưu chi phí vận hành thực tế.

Có 2 lộ trình thực hành:

- **Option 1 (Cơ bản):** Deploy website PHP lên Elastic Beanstalk, kết nối database RDS, mở port truy cập, kiểm thử website thực tế.
- **Option 2 (Nâng cao):** Mở rộng hệ thống, tích hợp domain riêng (Route 53), SSL/HTTPS (ACM), tối ưu ảnh/file bằng S3+CloudFront, giám sát log và cảnh báo với CloudWatch.

**Khuyến nghị:** Nên thực hành Option 1 trước để hiểu cơ bản về cloud web hosting với AWS, sau đó chuyển sang Option 2 để tối ưu hóa, chuyên nghiệp hóa website của bạn.

![deploy-php-eb-landscape](/images/sơdo.png) 

---

### Nội dung workshop

 1. [Giới thiệu tổng quan](1-introduce/)
 2. [Chuẩn bị tài khoản, công cụ, kiến thức](2-prerequiste/)
 3. [OPTION 1: Hệ thống Web PHP Cơ bản](3-Option_1/)
 4. [OPTION 2: Hệ thống Web PHP Nâng cao](4.Option_2/)
 5. [Kiểm thử website](5-Test-System/)
 6. [Dọn dẹp tài nguyên AWS](6-cleanup/)

---

> **TIP:**  
> Bạn có thể dùng bất kỳ source code PHP nào (PHP thuần, Laravel, CodeIgniter, WordPress...) cho workshop này.
