# Agentic SDLC Governance Core

**Version:** `1.0.0`  
**Status:** Architecture Handoff / documentation-only release

The Agentic SDLC Governance Core is a technology-neutral, fail-closed governance capability for agentic SDLC **Work Packages**. It makes work admissible, attributable, bounded, auditable, concurrency-aware, and completion-ready only when declared authority, scope, ownership, identity, baseline, policy, provenance, and evidence can be verified together.

This repository is a reusable governance reference. It contains no application code, runtime wiring, provider integration, persistence implementation, deployment mechanism, UI, or technology-specific dependency.

## Core vocabulary

- **Work Package Identity** — the stable identity and lifecycle-version binding for one bounded unit of work. In the normative source vocabulary this is `Work_Package_Identity`.
- **Run Identity** — a review-facing name for the identity of one actual execution run. It is represented by the normative `Attempt_Identity`; it does not create a second identity system.
- **Attempt Identity** — the unique, non-reusable identity of one actual execution attempt, bound to exactly one parent Work Package Identity and lifecycle version. Validation, inspection, and replay do not allocate one; retry, rerun, or new actual execution does.
- **Evidence Artifact** — a review-facing artifact carrying an attributable `Evidence_Record`. It must be current, sufficient, identity-bound, baseline-bound, and provenance-complete; a completion claim is not evidence.
- **Decision Record** — the review-facing decision form of an immutable `Governance_Record`. It retains decision status, stable reason, authority, provenance, identity/boundary, baseline, policy, and related-record references; it is not duplicate business logic.
- **`HUMAN_DECISION_REQUIRED`** — an explicit non-success blocking status used when the declared authority or resolution requires a human decision. It never authorizes execution, progression, readiness, or completion.
- **Implementation-entry gate** — no implementation, adapter, parser, storage, integration, or runtime mechanism may begin until applicable ADRs are accepted and non-conflicting, requirement/property traceability is recorded, required authority and provenance are complete, and boundary approval is accepted.

## Non-negotiable invariants

1. Complete validation precedes every finalized decision.
2. Missing, ambiguous, contradictory, stale, or unverifiable inputs fail closed.
3. No fact is inferred from omission, convention, timing, process identity, collection order, or a completion claim.
4. Accepted authority and baseline facts are immutable; material differences become linked `Change_Record` entries or new versions.
5. Every material input and outcome has complete provenance and an exact Work Package Identity or governed boundary.
6. Every governance meaning has exactly one attributable `Semantic_Owner`; composition references existing meaning instead of duplicating it.
7. Completion requires current, sufficient, attributable Evidence Artifacts for every declared condition.
8. Rejected, blocked, quarantined, and `HUMAN_DECISION_REQUIRED` outcomes never authorize work.
9. A stable Work Package Identity is the parent of each actual run; every attempt has one unique, non-reusable Attempt Identity.
10. Equivalent authoritative inputs produce equivalent decisions, bindings, reasons, boundaries, and records.
11. Declared concurrency relations govern overlap, conflict, ordering, serialization, waiting, and independence; timing never invents a relation.
12. Affected-scope blocks preserve unrelated valid work and the last prior safe state.
13. Later artifact representations must round-trip without loss of governed meaning, authority, provenance, identity, lifecycle, or status.

## Repository contents

- [`docs/requirements.md`](docs/requirements.md) — public requirements and acceptance criteria.
- [`docs/architecture-handoff.md`](docs/architecture-handoff.md) — logical architecture, lifecycle, semantic records, ownership, blocking, identity, concurrency, ADR, and future-boundary contracts.
- [`docs/verification-matrix.md`](docs/verification-matrix.md) — clause-level traceability and verification classifications.
- [`docs/governance-model.md`](docs/governance-model.md) — concise implementation-neutral operating model and review checklist.
- [`schemas/`](schemas/) — illustrative JSON Schema representations of semantic records; schemas do not select storage or runtime mechanisms.
- [`templates/`](templates/) — review templates for Work Packages, Decision Records, ADRs, and blocking states.
- [`examples/`](examples/) — finite, non-authoritative examples showing admitted, blocked, replayed, and retried work.
- [`.github/workflows/markdown-validation.yml`](.github/workflows/markdown-validation.yml) — documentation-only markdown validation.

## Review and implementation boundary

This release is a handoff, not an implementation. A later proposal must preserve the semantic owner, authority, provenance, version, lifecycle, identity, governed boundary, and immutable history of every artifact. It must pass the **Implementation-entry gate** and an applicable accepted ADR before mechanism-specific work begins.

Open decisions include identity derivation and representation, attempt allocation, persistence, storage, parser/serializer, test tooling, adapters, APIs, authorization exposure, deployment, observability, recovery mechanisms, and provider/model selection. Repository paths in this publication are documentation layout, not frozen runtime architecture.

## License

Released under the MIT License. See [`LICENSE`](LICENSE).