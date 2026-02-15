# Project Setup Guide  
AWS EC2 + S3 + Reverse Proxy Architecture

This guide explains how to:

- Use two separate Chrome profiles for different IAM users  
- Log in to AWS using separate IAM accounts  
- Launch an EC2 instance with an Elastic IP  
- Create and configure an S3 bucket for application data  
- Configure Nginx as a reverse proxy to route traffic to EC2 app or S3  

---

## 📌 Architecture Overview

- **John (Developer IAM Account)** → EC2 setup  
- **Mary (Data Analyst IAM Account)** → S3 configuration  
- **EC2 Instance** → Hosts main application  
- **S3 Bucket** → Stores application data / static content  
- **Nginx (Reverse Proxy)** → Routes traffic based on URL path  

---

# 1️⃣ Create Two Separate Chrome Profiles

This ensures IAM sessions do not conflict.

### Steps:
1. Open Chrome.
2. Click the profile icon (top right).
3. Click **Add**.
4. Create:
   - Profile 1 → `John - Developer`
   - Profile 2 → `Mary - Data Analyst`

Use:
- John profile for EC2 tasks  
- Mary profile for S3 tasks  

---

# 2️⃣ AWS Management Console Access

## Login as John (Developer IAM Account)

1. Open Chrome using **John’s profile**.
2. Go to:  
3. Enter:
- IAM Username: `John`
- Password
4. Sign in to AWS Management Console.

---

# 3️⃣ EC2 Instance Setup (John)

## Step 1: Launch EC2 Instance

1. Navigate to **EC2 Dashboard**
2. Click **Launch Instance**
3. Configure:
- Name: `main-app-server`
- AMI: Amazon Linux 2
- Instance type: `t2.micro` (Free Tier eligible)
- Key pair: Create or select existing
- Security Group:
  - Allow HTTP (80)
  - Allow HTTPS (443)
  - Allow SSH (22)

4. Click **Launch Instance**

---

## Step 2: Allocate and Associate Elastic IP

1. Go to **EC2 → Elastic IPs**
2. Click **Allocate Elastic IP**
3. Click **Associate**
4. Select your EC2 instance

Now your EC2 has a static public IP.

---

# 4️⃣ S3 Bucket Configuration (Mary)

## Login as Mary (Data Analyst IAM Account)

1. Open Chrome using **Mary’s profile**
2. Login to AWS Console with Mary’s IAM credentials

---

## Step 1: Create S3 Bucket

1. Go to **S3**
2. Click **Create bucket**
3. Configure:
- Bucket name: `app-data-bucket-unique-name`
- Region: Same as EC2
4. Disable “Block all public access” (if hosting static website)
5. Create bucket

---

## Step 2: Configure Bucket for Static Website Hosting

1. Open the bucket
2. Go to **Properties**
3. Enable **Static website hosting**
4. Set:
- Index document: `index.html`
- Error document: `error.html`

---

## Step 3: Configure Bucket Policy (Public Read Example)

```json
{
"Version": "2012-10-17",
"Statement": [
 {
   "Sid": "PublicReadAccess",
   "Effect": "Allow",
   "Principal": "*",
   "Action": "s3:GetObject",
   "Resource": "arn:aws:s3:::app-data-bucket-unique-name/*"
 }
]
}

## 5️⃣ Reverse Proxy Configuration (Nginx on EC2)
Step 1: Connect to EC2 via SSH
ssh -i your-key.pem ec2-user@<Elastic-IP>

Step 2: Install Nginx

For Amazon Linux:

sudo yum update -y
sudo yum install nginx -y


Start and enable:

sudo systemctl start nginx
sudo systemctl enable nginx

Step 3: Configure Reverse Proxy

Edit Nginx config:

sudo nano /etc/nginx/nginx.conf


Example configuration:

server {
    listen 80;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }

    location /static/ {
        proxy_pass http://app-data-bucket-unique-name.s3-website-region.amazonaws.com/;
    }
}

Step 4: Restart Nginx
sudo systemctl restart nginx
