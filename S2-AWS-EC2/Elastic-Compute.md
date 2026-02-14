
# S2 – AWS EC2 (Elastic Compute Cloud)

## 1. What problem does this service solve?

Before cloud computing, companies had to:

* Buy physical servers
* Maintain data centers
* Predict capacity in advance
* Spend high upfront costs

This caused:

* Wasted resources
* Scaling issues
* Long provisioning time

**Amazon Elastic Compute Cloud**

Solves the problem of:

👉 **On-demand compute**
👉 **Scalable virtual servers**
👉 **Pay only for what you use**

---

## 2. Why do companies use EC2?

Companies use EC2 to:

* Launch servers in minutes
* Scale applications up or down
* Run applications without owning hardware
* Choose OS, CPU, RAM, and storage
* Pay per second/minute usage

👉 EC2 is the **backbone of AWS compute services**.

---

## 3. Core EC2 Components

![Image](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/instance_lifecycle.png)


### 3.1 EC2 Instances

An EC2 instance is a **virtual server** in the cloud.

Key points:

* Runs on AWS infrastructure
* Can host applications, websites, databases
* Fully customizable

Instance states:

* Running
* Stopped
* Terminated

---

### 3.2 Amazon Machine Image (AMI)

An AMI is a **template** used to launch EC2 instances.

Includes:

* Operating system
* Preinstalled software
* Configuration settings

Types of AMIs:

* AWS provided
* Marketplace
* Custom AMIs

👉 AMI ensures **consistent server creation**.

---

### 3.3 Instance Types

Instance types define **hardware configuration**.

They specify:

* vCPU
* Memory
* Network performance

Examples:

* `t3.micro` – small workloads
* `m5` – general purpose
* `c5` – compute optimized

👉 Choose instance type based on workload.

---

### 3.4 Key Pairs

Key pairs are used for **secure login**.

* Public key → stored in AWS
* Private key → stored by user
* Used mainly for SSH access

⚠️ Best Practice:
Never share or lose your private key.

---

### 3.5 Security Groups

Security Groups act as a **virtual firewall**.

* Control inbound traffic
* Control outbound traffic
* Works at instance level

Examples:

* Allow SSH (22)
* Allow HTTP (80)
* Allow HTTPS (443)

👉 Security Groups are **stateful**.

---

### 3.6 Elastic Block Store (EBS)

EBS provides **block storage** for EC2.

Key points:

* Attached to EC2 instances
* Persists even after instance stop
* Used as root volume

👉 EBS stores your **server data**.

---

## 4. Basic EC2 Architecture

```
User → EC2 Instance
        → Security Group
        → EBS Volume
        → AMI
```

* EC2 provides compute
* Security Groups control traffic
* EBS stores data
* AMI defines the server image

---

## 5. Important EC2 Concepts to Remember

* EC2 is a **regional service**
* Instances run inside a **VPC**
* Data is stored on **EBS**
* Security Groups control access
* Stop ≠ Terminate
* Instance type impacts cost & performance

---


## 6. Hands-on Practice – Scenario Based

### Scenario 1

You want to launch a small test server that should:

* Be low cost
* Run Linux
* Be accessible via SSH

👉 Which EC2 instance type will you choose and why?

---

### Scenario 2

Your EC2 instance was stopped and started again.
The public IP address changed.

👉 Why did this happen? How can you fix it?

---

### Scenario 3

You accidentally terminated an EC2 instance.
The data is lost.

👉 How could this have been prevented?

---

### Scenario 4

You want only HTTP and HTTPS traffic to reach your EC2 instance.

👉 Which EC2 component controls this?

---

## 7. Interview-Questions

1. What is an EC2 instance?
2. What is the purpose of an AMI?
3. Difference between stop and terminate?
4. What is a Security Group?
5. Is EC2 global or regional?

---



