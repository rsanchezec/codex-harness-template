# Harness Orchestrator Repository

This repository defines a Codex delivery harness for software projects that need explicit requirements, architecture, quality, security and delivery planning before implementation.

## Purpose

The harness is designed to prevent direct jumps from idea to code. It provides:

* Delivery workflows for features, bug fixes and architecture reviews.
* Web AI agent workflow for React, Next.js, backend APIs and Azure AI Foundry integrations.
* Specialist role instructions under `.codex/agents`.
* Reusable templates under `.codex/templates`.
* Local skills under `skills`.
* Documentation folders for specifications, designs, ADRs, tests, PR plans, operations and reviews.

## Standard Delivery Flow

Use this flow for production changes:

1. Discovery
2. Requirements Analysis
3. Specification
4. Architecture Design
5. Security Review
6. Test Strategy
7. Implementation Plan
8. Pull Request Chain Plan
9. Implementation
10. Review

For React, Next.js or AI chat applications, use `.codex/workflows/web-ai-agent-app.md`. The expected boundary is:

```text
React or Next.js UI
  -> Backend API or BFF
      -> Azure AI Foundry Agent or other AI service
```

Do not call Foundry or other privileged AI services directly from browser code.

Implementation should not begin until the Definition of Ready in `AGENTS.md` is satisfied or skipped gates are explicitly documented with risk.

## Documentation Map

| Folder | Purpose |
| --- | --- |
| `docs/specs` | Functional specifications, user stories and acceptance criteria |
| `docs/designs` | Technical designs, security reviews and implementation plans |
| `docs/adr` | Architecture decision records |
| `docs/tests` | Test plans, regression plans and AI evaluation plans |
| `docs/pr-plan` | Pull request chain plans |
| `docs/operations` | Deployment, observability and production readiness artifacts |
| `docs/reviews` | Code, architecture and delivery review reports |

## Template Usage

Start from the templates in `.codex/templates` when creating new artifacts. Keep status, owner, date, risks, open questions and approvals current.

Recommended status values:

* Draft
* In Review
* Approved
* Blocked
* Superseded

## Delivery Expectations

Every non-trivial change should link these artifacts together:

* Specification
* Technical design
* Web/API integration design for React, Next.js or browser-to-agent features
* ADRs when decisions have long-term impact
* Security review when risk is material
* Test plan
* Implementation plan
* PR chain plan
* Final review

Small, reversible changes may use lighter documentation, but skipped steps must be explicit.

## Repository Governance

Git is initialized for this harness. Use branch and PR conventions from `docs/operations/repository-governance.md`.
