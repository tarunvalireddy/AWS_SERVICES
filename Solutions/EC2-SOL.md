
# 🖥️ AWS EC2 Scenario-Based Questions & Answers

## Q1. Launch a Low-Cost Test Server

**Scenario:**
You want to launch a small test server that should:

* Be low cost
* Run Linux
* Be accessible via SSH

👉 **Which EC2 instance type will you choose and why?**

### ✅ Answer

**Instance Type:** `t2.nano` *(or t2.micro if nano not available)*
**AMI:** Amazon Linux

### ✔ Configuration

* Choose **Amazon Linux AMI**
* Select **t2.nano** (very low cost, suitable for testing)
* Configure Security Group:

  * Inbound Rule → **SSH (Port 22)**

### 🎯 Why?

* Burstable instance → cost efficient
* Enough for testing & learning
* SSH access allows remote administration

---

## Q2. Public IP Changed After Restart

**Scenario:**
Your EC2 instance was stopped and started again.
The public IP address changed.

👉 **Why did this happen? How can you fix it?**

### ✅ Answer

### 🔍 Why it happened

* Default public IPs are **dynamic**
* AWS releases the IP when the instance stops
* A new IP is assigned when it starts

### ✔ Fix

Use an **Elastic IP**

### ✔ Steps:

1. Allocate Elastic IP
2. Associate it with the EC2 instance

### 🎯 Result

Your public IP remains **permanent**.

---

## Q3. EC2 Instance Terminated — Data Lost

**Scenario:**
You accidentally terminated an EC2 instance and lost data.

👉 **How could this have been prevented?**

### ✅ Answer

Enable **Termination Protection**

### ✔ Steps:

1. Select EC2 instance
2. Actions → Instance Settings
3. Enable **Termination Protection**

### 🔒 Additional Best Practices

* Store data on **EBS volumes**
* Enable **EBS snapshots**
* Use **AMI backups**

---

## Q4. Allow Only HTTP & HTTPS Traffic

**Scenario:**
You want only web traffic to reach your EC2 instance.

👉 **Which EC2 component controls this?**

### ✅ Answer

**Security Groups**

### ✔ Inbound Rules:

| Protocol | Port | Purpose                |
| -------- | ---- | ---------------------- |
| HTTP     | 80   | Website traffic        |
| HTTPS    | 443  | Secure website traffic |

### ✔ Configuration

* Add inbound rule → HTTP → Port 80
* Add inbound rule → HTTPS → Port 443

### 🎯 Result

Only web traffic is allowed. All other traffic is blocked.

---


