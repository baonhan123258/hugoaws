---
title : "Test System"
date: 2025-07-10
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

# Hướng dẫn kiểm thử hệ thống website bán điện thoại PHP trên Elastic Beanstalk

## 1. Truy cập website

- Mở đường dẫn **Environment URL** mà Elastic Beanstalk cấp (hoặc domain riêng nếu đã gắn).
- Kiểm tra xem website có hiển thị giao diện bán điện thoại, truy cập ổn định, tốc độ tải nhanh.

## 2. Kiểm tra chức năng upload ảnh sản phẩm

- Đăng nhập admin (nếu có) hoặc vào trang thêm sản phẩm mới.
- Upload thử một file ảnh đại diện cho sản phẩm.
- Kiểm tra ảnh hiển thị đúng trên website (nếu có tích hợp S3/CloudFront, link ảnh phải ra domain CloudFront/S3).

## 3. Kiểm tra database

- Thêm/sửa/xóa sản phẩm hoặc đơn hàng từ website.
- Vào RDS (qua công cụ quản trị MySQL như phpMyAdmin, Adminer, hoặc DBeaver...) kiểm tra dữ liệu có thay đổi đúng trong bảng tương ứng.
- Nếu web báo lỗi kết nối database, kiểm tra lại Security Group và cấu hình `.env`/config PHP.

## 4. Kiểm tra domain và SSL

- Truy cập website qua domain riêng (ví dụ: `https://yourshop.com`).
- Đảm bảo trình duyệt hiển thị ổ khóa xanh (HTTPS) và không cảnh báo bảo mật.

## 5. Kiểm tra tốc độ tải ảnh/file (nếu dùng S3/CloudFront)

- Duyệt trang chi tiết sản phẩm, kiểm tra các link ảnh sản phẩm có dạng CDN/S3 không.
- Test tốc độ tải ảnh từ các vị trí khác nhau (nên rất nhanh nếu dùng CloudFront).

## 6. Xem log và giám sát

- Truy cập Elastic Beanstalk → **Logs** → tải về và kiểm tra file error/access log để phát hiện lỗi.
- Vào CloudWatch kiểm tra metric (CPU, memory, HTTP error, log…).
- Đảm bảo website không có lỗi nghiêm trọng hoặc cảnh báo health ở môi trường Beanstalk.

## 7. Kiểm tra cảnh báo (Alarm) nếu đã cấu hình

- Thử tạo nhiều lượt truy cập hoặc gây lỗi để xem CloudWatch Alarm có gửi email/cảnh báo không.

---

> **Kết quả mong đợi:**  
> - Website truy cập nhanh, bảo mật HTTPS, upload được ảnh, dữ liệu lưu vào DB, hình ảnh tối ưu CDN, log sạch lỗi, domain riêng hoạt động tốt!

---

**Sau khi kiểm thử hoàn tất, bạn đã sẵn sàng nghiệm thu website bán điện thoại PHP chạy thực tế trên AWS!**
