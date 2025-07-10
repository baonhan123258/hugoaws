---
title : "Giới thiệu"
date: 2025-06-18
weight : 1
chapter : false
pre : " <b> 1. </b> "
---

## Tổng quan Workshop

Workshop này hướng dẫn bạn **triển khai (deploy) một dự án web bán điện thoại viết bằng PHP lên AWS Elastic Beanstalk**. Đây là dịch vụ quản lý ứng dụng giúp bạn triển khai, vận hành và mở rộng website mà không cần quản lý máy chủ vật lý.

## AWS Elastic Beanstalk là gì?

**Elastic Beanstalk** là dịch vụ Platform-as-a-Service (PaaS) của AWS, cho phép bạn đưa code ứng dụng PHP (hoặc Node.js, Python, Java,...) lên cloud. Elastic Beanstalk sẽ tự động cấu hình, triển khai, mở rộng và giám sát ứng dụng cho bạn.

### Đặc điểm nổi bật:
- **Không cần quản lý server**: AWS lo cấu hình, cập nhật, bảo trì server.
- **Tự động mở rộng**: Ứng dụng tự scale lên/xuống theo nhu cầu sử dụng.
- **Theo dõi & cảnh báo tích hợp**: Có sẵn log, dashboard và alert qua CloudWatch.
- **Triển khai nhiều môi trường**: Dễ tạo môi trường dev, staging, production.
- **Rollback nhanh chóng**: Có thể quay lại version cũ nếu gặp lỗi.


## Kiến trúc Triển khai

*Hình: Kiến trúc hệ thống web bán điện thoại PHP bảo mật trên AWS Elastic Beanstalk với VPC.*

### Các thành phần chính:

#### 1. **Elastic Beanstalk Environment**
- Quản lý EC2, Load Balancer, Auto Scaling, Security Group hoàn toàn tự động.
- Hỗ trợ nhiều ngôn ngữ/platform, đặc biệt là PHP.



#### 2. **Amazon S3**
- Lưu trữ mã nguồn ứng dụng, hình ảnh sản phẩm và các tài nguyên tĩnh.

#### 3. **Amazon RDS** *(nên dùng cho database sản xuất)*
- Quản lý database MySQL/PostgreSQL.
- Dễ dàng tích hợp với Elastic Beanstalk, tự động backup, bảo mật, mở rộng.


#### 4. **Amazon CloudWatch**
- Theo dõi log, hiệu năng, cảnh báo lỗi khi deploy và vận hành.

## Ưu điểm của Elastic Beanstalk

### 1. **Tiết kiệm chi phí**
- **Trả theo nhu cầu**: Không mất phí khi không dùng.
- **Hỗ trợ Free Tier**: Phù hợp thử nghiệm, học tập hoặc demo.

### 2. **Mở rộng & Đảm bảo tin cậy**
- **Tự động mở rộng**: Đáp ứng lượng truy cập lớn, không sợ “sập”.
- **Tự động dự phòng lỗi**: Có thể chạy đa vùng (multi-AZ) tăng uptime.

### 3. **Tăng năng suất lập trình viên**
- **Triển khai nhanh**: Từ code lên cloud chỉ vài phút.
- **Dễ tích hợp với nhiều dịch vụ AWS**: S3, RDS, CloudWatch...

## Ứng dụng thực tế

- **Web bán điện thoại**: Laravel, CodeIgniter hoặc PHP thuần đều chạy tốt.
- **CMS/Blog**: WordPress, Drupal, v.v.
- **REST API/Backend**: Dành cho mobile hoặc web client.

## Các bước triển khai thực tế

### 1. Chuẩn bị mã nguồn PHP

- Đảm bảo chạy ổn định local (test với `php -S localhost:8000`).
- Nếu dùng Laravel: chạy `composer install`, kiểm tra `.env`.
- Xoá dữ liệu test, loại bỏ file/thư mục không cần thiết trước khi triển khai.



### 2. Đóng gói mã nguồn

- Có thể nén project thành file .zip (loại trừ `node_modules`, `.git`,...) hoặc quản lý source code bằng GitHub để tiện cho việc triển khai tự động qua Elastic Beanstalk.

### 3. Tạo môi trường Elastic Beanstalk

1. Đăng nhập AWS Console → Elastic Beanstalk.
2. Chọn **Create Application**.
3. Nhập tên ứng dụng (ví dụ: `ban-dien-thoai`).
4. Chọn **PHP** platform.
5. Chọn file .zip mã nguồn hoặc nhập link Git repo.
6. Chọn loại môi trường **Web server**.
7. Cấu hình chi tiết (instance type, RDS, scaling,...).
8. Nhấn **Create Environment** và chờ deploy.


### 4. Kết nối Database (tùy chọn)

- Tạo mới RDS hoặc kết nối DB sẵn có.
- Khai báo thông tin kết nối trong `.env` (Laravel) hoặc file config của bạn.

### 5. Cấu hình môi trường

- Thêm biến môi trường (environment variables) trong phần Software Configuration.
- Thiết lập HTTPS (cấp phát chứng chỉ qua ACM, cấu hình trên Load Balancer nếu cần).

### 6. Deploy và kiểm tra

- Sau khi triển khai, truy cập URL Beanstalk cung cấp.
- Test các chức năng: xem sản phẩm, đặt hàng, upload ảnh,...
- Xem log hoặc metric trong CloudWatch nếu gặp lỗi.



### 7. Gắn domain riêng (nếu cần)

- Thêm domain tại Route 53 hoặc DNS provider bên ngoài.
- Trỏ CNAME về endpoint của Beanstalk.

## Điều kiện cần thiết

- **Tài khoản AWS** (nên có Free Tier).
- **Dự án PHP** đã sẵn sàng.
- **Git** (nếu triển khai qua repo).
- **Email** để nhận thông báo từ AWS.
- **Kiến thức cơ bản về AWS Console**.

## Lưu ý chi phí

> **Tip**: Phần lớn môi trường dev/test chạy trong Free Tier hoặc chỉ tốn < 1 USD nếu dùng ngắn.  
> **Luôn xoá môi trường sau khi test xong để tránh phát sinh phí!**

## Bảng tóm tắt các bước

| Bước         | Nội dung                          | Dịch vụ AWS        |
|--------------|-----------------------------------|--------------------|
| Chuẩn bị     | Soạn mã nguồn PHP                 | Local/IDE          |
| Đóng gói     | Nén file/Git push                 | S3 (tùy chọn)      |
| Deploy       | Đưa lên Elastic Beanstalk         | Elastic Beanstalk  |
| Database     | Kết nối/khởi tạo RDS (tùy chọn)   | RDS                |
| Monitor      | Theo dõi logs, cảnh báo           | CloudWatch         |
| Domain       | Gắn domain riêng (tùy chọn)       | Route53            |

## Kết luận

- **Không cần quản lý server thủ công**: Elastic Beanstalk lo hết cho bạn!
- **Triển khai PHP web bán điện thoại nhanh chóng, an toàn**.
- **Phù hợp cả cho demo, dự án nhỏ, hoặc vận hành thực tế.**

---

Nếu bạn cần **hướng dẫn chi tiết từng thao tác trên AWS Console**, **lệnh CLI**, hoặc muốn nhận file hướng dẫn hoàn chỉnh, cứ nói nhé!
