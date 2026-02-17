# aws-3tier-web-application
Production-ready 3-tier web application deployed on AWS using S3, CloudFront, ALB, EC2, and RDS.
# AWS 3-Tier Web Application

##  Project Overview

This project demonstrates a production-style 3-tier web architecture deployed on AWS.

It includes:
- Static frontend hosted on Amazon S3
- Global CDN using CloudFront
- Application Load Balancer for routing
- Backend API running on EC2 (Node.js)
- MySQL database hosted on Amazon RDS (private subnet)
- Secure VPC networking with proper security groups

---

##  Architecture

User  
↓  
CloudFront (CDN + HTTPS)  
↓  
S3 (Frontend)  
↓  
Application Load Balancer  
↓  
EC2 (Node.js Backend)  
↓  
RDS (MySQL - Private Subnet)

---

##  AWS Services Used

- Amazon S3 (Static Website Hosting)
- Amazon CloudFront (CDN)
- Application Load Balancer (ALB)
- Amazon EC2 (Backend Server)
- Amazon RDS (MySQL)
- Amazon VPC (Public & Private Subnets)
- Security Groups
- Target Groups

---

##  Security Architecture

- RDS is deployed in a private subnet
- Database is NOT publicly accessible
- EC2 security group allows traffic only from ALB
- RDS security group allows traffic only from backend EC2
- CloudFront routes `/api/*` traffic to ALB

---

##  Key Features

- Fully functional 3-tier architecture
- CloudFront behavior routing (`/api/*`)
- CORS handled properly
- Target group health checks
- Secure database connectivity
- Scalable architecture design

---

##  Screenshots

- Architecture Diagram
- S3 Bucket Configuration
- CloudFront Distribution
- ALB + Target Group (Healthy)
- EC2 Instance
- RDS Instance (Private)
- Final Working Output

---

##  Backend Tech Stack

- Node.js
- Express.js
- MySQL
- CORS Middleware

---

##  How It Works

1. User accesses CloudFront URL.
2. CloudFront serves frontend from S3.
3. API calls to `/api/*` are routed to ALB.
4. ALB forwards traffic to EC2 backend.
5. Backend connects securely to RDS.
6. Response is returned via CloudFront.

---

##  Future Improvements

- Add HTTPS listener on ALB using ACM
- Implement Auto Scaling Group
- Add CI/CD using GitHub Actions
- Add custom domain with Route 53

---

##  Author

Shreya Pk
