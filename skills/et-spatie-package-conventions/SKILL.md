---
name: et-spatie-package-conventions
description: Use when creating or changing modular Laravel DTOs with spatie/laravel-data, media handling with spatie/laravel-medialibrary, settings classes with spatie/laravel-settings, or roles and permissions with spatie/laravel-permission in an existing modular Laravel project.
---

# Spatie Package Conventions

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

Use this skill when the task touches package-level conventions rather than
generic Laravel code. Read the references for portable package conventions.
For roles and permissions, also read repository RBAC documentation when it
exists and is inside the approved read scope. Consult repository package docs
only when the task explicitly scopes them in.

## References

- `references/laravel-data.md` for DTO placement, validation attributes,
  `rules()`, controller input, and Resource boundaries.
- `references/media-settings.md` for Media Library and Laravel Settings
  conventions, private storage, import image validation, and settings cache.
- `references/permission.md` for roles/permissions modules, administrative
  authentication guard, endpoint-specific permissions, Spatie cache reset,
  tests, and API documentation `403` examples.

## Anti-Triggers

- Do not run `composer require` or `vendor:publish` in the target project unless the
  user explicitly approves dependency/config changes.
- Do not use for general package documentation, package onboarding, or
  unrelated third-party package installation/configuration.
- Do not create parallel package wrappers when an existing module convention or
  enum already covers the use case.
- Do not edit externally provided or package-owned skills while applying project
  Spatie rules.

## Package Integration Rules

- Reuse existing integration boundaries; add wrappers only when they isolate a
  real application contract or useful policy.
- Keep naming, exceptions, and tests aligned with the rest of the project.
- For new usage of supported Spatie packages, follow the repository package
  onboarding template only when the task explicitly scopes it in. Do not use
  this skill to onboard unrelated packages.
