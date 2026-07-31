---
name: process-norm
description: Enforce specification-led software delivery for frontend and backend coding, implementation, refactoring, code review, and debugging. Use whenever Codex changes or evaluates code and must preserve the intended UI and product behavior. Require project-root design.md and feature.md, use them as the baseline for every coding/review/debug decision, prevent documented features or designs from being misclassified as bugs, and require implementation-level comments for large modules.
---

# Process Norm

Use `design.md` and `feature.md` as the project contract. Keep the contract, implementation, tests, and review findings traceable to one another.

## Establish the contract before acting

1. Locate the working project root and obey its repository instructions.
2. Check for the exact project-root files `design.md` and `feature.md`.
3. If either file is missing, create it from the matching file in `assets/` and replace template prompts with project-specific content before changing code.
4. If a project has no frontend, still create `design.md`; state that no UI is in scope and document any client-facing states or presentation impacts as not applicable.
5. Read both files completely before coding, reviewing, debugging, refactoring, or proposing a fix. Re-read the affected sections after either file changes.
6. Do not proceed with unresolved placeholders, empty required sections, or contradictions that materially affect the task. Resolve them from repository evidence when safe; otherwise surface the ambiguity.

Treat the files as separate but complementary authorities:

- `design.md` defines how the frontend is presented and experienced: information hierarchy, layout, components, visual tokens, interaction, responsive behavior, accessibility, content, motion, and loading/empty/error/success states.
- `feature.md` defines what the system does: actors, capabilities, flows, business rules, data and API behavior, permissions, side effects, error handling, compatibility, non-goals, and acceptance criteria.

Apply explicit, current user instructions first. If they intentionally change behavior or presentation, update the relevant specification before implementing the change. Do not silently rewrite a specification merely to match the existing code.

## Maintain traceability

Before editing, build a compact task map:

| Requested outcome | `design.md` section | `feature.md` feature/criterion | Code and tests |
|---|---|---|---|
| One row per outcome | Heading or N/A | Stable ID or N/A | Expected targets |

Use `N/A` only with a short reason. Keep stable feature and acceptance IDs from `feature.md` in plans, tests, review findings, and completion summaries when applicable.

## Classify behavior before fixing it

Compare the reported or observed behavior with both specifications:

- **Implementation defect**: behavior violates an unambiguous functional acceptance criterion.
- **Design drift**: frontend appearance or interaction violates an unambiguous design rule.
- **Regression**: previously conforming behavior now violates the contract.
- **Specification ambiguity**: the documents do not determine the expected result or contradict each other.
- **Intended feature**: behavior matches the documented feature and design, even if it is surprising or unpopular.
- **Change request**: the desired result intentionally differs from the current contract.

Never label an intended feature as a bug merely because the implementation is unfamiliar, a test expects older behavior, or changing it is convenient. Report usability concerns separately from defects. Never delete or weaken a documented requirement simply to make code or tests pass.

For an ambiguity, document the competing interpretations and avoid a behavior-changing fix until the intended contract is resolved. For an authorized change request, revise the specification first and then implement and test it.

## Execute the applicable workflow

### Coding or refactoring

1. Read both specifications and create the task map.
2. Update `design.md` or `feature.md` first when the requested work changes the contract.
3. Plan frontend and backend work against the mapped sections, including all documented states and error paths.
4. Implement the smallest coherent change that satisfies the entire mapped contract.
5. Add or update tests that prove the relevant feature IDs and design behavior.
6. Add implementation-level comments to every large module created or substantially changed.
7. Re-read the mapped sections, inspect the final diff, and verify that code, tests, and documentation agree.

Do not declare a frontend complete based only on the happy path. Verify hierarchy, spacing and tokens, responsive breakpoints, keyboard and screen-reader behavior, and every documented loading, empty, partial, error, disabled, permission, and success state. For backend changes, preserve response shapes and state signals that the documented frontend relies on.

### Code review

1. Read both specifications before judging the diff.
2. Review each changed behavior against its exact design section and feature/acceptance ID.
3. Classify findings as implementation defect, design drift, regression risk, specification ambiguity, or maintainability issue.
4. Include the governing specification reference and concrete impact in every behavioral finding.
5. Do not mutate code or specifications during a review-only request.

Do not call a documented feature a bug. If a test conflicts with the contract, flag the stale test or specification conflict instead of assuming the production behavior is wrong.

### Debugging

1. Read both specifications before reproducing or patching.
2. Reproduce the issue and capture actual behavior.
3. Map expected behavior to the exact design and feature criteria.
4. Classify the issue before editing.
5. Fix code only for a confirmed defect, design drift, or regression. Treat desired deviations as change requests and update the contract first when authorized.
6. Add a regression test and verify adjacent documented states.
7. Confirm the fix did not erase, bypass, or relabel another feature.

## Require comments for large modules

Treat a module as large when it owns a subsystem or public boundary, coordinates multiple components, implements a state machine or workflow, contains substantial domain logic, or is otherwise difficult to understand from local functions alone. Do not rely only on a line-count threshold.

Add a language-appropriate module docstring, file header, class docblock, or adjacent architectural comment that explains:

- the module's purpose and responsibility;
- what it deliberately does not own;
- its main collaborators and data/control flow;
- important invariants, state transitions, or non-obvious design decisions;
- side effects, failure behavior, and recovery boundaries where relevant.

Comment intent and architecture, not syntax. Keep comments accurate when behavior changes. Do not deliver a newly implemented or substantially changed large module without this commentary.

## Finish with a conformance report

Report:

- which `design.md` sections and `feature.md` IDs were consulted or updated;
- which code and tests implement each mapped outcome;
- validation performed and its result;
- any remaining ambiguity, deliberate deviation, or follow-up.

Do not claim conformance when either specification was skipped or a mapped criterion remains unverified.

## Use the templates

- Copy `assets/design.md` to the project root when `design.md` is missing.
- Copy `assets/feature.md` to the project root when `feature.md` is missing.
- Preserve useful headings, replace bracketed prompts, remove instructions that do not apply, and record explicit `N/A` decisions rather than leaving sections silently blank.
