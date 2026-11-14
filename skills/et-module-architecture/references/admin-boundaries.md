# Administrative Boundaries

- Discover administrative namespaces, routes, guards and actor models. Keep
  administrative presentation and privileged fields within that boundary.
- Reuse domain models, factories and business behavior instead of duplicating
  them solely because a caller is administrative.
- Share Resources only when the serialized contract and authorization are truly
  shared; separate projections when administrative fields could leak publicly.
- Inspect route groups before adding authentication or permission middleware.
  Do not assume a shared loader supplies either or duplicate it unnecessarily.
- Apply endpoint policies/permissions and current tenant/context scope. Binding
  a model or checking its existence is insufficient.
- Login/bootstrap exceptions need abuse controls and safe failure responses;
  failures must not issue tokens or sessions.
- Follow existing repository inheritance and controller patterns only where the
  target uses them. No particular admin directory or class hierarchy is required.
- Test ordinary authorized actors, missing permission, unauthenticated access,
  and out-of-scope targets as relevant. Reserve super-admin actors for bypass
  behavior; verify denied writes have no side effects.
