---
title : "Edit Security Group – Configure Inbound Rules"
date: 2025-06-18
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

## Steps to Open Access Ports (Edit Inbound Rules) for a Security Group on AWS

### 1. Access the EC2 Service

- Log in to the **AWS Console**, search for **EC2**, and select the **EC2** service.  
![Picture8](/images/3.2/image8.png)

---

### 2. Go to the Security Groups List

- In the left-hand menu, scroll down to **Network & Security** → click **Security Groups**.  
![Picture9](/images/3.2/image9.png)

---

### 3. Select the Security Group to Modify

- Find the Security Group you want to configure (e.g., associated with EC2, Elastic Beanstalk, or RDS).
- Click on the Security Group name to view its details.  
![Picture10](/images/3.2/image10.png)

---

### 4. Edit Inbound Rules

- Switch to the **Inbound rules** tab.
- Click **Edit inbound rules** to add or modify rules that allow inbound connections.  
![Picture12](/images/3.2/image12.png)

---

#### Example: Add a New Rule (e.g., for RDS MySQL)

- **Type**: Select **MySQL/Aurora** (or port 3306), or manually enter the port you want to open (e.g., 80, 443, 22…)
- **Protocol**: TCP
- **Port range**: 3306 (or another service port, like 5432 for PostgreSQL)
- **Source**:
  - To allow all IPs: enter `0.0.0.0/0` (**ONLY for testing purposes; not recommended in production!**)
  - To restrict access to Beanstalk/EC2 only: enter a specific Security Group ID or trusted IP range

![Picture13](/images/3.2/image13.png)  
![Picture14](/images/3.2/image14.png)

---

### 5. Save the New Rule

- After adding/editing the rules, scroll down and click **Save rules** to apply the changes.  
![Picture16](/images/3.2/image16.png)

---

> **Important Notes:**  
> - Only open ports to trusted IPs or Security Groups. Avoid using `0.0.0.0/0` unless for testing/lab purposes—and remember to remove it afterward!
> - For RDS, it's recommended to set the source as the Security Group of EC2 or Elastic Beanstalk to enhance security.

---

**You’ve successfully configured Inbound Rules for the Security Group! You're now ready to connect your application to the database or other AWS services.**
