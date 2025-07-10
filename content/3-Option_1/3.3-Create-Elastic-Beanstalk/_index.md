---
title : "Tạo Elastic Beanstalk và Upload File PHP"
date: 2025-06-18
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

## Hướng dẫn từng bước tạo Elastic Beanstalk và upload (deploy) dự án PHP

---

### 1. Truy cập dịch vụ Elastic Beanstalk

- Trên **AWS Console**, nhập **Elastic Beanstalk** vào ô tìm kiếm và chọn **Elastic Beanstalk**.
- Đảm bảo Region vẫn là **ap-southeast-1**.
![Hình: Truy cập Elastic Beanstalk](/images/3.3/image21.png)

---

### 2. Tạo Application mới

- Nhấn **Create Application**.
![Hình: Nhấn Create Application](/images/3.3/image22.png)

- **Application name**: Nhập tên ứng dụng, ví dụ `ban-dien-thoai-php`.
- **Platform**: Chọn **PHP**.
- **Platform branch**: Chọn phiên bản PHP phù hợp (VD: PHP 8.1, PHP 8.2...).
- **Application code**: Chọn **Upload your code**.

---

### 3. Upload file dự án PHP (.zip)

- Nhấn **Choose file** để upload file `.zip` chứa mã nguồn dự án PHP của bạn (hoặc chọn file từ S3 nếu đã upload trước).
- File `.zip` nên đặt các file (ví dụ: `index.php`, `composer.json`, v.v...) ở thư mục gốc, **không bọc thêm một thư mục cha**.
![Hình: Upload file zip dự án PHP](/images/3.3/image23.png)

---

### 4. Cấu hình môi trường

- **Environment name**: Đặt tên (ví dụ: `ban-dien-thoai-env`).
- **Domain**: AWS tự động gợi ý domain (giữ mặc định hoặc chỉnh sửa nếu muốn).
- **Instance type**: Chọn `t2.micro` hoặc nhỏ nhất cho tiết kiệm chi phí.
- **Key pair**: Để trống nếu không SSH, hoặc chọn key nếu muốn SSH vào EC2 instance.

---

### 5. Tạo môi trường và deploy code

- Nhấn **Create environment** để bắt đầu quá trình deploy.
![Hình: Tạo môi trường và deploy](/images/3.3/image24.png)
- Chờ AWS khởi tạo môi trường (khoảng 5-10 phút). AWS sẽ tự động tạo EC2, Load Balancer, cài PHP và triển khai mã nguồn.

---

### 6. Truy cập web sau khi deploy

- Khi hoàn tất, bạn sẽ thấy **Environment URL** (VD: http://ban-dien-thoai-env.eba-xxxxxx.ap-southeast-1.elasticbeanstalk.com).
- Click vào link này để truy cập website PHP vừa deploy.
![Hình: Truy cập website Elastic Beanstalk](/images/3.3/image26.png)

---

### 7. Quản lý, cập nhật dự án (Deploy lại code mới)

- Vào tab **Application versions** trong ứng dụng Elastic Beanstalk.
- Nhấn **Upload and deploy** để upload file `.zip` mới và deploy phiên bản mới nhất.
- Dùng tính năng này mỗi khi cập nhật code cho website.

---

> **Lưu ý:**  
> - Nếu gặp lỗi khi deploy (502, 503, trắng trang), hãy kiểm tra lại cấu trúc file zip, file log tại tab **Logs**.
> - Để cấu hình biến môi trường (database, API key...), vào **Configuration → Software** và thêm environment variables theo nhu cầu.

---

**Bạn đã hoàn thành việc tạo Elastic Beanstalk và deploy dự án PHP thành công! Hãy tiếp tục cấu hình Database, domain, hoặc các dịch vụ AWS khác nếu cần.**
