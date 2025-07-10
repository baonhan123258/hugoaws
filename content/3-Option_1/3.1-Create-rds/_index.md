---
title : "Tạo RDS Instance"
date: 2025-07-10
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

## Các bước tạo RDS (MySQL) trên AWS

### 1. Truy cập dịch vụ RDS

- Đăng nhập **AWS Console**, gõ **RDS** vào ô tìm kiếm và chọn dịch vụ **RDS**.
![Picture1](/images/3.1/image1.png)

---

### 2. Tạo Database Instance mới

- Ở trang **Amazon RDS**, chọn **Databases** ở menu trái, nhấn **Create database**.
![Picture2](/images/3.1/image2.png)

#### Thiết lập thông tin Database:

- **Engine options**: Chọn **MySQL** (hoặc PostgreSQL nếu project yêu cầu).
- **Version**: Chọn phiên bản mặc định hoặc bản mới nhất (gợi ý: MySQL 8.x).
- **Templates**: Chọn **Free tier** (nếu dùng cho học tập/demo).
![Picture3](/images/3.1/image3.png)

- **DB instance identifier**: Nhập tên định danh, ví dụ: `myshop-db`
- **Master username**: Nhập tên user (gợi ý: `admin`)
- **Master password**: Đặt password mạnh, lưu lại để dùng kết nối trong PHP.
- **DB instance size**: Chọn loại nhỏ nhất hỗ trợ Free Tier (`db.t3.micro` hoặc `db.t2.micro`).
![Picture4](/images/3.1/image4.png)

---

#### Thiết lập Networking & Connectivity:

- **Virtual Private Cloud (VPC)**: Chọn default (hoặc VPC bạn muốn)
- **Subnet group**: Giữ mặc định
- **Public access**:  
  - Nếu cần truy cập từ bên ngoài (local, Beanstalk), chọn **Yes**
  - Nếu chỉ dùng nội bộ VPC, chọn **No**
- **Availability Zone**: Để mặc định hoặc chọn zone bất kỳ ở Singapore

- **VPC security group**:  
  - Tạo mới hoặc chọn security group đã cho phép cổng 3306 (MySQL) hoặc 5432 (PostgreSQL) cho IP/EC2/Elastic Beanstalk
![Picture5](/images/3.1/image5.png)

---

#### Các thiết lập khác:

- **Initial database name**: Đặt tên CSDL sẽ tạo (ví dụ: `shopdb`)
- **Backup**, **Monitoring**, **Encryption**: Để mặc định hoặc tắt nếu chỉ dùng lab.
- **Deletion protection**: Có thể bỏ check nếu muốn xóa nhanh khi xong lab.

---

### 3. Tạo Database

- Kiểm tra lại các thông tin đã nhập.
- Nhấn **Create database** để bắt đầu khởi tạo RDS instance.
![Picture6](/images/3.1/image6.png)

---

#### **Lưu ý sau khi tạo xong:**
- Ghi lại endpoint (host), username, password để dùng trong file cấu hình của PHP/Laravel.
- Nếu project PHP/Laravel trên Elastic

