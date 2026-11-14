---
name: et-module-architecture
description: Use when organizing Laravel application architecture in standard shared directories or domain modules, including routes, controllers, validation, use cases, persistence, resources, providers, administrative code, and integrations.
---

# et-module-architecture

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

## Workflow

Map the actual request/use-case/persistence/serialization flow before changing
it. Module boundaries and dependency direction matter more than directory names.
Keep HTTP handling small, business decisions explicit, persistence scoped, and
serialization free of hidden queries or writes.

If the target uses Actions, Tasks and Repositories, preserve their documented
entrypoints and dependency rules. A possible flow is controller → use case →
atomic operation → repository; it is an example, not a required stack. Do not
introduce missing layers or forbid direct Eloquent merely because another
application uses repositories.

## References

- `references/layer-flow.md`: responsibility and dependency boundaries.
- `references/admin-boundaries.md`: administrative code and authorization.
- `references/resources-and-responses.md`: serialization and eager loading.

Check sibling files and current route/provider registration before adding files.
Keep integrations behind a contract when a real external boundary warrants it.
Use related naming, validation, package, testing, and API-documentation skills
when available and relevant.

## Companion Guides

When using the ai-init checkout, consult the relevant guides below. A standalone
skill installation may omit them; use available local guidance and the bundled
references instead. These guides describe both standard and modular layouts.

- [Architecture profiles](../../docs/architecture.md)
- [Concurrency and delivery](../../docs/concurrency-and-delivery.md)
