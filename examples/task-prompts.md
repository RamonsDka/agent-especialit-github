# Task Prompts

Use an explicit Task invocation. Keep repository and Issue/PR scope concrete.

## Issue Triage

```text
Invoke agent-especialit-github for owner/repo Issue #42. Classify validity,
duplicates, scope, labels, approval state, and acceptance criteria. Read only;
return traceability, evidence states, findings, and a decision.
```

## Pull Request Review

```text
Invoke agent-especialit-github for owner/repo PR #87 against its current base
SHA. Inspect the linked Issue, diff, reviews, required checks, conflicts, and
receipt scope. Do not write GitHub data. Return only evidence-backed findings.
```

## Comment Remediation

```text
Invoke agent-especialit-github to validate every unresolved review comment on
owner/repo PR #87. Map each comment to current code, acceptance criteria, and
tests/checks. Do not resolve conversations or post comments.
```

## CI Diagnosis

```text
Invoke agent-especialit-github for owner/repo workflow run 123456. Identify
the first actionable failure, affected commit, rerun state, and whether the
cause is code, workflow, permissions, runner, flaky, or unavailable. Do not
rerun the check.
```

## Pre-Merge Validation

```text
Invoke agent-especialit-github for owner/repo PR #87. Re-check the immutable
candidate SHA, branch relationship, approvals, required checks, conflicts, and
native review receipt supplied by the orchestrator. Recommend allow or block;
do not merge.
```
