<!--
Sync Impact Report
Version change: unratified Spec Kit template -> 1.0.0 draft
Modified principles: placeholders -> Central Sources; Spec-Bounded Delivery;
  Backend-Owned Contracts; Server-Safe Frontend; Scoped, Verified Changes
Added sections: Technical Constraints; Development Workflow
Removed sections: template examples and unfilled placeholders
Follow-up TODO: RATIFICATION_DATE requires project owner confirmation.
-->
# HireUS Frontend Constitution

## Core Principles

### I. Central Sources

Business requirements, shared architecture, and cross-repository decisions MUST
be verified through CNPM-Docs using the precedence in PROJECT_SOURCES.md.
Proposals and plans MUST remain labeled as proposed until confirmed. Local
Frontend documents may link to sources but MUST NOT duplicate product
requirements or project plans.

### II. Spec-Bounded Delivery

Feature work MUST follow accepted specifications and their acceptance criteria.
Agents MUST NOT infer product behavior beyond confirmed sources. If a source
changes, verify the affected requirement before changing implementation. If
authoritative sources conflict, pause only work that depends on the conflict
and request confirmation.

### III. Backend-Owned Contracts

Backend owns the authoritative REST API contract; Frontend is a consumer.
Frontend MUST NOT invent endpoints, methods, request or response shapes, errors,
or authentication behavior. Contract changes require agreement with Backend.
Record the source repository-relative path and revision when a task depends on
a contract snapshot. Do not create OpenAPI schemas before the API is designed.

### IV. Server-Safe Frontend

Preserve the verified Next.js App Router and strict TypeScript setup. Server
Components are the default; use Client Components only for browser APIs and
interactive state that require them. Never hardcode secrets or expose
privileged credentials to the browser. Client-side authorization is not a
security boundary. Add dependencies or state-management layers only for a
demonstrated requirement.

### V. Scoped, Verified Changes

Make the smallest change that satisfies the accepted task. Do not change
unrelated application behavior, update CNPM-Docs from a Frontend task, or
commit or push without an explicit request. Report changed files, verification
results, and unresolved requirements or contract questions.

## Technical Constraints

- The verified application stack is Next.js 16.4.3, React 19.3.0,
  TypeScript 5.9.3, npm, App Router, and src/.
- Use the configured @/* alias for imports from src/.
- Available checks are npm run lint, npx tsc --noEmit, and npm run build.
- No test command or test framework is currently configured. Do not add one
  outside a task that requires it.
- The API contract ownership boundary is documented in contracts/README.md.

## Development Workflow

- Read AGENTS.md and the relevant repo-local skill before applicable work.
- For business features, read PROJECT_SOURCES.md and the required CNPM-Docs
  sources before planning or implementation.
- For Spec Kit work, use the installed .agents/skills/speckit-* workflows.
  Do not regenerate Spec Kit integration files as part of feature work.
- Verify applicable loading, empty, error, and success states, and run the
  checks requested by the task.
- Shared requirement or decision updates belong in CNPM-Docs; report the
  specific proposed change for that repository.

## Governance

This constitution governs Frontend engineering and local Spec Kit artifacts.
CNPM-Docs remains authoritative for product requirements and shared project
decisions. The constitution is a draft until the project owner confirms its
ratification date.

Amendments MUST state the reason and impact, preserve the source-of-truth
boundary, increment the version, and receive project-owner review. Use
MAJOR for incompatible governance changes, MINOR for new principles or
materially expanded policy, and PATCH for non-semantic clarification. Review
feature specifications against these principles before planning and
implementation.

**Version**: 1.0.0 (draft) | **Ratified**: TODO(RATIFICATION_DATE): pending owner confirmation | **Last Amended**: 2026-10-27
