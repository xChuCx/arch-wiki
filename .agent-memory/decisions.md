# Architectural Decisions & Invariants
<!-- @id: arch-decisions -->

## SAR-001: Keyset Pagination over OFFSET
<!-- @id: sar-001-keyset-pagination -->
- **Classification**: L1.Foundations (`canonical / textbook-consensus`).
- **Context**: Autonomous agents querying linear feeds via `OFFSET n LIMIT m` experience $O(n)$ scanning overhead and pagination drift when new items are inserted during pagination.
- **Decision**: All swarm feed and activity APIs must enforce keyset pagination:
  ```sql
  WHERE (seq, id) < (:cur_seq, :cur_id) ORDER BY seq DESC, id DESC LIMIT :limit
  ```
- **Consequences**: Deterministic $O(\log N)$ index seeking, zero skipped items, zero duplicate items on concurrent appends.

## SAR-002: Deterministic LF Normalization
<!-- @id: sar-002-crlf-normalization -->
- **Classification**: L2.Architecture (`stable / independently-reproduced`).
- **Context**: Windows platforms emit `\r\n` (CRLF) while POSIX platforms emit `\n` (LF). Content hashes calculated across platforms diverge if raw bytes are digested without line-ending normalization.
- **Decision**: All task specifications, proposals, and verification receipts must undergo uniform CRLF-to-LF conversion before SHA-256 digesting. Implemented in `internal/vtp/vtp.go` (`NormalizeLF`).

## SAR-003: Adaptive Jittered Backoff against Handle Locks
<!-- @id: sar-003-jittered-backoff -->
- **Classification**: L2.Architecture (`proposed`).
- **Context**: On Windows NT, background scanners (Windows Defender, SearchIndexer) open active files without `FILE_SHARE_DELETE`, causing atomic swap (`MoveFileExW` / `os.replace`) to fail transiently with `[WinError 5] Access is denied` for 1.5–2.5 seconds.
- **Decision**: File replacement loops must use an exponential backoff with random jitter (base 50ms, factor 1.3, ceiling 250ms, jitter ±20%) with a total budget of 3000ms. Tested and proven against a 2000ms external lock.

## SAR-004: Dual-Oracle Settlement & Clause B
<!-- @id: sar-004-dual-oracle-settlement -->
- **Classification**: L2.Architecture (`stable / codified`).
- **Context**: Trustless autonomous agents claiming bounties must not settle their own work or rely on single-seat self-attestations.
- **Decision**: Verifiable Task Protocol (VTP-1) mandates two disjoint oracles: Claimant generates `TASK-RECEIPT`; independent Verifier generates `TASK-VERIFY`. Escrow settles to `TASK-SETTLE` iff `ClaimantSeat != VerifierSeat`.

## SAR-006: Skill Evaluation & Benchmarking Contract
<!-- @id: sar-006-skill-evaluation -->
- **Classification**: L3.Governance (`codified / standard`).
- **Context**: Autonomous agent skills and capabilities frequently degrade silently across prompt or model updates without deterministic benchmarking.
- **Decision**: Every autonomous skill must define explicit capability vectors, measurable pass/fail assertions, token budgets, and reproducible canary suites.

## SAR-007: Representation & Byte-Preserving Storage Contract
<!-- @id: sar-007-representation -->
- **Classification**: L2.Architecture (`codified / standard`).
- **Context**: Formatting mutations in markdown memory files often corrupt human-authored text, strip frontmatter, or rewrite line endings.
- **Decision**: Memory stores must guarantee byte-preserving section replacements (`Splice`), preserving all untouched byte offsets, comments, and whitespace byte-identically.

## SAR-008: Grounding, Staging & Write-Skew Closure Contract
<!-- @id: sar-008-grounding-staging-write-skew -->
- **Classification**: L2.Architecture (`stable / codified in v0.6.2`).
- **Context**: Sectional CAS prevents write-write races but misses read-write races (write skew / snapshot isolation anomalies), and policy manifests can be misinterpreted if interpreter semantics drift.
- **Decision**: 
  1. Mutations require two-phase staging (`propose_update` $\to$ `apply_staged`).
  2. Staged proposals record `ReadSections` (path#section_id $\to$ content sha256). During `rebase_staged`, any drifted read-set premise blocks the rebase with `ReasonReadSkewDrift`.
  3. Proposals bind an `InterpreterDigest` preventing application if policy precedence rules or runtime versions have drifted.

## SAR-009: Sovereign Runtime Isolation & Negative Canaries Contract
<!-- @id: sar-009-runtime-isolation -->
- **Classification**: L2.Architecture (`codified / standard`).
- **Context**: Self-reported hermeticity (`VERIFIED_HERMETIC=true`) is vulnerable to runner deception and unclosed tap/socket configurations.
- **Decision**: Runtime isolation is established mechanically via Negative Canaries (Egress block `ENETUNREACH`/`EPERM`, Host Sentinel `ENOENT`, Monotonic Entropy) verified inside-out, combined with active heartbeat leases and strict environment allowlists.

## SAR-010: Unicode Normalization, Canonical Identifiers & Federated Overlays
<!-- @id: sar-010-unicode-federated-overlays -->
- **Classification**: L1.Foundations & L2.Architecture (`codified / standard`).
- **Context**: Naive SQLite `COLLATE NOCASE` and `strings.ToLower` fail on non-ASCII characters (`Straße` $\neq$ `STRASSE`), and federated stores risk namespace collisions.
- **Decision**: 
  1. Identifiers are pre-canonicalized via `FullCasefold(NFC(Trim(s)))` and stored in `COLLATE BINARY` unique indexes.
  2. Federated key collisions trigger granular quarantine (`KEY_COLLISION_QUARANTINE`) emitting cryptographic doctor/CI receipts without secret leaks.
  3. Third-party read-only stores use Local Resolution Overlays (`store_overrides.yaml`) pinned to upstream commit SHAs with fail-closed drift detection (`OVERLAY_OUTDATED_DRIFT`).
