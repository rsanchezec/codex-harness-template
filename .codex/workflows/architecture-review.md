# Architecture Review Workflow

Purpose

Review architecture before implementation to identify risks, tradeoffs and long-term impacts.

Use this workflow for:

* New systems
* Major architecture changes
* SaaS platforms
* AI platforms
* ERP integrations
* Cloud migrations
* Enterprise solutions

---

# Workflow

1. Review Requirements
2. Review Existing Architecture
3. Identify System Boundaries
4. Review Components
5. Review Integrations
6. Review Security Architecture
7. Review Scalability
8. Review Observability
9. Review Deployment Model
10. Review Risks and Tradeoffs
11. Create ADR Recommendations

---

# Specialists

Required:

* Architect

Recommended:

* Security Reviewer
* DevOps Engineer
* AI Foundry Engineer (for AI solutions)

---

# Skills

Use:

* Architecture Review

Optional:

* Security Review
* AI Foundry

---

# Review Areas

Evaluate:

* Maintainability
* Scalability
* Reliability
* Security
* Performance
* Cost
* Operational Complexity

---

# Deliverables

Generate:

/docs/designs/[solution]-architecture-review.md

When needed:

/docs/adr/[number]-[decision].md

Recommended supporting artifacts:

* /docs/operations/[solution]-production-readiness.md
* /docs/reviews/[solution]-review.md

Include:

* Findings
* Risks
* Tradeoffs
* Recommendations
* ADR Proposals

---

# Exit Criteria

Architecture is considered approved when:

* Major risks are documented
* Tradeoffs are documented
* Security concerns are reviewed
* Deployment model is defined
* Observability strategy is defined
* ADRs are created for major decisions

Approval Record

Every architecture review should record:

* Review status
* Review date
* Reviewer roles
* Conditions for approval
* Residual risks
