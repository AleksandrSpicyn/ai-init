# PHP Style and Contracts

- Read the installed formatter configuration and declared PHP version first.
  Follow existing rules for quotes, imports, line breaks, trailing commas,
  nullable syntax, enum cases, unused parameters and PHPDoc tag order.
- Prefer explicit parameter/property/return types where compatible with parent
  signatures and framework APIs. Preserve valid union/intersection types;
  `mixed` may be necessary at a genuine dynamic boundary.
- Use PHPDoc for shapes, generics, non-obvious iterables/callables and meaningful
  propagated exceptions. Avoid repeating an obvious native signature.
- Match external enum values and persisted contracts exactly; style cleanup
  does not authorize renaming them. Use local enum helpers only if present.
- Choose arrays, DTOs, Resources or value objects according to the actual
  contract and local conventions; do not wrap every local scalar array.
- Prefer loops for early exits or side effects and collection transformations
  when they improve readability. Do not rewrite one into the other mechanically.
- Comments explain non-obvious invariants, external protocols and workarounds.
- Avoid mutable request state in persistent singletons/statics.
- Apply formatter/static-analysis fixes to the intended scope. Do not hide
  behavior changes in style cleanup or add broad modernization churn.
- SQL fragments require binding and data-flow review; a stylistic issue alone
  is not evidence of an exploitable vulnerability.
