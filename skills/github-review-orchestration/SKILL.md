---
name: github-review-orchestration
description: >
  Orchestrate GitHub Issue triage, PR readiness and review, comment validation
  or remediation, CI/CD and checks diagnosis, and pre-merge validation using
  live gh evidence. Trigger when a request mentions GitHub, gh, Issue, PR,
  pull request, review, comment, CI, Actions, checks, merge readiness, or
  requested-change remediation.
license: Apache-2.0
metadata:
  author: gentleman-programming
  version: "1.0"
---

# GitHub Review Orchestration

Use this skill only for an explicit GitHub work request or when the
orchestrator has identified GitHub state as a required dependency. It is a
decision and evidence layer, not a replacement for Gentle-AI review authority.

## Critical Rules

- Use authenticated `gh` first for live GitHub state. Never add tokens, cookies, secrets, or an unverified GitHub MCP.
- Read first, write only with explicit task instruction. Merge, close, delete, dismiss, resolve, rerun, rollback, and force-push require confirmation.
- Do not fan out reviewers or create review authority. Native bounded review is the only source of truth: explicit `review/start` -> selected lens result -> `review/finalize` -> `review/validate`.
- A severe finding blocks only with candidate-causal evidence. Use `introduced`, `behavior-activated`, `worsened`, `pre-existing`, `base-only`, or `unknown` when reviewing a candidate.
- Never claim success from source inspection alone. Record commands, exit state, timestamps or commit SHA, and whether evidence was verified, inferred, not checked, or unavailable.

## Decision Flow

| Request | Inspect first | Decision gate |
| --- | --- | --- |
| Issue triage | Issue body, template fields, duplicates, labels, discussion | Valid, in scope, actionable, approval state |
| PR readiness/review | Linked Issue, diff, base/head, labels, review state, checks | Traceability, candidate risks, required checks, receipt |
| Comment remediation | Exact thread, changed location, current code, tests/checks | Each comment fixed, disproved with evidence, or still open |
| CI/check diagnosis | Check suite, failing job, run, first error, commit | Reproducible code/workflow cause vs infra/flaky/unavailable |
| Pre-merge validation | Immutable SHA, branch relation, checks, approvals, conflicts | All required gates pass and authority allows |

## Traceability Schema

```yaml
task_type: issue-triage|pr-review|comment-remediation|ci-diagnosis|pre-merge
scope: {repository, issue_or_pr, base_sha, head_sha, branch}
traceability:
  issue: {id, acceptance_criteria, approval_state}
  code: [{location, behavior_or_requirement}]
  verification: [{kind, name, command_or_url, status, sha}]
decision: allow|block|needs-information|unavailable
findings:
  - {severity, confidence, location, impact, evidence, recommendation}
evidence_status: verified|inferred|not checked|unavailable
writes: []
```

## Focused `gh` Commands

```bash
gh auth status
```

Use only focused read-only commands permitted by the agent policy; do not use `gh api` generically. Redact sensitive output. For web UI evidence, prefer `gh`; if browser-only context is required, label it as UI evidence and record what was visibly verified.

## Risk Gates

- Security: inspect permissions, secrets exposure, unsafe workflow triggers, untrusted input, dependency changes, and token scopes. Escalate to the native `review-risk` path only through explicit `review/start`.
- Actions/CI: distinguish failing code, workflow syntax, permissions, runner/environment, cancelled, queued, flaky, and unavailable. Do not rerun automatically; a rerun is a write and needs explicit authorization.
- Performance: require a measured regression, benchmark, query/runtime evidence, or a concrete changed hot path. Do not block on speculation.
- Merge conflicts: identify base/head SHAs and conflicting paths. Do not resolve, rebase, or push; report the smallest safe remediation.
- Comment remediation: map every comment to a location and acceptance criterion, then verify code and tests. Keep unresolved conversations open.
- Sensitive or unavailable data: state the missing permission or API limitation and downgrade the decision to `needs-information` or `unavailable`.

## Local Contract Integration

Use the repository's named Gentle-AI/OpenCode contracts when available:
`branch-pr`, `issue-creation`, `comment-writer`, `tdd`, `architecture-guard`,
`karpathy-guidelines`, `agent-reach`, and `ecc-harness-patterns`. The native
Gentle-AI review lifecycle remains authoritative over review budgets, ledgers,
receipts, corrections, and gates.

## Report Quality

Findings must include an exact location where possible, observable impact,
evidence references, severity, confidence, and one actionable recommendation.
Separate blockers from warnings. If no finding is proven, say so and list
remaining unverified checks rather than manufacturing certainty.
