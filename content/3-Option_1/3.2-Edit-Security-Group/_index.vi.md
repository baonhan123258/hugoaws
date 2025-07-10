---
title : "Chỉnh sửa Security Group – Cấu hình Inbound Rules"
date: 2025-7-10
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

## Hướng dẫn từng bước chỉnh sửa Security Group (Edit inbound rules) trên AWS

---

### 1. Truy cập dịch vụ EC2

- Đăng nhập vào **AWS Console**.
- Nhập từ khóa **EC2** vào ô tìm kiếm và chọn dịch vụ **EC2**.
![Hình: Tìm kiếm EC2 trong AWS Console](/images/3.2/image8.png)

---

### 2. Mở danh sách Security Groups

- Trong menu bên trái, tìm phần **Network & Security** và chọn **Security Groups**.
![Hình: Truy cập Security Groups](/images/3.2/image9.png)

---

### 3. Tìm và chọn Security Group cần cấu hình

- Xác định đúng **Security Group** bạn cần chỉnh (ví dụ:  
  `sg-01a4978f83312cfac - default`).
- Nhấp vào tên Security Group để mở chi tiết.
![Hình: Danh sách Security Groups](/images/3.2/image10.png)

---

### 4. Chỉnh sửa Inbound Rules

- Chuyển sang tab **Inbound rules**.
- Nhấn **Edit inbound rules** để thêm hoặc chỉnh sửa rule.
![Hình: Tab Inbound rules và nút Edit](/images/3.2/image12.png)

---

#### Thiết lập rule mới (ví dụ mở port cho RDS hoặc Web):

- **Type**: Chọn dịch vụ phù hợp, ví dụ:  
  - **MySQL/Aurora** (port 3306)  
  - **HTTP** (port 80)  
  - **HTTPS** (port 443)  
  - Hoặc chọn **Custom TCP** để nhập port bạn cần
- **Port range**: Nhập số port cần mở
- **Source**: 
  - Nếu test/lab, có thể dùng `0.0.0.0/0` (mọi IP)  
    (**KHÔNG dùng cho production!**)
  - Nếu bảo mật hơn, nhập IP hoặc Security Group cụ thể (ví dụ: EC2/Beanstalk instance)

![Hình: Thêm rule mới - ví dụ mở port 3306 cho RDS](/images/3.2/image13.png)
![Hình: Chỉnh sửa cột Source cho phép đúng IP hoặc Security Group](/images/3.2/image14.png)

---

### 5. Lưu lại cấu hình

- Sau khi chỉnh xong, kéo xuống cuối trang và nhấn **Save rules** để lưu lại.
![Hình: Save inbound rules](/images/3.2/image16.png)

---

> **Lưu ý quan trọng:**  
> - Chỉ nên mở đúng port, đúng source cần thiết cho mục đích workshop/lab.
> - Nếu mở mọi IP (`0.0.0.0/0`) chỉ nên dùng khi test, nhớ xóa rule này khi kết thúc lab để bảo mật.
> - Với RDS, nên để source là Security Group của EC2/Elastic Beanstalk thay vì mở công khai.

---

**Bạn đã cấu hình xong Inbound Rules cho Security Group! Sẵn sàng kết nối dịch vụ AWS hoặc ứng dụng web tới database/server theo nhu cầu.**
