# Shared artifact contract

Feature folders: `docs/features/F001-short-name/`. Scan existing folders for the next unused number; never reuse IDs. Create artifacts only when needed. The orchestrator alone writes state.json, history.jsonl, approvals, and lifecycle transitions. Specialists may edit assigned artifacts/code and return concise results. User-maintained requirements retain their intent.

## Seven artifacts

| File | Sole primary responsibility |
| --- | --- |
| requirements.md | Behavior, scope/exclusions, stable F001-R001 requirement IDs, feature acceptance criteria, open questions. |
| decisions.md | Stable F001-D001 choices, proposed/accepted/superseded disposition, rationale, important alternatives, affected IDs, superseding references. |
| implementation-plan.md | Technical approach, interfaces, sequencing rationale, risks, verification strategy, fingerprints of approved inputs. |
| tasks.md | Stable F001-T001 definitions, requirement links, dependencies, acceptance/completion criteria, relevant checks; separate mutable execution evidence. |
| review.md | Review rounds, code/input baseline, scope, findings, evidence, severity, resolution, and limitations. |
| state.json | Small current checkpoint, approval records, blockers, next action. Never duplicate task lists or plans. |
| history.jsonl | Append-only significant events and reasons with artifact/task references. Never transcripts, secrets, or copied plans. |

In tasks.md, put definitions above this exact standalone marker and mutable execution records below it:

`<!-- execution-records -->`

Each execution record includes status (pending/in_progress/blocked/done), attempts, changed files, validation command/outcome and code revision or snapshot, commits, and limitations. A ready task has satisfied dependencies, current approvals, and sufficient product decisions. A done task satisfies its acceptance/completion criteria and relevant checks. Documentation/trivial tasks may use inspection with a reason instead of automated tests.

Review findings have stable IDs, confirmed-problem versus suggestion disposition, severity with impact, file/location, evidence, remedy, and open/fixed/accepted/deferred status. Critical/high confirmed findings block completion unless explicitly accepted by the user. Other confirmed problems require resolution or explicit disposition; style suggestions do not automatically block. Preserve prior rounds and reference fix commits and verification.

## Checkpoint and history

Initial state.json example (replace placeholders with actual values):

```json
{
  "schema_version": 1,
  "feature_id": "F001",
  "title": "Document acquisition",
  "stage": "discovery",
  "status": "in_progress",
  "mode": "economical",
  "current_task": null,
  "next_action": "Read supplied requirements",
  "blockers": [],
  "approvals": [],
  "updated_at": "<actual ISO-8601 timestamp>"
}
```

Stages: discovery, refinement, planning, implementation, review, complete. Status: in_progress, awaiting_approval, blocked, complete. Interrupted work keeps its stage; record partial progress in task evidence. Each history line has actual timestamp, feature_id, event, summary, and relevant artifact/task/revision references. Record transitions, approvals, impact assessments, task outcomes, blockers, and repairs. Git tracks content history; JSONL explains workflow events.

Validate existing JSON/JSONL before updating. Replace state atomically using a temporary file. No transactional engine: reconcile interrupted cross-file updates and append a repair event. Preserve malformed files before repair and disclose uncertain reconstruction.

## Revision-aware approvals

Requirements approval covers requirements.md and the accepted decisions relevant to it. Plan approval covers implementation-plan.md, task definitions, and accepted technical decisions. Record exact artifact/decision IDs, SHA-256 fingerprints, gate, actual timestamp, user approval evidence, and validity. Compute hashes from actual bytes, never invent them. For files use `shasum -a 256 FILE`. Hash only bytes preceding the execution marker for task definitions; execution progress must not invalidate approval.

For accepted decisions, hash each exact entry text separately and record included decision IDs. Entries use a consistent heading `## F001-D001: Title`; an entry runs from that heading to the next decision heading or end of file. Include disposition within the entry. Record an empty set when none are accepted. Proposed/superseded entries do not belong in a new approval's accepted set; retain earlier records.

Compare approved inputs before dependent work and on resume. A mismatch is unassessed/stale until evaluated. Record impact on requirements, decisions, tasks, tests, and review. Material behavior changes require renewed requirements approval; significant plan/architecture/scope changes require renewed plan approval. Preserve unrelated valid work. Editorial carry-forward needs an explicit recorded assessment with old/new fingerprints and why meaning is unchanged; retain original approval evidence. Never silently replace approved fingerprints. Code changes alone do not revoke requirements approval but can invalidate checks/review coverage. New review-fix tasks require plan impact assessment before execution.

## Git, validation, and recovery

Local commits within approved scope are permitted. Inspect working tree and stage only task-owned changes. Use logical messages such as `F001-T001: extract document text`. Check existing history before retrying commits. Do not invent author identity or bypass hooks. If Git is absent, initialize only during authorized implementation when permissions permit; otherwise report the blocker and retain work. Workflow evidence may be committed separately to avoid self-referential hashes.

Resume compares state with actual files, fingerprints, working tree, commits, task evidence, unresolved findings, and review baseline. Do not repeat completed work solely because state lags. Reuse tests/review only when relevant code, inputs, and environment still match. Rerun affected checks after changes. Completion needs satisfied approved acceptance criteria, relevant passing validation, and explicit disposition of findings. Missing independent review requires disclosure and user acceptance before completion.
