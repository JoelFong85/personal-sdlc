# Project workflow

For feature lifecycle work, read `workflow/skills/sdlc-orchestrator/SKILL.md` and its linked artifact contract. Apply sibling specialist skills for bounded stages. The orchestrator alone owns lifecycle state, history, and approvals. Skills are stored here because this environment protects `.agents` against writes; do not claim automatic skill discovery or registration.

The user maintains feature requirements. Preserve intent; distinguish approved behavior from proposals. `policy_research_rag_n8n_architecture.md` is reconstructed historical context with unverified settings, not an approved implementation specification.

Use sequential task execution and economical context by default. No Jira, remote publishing, mandatory worktrees, or external service mutations are implied. Preserve unrelated user edits. Local commits within approved implementation scope are permitted where Git configuration and permissions allow.
