## Requirements Gathering
- Define measurable success criteria and acceptance criteria early to anchor validation and avoid scope creep.
- Capture explicit non-functional requirements (security, performance, accessibility, maintainability) from the outset.
- Ensure traceability from requirements to tests and implementation to simplify validation.
- Identify risks, trade-offs, and decision boundaries to guide safe future changes.
- Distill requirements into minimal, testable abstractions to reduce rework.

## Architecture & Modularity
- Prefer explicit interfaces and dependency injection to ease testing, substitution, and future evolution.
- Design for cohesive, loosely coupled modules with clear boundaries and single responsibilities.
- Favor small, pure functions and immutable data where practical to improve reasoning and testability.
- Decouple core logic from delivery mechanisms (CLI/API/GUI) to maximize reusability.

## API Design
- Version APIs early and maintain stable contract tests to prevent breaking clients.
- Define clear input/output contracts with explicit error semantics and examples.
- Promote minimal, stable interfaces and provide migration paths for changes.
- Treat API contracts as first-class artifacts and ensure they are versioned and tested.

## Performance & Optimization
- Measure performance before optimizing; establish per-feature budgets and profile to locate real bottlenecks.
- Prefer readable, correct algorithms first; optimize only after demonstrable gains.
- Align data structures with expected workloads to avoid unnecessary complexity and rewrites.
- Consider observable performance boundaries (latency, throughput) and communicate them clearly.

## Testing Strategy
- Apply a test pyramid: unit, integration, and end-to-end tests, with contract tests where appropriate.
- Ensure tests are deterministic, data-driven, and aligned with explicit requirements.
- Use property-based or boundary testing to surface edge cases beyond hand-crafted cases.
- Keep tests fast, independent, and maintain traceability to acceptance criteria.
- Include reproducer scenarios for flaky or hard-to-debug failures and document them.

## Security
- Implement defense-in-depth and validate inputs thoroughly to prevent common vulnerabilities.
- Incorporate threat modeling early and integrate security tests into CI/CD.
- Validate dependencies for known vulnerabilities and minimize exposure of sensitive data in logs.
- Design with secure error handling to avoid leaking sensitive information.

## Documentation & Knowledge Transfer
- Document interfaces and architectural decisions using lightweight ADRs or decision logs.
- Centralize contracts and migration guides to reduce drift and onboarding effort.
- Auto-generate or maintain concise, cookbook-style examples to accelerate adoption.
- Strive for self-describing code and clear rationale to ease future maintenance.

## Versioning & Deployability
- Strive for independent deployability with clear, semantically versioned modules.
- Use feature flags and canary deployments to enable controlled rollouts and quick rollbacks.
- Define upgrade paths, deprecation timelines, and compatibility guarantees for consumers.
- Plan migrations in small, verifiable steps with rollback strategies.

## Collaboration & Process
- Assign clear ownership and maintain concise PR review checklists to reduce drift.
- Keep commits small and meaningful to improve traceability and review efficiency.
- Maintain a single source of truth for contracts, schemas, and migrations.
- Align on a shared Definition of Done and maintain lightweight decision logs for accountability.

## Reuse & Consistency
- Promote versioned components and canonical interfaces to support long-term reuse.
- Centralize common utilities and patterns; enforce consistent naming and usage.
- Document ownership and lifecycle for shared components to avoid duplication or drift.
- Strive for contract-driven development to stabilize cross-project integration.

## Observability & Debugging
- Standardize cross-service logging formats and propagate correlation IDs for end-to-end tracing.
- Implement distributed tracing and define a minimal, stable set of telemetry points per feature.
- Build proactive dashboards and create deterministic reproducer scenarios for complex bugs.
- Instrument critical code paths with structured telemetry to simplify root-cause analysis.

## Edge Cases & Correctness
- Formalize invariants and pre/post-conditions for critical domains and verify them in CI where feasible.
- Use fuzz testing and boundary checks to surface unexpected inputs and rare paths.
- Maintain explicit handling for null or missing data to prevent subtle defects.
- Document invariants and enforce them during migrations or refactors.

## Refactoring & Maintenance
- Prioritize small, well-tested refactors with clear rationale and regression tests.
- Maintain a changelog and rationale for significant changes to aid future maintenance.
- Plan migrations in incremental steps with rollback artifacts and traceable decisions.
- Prefer reversible changes and document rollback strategies for high-risk edits.
- Schedule periodic maintenance reviews to prevent rising technical debt.

## Tooling & CI (Cross-cutting)
- Integrate static analysis, type checks, and linters into the development workflow.
- Gate changes with fast-running tests and clear CI feedback to maintain quality.
- Use pre-commit hooks and consistent configuration to reduce drift across environments.