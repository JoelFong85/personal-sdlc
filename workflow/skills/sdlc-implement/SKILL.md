---
name: sdlc-implement
description: Implement approved bounded tasks, validate acceptance criteria, and record progress and logical local commits.
---

# Implement

Read [the contract](../sdlc-orchestrator/references/artifact-contract.md). Receive exact task or requested ready batch, scope, and current approval evidence from the orchestrator. If invoked without evidence, return the missing gate before changing product code.

Inspect dependencies, relevant code, working tree, partial work, and existing commits. Update task execution records below the marker; never state/history. Implement the smallest coherent change satisfying acceptance criteria. Surface missing product decisions and significant scope/architecture changes before affected work.

Run meaningful relevant checks, recording commands, outcome, code revision/snapshot, and limitations. Reuse valid results; broaden only for new failures/risks. Stop automatic correction after two unsuccessful attempts at the same issue. Do not fabricate passing tests, bypass hooks, or perform unauthorized consequential external actions.

Review the diff for accidental changes, stage only task-owned files, and commit logically within approved scope where Git permissions/configuration permit. Never invent identity or duplicate an existing commit. Record blocked commits honestly. Update execution evidence and return outcome, files, validation, commit references, and remaining issues. The orchestrator controls next-task selection and lifecycle state.
