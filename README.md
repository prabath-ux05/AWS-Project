# 🌐 AWS Multi-Region WordPress Deployment with Disaster Recovery

![AWS](https://img.shields.io/badge/AWS-Cloud-FF9900)
![EC2](https://img.shields.io/badge/Amazon%20EC2-Compute-orange)
![RDS](https://img.shields.io/badge/Amazon%20RDS-Database-blue)
![Route53](https://img.shields.io/badge/Amazon%20Route53-DNS-green)
![S3](https://img.shields.io/badge/Amazon%20S3-Storage-red)
![WordPress](https://img.shields.io/badge/WordPress-CMS-21759B)

---

## 📌 Overview

AWS Multi-Region WordPress Deployment with Disaster Recovery is a cloud infrastructure project focused on high availability, fault tolerance, and business continuity. The solution deploys WordPress across multiple AWS regions with production and disaster recovery environments, automated DNS failover, SSL integration, database replication strategy, and content synchronization.

The architecture leverages AWS networking services, Route 53 health checks, Elastic Load Balancers, Amazon RDS, S3 synchronization, and WordPress application servers to ensure seamless failover during outages while maintaining application availability and data consistency.

This project demonstrates practical cloud engineering skills including multi-region deployments, disaster recovery planning, DNS failover automation, infrastructure design, and highly available application hosting. :contentReference[oaicite:0]{index=0}

---

## ✨ Key Features

### ☁️ Multi-Region Architecture

- Mumbai Region Deployment
- Ohio Region Deployment
- Cross-Region Infrastructure
- Production & DR Environments
- Regional Isolation

### 🌐 High Availability

- Route 53 Failover Routing
- Health Check Monitoring
- Load Balancer Integration
- DNS-Based Failover
- Automated Recovery

### 🏗️ AWS Infrastructure

- Custom VPC Design
- Public & Private Subnets
- Internet Gateway
- NAT Gateway
- Route Tables

### 🗄️ Database Architecture

- Amazon RDS
- Production Database
- Disaster Recovery Database
- Private Subnet Deployment

### 🔒 Security & SSL

- AWS Certificate Manager
- HTTPS Configuration
- IAM Role Integration
- Secure DNS Routing

### 📦 Content Synchronization

- Amazon S3 Integration
- Automated Cron Jobs
- Production-to-DR Sync
- Media Asset Replication
- Website Backup Strategy

---

## 🏗️ Solution Architecture

```text
                     Users
                       │
                       ▼

                  Route 53
                       │
         ┌─────────────┴─────────────┐
         │                           │
         ▼                           ▼

   Production Region             DR Region
     (Mumbai)                     (Ohio)

         │                           │
         ▼                           ▼

        ELB                         ELB
         │                           │
         ▼                           ▼

        EC2                         EC2
      WordPress                   WordPress
         │                           │
         ▼                           ▼

        RDS                         RDS
         │                           │
         └──────────┬────────────────┘
                    ▼

                 Amazon S3
            Content Synchronization
```

---

<details>
<summary><strong>⚙️ Tech Stack</strong></summary>

### ☁️ Cloud Platform

- AWS EC2
- Amazon RDS
- Amazon S3
- Route 53
- Elastic Load Balancer
- AWS IAM

### 🌐 Networking

- VPC
- Public Subnets
- Private Subnets
- NAT Gateway
- Internet Gateway
- Route Tables

### 🔒 Security

- AWS Certificate Manager (ACM)
- SSL/TLS Certificates
- IAM Roles

### 💻 Application

- WordPress
- Apache HTTP Server
- PHP

### 🌍 DNS & Domains

- Route 53
- GoDaddy Domain Integration
- Health Checks
- Failover Routing

### ⚙️ Automation

- Linux Cron Jobs
- AWS CLI
- S3 Sync Operations

</details>

---

## 🔄 Deployment Workflow

```text
Custom VPC Setup
        →
Networking Configuration
        →
EC2 Provisioning
        →
RDS Deployment
        →
WordPress Installation
        →
SSL Configuration
        →
Load Balancer Setup
        →
Route 53 DNS Mapping
        →
S3 Synchronization
        →
Failover Testing
```

---

## 🌍 Multi-Region Architecture

```text
Mumbai Region
     │
     ├── Production ELB
     ├── Production EC2
     ├── Production RDS
     │
     ▼

Route 53 Failover Routing

     ▲
     │

Ohio Region
     │
     ├── DR ELB
     ├── DR EC2
     ├── DR RDS
```

---

## 🖼️ Project Preview

### 🔀 Flow Architecture 

<p align="center">
  <img src="docs/flow-architecture.png" width="90%">
</p>

### 🌐 VPC Architecture

<p align="center">
  <img src="docs/vpc-architecture.png" width="90%">
</p>

### 🖥️ WordPress Deployment

<p align="center">
  <img src="docs/wordpress-dashboard.png" width="90%">
</p>

### 🌍 Route 53 Failover Configuration

<p align="center">
  <img src="docs/route53-failover.png" width="90%">
</p>

### 📦 S3 Synchronization

<p align="center">
  <img src="docs/s3-sync.png" width="90%">
</p>

---

<details>
<summary><strong>📁 Project Structure</strong></summary>

```text
AWS-WordPress-MultiRegion-DR/
│
├── docs/
│   ├── vpc-architecture.png
│   ├── route53-failover.png
│   ├── wordpress-dashboard.png
│   └── s3-sync.png
│
├── scripts/
│   ├── wordpress-install.sh
│   ├── production-sync.sh
│   └── dr-sync.sh
│
├── architecture/
│   ├── networking-design.md
│   ├── route53-design.md
│   └── failover-workflow.md
│
└── README.md
```

</details>

---

## 🌐 VPC Architecture

The infrastructure uses custom Virtual Private Clouds across multiple AWS regions.

### Components

- Custom VPC
- Public Subnets
- Private Subnets
- Internet Gateway
- NAT Gateway
- Route Tables

### Benefits

- Network Isolation
- Secure Database Access
- Controlled Internet Access
- Multi-AZ Readiness

---

## 🗄️ Database Layer

Amazon RDS is deployed within private subnets for improved security and isolation.

### Database Architecture

```text
WordPress Application
          │
          ▼

      Amazon RDS
          │
          ▼

 Production Database
          │
          ▼

 Disaster Recovery Database
```

### Benefits

- Managed Database Service
- Improved Security
- Automated Backups
- Disaster Recovery Support

---

## 🌍 Route 53 Failover Routing

Route 53 continuously monitors the health of the production environment.

### Workflow

```text
User Request
      →
Route 53
      →
Health Check Validation
      →
Healthy ?
      ↓

     Yes → Production ELB

     No
      ↓

Disaster Recovery ELB
```

### Benefits

- Automated Failover
- Reduced Downtime
- Improved Availability
- DNS-Level Recovery

---

## 📦 S3 Synchronization Strategy

Amazon S3 is used to synchronize WordPress assets between Production and DR environments.

### Sync Workflow

```text
Production WordPress → Amazon S3 → DR WordPress
```

### Synced Components

- Media Uploads
- WordPress Content
- Application Assets
- Website Files

---

## 🔐 SSL & Domain Integration

### Implemented Services

- AWS Certificate Manager
- Route 53 Hosted Zones
- GoDaddy DNS Integration
- HTTPS Configuration

### Benefits

- Secure Traffic Encryption
- Automated Certificate Management
- Trusted HTTPS Access

---

## 🚀 Deployment Steps

### Create Networking Infrastructure

- Create VPC
- Create Public Subnets
- Create Private Subnets
- Configure NAT Gateway
- Configure Internet Gateway

### Deploy Compute Resources

- Launch EC2 Instances
- Attach IAM Roles
- Configure Security Groups
- Install WordPress

### Configure Database

- Create RDS Instances
- Configure Subnet Groups
- Connect WordPress to RDS

### Configure High Availability

- Create Load Balancers
- Configure Route 53
- Configure Health Checks
- Implement Failover Routing

### Configure Synchronization

- Create S3 Buckets
- Configure Cron Jobs
- Enable Content Replication

---

## 🛠️ Engineering Highlights

- Multi-Region AWS Deployment
- Disaster Recovery Architecture
- Route 53 Automated Failover
- DNS Health Monitoring
- High Availability Design
- Amazon RDS Deployment
- WordPress Production Hosting
- SSL Certificate Integration
- S3-Based Content Synchronization
- Multi-VPC Networking Design
- Load Balancer Integration
- Automated Recovery Strategy

---

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

- AWS Cloud Architecture
- High Availability Systems
- Disaster Recovery Planning
- Route 53 Failover Routing
- Multi-Region Deployments
- WordPress Hosting
- Amazon RDS Administration
- SSL Certificate Management
- DNS Management
- Cloud Networking
- S3 Synchronization
- Production Infrastructure Design

---

## 🔮 Future Enhancements

### High Availability

- Auto Scaling Groups
- Multi-AZ RDS
- Global Load Balancing

### Security

- AWS WAF
- Secrets Manager
- IAM Least Privilege Policies

### Observability

- Amazon CloudWatch
- SNS Alerts
- Centralized Logging

### Automation

- Terraform IaC
- Jenkins CI/CD
- Automated Disaster Recovery Testing

---

## 📄 License

This project is intended for educational, learning, and portfolio demonstration purposes.

---

## 👨‍💻 Author

**Prabath D**
