
# ☁️ AWS S3 Scenario-Based Questions & Answers

## Scenario 1: Long-Term Log Storage

**Requirement:**
Application logs must be:

* Rarely accessed
* Required for compliance
* Stored for many years

👉 **Which S3 storage class will you choose and why?**

### ✅ Answer

**Use:** **S3 Glacier Deep Archive**

### 🎯 Why?

* Lowest storage cost
* Designed for long-term archival
* Ideal for compliance & audit data
* Retrieval time acceptable (hours)


---

## Scenario 2: File Accidentally Deleted

A user accidentally deleted an important file from S3.

👉 **How can you recover the file?**

### ✅ Answer

Enable **S3 Versioning**

### 🔄 Recovery Steps

1. Open S3 bucket
2. Enable **Show versions**
3. Locate previous version
4. Restore or download it

### 🛡 Additional Protection

* Enable **MFA Delete**
* Use **Cross-Region Replication**
* Enable **Object Lock** for compliance

---

## Scenario 3: Restrict Public Access but Allow EC2 Access

You want to:

* Block public access
* Allow access only from EC2 instances

👉 **How will you configure permissions?**

### ✅ Answer

Use **IAM Roles + Bucket Policy + Block Public Access**

### ✔ Steps

#### 1️⃣ Block Public Access

* Enable **Block all public access** in bucket settings

#### 2️⃣ Create IAM Role for EC2

* Trusted entity: EC2
* Permissions:

  * `s3:GetObject`
  * `s3:PutObject` (if needed)

#### 3️⃣ Attach Role to EC2 Instance

#### 4️⃣ (Optional) Bucket Policy Restricting Access

Example bucket policy allowing only the IAM role:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::ACCOUNT-ID:role/EC2-S3-Access-Role"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

### 🎯 Result

* Public access blocked
* Only EC2 instances with the role can access the bucket

---

## Scenario 4: Global High Traffic for Images

Your S3 bucket serves images to users worldwide.

👉 **How can you improve performance?**

### ✅ Answer

Use **Amazon CloudFront (CDN)**

### ✔ How It Helps

* Caches images at edge locations worldwide
* Reduces latency
* Reduces load on S3
* Improves user experience

### ✔ Setup Flow

1. Create CloudFront distribution
2. Set S3 bucket as origin
3. Enable caching
4. Serve images via CloudFront URL

---


