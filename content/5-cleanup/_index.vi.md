---
title : "Dọn dẹp tài nguyên"
date: 2025-06-18
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

Sau khi hoàn thành workshop, bạn cần **dọn dẹp tài nguyên AWS** để tránh phát sinh chi phí không mong muốn.

---

## 1. Xóa Elastic Beanstalk Environment

- Vào **AWS Console** → **Elastic Beanstalk**
- Chọn môi trường bạn đã tạo (ví dụ: `web-ban-dien-thoai`)
- Nhấn **Actions** → **Terminate environment**
- Xác nhận xóa  
> **Lưu ý:** Môi trường sẽ xóa toàn bộ EC2, EBS, Load Balancer liên quan.

---

## 2. Xóa Database RDS (nếu có tạo)

- Vào **AWS Console** → **RDS** → **Databases**
- Chọn database (ví dụ: `shopdb`)
- **Actions** → **Delete**
- Chọn "Skip final snapshot" nếu không cần backup
- Gõ xác nhận, nhấn **Delete me**

---

## 3. Xóa S3 Bucket (nếu có dùng)

- Vào **AWS Console** → **S3**
- Chọn các bucket đã tạo (ví dụ: `media-yourshop-2025`)
- **Empty bucket** → **Confirm**
- **Delete bucket** → **Confirm**
> **S3 bucket phải rỗng mới xóa được.**

---

## 4. Xóa CloudFront Distribution (nếu dùng)

- Vào **AWS Console** → **CloudFront**
- Chọn distribution → **Disable**
- Chờ trạng thái "Deployed" → **Delete**

---

## 5. Xóa domain hoặc Hosted Zone (nếu mua domain trên AWS Route 53)

- Vào **Route 53** → **Hosted Zones**
- Chọn hosted zone, **Delete Record Set** từng record → **Delete Hosted Zone**
- Nếu đã mua domain, cân nhắc giữ lại hoặc huỷ đăng ký nếu không sử dụng.

---

## 6. Xóa CloudWatch Logs & Alarms

- Vào **CloudWatch** → **Log groups**
- Xóa log groups liên quan Elastic Beanstalk/EC2/app
- Vào **Alarms**, **Delete** các cảnh báo đã tạo

---

## 7. Xóa IAM Roles không còn dùng (tùy chọn)

- Vào **IAM** → **Roles**
- Xóa các role auto-created bởi Beanstalk, EC2 hoặc dịch vụ workshop
- Chỉ xóa khi chắc chắn không sử dụng ở chỗ khác

---

## 8. Kiểm tra Billing

- Vào **Billing Dashboard** → **Cost Explorer**
- Filter dịch vụ: **Elastic Beanstalk**, **EC2**, **RDS**, **S3**, **CloudFront**, **Route 53**, **CloudWatch**
- Đảm bảo không còn resource bị tính phí

---

## 9. Checklist dọn dẹp hoàn tất

✅ **Kiểm tra đã xóa các resource sau:**
- [ ] Elastic Beanstalk Environment  
- [ ] RDS Database  
- [ ] S3 Bucket  
- [ ] CloudFront Distribution  
- [ ] Hosted Zone/Domain  
- [ ] CloudWatch Logs/Alarms  
- [ ] IAM Roles (nếu cần)  
- [ ] Billing không còn bị charge

> **TIP:**  
> Một số tài nguyên có thể mất vài phút để biến mất khỏi console AWS sau khi xóa.

---

**Bạn đã dọn dẹp sạch môi trường AWS của mình!**
