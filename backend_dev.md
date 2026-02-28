# Backend Developer Best Practices

*Populated automatically after each council run. Contains only generalizable, reusable lessons.*

## Core Computation Patterns
- Use a running accumulator updated by shifting left by the next piece's width and adding the piece, avoiding expensive string concatenation.

## Bit-length / Width Management
- Track the width of the next piece efficiently by increasing the width only when the next piece increases in digit-length (e.g., at powers of two for binary).

## Modulo Arithmetic
- Apply modulo after each update to prevent overflow and maintain modular invariants.

## Input Validation
- Validate inputs early with clear exceptions to fail-fast and provide robust API behavior.

## Complexity & Performance
- Favor O(n) time and O(1) space patterns for streaming composition tasks over building large intermediates.

## Reusability & Abstraction
- Encapsulate the computation in a pure function to maximize reusability across CLI, API, and tests.

## Testing & Validation
- Write deterministic tests with a canonical reference implementation and parameterization to cover boundary cases and large inputs.

## Documentation & Clarity
- Document function contracts (signature, constraints, behavior) to ensure maintainability.

## Separation of Concerns
- Provide clean separation between core logic and I/O to facilitate testing and extension.

## Readability
- Use clear, descriptive variable names and concise comments to improve readability and maintainability.

## Portability
- Favor standard language features for portability across environments and Python versions.

## Instrumentation
- Expose optional instrumentation (logging) that can be toggled without affecting performance in the hot path.

## Change Management
- Use diff-friendly, incremental changes to facilitate code reviews and future council iterations.

## Design Simplicity
- When merging multiple approaches, prefer simpler invariant-based designs over brittle, case-specific logic.