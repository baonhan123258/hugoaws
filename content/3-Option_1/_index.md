---
title : "OPTION 1: Triển khai hệ thống web PHP BÁN ĐIỆN THOẠI với Elastic Beanstalk"
date:  2025-06-18
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

Trong **Option 1**, bạn sẽ thực hành **triển khai một hệ thống web bán hàng PHP cơ bản lên AWS Elastic Beanstalk**.  
Bạn sẽ học cách upload code PHP, khởi tạo môi trường, thiết lập database (RDS), mở port truy cập, và kiểm tra kết quả trên cloud.

**Kiến trúc hệ thống:**
- **Elastic Beanstalk Environment**: Tự động quản lý EC2, Load Balancer, triển khai & scale ứng dụng PHP
- **S3 Bucket (tuỳ chọn)**: Lưu file upload, ảnh sản phẩm, hoặc artifact deploy
- **RDS (Database - tuỳ chọn)**: Lưu trữ dữ liệu, đơn hàng, người dùng...

**Luồng hoạt động:**
1. Upload source code PHP (.zip) lên Elastic Beanstalk
2. AWS tự động tạo môi trường (EC2, Load Balancer, Security Group...)
3. Người dùng truy cập web qua domain/public URL
4. (Tùy chọn) Kết nối Database RDS nếu cần quản lý dữ liệu

![deploy-php-eb-basic](/images/sơdo.png)

---

### Nội dung chi tiết
3.1. [Tạo RDS Instance cho database](3.1-Create-RDS-Instance/) \
3.2. [Chỉnh sửa Security Group cho Elastic Beanstalk](3.2-Edit-Security-Group/) \
3.3. [Tạo môi trường Elastic Beanstalk & Upload file dự án PHP](3.3-Create-Elastic-Beanstalk/)

---

> **Ghi chú:** Nếu bạn l
