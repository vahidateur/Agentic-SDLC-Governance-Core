# Example: Admitted Work Package

> Non-authoritative finite example. Values are illustrative and do not select an implementation mechanism.

A Work Package has a stable Work Package Identity `wp-example-001`, lifecycle version `1`, complete authority and provenance, one Semantic Owner, an immutable Baseline, a declared scope, a valid concurrency result, and explicit completion conditions. All applicable validation checks are evaluated and attributable.

The Core records an `ACCEPTED` admission Decision Record bound to `wp-example-001`, its baseline, authority, policy references, and all material-input provenance. If actual execution begins, it allocates exactly one unique Attempt Identity (also reviewable as the Run Identity) for that execution. A replay of the admission does not allocate another attempt.

Completion remains pending until every declared condition has current, sufficient Evidence Artifacts bound to the exact Work Package Identity and applicable Baseline.