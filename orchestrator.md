## Product Management
- Always clarify acceptance criteria and edge cases before design to avoid scope creep.
- Define measurable success criteria and ensure testability aligns with QA coverage and performance expectations.
- Document constraints and assumptions up front to prevent misalignment during implementation.

## System Design & Algorithmic Approach
- Prefer incremental state propagation (e.g., running value) over rebuilding data on each traversal.
- Use a simple, consistent data representation to minimize coupling and maintenance burden.
- DFS typically provides a straightforward and expressive approach for root-to-leaf path problems.

## Backend Engineering Practices
- Validate inputs and handle empty or None roots gracefully to establish stable baselines.
- Use efficient bitwise updates (e.g., value = (value << 1) | node.val) to accumulate binary-path values.
- Write clear, idiomatic code with concise comments and minimize reliance on global mutable state.

## Quality Assurance & Testing
- Craft a test plan that covers empty trees, single-node trees, balanced and skewed trees, all-zeros, all-ones, mixed bits, and large trees.
- Leverage automated, deterministic tests using a standard framework and keep tests aligned with acceptance criteria.
- Include robustness tests for invalid inputs and boundary conditions to ensure graceful failure modes.

## Performance & Complexity
- Target O(N) time complexity and O(H) auxiliary space, with O(N) worst-case space in highly skewed trees.

## Documentation & Maintainability
- Document API contracts, edge-case behavior, and design rationale in the README to aid future maintenance.

## Edge Case Handling
- Define and apply consistent behavior for empty trees and None nodes across implementations.

## Error Handling
- Include defensive guards for unexpected values while relying on input constraints wherever feasible.