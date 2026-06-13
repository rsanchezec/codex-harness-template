# Pull Request Chain

Purpose

Break large implementations into small reviewable pull requests.

---

# Rules

Target:

- Less than 400 changed lines
- Single responsibility
- Easy review
- Easy rollback

---

# Chain Strategy

Example:

PR1
Contracts

PR2
Domain Models

PR3
Services

PR4
API

PR5
Integration

PR6
Tests

PR7
Documentation

---

# Review Requirements

Each PR must:

- Build successfully
- Pass tests
- Have clear purpose
- Avoid unrelated changes

---

# Risk Management

Avoid:

- Massive PRs
- Mixed responsibilities
- Hidden side effects

---

# Deliverables

Generate:

/docs/pr-plan/[feature-name].md

Include:

- PR Sequence
- Scope
- Dependencies
- Estimated Size
- Review Notes

---

# Exit Criteria

Every feature larger than one logical change must be split into chained PRs.