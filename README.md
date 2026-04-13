
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


## 💻 EC2 Instances

### 🟢 Public EC2 Instance
This instance is deployed in the public subnet and has internet access via Internet Gateway.

![Public EC2](https://github.com/khusrawamiri1/aws-vpc-project/blob/ba179fb876b2099fe62218c16dc798856ea15afb/screenshots/Public%20EC2.jpeg)

---

### 🔒 Private EC2 Instance
This instance is deployed in the private subnet and does NOT have direct internet access. It can reach the internet through NAT Gateway.

![Private EC2](https://github.com/khusrawamiri1/aws-vpc-project/blob/9540295e50836257cfe03710509188a23f654e00/screenshots/Private%20EC2.jpeg)

## 🔐 Security Groups Configuration

### 🟢 Public Security Group
- Allows SSH (port 22) access from the internet
- Allows HTTP/HTTPS access if required
- Attached to Public EC2 instance

![Public SG](https://github.com/khusrawamiri1/aws-vpc-project/blob/3b81c1afc3b6ff0045be23b9250f8bd60c0156b2/screenshots/Public%20Security%20Group.jpeg)

---

### 🔒 Private Security Group
- Allows SSH access ONLY from Public EC2 (Bastion Host)
- No direct internet access allowed
- Attached to Private EC2 instance

![Private SG](https://github.com/khusrawamiri1/aws-vpc-project/blob/e4c7c2ee404c69fb2d5d3996feda467f18679fbe/screenshots/Private%20Security%20Group.jpeg)

---

### 🔑 SSH Access Flow
- User connects to Public EC2 via SSH (port 22)
- Public EC2 is used to access Private EC2 securely

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
