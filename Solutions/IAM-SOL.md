
# 🔐 AWS IAM Scenario-Based Questions & Answers

## Q1. Limited EC2 Access for Developers

**Scenario:**
You have 3 developers who should only:

* View EC2 instances
* NOT create or delete anything

👉 **What IAM components will you use?**

### Answer

Use **IAM Users + IAM User Group + Permission Policy**

### ✔ Steps:

1. Create an IAM **User Group** (e.g., `EC2-ReadOnly-Developers`).
2. Attach a policy:

   * Use AWS managed policy: `AmazonEC2ReadOnlyAccess`
   * OR create a custom policy allowing only read actions.
3. Create IAM Users for each developer.
4. Add users to the group.

###  Important Note

You **must create IAM users first**, then add them to the group.
Groups cannot contain users that don’t exist.

###  Why use Groups?

* Centralized permission management
* Easy to add/remove users
* Scalable and secure

---

## Q2. EC2 Instance Uploading Logs to S3 (Without Access Keys)

**Scenario:**
An EC2 instance needs to upload logs to an S3 bucket.
You don’t want to store access keys on the server.

👉 **How will you grant access securely?**

### Answer

Use an **IAM Role for EC2**

### ✔ Steps:

1. Create an IAM Role with:

   * Trusted entity: **EC2**
2. Attach permissions:

   * Minimum required:

     * `s3:PutObject`
     * `s3:GetObject` *(optional)*
   * OR use managed policy like `AmazonS3FullAccess` (not recommended for production).
3. Launch EC2 instance with the role attached
   OR attach role via **Modify IAM Role** option.

###  Why this is secure?

* No access keys stored
* Temporary credentials via STS
* Automatic credential rotation

---

## Q3. Prevent S3 Bucket Deletion but Allow Read/Write

**Scenario:**
A user accidentally deleted an S3 bucket.
You want to allow read & write but prevent deletions.

👉 **How will you design the IAM policy?**

###  Answer

Use **Allow permissions + Explicit Deny for delete actions**

### ✔ Policy Example

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowReadWrite",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::your-bucket-name",
        "arn:aws:s3:::your-bucket-name/*"
      ]
    },
    {
      "Sid": "DenyDeleteActions",
      "Effect": "Deny",
      "Action": [
        "s3:DeleteBucket",
        "s3:DeleteObject",
        "s3:DeleteObjectVersion"
      ],
      "Resource": [
        "arn:aws:s3:::your-bucket-name",
        "arn:aws:s3:::your-bucket-name/*"
      ]
    }
  ]
}
```

###  Why Explicit Deny?

In AWS IAM:

> **Explicit Deny always overrides Allow**

###  Where to Attach?

* IAM User Policy
* IAM Group Policy
* Bucket Policy (recommended for stronger protection)

---

## Q4. Temporary Access for External Consultant (1 Week)

**Scenario:**
You need to give temporary AWS access to an external consultant for 1 week.

👉 **Will you use IAM User or IAM Role? Why?**

###  Answer

Use an **IAM Role**

###  Why IAM Role is Better

✔ Temporary credentials that expire
✔ No permanent passwords or keys
✔ Easy revocation
✔ More secure & auditable

---

### ✔ Implementation Overview

#### 1️⃣ Create IAM Role

* Define **permissions policy** (what they can do)
* Define **trust policy** (who can assume role)

---

### 🔐 Trust Policy Example

Allows external AWS account to assume the role.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::123456789012:root"
      },
      "Action": "sts:AssumeRole",
      "Condition": {
        "StringEquals": {
          "sts:ExternalId": "ConsultantSecret123"
        },
        "DateLessThan": {
          "aws:CurrentTime": "2026-02-26T00:00:00Z"
        }
      }
    }
  ]
}
```

---

### 🔒 Security Enhancements

* Use **External ID** to prevent confused deputy attacks
* Set time-based access restrictions
* Delete role after contract ends

---

## ✅ Key IAM Concepts Covered

✔ IAM Users
✔ IAM Groups
✔ IAM Roles
✔ Policies & Permissions
✔ Explicit Deny
✔ Temporary Credentials (STS)
✔ Trust Relationships

---


