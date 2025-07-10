---
title : "Test Hệ thống"
date: 2025-07-10
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

## 1. Upload file ảnh sản phẩm lên website

- Đăng nhập admin hoặc truy cập chức năng thêm/sửa sản phẩm.
- Upload thử một ảnh sản phẩm.
![Picture100](/images/5/image100.png)

---

## 2. Kiểm tra ảnh hiển thị trên website

- Xem lại trang chi tiết sản phẩm.  
- Ảnh đã upload phải hiển thị đúng, có thể kiểm tra link ảnh (nếu dùng S3/CloudFront, đường dẫn phải trỏ về domain CDN hoặc S3).

---

## 3. Kiểm tra lưu trữ database

- Thêm/sửa/xóa sản phẩm, đơn hàng… trên web.
- Dùng công cụ quản lý MySQL (phpMyAdmin, Adminer, DBeaver…) hoặc AWS RDS Console để kiểm tra dữ liệu thực tế được lưu vào bảng.
- Nếu website báo lỗi database, kiểm tra lại Security Group và file cấu hình kết nối.

---

## 4. Kiểm tra domain và SSL

- Truy cập website qua domain riêng (https://yourshop.com).
- Đảm bảo trình duyệt có ổ khóa xanh (HTTPS).

---

## 5. Kiểm tra tốc độ tải ảnh (S3/CloudFront)

- Kiểm tra link ảnh sản phẩm trên web, đảm bảo tải nhanh, link dạng CDN/S3.
- Duyệt nhiều trang sản phẩm để cảm nhận sự tối ưu.

---

## 6. Kiểm tra CloudWatch logs & metrics

- Vào Elastic Beanstalk → Logs → Request logs để xem file log.
- Vào **CloudWatch** → Dashboards để xem số liệu realtime (CPU, Memory, HTTP errors…).
![Picture108](/images/5/image108.png)
![Picture109](/images/5/image109.png)
- Nếu có cấu hình alarm, thử thao tác lỗi để test cảnh báo (email/SNS).

---

## 7. Tổng hợp kết quả kiểm thử

- Web chạy ổn định, truy cập được qua domain riêng, bảo mật HTTPS.
- Upload, hiển thị ảnh sản phẩm thành công.
- Thao tác với dữ liệu (thêm, sửa, xóa sản phẩm, đơn hàng) thành công, database lưu đúng.
- Log sạch lỗi hoặc phát hiện lỗi dễ kiểm tra qua CloudWatch/Logs.

---

> **TIP:**  
> Nên kiểm thử cả trên mobile, desktop, nhiều trình duyệt, kiểm tra tốc độ tải ảnh, sản phẩm, khả năng chịu tải khi có nhiều truy cập!

---

**Bạn đã kiểm thử đầy đủ hệ thống website bán điện thoại PHP trên AWS Elastic Beanstalk!**
