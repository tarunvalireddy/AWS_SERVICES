

# 🌍 AWS CloudFront Scenario-Based Questions & Answers

## Scenario 1: Slow Website for Global Users

Your website is hosted in one AWS region, but users from other continents experience slow loading.

👉 **How can CloudFront help?**

### ✅ Answer

Use **Amazon CloudFront (Content Delivery Network)**

### 🎯 How it helps

* Caches content at **edge locations** worldwide
* Serves users from the nearest location
* Reduces latency and load time
* Reduces traffic to origin server


---

## Scenario 2: Allow Only CloudFront to Access S3

You want:

* No direct public access to S3
* Only CloudFront should fetch content

👉 **How will you configure this?**

### ✅ Answer

Use **Origin Access Control (OAC)** *(recommended)*

### ✔ Steps

1. Keep S3 bucket **private**
2. Create CloudFront distribution
3. Configure **Origin Access Control (OAC)**
4. Update bucket policy to allow only CloudFront

### ✔ Example Bucket Policy

```json id="blv82p"
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "cloudfront.amazonaws.com"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*",
      "Condition": {
        "StringEquals": {
          "AWS:SourceArn": "arn:aws:cloudfront::ACCOUNT-ID:distribution/DISTRIBUTION-ID"
        }
      }
    }
  ]
}
```

---

## Scenario 3: Frequently Accessed Images, Rarely Updated

Your images rarely change, but users access them frequently.

👉 **How can caching improve performance and reduce cost?**

### ✅ Answer

Use **CloudFront caching**

### 🎯 Benefits

✔ Stores copies at edge locations
✔ Reduces requests to S3/origin
✔ Faster delivery to users
✔ Lower data transfer & origin costs

### ✔ Recommended Settings

* Increase **TTL (Time To Live)**
* Use cache headers:

  * `Cache-Control`
  * `Expires`

### ✔ Example

Set long cache duration for static images (e.g., 30 days).

---

## Scenario 4: Block Malicious Traffic from Specific Countries

You want to block malicious traffic from certain countries.

👉 **Which CloudFront feature can help?**

### ✅ Answer

Use **CloudFront Geo Restriction (Geo Blocking)**

### ✔ Options

* **Allow list** → only specific countries allowed
* **Block list** → deny specific countries

### 🎯 Additional Protection

For advanced filtering, combine with:

* AWS WAF (Web Application Firewall)
* Rate limiting rules
* IP reputation filtering

---


