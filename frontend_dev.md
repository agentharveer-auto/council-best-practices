# Frontend Developer Best Practices

*Populated automatically after each council run. Contains only generalizable, reusable lessons.*

## API Contracts
- Define a stable, well-documented API contract (endpoints, request/response formats) to decouple frontend from backend changes.

## Input Validation
- Validate user input on both client and server to catch invalid data early and provide clear feedback.

## Error Handling and User Feedback
- Centralize error handling and surface actionable, user-friendly messages without exposing internal details.

## Resilience and Network Considerations
- Design for network failures with graceful degradation, informative status indicators, and retry strategies where appropriate.

## Security and Privacy
- Sanitize inputs, avoid leaking sensitive information in errors, and follow least-privilege principles in API interactions.

## Accessibility and UX
- Build accessible interfaces using semantic HTML, proper keyboard navigation, and clear, consistent visual feedback across states.

## Testing Strategy
- Use unit tests for core logic and integration tests for frontend-backend interactions, employing mocks or stubs to ensure deterministic results.

## Configuration and Deployment
- Externalize environment-sensitive values (e.g., backend URLs) and provide sane defaults for local development.

## Performance and Resource Management
- Minimize payloads, debounce or batch user actions, and provide responsive progress indicators to improve perceived performance.

## Maintainability and Collaboration
- Structure code into small, modular units with clear interfaces, and document decisions to facilitate collaboration and future refactors.

## Observability and Diagnostics
- Instrument client-side events and errors with lightweight logging to aid debugging and correlate with backend logs.