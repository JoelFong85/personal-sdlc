# Personal SDLC workflow

Six local skills coordinate feature requirements, planning, task implementation, and independent review. Each feature saves progress for a fresh Codex session. No tracker, merge request, worktree, or separate engine is needed.

## Start here

Open Codex in this directory and say:

```text
Use workflow/skills/sdlc-orchestrator/SKILL.md to start a feature for
Google Drive document acquisition. I will supply the requirements.
Start with discovery and refinement.
```

`AGENTS.md` routes feature work to this skill. These skills are stored in `workflow/skills/` because this environment prevents writes to `.agents`. They are usable by path now; automatic `$sdlc-orchestrator` discovery is not installed. If you later move the six skill folders together into an allowed repository `.agents/skills/` or personal skill directory, update the routing paths and start a fresh session as needed. Keep their relative layout so shared links work.

The orchestrator allocates a stable ID such as F001 and creates artifacts only as needed. You explicitly approve finalized requirements, then the concrete plan and task definitions. Approval covers the revisions reviewed, not future changes. No product feature or Git repository was created by this installation.

## Everyday prompts

Use the orchestrator path above, or simply ask for feature work in this project:

```text
Show F001 status and the next decision needed.
Continue F001.
Implement F001-T002.
Implement the next three ready tasks in F001 sequentially.
Resume interrupted implementation in F001.
Review F001 independently.
Fix confirmed high-priority findings in F001, then re-review.
Assess adding scanned-PDF support to F001 before changing code.
Use thorough mode for F001 ingestion failure handling.
```

Default implementation scope is one ready task; request a batch to continue further. Approve concrete proposals explicitly, e.g. “I approve these F001 requirements” or “I approve this implementation plan and its task definitions.” The orchestrator records revision fingerprints and your approval evidence.

Routine changes, relevant tests, and local commits inside approved scope do not need repeated approval. Material requirements/architecture/plan changes return to you. Destructive external actions or material external spending require specific authorization. Installing the workflow calls no cloud services.

## Saved artifacts

```text
docs/features/F001-document-acquisition/
  requirements.md           # Intended behavior and acceptance criteria
  decisions.md              # Choices and rationale, including superseded choices
  implementation-plan.md    # Technical approach and verification strategy
  tasks.md                  # Task definitions and execution evidence
  review.md                 # Review baseline, findings, and resolutions
  state.json                # Current checkpoint and revision-bound approvals
  history.jsonl             # Significant workflow events and reasons
```

Artifacts appear only when useful. Stable IDs include F001-R001 for requirements, F001-D001 for decisions, and F001-T001 for tasks. [The artifact contract](workflow/skills/sdlc-orchestrator/references/artifact-contract.md) defines ownership, approval fingerprints, completion, and recovery.

You can maintain requirements yourself. On resume, changed approved inputs trigger impact assessment and renewed approval where meaning changes. Unrelated valid work is retained. Task definitions sit above `<!-- execution-records -->` in tasks.md; mutable status/evidence sits below, so recording progress does not invalidate plan approval.

## Skills and sessions

| Skill | Responsibility |
| --- | --- |
| [sdlc-orchestrator](workflow/skills/sdlc-orchestrator/SKILL.md) | Orchestrate, approve, resume, and manage changes |
| [sdlc-discover](workflow/skills/sdlc-discover/SKILL.md) | Assess supplied requirements and relevant code/context |
| [sdlc-refine](workflow/skills/sdlc-refine/SKILL.md) | Clarify behavior and acceptance criteria |
| [sdlc-plan](workflow/skills/sdlc-plan/SKILL.md) | Propose implementation approach and bounded tasks |
| [sdlc-implement](workflow/skills/sdlc-implement/SKILL.md) | Implement tasks, validate, and commit locally |
| [sdlc-review](workflow/skills/sdlc-review/SKILL.md) | Independently assess changes and record findings |

Your main session coordinates specialists. Applying a skill does not inherently spawn an agent. Lightweight stages usually stay in the main session; bounded subagents are used when helpful. Independent review uses a separate agent when available. If unavailable, the limitation is disclosed and your acceptance is required before completion. Delegation depends on tools actually available in the session.

## Cost and recovery

Economical mode is default: targeted context, sequential tasks, short handoffs, relevant tests, and reusable evidence. Thorough mode expands investigation and review depth; approval and critical correctness checks remain. Two failed correction attempts at the same issue stop automatic retries. Unusually expensive agent runs, evaluations, or corpus processing are surfaced beforehand.

There is no enforced monetary cap. Usage is recorded only when reliable data exists; prices are not invented.

After interruption, ask to continue the feature. The orchestrator compares checkpoint, actual files, Git, task evidence, and review coverage. Existing commits are checked before retrying, unrelated edits are preserved, and uncertainty is reported. A feature completes after approved acceptance criteria, relevant validation, and finding dispositions are satisfied.

## Git and project context

This directory had no Git repository at installation. During authorized implementation Codex can initialize Git if permitted, use your configured identity, and make logical local commits. Missing identity, hooks, or permissions are reported without bypassing safeguards. Branches are optional.

The [n8n architecture notes](policy_research_rag_n8n_architecture.md) remain historical context containing proposals and unverified settings. No LangChain implementation or dependency selection has been made.
