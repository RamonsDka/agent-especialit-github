# Installation

Install the two bundled OpenCode files and the minimal Task permission. The
repository does not install external skills or configure an unverified MCP.

## Files

| Source in this repository | Destination |
| --- | --- |
| `agent/agent-especialit-github.md` | Your OpenCode agent directory |
| `skills/github-review-orchestration/SKILL.md` | Your OpenCode skill directory under `github-review-orchestration` |
| `examples/opencode-permission.jsonc` | Merge into the `gentle-orchestrator` permission object |

Use the destination conventions of your OpenCode installation rather than
copying any workstation-specific path from this repository.

## Permission

![Task permission integration](../assets/images/task-permission.jpeg)

The only required integration is:

```jsonc
"gentle-orchestrator.permission.task[\"agent-especialit-github\"]": "allow"
```

Do not broaden the allow-list. The agent itself retains `task: deny`,
`edit: deny`, and `write: deny`.

## Restart

Restart OpenCode after installing agent, skill, or permission files. These are
configuration-time inputs and a running process may not reload them.

## Verify

1. Confirm the agent frontmatter parses and has `mode: subagent`, `hidden: true`, and the denied permissions.
2. Confirm the skill is discoverable under `github-review-orchestration`.
3. Confirm the orchestrator can explicitly Task `agent-especialit-github`.
4. Run `gh auth status` in the intended environment before a live request.

## Backend

`gh` is the default verified backend. The package does not require or configure
the GitHub MCP referenced in the skills catalog; add no backend until its
provenance, permissions, and behavior are independently verified.
