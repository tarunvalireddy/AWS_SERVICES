# S3 – AWS S3 (Simple Storage Service)

## 1. What problem does this service solve?

Before object storage and cloud storage, companies had to:

* Buy storage servers
* Manage disks and backups
* Worry about hardware failure
* Scale storage manually

This caused:

* Data loss risks
* High maintenance cost
* Limited scalability
* Complex backup processes

**Amazon Simple Storage Service**

Solves the problem of:

👉 **Highly durable storage**
👉 **Unlimited scalability**
👉 **Pay only for stored data**

---

## 2. Why do companies use S3?

Companies use S3 to:

* Store files, images, and videos
* Backup and archive data
* Host static websites
* Store logs and application data
* Integrate with almost all AWS services

👉 S3 is the **most widely used storage service in AWS**.

---

## 3. Core S3 Components

![Image](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2024/09/20/1-Solution-overview-of-transitioning-objects-across-storage-classes-using-S3-Batch-Operations-and-S3-Lifecycle.jpg)

### 3.1 S3 Buckets

A bucket is a **container for objects**.

Key points:

* Buckets must have **globally unique names**
* Created in a specific region
* Acts as the top-level storage

Example bucket name:

* `company-logs-bucket`

---

### 3.2 S3 Objects

Objects are the **actual data** stored in S3.

Each object consists of:

* Data (file)
* Key (object name)
* Metadata

Example objects:

* `image.jpg`
* `backup.zip`
* `logs/2026/app.log`

👉 S3 stores data as **objects**, not files or blocks.

---

### 3.3 S3 Storage Classes

Storage classes define **cost vs access frequency**.

Common classes:

* Standard
* Intelligent-Tiering
* Standard-IA
* Glacier
* Glacier Deep Archive

👉 Choose based on **how often data is accessed**.

---

### 3.4 Versioning

Versioning keeps **multiple versions of an object**.

Benefits:

* Protects against accidental deletion
* Enables object recovery
* Improves data protection

⚠️ Best Practice:
Enable versioning for critical data.

---

### 3.5 S3 Permissions & Access

Access to S3 is controlled using:

* IAM policies
* Bucket policies
* ACLs (not recommended)

👉 S3 is **private by default**.

---

### 3.6 S3 Durability & Availability

S3 provides:

* **99.999999999% durability (11 nines)**
* Automatic data replication across AZs

👉 Designed for **high availability and fault tolerance**.

---

## 4. Basic S3 Architecture

```
User / Application → S3 Bucket
                    → Objects
                    → Storage Class
```

* Buckets store objects
* Objects store data
* Storage class controls cost
* Access controlled by policies

---

## 5. Important S3 Concepts to Remember

* S3 is a **regional service**
* Buckets are **globally unique**
* Data is stored as **objects**
* S3 is **private by default**
* Versioning protects data
* No server management required

---


## 6. Hands-on Practice – Scenario Based

### Scenario 1

You want to store application logs that are:

* Rarely accessed
* Required for compliance
* Stored for many years

👉 Which S3 storage class will you choose and why?

---

### Scenario 2

A user accidentally deleted an important file from S3.

👉 How can you recover the file?

---

### Scenario 3

You want to restrict public access to your S3 bucket
but allow access only from EC2 instances.

👉 How will you configure permissions?

---

### Scenario 4

Your S3 bucket is receiving large traffic for images globally.

👉 How can you improve performance?

---

## 7. Interview-Questions

1. What is an S3 bucket?
2. What is the difference between bucket and object?
3. Is S3 global or regional?
4. What is S3 versioning?
5. Why is S3 highly durable?

---

