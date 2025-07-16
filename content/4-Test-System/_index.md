---
title : "Test System"
date: 2025-06-18
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

# Guide to Testing Your PHP Phone Store Website on Elastic Beanstalk

## 1. Access the Website

- Open the **Environment URL** provided by Elastic Beanstalk (or your custom domain if configured).
- Check if the site displays the phone store interface correctly, loads quickly, and operates smoothly.

## 2. Test Product Image Upload Functionality

- Log in to the admin panel (if available) or navigate to the add-new-product page.
- Upload a sample product image.
- Verify that the image displays correctly on the website.
  - If using S3/CloudFront for storage, the image link should point to a CloudFront or S3 domain.

## 3. Verify Database Integration

- Add/edit/delete a product or order through the website.
- Use a database management tool (e.g., phpMyAdmin, Adminer, DBeaver) to connect to RDS and confirm that the data is reflected correctly in the database tables.
- If the site reports a database connection error, double-check the Security Group rules and PHP configuration (`.env`, config file, etc.).

## 4. Check Domain and SSL

- Access your website using your custom domain (e.g., `https://yourshop.com`).
- Ensure the browser displays a secure padlock icon (HTTPS) with no security warnings.

## 5. Test Image/File Loading Speed (if using S3/CloudFront)

- Visit a product detail page and check whether image URLs are served from CDN/S3.
- Test image loading speed from different locations — it should be fast if CloudFront is properly configured.

## 6. View Logs and Monitor the Application

- Go to Elastic Beanstalk → **Logs** → download and review error/access logs for any issues.
- Open CloudWatch to monitor metrics like CPU usage, memory, HTTP errors, and logs.
- Ensure there are no critical errors and the Elastic Beanstalk environment health is **green**.

## 7. Test Alerts (if CloudWatch Alarms are configured)

- Simulate high traffic or application errors to trigger CloudWatch alarms.
- Verify if alerts are sent via email or other configured channels.

---

> **Expected Outcome:**  
> - Website loads fast, uses HTTPS, supports image uploads, stores data in the DB, delivers images via CDN, logs are clean, and custom domain is working properly.

---

**Once all tests are complete, your PHP phone store website is ready to go live on AWS!**
