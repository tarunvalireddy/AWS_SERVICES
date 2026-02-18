# S4 – AWS CloudFront (Content Delivery Network)

## 1. What problem does this service solve?

When users access applications or websites from different locations:

* Content loads slowly for distant users
* High latency affects user experience
* Origin servers get overloaded
* Performance varies by geography

This caused:

* Slow website loading
* Poor global user experience
* Increased load on backend servers

**Amazon CloudFront**

Solves the problem of:

👉 **Low latency content delivery**
👉 **Global performance improvement**
👉 **Reduced load on origin servers**

---

## 2. Why do companies use CloudFront?

Companies use CloudFront to:

* Deliver content faster globally
* Improve website and application performance
* Cache static and dynamic content
* Protect applications from attacks
* Reduce bandwidth cost on origin servers

👉 CloudFront acts as a **global accelerator for content delivery**.

---

## 3. Core CloudFront Components

![Image](https://labresources.whizlabs.com/1b04ccccd92a080ad0ed3fa9a8add0cc/10021-2.png)

### 3.1 Distributions

A distribution is a **CloudFront configuration**.

Types of distributions:

* Web distribution – websites, APIs
* RTMP (legacy)

Key points:

* Each distribution has a unique domain name
* Controls caching and delivery behavior

---

### 3.2 Edge Locations

Edge locations are **AWS data centers** close to users.

* Content is cached here
* Requests are served from nearest location
* Reduces latency

👉 More edge locations = faster content delivery.

---

### 3.3 Origins

The origin is the **source of content**.

Common origins:

* S3 bucket
* EC2 instance
* Application Load Balancer
* Custom origin (on-premises server)

---

### 3.4 Cache Behavior

Cache behavior defines **how content is cached**.

Controls:

* TTL (Time To Live)
* HTTP methods allowed
* Query string handling
* Cookies forwarding

👉 Proper caching improves performance and reduces cost.

---

### 3.5 Security Features

CloudFront supports:

* HTTPS
* Signed URLs & Signed Cookies
* Integration with AWS WAF
* Origin access control (OAC)

👉 CloudFront helps **secure content delivery**.

---

## 4. Basic CloudFront Architecture

```id="6yq2oz"
User → Nearest Edge Location
     → (Cache Hit) Content Served
     → (Cache Miss) Origin (S3 / EC2 / ALB)
```

* Users connect to nearest edge location
* Cached content served instantly
* Origin accessed only when needed

---

## 5. Important CloudFront Concepts to Remember

* CloudFront is a **global service**
* Uses **edge locations**
* Improves performance and security
* Works with S3, EC2, ALB
* Reduces origin server load
* Supports HTTPS by default

---


## 6. Hands-on Practice – Scenario Based

### Scenario 1

Your website is hosted in one AWS region,
but users from other continents experience slow loading.

👉 How can CloudFront help?

---

### Scenario 2

You want only CloudFront to access your S3 bucket,
not direct public access.

👉 How will you configure this?

---

### Scenario 3

Your images rarely change, but users access them frequently.

👉 How can caching improve performance and reduce cost?

---

### Scenario 4

You want to block malicious traffic from specific countries.

👉 Which CloudFront feature can help?

---

## 7. Interview-Questions

1. What is CloudFront?
2. What are edge locations?
3. Difference between origin and edge location?
4. Is CloudFront global or regional?
5. How does CloudFront improve performance?

---
