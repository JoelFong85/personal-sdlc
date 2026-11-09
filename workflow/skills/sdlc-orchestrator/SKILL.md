---
name: sdlc-orchestrator
description: Coordinate numbered features through discovery, approval, planning, tasks, review, and resumable progress.
---

# Feature orchestrator

Read [the shared contract](references/artifact-contract.md). Own state, history, approval records, lifecycle transitions, and reconciliation. Specialists never independently update those files.

## Open and resume

Identify the feature; scan folders to allocate the next unused F-number for new work. Create only the folder and checkpoint initially. Do not invent a product feature to install the workflow. Load state and relevant artifacts, reconcile actual code/Git/evidence, and briefly report stage and next action. Respect status-only requests. Default implementation scope is one ready task; support an exact task, requested sequential batch, and interrupted-task resume.

Follow discovery → refinement → planning → implementation → review → complete, looping back when evidence requires it. Apply sibling skills by path. Reuse relevant findings; read only needed code and artifacts.

## Approval and change gates

Present finalized requirements and accepted decisions for explicit approval before authoritative planning. Present the concrete plan, task definitions, and technical decisions for explicit approval before implementation. Persist revision-bound approval under the contract. Silence or a specialist recommendation is not approval. Previously granted authorization remains valid for its covered revision/action.

Check freshness before dependent work and after resume. Assess changed inputs and record affected/unaffected work. Renew material requirements or significant architecture/scope/plan approvals; preserve unrelated validated work. Explain the applicable gate when asking. Routine implementation, tests, and local commits in approved scope proceed without repeated permission. Destructive/consequential external actions or material external spend require specific authorization unless already explicitly granted. Prepare concrete reviewable work before requesting approval.

## Delegation and cost

Economical is default. Handle lightweight discovery/refinement/planning in the main session; delegate substantial isolated work only when context savings or quality warrant it. Use bounded task implementation, sequential by default. Parallelism requires user request and independent dependencies/file ownership. Use a separate reviewer from implementation when available. If unavailable, disclose missing independence and seek user acceptance before marking complete.

A specialist brief includes skill path, feature path, exact task/scope, approved revisions, allowed files, and expected result. Handoffs are concise: outcome, files, checks, unresolved issues, next action. Keep user questions/approvals in the main session. Do not claim delegation occurred if it did not.

Thorough mode expands investigation/testing/review depth; critical safety and correctness checks apply in both modes. Reuse evidence while applicable. After two failed correction attempts at the same issue, stop automatic retries and present evidence and a revised approach. Warn before unusually expensive runs or corpus operations; do not invent dollar estimates. Record actual usage only when reliable data is exposed; these instructions enforce no monetary cap.

## Recovery and completion

Reconcile partial work and commits before retrying. Preserve unrelated edits and damaged state/history. Repair transparently using files and Git. Complete only after approved acceptance criteria, relevant validation, and finding dispositions satisfy the shared contract. Record limitations and a checkpoint before handoff or stopping.

Resolve feature artifact paths relative to the active application working directory, not the skill source directory.
