# ADR-0001: Formalize Delivery Artifacts

Metadata

| Field | Value |
| --- | --- |
| Status | Accepted |
| Date | 2026-06-13 |
| Decision Owner | Harness Orchestrator |
| Deciders | Architect, Security Reviewer, Test Engineer, Code Reviewer |
| Related Design | `docs/designs/harness-architecture-review.md` |

## Status

Accepted

## Context

The harness requires documentation before implementation, but the initial repository structure only included `docs/specs`, `docs/designs` and `docs/adr`. Other workflows and specialist roles also referenced test plans, PR plans, operations artifacts and review reports.

Without a complete and consistent artifact map, Codex can follow the intent of the harness inconsistently, and reviewers have less evidence to evaluate readiness.

## Decision

Formalize the delivery artifact structure as:

* `docs/specs`
* `docs/designs`
* `docs/adr`
* `docs/tests`
* `docs/pr-plan`
* `docs/operations`
* `docs/reviews`

Every non-trivial change should link its related specification, design, ADRs, test plan, implementation plan, PR plan and final review when applicable.

## Options Considered

| Option | Pros | Cons | Decision |
| --- | --- | --- | --- |
| Keep only the original three folders | Simple structure | Inconsistent with workflows; weak test and review traceability | Rejected |
| Add only missing test and PR folders | Fixes immediate workflow mismatch | Does not cover operations and review outputs required by specialists | Rejected |
| Formalize full artifact map | Strong traceability and delivery governance | More documentation overhead | Accepted |

## Consequences

* Workflows and templates can reference stable artifact locations.
* Reviews become easier to audit.
* Contributors have clearer expectations before implementation.
* Small changes may need explicit skipped-gate notes to avoid unnecessary process overhead.

## Security and Operational Impact

Security and operational readiness become first-class delivery artifacts instead of implicit review topics.

## Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Documentation burden increases | Slower delivery for small changes | Allow lightweight path with documented skipped gates |
| Artifact links become stale | Review evidence becomes unreliable | Update related artifact links during review |

## Reversal or Revisit Criteria

Revisit this decision if the harness becomes too heavy for the project team, or if a future tool provides automated artifact tracking that replaces folder-based governance.

## Related Documents

* `AGENTS.md`
* `.codex/workflows/feature-delivery.md`
* `docs/designs/harness-architecture-review.md`
