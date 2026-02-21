## Code Writer Best Practices

## Requirements Gathering
- Document forward-compatible constraints to guide safe future expansions.

## API Design
- Version APIs early and communicate deprecations to prevent breaking clients.

## Architecture & Modularity
- Prefer evolvable data representations (e.g., JSON-based state) to minimize schema migrations when rules evolve.

## Performance & Optimization
- Measure impact before optimizing; avoid premature optimization.

## Testing Strategy
- Adopt a test pyramid and ensure coverage across unit, integration, and end-to-end tests; include property-based tests.

## Security
- Implement defense-in-depth with least privilege across services.

## Documentation & Knowledge Transfer
- Document interfaces and decisions in version-controlled docs; avoid task-specific details.

## Versioning & Deployability
- Aim for independent deployability and clear versioning of modules to ease rollback.

## Collaboration & Process
- Establish clear ownership and code reviews to reduce drift.

## Reuse & Consistency
- Maintain consistent naming conventions to facilitate code reuse and readability.

## Observability & Debugging
- Standardize cross-service logging formats and use correlation IDs to enable end-to-end tracing.

## Edge Cases & Correctness
- Use invariants and property-based testing to surface edge cases and ensure correctness.

## Refactoring & Maintenance
- Prioritize small, well-tested refactors with incremental commits to minimize risk.