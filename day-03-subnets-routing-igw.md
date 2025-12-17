# Day 03 – Subnets, Route Tables & Internet Gateway (IGW)

## 🎯 Objective
To understand how AWS Subnets work and how internet connectivity is controlled using Route Tables and Internet Gateway inside a VPC.

---

## 🧱 What is a Subnet?
A **Subnet** is a range of IP addresses inside a VPC.  
It allows you to organize and isolate resources within a VPC.

AWS supports:
- **Public Subnet**
- **Private Subnet**

---

## 🌐 Public Subnet
A subnet is called **Public** when:
- It has a route to an **Internet Gateway (IGW)**
- Instances inside it can access the internet
- Instances can receive public IP addresses

**Example CIDR:**
10.0.1.0/24

---

## 🔐 Private Subnet
A subnet is called **Private** when:
- It does NOT have a route to an Internet Gateway
- Instances cannot access the internet directly
- Used for databases and backend services

**Example CIDR:**
10.0.2.0/24

---

## 🌍 What is an Internet Gateway (IGW)?
An **Internet Gateway** allows communication between:
- Resources in a VPC
- The public internet

### Key Points:
- One IGW per VPC
- Required for public internet access
- Must be attached to a VPC

---

## 🛣️ What is a Route Table?
A **Route Table** defines how traffic is routed within a VPC.

### Important Route:
0.0.0.0/0 → Internet Gateway
This route allows traffic to go anywhere on the internet.

---

## 🔄 Public Route Table Configuration
Steps:
1. Create a Route Table
2. Add route:
   - Destination: `0.0.0.0/0`
   - Target: Internet Gateway
3. Associate the Route Table with the **Public Subnet**

This makes the subnet public.

---

## 🧠 Auto-Assign Public IP
To allow EC2 instances to receive public IPs:
- Enable **Auto-assign public IPv4 address** on the public subnet

Without this, instances will not be reachable from the internet.

---

## 🏗️ Architecture Overview

VPC (10.0.0.0/16)
│
├── Public Subnet (10.0.1.0/24)
│ ├── Route: 0.0.0.0/0 → IGW
│ └── Internet Access ✅
│
└── Private Subnet (10.0.2.0/24)
└── No Internet Access ❌

---

## 📌 Key Takeaways
- Subnets divide a VPC into smaller networks
- Internet access is controlled by **Route Tables**
- IGW is mandatory for public access
- Public and Private subnets improve security and design

---

## ✅ Status
**Day 03 – Completed Successfully**
