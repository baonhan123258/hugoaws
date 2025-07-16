---
title : "Create an RDS Instance"
date: 2025-06-18
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

## Steps to Create an RDS (MySQL) Instance on AWS

### 1. Access the RDS Service

- Log in to the **AWS Console**, type **RDS** in the search bar, and select the **RDS** service.  
![Picture1](/images/3.1/image1.png)

---

### 2. Create a New Database Instance

- On the **Amazon RDS** page, go to the **Databases** section in the left menu, then click **Create database**.  
![Picture2](/images/3.1/image2.png)

#### Configure Database Settings:

- **Engine options**: Choose **MySQL** (or PostgreSQL if required by your project).
- **Version**: Select the default or latest version (recommended: MySQL 8.x).
- **Templates**: Choose **Free tier** (recommended for learning/demo purposes).  
![Picture3](/images/3.1/image3.png)

- **DB instance identifier**: Enter a name, e.g., `myshop-db`
- **Master username**: Enter a username (suggested: `admin`)
- **Master password**: Set a strong password and save it for use in your PHP config.
- **DB instance size**: Choose the smallest free tier eligible type (`db.t3.micro` or `db.t2.micro`)  
![Picture4](/images/3.1/image4.png)

---

#### Networking & Connectivity Settings:

- **Virtual Private Cloud (VPC)**: Choose the default VPC (or a custom one if applicable)
- **Subnet group**: Leave as default
- **Public access**:  
  - Select **Yes** if you want to access from outside (local machine or Elastic Beanstalk)
  - Select **No** if it's only used internally in the VPC
- **Availability Zone**: Leave default or choose any zone in Singapore

- **VPC security group**:  
  - Either create a new security group or select an existing one that allows port 3306 (for MySQL) or 5432 (for PostgreSQL) from your IP/EC2/Elastic Beanstalk instance  
![Picture5](/images/3.1/image5.png)

---

#### Additional Settings:

- **Initial database name**: Set the default database name (e.g., `shopdb`)
- **Backup**, **Monitoring**, and **Encryption**: Leave at default or disable if only used for lab/demo
- **Deletion protection**: Uncheck if you want to delete the DB quickly after finishing the lab

---

### 3. Create the Database

- Review the settings you've configured.
- Click **Create database** to begin provisioning the RDS instance.  
![Picture6](/images/3.1/image6.png)

---

#### **Important Notes After Creation:**

- Take note of the database **endpoint (host)**, **username**, and **password** for use in your PHP/Laravel configuration files.
- If your PHP/Laravel project is hosted on Elastic Beanstalk, make sure the security group allows inbound traffic from the application.
