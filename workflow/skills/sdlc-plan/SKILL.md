---
name: sdlc-plan
description: Create an implementation approach and bounded dependency-aware tasks from approved feature requirements.
---

# Plan

Read [the contract](../sdlc-orchestrator/references/artifact-contract.md). Require current requirements approval from the orchestrator before finalizing; exploratory drafts remain explicitly unapproved. Read relevant code and reuse discovery context.

Write implementation-plan.md: approach, interfaces, sequencing rationale, risks, verification strategy, and source revisions. Reference decisions.md rather than copying choices. Flag significant architecture decisions for approval with the plan.

Write tasks.md: stable task IDs, requirement/decision links, scope, dependencies, acceptance criteria, relevant meaningful checks, completion criteria. Separate definitions from execution records using the exact contract marker. Prefer testable increments; use bounded investigation tasks for genuine unknowns. Layers/groupings are optional, not required architecture.

Identify the first ready task and expensive operations. Return summary, key choices, risks, and affected files. No implementation before explicit plan approval; no state/history/approval writes.
