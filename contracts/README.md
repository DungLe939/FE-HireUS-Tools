# REST API Contract Boundary

Backend is the authoritative owner of the REST API contract. Frontend consumes the approved contract and does not define or modify its source.

Before integrating an endpoint, identify the approved contract file in the Backend repository and record its repository-relative path plus the source commit, tag, or revision in the feature specification or change report.

If the contract does not specify the method, path, request and response shapes, error behavior, or authentication requirements needed by the task, leave those details unresolved and request Backend confirmation. Do not fabricate DTOs, endpoint conventions, or OpenAPI schemas.

Coordinate contract changes with Backend. Frontend may implement consumer types and adapters from an approved contract, but must not silently change the source contract or make a local copy that can drift.

This directory currently contains ownership guidance only; it does not contain an API schema.
