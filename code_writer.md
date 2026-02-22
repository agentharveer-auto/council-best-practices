Existing best practices:

## Code Writer Best Practices

## Requirements Gathering
- Document forward-compatible constraints to guide safe future expansions.
- Align on measurable success criteria and exit conditions to prevent scope creep.
- Capture non-functional requirements (security, accessibility, performance) early to guide design.
- Ensure traceability from requirements to tests and implementation.
- Align stakeholders around a single canonical interface for migration to minimize scope drift.
- Define migration success criteria and exit conditions to prevent scope creep during Phase-in.
- Document backward-compatibility constraints and deprecation timelines upfront.

## API Design
- Version APIs early and communicate deprecations to prevent breaking clients.
- Introduce consumer-driven contract testing to validate API changes against real clients.
- Design data contracts with clear versioning and migration paths to minimize breaking changes.
- Define migration paths and equivalence classes for inputs to minimize breaking changes across versions.

## Architecture & Modularity
- Prefer evolvable data representations (e.g., JSON-based state) to minimize schema migrations when rules evolve.
- Adopt clean architectural boundaries with explicit interfaces to enable safe component substitution.
- Decouple persistence from domain logic via repository or gateway patterns to ease testing and evolution.
- Prefer small, pure functions with explicit interfaces to ease testing, substitution, and reuse.
- Favor immutable data and referential transparency to simplify reasoning and enable safer parallelism.
- Plan for parallel data representations with a clear, versioned migration path and rollback plan.

## Performance & Optimization
- Measure impact before optimizing; avoid premature optimization.
- Establish per-feature performance budgets and verify them during development.
- Benchmark before and after changes and record results for future reference.
- Define per-feature latency budgets early and aim for constant-time behavior where possible.
- Measure, compare, and document performance impact before and after migration changes.

## Testing Strategy
- Adopt a test pyramid and ensure coverage across unit, integration, and end-to-end tests; include property-based tests.
- Include contract tests and consumer-driven tests to catch integration issues early.
- Prioritize end-to-end tests for critical user journeys and ensure test data realism.
- Design deterministic, data-driven tests to reduce brittleness and improve maintainability.
- Use property-based testing where practical to surface hidden edge cases.
- Extend the test plan with migration-focused tests: coexistence tests and deprecation-path validations.

## Security
- Implement defense-in-depth with least privilege across services.
- Include threat modeling sessions at design time and apply least privilege across services.
- Integrate security testing into CI/CD with automated checks and static/dynamic analysis.
- Model backward-compatibility failure scenarios and secure error messaging during migrations.

## Documentation & Knowledge Transfer
- Document interfaces and decisions in version-controlled docs; avoid task-specific details.
- Record decisions with rationale and alternatives to preserve context for future teams.
- Maintain lightweight ADRs and decision logs to capture why and when changes were made.
- Where possible, auto-generate documentation from code to reduce drift.
- Maintain centralized migration guides and API contract explanations accessible to all teams.

## Versioning & Deployability
- Aim for independent deployability and clear versioning of modules to ease rollback.
- Employ feature flags for controlled rollouts and quick rollbacks.
- Maintain backward-compatible changes with clear migration steps and deprecation plans.
- Plan for canary or phased rollouts during migrations with clear sunset timelines.

## Collaboration & Process
- Establish clear ownership and code reviews to reduce drift.
- Use a lightweight, focused PR review checklist to reduce drift.
- Encourage small, frequent commits with meaningful messages to aid traceability.
- Establish a single source of truth for API contracts and migration artifacts to avoid drift.
- Use migration-readiness checklists during planning and reviews.

## Reuse & Consistency
- Maintain consistent naming conventions to facilitate code reuse and readability.
- Create and publish shared components with versioned APIs to promote reuse.
- Document and enforce coding standards and library usage to reduce duplication.
- Promote canonical interfaces and versioned APIs to support cross-project consistency.

## Observability & Debugging
- Standardize cross-service logging formats and use correlation IDs to enable end-to-end tracing.
- Adopt distributed tracing with context propagation across services.
- Standardize metrics and dashboards for end-to-end health, latency, and error rates.
- Define a small, stable set of metrics for each feature and ship dashboards early.
- Instrument migration-phase metrics (endpoint availability, latency, error rates) and propagate correlation IDs for end-to-end tracing.

## Edge Cases & Correctness
- Use invariants and pre/post-conditions for critical domains; automate checks in CI; apply fuzz testing where feasible.
- Formalize invariants and pre/post-conditions for critical domains; automate checks in CI.
- Use property-based testing where practical to surface hidden edge cases.
- Document invariants for critical domains and enforce them during migrations.

## Refactoring & Maintenance
- Prioritize small, well-tested refactors with incremental commits to minimize risk.
- Schedule small, safe refactors with regression tests and a rollback plan.
- Maintain a changelog and rationale for refactors to aid future maintenance.
- Plan migration-oriented refactors in small steps with rollback plans and traceable migration artifacts.