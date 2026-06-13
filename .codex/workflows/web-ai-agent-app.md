# Web AI Agent App Workflow

Use this workflow when building a React, Next.js, Vite or other browser frontend that interacts with an AI agent, backend API, BFF or Azure AI Foundry.

Core boundary:

```text
React or Next.js UI
  -> Backend API or BFF
      -> Azure AI Foundry Agent or other AI service
```

Never call Azure AI Foundry directly from browser code.

---

# Workflow

1. Use Product Analyst
2. Apply SDD skill
3. Use Frontend Engineer
4. Use API Integration Engineer
5. Use Architect
6. Apply Web Agent Integration skill
7. Apply Architecture Review skill
8. Use Security Reviewer
9. Apply Security Review skill
10. Use Test Engineer
11. Apply TDD skill
12. Apply PR Chain skill
13. Implement only after approval

---

# Required Artifacts

- /docs/specs/[feature].md
- /docs/designs/[feature]-web-agent-integration.md
- /docs/designs/[feature]-api-contract.md
- /docs/designs/[feature]-security-review.md
- /docs/designs/[feature]-implementation-plan.md
- /docs/tests/[feature]-web-agent-test-plan.md
- /docs/pr-plan/[feature].md

When needed:

- /docs/adr/[number]-[decision].md
- /docs/operations/[feature]-operations.md

---

# Review Checklist

- Frontend framework and rendering model are explicit
- Backend API boundary is documented
- Foundry or AI service invocation remains server-side
- Secrets are not exposed to browser code
- Authentication and authorization are enforced server-side
- CORS and rate limits are defined
- Session or conversation model is documented
- Loading, error, retry and timeout behavior is defined
- Observability and audit requirements are documented
- Tests cover UI, API, security and AI agent behavior

---

# Exit Criteria

- Definition of Ready is satisfied before implementation
- API contract is approved before frontend/backend work diverges
- Security review accepts browser/backend/agent boundaries
- PR plan separates contracts, backend, frontend, integration and tests
