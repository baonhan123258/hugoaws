---
title : "Tạo RDS Instance"
date: 2025-06-18
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

## Hướng dẫn từng bước tạo RDS Database (MySQL) trên AWS

### 1. Mở dịch vụ RDS

- Tại **AWS Console**, nhập từ khóa **RDS** vào ô tìm kiếm và chọn dịch vụ **RDS**.
![Picture1](/images/3.1/image1.png)

---

### 2. Tạo Database Instance mới

- Ở menu bên trái, chọn **Databases** → nhấn **Create database**.
![Picture2](/images/3.1/image2.png)

#### Thiết lập thông tin database:

- **Engine options**: Chọn **MySQL** (nếu bạn dùng Laravel, WordPress hoặc PHP thuần; cũng có thể chọn PostgreSQL nếu cần).
- **Version**: Chọn phiên bản mặc định hoặc mới nhất (ví dụ: MySQL 8.x).
- **Templates**: Chọn **Free tier** (rất quan trọng để không bị tính phí!).
![Picture3](/images/3.1/image3.png)

- **DB instance identifier**: Đặt tên cho instance, ví dụ: `myshop-db`
- **Master username**: Đặt username, ví dụ: `admin`
- **Master password**: Đặt mật khẩu mạnh và nhớ lưu lại
- **DB instance size**: Chọn loại nhỏ nhất được Free Tier hỗ trợ (`db.t3.micro` hoặc `db.t2.micro`)
![Picture4](/images/3.1/image4.png)

---

#### Thiết lập Networking & Kết nối

- **Virtual Private Cloud (VPC)**: Chọn default (hoặc VPC bạn muốn)
- **Subnet group**: Giữ mặc định
- **Public access**:  
  - Nếu bạn cần ứng dụng truy cập từ bên ngoài (Elastic Beanstalk/localhost), chọn **Yes**
  - Nếu chỉ dùng nội bộ AWS, chọn **No**
- **Availability Zone**: Để mặc định hoặc chọn bất kỳ trong ap-southeast-1

- **VPC security group**:  
  - Chọn hoặc tạo Security Group cho phép cổng 3306 (MySQL) hoặc 5432 (PostgreSQL) từ EC2/Elastic Beanstalk hoặc IP của bạn
![Picture5](/images/3.1/image5.png)

---

#### Các tùy chọn nâng cao

- **Initial database name**: Đặt tên database sẽ tạo, ví dụ: `shopdb`
- **Backup**, **Monitoring**, **Encryption**: Để mặc định (bạn có thể tắt hết nếu chỉ làm demo/lab).
- **Deletion protection**: Có thể bỏ chọn để dễ xóa sau khi thực hành xong.

---

### 3. Tạo database

- Kiểm tra kỹ lại thông tin, đảm bảo chọn đúng Free Tier, public access, thông số bảo mật.
- Nhấn **Create database** để bắt đầu tạo RDS instance.
![Picture6](/images/3.1/image6.png)

---

### 4. Sau khi tạo xong

- Chờ AWS tạo xong instance (mất khoảng 5-10 phút).
- **Copy lại endpoint** (hostname), username, password để cấu hình vào ứng dụng PHP (file `.env` của Laravel hoặc config PHP).
- Nếu ứng dụng không kết nối được RDS, kiểm tra lại Security Group đã mở port 3306, cho phép IP hoặc Elastic Beanstalk instance truy cập.
- Khi hoàn thành workshop, hãy xóa RDS instance để tránh bị tính phí.

---

> **Lưu ý:**  
> - Nếu muốn test từ máy cá nhân, bạn phải mở public access và mở port 3306 cho địa chỉ IP máy bạn (hoặc 0.0.0.0/0 nếu chỉ lab và xong sẽ xóa).
> - Hạn chế dùng mật khẩu yếu, tránh đặt thông tin nhạy cảm trong project demo.

---

**Bạn đã hoàn tất tạo RDS Database Instance, sẵn sàng cho bước cấu hình kết nối ứng dụng PHP!**

