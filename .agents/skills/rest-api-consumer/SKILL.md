---
name: rest-api-consumer
description: Use when connecting a Frontend route or component to an approved REST API owned by the Backend repository.
---

# REST API Consumer Workflow

1. Read contracts/README.md and locate the approved API contract in the Backend repository. Record its relative path and source revision for the task.
2. Confirm the HTTP method, path, request and response types, error behavior, and authentication requirements from that contract.
3. If any required contract detail is missing or inconsistent, stop the API-specific design and ask Backend or the user for confirmation. Do not infer DTOs or endpoint conventions.
4. Design the smallest typed consumer boundary that fits the current Next.js server/client architecture. Do not add an API library or state-management dependency without a demonstrated need.
5. Handle timeouts, network failures, HTTP errors, and session data according to the approved contract. Keep secrets and privileged operations on the server; client checks do not replace Backend authorization.
6. Test mapping and error handling with the existing project setup when requested. Do not create a speculative OpenAPI file or change the Backend contract from Frontend.
7. Report the contract source and revision, files changed, validation performed, and any contract changes that need agreement with Backend.
