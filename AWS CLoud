
The exam has the following content domains and weightings:

Content Domain 1: Cloud Concepts (24% of scored content)

Content Domain 2: Security and Compliance (30% of scored content)

Content Domain 3: Cloud Technology and Services (34% of scored content)

Content Domain 4: Billing, Pricing, and Support (12% of scored content)


Amazon CDN & S3, Lambda,Amazon ses Usage:
=============================


CDN Aws:
https://www.youtube.com/watch?v=akwAv_L1XQ4

Aws Lambda :
https://www.youtube.com/watch?v=NWzfgAw_DYA




Aws Question answers:
https://www.netcomlearning.com/blog/aws-interview-questions

=============================
## What is Amazon VPC?

**Amazon VPC (Virtual Private Cloud)** is your own private network inside AWS.

Think of AWS as a large apartment building. A **VPC is like your own apartment** where you control:

* IP addresses
* Servers (EC2)
* Network access
* Security rules
* Internet access

This means the VPC can use IP addresses from:
10.0.0.0  to  10.0.255.255

VPC     = Big House
Subnet  = Rooms inside the House
EC2     = People inside the Rooms

You decide which resources are public and which are private.

### Example

Suppose you have a PHP website:

* Web Server (EC2) → Public (users can access)
* Database (MySQL) → Private (only web server can access)

Both are placed inside the same VPC.


AWS Cloud
└── VPC (10.0.0.0/16)
    ├── Public Subnet
    │   └── Web Server (EC2)
    │
    └── Private Subnet
        └── MySQL Database


---
# Types of Networks

## 1. Public Network
Resources can be accessed directly from the internet.

### Example
* Website server
* Load Balancer

Internet
    |
Web Server


AWS Example:

* EC2 in Public Subnet
* Has Public IP
* Route to Internet Gateway

---

## 2. Private Network

Resources cannot be accessed directly from the internet.

### Example

* Database server
* Internal application server


Internet
   X
Database Server


AWS Example:

* EC2 in Private Subnet
* No Public IP
* Access only from internal servers

---

## 3. Hybrid Network

Combination of On-Premise Data Center and Cloud.

### Example
Office Data Center
        |
      VPN
        |
      AWS VPC


Company keeps some servers in office and some in AWS.

A bank might:

Keep customer records in its private data center.
Run web applications in AWS.
Connect both environments through AWS networking.

Amazon VPC — Creates private networks in AWS.
AWS Site-to-Site VPN — Encrypted connection over the internet.
AWS Direct Connect — Private dedicated link to AWS.
AWS Transit Gateway — Connects multiple VPCs and on-prem networks.
AWS Cloud WAN — Global network management.


---
# Types of VPC Components

## 1. VPC

Your private network.

Example:
10.0.0.0/16

---
## 2. Subnet

A subnet is a smaller network inside a VPC.

Example:


VPC: 10.0.0.0/16

Public Subnet:
10.0.1.0/24

Private Subnet:
10.0.2.0/24


---
## 3. Internet Gateway (IGW)
Allows communication between VPC and the Internet.

Internet
    |
   IGW
    |
  VPC

Without IGW, internet access is not possible.

---
## 4. Route Table

Works like Google Maps for network traffic.

Example:

Destination      Target
0.0.0.0/0        IGW


Meaning:
"Send all internet traffic to Internet Gateway."

---

## 5. Security Group

Acts as a **firewall for EC2 instances**.

Example:

Allow:

* HTTP (80)
* HTTPS (443)
* SSH (22)

Block everything else.

---

## 6. Network ACL (NACL)

Acts as a **firewall for the subnet**.

| Security Group | NACL         |
| -------------- | ------------ |
| Instance level | Subnet level |
| Stateful       | Stateless    |

---

# Interview Answer (Short)

Amazon VPC is a logically isolated private network in AWS where we launch and manage resources like EC2, RDS, and Load Balancers. It gives us control over IP addresses, subnets, routing, internet access, and security. A VPC typically contains public and private subnets, route tables, internet gateways, and security groups.

### One-Line Interview Answer

**"Amazon VPC is my own private network inside AWS where I control networking, security, and access to cloud resources."**


Since you're preparing for AWS interviews as an experienced PHP developer, focus on **concepts**, not just definitions.

# 1. What is a Region?

**Answer:**
A Region is a geographical location where AWS has data centers.

Examples:

* Mumbai Region
* Singapore Region
* N. Virginia Region

**Interview Question:**
Why deploy in multiple regions?

**Answer:**
For disaster recovery and lower latency for global users.

---

# 2. What is an Availability Zone (AZ)?

**Answer:**
An AZ is one or more data centers inside a Region.

Example:


Mumbai Region
├── AZ-A
├── AZ-B
└── AZ-C


If one AZ fails, another AZ can continue serving traffic.

---

# 3. Difference Between Region and AZ?

| Region          | AZ                        |
| --------------- | ------------------------- |
| Geographic area | Data center within region |
| Mumbai          | Mumbai-A, Mumbai-B        |
| Multiple AZs    | Part of one Region        |

---

# 4. What is CIDR?

CIDR defines the IP range of a network.

Example:


10.0.0.0/16


Means:


10.0.0.0 - 10.0.255.255


Used in VPC and Subnets.

---

# 5. What is a Public Subnet?

A subnet that has a route to an Internet Gateway.

Example:

* Web Server
* Load Balancer

Users can access it from the internet.

---

# 6. What is a Private Subnet?

A subnet without direct internet access.

Example:

* Database
* Internal APIs

More secure.

---

# 7. What Makes a Subnet Public?

**Answer:**
Not the public IP.

A subnet becomes public when its route table contains:


0.0.0.0/0 → Internet Gateway


This is a very common interview question.

---

# 8. What is an Internet Gateway?

It allows communication between VPC resources and the internet.

Without IGW:


Internet ❌ EC2


---

# 9. What is a NAT Gateway?

Allows private subnet servers to access the internet without exposing them publicly.

Example:


Private EC2
    |
NAT Gateway
    |
Internet


Use case:
Installing updates from a private server.

---

# 10. Security Group vs NACL?

| Security Group     | NACL                      |
| ------------------ | ------------------------- |
| Instance level     | Subnet level              |
| Stateful           | Stateless                 |
| Allow rules only   | Allow & Deny              |
| Most commonly used | Additional security layer |

---

# 11. What is Stateful?

Security Groups are stateful.

Example:


Allow Port 80 Inbound


Response traffic is automatically allowed.

No outbound rule needed.

---

# 12. What is Stateless?

NACLs are stateless.

If inbound is allowed, outbound must also be explicitly allowed.

---

# 13. What is EC2?

Virtual machine in AWS.

Example:

* PHP Application
* Laravel Application
* WordPress

---

# 14. What is Auto Scaling?

Automatically adds or removes EC2 instances based on traffic.

Example:


100 Users -> 2 Servers
5000 Users -> 10 Servers


Reduces cost and improves performance.

---

# 15. What is Elastic Load Balancer (ELB)?

Distributes traffic across multiple servers.


Users
  |
Load Balancer
 /   \
EC2  EC2


Prevents a single server from being overloaded.

---

# 16. Why Use Load Balancer?

Without it:


All Traffic
     |
   EC2-1


One server can crash.

With ELB:


Traffic
   |
 ELB
 / \
EC2 EC2


Traffic is shared.

---

# 17. What is S3?

Object storage service.

Store:

* Images
* Videos
* Backups
* Static websites

---

# 18. Difference Between EBS and S3?

| EBS                 | S3                     |
| ------------------- | ---------------------- |
| Attached to EC2     | Standalone Storage     |
| Block Storage       | Object Storage         |
| Acts like Hard Disk | Acts like File Storage |

---

# 19. What Happens If EC2 Stops?

* Instance store data may be lost.
* EBS data remains.

That's why production servers use EBS.

---

# 20. What is IAM?

Identity and Access Management.

Controls:

* Who can log in
* What actions they can perform

Example:


Developer:
✔ EC2 Access
✔ S3 Access
✖ IAM Access


---

# 21. IAM Role vs IAM User?

### IAM User

For a person.

Example:

* Developer
* Admin

### IAM Role

For AWS services.

Example:


EC2 → S3
Lambda → DynamoDB


No passwords or access keys needed.

---

# 22. Why Use IAM Roles Instead of Access Keys?

Bad:


Access Key inside PHP code


Good:


EC2 IAM Role


More secure and recommended by AWS.

---

# 23. What is RDS?

Managed relational database service.

Supports:

* MySQL
* PostgreSQL
* MariaDB

AWS handles:

* Backups
* Patching
* Monitoring

---

# 24. EC2 Database vs RDS?

| EC2 MySQL       | RDS                |
| --------------- | ------------------ |
| Self-managed    | AWS-managed        |
| Manual backup   | Automatic backup   |
| Manual patching | Automatic patching |

---

# 25. What is CloudWatch?

Monitoring service.

Tracks:

* CPU
* Memory (with agent)
* Disk
* Logs
* Errors

Example:
Get alerted when CPU > 80%.

---

# Common Scenario Question

**Q: Design a highly available PHP application.**

Answer:


Internet
    |
Load Balancer
    |
Auto Scaling Group
  /       \
EC2       EC2
    |
   RDS
    |
    S3


Use:

* VPC
* Public & Private Subnets
* ELB
* Auto Scaling
* RDS
* S3
* CloudWatch

This is one of the most common AWS architecture interview discussions for web developers.

What is a Load Balancer?
=========================
A Load Balancer distributes incoming user requests across multiple servers.

Instead of sending all traffic to one server, it shares the traffic among several servers.

188978
========================================================================
Steps to Create EC2 Instance

1. Login to AWS Console

Go to:

AWS Console

2. Open EC2 Service

Search for:
EC2

Click:
Launch Instance

3. Choose AMI
AMI = Operating System template.



Examples:

Amazon Linux
Ubuntu ###
Windows

Choose one OS.

4. Choose Instance Type

Example:

t2.micro (Free Tier)

| Instance | RAM  | CPU    |
| -------- | ---- | ------ |
| t2.micro | 1 GB | 1 vCPU |
| m4.large | 8 GB | 2 vCPU |


This decides:

CPU
RAM
Performance

5. Create Key Pair

Key Pair is used to connect securely.

Create new key pair
Download .pem file => Privacy-Enhanced Mail.
Keep it safe

6. Configure Network Settings

Allow required traffic:

Common Rules
SSH → Port 22
HTTP → Port 80
HTTPS → Port 443

These are configured in Security Group.

7. Configure Storage

Choose disk size.

Example:

8 GB
20 GB

AWS uses:
Amazon EBS

8. Click "Launch Instance"

Your EC2 server will start in a few seconds.

| Term           | Meaning          |
| -------------- | ---------------- |
| EC2            | Virtual Server   |
| AMI            | OS Template      |
| Security Group | Firewall         |
| EBS            | Storage          |
| Key Pair       | Secure Login Key |

A Key Pair in AWS is used to securely connect to an EC2 instance. It contains a public key stored in AWS and a private key downloaded by the user for authentication.

.pem (Privacy-Enhanced Mail.)
===============================
A .pem file is a private key file used to securely connect to an AWS EC2 server.

It is generated when creating an Amazon EC2 instance.

Main Use of .pem File

The .pem file is used for:

Secure SSH login
Authentication
Password-less server access


How to Create a CDN in AWS (Using CloudFront)
==============================================
Amazon CloudFront is AWS CDN service used to deliver website content faster worldwide.

To create an image CDN in AWS, images are stored in an S3 bucket and distributed globally using CloudFront. CloudFront caches images at edge locations and delivers them faster to users.

Steps to Create CDN in AWS
1. Login to AWS Console

Open:
AWS Console

2. Open CloudFront

Search:
CloudFront

Click:
Create Distribution

3. Choose Origin

Origin = Main server/storage.

You can use:

Amazon S3 bucket
EC2 website
Load Balancer
Custom domain

Example:

mywebsite.s3.amazonaws.com

4. Configure CDN Settings

Common settings:

Setting	Value
Viewer Protocol Policy   	Redirect HTTP to HTTPS
Allowed Methods	            GET, HEAD
Cache Policy	            CachingOptimized


5. Add Domain Name (Optional)

Example:

cdn.example.com

Use:
Amazon Route 53 for DNS mapping.

6. Enable SSL Certificate

Use:
AWS Certificate Manager

This provides HTTPS security.

7. Click Create Distribution

AWS creates CDN in few minutes.

8. Use CloudFront URL

You will get URL like:
d123abcd.cloudfront.net

Use this URL for:

Images
CSS
JS
Videos

How CDN Flow Works
----------------------
User → Nearest CloudFront Edge Location → Origin Server
Example

Without CDN:

example.com/image.png

With CDN:

d123abcd.cloudfront.net/image.png
Benefits
Faster website
Lower latency
Global delivery
Reduced server load
Better security
Interview Answer (Short)

We can create a CDN in AWS using CloudFront by selecting an origin server like S3 or EC2, configuring cache and security settings, and creating a distribution that serves content from edge locations worldwide.

===========================================================================

How to Host a Website in AWS (Simple)
==========================================
There are multiple ways to host a website in AWS.

Common methods:

EC2 Hosting
S3 Static Website Hosting
Elastic Beanstalk

Most interviewers ask about EC2 hosting.

Method 1: Host Website Using EC2

Using Amazon EC2

Step 1: Create EC2 Instance
Login to AWS
Open EC2
Click "Launch Instance"
Choose:
Ubuntu/Linux
t2.micro

Allow ports:

22 → SSH
80 → HTTP
443 → HTTPS
Step 2: Connect to Server

Use SSH:

ssh -i mykey.pem ubuntu@public-ip
Step 3: Install Web Server

For Ubuntu:

Install Apache
sudo apt update
sudo apt install apache2 -y

Start Apache:

sudo systemctl start apache2
Step 4: Upload Website Files

Website files go inside:

/var/www/html

Example:

sudo cp index.html /var/www/html/
Step 5: Open Website

Open browser:

http://your-public-ip

Website will load.

Optional Steps
Add Domain

Use:
Amazon Route 53

Example:

www.example.com
Add SSL (HTTPS)

Use:
AWS Certificate Manager

Website Hosting Architecture
User → Domain → EC2 Server → Website
Method 2: Static Website Hosting Using S3

Using:
Amazon S3

Best for:

HTML
CSS
JS static websites
Simple Steps for S3 Hosting
Create S3 bucket
Upload website files
Enable static website hosting
Make bucket public
Use S3 website URL
Interview Answer (Short)

A website can be hosted in AWS using EC2 by launching a server, installing a web server like Apache or Nginx, uploading website files, and accessing it through the public IP or domain name.

================================================================

How to Host PHP Website with MySQL Database in AWS (Simple Steps)
===================================================================
A PHP website can be hosted in AWS by launching an EC2 instance, installing Apache and PHP, uploading website files, creating a MySQL database in RDS, and connecting the PHP application to the RDS database securely.

We use:

Amazon EC2 → PHP website hosting
Amazon RDS → MySQL database

Architecture

User → EC2 (PHP Website) → RDS MySQL Database
Step 1: Create EC2 Instance

Open AWS Console:
AWS Console
Go to EC2 → Launch Instance

Choose:
Ubuntu
t2.micro

Allow ports:

22 → SSH
80 → HTTP
443 → HTTPS

Create/download .pem key.

Step 2: Connect to EC2

ssh -i mykey.pem ubuntu@your-public-ip
Step 3: Install Apache + PHP + MySQL Client

Run:

sudo apt update
sudo apt install apache2 php libapache2-mod-php php-mysql mysql-client -y

Step 4: Start Apache
sudo systemctl start apache2

Step 5: Upload PHP Website Files

Website folder:

/var/www/html

Upload files:

sudo cp -r mywebsite/* /var/www/html/
Step 6: Create MySQL Database in RDS

Open:
Amazon RDS

Click:
Create Database

Choose:
MySQL
Free Tier
Username/password

Step 7: Allow EC2 to Access RDS

In RDS Security Group:

Open MySQL port:
3306

Allow access from EC2 security group.

Step 8: Connect PHP to MySQL

Example PHP code:

<?php

$conn = mysqli_connect(
    "your-rds-endpoint",
    "admin",
    "password",
    "mydb"
);

if(!$conn){
    die("Connection failed");
}

echo "Database Connected";

?>
Step 9: Open Website

Browser:

http://your-ec2-public-ip

Website will load.

Optional Steps
Add Domain

Use:
Amazon Route 53

Example:

www.example.com
Add SSL (HTTPS)

Use:
AWS Certificate Manager

Simple Deployment Flow
PHP Files → EC2
Database → RDS
Users → Website
Interview Answer (Short)

A PHP website can be hosted in AWS by launching an EC2 instance, installing Apache and PHP, uploading website files, creating a MySQL database in RDS, and connecting the PHP application to the RDS database securely.

============

How AWS Lambda Hosts an API (Serverless)
===========================================
AWS Lambda allows us to run backend code without managing servers.

Usually AWS Lambda works with:
Amazon API Gateway

AWS API Gateway is a managed service used to create, secure, and manage APIs. It receives client requests, sends them to backend services like Lambda or EC2, and returns responses to users.

AWS API Gateway (Simple Explanation)

Amazon API Gateway is a service used to create, manage, and secure APIs in AWS.
It acts like a middle layer between users and backend services.

Together they create a serverless API.

Simple Flow
------------
User Request
     ↓
API Gateway
     ↓
AWS Lambda Function
     ↓
Response Returned

What is Serverless?

Serverless means:

No server management
AWS handles scaling
Pay only when function runs

Example API
Suppose API:

GET/users

When user calls API:

API Gateway receives request
Lambda function executes code
Returns JSON response

Steps to Create Serverless API
==============================
Step 1: Open AWS Lambda

Go to:
AWS Lambda Console

Click:
Create Function

Step 2: Create Lambda Function

Choose:
Author from scratch

Runtime:
Node.js
Python
PHP (via custom runtime)
Java

Example function:

exports.handler = async (event) => {
    return {
        statusCode: 200,
        body: JSON.stringify({
            message: "API Working"
        })
    };
};

Step 3: Create API Gateway

Open:
Amazon API Gateway

Create:
HTTP API or REST API

Step 4: Connect API Gateway to Lambda

Add route:
GET /users
Attach Lambda function.

Step 5: Deploy API
AWS gives URL like:

https://abc123.execute-api.ap-south-1.amazonaws.com

Step 6: Test API
Open browser/Postman:

https://abc123.execute-api.ap-south-1.amazonaws.com/users

Response:

{
  "message": "API Working"
}
Benefits of Lambda APIs
No server management
Auto scaling
Low cost
Fast deployment
High availability
Real Example

Frontend:
React / Mobile App

Backend:
API Gateway + Lambda

Database:

Amazon DynamoDB
Amazon RDS
Interview Answer (Short)

AWS Lambda hosts serverless APIs using API Gateway. API Gateway receives HTTP requests and triggers Lambda functions, which process the request and return a response without managing servers.

=================

How to Upload Image in S3 Bucket and Use It
===============================================
Amazon S3 is used to store files like:

Images
Videos
PDFs
Backups
Step 1: Open S3

Login to AWS Console:

AWS S3 Console

Step 2: Create Bucket

Click:

Create Bucket

Example bucket name:

my-image-bucket

Choose region and create bucket.

Step 3: Upload Image

Open bucket → Click:

Upload

Select image:

photo.jpg

Click:

Upload
Step 4: Make Image Public

By default images are private.

To use image publicly:

Option 1: Public Access

Go to:

Permissions
Bucket Policy / Object Permissions

Enable public read access.

Step 5: Copy Image URL

Example:

https://my-image-bucket.s3.amazonaws.com/photo.jpg
Step 6: Use Image Anywhere
In HTML
<img src="https://my-image-bucket.s3.amazonaws.com/photo.jpg">
In CSS
background-image: url('https://my-image-bucket.s3.amazonaws.com/photo.jpg');
In PHP
echo $image_url;
Optional: Use CloudFront CDN

For faster delivery use:

Amazon CloudFront

Flow:

User → CloudFront CDN → S3 Bucket
Example Real Use Cases
Shopify product images
User uploads
AI generated images
Website assets
Profile pictures
Simple Architecture
Website/App → S3 Bucket → Image URL

Interview Answer (Short)

Images can be uploaded to an S3 bucket through the AWS Console or SDK. After making the object public or using signed URLs, the image URL can be used in websites, APIs, or applications.

========================================================================================================================================

# AWS Certified Cloud Practitioner Exam Questions & Answers


## 🌩️ **1. Compute Services**
AWS Compute Services run our applications in the cloud without buying or maintaining hardware.

| Service                              | Description                                                                   |
| ------------------------------------ | ----------------------------------------------------------------------------- |
| **EC2 (Elastic Compute Cloud)**      | Virtual servers in the cloud. You choose CPU, memory, storage, and OS.        |
| **Lambda**                           | Run code without managing servers — pay only for execution time (serverless). |
| **Elastic Beanstalk**                | Easy deployment for web apps — AWS manages scaling and provisioning.          |
| **ECS (Elastic Container Service)**  | Run Docker containers on AWS easily.                                          |
| **EKS (Elastic Kubernetes Service)** | Managed Kubernetes cluster on AWS.                                            |
| **Lightsail**                        | Simplified hosting for small apps, blogs, or websites (easy setup).           |
| **AWS Batch**                        | Runs large-scale batch computing jobs efficiently.                            |
| **Outposts**                         | Bring AWS infrastructure to on-premises environments.                         |

---

## 💾 **2. Storage Services**

| Service                         | Description                                                           |
| ------------------------------- | --------------------------------------------------------------------- |
| **S3 (Simple Storage Service)** | Object storage for any amount of data — used for backups, media, etc. |
| **EBS (Elastic Block Store)**   | Block storage used with EC2 instances (like hard drives).             |
| **EFS (Elastic File System)**   | Scalable shared file storage for multiple EC2 instances.              |
| **Glacier**                     | Low-cost long-term archival storage.                                  |
| **Storage Gateway**             | Connects on-premises storage with AWS cloud storage.                  |
| **FSx**                         | Managed Windows File Server or Lustre file systems.                   |


| Storage Class                  | Cost     | Retrieval Time      | Use Case                                |
| ------------------------------ | -------- | ------------------- | --------------------------------------- |
| **Glacier Instant Retrieval**  | Low      | Milliseconds (fast) | Medical records, photos, documents      |
| **Glacier Flexible Retrieval** | Very low | Minutes–Hours       | Backup, archives                        |
| **Glacier Deep Archive**       | Lowest   | 12–48 Hours         | Compliance, old data, long-term storage |


---

## 🗄️ **3. Database Services**

| Service                               | Description                                                          |
| ------------------------------------- | -------------------------------------------------------------------- |
| **RDS (Relational Database Service)** | Managed SQL databases (MySQL, PostgreSQL, Oracle, SQL Server, etc.). |
| **Aurora**                            | High-performance MySQL/PostgreSQL-compatible cloud database.         |
| **DynamoDB**                          | Fully managed NoSQL database with fast performance.                  |
| **Redshift**                          | Data warehouse for analytics and big data.                           |
| **ElastiCache**                       | In-memory cache (Redis/Memcached) to speed up apps.                  |
| **Neptune**                           | Graph database for relationship data (e.g., social networks).        |

---

## 🌐 **4. Networking & Content Delivery**

| Service                         | Description                                                               |
| ------------------------------- | ------------------------------------------------------------------------- |
| **VPC (Virtual Private Cloud)** | Isolated network within AWS for your resources.                           |
| **CloudFront**                  | Content Delivery Network (CDN) to deliver data globally with low latency. |
| **Route 53**                    | DNS and domain management service.                                        |
| **Direct Connect**              | Dedicated network connection between your data center and AWS.            |
| **API Gateway**                 | Create and manage APIs securely at scale.                                 |
| **App Mesh**                    | Service mesh to monitor and control microservices communication.          |


---

## 🔐 **5. Security, Identity & Compliance**

| Service                                  | Description                                                 |
| ---------------------------------------- | ----------------------------------------------------------- |
| **IAM (Identity and Access Management)** | Manage users, roles, and permissions.                       |
| **Cognito**                              | Add user sign-up, sign-in, and authentication to your apps. |
| **KMS (Key Management Service)**         | Manage encryption keys for data security.                   |
| **GuardDuty**                            | Threat detection and continuous security monitoring.        |
| **Shield**                               | DDoS protection for AWS apps.                               |
| **WAF (Web Application Firewall)**       | Protect web apps from common exploits.                      |
| **CloudHSM**                             | Hardware-based key storage for encryption.                  |

---

## 🧠 **6. Machine Learning & AI**

| Service         | Description                                                     |
| --------------- | --------------------------------------------------------------- |
| **SageMaker**   | Build, train, and deploy ML models quickly.                     |
| **Rekognition** | Image and video analysis (detect faces, objects, etc.).         |
| **Comprehend**  | Natural Language Processing (NLP) — extract insights from text. |
| **Lex**         | Build chatbots using the same tech as Alexa.                    |
| **Polly**       | Convert text to speech.                                         |
| **Translate**   | Language translation.                                           |
| **Transcribe**  | Speech-to-text service.                                         |

---

## 🧩 **7. Developer Tools**

| Service          | Description                                           |
| ---------------- | ----------------------------------------------------- |
| **CodeCommit**   | Private Git repositories (like GitHub).               |
| **CodeBuild**    | Build and test code automatically.                    |
| **CodeDeploy**   | Automate deployments to EC2 or on-prem servers.       |
| **CodePipeline** | Continuous Integration/Continuous Deployment (CI/CD). |
| **Cloud9**       | Online IDE for coding in the browser.                 |

---

## 🧾 **8. Management & Monitoring**

| Service             | Description                                            |
| ------------------- | ------------------------------------------------------ |
| **CloudWatch**      | Monitoring performance CPU, memory,logs, metrics, and system performance.|
| **CloudTrail**      | Record API calls and track user activity for auditing. |
| **Config**          | Track configuration changes in resources.              |
| **Trusted Advisor** | Recommendations for cost, performance, and security.   |
| **Systems Manager** | Manage servers and automation tasks across AWS.        |

1. AWS CloudWatch: The Performance Monitor
CloudWatch is all about performance and health.It tells you how your applications and servers are running.

2. AWS CloudTrail: The Auditor
CloudTrail is all about accountability and security.It records every single "API call" (action) taken in your account.


---

## 🧱 **9. Migration & Transfer**

| Service                              | Description                                                |
| ------------------------------------ | ---------------------------------------------------------- |
| **DMS (Database Migration Service)** | Migrate databases to AWS with minimal downtime.            |
| **SMS (Server Migration Service)**   | Migrate on-prem servers to AWS.                            |
| **Snowball / Snowmobile**            | Physical data transfer devices for moving large data sets. |
| **DataSync**                         | Transfer large amounts of data between on-prem and cloud.  |

---

## 🧮 **10. Analytics & Big Data**

| Service                     | Description                                              |
| --------------------------- | -------------------------------------------------------- |
| **Athena**                  | Query S3 data using SQL (serverless).                    |
| **EMR (Elastic MapReduce)** | Big data processing using Hadoop, Spark, etc.            |
| **Kinesis**                 | Real-time data streaming and analytics.                  |
| **QuickSight**              | Business intelligence (BI) dashboards and visualization. |
| **Data Pipeline**           | Automate data movement and transformation.               |

---

## 🧑‍💼 **11. Customer Engagement**

| Service                        | Description                                            |
| ------------------------------ | ------------------------------------------------------ |
| **Pinpoint**                   | Targeted push notifications, email, and SMS campaigns. |
| **SES (Simple Email Service)** | Send and receive bulk or transactional emails.         |
| **Connect**                    | Cloud contact center service for customer support.     |

---

## 🧰 **12. Other Services**

| Service                             | Description                                      |
| ----------------------------------- | ------------------------------------------------ |
| **IoT Core**                        | Connect IoT devices to AWS securely.             |
| **Step Functions**                  | Coordinate multiple AWS services into workflows. |
| **EventBridge (CloudWatch Events)** | Event bus for connecting apps and services.      |
| **AppSync**                         | Managed GraphQL API service.                     |
| **WorkSpaces**                      | Cloud-based virtual desktop environment.         |
| **AppRunner**                       | Quickly deploy containerized web apps and APIs.  |

---

| Concept               | Meaning (Simple)           |
| --------------------- | -------------------------- |
| **Agility**           | Fast changes & deployments |
| **Elasticity**        | Auto scale up/down         |
| **Scalability**       | Can handle more load       |
| **Reliability**       | Works without corruption   |
| **Fault Tolerance**   | Survives failures          |
| **High Availability** | Always available online    |


This comprehensive guide covers all exam domains with detailed questions and answers to help you pass the AWS Cloud Practitioner certification exam.


### How many AWS Regions are there?
**Answer:** As of 2026, Amazon Web Services (AWS) has:
🌍 36 AWS Regions
🏢 114 Availability Zones (AZs)


AWS currently operates two main infrastructure regions in 
India: Asia Pacific (Mumbai) 
and Asia Pacific (Hyderabad). 


## Domain 1: Cloud Concepts (26%)

### What is cloud computing?
**Answer:** Cloud computing is the delivery of computing services—including servers, storage, databases, networking, software, analytics, and intelligence—over the Internet ("the cloud") to offer faster innovation, flexible resources, and economies of scale.

### What are the three main cloud service models?
**Answer:**
- **IaaS (Infrastructure as a Service)**: Provides basic building blocks for cloud IT (e.g., EC2)


👉 You rent servers and manage everything yourself.

Popular Examples:

Amazon EC2
Google Compute Engine
Microsoft Azure Virtual Machines
DigitalOcean Droplets

- **PaaS (Platform as a Service)**: Removes the need for organizations to manage underlying infrastructure (e.g., Elastic Beanstalk)

You deploy your app, platform handles infrastructure.

Popular Examples:

Heroku
AWS Elastic Beanstalk
Google App Engine
Render



- **SaaS (Software as a Service)**: Complete software applications run and managed by service provider (e.g., Gmail, Salesforce)

Very Common Daily Apps:

Gmail
Google Drive
Dropbox
Zoom
Slack
Shopify
Salesforce
Netflix

How CDN Works (Simple Explanation)
====================================
A CDN (Content Delivery Network) is a network of servers located in different places around the world.
It helps websites load faster by delivering content from the server closest to the user.

One popular CDN service is Amazon CloudFront.

Example Without CDN

Suppose your website server is in India.

A user from India opens the website → fast
A user from the USA opens the website → slow because data travels a long distance

This increases:

Loading time
Server load
Latency

Example With CDN

With CDN:

Your website files are copied to multiple CDN servers worldwide.
When a user opens the website:
CDN finds the nearest server
Sends data from that nearby location
Website loads much faster.

===================================================================================================

AMI stands for:
Amazon Machine Image

Simple Meaning
AMI is a pre-configured template used to launch an EC2 instance.

It contains:

Operating System
Application software
Configurations
Storage settings

### What are the four main cloud deployment models?
**Answer:**
- **Public Cloud**: Services offered by third-party providers over the public Internet
- **Private Cloud**: Cloud services used exclusively by a single organization
- **Hybrid Cloud**: Combination of public and private clouds
- **Multi-Cloud**: Using multiple cloud providers

### What are the six advantages of cloud computing?
**Answer:**
1. **Trade capital expense for variable expense** - Pay only for what you use
2. **Benefit from massive economies of scale** - AWS can achieve lower costs than individuals
3. **Stop guessing about capacity** - Scale up/down as needed
4. **Increase speed and agility** - Launch resources in minutes
5. **Stop spending money running and maintaining data centers** - AWS handles infrastructure
6. **Go global in minutes** - Deploy applications worldwide quickly

### What is AWS's global infrastructure made of?
**Answer:**
- **Regions**: Geographic areas containing multiple Availability Zones
- **Availability Zones (AZs)**: Isolated data centers within a region
- **Edge Locations**: Points of presence for CloudFront CDN
- **Regional Edge Caches**: Caches content closer to users

### How many AWS Regions are there?
**Answer:** As of 2026, Amazon Web Services (AWS) has:
🌍 36 AWS Regions
🏢 114 Availability Zones (AZs)

### What is high availability in AWS? => minimal downtime
**Answer:** High availability refers to systems that remain operational and accessible for long periods with minimal downtime. AWS achieves this through:
- Multiple Availability Zones within regions
- Auto scaling
- Load balancing
- Fault-tolerant architectures

### What is scalability vs elasticity?
**Answer:**

1. Scalability

Scalability means increasing system capacity when needed.
You manually or permanently increase resources.

Example
Your website gets more users, so you upgrade:
Bigger server
More CPU
More RAM

This is scalability.

2. Elasticity

Elasticity means automatically adding/removing resources based on traffic.
Resources increase and decrease automatically.

Example
During sale → AWS adds servers automatically
After traffic drops → AWS removes extra servers

### What are the benefits of AWS's pay-as-you-go pricing?
**Answer:**
- No upfront costs
- Pay only for what you consume
- Scale costs with usage
- No long-term commitments required

## Domain 2: Security and Compliance (25%)

### What is AWS Identity and Access Management (IAM)?
**Answer:** IAM is a web service that helps you securely control access to AWS resources. 

It allows you to:
- Create and manage AWS users and groups
- Use permissions to allow/deny access to AWS resources
- Create roles for AWS services
- Enable multi-factor authentication (MFA)

### What is the principle of least privilege?
**Answer:** Grant users only the minimum permissions they need to perform their tasks. This is a core security best practice in AWS.

### What are IAM policies?
**Answer:** JSON documents that define permissions. They can be:
- **Identity-based policies**: Attached to users, groups, or roles
- **Resource-based policies**: Attached to resources like S3 buckets
- **Permissions boundaries**: Set maximum permissions for IAM entities

### What is an IAM role?
**Answer:** An IAM identity that you can create in your account that has specific permissions. Roles are intended to be assumable by anyone who needs them, unlike users which are meant for specific people.

### What is AWS Organizations?
**Answer:** AWS Organizations helps you centrally manage and govern your environment as you grow and scale your AWS resources. It allows you to:
- Create accounts and organize them into groups
- Apply policies across accounts
- Consolidate billing
- Enable cross-account access

### What is AWS CloudTrail?
**Answer:** A service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. 
It logs API calls and related events made by or on behalf of your AWS account.

### What is Amazon GuardDuty?
**Answer:** A threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts and workloads.

### What is AWS Shield?
**Answer:** A managed DDoS protection service that safeguards applications running on AWS. It provides:
- **AWS Shield Standard**: Automatic protection for all AWS customers
- **AWS Shield Advanced**: Enhanced protection with additional features

### What is AWS Web Application Firewall (WAF)?
**Answer:** A web application firewall that helps protect your web applications from common web exploits that could affect availability, compromise security, or consume excessive resources.

### What is encryption in AWS?
**Answer:** AWS provides encryption at rest and in transit:
- **Encryption at rest**: Data encrypted when stored (S3 SSE, EBS encryption)
- **Encryption in transit**: Data encrypted during transmission (TLS/SSL)

### What is AWS Key Management Service (KMS)?
**Answer:** A managed service that makes it easy for you to create and control the encryption keys used to encrypt your data.

### What are AWS compliance programs?
**Answer:** AWS complies with various standards including:
- SOC 1, 2, 3
- PCI DSS
- HIPAA
- GDPR
- ISO 27001
- FedRAMP

## Domain 3: Technology (33%)

### What is Amazon EC2?
**Answer:** Amazon Elastic Compute Cloud (EC2) is a web service that provides secure, resizable compute capacity in the cloud. It allows you to launch virtual servers called instances.

### What are EC2 instance types?
**Answer:** EC2 instances are categorized by use case:
- **General Purpose**: Balanced compute, memory, and networking (T3, M5)
- **Compute Optimized**: High-performance processors (C5)
- **Memory Optimized**: Large amounts of RAM (R5, X1)
- **Storage Optimized**: High I/O performance (I3, D2)
- **Accelerated Computing**: GPU instances (P3, G4dn)

### What is Amazon S3?
**Answer:** Amazon Simple Storage Service (S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance.

### What are S3 storage classes?
**Answer:**
- **S3 Standard**: General-purpose storage
- **S3 Intelligent-Tiering**: Automatically moves data between tiers
- **S3 Standard-IA**: Lower cost for infrequently accessed data
- **S3 One Zone-IA**: Single AZ storage for non-critical data
- **S3 Glacier**: Low-cost archival storage
- **S3 Glacier Deep Archive**: Lowest cost for long-term archival

### What is Amazon RDS?
**Answer:** Amazon Relational Database Service (RDS) is a managed database service that makes it easy to set up, operate, and scale a relational database in the cloud. It supports:
- MySQL
- PostgreSQL
- Oracle
- SQL Server
- MariaDB
- Amazon Aurora

### What is AWS Lambda?
**Answer:** AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers. You pay only for the compute time you consume.

### What is Amazon VPC?
**Answer:** Amazon Virtual Private Cloud (VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.

### What are VPC components?
**Answer:**
- **Subnets**: Segments of the VPC's IP address range
- **Internet Gateway**: Enables communication between VPC and internet
- **NAT Gateway**: Allows instances in private subnets to connect to internet
- **Security Groups**: Virtual firewalls for instances
- **Network ACLs**: Firewall for subnets
- **Route Tables**: Rules for directing network traffic

### What is Elastic Load Balancing?
**Answer:** AWS provides three types of load balancers:
- **Application Load Balancer (ALB)**: Layer 7, HTTP/HTTPS traffic
- **Network Load Balancer (NLB)**: Layer 4, TCP traffic
- **Classic Load Balancer (CLB)**: Legacy, both Layer 4 and 7

### What is Amazon CloudFront?
**Answer:** Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.

### What is AWS Auto Scaling?
**Answer:** AWS Auto Scaling monitors your applications and automatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost.

### What is Amazon Route 53?
**Answer:** Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service. It provides:
- Domain registration
- DNS routing
- Health checking
- Traffic flow

### What is AWS CloudFormation?
**Answer:** AWS CloudFormation provides a common language for you to describe and provision all the infrastructure resources in your cloud environment.

### What is Amazon SQS?
**Answer:** Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications.

### What is Amazon SNS?
**Answer:** Amazon Simple Notification Service (SNS) is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.

### What is Amazon CloudWatch?
**Answer:** Amazon CloudWatch is a monitoring and observability service that provides data and actionable insights to monitor your applications, respond to system-wide performance changes, and optimize resource utilization.

### What is AWS Elastic Beanstalk?
**Answer:** AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker.

### What is AWS Fargate?
**Answer:** AWS Fargate is a serverless compute engine for containers that works with both Amazon ECS and Amazon EKS.

### What is Amazon EKS?
**Answer:** Amazon Elastic Kubernetes Service (EKS) is a managed Kubernetes service to run Kubernetes in the AWS cloud and on-premises data centers.

### What is Amazon ECS?
**Answer:** Amazon Elastic Container Service (ECS) is a fully managed container orchestration service that makes it easy to deploy, manage, and scale containerized applications.

## Domain 4: Billing and Pricing (16%)

### What are the four fundamental pricing principles of AWS?
**Answer:**
1. **Pay as you go**: Pay only for what you use
2. **Pay less when you reserve**: Reserved Instances for steady usage
3. **Pay even less as AWS grows**: Benefit from economies of scale
4. **Pay less by using more**: Volume-based discounts

### What is AWS Free Tier?
**Answer:** AWS Free Tier provides customers with no-cost access to AWS services for 12 months following their AWS sign-up date. It includes:
- Always Free: Services that are free indefinitely
- 12 Months Free: Trial usage for 12 months
- Trials: Short-term free trials

### What are EC2 pricing models?
**Answer:**
- **On-Demand**: Pay for compute capacity by the hour/second with no long-term commitments
- **Reserved Instances**: Significant discount (up to 75%) for 1-3 year commitments
- **Spot Instances**: Bid for unused EC2 capacity, up to 90% discount
- **Savings Plans**: Flexible pricing model with commitment to consistent usage

### What is AWS Cost Explorer?
**Answer:** AWS Cost Explorer is a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

### What is AWS Budgets?
**Answer:** AWS Budgets gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount.

### What are AWS Cost Allocation Tags?
**Answer:** Cost allocation tags are labels you can attach to your AWS resources to organize and track your costs. You can use tags to:
- Group resources by department, project, or environment
- Allocate costs to different business units
- Track spending patterns

### What is AWS Trusted Advisor?
**Answer:** AWS Trusted Advisor is an online tool that provides real-time guidance to help you provision your resources following AWS best practices. It covers:
- Cost optimization
- Performance
- Security
- Fault tolerance
- Service limits

### What are the support plans in AWS?
**Answer:**
- **Basic**: Free, includes access to whitepapers, documentation, and support communities
- **Developer**: $29/month, email support, general guidance
- **Business**: $100/month, phone/email support, faster response times
- **Enterprise**: $15,000+/month, dedicated Technical Account Manager, consultative support

### What is AWS Pricing Calculator?
**Answer:** AWS Pricing Calculator is a web-based planning tool that you can use to create estimates for your AWS use cases.

### What is AWS Cost and Usage Report?
**Answer:** The AWS Cost and Usage Report contains the most comprehensive set of cost and usage data available. It includes additional metadata about AWS services, pricing, and reservations.

### What are Consolidated Billing features in AWS Organizations?
**Answer:** Consolidated billing allows you to:
- Pay for multiple accounts with one bill
- Get volume discounts across accounts
- Track charges across accounts
- Share Reserved Instances across accounts

### What is AWS Marketplace?
**Answer:** AWS Marketplace is a digital catalog with thousands of software listings from independent software vendors that make it easy to find, test, buy, and deploy software that runs on AWS.

### Additional Practice Questions

#### Cloud Concepts
1. **What is the AWS global infrastructure?**
   **Answer:** AWS global infrastructure consists of Regions, Availability Zones, and Edge Locations that provide high availability, fault tolerance, and low-latency access to AWS services.

2. **Explain the difference between vertical scaling and horizontal scaling.**
   **Answer:**
   - **Vertical scaling**: Increasing the size/capacity of a single instance (e.g., adding more CPU/RAM)
   - **Horizontal scaling**: Adding more instances to distribute load

3. **What is serverless computing?**
   **Answer:** Serverless computing allows you to run code without provisioning or managing servers. AWS Lambda is an example of serverless computing.

#### Security and Compliance
1. **What is the shared responsibility model?**
   **Answer:** AWS is responsible for security OF the cloud (physical infrastructure), while customers are responsible for security IN the cloud (data, applications, configurations).

2. **What is MFA in AWS?**
   **Answer:** Multi-Factor Authentication adds an extra layer of security by requiring users to provide two or more forms of identification before accessing AWS resources.

3. **What is AWS Config?**
   **Answer:** AWS Config is a service that enables compliance auditing, security analysis, and resource tracking by recording configuration changes of your AWS resources.

#### Technology
1. **What is the difference between EBS and Instance Store?**
   **Answer:**
   - **EBS**: Persistent block storage that survives instance termination
   - **Instance Store**: Temporary block storage tied to the instance lifecycle

2. **What is Amazon Aurora?**
   **Answer:** Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud that combines the performance and availability of high-end commercial databases with the simplicity and cost-effectiveness of open-source databases.

3. **What is AWS Direct Connect?**
   **Answer:** AWS Direct Connect is a cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS.

4. **What is Amazon DynamoDB?**
   **Answer:** Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale.

#### Billing and Pricing
1. **What is AWS Savings Plans?**
   **Answer:** AWS Savings Plans offer lower prices on Amazon EC2, AWS Lambda, and AWS Fargate usage, in exchange for a commitment to a consistent amount of usage (measured in $/hour) for a 1 or 3 year term.

2. **What is the difference between RI and Savings Plans?**
   **Answer:**
   - **Reserved Instances**: Specific instance type in specific region/AZ
   - **Savings Plans**: More flexible, apply across instance families and regions

3. **What is AWS Cost Anomaly Detection?**
   **Answer:** AWS Cost Anomaly Detection uses machine learning to continuously monitor your costs and usage to detect anomalous spend and root causes.

### Tips for Exam Success
- Focus on understanding concepts rather than memorizing
- Practice with AWS Free Tier services
- Review AWS documentation and whitepapers
- Take practice exams
- Understand the exam blueprint and weightings
- Be familiar with AWS pricing models and support plans

==============================================================
AWS Interview Questions and Answers (Simple Terms)
1. What is AWS?

AWS (Amazon Web Services) is a cloud platform that provides servers, storage, databases, networking, and many other services over the internet.

2. What is Cloud Computing?

Cloud computing means using IT resources like servers and storage through the internet instead of owning physical hardware.

3. What are the types of cloud services?
IaaS – Infrastructure as a Service (EC2)
PaaS – Platform as a Service (Elastic Beanstalk)
SaaS – Software as a Service (Gmail, Office365)
4. What is EC2 in AWS?

Amazon EC2 is a virtual server service used to run applications in the cloud.

5. What is S3?

Amazon S3 is a storage service used to store files, images, videos, backups, etc.

6. What is an AMI?

AMI (Amazon Machine Image) is a template used to create EC2 instances.

7. What is an EC2 Instance?

An EC2 instance is a virtual machine running in AWS.

8. What is Auto Scaling?

Auto Scaling automatically increases or decreases EC2 instances based on traffic.

9. What is Elastic Load Balancer?

Load Balancer distributes incoming traffic across multiple servers.

10. What is VPC?

Amazon VPC is a private virtual network inside AWS.

11. What is IAM?

AWS Identity and Access Management manages users, roles, and permissions in AWS.

12. What is a Security Group?

Security Group acts like a firewall for EC2 instances.

13. What is Route 53?

Amazon Route 53 is AWS DNS and domain management service.

14. What is CloudFront?

Amazon CloudFront is a CDN service used to deliver content faster globally.

15. What is RDS?

Amazon RDS is a managed relational database service.

16. What databases are supported by RDS?

MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Aurora.

17. What is DynamoDB?

Amazon DynamoDB is a fully managed NoSQL database.

18. Difference between S3 and EBS?
S3 → Object storage
EBS → Block storage attached to EC2
19. What is EBS?

Amazon EBS provides storage volumes for EC2 instances.

20. What is AWS Lambda?

AWS Lambda runs code without managing servers.

21. What is Serverless Computing?

Running applications without managing servers manually.

22. What is Elastic Beanstalk?

AWS Elastic Beanstalk helps deploy and manage applications easily.

23. What is CloudWatch?

Amazon CloudWatch monitors AWS resources and applications.

24. What is CloudTrail?

AWS CloudTrail records AWS account activities and API calls.

25. What is SNS?

Amazon SNS is a notification service for sending emails, SMS, etc.

26. What is SQS?

Amazon SQS is a message queue service for decoupling applications.

27. What is AWS Region?

A geographic area where AWS data centers are located.

28. What is an Availability Zone?

An isolated data center inside a region.

29. Difference between Region and Availability Zone?
Region = Geographic location
Availability Zone = Data center inside region
30. What is AWS CLI?

AWS Command Line Interface is a command-line tool to manage AWS services.

31. What is CloudFormation?

AWS CloudFormation automates infrastructure setup using templates.

32. What is EFS?

Amazon EFS is a shared file storage service.

33. What is the difference between EBS and EFS?
EBS → Attached to one EC2
EFS → Shared across multiple EC2 instances
34. What is AWS Glacier?

Amazon S3 Glacier is low-cost storage for backups and archives.

35. What is NAT Gateway?

Allows private servers to access the internet securely.

36. What is an Internet Gateway?

Connects a VPC to the internet.

37. What is a Subnet?

A smaller network inside a VPC.

38. Difference between Public and Private Subnet?
Public subnet → Has internet access
Private subnet → No direct internet access
39. What is Redshift?

Amazon Redshift is a data warehousing service for analytics.

40. What is API Gateway?

Amazon API Gateway helps create and manage APIs.

41. What is ECS?

Amazon ECS manages Docker containers.

42. What is EKS?

Amazon EKS is a managed Kubernetes service.

43. What is Docker?

Docker is a tool used to package applications into containers.

44. What is Kubernetes?

Kubernetes manages containerized applications.

45. What is Multi-Factor Authentication (MFA)?

Extra security using password plus OTP/authentication app.

46. What is the AWS Free Tier?

AWS Free Tier provides limited free usage for learning and testing.

47. What is a Key Pair in AWS?

A public and private key used to securely connect to EC2 instances.

48. What is the difference between Vertical and Horizontal Scaling?
Vertical Scaling → Increase server size
Horizontal Scaling → Add more servers
49. What is High Availability?

Keeping applications running even during failures.

50. Why should companies use AWS?
Easy scaling
Cost-effective
Secure
Fast deployment
Global infrastructure

=============================================

#############################################################

Cloud Concepts
=========================
Q1. What is cloud computing?
Cloud computing is the delivery of IT resources — servers, storage, databases, networking, analytics, and more — over the internet. It lets organizations rent these resources from a cloud provider rather than buying and managing physical infrastructure.

Example: A startup can launch its application on AWS and scale the resources automatically as more users join, without purchasing servers or renting a data center.

Q2. What are the types of cloud computing?

Public cloud: Services offered by providers like AWS, Microsoft Azure, or Google Cloud. Resources are shared across customers.

Private cloud: Dedicated infrastructure for one organization, either on-premises or hosted.

Hybrid cloud: A mix of public and private clouds that allows workloads to move between environments.

Example: A company may store sensitive data on a private cloud for compliance, while running its public-facing website on AWS.

Q3. What is IaaS?

Infrastructure as a Service (IaaS) provides virtualized computing resources over the internet. Customers manage operating systems, applications, and data while the provider maintains the hardware.

Example: Amazon EC2 is IaaS because it gives you virtual machines and storage while you manage the software and OS.

Q4. What is PaaS?
Platform as a Service (PaaS) provides a platform for building, testing, and deploying applications without managing the underlying infrastructure.

Sticky 
Konnektive
Salesforce
HubSpot CRM
Zoho CRM

Example: AWS Elastic Beanstalk lets developers deploy code and automatically handles capacity provisioning, load balancing, and health monitoring.

Q5. What is SaaS?
Software as a Service (SaaS) delivers software applications over the internet. The provider manages everything from infrastructure to application updates.

Gmail,zoho mail,zoom meeting

Example: Gmail or Salesforce are SaaS applications, where users log in and use the service without managing servers.

Q6. What is scalability?
Scalability is the ability of a system to handle increased load by adding resources, or to reduce resources when demand decreases.

Example: An e-commerce site scales its web servers during peak shopping season and scales down after the sale.

Q7. What is elasticity?
Elasticity is the ability of a system to automatically adjust resources in response to real-time demand.

Example: Auto Scaling can add EC2 instances when traffic spikes and remove them when traffic drops.

Q8. What is high availability?
High availability means keeping applications running with minimal downtime by using redundant resources and failover mechanisms.

Example: Deploying applications across multiple Availability Zones ensures service continuity when one zone fails.

Q9. What is fault tolerance?
Fault tolerance is the ability of a system to continue operating even when components fail. It requires redundancy and automatic recovery.

Example: A database configured with replication can continue processing requests when one node fails.

Q10. What is disaster recovery?
Disaster recovery is the strategy for restoring systems and data after a catastrophic event, such as a data center outage.

Example: Using cross-region backups and recovery plans to restore applications in a second AWS region after a regional outage.

Q11. What is RTO?
Recovery Time Objective is the maximum acceptable time to restore operations after a failure.

Example: If a business sets an RTO of 30 minutes, its recovery plan must bring services back online within half an hour.

Q12. What is RPO?
Recovery Point Objective is the maximum acceptable amount of data loss, measured in time.

Example: An RPO of 15 minutes means backups or replication must preserve data so no more than 15 minutes of work is lost.

Q13. What is serverless computing?
Serverless computing allows developers to run code without managing servers. The cloud provider automatically handles capacity, scaling, and infrastructure.

Example: AWS Lambda runs application code in response to events, such as file uploads or API requests, without provisioning servers.

Q14. What is the AWS Shared Responsibility Model?
AWS secures the cloud infrastructure, while customers secure their applications and data in the cloud.

AWS manages physical security, hardware, and networking.
Customers manage identity and access, data encryption, OS updates, and application security.
Example: AWS protects the data center, while you configure IAM policies and encrypt data stored in S3.

Q15. What are the benefits of cloud computing?
Key cloud benefits include:

Cost savings: pay only for what you use.
============================================
Scalability: grow resources with demand.
Elasticity: automatically adjust to traffic.
Global reach: deploy in multiple regions.
Security: built-in protections and compliance features.
Faster time to market: provision infrastructure quickly.
Example: A new mobile app can be deployed globally within hours using managed cloud services.


#################################################################################

AWS Global Infrastructure
=================================
Q1. What is an AWS Region? (conains muliple availabili zone.)
An AWS Region is a geographic area containing multiple Availability Zones. Regions are isolated from each other for fault tolerance and data residency requirements.

36  Region
114 aailablity zones

Example: Use us-east-1 for the eastern U.S. and eu-west-1 for Europe to keep data local and reduce latency.

Q2. What is an Availability Zone?
An Availability Zone (AZ) is an isolated data center within an AWS Region, with independent power, cooling, and networking.

Example: Deploying servers in multiple AZs protects your application from a single data center failure.

Q3. What is an edge location?
Edge locations are AWS sites used by CloudFront to cache content close to users. They reduce latency for downloads, streaming, and web requests.

Example: A website can serve images from an edge location near users in Asia for faster load times.

Q4. Why use multiple Availability Zones?
Using multiple AZs improves availability and fault tolerance by distributing resources across independent infrastructure.

Example: If one AZ becomes unavailable, traffic is routed to instances in another AZ.

Q5. What is AWS Local Zone?
AWS Local Zones place computing resources closer to end users in specific cities, offering very low latency.

Example: Video production workflows can run in a Local Zone near the studio for faster rendering.

Q6. What is AWS Wavelength?
AWS Wavelength extends AWS infrastructure into telecom provider networks for low-latency 5G applications.

Example: Real-time gaming or AR apps can use Wavelength zones to minimize latency for mobile users.

Q7. What is AWS Outposts?
AWS Outposts brings AWS infrastructure on-premises while using the same AWS APIs and tools.

Example: A hospital can run AWS services locally to meet strict data residency and latency requirements.

Q8. What is AWS Global Accelerator?
AWS Global Accelerator improves application availability and performance by routing traffic through the AWS global network.

Example: A global application uses Global Accelerator to send users to the nearest healthy endpoint automatically.

Q9. What is latency?
Latency is the delay between sending a request and receiving a response. Lower latency provides a better user experience.

Example: An application hosted near its users will have lower latency than one hosted far away.

Q10. What is cross-region replication?
Cross-region replication copies data from one AWS region to another for redundancy and disaster recovery.

Example: Using S3 cross-region replication to keep critical files synchronized between us-east-1 and eu-west-1.

EC2
============================

Q1. What is Amazon EC2?
Amazon Elastic Compute Cloud (EC2) provides resizable virtual servers in the cloud. You can choose the instance type, operating system, and storage configuration.

Example: Launch a Linux web server on EC2 to host a web application with full control over the environment.

Q2. What is an AMI?
An Amazon Machine Image (AMI) is a template containing the OS, application server, and software required to launch an EC2 instance.

Example: Use a standard Ubuntu AMI or create a custom AMI with your application dependencies preinstalled.

Q3. What is a key pair?
A key pair is a public/private SSH key pair used to securely connect to EC2 instances. AWS stores the public key and you keep the private key.

Example: Use ssh -i my-key.pem ec2-user@ec2-public-ip to access a Linux EC2 instance.

Q4. What is a Security Group?
A Security Group acts as a virtual firewall for EC2 instances. It controls inbound and outbound traffic using rules that specify ports, protocols, and IP ranges.

Example: Allow inbound HTTP on port 80 from anywhere, and SSH on port 22 from your office IP only.

Q5. What is an Elastic IP?
An Elastic IP is a static public IPv4 address for EC2 instances. It stays assigned to your account even if you stop and restart the instance.

Example: Assign an Elastic IP to a public web server so its address remains constant.

Q6. What is Auto Scaling?
Auto Scaling automatically adjusts the number of EC2 instances based on demand using scaling policies and CloudWatch metrics.

Example: Scale out more instances when CPU utilization exceeds 70%, and scale in when demand drops.

Q7. What is Elastic Load Balancer?
Elastic Load Balancer distributes incoming traffic across multiple EC2 instances. It helps maintain availability and prevents any single instance from becoming overloaded.

Example: An Application Load Balancer routes web requests to healthy instances across multiple AZs.

Q8. What are EC2 pricing models?
EC2 pricing models include:

On-Demand: pay per hour or second with no long-term commitment.
Reserved Instances: commit for 1 or 3 years for a lower hourly rate.
Spot Instances: bid on unused capacity at deep discounts, with possible interruptions.
Dedicated Hosts: physical servers dedicated to one customer.
Savings Plans: flexible discounts based on spend commitments.
Example: Use On-Demand for development, Reserved Instances for stable production workloads, and Spot Instances for batch jobs.

Q9. What are Spot Instances?
Spot Instances use spare EC2 capacity at significantly reduced prices. AWS may reclaim them with short notice, so they are best for fault-tolerant workloads.

Example: Run large data processing jobs on Spot Instances to reduce cost.

Q10. What are Reserved Instances?
Reserved Instances offer a lower price in exchange for a one- or three-year commitment. They are ideal for workloads with predictable demand.

Example: A production database that runs continuously can use a Reserved Instance to save money.

Q11. Difference between stop and terminate?
Stop: shuts down the instance and preserves data on attached EBS volumes. You can restart it later.
Terminate: deletes the instance and usually removes the root volume, destroying data unless explicitly preserved.
Example: Stop an instance when temporarily not needed, but terminate it when the workload is finished.

Q12. What is instance store?
Instance store is temporary storage attached directly to the EC2 host. It offers high performance but data is lost if the instance stops or terminates.

Example: Use instance store for cache, temporary files, or scratch space where durability is not required.

Q13. What is placement group?
A placement group is a logical grouping of instances for specific performance or availability requirements.

Cluster placement group: instances are placed close together for low network latency.
Spread placement group: instances are placed on separate hardware to reduce correlated failures.
Partition placement group: instances are divided into partitions to isolate failures.
Example: Use a cluster placement group for high-performance computing workloads.

Q14. What is hibernation in EC2?
Hibernation saves an instance’s RAM state to the EBS root volume before stopping it. When restarted, the instance resumes from where it left off.

Example: Use hibernation for development environments where you want to preserve in-memory state between sessions.

Q15. What is user data in EC2?
User data is a script or configuration passed to an EC2 instance at launch. It runs automatically during startup and is commonly used for bootstrapping.

Example: Use user data to install software, configure services, or join the instance to a cluster on first boot.

Lambda
============================

Amazon Web Services Amazon API Gateway is a service that helps developers create, manage, and secure APIs.

In simple words:

API Gateway acts like a middleman between:

Your frontend (website/mobile app)
And your backend services (server, database, Lambda, etc.)

What API Gateway does:

Receives API requests
Sends requests to the correct backend
Handles security/authentication
Controls traffic
Monitors API usage
Returns responses to users

Q1. What is AWS Lambda?
AWS Lambda is a serverless compute service where you run code in response to events without managing servers.

Example: A Lambda function processes images uploaded to S3 and stores resized versions in another bucket.

Q2. What triggers Lambda?
Lambda can be triggered by many AWS services, including:

S3 object creation
SNS notifications
API Gateway requests
EventBridge scheduled events
DynamoDB streams
CloudWatch alarms
SNS notifications

Example: An S3 upload event can trigger Lambda to validate a file and move it to the correct folder.

Q3. What is a cold start?
A cold start happens when Lambda initializes a new execution environment before running your code. This adds latency for the first request.

Example: Functions using Java or .NET typically have longer cold starts than lightweight Node.js or Python functions.

Q4. How is Lambda priced?
Lambda pricing is based on the number of requests and the execution duration weighted by allocated memory. You pay only for actual compute time.

Example: A function that runs for 100ms with 128 MB memory costs much less than a function that runs for 2 seconds with 1 GB memory.

Q5. What are Lambda layers?
Lambda layers are reusable packages that can be attached to functions. They let you share libraries, runtime dependencies, or common code across functions.

Example: Place the AWS SDK or custom utilities in a layer and use them across multiple Lambda functions.

Q6. What is provisioned concurrency?
Provisioned concurrency keeps Lambda environments initialized and ready to respond instantly, reducing cold starts.

Example: Use provisioned concurrency for APIs with strict latency requirements.

Q7. What is Lambda timeout?
Lambda timeout is the maximum execution time allowed for a function. If it exceeds this limit, Lambda stops the execution.

Example: Set the timeout to 30 seconds if a task should not run longer than that.

Q8. Can Lambda run inside a VPC?
Yes. Lambda can access resources within a VPC, such as private RDS databases or internal services, by configuring VPC access.

Example: A Lambda function inside a VPC can query a private Aurora database.

Q9. What are common Lambda use cases?
Common use cases include:

API backends
Data processing and ETL
Scheduled tasks
Event-driven automation
File processing
Example: Use Lambda to generate thumbnails when users upload images.

Q10. Difference between Lambda and EC2?
Lambda is serverless and event-driven, with no server management.

EC2 is a virtual machine where you manage the OS and runtime.
Example: Use Lambda for short-lived tasks and APIs, and EC2 for long-running applications or when you need full control.

S3 & Storage
=========================

Q1. What is Amazon S3?
Amazon S3 is object storage for storing and retrieving any amount of data from anywhere. It is designed for durability, scalability, and security.

Example: Store application logs, backups, media files, and static website assets in S3.

Q2. What is an S3 bucket?
An S3 bucket is a container for objects in S3. Every object is stored in a bucket and identified by a unique key.

Example: Create a bucket named my-app-assets and upload files like images/logo.png.

Q3. What are S3 storage classes?
S3 storage classes are designed for different access and cost patterns:

Standard: frequent access.
Intelligent-Tiering: automatic cost optimization.
Standard-IA: infrequent access.
One Zone-IA: infrequent access in a single AZ.

Glacier: archival storage.
Glacier Deep Archive: lowest-cost long-term archiving.

Example: Use Standard for current application data and Glacier for year-old archive logs.

Q4. What is versioning in S3?
Versioning keeps multiple versions of the same object. It protects against accidental deletion or overwriting.

Example: If someone overwrites a file, you can restore an earlier version from bucket history.

Q5. What is lifecycle management?
Lifecycle management automates object transitions between storage classes or expiration. It helps reduce cost by aging data automatically.

Example: Automatically move logs to Standard-IA after 30 days and to Glacier after 180 days.

Q6. What is S3 Glacier?
S3 Glacier is low-cost archival storage for data that is rarely accessed. Retrieval times can range from minutes to hours.

Example: Archive compliance records in Glacier for long-term retention.

Q7. What is multipart upload?
Multipart upload allows large objects to be uploaded in parts. It improves transfer reliability and can resume if a part fails.

Example: Upload a 10 GB video in multiple parts to avoid restarting the entire transfer after a network interruption.

Q8. What is bucket policy?
A bucket policy is a JSON document that defines access permissions for an S3 bucket. It controls who can perform actions on objects.

Example: Use a bucket policy to allow only a specific IAM role to upload files and deny public access.

Q9. What is server-side encryption?
Server-side encryption means AWS encrypts data at rest in S3 and decrypts it when accessed. AWS can manage the encryption keys, or you can use AWS KMS keys.

Example: Use SSE-S3 for default encryption or SSE-KMS for additional key control.

Q10. What are pre-signed URLs?
Pre-signed URLs grant temporary access to private S3 objects without requiring IAM credentials.

Example: Generate a URL that allows a user to download a file for one hour.

Q11. What is Amazon EBS?
Amazon Elastic Block Store (EBS) provides block storage volumes for EC2 instances. EBS volumes are durable and can be attached to instances like a hard drive.

Example: Use EBS for the disk that stores a database’s data files.

Q12. What is Amazon EFS?
Amazon Elastic File System (EFS) is a managed file storage service that multiple EC2 instances can mount and access simultaneously.

Example: Use EFS for shared application content in a cluster of web servers.

Q13. Difference between EBS and EFS?
EBS is block storage attached to a single EC2 instance.
EFS is shared file storage accessible by many instances.
Example: Use EBS for a single database server and EFS for shared configuration files across multiple instances.

Q14. What are EBS snapshots?
EBS snapshots are point-in-time backups of EBS volumes stored in S3. Snapshots are incremental and can be used to restore data or create new volumes.

Example: Take nightly snapshots of a database volume for recovery after corruption.

Networking & VPC
================================

Q1. What is a VPC?
A VPC is an isolated virtual network in AWS where you can launch resources like EC2 instances and RDS databases. It provides control over IP ranges, subnets, routing, and security.

Example: Create a VPC for a web application with separate public and private subnets.

Q2. What is a subnet?
A subnet is a segment of a VPC IP range. It groups resources into smaller network sections that can be public or private.

Example: Place public web servers in a public subnet and backend databases in a private subnet.

Q3. Difference between public and private subnet?
A public subnet has a route to the internet through an Internet Gateway, while a private subnet has no direct internet route.

Example: Place load balancers in public subnets and application servers in private subnets to protect backend systems.

Q4. What is an Internet Gateway?
An Internet Gateway enables internet access for resources in a VPC. It is attached to the VPC and allows traffic to flow between the VPC and the internet.

Example: Attach an Internet Gateway so public EC2 instances can send and receive traffic from the internet.

Q5. What is NAT Gateway?
A NAT Gateway allows instances in a private subnet to access the internet for updates or external services without exposing them to incoming traffic.

Example: Use a NAT Gateway so private EC2 instances can download patches from the internet.

Q6. What is Route 53?
Route 53 is AWS’s DNS and domain routing service. It translates domain names to IP addresses and can route traffic based on latency, geolocation, or health checks.

Example: Use Route 53 to direct www.example.com traffic to your application load balancer.

Q7. What is CloudFront?
CloudFront is AWS’s content delivery network (CDN) that caches content at edge locations to deliver it faster to users.

Example: Use CloudFront to speed up delivery of website images and videos worldwide.

Q8. What is VPC peering?
VPC peering connects two VPCs privately so resources can communicate as if they are in the same network.

Example: Peer a production VPC with a logging VPC so instances can securely send logs.

Q9. What is Transit Gateway?
Transit Gateway is a centralized hub that connects multiple VPCs and on-premises networks through a single gateway.

Example: Use Transit Gateway to simplify connectivity across several VPCs in different regions.

Q10. Difference between Security Group and NACL?
Security Groups are stateful firewalls controlling inbound and outbound traffic at the instance level. NACLs are stateless network filters applied at the subnet level.

Example: Use Security Groups for instance-level rules and NACLs as an additional subnet perimeter.

Q11. What is AWS Direct Connect?
AWS Direct Connect provides a dedicated network connection from your on-premises data center to AWS for more consistent bandwidth and lower latency.

Example: Use Direct Connect for stable connectivity between a corporate network and AWS.

Q12. What is AWS VPN?
AWS VPN establishes an encrypted connection between your on-premises network and your AWS VPC.

Example: Use VPN for secure remote access to AWS resources from a company office.

Q13. What is DNS?
DNS is the Domain Name System that translates human-readable domain names into IP addresses.

Example: When a browser requests example.com, DNS returns the address of the web server.

Q14. What is a route table?
A route table contains rules that direct network traffic within a VPC and between subnets.

Example: A route table can send all internet-bound traffic from a public subnet to the Internet Gateway.

Q15. What is AWS WAF?
AWS WAF is a Web Application Firewall that protects web applications from common web exploits.

Example: Use WAF to block malicious traffic patterns and prevent SQL injection attacks.

Databases
====================

Q1. What is Amazon RDS?
Amazon RDS is a managed relational database service. AWS handles database provisioning, backups, patching, and scaling.

Example: Use RDS to run MySQL, PostgreSQL, or SQL Server without managing the underlying database host.

Q2. Which databases does RDS support?
RDS supports MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.

Example: Choose PostgreSQL on RDS for open-source compatibility and managed database operations.

Q3. What is DynamoDB?
DynamoDB is a fully managed NoSQL database service designed for fast and predictable performance at any scale.

Example: Use DynamoDB for session storage or user profiles in a high-traffic application.

Q4. What is Amazon Aurora?
Amazon Aurora is a high-performance managed relational database compatible with MySQL and PostgreSQL.

Example: Use Aurora for large transactional applications that need faster performance than standard RDS.

Q5. What is Multi-AZ deployment?
Multi-AZ deployment creates a standby replica in another AZ for automatic failover if the primary DB fails.

Example: Use Multi-AZ for production databases that require high availability.

Q6. What is a read replica?
A read replica is a read-only copy of a database used to improve performance for read-heavy workloads.

Example: Use read replicas to offload reporting queries from the primary database.

Q7. Difference between SQL and NoSQL?
SQL databases use structured schemas and relational tables. NoSQL databases use flexible schemas and are optimized for scalability.

Example: Choose SQL for transactional applications and NoSQL for flexible, high-scale storage of unstructured data.

Q8. What is ElastiCache?
ElastiCache is a managed in-memory caching service supporting Redis and Memcached.

Example: Use ElastiCache to speed up database reads by caching popular queries.

Q9. What is Redshift?
Redshift is AWS’s data warehouse service for analyzing large data sets using SQL.

Example: Use Redshift to run analytics on historical sales data.

Q10. What is eventual consistency?
Eventual consistency means data updates propagate asynchronously, so reads may temporarily return stale data.

Example: DynamoDB eventually propagates writes across replicas, making it fast and scalable but not always immediately consistent.

Q11. What is database backup?
Database backup is a copy of data stored to recover from corruption or loss.

Example: Use automated RDS snapshots to back up a database daily.

Q12. What is DynamoDB partition key?
A partition key determines how data is distributed across storage partitions.

Example: Use a user ID as the partition key to ensure balanced throughput across items.

Q13. What is Aurora Serverless?
Aurora Serverless is an on-demand auto-scaling database deployment that adjusts capacity automatically.

Example: Use Aurora Serverless for development or unpredictable workloads to save cost.

Q14. What is database failover?
Database failover automatically switches to a standby database when the primary fails.

Example: In RDS Multi-AZ, failover ensures the application keeps working if the primary database becomes unavailable.

Q15. What is encryption in databases?
Encryption in databases protects stored data by using cryptographic keys.

Example: Enable encryption at rest for RDS and DynamoDB to secure sensitive customer information.

Security & IAM
=====================

Q1. What is IAM?
AWS IAM is Identity and Access Management for controlling who can access AWS resources.

Example: Use IAM to create users and roles with permissions for specific AWS services.

Q2. What is an IAM user?
An IAM user is an identity that represents a person or application and can have credentials.

Example: Create an IAM user for a developer who needs console access.

Q3. What is an IAM role?
An IAM role grants temporary permissions to trusted entities like EC2 instances or Lambda functions.

Example: Attach an IAM role to an EC2 instance so it can access S3 without storing credentials.

Q4. What is MFA?
Multi-Factor Authentication adds an additional verification step beyond username and password.

Example: Enable MFA for privileged IAM users to improve account security.

Q5. What is least privilege?
Least privilege means granting only the permissions required to perform a task.

Example: Give a user read-only access to S3 instead of full administrator rights.

Q6. What is AWS KMS?
AWS KMS is Key Management Service for creating and managing encryption keys.

Example: Use KMS to encrypt S3 objects and RDS databases with customer-managed keys.

Q7. What is AWS Shield?
AWS Shield protects against DDoS attacks at the network and transport layers.

Example: Use AWS Shield Standard to protect a public-facing website from common attacks.

Q8. What is AWS WAF?
AWS WAF is a Web Application Firewall that blocks malicious web requests.

Example: Use WAF to prevent common attacks like cross-site scripting and SQL injection.

Q9. What is AWS CloudTrail?
CloudTrail logs AWS API activity for audit and compliance.

Example: Use CloudTrail to track who created or modified IAM policies.

Q10. What is AWS Config?
AWS Config records resource configurations and evaluates them against compliance rules.

Example: Use Config to ensure S3 buckets are not publicly accessible.

Q11. What is AWS Organizations?
AWS Organizations helps manage multiple AWS accounts centrally.

Example: Use Organizations to apply consolidated billing and service control policies across accounts.

Q12. Difference between authentication and authorization?
Authentication verifies identity, while authorization determines what actions an identity can perform.

Example: Logging in is authentication; checking whether the user can access an S3 bucket is authorization.

Q13. What is encryption at rest?
Encryption at rest protects stored data using encryption while it is saved on disk.

Example: Enable encryption at rest for RDS and EBS volumes.

Q14. What is encryption in transit?
Encryption in transit protects data as it moves between systems.

Example: Use HTTPS or TLS for API calls and database connections.

Q15. What is Secrets Manager?
AWS Secrets Manager securely stores credentials, API keys, and other secrets.

Example: Store database passwords in Secrets Manager and retrieve them from an application securely.

Monitoring & Management
=============================

Q1. What is Amazon CloudWatch?
Amazon CloudWatch monitors AWS resources and applications using metrics, logs, and events.

Example: Use CloudWatch to track CPU usage on EC2 instances.

Q2. What are CloudWatch metrics?
CloudWatch metrics are numerical data points that measure resource performance.

Example: Metrics include CPU utilization, disk I/O, and network traffic.

Q3. What is a CloudWatch alarm?
A CloudWatch alarm triggers actions when a metric crosses a threshold.

Example: Send an alert or scale out instances when CPU utilization exceeds 80%.

Q4. Difference between CloudWatch and CloudTrail?
CloudWatch monitors performance and resource health, while CloudTrail logs API activity and user actions.

Example: Use CloudWatch for operational alerts and CloudTrail for auditing changes.

Q5. What is AWS Trusted Advisor?
Trusted Advisor provides best practice recommendations for security, cost, performance, and reliability.

Example: Use Trusted Advisor to identify unused EC2 instances and reduce costs.

Q6. What is AWS Health Dashboard?
AWS Health Dashboard shows the health and status of AWS services that affect your account.

Example: Check the dashboard for announcements about region outages.

Q7. What is AWS Systems Manager?
Systems Manager is an operational service for managing AWS resources and automating tasks.

Example: Use Systems Manager Run Command to patch instances across multiple environments.

Q8. What is CloudFormation?
CloudFormation is Infrastructure as Code service for provisioning AWS resources using templates.

Example: Use CloudFormation to deploy a VPC, subnets, and EC2 instances consistently.

Q9. What is AWS OpsWorks?
OpsWorks is a configuration management service that supports Chef and Puppet.

Example: Use OpsWorks to automate application deployment with Chef recipes.

Q10. What is observability?
Observability is understanding system behavior using metrics, logs, and traces.

Example: Combine CloudWatch metrics, application logs, and distributed traces to troubleshoot issues.

Billing & Pricing
=================================

Q1. What is the AWS Free Tier?
The AWS Free Tier offers free usage limits for many AWS services during the first 12 months or indefinitely for certain services.

Example: Use the Free Tier to experiment with EC2, S3, and Lambda without incurring charges.

Q2. What is pay-as-you-go pricing?
Pay-as-you-go means customers are billed only for the resources they consume.

Example: You pay for EC2 hours used and S3 storage consumed, rather than paying a fixed infrastructure fee.

Q3. What are Savings Plans?
Savings Plans offer discounted pricing in exchange for a commitment to a certain amount of spend over one or three years.

Example: Use Compute Savings Plans to lower costs for EC2, Lambda, and Fargate usage.

Q4. What is Cost Explorer?
Cost Explorer is a tool for viewing and analyzing AWS spending patterns.

Example: Use Cost Explorer to identify which services are driving your monthly costs.

Q5. What is AWS Budgets?
AWS Budgets lets you set spending or usage thresholds and receive alerts when you approach them.

Example: Create a budget alert for monthly EC2 spending.

Q6. What is consolidated billing?
Consolidated billing combines charges from multiple AWS accounts into one invoice.

Example: Use consolidated billing for a master account that oversees several project accounts.

Q7. What are data transfer charges?
Data transfer charges are fees for moving data between AWS services, regions, or the internet.

Example: Transferring data out of AWS to the internet incurs charges, while transfers within the same region are often free.

Q8. What is TCO?
Total Cost of Ownership compares the full cost of cloud infrastructure to traditional on-premises infrastructure.

Example: Use TCO analysis to demonstrate savings from moving data center servers to AWS.

Q9. What is AWS Marketplace?
AWS Marketplace is an online store for third-party software and services that can run on AWS.

Example: Purchase a security appliance or database license and deploy it directly to your AWS account.

Q10. How can AWS costs be optimized?
Optimize costs by using Reserved Instances, Auto Scaling, lifecycle policies, rightsizing resources, and monitoring usage.

Example: Use S3 lifecycle rules to move old data to cheaper storage classes and delete unused resources.



