---
title : "OPTION 1: Deploy a PHP Web-based Mobile Phone Store with Elastic Beanstalk"
date: 2025-06-18
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

In **Option 1**, you will practice **deploying a basic PHP-based e-commerce website to AWS Elastic Beanstalk**.  
You will learn how to upload PHP code, set up an environment, configure a database (RDS), open access ports, and test the deployed application in the cloud.

**System Architecture:**
- **Elastic Beanstalk Environment**: Automatically manages EC2, Load Balancer, deployment & scaling of the PHP app.
- **S3 Bucket (optional)**: Stores uploaded files, product images, or deployment artifacts.
- **RDS (optional)**: Stores data such as orders, users, and other business information.

**Workflow:**
1. Upload your PHP source code (.zip) to Elastic Beanstalk.
2. AWS automatically provisions the environment (EC2, Load Balancer, Security Group, etc.).
3. Users can access the website via a public URL or domain.
4. (Optional) Connect to an RDS database for data management.

![deploy-php-eb-basic](/images/sơdo.png)

---

### Detailed Steps
3.1. [Create an RDS Instance for the database](3.1-Create-RDS-Instance/) \
3.2. [Edit the Security Group for Elastic Beanstalk](3.2-Edit-Security-Group/) \
3.3. [Create Elastic Beanstalk Environment & Upload PHP Project Files](3.3-Create-Elastic-Beanstalk/)

---

> **Note:** If you only want to try deploying without using a database, you can skip Step 3.1.
