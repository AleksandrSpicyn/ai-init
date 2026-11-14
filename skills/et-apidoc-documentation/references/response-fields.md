# Successful JSON Field Schemas

Trace the controller return, response wrapper, nested serializers, relation
loading, pagination, casts and conditional branches. Inventory root containers,
nested objects, lists and leaves across reachable success variants.

- Record wire types, not PHP storage types. Keep numeric strings distinct from
  numbers and empty lists distinct from objects.
- Distinguish absent keys from keys containing null. A conditional field is not
  universally required; a present key is not necessarily non-nullable.
- Check `whenLoaded`, `whenNotNull`, `mergeWhen`, pivot/count helpers and
  equivalent application serializers. `MissingValue` represents omission.
- Capture exhaustive enum values only when proven across relevant scenarios.
  Keep examples/defaults compatible with types and allowed values.
- Use field-path, array and nullable syntax supported by the installed Scribe
  version or custom strategy. Do not assume dotted paths, `[]`, union types,
  modifiers or enum markers are universally parsed.
- Use complete response scenarios for meaningful shape variants; individual
  field examples do not describe an entire payload.
- Verify how the generator applies response-field metadata to status codes.
  Success constraints must not incorrectly alter error response schemas.
- Verify every expected field, item type, optional/nullable flag and description
  in generated OpenAPI and rendered documentation. If annotations cannot express
  the contract, use an existing supported schema override mechanism.
