# Repository Governance

Metadata

| Field | Value |
| --- | --- |
| Owner | Harness Orchestrator |
| Status | Approved |
| Date | 2026-06-13 |
| Scope | Git, branch naming, pull request and repository hygiene conventions |

## Git Usage

This repository is initialized as a Git repository. All implementation work should happen on branches and follow the PR chain plan when the change is larger than one logical unit.

## Branch Naming

Use lowercase kebab-case branch names:

* `feature/[feature-name]`
* `bugfix/[bug-name]`
* `docs/[documentation-change]`
* `chore/[maintenance-change]`
* `review/[review-topic]`

## Pull Request Expectations

Each pull request should:

* Have one responsibility.
* Prefer fewer than 400 changed lines.
* Link to related docs in `docs/specs`, `docs/designs`, `docs/tests` and `docs/pr-plan`.
* Include test evidence when applicable.
* Document rollback steps.
* Avoid unrelated changes.

## Secret Hygiene

Do not commit secrets, credentials, private keys, certificates or environment-specific configuration. Use `.env.example` for safe examples and keep real values outside the repository.

## Review Hygiene

Reviewers should check:

* Requirements traceability.
* Architecture and ADR compliance.
* Test coverage.
* Security controls.
* Operational readiness.
* Rollback path.
