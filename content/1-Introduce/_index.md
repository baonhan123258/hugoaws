## What is AWS Elastic Beanstalk?

Elastic Beanstalk is an AWS PaaS (Platform as a Service) that simplifies the deployment of PHP applications (as well as Node.js, Python, Java, etc.) to the cloud **without the need to manage server infrastructure**.

### Key Features:
- No server management required  
- Automatic scaling  
- Integrated monitoring  
- Supports multiple environments  
- Easy rollback capabilities  

---

## Deployment Architecture

### Main Components:

#### 1. Elastic Beanstalk Environment
- Automatically provisions EC2, Load Balancer, Auto Scaling, and Security Groups  
- Supports multiple platforms (PHP, Node.js, Python, etc.)

#### 2. Amazon S3
- Stores application source code during deployment  
- Can also store static assets like product images or uploads

#### 3. Amazon RDS (recommended for production databases)
- Manages MySQL/PostgreSQL databases  
- Easy to back up and scale  

#### 4. Amazon CloudWatch
- Monitors logs, metrics, and alerts  
