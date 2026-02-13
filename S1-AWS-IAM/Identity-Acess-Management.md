
# S1 – AWS IAM (Identity and Access Management)

## 1. What problem does this service solve?

In AWS, **everything is secured by default**.
Without a proper identity and permission system:

* Anyone could access resources
* There would be no control over *who can do what*
* Security breaches would be very common

**AWS Identity and Access Management** 

Solves the problem of:

👉 **Authentication (who you are)**
👉 **Authorization (what you are allowed to do)**

---

## 2. Why do companies use IAM?

Companies use IAM to:

* Avoid using the **root account**
* Enforce **least privilege**
* Secure production resources
* Track **who did what and when**
* Provide **temporary access** instead of permanent credentials

👉 IAM is the **foundation of AWS security**.

---

## 3. Core IAM Components

![Image](https://docs.aws.amazon.com/images/IAM/latest/UserGuide/images/Relationship_Between_Entities_Example.diagram.png)


### 3.1 IAM Users

An IAM User represents a **person or application**.

* Has a **username**
* Can have:

  * Console access (username + password)
  * Programmatic access (access key & secret key)

⚠️ Best Practice:
Never use the **root user** for daily work.

---

### 3.2 IAM User Groups

An IAM Group is a **collection of users**.

* Permissions are assigned to the group
* Users inherit group permissions
* A user can belong to multiple groups

Example:

* `AdminGroup`
* `DeveloperGroup`
* `ReadOnlyGroup`

👉 Groups **simplify permission management**.

---

### 3.3 IAM Roles

IAM Roles are used to provide **temporary permissions**.

Key points:

* Roles are **not attached to users permanently**
* No username or password
* Used by:

  * EC2 instances
  * Lambda functions
  * AWS services
  * Cross-account access

Example:

* EC2 role to access S3
* Lambda role to write logs to CloudWatch

👉 **Roles are preferred over access keys**.

---

### 3.4 IAM Policies

Policies define **permissions**.

They answer:

> “What actions are allowed or denied on which resources?”

Policies are written in **JSON format**.

Types of policies:

* AWS Managed Policies
* Customer Managed Policies
* Inline Policies (not recommended)

Basic policy elements:

* Version
* Effect (Allow / Deny)
* Action
* Resource

---

## 4. Basic IAM Architecture

```
User → Group → Policy → AWS Resource
User → Role  → Policy → AWS Resource
```

* Users don’t directly access services
* Permissions always flow through **policies**
* Roles provide **temporary credentials**

---


## 5. Important IAM Concepts to Remember

* IAM is a **global service**
* Root user should be used **only once**
* Follow **least privilege**
* Prefer **roles over access keys**
* Use **groups** for easier management
* Enable **MFA** for sensitive users

---


## 6. Hands-on Practice – Scenario Based

### Scenario 1

You have 3 developers who should only:

* View EC2 instances
* Not create or delete anything

👉 What IAM components will you use?

---

### Scenario 2 

An EC2 instance needs to upload logs to an S3 bucket.
You don’t want to store access keys on the server.

👉 How will you grant access securely?

---

### Scenario 3 

A user accidentally deleted an S3 bucket.
You want to **restrict delete access** but allow read/write.

👉 How will you design the IAM policy?

---

### Scenario 4

You need to give temporary AWS access to an external consultant for 1 week.

👉 Will you use IAM User or IAM Role? Why?

---

## 7. Interview-Questions

1. What is the difference between IAM User and IAM Role?
2. Why are IAM Roles more secure than access keys?
3. What is least privilege?
4. Is IAM regional or global?

---





