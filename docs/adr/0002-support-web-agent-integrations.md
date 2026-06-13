# ADR-0002: Support Web Agent Integrations

Metadata

| Field | Value |
| --- | --- |
| Status | Accepted |
| Date | 2026-06-13 |
| Decision Owner | Harness Orchestrator |
| Deciders | Architect, Frontend Engineer, API Integration Engineer, Security Reviewer |
| Related Design | `docs/designs/harness-architecture-review.md` |

## Status

Accepted

## Context

The Harness originally covered requirements, architecture, security, testing, AI Foundry and PR planning, but it did not explicitly model browser frontends such as React or Next.js interacting with backend APIs and AI agents.

Projects that use Azure AI Foundry agents commonly need a user-facing application. Browser applications cannot safely hold Azure credentials, call privileged Foundry endpoints directly or enforce authorization by UI controls alone.

## Decision

Add explicit support for web-to-agent architectures:

```text
React or Next.js UI
  -> Backend API or BFF
      -> Azure AI Foundry Agent
```

Add:

* `Frontend Engineer` agent.
* `API Integration Engineer` agent.
* `web-agent-integration` skill.
* `web-ai-agent-app` workflow.
* Web integration and API contract templates.

## Options Considered

| Option | Pros | Cons | Decision |
| --- | --- | --- | --- |
| Keep only existing AI Foundry guidance | Simpler Harness | Missing browser/API security boundary | Rejected |
| Let React call Foundry directly | Fast prototype | Exposes secrets and bypasses server-side controls | Rejected |
| Add web-to-agent gateway pattern | Secure, maintainable, reusable | More architecture artifacts | Accepted |

## Consequences

* React and Next.js projects receive explicit architecture guidance.
* Foundry credentials and privileged calls remain server-side.
* Frontend, API and AI agent work can be split into reviewable PRs.
* Security review can evaluate browser/backend/agent boundaries.

## Security and Operational Impact

The backend API or BFF becomes the trusted enforcement point for authentication, authorization, input validation, rate limiting, audit logging and Foundry invocation.

## Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Additional process for simple prototypes | Slower initial setup | Allow lightweight docs for throwaway prototypes, but keep secrets server-side |
| Backend gateway becomes too generic | Harder security review | Keep API contracts explicit and scoped per feature |

## Reversal or Revisit Criteria

Revisit if the chosen platform provides a safe managed browser-to-agent pattern with equivalent credential isolation, authorization and audit controls.

## Related Documents

* `AGENTS.md`
* `.codex/workflows/web-ai-agent-app.md`
* `skills/web-agent-integration/SKILL.md`
