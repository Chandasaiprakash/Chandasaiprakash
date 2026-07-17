<h1 align="center">Hi, I'm Chanda Sai Prakash 👋</h1>
<h3 align="center">Backend Software Engineer — Distributed Systems & Event-Driven Architecture</h3>

<p align="center">
Java Backend Engineer at <b>Accenture</b> (Financial Services & IoT) — ~4 years building production backend systems that process <b>5M+ events/day</b>.
I propose and drive architectural decisions (Kafka adoption, Saga design, CQRS strategy) end-to-end, reviewed with senior architects — not just ticket execution.
</p>

<p align="center">
<a href="https://chandasaiprakash.online/"><img src="https://img.shields.io/badge/Portfolio-FF6B6B?style=for-the-badge&logo=firefox&logoColor=white"></a>
<a href="https://www.linkedin.com/in/chandasaiprakash/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>
<a href="https://www.leetcode.com/u/chandasaiprakash/"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black"></a>
<a href="mailto:chandasaiprakash123@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"></a>
</p>

---

### 🛠 Core Stack

`Java 21` `Spring Boot 3.x` `Spring Cloud` `Apache Kafka` `Redis` `MySQL` `PostgreSQL` `MongoDB` `AWS EKS` `Terraform` `Helm` `Docker` `Resilience4j` `OpenTelemetry` `Prometheus` `Grafana` `ELK` `Jaeger`

**Patterns I reach for:** Orchestrated Saga · CQRS · Outbox Pattern · Idempotent Consumers · Circuit Breaker / Bulkhead · Dead Letter Queues

---

### 🎯 Featured Projects

<details>
<summary><b>⚡ SwiftPay — Real-Time Event-Driven Payment Ledger</b> (production-grade, load-tested)</summary>
<br>

**[github.com/Chandasaiprakash/swiftpay](https://github.com/Chandasaiprakash/swiftpay)**

A distributed fintech platform for peer-to-peer payment processing — `Java 21` · `Spring Boot 3.5` · `Kafka` · `PostgreSQL 16` · `Redis 7` — 3 services (Transaction Gateway, Ledger Service, Analytics Worker), Outbox pattern for guaranteed publishing, dual-layer idempotency (Redis API dedup + DB consumer dedup), and a DLQ + retry pipeline for failure isolation.

**Load test — before vs after optimization** (k6, sustained 250 req/s target, 1M iterations):

| Metric | Before | After |
|---|---|---|
| p95 latency | 2.55s ❌ | **109.99ms** ✅ |
| Avg latency | 1.16s | 38.04ms |
| Dropped iterations | 232 | **0** |
| Error rate | — | **0.00%** |
| Throughput | degrading | stable **250 TPS** |

Root cause of the bottleneck: single Kafka partition + single consumer thread serializing processing at ~40 events/sec while the gateway accepted 250 req/s. Fixed by repartitioning (1→3), scaling consumer concurrency, switching to manual ack, and tuning the HikariCP pool, Tomcat threads, and Kafka producer batching — full before/after config diff is in the [repo](https://github.com/Chandasaiprakash/swiftpay#-performance-testing).

</details>

<details>
<summary><b>🍔 Foodie — Cloud-Native Distributed Food Ordering Platform</b> (personal project, load & chaos tested)</summary>
<br>

**[github.com/Chandasaiprakash/Foodie](https://github.com/Chandasaiprakash/Foodie)**

6 microservices (Order, Payment, Inventory, Delivery, Auth, Notification) on an orchestrated Saga with an Order-service coordinator, polyglot persistence (MySQL for transactions, MongoDB for catalog, Redis for real-time delivery state via CQRS), and full IaC (Terraform + Helm on AWS EKS, zero-downtime rolling deploys).

**Load test results** (k6, 200 concurrent users, end-to-end order flow):

| Metric | Result |
|---|---|
| Throughput | ~1,200 req/sec sustained |
| p95 latency | ~310ms |
| Redis read latency | 8–18ms p95 |
| Kafka consumer lag | <500 messages, stable under load |
| Error rate | ~0.3% (transient retries, no data corruption) |

**Production-inspired failure scenarios:** duplicate payment events from Kafka retries (fixed with idempotent consumers), payment success + order stuck PENDING from a failed publish (fixed with Outbox + retry publisher), coordinator crash mid-saga (fixed with persisted saga state + recovery scheduler), and a cache stampede on hot keys (fixed with probabilistic early expiration + mutex on cache miss).

</details>

---

### 💼 What I've actually shipped at work

At Accenture, on a 4-member backend team across Financial Services and IoT clients:

- **Proposed and drove Kafka adoption** for async payment flows — presented the REST-vs-async tradeoff, defined the topic/partition strategy, reviewed with senior architects.
- **Designed the orchestrated Saga** used across payment flows, owning idempotency guarantees and failure recovery.
- **Introduced the Outbox pattern** to close a dual-write data-loss gap.
- **Owned the CQRS + Redis read-model strategy** — justified a ~40% memory increase against a ~60% DB CPU reduction, which enabled an MySQL tier downgrade (net cost reduction).
- **Fixed an N+1 query bottleneck** in the transaction history API via execution-plan analysis — P95 latency 800ms → 500ms, no caching needed.
- **Debugged a recurring JVM OOM crash** in an IoT telemetry pipeline (5M+ events/day) — root-caused to an unbounded HashMap in dedup logic, fixed with a bounded Caffeine cache, eliminating the 6–8hr crash cycle.
- **Achieved 85%+ test coverage** on critical fund-transfer flows (JUnit 5 + Mockito), cutting production regressions.

More detail, including 5 real production-incident postmortems, is on my [portfolio](https://chandasaiprakash.online/).

---

### 📜 Certifications

`AWS Certified Solutions Architect – Associate (SAA-C02)` · `Microsoft Certified: DevOps Engineer Expert (AZ-400)` · `Microsoft Certified: Azure Administrator Associate (AZ-104)` · `Microsoft Certified: Azure Fundamentals (AZ-900)`

---

### 🚀 Currently Exploring

- Apache Flink
- Temporal
- gRPC
- Kubernetes Operators
- JVM Performance Engineering

---

### 🎯 Current Focus

- High-scale backend systems
- Performance engineering
- Distributed systems
- End-to-end service ownership
- Senior Backend Engineer opportunities

---

<p align="center">
<b>Let's build scalable, resilient, and observable systems together! 🚀</b>
</p>