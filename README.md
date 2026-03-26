#  AWS 2-Tier MERN Stack Deployment Project

##  Project Overview

This project demonstrates how to deploy a **production-style MERN stack application** on **AWS using a 2-tier architecture** with:

* Application Load Balancer (ALB)
* Auto Scaling Groups (ASG)
* Private/Public Subnet Architecture
* MongoDB Atlas Integration
* High Availability Design
* Secure Backend Deployment

The goal is to simulate an **industry-standard scalable cloud deployment architecture**.

---

#  Problem Statement

A MERN stack application currently runs on a **single local server**, causing:

* Single Point of Failure
* No scalability support
* No load balancing
* Backend exposed publicly
* No production-grade database setup
* No infrastructure separation between frontend & backend

This project solves these issues by deploying the application on **AWS using a secure and scalable 2-tier architecture**.

---

#  Architecture Diagram

```
User
  │
  ▼
Public Application Load Balancer
  │
  ▼
Frontend Auto Scaling Group (React App)
  │
  ▼
Internal Application Load Balancer
  │
  ▼
Backend Auto Scaling Group (Node.js API)
  │
  ▼
MongoDB Atlas (Managed Database)
```

---

# ☁️ AWS Services Used

| Service             | Purpose                        |
| ------------------- | ------------------------------ |
| VPC                 | Custom network isolation       |
| Public Subnets      | Load Balancer layer            |
| Private Subnets     | Backend application layer      |
| Internet Gateway    | Public internet access         |
| NAT Gateway         | Private subnet outbound access |
| EC2                 | Application hosting            |
| ALB                 | Traffic distribution           |
| Launch Templates    | Instance configuration         |
| Auto Scaling Groups | Horizontal scaling             |
| Security Groups     | Firewall control               |
| MongoDB Atlas       | Managed database service       |

---

#  Infrastructure Design

## Tier 1 – Frontend Layer

React application deployed:

* Behind Public Application Load Balancer
* Inside Auto Scaling Group
* Multi-AZ deployment
* Publicly accessible

---

## Tier 2 – Backend Layer

Node.js + Express backend deployed:

* Inside Private Subnets
* Behind Internal Load Balancer
* Connected securely to MongoDB Atlas
* Auto-scaled based on CPU utilization

---

#  Database Layer

MongoDB Atlas is used as managed database service.

Benefits:

* Fully managed cloud database
* Secure connection string authentication
* No EC2 database hosting required
* Built-in availability & backup support

---

#  Security Implementation

Security best practices followed:

* Backend deployed inside private subnet
* Only Load Balancer exposed publicly
* Frontend communicates with backend internally
* SSH restricted via IP-based access
* Security Groups follow least-privilege principle
* MongoDB credentials secured using environment variables / Secrets Manager

---

#  Scalability Features

This architecture supports:

* Horizontal scaling using Auto Scaling Groups
* Load-balanced traffic distribution
* Multi-AZ deployment
* Automatic unhealthy instance replacement

---

#  Networking Architecture

Custom VPC configured with:

| Component        | Purpose                 |
| ---------------- | ----------------------- |
| Public Subnet    | Load Balancer hosting   |
| Private Subnet   | Backend hosting         |
| Internet Gateway | Public connectivity     |
| NAT Gateway      | Secure outbound traffic |

---

#  Deployment Workflow

### Step 1

Create Custom VPC

### Step 2

Create Public & Private Subnets

### Step 3

Attach Internet Gateway

### Step 4

Configure NAT Gateway

### Step 5

Deploy Backend EC2 Instance

### Step 6

Connect Backend with MongoDB Atlas

### Step 7

Create Backend AMI

### Step 8

Create Backend Launch Template

### Step 9

Configure Backend Auto Scaling Group

### Step 10

Deploy Frontend EC2 Instance

### Step 11

Configure Frontend API Endpoint

### Step 12

Create Frontend AMI

### Step 13

Create Frontend Launch Template

### Step 14

Configure Frontend Auto Scaling Group

### Step 15

Create Public Application Load Balancer

### Step 16

Create Internal Application Load Balancer

### Step 17

Attach Target Groups

### Step 18

Configure Security Groups

### Step 19

Configure Auto Scaling Policies

---

# 📊 Expected Outcome

After deployment:

```
User → Public ALB → Frontend → Internal ALB → Backend → MongoDB Atlas
```

Results:

✅ High availability
✅ Secure backend infrastructure
✅ Production-ready architecture
✅ Horizontally scalable deployment
✅ Industry-standard AWS implementation

---

# ⭐ Future Improvements

Possible enhancements:

* HTTPS using ACM
* Route53 domain setup
* Docker container deployment
* Jenkins CI/CD pipeline
* GitHub Actions automation
* CloudWatch monitoring dashboards
* AWS WAF integration

---

# Setup Guide
* https://www.notion.so/Deploy-MERN-Project-on-AWS-32f50c8296ee8049a9d8d088151ee4f6?source=copy_link

# 👨‍💻 Author

**Mayank Mishra**

DevOps Engineer | Cloud Engineer | Corporate Trainer
Specializing in AWS • Azure • Docker • CI/CD • MERN Stack Deployment
