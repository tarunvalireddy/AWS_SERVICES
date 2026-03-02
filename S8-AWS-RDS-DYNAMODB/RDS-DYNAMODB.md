
# S7 – AWS RDS & DynamoDB (Managed Databases)

## 1. What problem does this service solve?

Before managed databases, companies had to:

* Install databases manually
* Handle backups and patching
* Manage scaling and failover
* Worry about database availability

This caused:

* High operational overhead
* Risk of data loss
* Downtime during failures
* Complex database management

**Amazon Relational Database Service**
**Amazon DynamoDB**

Solve the problem of:

?? **Fully managed databases**
?? **High availability**
?? **Scalable data storage**

---

## 2. Why do companies use RDS and DynamoDB?

Companies use these services to:

* Focus on application logic, not database management
* Get automated backups and patching
* Achieve high availability
* Scale databases easily
* Reduce operational complexity

?? AWS manages the **database infrastructure**, you manage the **data**.

---

## 3. Core Database Components


![Image](https://docs.aws.amazon.com/images/AmazonRDS/latest/UserGuide/images/aws-cloud-deployment-architecture.png)
![Image](https://media.geeksforgeeks.org/wp-content/uploads/20231026153053/serverless-authrntication_2-768.jpg)
### 3.1 Amazon RDS

RDS is a **managed relational database service**.

Supported engines:

* MySQL
* PostgreSQL
* MariaDB
* Oracle
* SQL Server

Key points:

* Uses tables, rows, and columns
* Supports SQL queries
* Best for structured data

---

### 3.2 RDS Multi-AZ

Multi-AZ provides **high availability**.

* Primary database in one AZ
* Standby replica in another AZ
* Automatic failover

?? Used for **production workloads**.

---

### 3.3 RDS Backups & Snapshots

RDS provides:

* Automated backups
* Manual snapshots
* Point-in-time recovery

?? Protects against data loss.

---

### 3.4 Amazon DynamoDB

DynamoDB is a **serverless NoSQL database**.

Key points:

* Key-value and document-based
* No server management
* Single-digit millisecond latency
* Automatically scales

?? Ideal for high-scale applications.

---

### 3.5 DynamoDB Tables

A DynamoDB table consists of:

* Items (rows)
* Attributes (columns)
* Primary key:

  * Partition key
  * Partition + Sort key

?? Data access depends on primary key design.

---

### 3.6 Consistency & Performance

DynamoDB supports:

* Strongly consistent reads
* Eventually consistent reads
* On-demand or provisioned capacity

?? Performance is predictable and scalable.

---

## 4. Basic Database Architecture

```
Application ? RDS (SQL Database)
Application ? DynamoDB (NoSQL Database)
```

* RDS for relational workloads
* DynamoDB for serverless, high-scale workloads
* Both integrate with VPC and IAM

---

## 5. Important Database Concepts to Remember

* RDS is a **regional service**
* DynamoDB is **serverless**
* RDS supports SQL
* DynamoDB does not support SQL
* RDS requires capacity planning
* DynamoDB scales automatically

---

## 6. Real-World Example

A company runs an e-commerce application.

Implementation:

* User data ? RDS (MySQL)
* Product catalog ? DynamoDB
* Orders ? RDS
* Session data ? DynamoDB

---

## 7. Hands-on Practice – Scenario Based

### Scenario 1

You need a database that:

* Uses SQL
* Supports joins
* Stores structured data

?? Which AWS database will you choose and why?

---

### Scenario 2

Your application handles millions of requests per second
with unpredictable traffic.

?? Which database fits best?

---

### Scenario 3

Your production database must survive AZ failure.

?? Which RDS feature will you enable?

---

### Scenario 4

You want zero server management and automatic scaling.

?? Will you choose RDS or DynamoDB? Why?

---

## 8. Interview-Questions

1. What is the difference between RDS and DynamoDB?
2. What is RDS Multi-AZ?
3. Is DynamoDB serverless?
4. Does DynamoDB support SQL?
5. Is RDS global or regional?

---





