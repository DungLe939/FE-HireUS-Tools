---
name: frontend-quality
description: Use for read-only reviews of Next.js, React, TypeScript, UI accessibility, performance, forms, or frontend API integration.
---

# Frontend Quality Review

1. Inspect the requested change and the directly affected callers, routes, and styles. For business behavior, use PROJECT_SOURCES.md and verify the relevant source.
2. Review runtime correctness, TypeScript safety, Server/Client Component boundaries, rendering and performance, accessibility, form states, API error handling, and authentication boundaries as applicable.
3. Compare API usage with the approved Backend contract. Report missing contract details as unknown; do not infer a fix.
4. Check whether relevant existing tests cover changed behavior and whether the requested verification was run. Do not claim tests passed without evidence.
5. Return actionable findings first, each with severity, file and line, evidence, and user impact. Separate confirmed defects from questions or optional improvements.
6. Do not edit files during a review unless the user also requested fixes.
