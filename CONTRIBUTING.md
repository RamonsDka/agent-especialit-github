# Contributing

Contributions should preserve the package's small runtime boundary and evidence
discipline.

## Before Opening A Change

- Read `AGENTS.md` and the relevant docs.
- Keep agent and skill frontmatter valid.
- Use relative repository links for local content.
- Do not add secrets, token examples, fake CI claims, or unverified backends.
- Keep docs and examples with the behavior they explain.

## Review Checklist

- [ ] The change has one clear purpose.
- [ ] Safety and write authorization remain explicit.
- [ ] Traceability and evidence states remain complete.
- [ ] Any image is unchanged, cataloged, and contextually embedded.
- [ ] `git diff --check` is clean.
- [ ] Validation commands and exact results are included in the PR description.

## Pull Requests

Use the pull request template. Prefer focused work units; if a change grows
beyond 400 authored lines, split it into reviewable slices rather than hiding
complexity in one PR.
