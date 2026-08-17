# Example: Blocked Work Package

> Non-authoritative finite example.

A Work Package has an otherwise valid identity and scope, but one required authority reference is stale and one completion condition lacks current Evidence Artifact coverage. The complete Validation Set records both findings.

The Core creates a named `Blocking_State` with status `BLOCKED` and stable reasons for the stale authority and insufficient evidence. It withholds admission and completion, preserves the prior safe state, and creates a linked Decision Record. It does not infer a replacement authority or convert the completion claim into evidence.

If the condition requires a human decision, the block may use `HUMAN_DECISION_REQUIRED`. That status remains non-success and never authorizes work. After attributable resolution, the Core must perform a fresh complete evaluation.
