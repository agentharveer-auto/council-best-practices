## Code Writer Best Practices

## Requirements Gathering
- Define a clear, testable contract and acceptance criteria before coding to prevent scope creep.

## API Design
- Design stable, well-documented interfaces that decouple frontend and backend concerns and enable independent testing.

## Architecture & Modularity
- Isolate core logic into pure, side-effect-free units that are easy to unit test and reuse.

## Performance & Optimization
- Apply memoization, caching, or algorithmic improvements only after measuring impact to avoid premature optimization.

## Testing Strategy
- Build a balanced test pyramid emphasizing unit tests for logic, integration tests for interfaces, and end-to-end tests for user flows.

## Quality & Reliability
- Validate inputs at every boundary and provide actionable error messages to aid users and developers.

## Documentation & Knowledge Transfer
- Document interfaces, usage patterns, and decisions in concise, version-controlled docs rather than task-specific details.

## Versioning & Deployability
- Keep modules loosely coupled to support independent deployment and backward-compatible APIs.

## Security
- Treat all external input as untrusted and validate thoroughly at network and API boundaries.

## Collaboration & Process
- Establish clear ownership, code reviews, and a single source of truth for the core algorithm to reduce drift.

## Reuse & Consistency
- Favor reusable utilities and patterns across projects to reduce cognitive load and duplication.

## Observability & Debugging
- Instrument critical functions with lightweight logging or tracing to expedite debugging in production.

## Edge Cases & Correctness
- Prioritize correctness with coverage of edge cases and invariants before chasing performance gains.

## Refactoring & Maintenance
- Make small, well-tested refactors with incremental commits to minimize risk and maintainability.