# Governance Model

This concise model is a public review aid. The normative acceptance criteria and architecture contracts remain in [`requirements.md`](requirements.md) and [`architecture-handoff.md`](architecture-handoff.md).

## Lifecycle

A governed Work Package proceeds through these semantic phases:

1. **Declare** — receive the bounded request, requested outcome, complete authority/scope/ownership inputs, completion-condition declaration, relations, and provenance declarations.
2. **Identity** — bind exactly one stable Work Package Identity and lifecycle version. For an admitted actual execution intent, allocate exactly one unique, non-reusable Attempt Identity.
3. **Validate** — evaluate the complete applicable Validation Set, including negative, contradictory, stale, and unverifiable findings.
4. **Baseline** — capture accepted authority, Scope Boundary, Semantic Owner, identity/version, policy references, acceptance provenance, and integrity references immutably.
5. **Admit or block** — produce one attributable decision for the exact boundary, or a named Blocking State. `HUMAN_DECISION_REQUIRED` is a block, never permission.
6. **Observe/change** — compare attributable observations with the accepted baseline and append immutable Change Records for material differences.
7. **Re-evaluate** — after an affecting change or valid block resolution, run a fresh complete evaluation against current authority. Never resume by inference.
8. **Complete or block** — accept completion only when every declared condition has current, sufficient, exact-identity-bound Evidence Artifacts and complete provenance.
9. **Record** — preserve one immutable Governance_Record / Decision Record for each governed outcome.

## Boundary rules

- A block withholds the named outcome and every dependent outcome.
- If a shared authority, scope, baseline, identity, or concurrency condition is affected, freeze the affected dependency graph while preserving unrelated valid boundaries.
- Resolution is attributable and linked to the original block; resolution alone does not restore permission.
- A failed preservation of identity, block, outcome, or record is itself fail-closed and retains the prior safe state.
- Validation, inspection, and replay preserve identity and prior attempt references without allocating an attempt. A retry, rerun, or new actual execution receives a new Attempt Identity.

## Implementation-entry gate checklist

Before mechanism-specific work begins, confirm all of the following:

- applicable ADRs exist, are accepted, non-conflicting, and have immutable history;
- each selected decision traces to requirements/properties and an affected boundary;
- authority, provenance, ownership, identity, lifecycle, and policy references are complete;
- exact Work Package / Attempt binding is defined and verifiable;
- preservation, blocking, fresh evaluation, and unrelated-work isolation are demonstrated;
- no future option has been presented as delivered capability.

If any item is unresolved, classify the proposal as a future option or create a named block. Do not infer approval from repository convention, prior approval, timing, or an implementation document.
