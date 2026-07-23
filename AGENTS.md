# Agent Guidance

This repository packages a hidden OpenCode/Gentle-AI GitHub specialist.

- Preserve `agent/agent-especialit-github.md` frontmatter and Task-only semantics.
- Preserve `skills/github-review-orchestration/SKILL.md` as the portable runtime contract.
- Keep `gh` as the default verified backend; never add secrets or unverified MCP configuration.
- Keep local mutation denied and GitHub writes explicit.
- Use native bounded review only: one explicit `review/start`, deterministic lens selection, finalize, validate.
- Do not fan out reviewers or spawn subagents from the specialist.
- Use relative local links and update `docs/image-catalog.md` for new images.
- Validate with read-only checks; do not build or commit in routine package work.

See [CONTRIBUTING.md](CONTRIBUTING.md) and [docs/output-contract.md](docs/output-contract.md).
