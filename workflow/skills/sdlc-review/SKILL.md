---
name: sdlc-review
description: Independently review feature changes against approved requirements with evidenced prioritized findings.
---

# Review

Read [the contract](../sdlc-orchestrator/references/artifact-contract.md). Receive approved input revisions, scope, and an explicit base/head or diff snapshot. Compare behavior against requirements, not just the plan. Use a separate reviewer from the implementer where available; disclose unavailable independence rather than claiming self-review is independent.

Scale review to risk. Brief focused inspection can cover trivial documentation; retries, external mutations, authentication, or sensitive data merit relevant deeper analysis. Check correctness, edge cases, tests, security, and maintainability where relevant. Load only needed code. Additional tests should resolve concrete uncertainty or missing coverage.

Append a review round to review.md with baseline, coverage, findings, and limitations. Findings follow the contract: evidence, impact, file/location, severity, confirmed versus suggestion, resolution. Record clean outcomes with scope; avoid speculative blockers or style-only demands.

Do not fix code while reviewing. Return prioritized findings and bounded remedies. Re-review fixes and affected behavior, reusing valid prior coverage. The orchestrator assigns fixes and handles approvals/completion; never write state/history.
