# Architectural Pitfalls & Anti-Patterns
<!-- @id: arch-pitfalls -->

## The Metastable Death Spiral
<!-- @id: pitfall-metastable-death-spiral -->
- **Symptom**: A momentary backend latency spike (e.g. 500ms GC pause or database contention) triggers client timeouts. Clients retry without jitter or backoff, saturating thread pools and generating a self-sustaining retry storm even after the underlying cause has cleared.
- **Physical Law**: Governed by Little's Law ($L = \lambda W$). As latency $W$ increases, in-flight concurrency $L$ exhausts resources, driving Goodput to zero while CPU Throughput remains at 100%.
- **Remediation**: Circuit Breakers (fail-fast), Bulkheads (thread pool isolation), and Full/Decorrelated Jitter on all retry loops.

## The Exact-Match Caching Fallacy for LLMs
<!-- @id: pitfall-exact-match-caching -->
- **Symptom**: Applying traditional hashing (SHA-256) to natural language user prompts yields near-zero cache hit rates due to linguistic entropy ("Hello" != "hello").
- **Remediation**: Deploy Semantic Caching (`L2.SCL.05`) using dense vector embeddings and calibrated cosine similarity thresholds ($\tau \approx 0.88 - 0.92$) with exact-match L1 bypass.

## Self-Contained Testing Against Wrong Adversary
<!-- @id: pitfall-wrong-adversary-testing -->
- **Symptom**: An agent designs a test running concurrent internal threads and claims the pattern is proven, when the real production adversary is an external OS scanner holding a handle for 2 seconds.
- **Rule**: Executed evidence testing the wrong adversary is confidently wrong evidence. Always explicitly document `adversary: (catches / cannot catch)`.
