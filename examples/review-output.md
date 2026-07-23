# Example Review Output

The following is illustrative format, not a claim about a live repository.

```text
Task type: pr-review
Scope: acme/widget, PR #87, base abc1234, head def5678, current bounded review scope
Decision: block

Traceability:
- Issue and acceptance criteria: Issue #42; pagination must preserve filters and expose an empty state.
- Code and changed locations: src/list.ts:44-71; filter state is dropped when the next page loads.
- Tests, checks, and review evidence: test/list.spec.ts:18-39 fails in the focused scenario; required CI is verified for the same head SHA.

Findings:
- [BLOCKER] [high] src/list.ts:58: the candidate loses the active filter on pagination. Evidence: focused test failure on head def5678. Recommendation: retain the filter in the page request and add a regression assertion.

Evidence status:
- verified: head SHA, linked Issue, changed location, focused test output, required check state.
- inferred: no data-loss impact beyond the filtered list path.
- not checked: production telemetry.
- unavailable: none.

Writes performed: none
skill_resolution: paths-injected
```
