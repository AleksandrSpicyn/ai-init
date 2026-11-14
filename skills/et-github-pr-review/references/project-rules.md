# Review Lenses

## Architecture and Ownership

Read repository instructions and nearby code. Verify actual dependency direction,
entrypoints, ownership and registration. Actions, Tasks, processors, repositories
and dedicated admin trees are optional architectural choices; report violations
only when the target has adopted the relevant rule or the dependency causes a
concrete defect. Do not impose another application's hierarchy.

## Runtime Behavior and Contracts

Trace routes, middleware, validation, business behavior, persistence, serializers
and callers. Check error paths, conditional response fields, pagination, eager
loading, authorization and missing side effects on rejected writes. Compare
changed API documentation and frontend/integration consumers with real output.

## Packages

Confirm installed versions, custom models/config and wrappers. For DTOs review
validation, casts, defaults and context. For media review storage, visibility,
conversion and cleanup. For settings review migrations, discovery and cache
lifecycle. For permissions review guards, scopes, policies/middleware and tests.
Package wrappers and local enums are not required where absent.

## Data and Side Effects

Review migrations, indexes, rollback, production-data compatibility and deployment
order. Imports/exports need scope, validation, duplicate/retry behavior and
failure cleanup. Side effects requiring committed data must respect transaction
boundaries. Check retries, idempotency and cache invalidation for every changed
write path, including queues and events.

## Tests

Require meaningful coverage for changed behavior and relevant failure modes.
Use configured test directories and style. Prefer factories/states and realistic
relations; do not mock internal layers away when they are the behavior under
review. Status/count-only assertions do not prove changed fields or side effects.
Respect legitimate unit boundaries and existing helper conventions.

## Security and Persistent Runtime

Require evidence for a realistic access, integrity, confidentiality or availability
risk. Review current actor/tenant scope, private files, secrets, raw input/SQL,
queue payloads and cache identity. Under persistent workers inspect request-state
leaks and lifecycle/reload behavior. Concurrency needs independent operations,
compatible runtime behavior and measured benefit over a realistic sequential path.

## Naming, Style and Tooling

Cite a concrete local rule or failing tool output for convention findings. Match
local language, naming and formatting instead of enforcing personal preferences.
Do not rename external contracts incidentally. AI/MCP/skill changes need portable
configuration, accurate triggers and verified references, without workstation
paths or secrets. Generated output is evidence to review, not automatic proof.

## Documentation

Compare relevant documentation with actual code and tests. Load a local module
README when the changed contract is documented there. Global docs and green
quality gates do not establish that local contracts remain correct.
