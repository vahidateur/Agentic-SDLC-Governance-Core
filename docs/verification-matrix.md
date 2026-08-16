
> **Public documentation:** This document is a technology-neutral, reusable publication of the Agentic SDLC Governance Core v1.0.0 handoff. It defines governance semantics and review obligations; it does not authorize application implementation.

# Requirements-to-Handoff / Property Verification Matrix

**Feature:** `agentic-sdlc-governance-core`  
**Handoff:** Architecture Handoff v1.0  
**Authority:** [`requirements.md`](./requirements.md)  
**Design:** [`design.md`](./architecture-handoff.md)  
**Purpose:** Clause-level traceability for task 1.3. Every acceptance criterion in Requirements 1–17 appears exactly once below and has at least one handoff/semantic or verification classification.

## Coverage rules

- Requirement references use the `Requirement.AcceptanceCriterion` form (`1.1` through `17.5`).
- `P#` always means the numbered correctness property in `design.md`; property names and exact `Validates: Requirements ...` lines are reproduced in the property register below.
- `EX#` is a finite example/unit check, `F#` is an edge/fault or preservation check, `I#` is a later integration check gated by the applicable ADR, and `SM#` is a handoff smoke/traceability/isolation check.
- A dash means that verification class is not the primary classification for that clause; the row is still covered by another listed classification.
- `Covered` means the clause has a handoff section or semantic rule plus at least one reviewable verification classification. No clause is intentionally left unclassified.

## Verification check catalog

| ID | Classification | Check | Scope / gate |
|---|---|---|---|
| EX-01 | Example/unit | Handoff wording and finite classification | v1.0 metadata, purpose/problem, mandatory sections, examples/observations/proposals/non-goals/future boundaries |
| EX-02 | Example/unit | Finite governance cases | Missing completion conditions, unsupported claims, nonexistent block resolution, invalid relations, unapproved mechanisms, non-success outcomes |
| F-01 | Edge/fault | Validation and evidence preservation | Missing/ambiguous/contradictory/stale/unverifiable authority, provenance, baseline, policy, or evidence; no partial outcome; prior-safe-state preservation |
| F-02 | Edge/fault | Blocking/change/record preservation | Change attribution, block activation/resolution, affected-scope freezing, immutable-record failure, halt, and unrelated-work preservation |
| F-03 | Edge/fault | Hybrid identity failure | Identity assignment, Attempt_Identity allocation/binding/uniqueness/non-reuse, lifecycle mismatch, and fail-closed preservation |
| F-04 | Edge/fault | ADR history and entry gate | Missing/conflicting/unaccepted ADR, immutable original, linked successor, atomic supersession, and implementation halt |
| F-05 | Edge/fault | Lossless artifact recovery | Malformed/lossy parse/print/recovery and preservation of governed meaning and references |
| F-06 | Edge/fault | Ownership and repository placement | Duplicate owner, boundary conflict, metadata loss, duplicate semantic meaning, and safe placement |
| I-01 | Integration | Later governed adapters | Authoritative source, evidence/validity, immutable record, identity, and concurrency adapters; only after applicable ADR acceptance |
| I-02 | Integration | Later exposure/authorization boundary | API/CLI/UI/authorization integration; only after applicable ADR acceptance; no partial/non-success authorization |
| SM-01 | Smoke | Handoff metadata/readiness | Version, feature, Requirements Freeze, mandatory sections, logical repository areas, non-goals, and readiness markers |
| SM-02 | Smoke | Requirement/property traceability | Every clause classified; every selected decision/property traces to requirements; hybrid identity included |
| SM-03 | Smoke | Approved-boundary isolation | No application code, unrelated spec, protected task, runtime record, Git-state, or unrelated ownership changes |
| SM-04 | Smoke | ADR/future-boundary gate | Open decisions remain open; no mechanism is admitted without applicable accepted ADR and boundary approval |

## Semantic rule register

| ID | Handoff semantic rule | Primary design section |
|---|---|---|
| SR-01 | Complete validation fails closed and withholds dependent outcomes. | Core Principles — Fail Closed; Decision Lifecycle |
| SR-02 | Declared authoritative facts only; no inference from omission, order, timing, process identity, or claims. | Core Principles — No Inference |
| SR-03 | Accepted authority/baseline facts are immutable; differences become linked records or versions. | Core Principles — Immutable Authority |
| SR-04 | Provenance is complete, attributable, integrity-bound, and part of meaning. | Core Principles — Provenance Is Part of Meaning |
| SR-05 | Admission is exact, attributable, identity-bound, and bounded by accepted inputs. | Components and Interfaces — Execution Admission |
| SR-06 | Scope dimensions and exactly one Semantic_Owner are explicit; composition reuses rather than duplicates meaning. | Scope & Ownership Control; Semantic Ownership and Boundary Composition Rules |
| SR-07 | Material changes are captured, impact-classified, and freshly re-evaluated; unrelated valid state is preserved. | Change Capture; Decision Lifecycle |
| SR-08 | Completion requires explicit conditions and current, sufficient, exactly bound evidence. | Completion Model |
| SR-09 | Named blocking states withhold outcomes; attributable resolution requires fresh evaluation; preservation failure halts. | Blocking State Model |
| SR-10 | Stable Work_Package_Identity is the parent; actual attempts receive unique non-reusable Attempt_Identity values. | Work Package Identity Rules |
| SR-11 | Declared concurrency relations govern overlap, independence, waiting, ordering, and serialization; inference is forbidden. | Admission Concurrency Rules |
| SR-12 | Every governed outcome has one complete immutable, replayable Governance_Record. | Governance Records / record contract |
| SR-13 | Boundary-affecting decisions require immutable ADR history and an accepted entry gate. | ADR rules / Future Decision Register |
| SR-14 | Logical placement preserves owner, provenance, version, lifecycle, identity, and boundary relationships. | Repository structure boundary |
| SR-15 | Handoff scope is isolated; excluded/future mechanisms are not implementation commitments. | Scope and Classification Verification Register; non-goals |
| SR-16 | Equivalent authoritative inputs produce equivalent governed results. | Core Principles — Deterministic Evaluation |
| SR-17 | Accepted artifact representation is lossless through parse/print/recovery. | Property-Based Testing Tooling and Generator ADR Prerequisite |
| SR-18 | Rejected, blocked, and quarantined outcomes never authorize work. | Core Principles — Fail Closed; Error Handling |

## Numbered correctness-property register

The following names and requirement traces are copied from `design.md`; they are the fixed property numbers used in the matrix.

| Property | Name | Exact design requirement trace |
|---|---|---|
| P1 | Complete validation fails closed | **Validates: Requirements 2.1, 2.2, 2.3, 2.5, 16.1, 16.7, 16.11** |
| P2 | Provenance is complete and deterministic | **Validates: Requirements 3.1, 3.2, 3.3, 3.4, 3.5, 16.3, 16.4** |
| P3 | Admission is exact, attributable, and bounded | **Validates: Requirements 4.1, 4.2, 4.3, 4.4, 4.5** |
| P4 | Accepted facts remain immutable and differences are captured | **Validates: Requirements 2.4, 5.1, 5.2, 5.3, 5.4, 5.5, 7.1, 7.2, 7.3, 16.2** |
| P5 | Change impact is re-evaluated without unrelated drift | **Validates: Requirements 7.4, 7.5, 16.5** |
| P6 | Scope and semantic ownership are explicit and unique | **Validates: Requirements 6.1, 6.2, 6.3, 6.4, 6.5, 16.9** |
| P7 | Completion requires current sufficient evidence | **Validates: Requirements 8.2, 8.3, 8.4, 8.6, 16.7** |
| P8 | Blocking states govern recovery explicitly | **Validates: Requirements 9.1, 9.2, 9.3, 9.4, 9.6** |
| P9 | Identity is stable, unique, and version-preserving | **Validates: Requirements 10.1, 10.3, 10.4, 10.5, 10.6, 10.8, 10.9, 10.10, 10.11, 10.12, 10.13, 16.4, 16.14, 16.15** |
| P10 | Concurrency follows declared semantics and never inference | **Validates: Requirements 11.1, 11.2, 11.3, 11.4, 11.6, 11.8, 16.5, 16.6, 16.12, 16.13** |
| P11 | Governance records are complete, immutable, and replayable | **Validates: Requirements 12.1, 12.2, 12.3, 12.5, 12.6** |
| P12 | ADR history is immutable and supersession is atomic | **Validates: Requirements 13.3, 13.5, 13.6** |
| P13 | Safe repository placement preserves governance metadata | **Validates: Requirements 14.2, 14.4** |
| P14 | Accepted artifact representation is lossless | **Validates: Requirements 16.10** |
| P15 | Non-success statuses never authorize work | **Validates: Requirements 16.8** |
## Clause matrix

### Requirements 1–5

| Clause | Handoff section / semantic rule | Property | Example/unit | Edge/fault | Integration | Smoke | Status |
|---|---|---|---|---|---|---|---|
| 1.1 | Executive Summary; SR-15 | — | EX-01 | — | — | SM-01 | Covered |
| 1.2 | Problem Statement; SR-15 | — | EX-01 | — | — | SM-01 | Covered |
| 1.3 | Scope and Classification Verification Register; SR-15 | — | EX-01 | — | — | SM-04 | Covered |
| 1.4 | Scope and Classification Verification Register; SR-15 | — | EX-01 | — | — | SM-04 | Covered |
| 2.1 | Fail Closed; Decision Lifecycle; SR-01 | P1 | — | F-01 | I-01 | SM-02 | Covered |
| 2.2 | Fail Closed; No Inference; SR-01, SR-02, SR-18 | P1 | — | F-01 | I-01 | SM-02 | Covered |
| 2.3 | No Inference; SR-02 | P1 | EX-02 | F-01 | — | SM-02 | Covered |
| 2.4 | Immutable Authority; SR-03 | P4 | — | F-01 | I-01 | SM-02 | Covered |
| 2.5 | Fail Closed; Decision Lifecycle; SR-01, SR-09 | P1, P8 | — | F-02 | I-01 | SM-02 | Covered |
| 3.1 | Provenance Is Part of Meaning; Task Execution Provenance Control; SR-04 | P2 | — | F-01 | I-01 | SM-02 | Covered |
| 3.2 | Provenance Is Part of Meaning; SR-04 | P2 | — | F-01 | I-01 | SM-02 | Covered |
| 3.3 | Task Execution Provenance Control; SR-04 | P2 | — | F-01 | I-01 | SM-02 | Covered |
| 3.4 | Deterministic Evaluation; SR-04, SR-16 | P2 | — | F-01 | I-01 | SM-02 | Covered |
| 3.5 | Provenance Is Part of Meaning; Fail Closed; SR-01, SR-04 | P1, P2 | — | F-01 | I-01 | SM-02 | Covered |
| 4.1 | Execution Admission; SR-05 | P3 | — | — | I-01 | SM-02 | Covered |
| 4.2 | Execution Admission; SR-05 | P3 | — | — | I-01 | SM-02 | Covered |
| 4.3 | Execution Admission; Fail Closed; SR-01, SR-05, SR-18 | P1, P3 | — | F-01 | I-01 | SM-02 | Covered |
| 4.4 | Execution Admission; No Inference; SR-02, SR-05, SR-18 | P3, P15 | EX-02 | F-01 | I-02 | SM-02 | Covered |
| 4.5 | Execution Admission; Provenance Is Part of Meaning; SR-04, SR-05 | P3, P2 | — | — | I-01 | SM-02 | Covered |
| 5.1 | Immutable Baseline Control; SR-03, SR-04 | P4 | — | — | I-01 | SM-02 | Covered |
| 5.2 | Immutable Baseline Control; Fail Closed; SR-01, SR-03 | P1, P4 | — | F-01 | I-01 | SM-02 | Covered |
| 5.3 | Immutable Authority; Immutable Baseline Control; SR-03 | P4 | — | F-01 | I-01 | SM-02 | Covered |
| 5.4 | Change Capture; Immutable Authority; SR-03, SR-07 | P4 | — | F-02 | I-01 | SM-02 | Covered |
| 5.5 | Immutable Baseline Control; Deterministic Evaluation; SR-04, SR-16 | P4 | — | — | I-01 | SM-02 | Covered |
### Requirements 6–10

| Clause | Handoff section / semantic rule | Property | Example/unit | Edge/fault | Integration | Smoke | Status |
|---|---|---|---|---|---|---|---|
| 6.1 | Scope & Ownership Control; SR-06 | P6 | — | — | I-01 | SM-02 | Covered |
| 6.2 | Semantic Ownership and Boundary Composition Rules; SR-06 | P6 | — | — | I-01 | SM-02 | Covered |
| 6.3 | Ownership cardinality and ownership dimensions; SR-06 | P6 | — | F-06 | I-01 | SM-02 | Covered |
| 6.4 | Scope & Ownership Control; SR-06 | P6, P3 | EX-02 | F-06 | — | SM-02 | Covered |
| 6.5 | Reference and composition contract; Composition acceptance procedure; SR-06 | P6 | — | F-06 | I-01 | SM-02 | Covered |
| 7.1 | Change Capture; SR-03, SR-07 | P4 | — | F-02 | I-01 | SM-02 | Covered |
| 7.2 | Change Capture; SR-04, SR-07 | P4 | — | F-02 | I-01 | SM-02 | Covered |
| 7.3 | Change Capture; Fail Closed; SR-01, SR-07, SR-09 | P1, P4, P8 | — | F-02 | I-01 | SM-02 | Covered |
| 7.4 | Change Capture; Decision Lifecycle; SR-07 | P5 | — | F-02 | I-01 | SM-02 | Covered |
| 7.5 | Change Capture; SR-07, SR-16 | P5 | — | — | I-01 | SM-02 | Covered |
| 8.1 | Completion Model; Blocking State Model; SR-08, SR-09 | — | EX-02 | F-01 | I-01 | SM-02 | Covered |
| 8.2 | Completion Model; SR-08 | P7 | — | — | I-01 | SM-02 | Covered |
| 8.3 | Completion Model; SR-08 | P7 | — | F-01 | I-01 | SM-02 | Covered |
| 8.4 | Completion Model; Fail Closed; SR-01, SR-08 | P1, P7 | — | F-01 | I-01 | SM-02 | Covered |
| 8.5 | Completion Model; No Inference; SR-02, SR-08, SR-18 | — | EX-02 | F-01 | I-01 | SM-02 | Covered |
| 8.6 | Completion Model; Governance Records; SR-04, SR-08, SR-12 | P7, P11 | — | — | I-01 | SM-02 | Covered |
| 9.1 | Blocking State Model; SR-09 | P8 | — | F-02 | I-01 | SM-02 | Covered |
| 9.2 | Blocking State Model; Fail Closed; SR-09, SR-18 | P8, P15 | — | F-02 | I-01 | SM-02 | Covered |
| 9.3 | Blocking State Model; preservation rule; SR-09, SR-15 | P8, P5 | — | F-02 | I-01 | SM-02 | Covered |
| 9.4 | Blocking State Model; Decision Lifecycle; SR-09 | P8 | — | F-02 | I-01 | SM-02 | Covered |
| 9.5 | Blocking State Model; SR-09 | — | EX-02 | F-02 | — | SM-02 | Covered |
| 9.6 | Blocking State Model; No Inference; SR-02, SR-09 | P8, P1 | — | F-02 | I-01 | SM-02 | Covered |
| 9.7 | Blocking State Model; Error Handling; SR-09, SR-12 | — | — | F-02 | I-01 | SM-02 | Covered |
| 10.1 | Work Package Identity Rules; SR-10 | P9 | — | F-03 | I-01 | SM-02 | Covered |
| 10.2 | Work Package Identity Rules; fail-closed identity binding; SR-01, SR-10 | — | — | F-03 | I-01 | SM-02 | Covered |
| 10.3 | Work Package Identity Rules; SR-10, SR-12 | P9 | — | — | I-01 | SM-02 | Covered |
| 10.4 | Work Package Identity Rules; SR-09, SR-10 | P9 | — | F-03 | I-01 | SM-02 | Covered |
| 10.5 | Work Package Identity Rules; Deterministic Evaluation; SR-10, SR-16 | P9 | — | — | I-01 | SM-02 | Covered |
| 10.6 | Work Package Identity Rules; lifecycle/version preservation; SR-03, SR-10 | P9 | — | F-03 | I-01 | SM-02 | Covered |
| 10.7 | Work Package Identity Rules; Blocking State Model; SR-09, SR-10 | — | — | F-03 | I-01 | SM-02 | Covered |
| 10.8 | Work Package Identity Rules; authorized hybrid identity revision; SR-10 | P9 | — | — | I-01 | SM-01, SM-02 | Covered |
| 10.9 | Exact identity and attempt binding; SR-10 | P9 | — | F-03 | I-01 | SM-02 | Covered |
| 10.10 | Work Package Identity Rules; replay non-allocation; SR-10, SR-16 | P9 | — | — | I-01 | SM-02 | Covered |
| 10.11 | Work Package Identity Rules; retry/rerun allocation; SR-10 | P9 | — | — | I-01 | SM-02 | Covered |
| 10.12 | Work Package Identity Rules; Fail Closed; SR-01, SR-09, SR-10 | P9 | — | F-03 | I-01 | SM-02 | Covered |
| 10.13 | Work Package Identity Rules; non-reuse; SR-03, SR-10 | P9 | — | F-03 | I-01 | SM-01, SM-02 | Covered |
### Requirements 11–13

| Clause | Handoff section / semantic rule | Property | Example/unit | Edge/fault | Integration | Smoke | Status |
|---|---|---|---|---|---|---|---|
| 11.1 | Admission Concurrency Rules; relation representation contract; SR-11 | P10 | — | — | I-01 | SM-02 | Covered |
| 11.2 | Admission Concurrency Rules; relation-kind acceptance criteria; SR-11 | P10 | — | — | I-01 | SM-02 | Covered |
| 11.3 | Admission Concurrency Rules; Fail Closed; SR-01, SR-11 | P1, P10 | EX-02 | F-02 | I-01 | SM-02 | Covered |
| 11.4 | Admission Concurrency Rules; Deterministic Evaluation; SR-11, SR-16 | P10 | — | — | I-01 | SM-02 | Covered |
| 11.5 | Admission Concurrency Rules; waiting-state rule; SR-11 | — | EX-02 | — | I-01 | SM-02 | Covered |
| 11.6 | Admission Concurrency Rules; preservation rule; SR-11, SR-15 | P10 | — | — | I-01 | SM-02 | Covered |
| 11.7 | Admission Concurrency Rules; relation-kind acceptance criteria; SR-01, SR-11 | — | EX-02 | F-02 | I-01 | SM-02 | Covered |
| 11.8 | Admission Concurrency Rules; SR-01, SR-11 | P10 | — | F-02 | I-01 | SM-02 | Covered |
| 12.1 | Governance Records contract; Decision Lifecycle; SR-12 | P11 | — | — | I-01 | SM-02 | Covered |
| 12.2 | Governance Records contract; Provenance Is Part of Meaning; SR-04, SR-12 | P11 | — | F-02 | I-01 | SM-02 | Covered |
| 12.3 | Governance Records contract; Fail Closed; SR-01, SR-12, SR-18 | P11, P15 | — | F-02 | I-01 | SM-02 | Covered |
| 12.4 | Governance Records contract; Error Handling; SR-09, SR-12 | — | — | F-02 | I-01 | SM-02 | Covered |
| 12.5 | Governance Records contract; Immutable Authority; SR-03, SR-12 | P11 | — | F-02 | I-01 | SM-02 | Covered |
| 12.6 | Governance Records contract; Deterministic Evaluation; SR-12, SR-16 | P11 | — | — | I-01 | SM-02 | Covered |
| 13.1 | ADR rules; Future Decision Register; SR-13 | — | EX-02 | F-04 | I-01 | SM-02, SM-04 | Covered |
| 13.2 | ADR gate; implementation-entry rule; SR-13, SR-15 | — | EX-02 | F-04 | — | SM-04 | Covered |
| 13.3 | ADR immutability and linked successor rule; SR-13 | P12 | — | F-04 | I-01 | SM-02 | Covered |
| 13.4 | ADR gate; future-boundary classification; SR-13, SR-15 | — | EX-02 | F-04 | — | SM-04 | Covered |
| 13.5 | Conflicting active ADR rule; SR-13, SR-18 | P12 | — | F-04 | I-01 | SM-02, SM-04 | Covered |
| 13.6 | Atomic supersession rule; SR-03, SR-13 | P12 | — | F-04 | I-01 | SM-02 | Covered |
### Requirements 14–17

| Clause | Handoff section / semantic rule | Property | Example/unit | Edge/fault | Integration | Smoke | Status |
|---|---|---|---|---|---|---|---|
| 14.1 | Scope and Classification Verification Register; logical repository area rule; SR-14, SR-15 | — | EX-01 | — | — | SM-01 | Covered |
| 14.2 | Repository structure boundary; SR-14 | P13 | — | F-06 | I-01 | SM-02 | Covered |
| 14.3 | Repository structure boundary; SR-14, SR-15 | — | EX-02 | F-06 | — | SM-01, SM-02 | Covered |
| 14.4 | Repository structure boundary; SR-14 | P13 | — | F-06 | I-01 | SM-02 | Covered |
| 14.5 | Non-goals and isolation boundary; SR-15 | — | — | — | — | SM-03 | Covered |
| 15.1 | Non-goals and future implementation boundaries; SR-15 | — | EX-01 | — | — | SM-04 | Covered |
| 15.2 | ADR gate; implementation-entry rule; SR-13, SR-15 | — | EX-02 | F-04 | — | SM-04 | Covered |
| 15.3 | Scope and Classification Verification Register; SR-15 | — | EX-01 | — | — | SM-01, SM-04 | Covered |
| 15.4 | Approved-boundary isolation; SR-15 | — | — | — | — | SM-03 | Covered |
| 15.5 | Scope revision and future-boundary rule; SR-13, SR-15 | — | EX-01 | F-04 | — | SM-03, SM-04 | Covered |
| 16.1 | Governance Invariant Register — no-inference/fail-closed; SR-01 | P1 | — | F-01 | I-01 | SM-02 | Covered |
| 16.2 | Governance Invariant Register — immutability/change; SR-03, SR-07 | P4 | — | F-02 | I-01 | SM-02 | Covered |
| 16.3 | Governance Invariant Register — provenance/identity binding; SR-04, SR-10 | P2 | — | F-01 | I-01 | SM-02 | Covered |
| 16.4 | Governance Invariant Register — determinism/identity; SR-10, SR-16 | P2, P9 | — | — | I-01 | SM-02 | Covered |
| 16.5 | Governance Invariant Register — independent eligibility/determinism; SR-11, SR-16 | P5, P10 | — | — | I-01 | SM-02 | Covered |
| 16.6 | Governance Invariant Register — declared concurrency; SR-11 | P10 | — | F-02 | I-01 | SM-02 | Covered |
| 16.7 | Governance Invariant Register — blocked/no partial outcome; SR-01, SR-08, SR-18 | P1, P7 | — | F-01 | I-01 | SM-02 | Covered |
| 16.8 | Governance Invariant Register — non-success never authorizes; SR-18 | P15 | EX-02 | — | I-02 | SM-02 | Covered |
| 16.9 | Governance Invariant Register — one meaning/one owner; SR-06 | P6 | — | F-06 | I-01 | SM-02 | Covered |
| 16.10 | Governance Invariant Register — round-trip; SR-17 | P14 | — | F-05 | I-01 | SM-02 | Covered |
| 16.11 | Governance Invariant Register — ambiguity fails closed; SR-01, SR-02 | P1 | — | F-01 | I-01 | SM-02 | Covered |
| 16.12 | Governance Invariant Register — overlapping relation preservation; SR-11 | P10 | — | F-02 | I-01 | SM-02 | Covered |
| 16.13 | Governance Invariant Register — no inferred serialization; SR-02, SR-11 | P10 | EX-02 | F-02 | I-01 | SM-02 | Covered |
| 16.14 | Governance Invariant Register — hybrid identity; SR-10 | P9 | — | F-03 | I-01 | SM-01, SM-02 | Covered |
| 16.15 | Governance Invariant Register — Attempt_Identity fail closed; SR-01, SR-10 | P9 | — | F-03 | I-01 | SM-01, SM-02 | Covered |
| 17.1 | Traceability and Handoff Readiness; v1.0 metadata; SR-15 | — | EX-01 | — | — | SM-01 | Covered |
| 17.2 | Traceability and Handoff Readiness; mandatory-section register; SR-15 | — | EX-01 | — | — | SM-01, SM-02 | Covered |
| 17.3 | Handoff readiness gate; SR-01, SR-15 | — | — | — | — | SM-01 | Covered |
| 17.4 | Future Decision Register; ADR gate; SR-02, SR-13, SR-15 | — | EX-02 | F-04 | — | SM-04 | Covered |
| 17.5 | Traceability and Handoff Readiness; SR-13, SR-15 | — | — | — | — | SM-02, SM-04 | Covered |

## Coverage result

- **Acceptance-criteria rows:** 110 expected; 110 present (Requirements 1–17, including every clause in Requirements 10 and 16).
- **Unclassified clauses:** 0. Every row is marked `Covered` and points to a handoff section/semantic rule plus at least one verification classification.
- **Correctness-property coverage:** P1–P15 are preserved without renumbering; exact design requirement traces are listed in the property register.
- **Hybrid identity coverage:** Requirements 10.8–10.13 and 16.14–16.15 map to P9, the identity failure check F-03, integration check I-01, and smoke traceability/metadata checks.
- **Deferred integration rule:** I-01 and I-02 are planned checks only; they cannot admit implementation until the applicable ADR and boundary approval are accepted.
- **Isolation rule:** This matrix is a governance verification artifact only. It authorizes no application code, runtime, persistence, deployment, Git, existing-specification, protected-task, runtime-record, or unrelated-domain change.
