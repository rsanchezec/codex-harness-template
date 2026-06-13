# .codex/workflows/feature-delivery.md

# Feature Delivery Workflow

Use this workflow for new features.

1. Use Product Analyst
2. Apply SDD skill
3. Use Architect
4. Apply Architecture Review skill
5. Use Security Reviewer
6. Apply Security Review skill
7. Use Test Engineer
8. Apply TDD skill
9. Apply PR Chain skill
10. Implement only after approval

For React, Next.js or browser-based features:

1. Use Frontend Engineer
2. Use API Integration Engineer when the browser calls a backend API
3. Apply Web Agent Integration skill when the frontend interacts with an AI agent, backend gateway, BFF or Azure AI Foundry
4. Keep Foundry and other privileged service calls server-side

Required artifacts:

- /docs/specs/[feature].md
- /docs/designs/[feature]-architecture.md
- /docs/designs/[feature]-security-review.md
- /docs/designs/[feature]-implementation-plan.md
- /docs/adr/[number]-[decision].md
- /docs/tests/[feature]-test-plan.md
- /docs/pr-plan/[feature].md

Additional artifacts for React, Next.js or web-to-agent features:

- /docs/designs/[feature]-web-agent-integration.md
- /docs/designs/[feature]-api-contract.md
- /docs/tests/[feature]-web-agent-test-plan.md

Approval checklist:

- Specification status is Approved or accepted with tracked risks
- Technical design links to relevant ADRs
- Security risks have mitigations or explicit acceptance
- Test plan covers acceptance criteria and critical failure modes
- PR plan keeps each PR focused, reviewable and rollback-friendly
- Open questions have owner, impact and next action

Exit criteria:

- Feature has a Definition of Ready before implementation
- Feature has a Definition of Done before final review
- Every skipped workflow step is documented with risk
