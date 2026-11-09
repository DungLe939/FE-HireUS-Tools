# HireUS Frontend Constitution

## Core Principles

### I. Central Sources

CNPM-Docs is the authoritative source for business requirements and confirmed
cross-repository decisions. For business-related work, use the source order and
access rules in PROJECT_SOURCES.md. Treat proposals and plans according to their
stated status; they do not prove implementation. Frontend documents may link to
central sources but MUST NOT duplicate product requirements or shared project
plans. Do not update CNPM-Docs from a Frontend task; identify proposed shared
document changes for that repository.

### II. Spec-Bounded Delivery

A clear, direct user request authorizes work only within its stated scope and may
be sufficient requirements for a bounded change. Significant features or changes
to product behavior MUST have sufficiently clear requirements and acceptance
criteria before implementation. Bug fixes and small maintenance changes do not
require the full Spec Kit workflow.

Agents MUST NOT infer product behavior beyond authoritative sources, explicit
user instructions, and accepted specifications. Generic Spec Kit assumptions do
not override project sources or rules. Small, reversible technical assumptions
that do not affect product behavior may be used when stated. Missing
authentication, data semantics, permissions, or API contract details MUST be
clarified before implementing dependent behavior. If a source changes or
authoritative sources conflict, verify the relevant requirement and pause only
work that depends on the unresolved point.

### III. Backend-Owned Contracts

Backend owns the authoritative REST API contract. Frontend consumes a contract
that the repositories have agreed on and MUST NOT invent endpoint paths,
methods, DTOs, request or response schemas, error formats, or authentication
behavior. If a required contract detail is missing, do not implement behavior
that depends on it until Backend or the user confirms it.

OpenAPI is the preferred format proposed for consideration, not a mandatory
project decision. API versioning, error format, and authentication policies
remain pending decisions. Contract location, revision tracking, and coordination
procedures belong in contracts/README.md.

### IV. Server-Safe Frontend

Preserve the verified Next.js App Router and TypeScript configuration. Use Server
Components by default; introduce Client Components for browser APIs or interaction
that requires them. Never hardcode secrets or expose privileged credentials to
the browser. Client-side authorization is for user experience and does not
replace Backend authorization. Add dependencies, shared abstractions, or
state-management layers only when a demonstrated requirement justifies them.

### V. Scoped, Verified Changes

Make only changes needed for the accepted task and preserve unrelated behavior.
A Frontend task MUST NOT modify CNPM-Docs or other repositories. Do not commit or
push unless explicitly requested. Report the files changed, checks actually run,
and unresolved requirements or decisions.

### VI. Learning-Oriented Development

For significant code changes, explain in Vietnamese the goal and approach,
important files and their roles, the main processing flow, notable logic or
technical concepts, relevant trade-offs, and how to verify the result. Keep
explanations concise for obvious changes. Do not put long tutorial material in
production source code.

## Technical Constraints

- The verified Frontend baseline is Next.js 16.4.3, React 19.3.0, TypeScript
  5.9.3 resolved, npm, App Router under src/, and the configured @/* alias.
  AGENTS.md records current repository setup and commands. Technologies listed
  as planned in CNPM-Docs MUST NOT be described as implemented without repository
  evidence.
- Frontend changes MUST run applicable checks configured in this repository,
  including lint, TypeScript typecheck, and build as appropriate. This repository
  currently has no test command or framework; do not assume one exists or
  introduce a framework or coverage threshold without an approved task or team
  decision.
- For coordinated Backend changes, Backend is responsible for applicable Jest
  tests, TypeScript typecheck, and build checks in its repository. Do not report a
  check as passing unless it was run or its result was otherwise verified.
- The Proposal's coverage target of at least 70% is a planning target, not a
  mandatory quality gate. This Constitution sets no coverage threshold.

## Development Workflow

Use each document for its defined role: this Constitution for durable principles;
AGENTS.md for repository instructions and development workflow;
PROJECT_SOURCES.md for finding and handling central requirements;
contracts/README.md for API contract procedures; task-specific SKILL.md files for
specialized workflows; and CNPM-Docs for shared product and cross-repository
documentation. Keep procedural detail in its owning document instead of
duplicating it here. Project rules and authoritative sources take precedence
over generic skill assumptions; do not modify upstream Spec Kit skills to enforce
local policy.

## Governance

This Constitution governs engineering work and local Spec Kit artifacts in the
HireUS Frontend repository. It defines Frontend responsibilities at the Backend
boundary but does not prescribe Backend's internal architecture. CNPM-Docs
remains authoritative for shared product requirements and confirmed
cross-repository decisions.

This document remains Draft / Unratified until the project owner explicitly
approves it. Do not record a ratification date before that approval. Amendments
MUST state their reason and impact, follow the version policy below, and receive
project-owner review. Use MAJOR for incompatible changes to existing principles,
MINOR for a new principle or materially expanded policy, and PATCH for
clarifications or non-semantic refinements. Draft versions use a SemVer
prerelease suffix; ratification removes the suffix and records the approved date.
Review applicable changes against these principles without imposing the full
Spec Kit workflow on small fixes.

**Version**: 1.1.0-draft.1 | **Status**: Draft / Unratified | **Ratified**: Not ratified | **Last Amended**: 2026-10-28
