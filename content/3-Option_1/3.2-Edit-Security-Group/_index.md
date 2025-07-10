---
title : "Chỉnh sửa Security Group – Cấu hình Inbound Rules"
date: 2025-7-10
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

## Các bước mở cổng truy cập (Edit Inbound Rules) cho Security Group trên AWS

### 1. Truy cập dịch vụ EC2

- Đăng nhập **AWS Console**, tìm kiếm **EC2** và chọn dịch vụ **EC2**.
![Picture8](/images/3.2/image8.png)

---

### 2. Truy cập danh sách Security Groups

- Ở menu bên trái, kéo xuống mục **Network & Security** → nhấn **Security Groups**.
![Picture9](/images/3.2/image9.png)

---

### 3. Chọn Security Group cần chỉnh

- Tìm Security Group mà bạn muốn cấu hình (ví dụ: của EC2, Elastic Beanstalk, hoặc RDS).
- Click vào tên Security Group để xem chi tiết.
![Picture10](/images/3.2/image10.png)

---

### 4. Chỉnh sửa Inbound Rules

- Chuyển sang tab **Inbound rules** (hoặc “Quy tắc vào”).
- Nhấn **Edit inbound rules** để thêm hoặc sửa các rule cho phép kết nối vào.
![Picture12](/images/3.2/image12.png)

---

#### Thiết lập các rule mới (ví dụ cho RDS MySQL):

- **Type**: Chọn **MySQL/Aurora** (hoặc port 3306), hoặc nhập thủ công port bạn cần mở (ví dụ 80, 443, 22…)
- **Protocol**: TCP
- **Port range**: 3306 (hoặc cổng dịch vụ khác, như 5432 cho PostgreSQL)
- **Source**: 
  - Nếu muốn cho phép mọi IP: nhập `0.0.0.0/0` (**CHỈ nên dùng khi test, không khuyến nghị cho production!**)
  - Nếu chỉ cho phép Beanstalk/EC2: nhập Security Group ID hoặc IP cụ thể

![Picture13](/images/3.2/image13.png)
![Picture14](/images/3.2/image14.png)

---
s
### 5. Lưu lại rule vừa thêm

- Sau khi thêm/sửa rule, kéo xuống cuối trang và nhấn **Save rules** để lưu cấu hình.
![Picture16](/images/3.2/image16.png)

---

> **Lưu ý quan trọng:**  
> - Chỉ nên mở cổng cho đúng IP hoặc Security Group, tránh mở toàn bộ Internet trừ khi chỉ test/lab và nhớ xóa sau khi thực hành!
> - Với RDS, nên để source là Security Group của EC2/Elastic Beanstalk để tăng bảo mật.

---

**Bạn đã cấu hình xong Inbound Rules cho Security Group! Sẵn sàng kết nối ứng dụng tới database hoặc các dịch vụ AWS khác.**
