---
name: et-pest-testing
description: Use when adding, editing, reviewing, or fixing Pest tests, factories, endpoint assertions, permission coverage, scoped cases, or fake assertions in modular Laravel projects.
---

# Pest Testing

## Adapting to the Target Repository

Read the target repository's instructions, dependency manifests and lockfiles,
configuration, and nearby implementations before applying this skill. Discover
actual source/test paths, namespaces, commands, languages, guards, and contracts;
no particular directory layout or application API is required.

Repository rules and installed package versions determine concrete APIs and
conventions. Architectural examples below apply only when the target already
uses that pattern; do not add layers, wrappers, helpers, or dependencies merely
to satisfy this skill. If local guidance is absent, prefer framework defaults
and the smallest change consistent with nearby code.

Read local documentation when it exists and is relevant; verify it against
current code. Other skills are optional companions when installed, not required
dependencies. Keep verification proportional to the changed behavior.

## Overview

Follow local Pest rules from the repository testing documentation and AGENTS.md. Keep tests short,
explicit, and placed according to configured discovery.

## Trigger Boundaries

- Trigger for configured test directories, test helpers, fixtures, factories
  used for test setup, and documentation about test conventions.
- Trigger for backend behavior changes when deciding what targeted Pest coverage to add or update.
- Do not treat green status-only smoke tests as sufficient; check the referenced anti-patterns.
- Do not rewrite externally provided or package-owned skills or generic Pest
  docs.

## References

- `references/anti-patterns.md` for coverage-only, smoke-only,
  mocked-internal-layer, response-contract, endpoint-specific permission, and
  list-test problems.
- `references/endpoint-scenarios.md` for route/controller feature test coverage
  expectations.
- `references/factory-setup.md` for factories, states, relations, fixtures, and
  admin helper usage.
- `references/test-style-and-placement.md` for placement, Pest style, imports,
  helpers, module groups, and assertion style.

## Must Check

- Keep each test focused on behavior, not implementation details.
- Do not accept smoke-only, status-only, or internal-mock tests when behavioral
  assertions are possible.

## Review Checklist

- Verify the test path matches the tested layer.
- Verify test organization keeps scenarios focused and discoverable.
- Verify factories reflect realistic relations and states.
- Verify administrative test actors use the actual authentication model and
  guard. Reuse existing permission helpers when available; do not assume separate
  public/admin models or a custom base permission exist.
- Verify super-admin helper usage is reserved for bypass behavior.
- Verify the test covers the behavior, not the implementation details.
- Add or update tests for every behavior change, not only for green paths.
