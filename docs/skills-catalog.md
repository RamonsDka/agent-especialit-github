# Skills Catalog

This catalog distinguishes what ships in this repository from contracts that
may already exist in a Gentle-AI/OpenCode environment, external recommendations,
and backend/tool references. External entries are not claimed to be installed.

## Bundled Local Skill

| Name | Reference | Role | Trigger/phase | Priority | Integration status |
| --- | --- | --- | --- | --- | --- |
| github-review-orchestration | [bundled skill](../skills/github-review-orchestration/SKILL.md) | GitHub evidence, traceability, safety, and native review alignment | Explicit GitHub request; agent runtime | Primary | Bundled local skill |

## Existing Gentle-AI/OpenCode Contracts

| Name | Reference | Role | Trigger/phase | Priority | Integration status |
| --- | --- | --- | --- | --- | --- |
| branch-pr | Environment-provided local contract; not bundled as a URL | Branch and PR workflow | Branch/PR preparation | High | Existing Gentle-AI skill; load when available |
| issue-creation | Environment-provided local contract; not bundled as a URL | Issue-first checks and issue creation discipline | Issue creation | High | Existing Gentle-AI skill; load when available |
| comment-writer | Environment-provided local contract; not bundled as a URL | Clear collaboration comments | Comments and PR feedback | Medium | Existing Gentle-AI skill; load when available |
| tdd | Environment-provided local contract; not bundled as a URL | Evidence-based test changes | Bug fixes and tests | High | Existing Gentle-AI skill; load when available |
| architecture-guard | Environment-provided local contract; not bundled as a URL | Repository-boundary decisions | Architecture and structure | High | Existing Gentle-AI skill; load when available |
| karpathy-guidelines | Environment-provided local contract; not bundled as a URL | Minimal, observable changes | Implementation and review | High | Existing Gentle-AI skill; load when available |
| agent-reach | Environment-provided local contract; not bundled as a URL | Research/backend routing convention | GitHub discovery and web research | Medium | Existing Gentle-AI skill; use its routing when available |
| ecc-harness-patterns | Environment-provided local contract; not bundled as a URL | Verification-by-evidence and immutability | Harness and review standards | High | Existing Gentle-AI skill; load when available |
| review-risk | Environment-provided local contract; not bundled as a URL | Security and architecture lens | High-risk native review | High | Existing Gentle-AI lens; native lifecycle only |
| review-readability | Environment-provided local contract; not bundled as a URL | Naming and maintainability lens | Standard or high-risk review | Medium | Existing Gentle-AI lens; native lifecycle only |
| review-reliability | Environment-provided local contract; not bundled as a URL | Behavior, state, and regression lens | Standard or high-risk review | High | Existing Gentle-AI lens; native lifecycle only |
| review-resilience | Environment-provided local contract; not bundled as a URL | Process, partial failure, and recovery lens | High-risk native review | High | Existing Gentle-AI lens; native lifecycle only |
| review-refuter | Environment-provided local contract; not bundled as a URL | Read-only blocker refutation | Native review when required | High | Existing Gentle-AI contract; no standalone fan-out |
| judgment-day | Environment-provided local contract; not bundled as a URL | Extraordinary dual review | Explicit extraordinary review only | Exceptional | Existing Gentle-AI contract; conditional |
| work-unit-commits | Environment-provided local contract; not bundled as a URL | Reviewable work-unit boundaries | Implementation and delivery | Medium | Existing Gentle-AI skill; no commits performed here |
| chained-pr | Environment-provided local contract; not bundled as a URL | Split oversized review slices | Over-400-line or stacked PR planning | Medium | Existing Gentle-AI skill; conditional |
| completion-summary | Environment-provided local contract; not bundled as a URL | Evidence-based completion receipt | Task completion | Medium | Existing Gentle-AI skill; load when available |

These named local contracts are environment-provided references, not bundled
URLs or installation requirements. The package's portable source of truth is
the bundled skill and agent files.

## External Recommended Skills And References

| Name | Exact URL | Role | Trigger/phase | Priority | Integration status |
| --- | --- | --- | --- | --- | --- |
| github-issues | https://www.skills.sh/github/awesome-copilot/github-issues | Issue operations patterns | Issue triage | Medium | External recommended; not installed |
| GitHub MCP official/source referenced by research | https://www.aitmpl.com/plugins/claude-plugins-official/ | MCP source reference | Only after independent verification | Low | External reference; not configured |
| analyze-issue | https://www.aitmpl.com/ and https://www.aitmpl.com/plugins/cc-marketplace/ | Issue analysis patterns | Issue analysis | Medium | External recommended; not installed |
| triage | https://skills.sh/mattpocock/skills/triage | Triage workflow | Issue triage | Medium | External recommended; not installed |
| to-issues | https://skills.sh/mattpocock/skills/to-issues | Convert findings to issues | Explicit issue creation | Medium | External recommended; not installed |
| pr-review | https://www.aitmpl.com/plugins/cc-marketplace/ | PR review patterns | PR review | Medium | External recommended; not installed |
| code-review | https://skills.sh/mattpocock/skills/code-review | Review heuristics | Code review | Medium | External recommended; not installed |
| receiving-code-review | https://skills.sh/obra/superpowers/receiving-code-review | Process review feedback | Comment remediation | Medium | External recommended; not installed |
| requesting-code-review | https://skills.sh/obra/superpowers/requesting-code-review | Request review preparation | PR readiness | Medium | External recommended; not installed |
| verification-before-completion | https://skills.sh/obra/superpowers/verification-before-completion | Completion verification | Every decision | High | External recommended; not installed |
| test-driven-development | https://skills.sh/obra/superpowers/test-driven-development | TDD practice | Code and regression changes | High | External recommended; not installed |
| systematic-debugging | https://skills.sh/obra/superpowers/systematic-debugging | Failure diagnosis | CI and bug diagnosis | High | External recommended; not installed |
| qa | https://skills.sh/mattpocock/skills/qa | QA workflow | Validation | Medium | External recommended; not installed |
| webapp-testing | https://skills.sh/anthropics/skills/webapp-testing | Web testing patterns | Web-specific checks | Low | External recommended; not installed |
| resolving-merge-conflicts | https://skills.sh/mattpocock/skills/resolving-merge-conflicts | Conflict guidance | Conflict diagnosis | Medium | External recommended; not installed |
| git-guardrails-claude-code | https://skills.sh/mattpocock/skills/git-guardrails-claude-code | Git safety | Git operations | High | External recommended; not installed |
| using-git-worktrees | https://skills.sh/obra/superpowers/using-git-worktrees | Worktree guidance | Isolated development | Low | External recommended; not installed |
| dispatching-parallel-agents | https://skills.sh/obra/superpowers/dispatching-parallel-agents | Background delegation research | Contextual only | Low | External background reference; not used for uncontrolled fan-out |
| github-actions-expert | https://www.aitmpl.com/component/agent/security/github-actions-expert | Actions expertise | CI/security diagnosis | Medium | External recommended; not installed |
| fix-pr | https://www.aitmpl.com/plugins/cc-marketplace/ | PR remediation patterns | Explicit remediation | Medium | External recommended; not installed |
| fix-github-issue | https://www.aitmpl.com/plugins/cc-marketplace/ | Issue remediation patterns | Explicit remediation | Medium | External recommended; not installed |

## Backend And Tool

| Name | Exact URL | Role | Trigger/phase | Priority | Integration status |
| --- | --- | --- | --- | --- | --- |
| GitHub CLI (`gh`) | https://cli.github.com/ | Authenticated live GitHub backend | Every live GitHub workflow | Primary | Default verified backend |
| Git | https://git-scm.com/ | Candidate SHA and local diff evidence | Every candidate workflow | Primary | Host tool |

## Native Lens Selection

Low risk means documentation, comments, formatting, or typo-only string edits:
no lens. Standard risk means every other change: exactly one dominant-risk
lens. High risk means security/auth/update/payments, data exposure/loss,
permissions, shell/process integration, or more than 400 authored changed
lines: the full 4R set. This selection happens only inside one explicit native
`review/start`; `dispatching-parallel-agents` is contextual background, not a
license for uncontrolled fan-out.
