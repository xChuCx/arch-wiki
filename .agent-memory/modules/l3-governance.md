# L3. Governance, Processes, Leadership & SRE
<!-- @id: l3-governance -->

## Architectural Fitness Functions & Review Gates
<!-- @id: l3-fitness-functions-code-review -->
- **Definition**: An architectural fitness function provides an objective, automated integrity assessment of an architectural characteristic (layering purity, cyclic dependency absence, test coverage floors, latency budgets).
- **Merge-Decision Code Review Gate**:
  Autonomous code review prompts must evaluate PR diffs strictly on a three-tier hierarchy:
  1. *Task Deviations*: Scope narrowing, omitted acceptance criteria, or unrequested scope creep.
  2. *Architectural Invariants*: Domain logic importing infrastructure, circular module dependencies, unmanaged mutable global state, duplicated mechanisms.
  3. *Runtime Correctness*: Race conditions, missing locks, unhandled error paths, metastable loops.
  - *Strict Negative Invariant*: Zero tolerance for style, naming, docstring presence, or linter-catchable items. Any non-fatal comment that would not alter a Senior/Staff merge decision must be self-pruned.

## Operational Excellence, SLOs & Error Budgets
<!-- @id: l3-sre-error-budgets -->
- **Service Level Objectives (SLOs)**: Target reliability metric (e.g. 99.9% successful responses under 200ms) derived from user happiness, not internal infrastructure capability.
- **Error Budget Policy**: Governs the trade-off between velocity and reliability. When an error budget is depleted ($> 0.1\%$ failures within rolling 30-day window), all feature deployments freeze, and engineering capacity shifts exclusively to resilience, automated testing, and technical debt reduction.
- **Blameless Post-Mortems**: Focus on systemic contributing causes rather than individual human/agent error. Action items must be tracked as prioritized engineering tickets with assigned owners.
