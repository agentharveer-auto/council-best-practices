## Requirements Gathering
- Document forward-compatible constraints to guide safe future expansions.
- Align on measurable success criteria and exit conditions to prevent scope creep.
- Capture non-functional requirements (security, accessibility, performance) early to guide design.
- Ensure traceability from requirements to tests and implementation.
- Define acceptance criteria per requirement to enable early testability.
- Identify regulatory, privacy, and accessibility constraints early to steer design decisions.
- Capture explicit risk assumptions and trade-offs to surface potential impacts.

## API Design
- Version APIs early and communicate deprecations to prevent breaking clients.
- Maintain a single source of truth for API contracts to avoid drift.
- Design data contracts with clear versioning and migration paths.
- Promote contract testing to catch integration issues early.
- Define migration paths and equivalence classes to minimize breaking changes.
- Promote semantic versioning and deprecation paths for stable client upgrades.
- Encourage forward-compatible interfaces to reduce cross-project drift over time.

## Architecture & Modularity
- Prefer evolvable data representations and minimize schema migrations when rules evolve.
- Design with explicit interfaces and dependency injection to ease testing and substitution.
- Decouple persistence from domain logic using repository-like boundaries.
- Favor small, pure functions with well-defined interfaces for easier testing and reuse.
- Promote immutability and referential transparency to simplify reasoning and parallelism.

## Performance & Optimization
- Measure impact before optimizing; avoid premature optimization.
- Establish per-feature performance budgets and verify them during development.
- Benchmark changes before and after and document results for future reference.
- Define explicit latency budgets and aim for predictable, constant-time behavior where feasible.
- Use canary deployments or staged rollouts to validate performance in production.

## Testing Strategy
- Adopt a test pyramid with unit, integration, and end-to-end tests; include contract tests.
- Ensure tests are deterministic, data-driven, and aligned with requirements.
- Use property-based testing where practical to surface hidden edge cases.
- Maintain traceability between tests and acceptance criteria to ensure coverage.

## Security
- Apply defense-in-depth with least privilege across services.
- Include threat modeling at design time and integrate security tests into CI/CD.
- Log security-relevant events with privacy-conscious handling and minimize sensitive data exposure.
- Validate inputs thoroughly and enforce secure error messaging to avoid information leakage.

## Documentation & Knowledge Transfer
- Document interfaces and decisions in version-controlled ADRs and architecture docs.
- Maintain lightweight decision logs to preserve rationale for future teams.
- Where possible, auto-generate documentation from code to reduce drift.
- Centralize API contracts and migration guides accessible to all teams.

## Versioning & Deployability
- Aim for independent deployability with clear versioning of modules.
- Use feature flags to enable controlled rollouts and quick rollbacks.
- Maintain backward-compatible changes with explicit migration steps and sunset plans.
- Plan canary or phased deployments and document rollback criteria.

## Collaboration & Process
- Establish clear ownership and concise PR review checklists to reduce drift.
- Encourage small, frequent commits with meaningful messages to aid traceability.
- Maintain a single source of truth for API contracts and migration artifacts.
- Use decision logs and planning checklists to improve cross-team alignment.

## Reuse & Consistency
- Publish versioned components and contract tests to encourage cross-project reuse.
- Maintain consistent naming conventions to facilitate readability and reuse.
- Enforce coding standards and library usage to reduce duplication.
- Promote canonical interfaces and versioned APIs to support long-term consistency.

## Observability & Debugging
- Standardize cross-service logging formats and propagate correlation IDs.
- Implement distributed tracing across services for end-to-end debugging.
- Define a minimal, stable set of telemetry points per feature and align dashboards with acceptance criteria.
- Build early, actionable dashboards to monitor health, latency, and error rates.

## Edge Cases & Correctness
- Formalize invariants and pre/post-conditions for critical domains and verify them in CI.
- Use fuzz testing for parsing/validation paths to surface unexpected inputs.
- Document invariants clearly and enforce them during migrations.

## Refactoring & Maintenance
- Prioritize small, well-tested refactors with regression tests and clear rationale.
- Maintain a changelog and rationale for refactors to aid future maintenance.
- Plan migration-oriented refactors in small steps with rollback plans and traceable artifacts.