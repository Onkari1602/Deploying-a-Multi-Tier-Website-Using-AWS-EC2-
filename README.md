# 🚀 Deploying a Multi-Tier Website Using AWS EC2

## 📘 Project Overview

This project demonstrates the deployment of a scalable, highly available **PHP-MySQL website** using **Amazon EC2**, **Amazon RDS**, and **Auto Scaling Groups** on AWS.

---

## 🛠 Tech Stack

- **Amazon EC2** – For hosting the PHP website
- **Amazon RDS (MySQL)** – For backend database
- **Auto Scaling Group** – For high availability
- **Security Groups** – For network access control
- **PHP, MySQL**
- **Shell Scripting** – For automation

---

## 🔧 Project Steps

1. **Launch EC2 Instances**
   - Install Apache, PHP, and required packages
   - Deploy website code
   - Configure security groups

2. **Create RDS MySQL Instance**
   - Database Name: `intel`
   - Table Name: `data`
   - User: `admin`
   - Password: `intel123`

3. **Connect Website to RDS**
   - Replace `localhost` in `index.php` with RDS endpoint

4. **Enable Auto Scaling**
   - Create a Launch Template
   - Create Auto Scaling Group (min: 2 instances)

5. **Security Group Rules**
   - Allow EC2 instances to communicate with RDS (port 3306)
   - Allow HTTP (port 80) to EC2 from the internet

---

---

## 📂 Folder Structure

multi-tier-website-aws/
├── README.md
├── architecture-diagram.png
├── setup/
│ ├── ec2-setup.sh
│ ├── rds-setup.sql
│ └── asg-launch-template.json
├── website/
│ └── index.php
├── scripts/
│ └── change-hostname.sh

pgsql
Copy
Edit

---

## 🚀 How to Deploy

1. **Launch EC2 Instance** using `setup/ec2-setup.sh`
2. **Create RDS Instance** and run `setup/rds-setup.sql` via MySQL client
3. **Update DB Host** in `website/index.php` using `scripts/change-hostname.sh`
4. **Create Launch Template & Auto Scaling Group**
5. **Test Availability** by terminating EC2s and watching new instances spin up

---

## 📊 Example Database Table

```sql
CREATE DATABASE intel;
USE intel;

CREATE TABLE data (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100)
);
🙋‍♂️ Author
Onkar L. Ingale
Cloud Engineer | AWS | Azure | Devops
📍 Pune, India
📧 [onkarroi1602@gmail.com]
