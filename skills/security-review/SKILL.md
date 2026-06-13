# Security Review

Purpose

Identify security risks before implementation.

Security must be enforced in architecture and systems.

Never rely on prompts or UI for security.

---

# Review Process

1. Authentication Review
2. Authorization Review
3. Data Protection Review
4. API Security Review
5. Infrastructure Security Review
6. Secrets Review
7. Audit Review
8. Compliance Review

---

# Authentication

Verify:

- MFA
- SSO
- Token management
- Session management

Preferred:

- Microsoft Entra ID
- OAuth 2.0
- OpenID Connect

---

# Authorization

Verify:

- RBAC
- Resource ownership
- Tenant isolation

Never trust:

- Frontend validation
- Hidden controls

---

# Data Protection

Verify:

- Encryption at rest
- Encryption in transit
- Data ownership
- Data retention

---

# Multi-Tenant Security

Always evaluate:

- Tenant isolation
- Cross-tenant access
- Administrative boundaries

Critical Risk:

Tenant A accessing Tenant B data.

---

# API Security

Verify:

- Authentication
- Authorization
- Input validation
- Output filtering
- Rate limiting

---

# AI Security

Review:

- Prompt Injection
- Tool Abuse
- Data Leakage
- Hallucinations
- RAG Security

Never allow:

- Direct model access to ERP
- Direct model access to databases
- Unrestricted tools

---

# Secrets

Prefer:

- Azure Key Vault
- Managed Identity

Never store:

- Secrets in source code
- Secrets in repositories

---

# Output

Generate:

- Security Findings
- Risk Assessment
- Recommended Controls
- Residual Risks

---

# Deliverables

/docs/designs
/docs/adr

Create:

- Security Review
- Threat Model
- Risk Assessment