# Response Scenarios

- Document real success statuses and complete response bodies, including the
  actual envelope and pagination metadata. Do not invent `data`, `success`,
  `message`, application codes, or an empty-array body.
- `204` means the runtime returns no content. Document `201` only when emitted.
- Cover meaningful reachable variants, including omitted/nullable nested fields.
- Trace authentication, authorization, binding, validation and domain errors;
  they may share a status but have different bodies. Inspect production error
  rendering rather than copying debug output or a neighboring controller.
- Include application error codes only when returned; follow the target's
  registry/documentation conventions if one exists.
- Unmatched routes are not controller responses. Document routing failures at
  the routing/API level when that is part of the requested contract.
- Inspect Scribe response-call configuration before relying on generated calls
  for any HTTP method. Calls may execute writes or external side effects; use
  isolated configured environments and explicit examples where appropriate.
- Files, streams and multipart inputs need their actual headers, content types,
  limits and access requirements. Do not present them as JSON.
- Use supported scenario/example annotations for the installed generator.
  Verify generated output and semantic HTTP/file/stream behavior.
