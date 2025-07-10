---
title : "Triển khai (Deploy) Dự án PHP lên Elastic Beanstalk"
date: 2025-06-18
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

## Hướng dẫn từng bước triển khai (deploy) dự án PHP lên Elastic Beanstalk

---

### 1. Truy cập Elastic Beanstalk

- Tại **AWS Console**, nhập **Elastic Beanstalk** vào ô tìm kiếm và chọn dịch vụ **Elastic Beanstalk**.
- Đảm bảo Region vẫn là **ap-southeast-1**.
![Hình: Truy cập Elastic Beanstalk](/images/3.3/image21.png)

---

### 2. Tạo Application mới

- Nhấn **Create Application**.
![Hình: Nhấn Create Application](/images/3.3/image22.png)

- **Application name**: Đặt tên cho ứng dụng, ví dụ: `web-ban-dien-thoai`.
- **Platform**: Chọn **PHP**.
- **Platform branch**: Chọn phiên bản PHP phù hợp với dự án (ví dụ: PHP 8.1, PHP 8.2).
- **Application code**: Chọn **Upload your code**.

---

### 3. Upload file dự án PHP (.zip)

- Nhấn **Choose file** để upload file `.zip` mã nguồn PHP của bạn (có thể chọn từ máy tính hoặc từ S3 nếu đã upload trước).
- **Chú ý**: File zip cần chứa toàn bộ mã nguồn ở thư mục gốc, KHÔNG có thư mục cha lồng bên ngoài.
![Hình: Upload file zip dự án PHP](/images/3.3/image23.png)

---

### 4. Cấu hình môi trường triển khai

- **Environment name**: Đặt tên cho môi trường, ví dụ: `web-ban-dt-env`.
- **Domain**: AWS tự sinh domain (có thể giữ mặc định hoặc chỉnh lại).
- **Instance type**: Chọn loại nhỏ nhất (t2.micro hoặc t3.micro) để tiết kiệm phí.
- **Key pair**: Có thể để trống nếu không cần SSH vào EC2, hoặc chọn key pair nếu muốn SSH.

---

### 5. Deploy & khởi tạo môi trường

- Nhấn **Create environment** để bắt đầu deploy.
![Hình: Tạo môi trường Elastic Beanstalk](/images/3.3/image24.png)

- Chờ AWS khởi tạo môi trường và deploy code (khoảng 5-10 phút).
![Hình: Quá trình khởi tạo môi trường](/images/3.3/image25.png)

---

### 6. Truy cập website PHP sau khi deploy

- Khi deploy thành công, bạn sẽ thấy đường dẫn **Environment URL** (VD: http://web-ban-dt-env.eba-xxxxxxx.ap-southeast-1.elasticbeanstalk.com).
- Click vào link để kiểm tra ứng dụng đã chạy.
![Hình: Truy cập website trên Elastic Beanstalk](/images/3.3/image26.png)

---

### 7. Cập nhật (re-deploy) phiên bản mới

- Khi muốn deploy phiên bản code mới:
  - Truy cập tab **Application versions**.
  - Nhấn **Upload and deploy** để tải lên file zip mới và triển khai.
- Có thể deploy lại bất kỳ khi nào cần cập nhật code.

---

> **Lưu ý:**  
> - Nếu gặp lỗi 502/503, kiểm tra lại cấu trúc file zip và xem log tại tab **Logs**.
> - Để cấu hình biến môi trường (database, API key, v.v...), vào **Configuration → Software** và thêm/cập nhật environment variables.

---

**Bạn đã hoàn thành việc triển khai (deploy) dự án PHP lên Elastic Beanstalk thành công! Tiếp tục cấu hình database, domain hoặc bảo mật nếu cần thiết.**
