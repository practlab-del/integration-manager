<!-- Sync Impact Report: Initial constitution creation for integration-manager. Version: new → 1.0.0. Added: Core Principles (5), Technology Stack Requirements, Development Workflow, Testing Standards. Deferred: None. -->

# Integration Manager Constitution

## Core Principles

### I. Strict Type Safety
Type safety MUST be enforced across the entire stack. React TypeScript components MUST use proper type annotations. FastAPI endpoints MUST leverage Python type hints. All API contracts MUST be strictly typed and validated. Type errors MUST be caught at compile-time, never at runtime.

### II. Secure Pydantic Validation
All FastAPI request/response models MUST use Pydantic v2+ for runtime validation. Field constraints MUST be strictly defined. Custom validators MUST be implemented for complex business logic. Data parsing MUST be explicit and never implicit.

### III. Test-First Development (NON-NEGOTIABLE)
TDD MUST be followed: tests written first, user approval obtained, tests must fail, then implementation. React components MUST be tested with Vitest. FastAPI endpoints MUST be tested with pytest. Unit tests MUST cover business logic. Integration tests MUST verify inter-service contracts.

### IV. Comprehensive Testing Standards
Backend tests MUST achieve >90% coverage with pytest. Frontend tests MUST achieve >80% coverage with Vitest. All PRs MUST include test coverage reports. Integration tests MUST be written for any new API endpoints, shared schemas, or inter-service communication.

### V. UI/UX Consistency with Tailwind CSS
Tailwind CSS MUST be the primary styling framework. Custom components MUST use Tailwind utility classes. Design system MUST be consistent across the application. CSS customizations MUST be documented and follow Tailwind's utility-first approach.

## Technology Stack Requirements

**Frontend**: React 18+, TypeScript 5+, Tailwind CSS 3+, Vitest, @testing-library/react, React Router v6+

**Backend**: Python 3.11+, FastAPI 0.100+, Pydantic v2+, SQLAlchemy 2.0+, pytest, httpx, pytest-asyncio

**Development**: Node.js 20+, npm, pip, Git

**Standards**: ESLint (Airbnb config), Prettier, mypy, ruff (for linting, formatting, and import sorting)

**Contract Sync**: openapi-ts

## Development Workflow

Code review MUST be required for all PRs. PR descriptions MUST include Jira ticket references. Branch naming MUST follow `feature/[ticket]-description` or `fix/[ticket]-description` patterns. Squash merging MUST be used for feature branches, and **PR titles MUST follow Conventional Commits format**. Complexity MUST be justified in PR descriptions. All PRs MUST verify constitution compliance.

## Testing and Quality Gates

All tests MUST pass before merging. Type checking (TypeScript + mypy) MUST be part of CI/CD. Linting (ESLint + ruff) MUST pass before commits. Security scanning MUST be performed on dependencies. Performance tests MUST be included for critical paths. Load testing MUST be considered for high-traffic endpoints.

## Governance

This Constitution supersedes all other development practices. Amendments require documentation, team approval, and migration plan. All changes MUST follow semantic versioning. Complexity MUST always be justified. Use architecture decision records (ADRs) for significant technical decisions. Changes to this constitution must not go side by side with any other feature implementation or documentation. Strict exceptions to coverage or TDD gates for pure documentation or configuration-only changes MUST be explicitly tagged with [BYPASS] in the tracking task.

**Version**: 1.0.0 | **Ratified**: 2026-10-09 | **Last Amended**: 2026-10-09