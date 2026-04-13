
# AWS VPC Network Architecture Project (Public & Private Subnets)

## 📌 Project Overview
This project demonstrates the design and implementation of a secure and scalable AWS Virtual Private Cloud (VPC) architecture.  
The environment includes public and private subnets, route tables, an Internet Gateway, and EC2 instances to simulate a real-world production network setup.

The main goal is to understand how cloud network segmentation, routing, and security work in AWS.

---

## 🏗 Architecture Summary
The following components were implemented:

- Custom VPC with defined CIDR block
- Public Subnet for internet-facing resources
- Private Subnet for internal resources
- Internet Gateway (IGW)
- Route Tables for traffic control
- EC2 Instances in both subnets
- Security Groups for access control

---

## 🌐 Network Design Logic

- The **Public Subnet** is associated with a route table that routes traffic to the Internet Gateway, allowing internet access.
- The **Private Subnet** does not have direct internet access, ensuring higher security for internal resources.
- EC2 instances in the public subnet can communicate externally, while private instances remain isolated.
- Security Groups control inbound and outbound traffic at the instance level.

---

## ⚙️ Step-by-Step Implementation

### 1. Created VPC
- Defined a custom CIDR block for the VPC
- Enabled DNS resolution and DNS hostnames

### 2. Created Subnets
- Created a Public Subnet for internet-facing resources
- Created a Private Subnet for internal workloads
- Assigned appropriate CIDR ranges

### 3. Configured Internet Gateway
- Created an Internet Gateway
- Attached it to the VPC

### 4. Route Table Configuration
- Created a route table for the Public Subnet
- Added route `0.0.0.0/0 → Internet Gateway`
- Associated route table with Public Subnet

### 5. Launched EC2 Instances
- Deployed EC2 instance in Public Subnet
- Deployed EC2 instance in Private Subnet

### 6. Security Groups
- Configured inbound rules for SSH/HTTP access (where required)
- Restricted access for private instances

### 7. Testing
- Verified internet access from Public EC2 instance
- Confirmed Private subnet isolation

---

## 📸 Screenshots

### VPC Setup
![VPC](https://github.com/khusrawamiri1/aws-vpc-project/blob/784fb36720e7b703ac928d7791b45e3d4b5199e0/screenshots/VPC.jpeg)

## 🌐 Network Components

### 🟢 Public Subnet
![Public Subnet](https://github.com/khusrawamiri1/aws-vpc-project/blob/fc9efe888f3376878c7d36b9febedf89b77c2375/screenshots/Public%20Subnet.jpeg)

### 🔒 Private Subnet
![Private Subnet](https://github.com/khusrawamiri1/aws-vpc-project/blob/41f980a818ecd38f39eaa1479940354ae6e55c38/screenshots/Private%20Subnet.jpeg)

### 🌍 Internet Gateway
Provides internet access for resources in the public subnet.

![Internet Gateway](https://github.com/khusrawamiri1/aws-vpc-project/blob/70c7f1dfa8c5c22884962d45826291ac475fb825/screenshots/internet-gateway.jpeg)

### 🚪 NAT Gateway
Allows private subnet instances to access the internet securely without being directly exposed.

![NAT Gateway](https://github.com/khusrawamiri1/aws-vpc-project/blob/5541ba94648dbb063a07d022e884a367d4b20525/screenshots/Nat%20Gateway.jpeg)


### EC2 Instances
![EC2])

---

## 🎯 Key Skills Demonstrated

- AWS VPC design and implementation
- Public vs Private subnet architecture
- Route table configuration and traffic routing
- Internet Gateway usage
- Basic cloud security principles
- EC2 deployment in custom network

---

## 🚀 Project Outcome
Successfully built a functional and secure cloud networking environment that simulates a production-grade AWS architecture.

---

## 👨‍💻 Author
Khusraw Amiri  
Aspiring Cloud & Network Engineer
