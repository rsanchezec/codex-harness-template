# .codex/workflows/bug-fix.md

# Bug Fix Workflow

Use this workflow for defects.

1. Reproduce the bug
2. Identify expected behavior
3. Identify actual behavior
4. Find root cause
5. Create failing test
6. Fix minimally
7. Run regression tests
8. Review risk

Required artifacts when needed:

- /docs/tests/[bug]-regression-plan.md
- /docs/adr/[number]-[decision].md

Exit criteria:

- Root cause is documented
- Regression test or explicit manual validation exists
- Fix scope is minimal and reversible
- Risk of recurrence is reviewed
- Release or rollback notes are documented when production impact exists
