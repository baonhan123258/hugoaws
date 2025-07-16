---
title : "Resource Cleanup"
date: 2025-06-18
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

After completing the workshop, you **must clean up all AWS resources** to avoid unexpected charges.

---

## 1. Delete Elastic Beanstalk Environment

- Go to **AWS Console** → **Elastic Beanstalk**
- Select the application/environment you created (e.g., `web-ban-dien-thoai`)
- Click **Actions** → **Terminate environment**
- Confirm the termination.  
> **Note:** This will delete all associated EC2 instances, Load Balancers, and EBS volumes.

---

## 2. Delete RDS Database (if created)

- Go to **AWS Console** → **RDS** → **Databases**
- Select the database you created (e.g., `shopdb`)
- Click **Actions** → **Delete**
- Choose "Create final snapshot" if you want to back it up, or uncheck it to delete immediately.
- Type the database name to confirm, then click **Delete me**.

---

## 3. Delete S3 Buckets (if used for storing images/files)

- Go to **AWS Console** → **S3**
- Select the buckets created for the workshop (e.g., `media-yourshop-2025`)
- For each bucket:
    - Click **Empty bucket** → confirm to delete all files inside
    - Click **Delete bucket** → confirm to delete the bucket
> **Note:** A bucket must be empty before it can be deleted!

---

## 4. Delete CloudFront Distribution (if used as CDN)

- Go to **CloudFront** → select the distribution you created
- Click **Disable** → wait until the status becomes "Deployed" → then click **Delete**

---

## 5. Delete Domain/Hosted Zone in Route 53 (if you purchased a domain on AWS)

- Go to **Route 53** → **Hosted Zones**
- Select the Hosted Zone, **Delete Record Set** for each record, then **Delete Hosted Zone**
- If you purchased a domain, you may keep it for future use or choose to cancel the registration.

---

## 6. Delete CloudWatch Logs and Alarms

- Go to **CloudWatch** → **Log groups**
- Delete log groups related to Elastic Beanstalk, EC2, or the application
- Go to **Alarms** → **Delete** the alarms you created

---

## 7. Delete Unused IAM Roles (optional)

- Go to **IAM** → **Roles**
- Identify and delete any roles created for the workshop that are no longer in use (e.g., for EC2, Elastic Beanstalk, or RDS)
> **Note:** Be careful not to delete roles still in use by other services or applications.
