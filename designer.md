## Frontend UI/UX Guidelines: Input + Result Interfaces

### Core Interaction Model
- Keep a single input and a single result to minimize cognitive load and navigation.

### Input Controls & Validation
- Prefer an input type that triggers numeric keyboards on mobile, but validate edge cases robustly (e.g., pasted values).
- Provide a visible label with concise guidance and a helper text that states input constraints.
- Tie helper/error text to the input via aria-describedby for assistive tech.
- Disable the primary action until input is valid to prevent invalid submissions.
- Trigger the primary action with Enter when the input is focused.
- Offer a lightweight Clear action to reset both input and result.
- Communicate invalid input with a concise, actionable error message.

### Result Presentation & Feedback
- Render the result in a high-contrast, prominent area with clear typographic hierarchy.
- Format numeric results using locale-aware formatting for readability.
- Include an optional contextual line beneath the result to clarify meaning.
- Provide a small Copy action with an accessible confirmation (e.g., toast or aria-live message).
- Announce result updates via an appropriate ARIA live region to assist screen readers.

### Layout, Responsiveness & Visual Hierarchy
- On wide viewports, consider a two-column feel; on narrow viewports, stack input, action, and result vertically.
- Maintain generous tap targets and consistent vertical rhythm for readability and accessibility.
- Use a cohesive color system with clear contrast for primary actions and status states.

### Accessibility, Semantics & Keyboard Support
- Use a clear focus ring and ensure all interactive elements have visible focus states.
- Maintain a logical tab order: input → primary action → clear → result region (if focusable).
- Use descriptive labels and ensure all dynamic updates are announced to assistive technologies.
- Provide accessible labels for any additional actions (e.g., copy) and ensure non-sighted users receive feedback on actions.

### Localization & Internationalization
- Ensure number formatting respects the user’s locale, and design constraints consider RTL/LTR where relevant.
- Keep messages and labels succinct to accommodate translations without layout breaks.

### Performance & Feedback for Heavy Computation
- Show a subtle loading indicator if processing may block the UI, and avoid long stalls without user feedback.
- Keep UI responsive by decoupling heavy logic from rendering where possible.

### Patterns, References & Consistency
- Ground designs in established UI patterns (e.g., standard validation states, accessible form patterns) to reduce cognitive load.
- Favor reusable components for input, validation messaging, and result display to ensure consistency across features.

### Edge Cases, Testing & Quality Assurance
- Validate non-numeric, decimals, negative values, and other invalid inputs with clear error messaging.
- Consider locale variations and large result formatting for real-world usage.
- Include unit and manual accessibility testing, plus responsive verification across common breakpoints.

### Implementation, Extensibility & Collaboration
- Decouple core logic from UI layers to enable reuse across different frontends (web, API, CLI) without changing behavior.
- Document design decisions and validation rules to prevent rework when requirements evolve.
- Use a minimal, testable interface for future UI extensions (e.g., a REST API or a frontend framework integration).

### Quick Wins, Presets & Helpers
- If presets are used, label them clearly as quick-fill options and ensure they reset validation state appropriately.

### Foundational UX Principles (from council)
- Understand the 'why' behind requirements, not just the 'what'.
- Early-stage user flow diagrams help identify edge cases and clarify assumptions.
- Document design decisions to prevent revisiting them later.
- Iterate based on feedback; be willing to adjust.
- Focus on patterns rather than copying code from examples.
- Clearly articulate the user problem being solved before visual design.
- Prioritize accessibility from the outset, not as an afterthought.
- Regularly revisit requirements to stay aligned with evolving understanding.