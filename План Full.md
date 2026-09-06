Уровни владения (Taxonomy):
- **A = Awareness**
- **P = Practitioner**
- **E = Expert**
- **S = Scholar**

### L1. Foundations — Фундаментальные основы

#### 1.1. Computer Science / Algorithms & Data Structures

L1.CS.01 — Асимптотическая сложность, Big O/Θ/Ω, upper/lower bounds [E]  
L1.CS.02 — Анализ рекурсии, Master theorem, recursion tree [E]  
L1.CS.03 — Амортизированный анализ (динамический массив, хеш-таблица) [E]  
L1.CS.04 — Хеш‑таблицы: открытая адресация, chaining, resize стратегии [E]  
L1.CS.05 — Сбалансированные деревья: AVL, Red‑Black, B‑tree, B+‑tree [E]  
L1.CS.06 — Heap / priority queue, биномиальные / фибоначчиевы кучи [P]  
L1.CS.07 — Графы: BFS/DFS, topological sort, SCC [P]  
L1.CS.08 — Shortest path: Dijkstra, Bellman‑Ford, A*, multi‑source [P]  
L1.CS.09 — Minimum Spanning Tree: Prim/Kruskal, disjoint‑set (Union‑Find) [P]  
L1.CS.10 — Approximation algorithms и жадные стратегии [A]

#### 1.2. Probabilistic & Streaming Structures

L1.CS.11 — Bloom Filter: false positive rate, tuning, variants [E]  
L1.CS.12 — Counting Bloom / Cuckoo filters [E]  
L1.CS.13 — HyperLogLog, cardinality estimation, bias correction [dancres.github.io](https://dancres.github.io/Pages/?utm_source=chatgpt.com)  
L1.CS.14 — Count‑Min Sketch, heavy hitters [E]  
L1.CS.15 — Streaming‑алгоритмы: reservoir sampling, quantiles [P]
L1.CS.16 — Memory Allocators Internals: jemalloc / tcmalloc / mimalloc (арена, фрагментация) [E] L1.CS.17 — Garbage Collection Deep Dive: Generational hypothesis, Write barriers, Tricolor marking [E]
#### 1.3. Networking: модели и протоколы

L1.NET.01 — OSI vs TCP/IP, L2–L7, encapsulation [E]  
L1.NET.02 — Ethernet, VLAN, STP, link aggregation [P]  
L1.NET.03 — IP addressing, subnetting, CIDR, routing basics [P]  
L1.NET.04 — BGP: path selection, convergence, route flapping, communities E [High Performance Browser Networking](https://hpbn.co/?utm_source=chatgpt.com)  
L1.NET.05 — Anycast, ECMP, routing for large‑scale services [E]  
L1.NET.06 — TCP 3‑way handshake, connection states, TIME_WAIT [E]  
L1.NET.07 — TCP congestion control: Tahoe/Reno, CUBIC, BBR, BDP [High Performance Browser Networking](https://hpbn.co/?utm_source=chatgpt.com) [S]  
L1.NET.08 — TCP flow control, sliding window, Nagle, delayed ACK [E]  
L1.NET.09 — UDP, QUIC: отличие по надёжности, congestion control, 0‑RTT [IETF Datatracker](https://datatracker.ietf.org/doc/rfc9000/?utm_source=chatgpt.com) [E]  
L1.NET.10 — TLS 1.2 vs 1.3, handshake, session resumption, ALPN [High Performance Browser Networking](https://hpbn.co/?utm_source=chatgpt.com) [E]  
L1.NET.11 — HTTP/1.1 vs HTTP/2 vs HTTP/3, multiplexing, HoL blocking [E]  
L1.NET.12 — DNS, DNSSEC, load balancing via DNS [P]  
L1.NET.13 — gRPC: HTTP/2 framing, streaming, deadlines, interceptors [gRPC](https://grpc.io/docs/?utm_source=chatgpt.com) [P]  
L1.NET.14 — Service Mesh: Envoy, sidecar, mTLS, xDS APIs [Google Cloud+1](https://cloud.google.com/service-mesh/docs/service-routing/set-up-envoy-http-mesh?utm_source=chatgpt.com) [E]  
L1.NET.15 — SDN: OpenFlow, control plane vs data plane [A]  
L1.NET.16 — Anycast‑CDN, edge‑pop, geo‑routing [P]
L1.NET.17 — Network Virtualization: VXLAN, Geneve, Overlay networks internals [P]
#### 1.4. OS Internals (Linux)

L1.OS.01 — Архитектура ядра Linux: user/kernel space, syscalls [E] [GitHub](https://github.com/mthipparthi/operating-systems-three-easy-pieces/blob/master/book.pdf?utm_source=chatgpt.com)  
L1.OS.02 — Планировщик задач (CFS), приоритеты, cgroups [E]  
L1.OS.03 — Virtual memory, paging, page cache, NUMA awareness [E]  
L1.OS.04 Memory Reclaim, Swapping & OOM Killer [E]
L1.OS.05 — Copy‑on‑write, fork/exec, overcommit [E]  
L1.OS.06 — Filesystems basics: VFS, inodes, journaling [E]  
L1.OS.07 — ext4 journaling modes, delayed allocation [E]  
L1.OS.08 — ZFS: CoW, snapshots, checksums, ARC/L2ARC [P]  
L1.OS.09 — I/O schedulers, blk‑mq, async I/O [P]  
L1.OS.10 — eBPF: BPF VM, maps, hooks (kprobe, tracepoint) [GitHub](https://github.com/mthipparthi/operating-systems-three-easy-pieces/blob/master/book.pdf?utm_source=chatgpt.com) [E]  
L1.OS.11 — Containers vs VMs: namespaces, cgroups, seccomp [E]

#### 1.5. Concurrency Models

L1.CONC.01 — Threads vs processes, context switch cost [P]  
L1.CONC.02 — Mutex, RW‑lock, condition variables, deadlock patterns [P]  
L1.CONC.03 — Event loop, reactor/proactor, async I/O [E]  
L1.CONC.04 — Goroutines, schedulers, channels (Go) [P]  
L1.CONC.05 — Actor model (Akka, Erlang, Orleans) [P]  
L1.CONC.06 — Lock‑free структуры, CAS, ABA‑проблема [A]  
L1.CONC.07 — Java Memory Model, happens‑before, volatile [E]  
L1.CONC.08 — False sharing, cache coherence (MESI) [A]  
L1.CONC.09 — Coroutine frameworks (Kotlin, .NET async/await) [P]  
L1.CONC.10 — Structured concurrency (Go, Kotlin, C++) [A]

#### 1.6. Distributed Systems Theory

L1.DST.01 — Модель отказов: crash‑stop, crash‑recovery, Byzantine [E]  
L1.DST.02 — CAP theorem, формулировка и ограничения интерпретации [GitHub](https://github.com/pritamnikam/rag-langchain-architecture?utm_source=chatgpt.com) [E]  
L1.DST.03 — PACELC: latency vs consistency tradeoffs [The Data Lead](https://thedatalead.com/understanding-the-pacelc-theorem-in-distributed-systems/?utm_source=chatgpt.com) [E]  
L1.DST.04 — Eventual, causal, strong consistency: формальные определения [E]  
L1.DST.05 — Vector clocks, Lamport clocks, partial order [E] [pdos.csail.mit.edu](https://pdos.csail.mit.edu/6.824/schedule.html)  
L1.DST.06 — Consensus problem, FLP impossibility [S]  
L1.DST.07 — Paxos family: single‑decree, multi‑Paxos [S]  
L1.DST.08 — Viewstamped Replication (VRR) [S] [infraascode.com.br](https://infraascode.com.br/pacelc/?utm_source=chatgpt.com)  
L1.DST.09 — Raft: leader election, log replication, membership change [ilyasergey.net+1](https://ilyasergey.net/CS6213/_static/02-consensus/raft.pdf?utm_source=chatgpt.com) [S]  
L1.DST.10 — Zab / Zookeeper atomic broadcast [E]  
L1.DST.11 — Byzantine Generals problem и BFT (PBFT) [pdos.csail.mit.edu](https://pdos.csail.mit.edu/6.824/schedule.html) [E]  
L1.DST.12 — Gossip protocols, anti‑entropy, SWIM [P]  
L1.DST.13 — CRDTs: G‑Counter, OR‑Set, LWW‑Register [P]  
L1.DST.14 — 2PC/3PC, distributed commit, failure scenarios [E]  
L1.DST.15 — Replication: primary‑backup, chain, quorum [E]  
L1.DST.16 — Quorum systems: majority, read/write quorums, weighted [E]  
L1.DST.17 — Partitioning schemes: range/hash/consistent hashing [E]  
L1.DST.18 — Leaderless protocols (Dynamo‑style, Riak) [E]  
L1.DST.19 — Snapshotting и log compaction в replicated state machine [E]  
L1.DST.20 — Formal verification of distributed systems (TLA+) [A]
**L1.DST.21 — Deterministic Simulation Testing (FoundationDB style)**
L1.DST.22 — Time Synchronization: NTP vs PTP, TrueTime (Google), Hybrid Logical Clocks (HLC) детали реализации [E]

#### 1.7. Hardware & Storage Physics (Low Level)

**L1.HW.01** — Erasure Coding: Reed-Solomon, LRC (Local Reconstruction Codes), trade-off между storage overhead и repair network traffic [E].
**L1.HW.02** — SSD Internals: Pages, Blocks, Wear Leveling, Write Amplification, GC внутри диска [E].
**L1.HW.03** — CPU Caches: L1/L2/L3 latencies, Cache lines, False sharing (уже есть в Concurrency, но важно тут), NUMA topology impact [E].


---

### L2. System Design & Architecture

#### 2.1. Architectural Patterns

L2.ARCH.01 — Monolith: layered, hexagonal, модульность [P]  
L2.ARCH.02 — Microservices: autonomy, data ownership, Conway’s Law [samnewman.io+1](https://samnewman.io/books/building_microservices_2nd_edition/?utm_source=chatgpt.com) [E]  
L2.ARCH.03 — SOA vs microservices vs EDA [E]  
L2.ARCH.04 — Event‑Driven Architecture: event sourcing, CQRS [E]  
L2.ARCH.05 — Serverless: FaaS, cold start, idempotency, limits [pdos.csail.mit.edu+1](https://pdos.csail.mit.edu/6.824/schedule.html) [P]  
L2.ARCH.06 — Lambda architecture (batch+speed+serving) [P]  
L2.ARCH.07 — Kappa architecture (stream‑only) [P]  
L2.ARCH.08 — Cell‑based / micro‑frontends / multi‑tenant isolation [InfoQ](https://www.infoq.com/distributed_systems/?utm_source=chatgpt.com) [E]  
L2.ARCH.09 — Micro‑frontends  [E]  
L2.ARCH.10 — API Gateway vs BFF vs Service Mesh [E]  
L2.ARCH.11 — Multiregion active‑active vs active‑passive [E]  
L2.ARCH.12 — Data locality, edge computing, CDN integration [P]
**L2.ARCH.13** — Strangler Fig & Legacy Migration patterns [E].
**L2.ARCH.14** — API Management policies: Throttling tiers, Monetization strategies, Developer Portal DX [P].    
**L2.ARCH.15** — Webhooks & delivery guarantees (HMAC signature, retries, exponential backoff) [P].

L2.DDD.01 Strategic DDD: Bounded Contexts, Ubiquitous Language, Context Mapping (Partnership, ACL, OHS) [E] 
L2.DDD.02 Tactical DDD: Aggregates, Entities vs Value Objects, Domain Events invariants [P]

L2.API.01 API IDL & Schemas: Protobuf vs Avro vs Thrift (backward/forward compatibility rules) [E] 
L2.API.02 GraphQL Federation: Apollo Federation, Supergraph architecture, N+1 problem mitigation [P] 
L2.API.03 Contract Testing: Consumer-Driven Contracts (Pact), Schema Registry pattern [E]
L2.API.04 — Idempotency Keys implementation deep-dive
L2.API.05 Asynchronous Correlation & Long-Running Sagas
L2.API.06 REST API Versioning Strategies: URI vs Header vs Content Negotiation (pros/cons/caching impact) [E] 
L2.API.07 gRPC Versioning: Package Evolution & Interface Adapters [E]
L2.API.08 Kafka (Event Streaming) - Schema Evolution [E]
L2.API.09 Message Queues Versioning: Transient Messaging [E]
L2.API.10 — Hypermedia / HATEOAS: Richardson Maturity Model, практическая применимость vs сложность [A] 
L2.API.11 — AsyncAPI specification: документирование событийно-ориентированных архитектур [P]

**L2.INT.01** — **Enterprise Integration Patterns (EIP):** Message Broker patterns, Dead Letter Queues, Scatter-Gather, Wire Tap [P].
**L2.INT.02** — **Change Data Capture (CDC) at scale:** Debezium pitfalls, transactional outbox pattern implementation details [E].

##### Client-Side & Mobile Constraints
L2.MOB.01 — Offline-first architectures: Conflict Resolution strategies (Last-Write-Wins vs CRDT on client) [P] 
L2.MOB.02 — Battery & Bandwidth optimization: Batching, binary protocols, radio wake-up patterns [A] 
L2.MOB.03 — Backend for Frontend (BFF) patterns: Aggregation, trimming, protocol translation [E]
#### 2.2. Database Engineering

L2.DATA.01 — Data Modeling: Star Schema vs Snowflake vs Data Vault 2.0 [P] 
L2.DATA.02 — ETL vs ELT pipelines: dbt architecture, DAGs orchestration (Airflow/Prefect internals) [P] 
L2.DATA.03 — Data Quality & Governance: Data Contracts, Anomaly detection in data streams [P] 
L2.DATA.04 — Stream Processing Internals: Watermarks, Windowing types (Tumbling, Sliding, Session), Late data handling [E] 
L2.DATA.05 — Batch Processing Optimization: Spark Shuffle internals, Skew handling, Broadcast joins [E]

L2.DB.01 — ACID vs BASE, CAP implications [E]  
L2.DB.02 — Isolation levels: Read Uncommitted → Serializable, anomalies [Wikipedia+1](https://en.wikipedia.org/wiki/Snapshot_isolation?utm_source=chatgpt.com) [S]  
L2.DB.03 — MVCC internals (Postgres, MySQL InnoDB) [E]  
L2.DB.04 — WAL: write‑ahead logging, log‑structured storage [E]  
L2.DB.05 — B‑tree storage engines (InnoDB, Postgres heap+indexes) [E]  
L2.DB.06 — LSM‑tree engines (LevelDB/RocksDB/Cassandra/TiKV) [Database Internals](https://www.databass.dev/?utm_source=chatgpt.com) [E]  
L2.DB.07 — Columnar vs row‑oriented, vectorized execution, compression [research.google.com+1](https://research.google.com/pubs/archive/36632.pdf?utm_source=chatgpt.com) [E]  
L2.DB.08 — Query planning & cost‑based optimizers  [E]  
L2.DB.09 — Distributed SQL (Spanner, CockroachDB, Yugabyte) [research.google.com+1](https://research.google.com/pubs/archive/46103.pdf?utm_source=chatgpt.com) [E]  
L2.DB.10 — NoSQL families: key‑value, document, wide‑column, graph [P]  
L2.DB.11 — Graph DBs и social graph (TAO, Neo4j) [USENIX](https://www.usenix.org/system/files/conference/atc13/atc13-bronson.pdf?utm_source=chatgpt.com) [P]  
L2.DB.12 — Time‑series DBs (Prometheus, M3, Timescale) [P]  
L2.DB.13 — NewSQL & HTAP: TiDB, SingleStore, Snowflake [redbook.io](https://www.redbook.io/?utm_source=chatgpt.com) [A]  
L2.DB.14 — Change Data Capture (CDC), Debezium, log‑based replication [E]  
L2.DB.15 — Data warehouse vs data lake vs lakehouse (Delta/Apache Iceberg) [E]  
L2.DB.16 — OLTP vs OLAP workload characterization [P]  
L2.DB.17 — Secondary indexes, covering indexes, index‑only scans [P]  
L2.DB.18 — Sharding vs partitioning (DB‑уровень vs app‑level) [E]  
L2.DB.19 — Multi‑tenant схемы: pooled vs siloed vs hybrid [P]

#### 2.3. Scalability & Resilience

L2.SCL.01 — Horizontal vs vertical scaling; scaling laws (Amdahl/Gustafson) [P]  
L2.SCL.02 — Sharding strategies: range, hash, geo, customer‑tier [E] [Medium](https://medium.com/pinterest-engineering/sharding-pinterest-how-we-scaled-our-mysql-fleet-3f341e96ca6f?trk=public_post_comment-text&utm_source=chatgpt.com)  
L2.SCL.03 — Consistent hashing и виртуальные ноды (Cassandra, Dynamo) [Amazon Science+1](https://www.amazon.science/publications/dynamo-amazons-highly-available-key-value-store?utm_source=chatgpt.com) [E]  
L2.SCL.04 — Caching patterns: read‑through, write‑through, write‑behind [P]  
L2.SCL.05 — Semantic Caching: The AI Latency Shield [E]
L2.SCL.06 — Cache invalidation, cache stampede, dogpile protection [E]  
L2.SCL.07 — Rate limiting (token bucket, leaky bucket) [P]  
L2.SCL.08 — Circuit breaker, bulkhead, retry with jitter [P]  
L2.SCL.09 — Backpressure в async системах (Reactive Streams) [P]  
L2.SCL.10 — Idempotency ключей и безопасное повторение запросов [E]  
L2.SCL.11 — Chaos Engineering: fault injection, steady‑state hypothesis [rsystems.com+2TechHQ+2](https://www.rsystems.com/blogs/what-is-chaos-engineering-and-how-netflix-uses-it-to-make-its-system-more-resilient/?utm_source=chatgpt.com) [P]  
L2.SCL.12 — Multi‑region replication, failover runbooks [E]  
L2.SCL.13 — Tail latency, p99/p999, H‑T fairness [P]  
L2.SCL.14 — Thundering herd mitigation (queueing, pre‑warming) [P]  
L2.SCL.15 — Distributed locks (Zookeeper, etcd, Redis redlock caveats) [E]  
L2.SCL.16 — Saga pattern для распределённых транзакций [P]  
L2.SCL.17 — Blue/green, canary, feature flags, dark launches [P]  
L2.SCL.18 — Observability pillars: logs/metrics/traces [P]  
L2.SCL.19 — Capacity planning и load testing (stress/soak) [P]  

**L2.SCL.21** — Consumer-Driven Contract Testing (Pact) [P].
**L2.SCL.22** — Shadow Traffic / Traffic Mirroring (безопасный тест на проде) [E].

L2.K8S.01 K8s Internals: Controller pattern, Reconciliation loop, Informers/Listers [E] 
L2.K8S.02 K8s Networking deep-dive: CNI plugins (Calico/Cilium), eBPF dataplane, IPVS vs Iptables [P] 
L2.K8S.03 Operator Pattern: Writing Custom Resource Definitions (CRDs) & Operators (Kubebuilder) [P]
#### 2.4. Security Architecture

L2.SEC.01 — Threat modeling: STRIDE, DREAD [P]  
L2.SEC.02 — Defense in depth, least privilege, secure defaults [P]  
L2.SEC.03 — Zero Trust Architecture (BeyondCorp, NCSC principles) [services.google.com+1](https://services.google.com/fh/files/misc/ncsc_zero_trust_principles_on_google_cloud_v1.pdf?utm_source=chatgpt.com) [E]  
L2.SEC.04 — OAuth2 grant types, PKCE, scopes, refresh tokens [IETF+1](https://www.ietf.org/archive/id/draft-ietf-oauth-security-topics-26.html?utm_source=chatgpt.com) [E]  
L2.SEC.05 — OpenID Connect: ID Token, claims, discovery [oauch.io+1](https://oauch.io/Documents/Info/OIDC?utm_source=chatgpt.com) [E]  
L2.SEC.06 — TLS, PKI, CAs, certificate pinning, OCSP stapling [High Performance Browser Networking](https://hpbn.co/?utm_source=chatgpt.com) [E]  
L2.SEC.07 — Symmetric vs asymmetric crypto (AES, RSA, ECC) [P]  
L2.SEC.08 — Hashing: SHA‑2, SHA‑3, password hashing (bcrypt/argon2) [P]  
L2.SEC.09 — Secrets management (Vault, KMS, HSM) [P]  
L2.SEC.10 — Security for microservices: mTLS, JWT, service identity [E]  
L2.SEC.11 — Compliance: GDPR, PCI‑DSS, SOC2 controls overview [A]  
L2.SEC.12 — Kubernetes security & hardening (NSA/CISA guidance) [Kubernetes+1](https://kubernetes.io/blog/2021/10/05/nsa-cisa-kubernetes-hardening-guidance/?utm_source=chatgpt.com) [P]  
L2.SEC.13 — OWASP Top 10, ASVS, API security [P]  
L2.SEC.14 — Post‑Quantum Cryptography basics, NIST PQC standards [NIST+2NIST+2](https://www.nist.gov/news-events/news/2024/08/nist-releases-first-3-finalized-post-quantum-encryption-standards?utm_source=chatgpt.com) [A]  
L2.SEC.15 — Key rotation, crypto‑agility, “harvest now, decrypt later” risk [TechRadar+1](https://www.techradar.com/pro/cyber-resilience-in-the-post-quantum-era-the-time-of-crypto-agility?utm_source=chatgpt.com) [A]  
L2.SEC.16 — Authentication patterns: passwordless, WebAuthn [A]  
L2.SEC.17 — Data‑at‑rest & in‑transit encryption strategies [P]  
L2.SEC.18 — DLP и классификация данных [A]  
L2.SEC.19 — Multi‑tenant isolation & noisy neighbor security [P]  
L2.SEC.20 — Incident response for security events (IR playbooks) [P]
L2.SEC.21 Software Supply Chain: SLSA framework, in-toto attestation, SBOM (SPDX/CycloneDX) [E] 
L2.SEC.22 Code Signing: Sigstore/Cosign, TUF (The Update Framework) [P] 
L2.SEC.23 Secret Zero problem: SPIFFE/SPIRE architecture, workload identity federation [A]

#### Platform Engineering

**L2.PLAT.01** — **Internal Developer Platforms (IDP):** Backstage architecture, Software Templates concept [P].
**L2.PLAT.02** — **Infrastructure as Code (IaC) Patterns:** Ephemeral environments, Drift detection, Policy-as-Code (OPA/Kyverno) [E].

---

### L3. Processes, Leadership & Business (Staff+/CTO‑уровень)

#### 3.1. Technical Strategy & Economics

L3.BIZ.01 — Product vs platform thinking; technical vision [E]  
L3.BIZ.02 — Build vs Buy vs Open Source, vendor lock‑in analysis [E]  
L3.BIZ.03 — TCO: infra + лицензии + people + ops, amortization [E]  
L3.BIZ.04 — ROI оценки технических инициатив, бизнес‑кейс [E]  
L3.BIZ.05 — Cost optimization (FinOps, cloud cost allocation, unit economics) [P]  
L3.BIZ.06 — Portfolio of bets: core vs risky R&D [A]  
L3.BIZ.07 — Roadmapping: 1–3 year architecture north star [P]  
L3.BIZ.08 — Risk management: tech, vendor, regulatory, people [P]  
L3.BIZ.09 — Due diligence (M&A, крупные партнёрства) [A]  
L3.BIZ.10 — External representation: talks, papers, open source [P]

##### Financial Engineering (FinOps)
L3.FIN.01 — Unit Economics & Cloud FinOps
L3.FIN.02 — Cloud Cost Attribution: Tagging strategies, Shared resources cost splitting (K8s namespaces) [E] 
L3.FIN.03 — Reserved Instances / Savings Plans: математика коммитов, Break-even point analysis [P] 
L3.FIN.04 — Spot Instances Architecture: архитектура, устойчивая к прерываниям (checkpointing) [E]

##### Strategic Frameworks
L3.STRAT.01 — Wardley Mapping: Value chain, evolution axis, определение build/buy через карту [E] 
L3.STRAT.02 — North Star Metric Framework: связывание архитектурных метрик с метриками продукта [P] 
L3.STRAT.03 — Architecture Governance: Architecture Review Boards (ARB) vs Lightweight RFC process [E] 
L3.STRAT.04 — Compliance Engineering: PII scanning, Data Residency patterns, "Right to be Forgotten" implementation [E]

#### 3.2. Influence & Leadership

L3.LEAD.01 — Influence without authority, лидерство через экспертизу [E]  
L3.LEAD.02 — Stakeholder mapping (RACI, power/interest) [P]  
L3.LEAD.03 — Технические переговоры: компромиссы, trade‑offs [P]  
L3.LEAD.04 — Спонсорство (sponsorship) vs менторство [P]  
L3.LEAD.05 — Career frameworks, growth plans для инженеров [P]  
L3.LEAD.06 — Writing: RFCs, ADRs, tech vision docs [E]  
L3.LEAD.07 — Cross‑org alignment: Staff+ forums, architecture review boards [E]  
L3.LEAD.08 — Handling conflict и эскалации между командами [P]  
L3.LEAD.09 — Hiring бар для Senior/Staff, interview design [P]  
L3.LEAD.10 — Succession planning, knowledge transfer [A]
**L3.LEAD.11** — Team Topologies: 4 team types & 3 interaction modes [E].
**L3.LEAD.12** — Cognitive Load Management: платформенный подход для снижения нагрузки [E].

L3.ORG.01 Team Topologies: Stream-aligned, Enabling, Platform, Subsystem teams. Interaction modes (X-as-a-Service) [E] 
L3.ORG.02 Cognitive Load Theory: Оценка когнитивной нагрузки команд при выборе архитектуры [P] 
L3.ORG.03 Architecture Decision Records (ADR): внедрение культуры неизменяемого лога решений [E]
#### 3.3. Operational Excellence & SRE

L3.SRE.01 — SLO / SLI / SLA, error budgets, error budget policy [E]  
L3.SRE.02 — Incident lifecycle: detection → triage → mitigation → resolution [E]  
L3.SRE.03 — Post‑mortems: blameless, 5 Whys, corrective actions [E]  
L3.SRE.04 — On‑call дизайн, escalation policies, toil reduction [P]  
L3.SRE.05 — DORA metrics: deployment freq, lead time, MTTR, change fail rate [P]  
L3.SRE.06 — Error budget‑driven development (feature vs reliability work) [E]  
L3.SRE.07 — Runbooks, playbooks, GameDays [P]  
L3.SRE.08 — Observability strategy: metrics (RED/USE), tracing, logging [P]  
L3.SRE.09 — Capacity management и performance budgeting [P]  
L3.SRE.10 — Operability by design: graceful degradation, feature kill‑switches [E]  
L3.SRE.11 — Compliance & audits impact on operations (change management) [A]  
L3.SRE.12 — Incident communication: internal & external (status pages) [P]  
L3.SRE.13 — SLIs для ML/LLM‑систем (drift, hallucinations, latency) [A]  
L3.SRE.14 — Chaos experiments как часть SLO‑стратегии [P]  
L3.SRE.15 — Reliability review for new architectures (pre‑launch) [P]

**L3.GOV.01 — Architectural Fitness Functions:** (Building Evolutionary Architectures)

---

### L4. The Frontier — Академический / исследовательский уровень

#### 4.1. Classics (whitepapers)

L4.PAP.01 — Google File System (GFS) [S]  
L4.PAP.02 — MapReduce [S]  
L4.PAP.03 — BigTable [S]  
L4.PAP.04 — Dynamo (Amazon) [S]  
L4.PAP.05 — Spanner [S]  
L4.PAP.06 — ZooKeeper [S]  
L4.PAP.07 — Percolator (incremental indexing) [S]  
L4.PAP.08 — Dremel / columnar analytics [S]  
L4.PAP.09 — RDD / Spark [S]  
L4.PAP.10 — FaRM / RDMA‑based systems [S]


#### 4.2. AI/ML in Architecture

L4.AI.01 — RAG architectures: retrieval‑augmented generation basics [E]  
L4.AI.02 — Vector databases: HNSW, IVF, PQ, ANN search surveys [S]  
L4.AI.03 — LLMOps vs MLOps: lifecycle, monitoring, evaluation [E]  
L4.AI.04 — Federated Learning fundamentals, FedAvg [E]  
L4.AI.05 — ML platform case studies (Uber Michelangelo, TFX) [P]  
L4.AI.06 — Privacy‑preserving ML (differential privacy, secure aggregation) [A]  
L4.AI.07 — Serving LLMs at scale: KV‑cache sharding, tensor/sequence parallelism [A]  
L4.AI.08 — Online learning, bandits, recommendation systems infra [A]  
L4.AI.09 — AI‑assisted ops (anomaly detection, auto‑remediation) [A]  
L4.AI.10 — NeurIPS/OSDI/NSDI современные работы по DS+ML [S]

#### 4.3. Hardware Trends

L4.HW.01 — NVMe, NVMe‑oF, storage class memory [A]  
L4.HW.02 — GPU/TPU acceleration, heterogeneous compute [A]  
L4.HW.03 — FPGA usage in datacenters (network offload, acceleration) [A]  
L4.HW.04 — RDMA, SmartNICs, DPU‑архитектуры [A]  
L4.HW.05 — Energy‑aware computing, carbon‑aware scheduling [A]

#### 4.4. Cloud‑Native Research

L4.CLOUD.01 — Unikernels, MirageOS, OSv [A]  
L4.CLOUD.02 — WebAssembly (Wasm) в backend (Spin, wasmCloud) [A]  
L4.CLOUD.03 — eBPF‑based service meshes, sidecarless designs [A]  
L4.CLOUD.04 — Serverless platforms на базе microVM (Firecracker) [A]  
L4.CLOUD.05 — Multi‑cluster / multi‑cloud orchestration (KubeFed, GitOps) [A]

#### 4.5. Quantum & Post‑Quantum

L4.QC.01 — Основы квантовых вычислений (кубиты, суперпозиция, отложенный риск) [A]  
L4.QC.02 — Угроза для RSA/ECC, “harvest now, decrypt later” [A]  
L4.QC.03 — NIST PQC стандарты (CRYSTALS‑Kyber, Dilithium, HQC) [A]  
L4.QC.04 — Crypto‑agility и миграционные стратегии [A]  
L4.QC.05 — Архитектурные решения для PQC (hybrid key exchange, TLS upgrade) [A]
#### 4.6. Emerging Paradigms & Sustainability

L4.SUST.01 — Green Software Engineering: SCI (Software Carbon Intensity) specification [P]
L4.SUST.02 — Power-aware scheduling in K8s (Kepler) [A]
L4.LANG.01 — Rust in Infrastructure: Memory safety guarantees, affine types impact on system design [A]
L4.LANG.02 — Structured Concurrency (Project Loom, Swift concurrency) theoretical implications [E]