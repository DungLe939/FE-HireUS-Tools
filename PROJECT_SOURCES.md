# Central Project Sources

## Official documentation repository

CNPM-Docs is the source of truth for business requirements, the Project Proposal, shared project plans, cross-repository design, and confirmed project decisions.

## Read order

Follow the precedence rules in the first source before relying on the others:

1. CNPM-Docs: .agents/rules/source-of-truth.md
2. CNPM-Docs: docs/Week01/Submission/Project_Proposal.md
3. CNPM-Docs: docs/PROJECT_CONTEXT.md
4. CNPM-Docs: docs/Week01/Team_Decision/Material/HireUS_Implementation_Plan.md

The Project Context and Implementation Plan are navigation or summary documents; they do not override the confirmed source rules or Proposal. Treat plans as proposed work, not evidence that a feature has shipped. If authoritative sources conflict and the replacement is unclear, report the conflict and ask for confirmation.

The source rules also identify docs/Week01/Submission/Project_Proposal.html as the checked HTML counterpart to the Markdown Proposal. Compare both if they disagree; do not silently choose one when the conflict is unresolved.

## Providing sources to Codex

When CNPM-Docs is available in the workspace, read the relevant files at the paths above. Otherwise, provide the required files or make the repository accessible. If the sources cannot be accessed, say that the business information is unverified, request the relevant path or files, and continue only with independent technical work. Do not infer missing business requirements from old summaries or examples.

## Decision status

Label information as confirmed, proposed, implemented, or undecided. A proposal or implementation plan is not proof of implementation. Verify implementation in the application repository before describing it as shipped. Do not promote an AI suggestion into a project decision.

## Source revision

When a task, specification, or review depends on a particular documentation snapshot, record the CNPM-Docs commit or source revision together with the repository-relative paths consulted. If the Docs working tree is dirty, say so and identify the relevant local changes or use a supplied snapshot. Do not put machine-specific absolute paths in tracked files.

## Ownership

Do not edit CNPM-Docs while working in Frontend. If a shared requirement, plan, or decision needs an update, report the proposed change for the Docs repository. The Backend-owned API contract is referenced separately in contracts/README.md.
