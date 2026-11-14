# Layer Responsibilities

- Use the repository's route files, controller style and binding conventions.
  Resource controllers and single-action controllers are both valid patterns.
- Validate body/query input at the established boundary: Form Request, DTO, or
  another existing validator. Do not create an empty input object.
- Route binding and existence validation do not prove authorization; apply the
  actual actor/tenant policy before returning or changing data.
- Keep use cases focused on business outcomes. If the application has an atomic
  operation layer, keep it below orchestration and avoid dependency cycles.
- Preserve established public entrypoints and DI contracts. Do not mandate a
  method name, base class, interface or concrete repository binding universally.
- Reuse the existing query/filter mechanism. Add processors or repositories only
  when they solve a demonstrated need; do not wrap trivial queries for symmetry.
- Keep file writes and external side effects out of response serialization.
- Discover route and event registration rather than assuming centralized loading.
- Delay side effects until commit when they require persisted state; consider
  retry/idempotency behavior and whether an outbox is already available.
- Under persistent workers, avoid request-specific mutable singleton/static
  state. Prefer scoped dependencies or explicit context with a clear lifecycle.
- Keep console/queue orchestration independent of HTTP request objects.
