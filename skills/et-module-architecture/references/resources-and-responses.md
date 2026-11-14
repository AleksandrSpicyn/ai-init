# Resources and Responses

- Follow the target's serializer and envelope conventions. Laravel Resources
  are useful for stable API projections; package DTO serialization may also be
  an intentional contract. Avoid changing serializers as unrelated cleanup.
- Keep privileged fields out of public projections. Distinguish shared shapes
  from administrative projections and audit conditional authorization.
- Split meaningful or reused nested objects into serializers when that improves
  clarity; tiny scalar groups do not each require a class.
- Prefer normal resource collections unless custom pagination/meta is needed.
- Load required relations before serialization. Conditional helpers such as
  `whenLoaded()` must reflect the endpoint's actual load and omission contract.
- Avoid hidden service/database/cache work in serialization and API-only model
  helpers. Check query behavior across nested resources, not just the root.
- Document and test intentional variant responses; do not silently replace an
  established empty, nullable, or paginated shape with another.
- Never add request-specific presentation state to shared static properties or
  persistent service instances.
