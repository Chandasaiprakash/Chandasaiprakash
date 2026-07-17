# Hi there 👋, I'm Chanda Sai Prakash

## 🚀 Backend Developer | Microservices Architect | Cloud & DevOps Enthusiast

Welcome to my GitHub! I'm passionate about building scalable microservices, cloud-native applications, and distributed systems. Specialized in Java, Spring Boot, Kubernetes, and AWS.

---

## 💼 About Me

- 🎯 **Expertise:** Java, Spring Boot, Microservices Architecture & Design Patterns
- ☁️ **Cloud & DevOps:** AWS, Kubernetes, Docker, CI/CD pipelines
- 📊 **Observability:** ELK Stack, Prometheus, Jaeger for monitoring & tracing
- 💾 **Databases:** SQL (PostgreSQL, MySQL), MongoDB, NoSQL design
- 🌱 **Passionate about:** Building resilient, scalable, and maintainable systems
- 🤝 **Open to:** Collaborations, open-source contributions, and challenging projects

---

## 🛠️ Core Tech Stack

### 🔴 Backend & Frameworks
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![Microservices](https://img.shields.io/badge/Microservices-FF6B6B?style=for-the-badge&logo=microservices&logoColor=white)

### 📦 Databases
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=database&logoColor=white)

### ☁️ Cloud & Container Orchestration
![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![EC2](https://img.shields.io/badge/AWS%20EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)

### 📊 Observability & Monitoring
![ELK Stack](https://img.shields.io/badge/ELK%20Stack-005571?style=for-the-badge&logo=elastic&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Jaeger](https://img.shields.io/badge/Jaeger-00B4CC?style=for-the-badge&logo=jaeger&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F2F4F9?style=for-the-badge&logo=grafana&logoColor=orange)

### 🛠️ DevOps & Tools
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

### 📡 Additional Skills
![REST APIs](https://img.shields.io/badge/REST%20APIs-0066CC?style=for-the-badge&logo=api&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=for-the-badge&logo=apache-kafka&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

---

## 🎯 Featured Projects

### 1️⃣ ⚡ SwiftPay — Real-Time Event-Driven Payment Ledger

**Repository:** [github.com/Chandasaiprakash/swiftpay](https://github.com/Chandasaiprakash/swiftpay)

A **production-grade, distributed fintech platform** for peer-to-peer payment processing built with Java 21, Spring Boot 3, Apache Kafka, PostgreSQL, and Redis.

#### 🏆 Key Highlights:
- **Real-time Transaction Processing:** Handles peer-to-peer payments asynchronously with 100% transactional consistency
- **Dual-Layer Idempotency:** 
  - Redis-backed API deduplication (24h TTL) for duplicate request prevention
  - DB-backed consumer idempotency for Kafka redelivery safety
- **Event-Driven Resilience:** Apache Kafka-based async processing with Dead Letter Queue (DLQ) and intelligent retry handling
- **High Throughput:** Load-tested and validated at **250 TPS across 1 million transactions**
- **Pessimistic Locking:** Deadlock-free concurrent account updates using ordered `SELECT FOR UPDATE`

#### 🔄 Architecture:
- **Transaction Gateway (Port 8080):** REST API ingestion, Redis idempotency checks, outbox publishing
- **Ledger Service (Port 8081):** Kafka consumer, atomic balance mutations, event publishing
- **Analytics Worker (Port 8082):** Real-time payment analytics aggregation
- **Outbox Pattern:** Guaranteed event publishing with scheduler-based Kafka publishing

#### 📊 Observability Stack:
- **Prometheus:** Custom Micrometer metrics for payments (initiated, completed, failed, duplicates)
- **Jaeger:** Distributed tracing across services
- **ELK Stack:** Centralized logging and monitoring
- **Spring Boot Actuator:** Health checks, metrics endpoints

#### 🛡️ Failure Handling:
- **Insufficient Funds:** Routes to `payments.failed` (no retry)
- **Kafka Outage:** Outbox events remain in PostgreSQL, published on recovery
- **Service Crashes:** Kafka redelivery + DB idempotency prevents double-processing
- **Infrastructure Failures:** 3-retry mechanism with 2-second intervals → DLQ

#### 🚀 Deployment:
- **Docker Compose:** Full local development with Kafka UI, Redis, PostgreSQL
- **Kubernetes:** Multi-replica deployments on Docker Desktop Kubernetes
- **CI/CD:** GitHub Actions matrix strategy for all three services

#### 📈 Performance Results:
- **p95 Latency:** 109.99ms
- **Throughput:** Stable 250 TPS
- **Error Rate:** 0.00%
- **Success Rate:** 99.9%

#### 🔧 Tech Stack:
`Java 21` • `Spring Boot 3.5` • `Apache Kafka 7.6.1` • `PostgreSQL 16` • `Redis 7` • `Docker` • `Kubernetes` • `Prometheus` • `Jaeger` • `GitHub Actions`

---

### 2️⃣ 🍔 FOODIE — Cloud-Native Distributed Food Ordering Platform

**Repository:** [github.com/Chandasaiprakash/Foodie](https://github.com/Chandasaiprakash/Foodie)

A **production-grade microservices system** demonstrating **Event-Driven Architecture**, **Infrastructure as Code**, and **High-Availability** patterns on AWS with Kubernetes orchestration.

#### 🏆 Key Highlights:
- **Saga Pattern (Orchestration):** Distributed transactions across Order, Payment, Inventory, Delivery services
- **Bounded Contexts:** Clean domain isolation with independent deployment
- **Event-Driven Workflow:**
  - Order Created → Payment Processing → Delivery Allocation
  - Compensation mechanism for automatic rollback on failures
- **Polyglot Persistence:** MySQL for ACID transactions, MongoDB for Catalog, Redis for Caching
- **Real-time Updates:** WebSockets for live delivery status tracking

#### 🔄 Microservices Architecture:
- **Order Service:** Order creation, validation, state management
- **Payment Service:** Idempotent payment processing with compensation
- **Inventory Service:** Stock management and allocation
- **Delivery Service:** Rider allocation with real-time status updates
- **Auth Service:** JWT-based authentication and authorization
- **Notification Service:** Event-driven email/SMS notifications

#### 📊 Observability Stack:
- **Distributed Tracing:** OpenTelemetry for end-to-end request tracing (API → Kafka → Services)
- **Prometheus + Grafana:** Custom dashboards for:
  - Kafka consumer lag monitoring
  - P95 latency alerts (threshold: 200ms)
  - Circuit breaker state tracking
- **ELK Stack:** Centralized logging across all services
- **Jaeger:** Trace visualization and performance analysis

#### 🛡️ Resilience Patterns:
- **Circuit Breakers:** Resilience4j for fault tolerance
- **Bulkhead Pattern:** Isolated thread pools for Payment Gateway to prevent cascading failures
- **Rate Limiting:** Per-service rate limiters
- **Retry Topics:** Kafka-based retry mechanism for failed messages
- **Dead Letter Queues:** Poison message handling and inspection

#### ☁️ Infrastructure & DevOps:
- **AWS EKS:** Managed Kubernetes on AWS
- **Terraform:** Infrastructure as Code for VPC, EKS cluster, networking
- **Helm Charts:** Zero-downtime rolling updates with probes
- **S3 Backend:** Terraform state management with DynamoDB locking
- **Auto-scaling:** Worker node auto-scaling based on demand

#### 🚀 CI/CD Pipeline:
- **GitHub Actions:** Automated builds on PR/merge to main
- **Docker:** Service containerization with ECR push
- **Jenkins:** Alternative CI/CD integration
- **Helm Deployment:** Automated K8s deployment on merge

#### 📈 Deployment Strategy:
- **Rolling Updates:** Zero-downtime deployments
- **Liveness Probes:** Detect and recover from deadlocks
- **Readiness Probes:** Verify dependency health before routing traffic
- **Resource Management:** JVM memory profiling with tuned requests/limits

#### 🔧 Tech Stack:
`Java 21` • `Spring Boot 3.2` • `Apache Kafka` • `MySQL 8` • `MongoDB` • `Redis` • `AWS EKS` • `Terraform` • `Helm` • `Docker` • `Prometheus` • `Grafana` • `OpenTelemetry` • `Jaeger` • `ELK Stack` • `Resilience4j` • `GitHub Actions`

---

## 🏆 Key Expertise Areas

### Microservices Architecture
- Design patterns: Service Discovery, API Gateway, Circuit Breaker, Saga Pattern
- Inter-service communication: REST, gRPC, Apache Kafka, Message Queues
- Spring Cloud ecosystem expertise
- Event-driven architecture with Kafka

### Cloud-Native Development
- AWS Services: ECS, EKS, EC2, RDS, S3, Lambda, CloudWatch, ALB
- Container orchestration with Kubernetes and Helm
- Infrastructure as Code with Terraform
- Zero-downtime deployments

### Observability & Monitoring
- **ELK Stack:** Elasticsearch, Logstash, Kibana for centralized logging
- **Prometheus:** Metrics collection, custom instrumentation, alerting
- **Jaeger:** Distributed tracing and trace visualization
- **Grafana:** Advanced dashboards for business and infrastructure metrics
- **OpenTelemetry:** End-to-end instrumentation across services

### Database Design & Optimization
- SQL optimization and indexing strategies
- NoSQL design patterns with MongoDB
- Redis caching strategies (Cache-Aside pattern)
- Data consistency and ACID transaction management
- Polyglot persistence architectures

### Resilience & Fault Tolerance
- Idempotency patterns (API-layer and consumer-layer)
- Dead Letter Queue (DLQ) handling
- Circuit breakers and bulkhead isolation
- Pessimistic locking for concurrent transactions
- Outbox pattern for event-driven reliability

---

## 🌐 Connect With Me

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/chandasaiprakash/)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://www.leetcode.com/u/chandasaiprakash/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:chandasaiprakash123@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF6B6B?style=for-the-badge&logo=firefox&logoColor=white)](https://chandasaiprakash.online/)

</div>

---

## 💡 What I'm Up To

- 🔭 Building scalable microservices architectures at scale
- ☁️ Architecting cloud-native solutions on AWS with Kubernetes
- 🛠️ Designing event-driven systems with Apache Kafka
- 🎨 Designing resilient and highly observable systems
- 🚀 Exploring advanced Kubernetes patterns and GitOps
- 📊 Implementing comprehensive observability stacks (ELK, Prometheus, Jaeger)
- 💻 Solving LeetCode problems and competitive programming challenges

---

## 📈 My Goals

- [ ] Build and open-source enterprise-grade microservices frameworks
- [ ] Contribute to Spring ecosystem and Kubernetes projects
- [ ] Share deep expertise through technical articles and conference talks
- [ ] Mentor developers in backend architecture and cloud-native design
- [ ] Stay cutting-edge with emerging technologies in cloud and DevOps
- [ ] Create production-ready reference architectures for distributed systems

---

## 🔗 Useful Resources

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [Kubernetes Official Docs](https://kubernetes.io/docs/)
- [Apache Kafka Documentation](https://kafka.apache.org/documentation/)
- [Prometheus Monitoring](https://prometheus.io/)
- [Jaeger Tracing](https://www.jaegertracing.io/)
- [ELK Stack Guide](https://www.elastic.co/what-is/elk-stack)
- [AWS Documentation](https://docs.aws.amazon.com/)
- [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)

---

<div align="center">

### ⭐ If you find my work helpful, please consider starring my repositories!

**Let's build scalable, resilient, and observable systems together! 🚀**

</div>