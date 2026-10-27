# HireUS Frontend Agent Instructions

## Purpose and verified stack

This repository contains the HireUS Tools frontend. Product requirements and cross-repository decisions live in CNPM-Docs; use PROJECT_SOURCES.md to locate and verify them.

- Next.js 16.4.3 with App Router under src/app.
- React 19.3.0 and TypeScript 5.9.3 resolved by package-lock.json.
- npm is the package manager. The @/* alias maps to src/*.
- The current app uses global CSS and CSS Modules. Tailwind is not configured.
- There is no test script or test framework in package.json.

## Product sources and scope

- For business-related work, follow PROJECT_SOURCES.md and read the relevant CNPM-Docs source before planning or editing.
- Distinguish confirmed requirements from proposals and plans. Do not infer features beyond confirmed sources and the task's acceptance criteria.
- If the source changes, verify the relevant requirement again before changing implementation.
- Do not update CNPM-Docs while working in Frontend. If shared documentation needs a change, report the exact change for the Docs repository.

## Frontend implementation

- Preserve the existing App Router and strict TypeScript configuration.
- Keep route-specific UI close to its route. Add shared components only when reuse warrants them; avoid creating architecture or state-management layers without a concrete need.
- Use Server Components by default. Add Client Component boundaries only for browser APIs, local interaction state, or event handlers that need them.
- Prefer server-side data access where it fits the route. Keep client-side fetching for genuinely interactive browser flows.
- Follow the matching repo-local skills in .agents/skills. Use the Vercel React/Next.js guidance when it applies, without treating performance examples as requirements.

## REST API and security

- Backend owns the authoritative REST API contract; Frontend consumes it. Follow contracts/README.md.
- Do not invent endpoint paths, HTTP methods, request/response schemas, error shapes, or authentication behavior. Ask for the approved Backend contract when it is missing.
- Never hardcode API keys, secrets, or access tokens. Keep credentials and privileged operations on the server.
- Client-side authorization is for user experience only; Backend authorization remains authoritative.
- Authentication is not implemented or specified in this repository. Do not add an auth flow without an approved task and contract.

## Quality and completion

Available checks:

- npm run lint
- npx tsc --noEmit
- npm run build

No test command is currently configured. Use an existing relevant test suite when the task requests tests or verification; do not add a test framework as part of an unrelated change.

A change is complete when it meets its accepted scope, preserves the established component and server/client boundaries, handles applicable loading/empty/error/success states, and passes the requested checks. Report changed files, validation results, and unresolved source or contract questions.

## Change boundaries

- Change only files needed for the requested task. Do not modify other repositories, generated Spec Kit integration files, or unrelated application behavior.
- Do not commit or push unless the user explicitly asks.
- When reviewing, report evidence and file locations; do not edit unless implementation was requested.
