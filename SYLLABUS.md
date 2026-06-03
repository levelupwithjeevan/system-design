# System Design Handbook Syllabus

This syllabus is the canonical chapter order for the handbook. Each chapter folder will use the form `chapter-NN-kebab-title/`, with one `README.md` chapter file inside.

## Ordering Changes From The Proposed List

I kept every proposed topic area. Backstage is not a standalone chapter; it is covered inside the platform chapters where it naturally belongs. The syllabus now has 69 chapters.

- Added `Database Transactions and Isolation Levels` before `SQL vs NoSQL` so ACID, transaction boundaries, anomalies, and isolation levels are established before database-family tradeoffs.
- Added `Data Modeling at Scale` after `The NoSQL Families`, scoped to access-pattern-driven design so it complements rather than duplicates sharding.
- Moved `Design Walkthrough: URL Shortener` from the final walkthrough block to immediately after `Sharding and Partitioning` and `Consistent Hashing` as an early integration checkpoint.
- Added `Resilience Patterns: Timeouts, Retries, Circuit Breakers, Bulkheads` immediately after `Idempotency and Deduplication` so retry behavior is grounded in safe side effects before overload and async patterns.
- Reordered `Distributed Transactions` before `The Saga Pattern` because sagas are easier to evaluate after strict cross-resource atomicity has been explained.
- Added `Failure Detection` before `Leader Election and Split-Brain` because leader election depends on timeout, heartbeat, suspicion, and detector semantics.
- Merged the standalone `Backstage` chapter into `Internal Developer Platforms` and `Golden Paths and Self-Service Infrastructure` so Backstage is treated as one platform interface option, not as the platform itself.
- Moved TCP/UDP and HTTP before DNS, CDN, load balancing, gateways, RPC, and service discovery so edge and API design can refer back to transport and application protocol behavior.
- Moved indexing before SQL/NoSQL scaling choices because access paths often determine whether replication, partitioning, or a different data model is the right move.
- Moved generic replication and quorums before SQL replication because database-specific replication is easier to reason about after the quorum and replica-set tradeoffs are established.
- Moved message queues, async work, backpressure, and load shedding before event sourcing, distributed transactions, and sagas because those patterns depend on async failure and retry behavior.
- Moved observability and SRE before security, cloud, Kubernetes, and AI infrastructure so later chapters can rely on shared language for signals, SLOs, incidents, and operational readiness.
- Moved core security before cloud and platform chapters because landing zones, policy enforcement, and platform guardrails depend on identity, authorization, and secrets fundamentals.
- Placed service identity and mTLS before service mesh because mesh tradeoffs depend heavily on identity, certificate rotation, and encrypted service-to-service communication.

## Chapters

| # | Title | Objective |
|---:|---|---|
| 01 | Estimation and Capacity Modeling | Teach how to turn product requirements into explicit QPS, storage, bandwidth, and growth assumptions without false precision. |
| 02 | Performance vs Scalability, Latency vs Throughput | Separate speed, load, utilization, and growth so design reviews use the right metric for the right decision. |
| 03 | Availability and the Nines | Explain availability as a user-visible promise, including dependency math, failure domains, and operational tradeoffs. |
| 04 | Durability and Reliability | Distinguish keeping data from keeping behavior correct, and show how failure handling shapes both. |
| 05 | Consistency Models | Build a practical vocabulary for read/write guarantees and the product consequences of stale or conflicting data. |
| 06 | CAP and PACELC | Use partition tolerance, availability, consistency, latency, and normal-case operation as a decision framework rather than a slogan. |
| 07 | TCP, UDP, and Connection Semantics | Explain how connections, packets, retransmission, ordering, and flow control shape application behavior. |
| 08 | HTTP/1.1, HTTP/2, HTTP/3, and QUIC | Compare modern HTTP protocol behavior and its impact on latency, multiplexing, reliability, and edge design. |
| 09 | DNS | Treat naming as distributed infrastructure, covering resolution, caching, failover, and operational risk. |
| 10 | Load Balancing (L4/L7) | Show how traffic is distributed across instances and what algorithms, health checks, and failure modes matter. |
| 11 | Reverse Proxies and API Gateways | Explain request mediation, policy enforcement, routing, and where gateway centralization helps or hurts. |
| 12 | CDN and Edge Delivery | Design for content placement, cacheability, invalidation, regional latency, and origin protection. |
| 13 | REST vs RPC vs gRPC | Choose interface styles based on coupling, evolution, latency, streaming, tooling, and team boundaries. |
| 14 | Service Discovery | Explain how services find each other safely in dynamic environments and what happens when discovery lies. |
| 15 | Caching: Where to Cache | Map client, edge, application, database, and storage caches to the bottlenecks they actually solve. |
| 16 | Caching Patterns and Invalidation | Compare cache-aside, write-through, write-behind, refresh-ahead, TTLs, and invalidation under failure. |
| 17 | Indexing | Connect query patterns to data structures, write amplification, storage cost, and operational maintenance. |
| 18 | Database Transactions and Isolation Levels | Cover ACID, transaction boundaries, common anomalies, and standard isolation levels so database choices are grounded in correctness needs. |
| 19 | SQL vs NoSQL | Decide between relational and non-relational systems based on data shape, consistency, query needs, and operating model. |
| 20 | The NoSQL Families | Compare key-value, document, wide-column, graph, search, time-series, and object-store-backed approaches. |
| 21 | Data Modeling at Scale | Teach access-pattern-driven entity, aggregate, and query design for large systems without duplicating sharding mechanics. |
| 22 | Replication and Quorums | Explain replica placement, read/write quorum math, lag, repair, and the limits of majority thinking. |
| 23 | SQL Replication | Cover primary-replica, multi-primary, synchronous, asynchronous, and logical replication tradeoffs. |
| 24 | Sharding and Partitioning | Teach how to split data and traffic across partitions without hiding hot keys, joins, and rebalancing costs. |
| 25 | Consistent Hashing | Explain stable assignment, virtual nodes, replication rings, and where hash-based distribution breaks down. |
| 26 | Design Walkthrough: URL Shortener | Apply the early scaling chapters to a compact read-heavy service with redirects, uniqueness, caching, sharding, and abuse controls. |
| 27 | Rate Limiting | Design admission control for fairness, abuse resistance, dependency protection, and graceful degradation. |
| 28 | Idempotency and Deduplication | Make retries safe by designing operation identity, deduplication windows, and side-effect boundaries. |
| 29 | Resilience Patterns: Timeouts, Retries, Circuit Breakers, Bulkheads | Design bounded remote calls, safe retry policies, dependency isolation, and failure containment before overload becomes outage. |
| 30 | Message Queues and Async Work | Decide when to decouple with queues and how delivery semantics, ordering, retries, and dead letters shape reliability. |
| 31 | Backpressure and Load Shedding | Keep overload from becoming outage by controlling demand, work queues, concurrency, and priority. |
| 32 | Event Sourcing and CQRS | Evaluate append-only state changes, derived read models, replay, schema evolution, and operational recovery. |
| 33 | Distributed Transactions | Explain atomic commitment, two-phase commit, transactional outboxes, and when strict cross-service atomicity is worth the cost. |
| 34 | The Saga Pattern | Coordinate multi-step business workflows with compensating actions, explicit failure states, and realistic recovery. |
| 35 | Consensus With Raft | Teach replicated decision-making, leader terms, logs, elections, and why consensus is expensive but foundational. |
| 36 | Failure Detection | Explain heartbeats, timeouts, leases, phi-style suspicion, false positives, and why failure detection is a tradeoff rather than an oracle. |
| 37 | Leader Election and Split-Brain | Design leadership safely under partial failure, leases, fencing, and stale authority. |
| 38 | CRDTs and Vector Clocks | Explain conflict-aware data types and causality tracking for systems that cannot coordinate every write. |
| 39 | Metrics, Logs, Traces, and OpenTelemetry | Build an observability model from signals, cardinality, context propagation, and instrumentation ownership. |
| 40 | SLI, SLO, SLA, and Error Budgets | Turn reliability goals into measurable promises and release/risk decisions. |
| 41 | Incident Management | Show how detection, command, communication, mitigation, postmortems, and learning loops work in real organizations. |
| 42 | Chaos Engineering | Use controlled failure experiments to validate assumptions without gambling with users. |
| 43 | Zero Trust | Design systems around explicit identity, least privilege, continuous verification, and assumed breach. |
| 44 | IAM and RBAC | Model human and workload authorization, role design, privilege boundaries, and auditability. |
| 45 | Secrets Management | Handle credentials, rotation, encryption, access paths, and failure modes without spreading static trust. |
| 46 | Service Identity and mTLS | Secure service-to-service communication with workload identity, certificates, trust roots, and rotation. |
| 47 | Supply Chain Security (SBOM, SAST, DAST) | Protect build and release paths with dependency visibility, scanning, provenance, and realistic enforcement. |
| 48 | Policy as Code (OPA/Kyverno) | Make guardrails reviewable and enforceable across infrastructure, deployments, and runtime admission. |
| 49 | Landing Zones and Well-Architected Foundations | Establish cloud account structure, networking, guardrails, identity, and shared operating constraints. |
| 50 | Multi-Region Architectures | Compare active-passive, active-active, cell-based, and edge-heavy designs under data, latency, and failure constraints. |
| 51 | Disaster Recovery (RPO/RTO) | Design recovery objectives, backup/restore, failover, runbooks, and drills around business impact. |
| 52 | FinOps and Cloud Economics | Treat cost as an engineering constraint with allocation, unit economics, forecasting, and waste control. |
| 53 | Kubernetes Architecture Overview | Explain the control plane, nodes, scheduling, networking, storage, and failure domains of Kubernetes. |
| 54 | Service Mesh Tradeoffs | Decide whether a mesh earns its operational cost for traffic policy, identity, telemetry, and resilience. |
| 55 | GitOps | Use declarative desired state, review workflows, reconciliation, and rollback for infrastructure and applications. |
| 56 | Internal Developer Platforms | Design platform capabilities, service catalogs, portal patterns such as Backstage, and ownership models that improve delivery without centralizing every decision. |
| 57 | Golden Paths and Self-Service Infrastructure | Build paved roads for common workflows, including Backstage-style exposure, while preserving escape hatches and ownership clarity. |
| 58 | Vector Databases | Explain vector indexing, recall, filtering, freshness, and operational tradeoffs for semantic retrieval. |
| 59 | RAG Systems | Design retrieval-augmented generation around ingestion, chunking, indexing, ranking, grounding, and evaluation. |
| 60 | LLM Serving Architecture | Cover model hosting, routing, batching, streaming, latency control, safety, and cost management. |
| 61 | GPU Scheduling | Explain accelerator allocation, bin packing, isolation, queues, preemption, and utilization tradeoffs. |
| 62 | Agent Systems | Design tool-using AI workflows around planning limits, state, permissions, observability, and rollback. |
| 63 | AI Observability | Measure AI systems with quality, drift, safety, latency, cost, traceability, and human feedback loops. |
| 64 | Design Walkthrough: Rate-Limited Public API | Design a public API that survives abuse, tenant fairness problems, dependency limits, and product growth. |
| 65 | Design Walkthrough: Chat System | Build a real-time messaging system across delivery, ordering, presence, offline storage, and moderation. |
| 66 | Design Walkthrough: Twitter-Style Feed | Design fanout, ranking, timelines, caching, and write/read tradeoffs for social feeds. |
| 67 | Design Walkthrough: Web Crawler | Cover frontier management, politeness, deduplication, parsing, storage, and adversarial web behavior. |
| 68 | Design Walkthrough: Scaling to Millions of Users | Walk through the staged evolution from single service to partitioned, observable, multi-region architecture. |
| 69 | Design Walkthrough: Global RAG/AI Service | Combine AI, retrieval, multi-region serving, security, cost governance, and operations into one production design. |

