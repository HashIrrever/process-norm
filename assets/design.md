# Frontend Display Design

> Replace bracketed prompts with project-specific decisions. If the project has no frontend, state **No UI in scope** here and mark presentation sections `N/A` with a reason.

## 1. Purpose and scope

- Product/surface: [name]
- Target users and context: [users, devices, environment]
- In-scope screens or surfaces: [list]
- Out-of-scope presentation work: [list]
- Design intent: [the experience this UI should create]

## 2. Information architecture

Describe navigation, page hierarchy, primary actions, secondary actions, and how users know where they are.

| Surface | User goal | Content hierarchy | Primary action | Entry/exit |
|---|---|---|---|---|
| [screen/component] | [goal] | [ordered content] | [action] | [flow] |

## 3. Visual system

Document the source of truth for tokens. Prefer named semantic tokens over unexplained literal values.

| Category | Decision | Usage rules |
|---|---|---|
| Color | [palette/tokens] | [contrast and semantic meaning] |
| Typography | [families/scale/weights] | [hierarchy and fallback] |
| Spacing | [scale] | [layout rhythm] |
| Shape | [radius/borders] | [component rules] |
| Elevation | [shadows/layers] | [when permitted] |
| Icons/media | [style/assets] | [sizing and accessibility] |

## 4. Screen and component specifications

Give stable design IDs such as `D-001`.

| Design ID | Surface/component | Layout and hierarchy | Interaction | Responsive behavior | Acceptance |
|---|---|---|---|---|---|
| D-001 | [name] | [structure] | [mouse/touch/keyboard] | [breakpoints/reflow] | [observable result] |

## 5. Interaction flows

For each important flow, state the entry point, ordered user actions, system feedback, escape/cancel behavior, and completion state.

### Flow: [name]

1. [entry]
2. [action and immediate feedback]
3. [next state]
4. [completion or recovery]

## 6. State coverage

Do not specify only the happy path.

| Surface | Loading | Empty | Partial | Error | Disabled | Permission denied | Success |
|---|---|---|---|---|---|---|---|
| [name] | [presentation] | [presentation] | [presentation] | [recovery] | [reason/cue] | [message/action] | [confirmation] |

## 7. Responsive behavior

- Supported viewport/device classes: [list]
- Breakpoints or container rules: [values/rationale]
- Reflow and stacking rules: [rules]
- Touch targets and input adaptations: [rules]
- Overflow and long-content behavior: [rules]

## 8. Accessibility

- Semantic structure and landmarks: [rules]
- Keyboard order and shortcuts: [rules]
- Focus visibility and restoration: [rules]
- Labels, descriptions, and announcements: [rules]
- Contrast and non-color cues: [rules]
- Reduced motion, zoom, and text scaling: [rules]

## 9. Content and localization

- Voice and terminology: [rules]
- Labels, validation, and error-message style: [rules]
- Date, number, and time formats: [rules]
- Long-text, bidirectional, or locale constraints: [rules]

## 10. Motion and feedback

- Transitions and duration/easing: [rules]
- Progress and optimistic feedback: [rules]
- Reduced-motion behavior: [rules]
- Prohibited or distracting motion: [rules]

## 11. Design acceptance checklist

- [ ] Every in-scope surface has a stable design ID.
- [ ] Visual hierarchy and tokens are explicit.
- [ ] Loading, empty, partial, error, disabled, permission, and success states are covered.
- [ ] Responsive and accessibility behavior is testable.
- [ ] Frontend behavior is consistent with `feature.md`.

## 12. Decisions, changes, and open questions

| Date | Item | Decision/change | Reason | Owner |
|---|---|---|---|---|
| [YYYY-MM-DD] | [ID/section] | [decision] | [why] | [owner] |

Open questions:

- [question, impact, and decision owner]
