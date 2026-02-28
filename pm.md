## Requirements Gathering
- Always clarify the underlying problem and success criteria before proposing solutions.
- Define explicit input constraints and edge cases early; ensure acceptance criteria are measurable and testable.
- Align expectations with stakeholders to prevent scope creep and rework later.

## System Design & Architecture
- Favor a decoupled core logic layer from UI/API surfaces to enable reuse and future extension.
- Design interfaces with clear contracts and minimal leakage of implementation details.
- Favor incremental, upgrade-friendly architectures over monolithic, hard-to-change designs.

## API Design
- Expose stable, well-documented interfaces with a clear input/output contract and a versioning strategy.
- Keep the surface area small; introduce changes via non-breaking enhancements where possible.
- Document error responses, boundary conditions, and expected input types to support predictable integration.

## Error Handling
- Provide clear, actionable error messages and maintain consistent error shapes across the system.
- Validate inputs at the boundaries and fail fast with deterministic behavior.

## Testing & Validation
- Build deterministic reference implementations or baselines to validate correctness.
- Cover boundary conditions and state transitions that may change with input size or complexity.
- Use automated, maintainable test suites that run frequently and provide rapid feedback.

## Performance & Scalability
- Set and validate performance targets early; benchmark against realistic inputs.
- Favor simple, readable algorithms with known complexity to aid maintainability and future optimization.

## Documentation & Knowledge Sharing
- Keep the living document concise and actionable; update decisions, rationale, and learnings after each council.
- Capture design rationale, trade-offs, and future work to aid future teams and onboarding.

## Stakeholder Communication
- Maintain regular alignment on scope, progress, and risks; communicate changes promptly and transparently.
- Document decisions and rationale to prevent drift and facilitate future reviews.

## Trade-offs & Decision Making
- Explicitly weigh performance, maintainability, and complexity; document the reasoning behind choices.
- Favor MVP-driven decisions with measurable learning and clear exit criteria for pivots.

## Process & Workflow
- Use iterative, MVP-first delivery with measurable milestones; avoid big-bang releases.
- Merge updates to the living doc carefully to avoid duplication and maintain consistency.

## UI/UX Considerations
- If UI is optional, keep it decoupled from core logic to ensure maintainability and easy future extension.

## Integration & Deployment
- Treat integration points as contracts with clear observability and error-handling requirements. 

## Product Manager Best Practices

- Prioritize understanding the 'why' behind requests before diving into solutions.
- Early and frequent stakeholder alignment on core concepts prevents later divergence.
- Focus on defining clear problem statements before proposing solutions.
- A lightweight, iterative approach to documentation is preferable to comprehensive upfront design.
- Don't fall in love with your initial solution; be open to pivoting based on feedback.
- Reference existing open-source projects for inspiration, but avoid direct copy-pasting.