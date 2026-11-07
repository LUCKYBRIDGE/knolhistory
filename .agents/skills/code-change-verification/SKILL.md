---
name: code-change-verification
description: Verify non-trivial knolhistory code changes before completion. Use after feature work, bug fixes, refactors, data-model changes, routing changes, or UI interaction changes.
---

# Code Change Verification

1. Read `AGENTS.md` and the affected architecture/product docs.
2. Inspect the diff and identify the user-visible behavior that changed.
3. Run the repository's available format, lint, type-check, unit-test, and build commands that apply.
4. Test the changed interaction at least once through its expected user path.
5. Check loading, empty, error, and unavailable states when relevant.
6. Check keyboard use and responsive layout for UI changes.
7. For content/data changes, run schema validation when available.
8. For historical content changes, also invoke the `history-content-review` workflow.
9. Report exactly what was verified and what could not be verified.

If the repository does not yet have an automated verification command, do not invent one. Record the missing check as a project gap.
