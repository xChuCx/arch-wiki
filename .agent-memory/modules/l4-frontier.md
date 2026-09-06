# L4. The Frontier: AI Systems, Vector Search & Cloud-Native
<!-- @id: l4-frontier -->

## Semantic Caching & Latency Arbitrage for LLMs
<!-- @id: l4-semantic-caching-vector-search -->
- **Latency & Cost Arbitrage**: Autoregressive LLM generation requires GPU-bound inference taking 2–10 seconds. Vector similarity search over an existing embedding space executes in 5–20 milliseconds on standard CPU/RAM.
- **Cosine Threshold Calibration ($\tau$)**:
  - Distance: $\text{similarity}(\vec{u}, \vec{v}) = \frac{\vec{u} \cdot \vec{v}}{\|\vec{u}\| \|\vec{v}\|}$.
  - Threshold $\tau \ge 0.92$: Conservative exact synonymy. Zero false positives, lower hit rate.
  - Threshold $0.86 \le \tau < 0.92$: Optimal semantic match for conversational user queries.
  - Threshold $\tau < 0.85$: High danger of semantic collisions (e.g. confusing "Apple stock" with "apple fruit").
- **Two-Tier Cache Hierarchy**:
  - *Tier 1 (L1)*: In-memory exact-match hash table (SHA-256) for deterministic repeated queries ($O(1)$ lookup, 0.1ms).
  - *Tier 2 (L2)*: Vector similarity engine (HNSW / Flat cosine) with pre-filtering on scope/domain tags.

## Foundational Distributed Systems Papers
<!-- @id: l4-foundational-whitepapers -->
- **Google Spanner (2012)**: Globally distributed NewSQL database providing external consistency (linearizability) across datacenters at scale using TrueTime (atomic clocks + GPS receivers with bounded uncertainty $\epsilon$).
- **Amazon Dynamo (2007)**: High-availability leaderless key-value storage utilizing consistent hashing, vector clocks, sloppy quorums, and anti-entropy with Merkle trees.
- **Google BigTable & GFS (2003-2006)**: The foundation of distributed tabular data and chunked file storage, decoupling compute from storage.
