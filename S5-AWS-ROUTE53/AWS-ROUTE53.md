
# S5 – AWS Route 53 (Domain Name System Service)

## 1. What problem does this service solve?

Before cloud DNS services, companies had to:

* Manually manage DNS servers
* Map domain names to IP addresses themselves
* Handle failover routing manually
* Maintain high availability DNS infrastructure

This caused:

* Website downtime during failures
* Complex DNS management
* Slow domain resolution
* Poor reliability

**Amazon Route 53**

Solves the problem of:

👉 **Reliable domain name resolution**
👉 **Highly available DNS routing**
👉 **Intelligent traffic management**

---

## 2. Why do companies use Route 53?

Companies use Route 53 to:

* Connect domain names to AWS resources
* Route traffic to websites and applications
* Improve availability with failover routing
* Route users to nearest servers for better performance
* Manage domains and DNS records

👉 Route 53 acts as the **internet’s phonebook for your applications**.

---

## 3. Core Route 53 Components

![Image](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2022/09/20/fig1.jpg)

### 3.1 Domain Name

A domain name is the human-readable website name.

Examples:

* `example.com`
* `myapp.in`

👉 Route 53 connects domain names to AWS resources.

---

### 3.2 Hosted Zones

A hosted zone stores DNS records for a domain.

Types:

* Public Hosted Zone → internet-facing domains
* Private Hosted Zone → internal VPC domains

Example:

Domain: `example.com`
Records stored inside hosted zone.

---

### 3.3 DNS Records

DNS records map domain names to resources.

Common record types:

* A → maps to IPv4 address
* AAAA → maps to IPv6 address
* CNAME → maps to another domain
* MX → mail servers
* Alias → maps to AWS resources

👉 Alias records are commonly used with AWS services.

---

### 3.4 Alias Records

Alias records map domains directly to AWS resources such as:

* CloudFront distributions
* Load Balancers
* S3 static websites
* API Gateway

👉 Alias records are **free and AWS-optimized**.

---

### 3.5 Routing Policies

Routing policies control how traffic is directed.

Common policies:

* Simple Routing
* Weighted Routing
* Failover Routing
* Latency-based Routing
* Geolocation Routing

👉 Routing policies improve performance and availability.

---

### 3.6 Health Checks & Failover

Route 53 can monitor resource health.

If a resource fails:

* Traffic is redirected to a healthy endpoint
* Improvers application reliability

👉 Helps build **fault-tolerant architectures**.

---

## 4. Basic Route 53 Architecture

```
User → Route 53 DNS
     → Domain Name
     → AWS Resource (CloudFront / ELB / EC2 / S3)
```

* User enters domain name
* Route 53 resolves the DNS
* Traffic is routed to the correct resource

---

## 5. Important Route 53 Concepts to Remember

* Route 53 is a **global service**
* Hosted zones store DNS records
* Alias records connect domains to AWS services
* Routing policies control traffic flow
* Health checks enable failover routing

---

## 6. Hands-on Practice – Scenario Based

### Scenario 1

You want users to access your website using:

`www.mywebsite.com`

instead of an IP address.

👉 Which Route 53 component will you configure?

---

### Scenario 2

Your primary server fails and you want traffic to move automatically to a backup server.

👉 Which routing policy should you use?

---

### Scenario 3

You want users in India to connect to a server in Mumbai,
and users in the US to connect to a server in Virginia.

👉 Which routing policy is suitable?

---

### Scenario 4

You want to connect your domain to a CloudFront distribution.

👉 Which record type should you use?

---

## 7. Interview-Questions

1. What is Route 53?
2. What is a hosted zone?
3. Difference between CNAME and Alias record?
4. What is latency-based routing?
5. Is Route 53 global or regional?

---


