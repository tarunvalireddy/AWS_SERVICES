
# S6 – AWS ELB (Elastic Load Balancing)

## 1. What problem does this service solve?

When applications run on a single server:

* If the server fails, the application goes down
* Traffic spikes can crash the server
* Users experience slow response times
* High availability is hard to achieve

This caused:

* Single point of failure
* Poor user experience
* Downtime during traffic peaks

**Elastic Load Balancing**

Solves the problem of:

?? **Distributing traffic across multiple servers**
?? **High availability**
?? **Improved fault tolerance**

---

## 2. Why do companies use ELB?

Companies use ELB to:

* Handle increasing user traffic
* Improve application availability
* Automatically route traffic to healthy servers
* Integrate with Auto Scaling
* Reduce manual traffic management

?? ELB is a **core component for scalable architectures**.

---

## 3. Core ELB Components


![Image](https://d33wubrfki0l68.cloudfront.net/872ee6df901ead26b5b4ff099babaf7ef43c0478/fe21d/images/aws/ec2/1-simple-elb.png)



### 3.1 Load Balancer

A load balancer is a **single entry point** for your application.

Key points:

* Receives traffic from users
* Distributes traffic to backend targets
* Improves fault tolerance

Types of load balancers:

* Application Load Balancer (ALB)
* Network Load Balancer (NLB)
* Classic Load Balancer (legacy)

---

### 3.2 Target Groups

Target groups define **where traffic is sent**.

Targets can be:

* EC2 instances
* IP addresses
* Lambda functions

?? Load balancers route traffic to target groups.

---

### 3.3 Health Checks

Health checks monitor **backend target health**.

* Periodically checks target status
* Unhealthy targets stop receiving traffic
* Ensures high availability

Example:

* HTTP health check on `/health`

---

### 3.4 Application Load Balancer (ALB)

ALB works at **Layer 7 (HTTP/HTTPS)**.

Features:

* Path-based routing
* Host-based routing
* Works well for web applications

Example:

* `/api ? backend1`
* `/images ? backend2`

---

### 3.5 Network Load Balancer (NLB)

NLB works at **Layer 4 (TCP/UDP)**.

Features:

* Handles millions of requests per second
* Ultra-low latency
* Used for performance-critical workloads

---

### 3.6 Security Integration

ELB integrates with:

* Security Groups
* AWS Certificate Manager (HTTPS)
* AWS WAF (with ALB)

?? Enhances both **security and scalability**.

---

## 4. Basic ELB Architecture

```
User ? Load Balancer
     ? Target Group
     ? EC2 Instances
```

* Users access one endpoint
* ELB distributes traffic
* Only healthy instances receive requests

---

## 5. Important ELB Concepts to Remember

* ELB is a **regional service**
* Provides high availability
* Works across multiple AZs
* Health checks are mandatory
* Integrates with Auto Scaling
* Supports HTTPS termination

---


## 6. Hands-on Practice – Scenario Based

### Scenario 1

Your application runs on two EC2 instances.
One instance goes down.

?? How does ELB handle this situation?

---

### Scenario 2

You want to route traffic based on URL paths.

?? Which type of load balancer will you use?

---

### Scenario 3

Your application needs very low latency and handles millions of requests.

?? Which ELB type is suitable?

---

### Scenario 4

You want to enable HTTPS for your application.

?? Which AWS services will you integrate with ELB?

---

## 7. Interview-Questions

1. What is Elastic Load Balancing?
2. Difference between ALB and NLB?
3. What is a target group?
4. Why are health checks important?
5. Is ELB global or regional?

---


