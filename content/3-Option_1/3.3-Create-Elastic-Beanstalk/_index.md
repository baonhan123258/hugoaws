---
title : "Create Elastic Beanstalk and Upload PHP Files"
date: 2025-06-18
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

## Step-by-step Guide to Create Elastic Beanstalk and Deploy a PHP Project

---

### 1. Access the Elastic Beanstalk Service

- In the **AWS Console**, type **Elastic Beanstalk** in the search bar and select **Elastic Beanstalk**.
- Make sure the Region is set to **ap-southeast-1**.  
![Image: Access Elastic Beanstalk](/images/3.3/image21.png)

---

### 2. Create a New Application

- Click **Create Application**.  
![Image: Click Create Application](/images/3.3/image22.png)

- **Application name**: Enter a name, e.g., `ban-dien-thoai-php`.
- **Platform**: Choose **PHP**.
- **Platform branch**: Select the appropriate PHP version (e.g., PHP 8.1, PHP 8.2...).
- **Application code**: Choose **Upload your code**.

---

### 3. Upload Your PHP Project (.zip)

- Click **Choose file** to upload your `.zip` file containing the PHP source code (or select from S3 if already uploaded).
- The `.zip` file should place your files (e.g., `index.php`, `composer.json`, etc.) directly in the root — **do not wrap them in an extra folder**.  
![Image: Upload PHP zip file](/images/3.3/image23.png)

---

### 4. Configure the Environment

- **Environment name**: Enter a name (e.g., `ban-dien-thoai-env`).
- **Domain**: AWS will auto-suggest a domain (keep the default or edit it if desired).
- **Instance type**: Choose `t2.micro` or the smallest available for cost efficiency.
- **Key pair**: Leave empty if you don’t need SSH access, or choose a key pair if you want to connect to the EC2 instance.

---

### 5. Create Environment and Deploy Code

- Click **Create environment** to begin the deployment process.  
![Image: Create environment and deploy](/images/3.3/image24.png)
- Wait for AWS to provision the environment (about 5–10 minutes). It will automatically create EC2, a Load Balancer, install PHP, and deploy your source code.

---

### 6. Access the Website After Deployment

- Once completed, you’ll see the **Environment URL** (e.g., http://ban-dien-thoai-env.eba-xxxxxx.ap-southeast-1.elasticbeanstalk.com).
- Click this link to access your deployed PHP website.  
![Image: Access deployed Elastic Beanstalk website](/images/3.3/image26.png)

---

### 7. Manage and Update Your Project (Re-deploy New Code)

- Go to the **Application versions** tab in your Elastic Beanstalk application.
- Click **Upload and deploy** to upload a new `.zip` file and deploy the latest version.
- Use this feature every time you update your website's code.

---

> **Note:**  
> - If you encounter deployment issues (502, 503, blank page), check your zip structure and logs under the **Logs** tab.
> - To configure environment variables (e.g., for database, API keys), go to **Configuration → Software** and add them under *Environment properties*.

---

**You’ve successfully created an Elastic Beanstalk environment and deployed your PHP project! Continue configuring the database, domain, or other AWS services as needed.**
