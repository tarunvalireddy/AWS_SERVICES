
# S5 – AWS VPC (Virtual Private Cloud)

## 1. What problem does this service solve?

Before virtual networking in cloud, companies had to:

* Use shared public networks
* Expose servers directly to the internet
* Have limited control over traffic flow
* Rely heavily on on-premise firewalls

This caused:

* Security risks
* Poor network isolation
* Complex infrastructure management
* Limited control over inbound and outbound traffic

**Amazon Virtual Private Cloud**

Solves the problem of:

👉 **Network isolation**
👉 **Secure cloud networking**
👉 **Full control over traffic flow**

---

## 2. Why do companies use VPC?

Companies use VPC to:

* Create private networks in AWS
* Control inbound and outbound traffic
* Secure applications and databases
* Separate public and private resources
* Design production-ready architectures

👉 VPC is the **networking foundation of AWS**.

---

## 3. Core VPC Components


![Image](https://docs.aws.amazon.com/images/vpc/latest/userguide/images/vpc-example-private-subnets.png)


### 3.1 VPC

A VPC is a **logically isolated virtual network** in AWS.

Key points:

* Defined using a CIDR block (IP range)
* Exists within a region
* All AWS resources run inside a VPC

Example CIDR:

* `10.0.0.0/16`

---

### 3.2 Subnets

Subnets divide a VPC into smaller networks.

Types:

* Public Subnet
* Private Subnet

Key points:

* Subnets are **AZ-specific**
* Resources are launched inside subnets

👉 Subnets help organize and secure resources.

---

### 3.3 Internet Gateway (IGW)

An Internet Gateway allows **internet access**.

* Enables inbound & outbound internet traffic
* Attached at VPC level
* Required for public subnets

👉 Without IGW, no internet access is possible.

---

### 3.4 NAT Gateway

A NAT Gateway allows **private resources to access the internet**.

Key points:

* Used by private subnets
* Allows outbound internet only
* Prevents inbound access

👉 Keeps private servers secure.

---

### 3.5 Route Tables

Route tables define **how traffic is routed**.

* Associated with subnets
* Contains routes (destination → target)

Example:

* `0.0.0.0/0 → Internet Gateway`

👉 Route tables control traffic direction.

---

### 3.6 Security Groups

Security Groups act as **instance-level firewalls**.

* Allow rules only
* Stateful
* Applied to EC2 instances

Example:

* Allow HTTP (80)
* Allow HTTPS (443)

---

### 3.7 Network ACLs (NACLs)

NACLs act as **subnet-level firewalls**.

* Allow and deny rules
* Stateless
* Applied at subnet level

👉 Used for an extra security layer.

---

## 4. Basic VPC Architecture

```
User → Internet Gateway
     → Public Subnet (EC2 / ALB)
     → Private Subnet (EC2 / RDS)
     → NAT Gateway
```

* Public resources access the internet directly
* Private resources stay isolated
* Route tables control traffic
* Security Groups & NACLs enforce rules

---

## 5. Important VPC Concepts to Remember

* VPC is a **regional service**
* Subnets are **AZ-specific**
* IGW enables internet access
* NAT Gateway enables outbound internet
* Security Groups are **stateful**
* NACLs are **stateless**

---


## 6. Hands-on Practice – Scenario Based

### Scenario 1

You launched an EC2 instance in a private subnet.
It cannot access the internet.

👉 What component is missing?

---

### Scenario 2

You want users to access your web server from the internet.

👉 Which VPC components are required?

---

### Scenario 3

You want an extra layer of security at subnet level.

👉 Which VPC feature will you use and why?

---

### Scenario 4

Your database should never be accessible from the internet.

👉 How will you design the VPC architecture?

---

## 7. Interview-Questions

1. What is a VPC?
2. Difference between public and private subnet?
3. What is the role of an Internet Gateway?
4. Difference between Security Group and NACL?
5. Is VPC global or regional?

---

