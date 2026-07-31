# Functional Feature Specification

> Replace bracketed prompts with project-specific decisions. Describe intended behavior, not merely the current implementation.

## 1. Product objective and scope

- Problem: [problem being solved]
- Intended outcome: [measurable or observable outcome]
- In scope: [capabilities]
- Out of scope: [explicit exclusions]
- Assumptions and constraints: [list]

## 2. Actors and permissions

| Actor | Goal | Allowed actions | Restrictions |
|---|---|---|---|
| [role/system] | [goal] | [actions] | [rules] |

## 3. Feature catalog

Give stable feature IDs such as `F-001`. A documented feature remains intended behavior until an authorized specification change says otherwise.

| Feature ID | Capability | Trigger/preconditions | Rules | Result/side effects | Priority/status |
|---|---|---|---|---|---|
| F-001 | [capability] | [conditions] | [business rules] | [observable outcome] | [status] |

## 4. Functional flows

### Flow: [name]

1. [actor and precondition]
2. [request/action]
3. [validation and rules]
4. [state/data change]
5. [response, side effects, and next state]

Alternative and recovery paths:

- [condition] → [expected behavior]

## 5. Business rules and invariants

Give stable rule IDs such as `R-001`.

| Rule ID | Rule/invariant | Applies to | Failure behavior |
|---|---|---|---|
| R-001 | [rule] | [features/actors] | [error or recovery] |

## 6. Data and interface contracts

| Contract | Inputs | Outputs | Validation | Compatibility/versioning |
|---|---|---|---|---|
| [API/event/model] | [schema] | [schema] | [rules] | [guarantees] |

Record persistence, ordering, idempotency, concurrency, caching, and lifecycle rules where relevant.

## 7. Integrations and side effects

| Integration/effect | Trigger | Expected behavior | Failure/retry behavior |
|---|---|---|---|
| [service/event/notification] | [condition] | [effect] | [policy] |

## 8. Errors and recovery

| Condition | User/system-visible behavior | Retry/recovery | Observability |
|---|---|---|---|
| [failure] | [result] | [steps/policy] | [log/metric/trace] |

## 9. Non-functional requirements

- Performance and capacity: [targets]
- Security and privacy: [requirements]
- Reliability and consistency: [requirements]
- Auditability and observability: [requirements]
- Compatibility and migration: [requirements]

## 10. Non-goals

- [behavior deliberately not supported]

## 11. Acceptance criteria

Give stable IDs such as `AC-001` and link each criterion to a feature ID.

### AC-001 — [name] (`F-001`)

- Given [precondition]
- When [action]
- Then [observable functional result]
- And [side effect, error behavior, or invariant]

## 12. Feature-versus-defect rule

- Treat behavior matching the active feature, rule, and acceptance criteria as an intended feature.
- Treat behavior violating an unambiguous criterion as an implementation defect or regression.
- Treat behavior that only violates `design.md` as design drift unless functionality is also broken.
- Treat undocumented or contradictory expectations as specification ambiguity.
- Treat a requested intentional deviation as a change request; update this document before implementation.
- Never weaken this specification solely to make existing code or tests pass.

## 13. Decisions, changes, and open questions

| Date | Item | Decision/change | Reason | Owner |
|---|---|---|---|---|
| [YYYY-MM-DD] | [ID/section] | [decision] | [why] | [owner] |

Open questions:

- [question, impact, and decision owner]
