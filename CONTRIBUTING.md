# Contributing

Thank you for helping improve this project. Contributions are welcome when they are understandable, reviewable, respectful of existing contracts, and aligned with the project's architecture and governance goals.

## Contribution philosophy

Prefer small, focused changes that solve a clearly stated problem. Explain decisions rather than only implementation details, favor compatibility over unnecessary disruption, and make validation results reproducible. Documentation, tests, governance updates, and other non-code contributions are held to the same standard of clarity and reviewability.

Every contribution must preserve traceability and provenance. A reviewer should understand why a change was made, what changed, which evidence supports it, and who approved material decisions.

## Reporting issues

Search existing issues and documentation before opening a new issue. Use the applicable template and provide a concise description, expected and actual behavior, reproduction steps where relevant, environment details, and supporting evidence. Do not include secrets, credentials, private data, or undisclosed security vulnerabilities in a public issue; follow [SECURITY.md](SECURITY.md) for security reporting.

For governance concerns, identify the affected area and explain compatibility, migration, approval, and evidence implications.

## Proposing governance changes

Use the governance-change or ADR proposal template for changes to policies, controls, lifecycle rules, architecture decisions, approval requirements, or other governance contracts. State the motivation, affected area, alternatives, compatibility impact, migration considerations, and approval requirements. Reference relevant Evidence Artifact and Decision Record material, and identify required Human approval gates before implementation.

Where applicable, retain links to the Work Package Identity, Run Identity, and Attempt Identity so the proposal can be followed through its lifecycle.

## Pull request workflow

1. Open or identify an issue, proposal, or Decision Record defining the change and scope.
2. Create a focused branch from the appropriate maintained base branch.
3. Implement the change with relevant documentation and tests.
4. Complete the pull request template, including Governance Impact and Validation Evidence.
5. Request review from appropriate maintainers and domain owners.
6. Address feedback transparently and keep the branch synchronized without rewriting shared history.
7. Obtain required Human approval gates before merging.
8. Merge only after checks pass and traceability, provenance, and documentation are complete.

Maintainers may request additional evidence, smaller scope, an ADR, or a staged migration when a change has broad governance or compatibility impact.

## Branch naming convention

Use short, descriptive, lowercase names with slash-separated categories and kebab-case descriptions: `feature/<description>`, `fix/<description>`, `docs/<description>`, `chore/<description>`, or `governance/<description>`. Do not commit directly to protected branches. Keep one logical change per branch and avoid unrelated work.

## Commit message expectations

Use clear Conventional Commits-style messages in English: `<type>: <imperative summary>`. Common types include `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, and `governance`. Keep the subject concise, explain rationale or compatibility considerations in the body, and do not combine unrelated changes. History should support traceability to the issue, Evidence Artifact, Decision Record, and approvals where applicable.

## Identity, evidence, and approvals

- **Work Package Identity** identifies the governed unit of work.
- **Run Identity** identifies an execution or delivery run.
- **Attempt Identity** identifies a specific attempt within that run.
- **Evidence Artifact** records validation, observations, or supporting material.
- **Decision Record** captures a material decision and its rationale.
- **Human approval gates** mark required human review and authorization points.

Do not invent identifiers or approval outcomes. If an identifier, Evidence Artifact, Decision Record, or Human approval gate is required but unavailable, state that explicitly and request maintainer guidance.

## Review standards

Consider correctness, security, accessibility, compatibility, maintainability, documentation, test coverage, operational impact, and rollback or migration needs. Review comments should be specific, respectful, and focused on improving the contribution.
