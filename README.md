# System Design Handbook

This repository is a from-scratch system design handbook for engineers who want to make better architecture decisions, not memorize component names. It is written for a 3-5 year engineer preparing for system design interviews and for Staff or Principal engineers who want a careful reference for design reviews.

The handbook proceeds sequentially. Foundations come first, then networking and edge, data and scaling, distributed systems, observability, security, cloud, platform engineering, AI infrastructure, and full design walkthroughs.

## How To Use This Repository

- Read chapters in order when building fundamentals.
- Jump to a chapter when preparing a specific design review or interview topic.
- Use `STYLE_GUIDE.md` as the canonical vocabulary for shared terms.
- Use `STANDARDS.md` as the quality bar for every chapter.
- Treat capacity models as worked reasoning, not universal benchmark numbers.

## Numbering Scheme

Each chapter lives in a folder named `chapter-NN-kebab-title/` and contains a single `README.md`.

Example:

```text
chapter-01-estimation-and-capacity-modeling/README.md
```

Chapter numbers are stable once approved. If a later change requires inserting a new topic, prefer adding an appendix or renumbering only after explicit review.

## Table Of Contents

| # | Chapter |
|---:|---|
| 01 | [Estimation and Capacity Modeling](chapter-01-estimation-and-capacity-modeling/) |
| 02 | [Performance vs Scalability, Latency vs Throughput](chapter-02-performance-vs-scalability-latency-vs-throughput/) |
| 03 | [Availability and the Nines](chapter-03-availability-and-the-nines/) |
| 04 | [Durability and Reliability](chapter-04-durability-and-reliability/) |
| 05 | [Consistency Models](chapter-05-consistency-models/) |
| 06 | [CAP and PACELC](chapter-06-cap-and-pacelc/) |
| 07 | [TCP, UDP, and Connection Semantics](chapter-07-tcp-udp-and-connection-semantics/) |
| 08 | [HTTP/1.1, HTTP/2, HTTP/3, and QUIC](chapter-08-http-1-1-http-2-http-3-and-quic/) |
| 09 | [DNS](chapter-09-dns/) |
| 10 | [Load Balancing (L4/L7)](chapter-10-load-balancing-l4-l7/) |
| 11 | [Reverse Proxies and API Gateways](chapter-11-reverse-proxies-and-api-gateways/) |
| 12 | [CDN and Edge Delivery](chapter-12-cdn-and-edge-delivery/) |
| 13 | [REST vs RPC vs gRPC](chapter-13-rest-vs-rpc-vs-grpc/) |
| 14 | [Service Discovery](chapter-14-service-discovery/) |
| 15 | [Caching: Where to Cache](chapter-15-caching-where-to-cache/) |
| 16 | [Caching Patterns and Invalidation](chapter-16-caching-patterns-and-invalidation/) |
| 17 | [Indexing](chapter-17-indexing/) |
| 18 | [Database Transactions and Isolation Levels](chapter-18-database-transactions-and-isolation-levels/) |
| 19 | [SQL vs NoSQL](chapter-19-sql-vs-nosql/) |
| 20 | [The NoSQL Families](chapter-20-the-nosql-families/) |
| 21 | [Data Modeling at Scale](chapter-21-data-modeling-at-scale/) |
| 22 | [Replication and Quorums](chapter-22-replication-and-quorums/) |
| 23 | [SQL Replication](chapter-23-sql-replication/) |
| 24 | [Sharding and Partitioning](chapter-24-sharding-and-partitioning/) |
| 25 | [Consistent Hashing](chapter-25-consistent-hashing/) |
| 26 | [Design Walkthrough: URL Shortener](chapter-26-design-walkthrough-url-shortener/) |
| 27 | [Rate Limiting](chapter-27-rate-limiting/) |
| 28 | [Idempotency and Deduplication](chapter-28-idempotency-and-deduplication/) |
| 29 | [Resilience Patterns: Timeouts, Retries, Circuit Breakers, Bulkheads](chapter-29-resilience-patterns-timeouts-retries-circuit-breakers-bulkheads/) |
| 30 | [Message Queues and Async Work](chapter-30-message-queues-and-async-work/) |
| 31 | [Backpressure and Load Shedding](chapter-31-backpressure-and-load-shedding/) |
| 32 | [Event Sourcing and CQRS](chapter-32-event-sourcing-and-cqrs/) |
| 33 | [Distributed Transactions](chapter-33-distributed-transactions/) |
| 34 | [The Saga Pattern](chapter-34-the-saga-pattern/) |
| 35 | [Consensus With Raft](chapter-35-consensus-with-raft/) |
| 36 | [Failure Detection](chapter-36-failure-detection/) |
| 37 | [Leader Election and Split-Brain](chapter-37-leader-election-and-split-brain/) |
| 38 | [CRDTs and Vector Clocks](chapter-38-crdts-and-vector-clocks/) |
| 39 | [Metrics, Logs, Traces, and OpenTelemetry](chapter-39-metrics-logs-traces-and-opentelemetry/) |
| 40 | [SLI, SLO, SLA, and Error Budgets](chapter-40-sli-slo-sla-and-error-budgets/) |
| 41 | [Incident Management](chapter-41-incident-management/) |
| 42 | [Chaos Engineering](chapter-42-chaos-engineering/) |
| 43 | [Zero Trust](chapter-43-zero-trust/) |
| 44 | [IAM and RBAC](chapter-44-iam-and-rbac/) |
| 45 | [Secrets Management](chapter-45-secrets-management/) |
| 46 | [Service Identity and mTLS](chapter-46-service-identity-and-mtls/) |
| 47 | [Supply Chain Security (SBOM, SAST, DAST)](chapter-47-supply-chain-security-sbom-sast-dast/) |
| 48 | [Policy as Code (OPA/Kyverno)](chapter-48-policy-as-code-opa-kyverno/) |
| 49 | [Landing Zones and Well-Architected Foundations](chapter-49-landing-zones-and-well-architected-foundations/) |
| 50 | [Multi-Region Architectures](chapter-50-multi-region-architectures/) |
| 51 | [Disaster Recovery (RPO/RTO)](chapter-51-disaster-recovery-rpo-rto/) |
| 52 | [FinOps and Cloud Economics](chapter-52-finops-and-cloud-economics/) |
| 53 | [Kubernetes Architecture Overview](chapter-53-kubernetes-architecture-overview/) |
| 54 | [Service Mesh Tradeoffs](chapter-54-service-mesh-tradeoffs/) |
| 55 | [GitOps](chapter-55-gitops/) |
| 56 | [Internal Developer Platforms](chapter-56-internal-developer-platforms/) |
| 57 | [Golden Paths and Self-Service Infrastructure](chapter-57-golden-paths-and-self-service-infrastructure/) |
| 58 | [Vector Databases](chapter-58-vector-databases/) |
| 59 | [RAG Systems](chapter-59-rag-systems/) |
| 60 | [LLM Serving Architecture](chapter-60-llm-serving-architecture/) |
| 61 | [GPU Scheduling](chapter-61-gpu-scheduling/) |
| 62 | [Agent Systems](chapter-62-agent-systems/) |
| 63 | [AI Observability](chapter-63-ai-observability/) |
| 64 | [Design Walkthrough: Rate-Limited Public API](chapter-64-design-walkthrough-rate-limited-public-api/) |
| 65 | [Design Walkthrough: Chat System](chapter-65-design-walkthrough-chat-system/) |
| 66 | [Design Walkthrough: Twitter-Style Feed](chapter-66-design-walkthrough-twitter-style-feed/) |
| 67 | [Design Walkthrough: Web Crawler](chapter-67-design-walkthrough-web-crawler/) |
| 68 | [Design Walkthrough: Scaling to Millions of Users](chapter-68-design-walkthrough-scaling-to-millions-of-users/) |
| 69 | [Design Walkthrough: Global RAG/AI Service](chapter-69-design-walkthrough-global-rag-ai-service/) |

## Current Status

Phase 0 complete. Syllabus (69 chapters), style guide, standards, and this README are committed. Chapter 01 (Estimation and Capacity Modeling) is complete and committed. Awaiting approval to continue to Chapter 02.
