---
title : "Resource Cleanup"
date: 2025-06-18
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

Sau khi hoàn thành workshop, bạn **cần dọn dẹp toàn bộ tài nguyên AWS** để tránh bị tính phí ngoài ý muốn.

---

## 1. Xóa Elastic Beanstalk Environment

- Vào **AWS Console** → **Elastic Beanstalk**
- Chọn ứng dụng/môi trường vừa tạo (ví dụ: `web-ban-dien-thoai`)
- Nhấn **Actions** → **Terminate environment**
- Xác nhận xóa.  
> **Lưu ý:** Quá trình này sẽ xóa toàn bộ EC2, Load Balancer, EBS volume của môi trường này.

---

## 2. Xóa RDS Database (nếu có tạo)

- Vào **AWS Console** → **RDS** → **Databases**
- Chọn database vừa tạo (ví dụ: `shopdb`)
- Nhấn **Actions** → **Delete**
- Chọn "Create final snapshot" nếu muốn backup, hoặc bỏ chọn để xóa ngay.
- Gõ tên xác nhận và nhấn **Delete me**.

---

## 3. Xóa S3 Buckets (nếu dùng để lưu ảnh/file)

- Vào **AWS Console** → **S3**
- Chọn các bucket đã tạo cho workshop (ví dụ: `media-yourshop-2025`)
- Với mỗi bucket:
    - **Empty bucket** → xác nhận xóa toàn bộ file bên trong
    - **Delete bucket** → xác nhận để xóa bucket
> **Lưu ý:** Bucket phải empty mới xóa được!

---

## 4. Xóa CloudFront Distribution (nếu có dùng CDN)

- Vào **CloudFront** → chọn distribution đã tạo
- Nhấn **Disable** → chờ trạng thái "Deployed" → **Delete**

---

## 5. Xóa Domain/Hosted Zone Route 53 (nếu đã mua domain trên AWS)

- Vào **Route 53** → **Hosted Zones**
- Chọn Hosted Zone, **Delete Record Set** từng record, sau đó **Delete Hosted Zone**
- Nếu đã mua domain, có thể giữ lại nếu muốn sử dụng tiếp, hoặc hủy đăng ký.

---

## 6. Xóa CloudWatch Logs và Alarm

- Vào **CloudWatch** → **Log groups**
- Xóa các log group liên quan tới Elastic Beanstalk, EC2 hoặc app
- Vào **Alarms** → **Delete** các cảnh báo đã tạo

---

## 7. Xóa IAM Roles không còn dùng (tùy chọn)

- Vào **IAM** → **Ro**
