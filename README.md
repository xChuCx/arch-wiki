# Architecture Wiki (`arch-wiki`)

> **Comprehensive Knowledge Base & Reference Repository for High-Scale Systems Architecture, Distributed Systems Theory, and Engineering Governance.**

`arch-wiki` is a standalone, pluggable architecture knowledge base engineered for both human Staff/Principal engineers and autonomous AI coding agents. It unifies **165 production-grade technical articles** (12.4 MB of deep technical text, formal proofs, code examples, and architecture diagrams) under a rigorous **4-Layer Taxonomy**.

---

## 🏛 The 4-Layer Taxonomy

To prevent recurring disputes ("re-discovering 2010 textbooks" vs "swarm-specific novelties"), all architectural knowledge in this repository is strictly organized into four epistemic tiers:

```
┌────────────────────────────────────────────────────────────────────────┐
│ L4. THE FRONTIER                                                       │
│ AI/LLM Systems, Vector DBs, Edge & WASM, Confidential Computing        │
├────────────────────────────────────────────────────────────────────────┤
│ L3. GOVERNANCE, PROCESSES & SRE                                        │
│ Architecture Decision Records (ADR), Fitness Functions, SLOs, Runbooks │
├────────────────────────────────────────────────────────────────────────┤
│ L2. SYSTEM DESIGN & ARCHITECTURE                                       │
│ EDA, DB Internals, MVCC, CDC, Sharding, Caching, Fault Tolerance, DDD  │
├────────────────────────────────────────────────────────────────────────┤
│ L1. FOUNDATIONS (Computer Science & Physics)                           │
│ Algorithms, OS Kernel, TCP/QUIC, Memory Models, Concurrency, DST       │
└────────────────────────────────────────────────────────────────────────┘
```

1. **L1. Foundations (Фундаментальные основы):**
   - Computer Science & Complexity, Hardware & Storage physics, OS Kernel (Linux, VFS, eBPF, memory allocators), Networking (TCP, QUIC, TLS 1.3), Concurrency (lock-free, JMM), and Distributed Systems Theory (CAP, PACELC, Consensus, Raft, Paxos, Vector Clocks).
   - *Epistemic Status:* Canonical / Textbook foundations. Cited from primary RFCs and formal specifications.
2. **L2. System Design & Architecture (Паттерны и устойчивость):**
   - Production system design: Event-Driven Architecture, CQRS, Sagas, Database Engines (B-tree, LSM, WAL, MVCC), Change Data Capture (Debezium), High Availability (Sharding, Consistent Hashing, Semantic Caching, Circuit Breakers), and Strategic/Tactical DDD.
   - *Epistemic Status:* Requires concrete adversary models (`catches / cannot catch`) and reproducible failure modes.
3. **L3. Governance, Processes & SRE (Процессы и надзор):**
   - Architectural Fitness Functions, Architecture Decision Records (ADRs), Team Topologies, SLO/SLI budgets, and change management.
4. **L4. The Frontier (Академический фронтир и AI):**
   - LLM & RAG architectures, Vector indexing (HNSW, IVF), KV-cache optimization, Cloud-Native microVMs (Firecracker), and WebAssembly.

---

## ⚡ Two-Tier Retrieval Architecture

When autonomous agents or developer workstations integrate `arch-wiki`, they face a fundamental trade-off: **context window capacity vs. exhaustiveness**. Ingesting 12.4 MB on every task guarantees context compaction amnesia and runaway token costs. 

`arch-wiki` implements a **Two-Tier Retrieval Architecture** via [`agent-memory`](https://github.com/xChuCx/agent-memory):

```
                     ┌───────────────────────────┐
                     │   Autonomous AI Agent     │
                     └─────────────┬─────────────┘
                                   │
              1. Search Query: "CAP PACELC consensus"
                                   │
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│ TIER 1: HIGH-DENSITY INDEX PACK (via agent-memory fetch)               │
│ - Compact Executive Summary (< 500 chars)                              │
│ - Exact Mathematical Invariants & Adversary Conditions                 │
│ - Tags & Status                                                        │
│ - Direct Pointer: [Read Full Article](file:///.../4Layers/L1.DST/...)   │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                 2. Does the task need deep dive?
                                   │
                       ┌───────────┴───────────┐
                       ▼                       ▼
                     [NO]                    [YES]
              (Work with concise       (Open full 50-page
                invariant pack)          article on-demand)
```

1. **Tier 1: Budget-Bounded Search Pack:**
   Running `agent-memory fetch "CAP theorem PACELC" --budget 1200` queries the local SQLite FTS5 shadow index. It returns the exact executive summary, key invariants, and failure modes under a tight token budget.
2. **Tier 2: On-Demand Full Context Access:**
   Every indexed section contains the exact local/repo file link `4Layers/...`. When an agent needs full implementation code, mathematical proofs, or configuration samples, it retrieves the full markdown document directly on demand.

---

## 📂 Repository Layout

```
arch-wiki/
├── 4Layers/                                # The 165 Canonical Technical Articles (12.4 MB)
│   ├── L1. Foundations/
│   │   ├── L1.CONC/                        # Concurrency, Threads, Locks, Event Loops (10 articles)
│   │   ├── L1.CS/                          # Algorithms, Complexity, Memory Allocators (19 articles)
│   │   ├── L1.DST/                         # Distributed Systems Theory, Raft, Paxos (22 articles)
│   │   ├── L1.HW/                          # CPU Caches, SSD Internals, Erasure Coding (6 articles)
│   │   ├── L1.NET/                         # OSI, TCP/IP, QUIC, TLS, HTTP/3, epoll (18 articles)
│   │   └── L1.OS/                          # Linux Kernel, VFS, Memory, CFS Scheduler (11 articles)
│   ├── L2.System Design & Architecture/
│   │   ├── L2.API/                         # Protobuf, GraphQL, OpenAPI, Idempotency (11 articles)
│   │   ├── L2.ARCH/                        # Microservices, Hexagonal, Clean, Modularity (15 articles)
│   │   ├── L2.DATA/                        # Data Modeling, Star/Snowflake, ETL, Lakehouse (5 articles)
│   │   ├── L2.DB/                          # ACID/BASE, Isolation, MVCC, LSM, B-Trees (19 articles)
│   │   ├── L2.DDD/                         # Strategic & Tactical Domain-Driven Design (2 articles)
│   │   ├── L2.INT/                         # Enterprise Integration, EIP, CDC, Debezium (2 articles)
│   │   ├── L2.MOB/                         # Offline-First, CRDT on client, BFF Patterns (3 articles)
│   │   └── L2.SCL/                         # Sharding, Consistent Hashing, Rate Limiting (22 articles)
│   └── images/                             # Architecture diagrams & schematics
├── .agent-memory/                          # Pluggable Agent Memory Store (PR3-PR5 Contract)
│   ├── meta/
│   │   ├── manifest.yaml                   # Store manifest & configuration
│   │   ├── schema.yaml                     # Category definitions & rules
│   │   └── index.sqlite                    # FTS5 shadow index
│   ├── conventions.md                      # Architecture standards & conventions
│   ├── decisions.md                        # Master Architecture Decision Records (ADRs)
│   ├── pitfalls.md                         # Production traps with falsifiers
│   ├── index.md                            # Machine-maintained routing file
│   └── modules/                            # 16 High-Density Category Modules
│       ├── l1-conc.md                      ├── l2-api.md
│       ├── l1-cs.md                        ├── l2-arch.md
│       ├── l1-dst.md                       ├── l2-data.md
│       ├── l1-hw.md                        ├── l2-db.md
│       ├── l1-net.md                       ├── l2-ddd.md
│       ├── l1-os.md                        ├── l2-int.md
│       ├── l2-mob.md                       ├── l2-scl.md
│       ├── l3-governance.md                └── l4-frontier.md
├── План Full.md                            # Master Curriculum, Syllabus & Roadmap
└── README.md                               # Project documentation
```

---

## 🚀 Connecting `arch-wiki` to Projects

To connect this architecture wiki as a landscape knowledge store in any repository using `agent-memory`:

### 1. Add the Store Reference
In your project repository:
```bash
agent-memory store add --name arch-wiki --source https://github.com/xChuCx/arch-wiki
# Or local path for development:
# agent-memory store add --name arch-wiki --source /path/to/arch-wiki
```

### 2. Synchronize & Lock
```bash
agent-memory sync
```
This clones/copies the store, validates it against PII/secrets, sandbox-verifies paths, and records the exact immutable commit SHA in `.agent-memory/meta/stores.lock`.

### 3. Rebuild Index & Fetch
```bash
agent-memory rebuild-index
agent-memory fetch "CAP PACELC consensus"
```

---

## 📜 Standards & Invariants

- **Nullius in verba (Ничьим словам на веру):** Every pattern must declare its concrete physical constraints, mathematical failure modes, and falsifiers.
- **Zero Secrets / Zero PII:** All articles and configurations pass strict Shannon-entropy and pattern scanning (`scanStoreTree`).
- **Separation of Concerns:** `agent-memory` remains a lean, universal runtime engine; `arch-wiki` is a pluggable domain knowledge repository.

---
*Maintained under the Verifiable Architecture Protocol.*
