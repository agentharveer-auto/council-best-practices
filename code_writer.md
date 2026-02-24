## Requirements Gathering
- Document forward-compatible constraints to guide safe future expansions.
- Align on measurable success criteria and exit conditions to prevent scope creep.
- Capture non-functional requirements (security, accessibility, performance) early to guide design decisions.
- Ensure traceability from requirements to tests and implementation.
- Define acceptance criteria per requirement to enable early testability.
- Identify regulatory, privacy, and accessibility constraints early to steer design decisions.
- Capture explicit risk assumptions and trade-offs to surface potential impacts.
- Define decision scope and boundaries upfront to minimize mid-project scope shifts.
- Clarify stakeholders’ priorities and trade-offs to guide iterative planning.
- Set measurable milestones that tie back to validation criteria.

## API Design
- Version APIs early and communicate deprecations to prevent breaking clients.
- Maintain a single source of truth for API contracts to avoid drift.
- Design data contracts with clear versioning and migration paths.
- Promote contract testing to catch integration issues early.
- Define migration paths and equivalence classes to minimize breaking changes.
- Promote semantic versioning and deprecation paths for stable client upgrades.
- Encourage forward-compatible interfaces to reduce cross-project drift over time.
- Specify clear error semantics and data validation rules to improve client resilience.
- Document expected inputs/outputs with concrete examples to reduce misinterpretation.
- Prefer explicit, minimal interfaces to reduce surface area and maintenance burden.

## Architecture & Modularity
- Prefer evolvable data representations and minimize schema migrations when rules evolve.
- Design with explicit interfaces and dependency injection to ease testing and substitution.
- Decouple persistence from domain logic using repository-like boundaries.
- Favor small, pure functions with well-defined interfaces for easier testing and reuse.
- Promote immutability and referential transparency to simplify reasoning and parallelism.
- Break systems into cohesive, loosely coupled modules to ease maintenance.
- Favor single-responsibility modules to minimize ripple effects during changes.
- Reduce global state and shared mutable data to improve determinism.

## Performance & Optimization
- Measure impact before optimizing; avoid premature optimization.
- Establish per-feature performance budgets and verify them during development.
- Benchmark changes before and after and document results for future reference.
- Define explicit latency budgets and aim for predictable, constant-time behavior where feasible.
- Use canary deployments or staged rollouts to validate performance in production.
- Start with correct, readable algorithms; optimize only after profiling shows real gains.
- Choose data structures aligned with expected workloads to avoid costly rewrites.

## Testing Strategy
- Adopt a test pyramid with unit, integration, and end-to-end tests; include contract tests.
- Ensure tests are deterministic, data-driven, and aligned with requirements.
- Use property-based testing where practical to surface hidden edge cases.
- Maintain traceability between tests and acceptance criteria to ensure coverage.
- Write tests that express invariants and boundary conditions, not only happy paths.
- Keep tests fast and independent to encourage frequent execution.
- Include reproducer scenarios for flaky or hard-to-debug failures.

## Security
- Apply defense-in-depth with least privilege across services.
- Include threat modeling at design time and integrate security tests into CI/CD.
- Log security-relevant events with privacy-conscious handling and minimize sensitive data exposure.
- Validate inputs thoroughly and enforce secure error messaging to avoid information leakage.
- Audit dependencies for known vulnerabilities and maintain repeatable remediation processes.

## Documentation & Knowledge Transfer
- Document interfaces and decisions in version-controlled ADRs and architecture docs.
- Maintain lightweight decision logs to preserve rationale for future teams.
- Where possible, auto-generate documentation from code to reduce drift.
- Centralize API contracts and migration guides accessible to all teams.
- Provide concise, cookbook-style examples to accelerate onboarding.
- Include rationale and alternative options to preserve reasoning in future maintenance.

## Versioning & Deployability
- Aim for independent deployability with clear versioning of modules.
- Use feature flags to enable controlled rollouts and quick rollbacks.
- Maintain backward-compatible changes with explicit migration steps and sunset plans.
- Plan canary or phased deployments and document rollback criteria.
- Document upgrade paths and compatibility guarantees for consumers.
- Manage configuration as code to ensure reproducible deployments.

## Collaboration & Process
- Establish clear ownership and concise PR review checklists to reduce drift.
- Encourage small, frequent commits with meaningful messages to aid traceability.
- Maintain a single source of truth for API contracts and migration artifacts.
- Use decision logs and planning checklists to improve cross-team alignment.
- Align on a sharedDefinition of Done to reduce ambiguity across teams.
- Foster inclusive, constructive feedback in code reviews to improve quality.

## Reuse & Consistency
- Publish versioned components and contract tests to encourage cross-project reuse.
- Maintain consistent naming conventions to facilitate readability and reuse.
- Enforce coding standards and library usage to reduce duplication.
- Promote canonical interfaces and versioned APIs to support long-term consistency.
- Centralize common utilities and patterns to maximize cross-project reuse.
- Document intended ownership and lifecycle for shared components.

## Observability & Debugging
- Standardize cross-service logging formats and propagate correlation IDs.
- Implement distributed tracing across services for end-to-end debugging.
- Define a minimal, stable set of telemetry points per feature and align dashboards with acceptance criteria.
- Build early, actionable dashboards to monitor health, latency, and error rates.
- Create deterministic reproducer scenarios for complex bugs to speed up debugging.
- Instrument code paths with clear, structured telemetry to simplify root-cause analysis.

## Edge Cases & Correctness
- Formalize invariants and pre/post-conditions for critical domains and verify them in CI.
- Use fuzz testing for parsing/validation paths to surface unexpected inputs.
- Document invariants clearly and enforce them during migrations.
- Validate assumptions with small, targeted property-based checks where feasible.
- Maintain explicit handling for null or missing data to avoid subtle defects.

## Refactoring & Maintenance
- Prioritize small, well-tested refactors with regression tests and clear rationale.
- Maintain a changelog and rationale for refactors to aid future maintenance.
- Plan migration-oriented refactors in small steps with rollback plans and traceable artifacts.
- Prefer reversible changes and document rollback strategies for high-risk edits.
- Schedule periodic maintenance reviews to prevent technical debt from accumulating.