## Requirements Gathering
- Define acceptance criteria, inputs, and constraints before designing tests to avoid scope creep.
- Identify non-functional requirements (performance, determinism, repeatability) early to guide test design.
- Ensure the test strategy aligns with the product requirements and error-handling expectations.

## Reference & Determinism
- Build a small, independent reference implementation to verify correctness across edge cases.
- Keep the reference logic deterministic and well-documented to serve as a single source of truth.

## Test Design Patterns
- Use parameterized tests to cover a broad input space with minimal duplication.
- Favor pure functions and deterministic outputs to simplify reasoning and debugging.

## Boundary & Transition Testing
- Exercise boundary values where internal state or behavior changes to catch off-by-one and transition errors.
- Include both sides of a boundary (just below and at the threshold) to confirm correct transitions.

## Modulo Arithmetic & Numeric Safety
- Apply modulo after each arithmetic step to prevent overflow and ensure bounded results.
- Prefer using a canonical modulo constant and avoid duplicating literals.

## Data-Driven Test Architecture
- Centralize expected-value logic in a single helper to ensure consistency across tests.
- Keep test data separate from assertions to improve readability and maintainability.

## Large-Scale & Performance Considerations
- Include large input tests to validate performance viability without compromising test stability.
- Use timeouts or slow-test markers to communicate expectations to CI systems.

## Error Handling & Validation
- Validate input types and ranges in tests to ensure solutions fail gracefully and predictably.
- Assert that error messages are informative and stable across implementations.

## Cross-Language & Portability
- Design tests and reference logic to be easily ported to other languages, with minimal changes to the validation approach.
- Document the expected behavior clearly so other teams can reimplement tests in their preferred framework.

## CI/CD & Test Hygiene
- Keep tests deterministic and isolated, avoiding randomness or external dependencies.
- Organize tests with clear naming and grouping to enable selective running in CI.

## Documentation & Onboarding
- Include concise README notes explaining the testing strategy, how to adapt for different implementations, and how to run tests locally.