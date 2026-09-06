# Architecture Wiki (`arch-wiki`)
<!-- @id: arch-wiki-overview -->

> **Open Systems Architecture Knowledge Base & Landscape Store for AI Agents**

`arch-wiki` is a decoupled, federated architecture knowledge repository structured according to the **4-Level Systems Architecture Taxonomy**. It serves both human engineers and autonomous AI agents (via the `agent-memory` landscape store protocol).

---

## 1. The 4-Level Architecture Taxonomy (L1–L4)

All architectural patterns, invariants, and failure modes are categorized into four hierarchical tiers:

```
┌─────────────────────────────────────────────────────────────┐
│ L4. THE FRONTIER                                            │
│ Foundational Whitepapers, RAG & Vector DBs, Cloud-Native, PQC│
├─────────────────────────────────────────────────────────────┤
│ L3. GOVERNANCE, PROCESSES & SRE                             │
│ Fitness Functions, ADRs, SLO/Error Budgets, Code-Review Gate│
├─────────────────────────────────────────────────────────────┤
│ L2. SYSTEM DESIGN & ARCHITECTURE                            │
│ EDA/CQRS, DDD, API Idempotency, WAL/MVCC, Resilient Jitter  │
├─────────────────────────────────────────────────────────────┤
│ L1. FOUNDATIONS                                             │
│ CS Algorithms, OS Physics, Concurrency (CAS), DST Consensus │
└─────────────────────────────────────────────────────────────┘
```

1. **L1. Foundations**: Core computer science, operating system physics (VFS, page cache, eBPF), concurrency memory models (JMM, CAS, lock-free), and distributed systems theory (CAP/PACELC, vector clocks, Raft, Byzantine fault tolerance, CRDTs).
2. **L2. System Design & Architecture**: High-level patterns (Hexagonal, Event-Driven Architecture, CQRS), tactical/strategic Domain-Driven Design, API design (two-phase idempotency keys, Sagas), database engines (WAL, MVCC, B-tree vs LSM), and resilience patterns (Little's Law, Semantic Caching, Circuit Breakers, Exponential Backoff with Jitter, Bulkhead).
3. **L3. Governance, Processes & SRE**: Automated Architectural Fitness Functions, Architecture Decision Records (ADR), Team Topologies, SLO/SLI error budgets, and merge-decision code review gates.
4. **L4. The Frontier**: Foundational whitepapers (GFS, Spanner, BigTable, ZooKeeper), LLM system architectures (HNSW/IVF vector search, KV-cache sharding), and modern cloud-native virtualization.

---

## 2. Pluggable Landscape Store Contract (`agent-memory`)

`arch-wiki` is designed to be consumed by autonomous agents using the [`agent-memory`](https://github.com/xChuCx/agent-memory) engine without polluting the core runtime binary.

### A. Connecting this Wiki to any Repository

In any project managed by `agent-memory`, declare this repository as a referenced landscape store:

```bash
# Reference via Git URL or local directory
agent-memory store add --name arch-wiki --source https://github.com/xChuCx/arch-wiki --revision main

# Or in a local development workspace:
agent-memory store add --name arch-wiki --source /path/to/arch-wiki

# Materialize and lock into local cache:
agent-memory sync
```

### B. Querying Architectural Knowledge

Once synced, queries made via MCP (`memory.fetch_context`) or CLI search across both local memory and the federated architecture wiki:

```bash
# Query resilience and retry mechanics
agent-memory fetch "metastable failure retry jitter"

# Query AI memory and vector retrieval patterns
agent-memory fetch "semantic caching cosine similarity"

# Query consensus and verifiable receipts
agent-memory fetch "Clause B disjoint seat consensus"
```

### C. Creating Your Own Domain Wiki

Any team can author a custom domain wiki following this exact contract:
1. Initialize scaffold: `agent-memory init --name <my-wiki>`
2. Populate `.agent-memory/conventions.md`, `decisions.md`, `pitfalls.md`, and `modules/*.md` with markdown sections anchored by `<!-- @id:slug -->`.
3. Commit to Git and reference via `agent-memory store add`.
