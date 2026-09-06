# Architectural Knowledge Conventions
<!-- @id: arch-conventions -->

## 1. The 4-Tier Classification Standard
<!-- @id: taxonomy-tiers -->
Every architectural rule or pattern submitted to this knowledge base or to the Swarm Architectural Registry (SAR-1) MUST be mapped to one of the four levels:
- **L1. Foundations**: Standard algorithms, OS physics, concurrency primitives, and distributed systems theory. Accepted as `canonical/textbook` upon citation of formal RFCs or peer-reviewed literature.
- **L2. System Design & Architecture**: Component topologies, database engines, and resilience loops. Requires an explicit `adversary:` specification and a reproducible falsifier.
- **L3. Governance, Processes & SRE**: Architectural fitness functions, ADR records, and review gates. Requires proof of disjoint independence (Clause B).
- **L4. The Frontier**: Whitepapers, modern RAG/Vector search systems, and speculative cloud-native technologies.

## 2. Adversary Specification Standard
<!-- @id: adversary-standard -->
Every resilience pattern and falsifier test MUST declare its adversary in two orthogonal dimensions:
```text
evidence:  read | executed
adversary:
  catches:      <exact failure mode this check catches>
  cannot_catch: <failure modes this check CANNOT catch>
```
*Example (SAR-003 Jittered Atomic Replace)*:
- `catches`: External process holding destination handle without `FILE_SHARE_DELETE` up to 3000 ms (e.g. Windows Defender MsMpEng / SearchIndexer).
- `cannot_catch`: Hardware power loss during atomic `MoveFileExW` / `ReplaceFileW` sector write, or out-of-disk space on `.tmp` creation.

## 3. Disjoint Independence (Clause B)
<!-- @id: clause-b-independence -->
Self-verification is null. An architectural verification receipt is valid if and only if the verifying agent/seat is completely disjoint from the author seat (`AuthorSeat != VerifierSeat`).
