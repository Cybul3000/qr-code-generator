<!--
=============================================================================
SYNC IMPACT REPORT
=============================================================================
Version Change: [INITIAL] → 1.0.0
Principles Defined:
  - I. Accessibility (Non-Negotiable)
  - II. Readability First
  - III. Responsive Design
  - IV. Testing Standards
  - V. Safety First

Added Sections:
  - Core Principles (5 principles)
  - Quality Standards
  - Development Workflow
  - Governance

Templates Requiring Updates:
  ✅ plan-template.md - Constitution Check gates align with principles
  ✅ spec-template.md - Requirements aligned with accessibility & testing
  ✅ tasks-template.md - Task categorization reflects testing discipline

Follow-up TODOs:
  - None - all placeholders resolved

Rationale for MINOR version (1.0.0):
  - Initial ratification of constitution
  - Establishes baseline governance framework
  - Five core principles defined with clear enforcement rules
=============================================================================
-->

# QR Code Generator Constitution

## Core Principles

### I. Accessibility (Non-Negotiable)

Accessibility is a foundational requirement, not an optional enhancement. The project MUST target perfect accessibility scores and ensure all features are usable by individuals regardless of ability.

**Rules**:
- MUST achieve WCAG 2.1 Level AAA compliance where feasible, minimum Level AA
- MUST use semantic HTML elements and proper ARIA attributes
- MUST ensure keyboard navigation works for all interactive elements
- MUST provide sufficient color contrast ratios (minimum 4.5:1 for normal text, 3:1 for large text)
- MUST include alt text for all images and meaningful labels for form inputs
- MUST test with automated accessibility tools AND manual screen reader testing
- MUST NOT rely solely on color to convey information
- MUST ensure focus indicators are clearly visible

**Rationale**: Accessibility is a human right. Building accessible software from the start is more cost-effective than retrofitting, and it improves the experience for all users, not just those with disabilities.

### II. Readability First

Code readability takes precedence over performance optimization. Code MUST be written for humans first, compilers second.

**Rules**:
- MUST use descriptive variable, function, and class names that convey intent
- MUST prefer explicit, verbose code over clever, terse solutions
- MUST include comments explaining "why" for non-obvious logic (not "what")
- MUST limit function/method length to maintain comprehension (target <50 lines)
- MUST avoid deep nesting (maximum 3 levels preferred)
- MUST use consistent formatting and follow language conventions
- SHOULD optimize only when performance issues are measured and documented

**Rationale**: Code is read far more often than it is written. Readable code reduces bugs, eases maintenance, accelerates onboarding, and enables faster feature development. Premature optimization creates technical debt.

### III. Responsive Design

All layouts and interfaces MUST work seamlessly across all devices and screen sizes, from mobile phones to large desktop displays.

**Rules**:
- MUST use responsive design patterns (fluid grids, flexible images, media queries)
- MUST test on mobile (320px+), tablet (768px+), and desktop (1024px+) breakpoints
- MUST ensure touch targets are minimum 44×44 pixels for mobile
- MUST avoid horizontal scrolling on any viewport size
- MUST use relative units (rem, em, %) over fixed pixels where appropriate
- MUST ensure text remains legible without zooming on all devices
- MUST test on both portrait and landscape orientations

**Rationale**: Users access applications on diverse devices. A responsive design ensures a consistent, high-quality experience regardless of how users choose to interact with the application.

### IV. Testing Standards

Rigorous testing is mandatory to ensure quality, maintainability, and confidence in changes.

**Rules**:
- MUST achieve minimum 80% unit test coverage for business logic
- MUST write tests before implementation when following TDD approach
- MUST include accessibility tests that programmatically verify WCAG compliance (target 100% automated coverage where possible)
- MUST test critical user journeys with integration tests
- MUST include error case testing, not just happy paths
- MUST ensure tests are deterministic and can run in any order
- MUST run tests in CI/CD pipeline; failing tests block merges
- SHOULD use testing pyramid approach: many unit tests, some integration tests, few E2E tests

**Rationale**: High test coverage catches regressions early, enables confident refactoring, serves as documentation, and reduces production bugs. Automated accessibility testing ensures compliance at scale.

### V. Safety First

Destructive operations require explicit confirmation. The codebase and user data MUST be protected from accidental loss.

**Rules**:
- MUST prompt for confirmation before deleting files, data, or resources
- MUST provide clear, specific warnings about the consequences of destructive actions
- MUST implement soft deletes or versioning where appropriate
- MUST include rollback capabilities for critical operations
- MUST validate user input to prevent unintended destructive operations
- MUST log destructive operations for audit trails
- MUST require explicit flags (e.g., --force) for batch deletions via CLI

**Rationale**: Accidental data loss is costly and damaging. Requiring confirmation prevents mistakes, reduces support burden, and builds user trust. Once deleted, data is often unrecoverable.

## Quality Standards

All code submissions MUST meet the following baseline quality standards:

- Pass all automated tests (unit, integration, accessibility)
- Achieve minimum 80% test coverage for new code
- Pass linting and formatting checks
- Include documentation for public APIs and complex logic
- Demonstrate responsive behavior across required breakpoints
- Pass automated accessibility audits (axe, Lighthouse, WAVE)
- Include manual testing evidence for accessibility (screen reader testing notes)

## Development Workflow

### Code Review Requirements

- All changes MUST be reviewed by at least one other developer
- Reviewers MUST verify compliance with constitution principles
- Reviewers MUST check that tests adequately cover changes
- Reviewers MUST verify accessibility compliance for UI changes

### Testing Gates

- Unit tests MUST pass before code review
- Integration tests MUST pass before merge
- Accessibility tests MUST score minimum 95/100 on Lighthouse accessibility audit
- Manual accessibility testing MUST be documented in PR description

### Feature Implementation

- Specifications MUST be approved before implementation begins
- Test cases MUST be written and reviewed before implementation (when following TDD)
- Features MUST be implemented incrementally using spec-driven workflow
- Each user story MUST be independently testable and deliverable

## Governance

This constitution supersedes all other development practices and guidelines. All team members MUST adhere to these principles in their work.

### Amendment Process

Amendments to this constitution require:
1. Documented proposal with rationale and impact analysis
2. Review and approval from project stakeholders
3. Version increment following semantic versioning rules:
   - **MAJOR**: Backward-incompatible governance changes or principle removals
   - **MINOR**: New principles added or material expansions
   - **PATCH**: Clarifications, typo fixes, non-semantic refinements
4. Migration plan for existing code when principles change
5. Update to dependent templates and documentation

### Compliance Enforcement

- All pull requests MUST verify compliance with core principles
- Non-compliance MUST be justified and documented in complexity tracking
- Repeated violations require architecture review and remediation plan
- Constitution compliance is checked at specification and implementation phases

### Living Document

This constitution is maintained at `.specify/memory/constitution.md` and serves as the authoritative source for project governance. For runtime development guidance, refer to project-specific documentation in `.specify/templates/` and development guidelines.

**Version**: 1.0.0 | **Ratified**: 2026-01-08 | **Last Amended**: 2026-01-08
