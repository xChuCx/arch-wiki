# L2. System Design, Database Engineering & Resilience
<!-- @id: l2-architecture -->

## Resilience Engineering: Circuit Breaker, Bulkhead & Jittered Retry
<!-- @id: l2-resilience-circuit-breaker-jitter -->
- **The Order of Operations**: To avoid cascading failure, resilient network invocations must follow the strict execution sequence:
  ```text
  Bulkhead (Isolation) -> Circuit Breaker (Protection) -> Rate Limiter (Throttling) -> Retry (Recovery) -> Network Transport
  ```
- **Jitter Algorithms**:
  - *Naive Exponential Backoff*: $t = \min(t_{\max}, t_{\text{base}} \cdot 2^i)$. Causes synchronized thundering herds.
  - *Full Jitter*: $t_{\text{sleep}} = \text{random}(0, t)$. Decouples retry spikes across workers.
  - *Decorrelated Jitter*: $t_{\text{sleep}} = \min(t_{\max}, \text{random}(t_{\text{base}}, 3 \cdot t_{\text{prev}}))$. Smooths queue load across high-concurrency client fleets.
- **Bulkhead Pattern**: Isolates resources into separate pools (thread pools or semaphores) so that a failure or slowdown in one integration point (e.g. billing) cannot starve worker threads required for core operations.

## Database Storage Engines & Transaction Isolation
<!-- @id: l2-database-engines-isolation -->
- **Write-Ahead Logging (WAL)**: All state changes must append sequentially to durable disk before in-memory data structures (memtable/buffer pool) are mutated. Guarantees Atomicity and Durability across power failures.
- **B-Tree vs LSM-Tree**:
  - *B-Tree (InnoDB, Postgres)*: High read performance ($O(\log N)$ in-place pages), random write amplification.
  - *LSM-Tree (RocksDB, Cassandra)*: Sequential append-only writes via Memtable and CommitLog, background compaction (SSTables), optimized for high write throughput with Bloom filters to accelerate point reads.
- **Isolation Anomalies**: Read Uncommitted (Dirty Reads) $\rightarrow$ Read Committed (Non-repeatable Reads) $\rightarrow$ Repeatable Read (Phantom Reads) $\rightarrow$ Serializable (Write Skew). Multi-Version Concurrency Control (MVCC) provides snapshot isolation without read locks.

## Idempotency Keys & Deduplication Lifecycle
<!-- @id: l2-api-idempotency-keys -->
- **Two-Phase Idempotency Lifecycle**:
  1. *Acquisition*: Client sends unique `Idempotency-Key: <UUID>`. Server attempts atomic insertion (`INSERT INTO idempotency_keys ... ON CONFLICT DO NOTHING`). If status is `PROCESSING`, reject concurrent retry with `409 Conflict`.
  2. *Execution & Settlement*: Business mutation executes within database transaction.
  3. *Caching & Response*: Response payload and HTTP status are committed alongside transaction. Subsequent retries with identical key return cached response directly without re-executing business logic.
