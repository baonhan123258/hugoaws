# AWS Elastic Beanstalk Web Bán Điện Thoại PHP Workshop

[![AWS](https://img.shields.io/badge/AWS-Elastic%20Beanstalk-orange.svg)](https://aws.amazon.com/elasticbeanstalk/)
[![Hugo](https://img.shields.io/badge/Hugo-Static%20Site-blue.svg)](https://gohugo.io/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A comprehensive workshop for deploying a **PHP E-commerce Website (Bán Điện Thoại)** using AWS Elastic Beanstalk and related managed services. Learn to build, optimize, secure, and monitor a production-ready cloud web application.

---

## 🏗️ Architecture Overview

### Option 1: Basic Deployment
Local Source (.zip) → Elastic Beanstalk → EC2 + Web Server → Public URL
|
└─> [Option] Connect to RDS (MySQL/PostgreSQL)

shell
Sao chép
Chỉnh sửa

### Option 2: Advanced Deployment
Local Source (.zip) → Elastic Beanstalk → EC2 + Web Server → Public URL + Domain (Route 53)
| |
├─> RDS (MySQL) └─> S3 (images, static)
| |
└─> CloudWatch (logs, alerts) ← CloudFront (CDN)

yaml
Sao chép
Chỉnh sửa

---

## 🎯 Real-World Use Cases

- **E-commerce Website**: Website bán điện thoại hoặc bất kỳ sản phẩm nào, tối ưu cho cả traffic nhỏ (shop cá nhân) lẫn lớn (doanh nghiệp).
- **SaaS Landing Page**: Website giới thiệu dịch vụ, nhận đăng ký qua form, gửi email qua SES.
- **CMS/Blog**: Chạy WordPress/Laravel, lưu trữ media trên S3, tối ưu ảnh qua CDN.

---

## 🚀 What You'll Build

- **Production-ready PHP website** deployed on Elastic Beanstalk
- **Managed RDS Database** (MySQL/PostgreSQL)
- **Custom domain + SSL** (Route 53, ACM)
- **Image/file hosting** on S3 and CloudFront
- **Monitoring & alerting** with CloudWatch
- **Zero server management** (AWS handles scaling, patching, backups)

---

## 🛠️ Technologies Used & Why

### **Elastic Beanstalk**
- ✅ No server management
- ✅ Automatic scaling & health checks
- ✅ Fast rollback & blue-green deployments

### **RDS**
- ✅ Managed database (backup, HA, scaling)
- ✅ MySQL/PostgreSQL for transactional e-commerce data

### **S3 + CloudFront** (Option 2)
- ✅ Unlimited storage for images/assets
- ✅ Global CDN for fastest load time

### **Route 53 + ACM** (Option 2)
- ✅ Easy custom domain management
- ✅ Free auto-renew SSL certificate (HTTPS)

### **CloudWatch**
- ✅ Unified logs, alarms, cost tracking

---

## 📋 Prerequisites

- **AWS Account** (Free Tier eligible)
- **PHP Source Code** (any framework: Laravel, CodeIgniter, thuần PHP...)
- **Valid email** for alerts, notifications
- **Basic knowledge** of AWS services, web app, and MySQL
- **Modern web browser**

---

## 💰 Cost Estimation

Workshop is designed for Free Tier:
- **Estimated cost**: $0 if within Free Tier
- **Delete all resources after workshop to avoid extra charges**

---

## 🎯 Learning Objectives

- ✅ Deploy and manage a PHP web app on AWS Elastic Beanstalk
- ✅ Connect website to managed database (RDS)
- ✅ Attach custom domain, enable HTTPS
- ✅ Serve images & files via S3/CloudFront (CDN)
- ✅ Monitor logs and health with CloudWatch
- ✅ Apply best practices for cost and security

---

## 🏆 Best Practices Implemented

- **Security**: Only open required ports, use IAM least privilege, enable SSL/HTTPS
- **Performance**: Use CDN for media, tune database connections, scale EC2 as needed
- **Cost optimization**: Free Tier usage, auto-stop/delete idle resources
- **Reliability**: Managed backups, health checks, CloudWatch alerts

---

## 📚 Workshop Structure

1. [Giới thiệu](content/1-Introduce/)
2. [Chuẩn bị & Cấu hình](content/2-Prerequiste/)
3. [OPTION 1: Deploy web PHP cơ bản](content/3-Option_1/)
4. [OPTION 2: Nâng cao - domain, SSL, S3, CloudFront, CloudWatch](content/4.Option_2/)
5. [Kiểm thử hệ thống](content/5-Test-System/)
6. [Dọn dẹp tài nguyên](content/6-cleanup/)

---

## 🌐 Languages

- 🇻🇳 **Tiếng Việt** (`_index.vi.md`)
- 🇺🇸 **English** (`_index.md`)

---

## 🚀 Quick Start

1. **Clone repo & cài Hugo**  
2. Chạy lệnh: `hugo server -D`  
3. Mở trình duyệt tại http://localhost:1313 và làm từng bước

---

## 📖 For Learners & Instructors

- Người mới: làm Option 1 (deploy cơ bản, test, cleanup)
- Đã quen AWS: thử Option 2 (domain, SSL, CDN, logs...)

---

## 🤝 Contributing

Chào đón mọi đóng góp!  
Xem [CONTRIBUTING.md](CONTRIBUTING.md) để biết chi tiết.

---

## 📄 License

Project này theo [MIT License](LICENSE)

---

## 🙏 Acknowledgments

- **AWS Docs**  
- **Hugo Community**  
- **Nhóm đóng góp**

---

**⭐ Star repo nếu thấy hữu ích! – Chia sẻ cho bạn bè, đồng nghiệp quan tâm cloud/web dev!**