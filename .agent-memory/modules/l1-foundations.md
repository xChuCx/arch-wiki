# L1. Foundations: Core CS, OS & Distributed Systems
<!-- @id: l1-foundations -->

## Concurrency Models & Lock-Free State
<!-- @id: l1-concurrency-cas -->
- **Memory Models**: The Java Memory Model (JMM) and Go memory model establish *happens-before* relationships to guarantee visibility across hardware CPU caches (MESI protocol).
- **Compare-And-Swap (CAS)**: Atomic hardware primitive (`CMPXCHG`) enabling non-blocking state transitions. Avoids thread suspension overhead.
- **The ABA Problem**: In lock-free stacks/queues, a memory address modified from A to B and back to A fools a naive CAS. Resolved via versioned pointers (tagged pointers) or generation counters.
- **False Sharing**: Multiple independent threads modifying distinct variables located on the identical 64-byte CPU cache line, triggering cache line invalidation ping-pong. Remediation: cache line padding (`@Contended` or 64-byte struct padding).

## Distributed Systems Theory & Consensus
<!-- @id: l1-distributed-consensus -->
- **CAP & PACELC Theorems**: In the presence of a network partition (P), choose between Availability (A) and Consistency (C); else (E), choose between Latency (L) and Consistency (C).
- **Logical Clocks**: Lamport timestamps establish partial order; Vector Clocks capture causality and detect concurrent updates.
- **Consensus Protocols**:
  - Paxos / Multi-Paxos: Single and multi-decree consensus with leader leases.
  - Raft: Understandable consensus utilizing strong leader election, log matching invariants, and joint consensus membership changes.
  - Byzantine Fault Tolerance (BFT): PBFT guarantees safety with $3f + 1$ nodes resisting up to $f$ malicious or arbitrary Byzantine failures.
- **Conflict-Free Replicated Data Types (CRDTs)**:
  - State-based (CvRDT): Merge via monotonic semilattice join (LWW-Element-Set, OR-Set).
  - Operation-based (CmRDT): Reliable broadcast of commutative operations (G-Counter, PN-Counter).
- **Deterministic Simulation Testing (DST)**: FoundationDB methodology: executing distributed systems within a deterministic pseudo-random time and network simulator to catch 1-in-a-billion split-brain and crash-recovery bugs before production.
