# Example: Replay, Retry, and Rerun

> Non-authoritative finite example showing the hybrid identity boundary.

- Work Package Identity: `wp-example-002`, lifecycle version `3`.
- Validation replay: preserves `wp-example-002` and prior attempt references; allocates no Attempt Identity.
- Inspection: preserves the same parent identity; allocates no Attempt Identity.
- Actual execution: allocates `attempt-example-001` exactly once and binds it to `wp-example-002` version `3`.
- Retry or rerun: allocates `attempt-example-002`, even though the parent identity and lifecycle version remain unchanged.
- Failed, blocked, cancelled, completed, or abandoned attempts retain their identities as non-reusable.

A cross-parent, cross-version, duplicate, or unverifiable binding fails closed and withholds dependent outcomes.
