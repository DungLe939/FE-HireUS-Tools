---
name: nextjs-feature
description: Use when implementing a scoped page, route, component, form, or frontend feature in this Next.js App Router repository.
---

# Next.js Feature Workflow

1. Read the feature specification and acceptance criteria. For business requirements, follow PROJECT_SOURCES.md and consult the relevant CNPM-Docs sources.
2. Inspect the current route, components, styles, and data flow before choosing boundaries. Reuse established patterns and avoid new dependencies or architecture without a concrete need.
3. Decide which parts can remain Server Components and where browser interaction requires a Client Component. Identify applicable loading, empty, error, and success states.
4. Keep the implementation within confirmed requirements and acceptance criteria. Do not infer extra features or guess an API contract. Recheck the source if it has changed.
5. Implement only the requested behavior and keep unrelated files untouched.
6. Run relevant existing tests when requested or required by the task, then run the requested lint, type, and build checks.
7. Report the behavior implemented, files changed, checks run, and any unresolved product or API questions.
