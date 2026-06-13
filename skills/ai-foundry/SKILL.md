# Microsoft AI Foundry Delivery

Purpose

Provide a standard delivery process for Microsoft AI Foundry solutions.

Use this skill whenever the solution involves:

- AI Agents
- RAG
- Azure OpenAI
- AI Search
- Conversational AI
- AI Assistants
- Enterprise AI Platforms

---

# Delivery Workflow

1. Discovery
2. Use Case Definition
3. Agent Design
4. RAG Design
5. Tool Design
6. Security Review
7. Evaluation Design
8. Observability Design
9. Deployment Design
10. Production Readiness Review

---

# Discovery

Identify:

- Business Goal
- Users
- Expected Outcomes
- Risks
- Constraints

---

# Agent Design

Define:

- Agent Responsibilities
- Agent Boundaries
- Agent Permissions
- Agent Tools
- Agent Escalation Paths

Never create agents with excessive permissions.

---

# Tool Design

Define:

- Available Tools
- Tool Permissions
- Validation Rules
- Audit Requirements

Prefer:

- Least Privilege
- Explicit Authorization

---

# RAG Design

Define:

- Data Sources
- Chunking Strategy
- Embedding Strategy
- Retrieval Strategy
- Metadata Strategy
- Security Trimming

Prefer:

- Azure AI Search
- Hybrid Search
- Metadata Filters

---

# Evaluation Design

Always define:

- Groundedness
- Relevance
- Hallucination Rate
- Tool Call Accuracy
- Security Validation

Create evaluation datasets before production.

---

# Observability

Always define:

- Prompt Monitoring
- Tool Monitoring
- Cost Monitoring
- Evaluation Monitoring

Prefer:

- Azure Monitor
- Application Insights
- Foundry Evaluations

---

# Security

Verify:

- Agent Permissions
- Tool Authorization
- Data Access Controls
- Tenant Isolation

Never trust prompts as security boundaries.

---

# Deployment

Define:

- Dev Environment
- Test Environment
- Production Environment

Include:

- Rollback Strategy
- Monitoring
- Versioning

---

# Production Readiness Checklist

Verify:

- Evaluation completed
- Security review completed
- Monitoring configured
- Rollback strategy defined
- Cost controls defined

---

# Output

Generate:

- AI Solution Design
- Agent Design
- RAG Design
- Evaluation Plan
- Security Considerations
- Deployment Plan

---

# Deliverables

/docs/specs
/docs/designs
/docs/adr

Create:

- AI Architecture
- Agent Architecture
- RAG Design
- Evaluation Plan
- Deployment Plan