---
title : "OPTION 1: Website Bán Điện Thoại PHP  với Elastic Beanstalk"
date: 2025-06-18
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

Trong **Option 1**, bạn sẽ thực hành **triển khai một website bán điện thoại viết bằng PHP** lên AWS bằng Elastic Beanstalk.  
Phương án này phù hợp cho người mới, giúp bạn nắm rõ quy trình triển khai web thực tế mà không cần quản lý server thủ công.

**Kiến trúc hệ thống:**
- **Elastic Beanstalk Environment**: Tự động tạo EC2, Load Balancer, và scale web app PHP.
- **S3 Bucket** (tùy chọn): Lưu mã nguồn deploy hoặc hình ảnh sản phẩm.
- **RDS Database** (tùy chọn): Lưu thông tin sản phẩm, đơn hàng, người dùng.

**Luồng hoạt động:**
1. Upload mã nguồn PHP (file .zip) của website bán điện thoại lên Elastic Beanstalk
2. AWS tự động triển khai môi trường (tạo EC2, cấu hình web server, bảo mật, domain tạm thời)
3. Người dùng truy cập website qua link URL public của Beanstalk
4. (Tùy chọn) Kết nối database RDS để lưu thông tin sản phẩm, đơn hàng

![deploy-php-eb-basic](/images/sơdo.png)

---

### Các bước thực hành
3.1. [Tạo RDS Instance (MySQL/PostgreSQL) nếu cần](3.1-Create-RDS-Instance/)  
3.2. [Chỉnh sửa Security Group để mở port cho web/public](3.2-Edit-Security-Group/)  
3.3. [Tạo môi trường Elastic Beanstalk và Upload code website bán điện thoại PHP](3.3-Create-Elastic-Beanstalk/)

---

> **TIP:**  
> Bạn có thể dùng source code PHP thuần hoặc Laravel/CodeIgniter/WordPress cho dự án này.  
> Nên deploy trên môi trường dev/test trước khi đưa lên production thực tế.
