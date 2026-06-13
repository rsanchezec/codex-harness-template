---
name: web-agent-integration
description: Design and implement safe web application integrations where React, Next.js, Vite or other browser frontends interact with backend APIs, BFFs, Azure AI Foundry agents, AI chat experiences, RAG, tools, or agent gateways. Use for: React chat UI, Next.js frontend to AI agent, backend gateway to Foundry, web-to-agent API contracts, frontend/backend AI security boundaries, CORS, sessions, streaming, observability and tests.
---

# Web Agent Integration

Purpose

Guide delivery of web applications that connect a browser frontend to backend APIs and AI agents safely.

Use this skill when the solution includes:

- React
- Next.js
- Vite
- Browser-based chat UI
- Backend API or BFF
- Azure AI Foundry agent invocation
- AI support, assistant or agent experiences
- Frontend-to-backend contracts

---

# Core Rule

Never call Azure AI Foundry or privileged AI services directly from browser code.

Preferred boundary:

```text
React or Next.js UI
  -> Backend API or BFF
      -> Azure AI Foundry Agent
          -> Tools, knowledge and model runtime
```

The frontend sends user intent. The backend enforces security and invokes the agent.

---

# Workflow

1. Identify frontend framework
2. Identify rendering model
3. Define backend API boundary
4. Define AI agent invocation boundary
5. Define request and response contracts
6. Define authentication and authorization
7. Define session and conversation model
8. Define streaming or non-streaming behavior
9. Define error, retry and timeout handling
10. Define CORS and rate limiting
11. Define observability and audit logging
12. Define tests and evaluation gates
13. Define PR split

---

# Frontend Design

Always define:

- Framework: React, Vite, Next.js App Router, Next.js Pages Router or other.
- Rendering: CSR, SSR, SSG or hybrid.
- Main user flows.
- Component boundaries.
- API client module.
- Loading states.
- Error states.
- Empty states.
- Retry and cancellation behavior.
- Accessibility expectations.

Avoid:

- Secrets in frontend environment variables.
- Azure credentials in browser code.
- Direct browser calls to Foundry project endpoints.
- UI-only authorization checks.

---

# Backend API Design

Always define:

- Endpoint names and methods.
- Request schema.
- Response schema.
- Error schema.
- Authentication requirement.
- Authorization checks.
- Input validation.
- Output filtering.
- Rate limiting.
- CORS policy.
- Timeout policy.
- Audit logging.

Recommended minimal chat endpoint:

```text
POST /api/chat
```

Request:

```json
{
  "message": "User question",
  "conversationId": "optional-existing-session"
}
```

Response:

```json
{
  "message": "Agent response",
  "conversationId": "session-id",
  "requestId": "trace-id"
}
```

---

# Foundry Agent Integration

For Azure AI Foundry integrations, always define:

- Project endpoint source.
- Agent name source.
- Agent version policy.
- Credential strategy.
- Local development auth.
- Production auth.
- User-to-agent authorization rules.
- Conversation/session mapping.
- Tool permission boundaries.
- Trace and evaluation requirements.

Preferred credential strategy:

- Local development: Azure CLI or developer credential when appropriate.
- Production: Managed Identity or approved service principal.

Never:

- Expose `FOUNDRY_PROJECT_ENDPOINT` as a browser-consumed public variable if it reveals internal topology.
- Store Azure credentials in React or Next.js client components.
- Treat prompts as authorization.
- Let the browser choose arbitrary agent names, versions or tools.

---

# React and Next.js Decision Points

Use React SPA or Vite when:

- The backend is a separate API service.
- SSR is not needed.
- The app is mostly authenticated operational UI.

Use Next.js when:

- API routes or server actions are useful as a BFF.
- SSR or hybrid rendering is needed.
- The project benefits from colocated server and frontend code.

For Next.js:

- Keep Foundry calls in server-only code.
- Do not invoke Foundry from client components.
- Keep secrets in server environment variables only.
- Use API routes, route handlers or server actions as the trusted boundary.

---

# Security Review Checklist

Verify:

- Browser does not hold secrets.
- Backend enforces authorization.
- CORS only allows approved origins.
- Inputs are validated before agent invocation.
- Outputs are filtered for sensitive data when needed.
- Requests are rate limited.
- Tool calls are authorized server-side.
- Audit logs capture user, action, timestamp and request ID.
- Error responses do not leak internal details.

---

# Testing Requirements

Create:

- Frontend component tests.
- API contract tests.
- Backend integration tests for Foundry invocation.
- Authentication and authorization tests.
- CORS and rate limit tests when applicable.
- Regression tests for critical user flows.
- AI evaluation cases for groundedness, hallucination and tool-calling when applicable.

---

# Pull Request Split

Recommended sequence:

1. Contracts and documentation
2. Backend gateway
3. Frontend UI
4. Foundry integration
5. Tests and evaluation
6. Observability and operations
7. Documentation cleanup

---

# Deliverables

Generate:

/docs/designs/[feature]-web-agent-integration.md
/docs/designs/[feature]-api-contract.md
/docs/tests/[feature]-web-agent-test-plan.md
/docs/pr-plan/[feature].md

When needed:

/docs/adr/[number]-[decision].md
/docs/operations/[feature]-operations.md

Include:

- Frontend framework decision
- Backend API boundary
- Foundry invocation strategy
- Auth and authorization strategy
- Session model
- Error handling
- Observability
- Test strategy
- PR split

---

# Exit Criteria

The integration is ready for implementation when:

- The browser/backend/Foundry boundary is explicit.
- Secrets are server-side only.
- API contract is documented.
- Auth and CORS rules are documented.
- Session/conversation model is documented.
- Test plan covers frontend, API and agent behavior.
- PR plan separates contracts, backend, frontend and tests.
