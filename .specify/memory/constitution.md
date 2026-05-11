<!-- Sync Impact Report
Version Change: 0.0.0 → 1.0.0 (MAJOR: Initial constitution with React/UI standards)
New Principles: React Components, Tailwind CSS, Mobile-First Design
Templates Updated: ✅ plan-template.md, ✅ spec-template.md, ✅ tasks-template.md
Follow-up: Consider versioning policy and testing standards in future amendments
-->

# Spec-Driven Frontend Constitution
Design and implementation standards for React-based frontend applications.

## Core Principles

### I. React Functional Components Only
All React components MUST be implemented as functional components using modern React patterns 
(hooks, context, etc.). Class components are not permitted. This ensures consistency, 
simplicity, and alignment with React's current best practices and ecosystem tooling.

### II. Tailwind CSS Styling
All styling MUST be implemented using Tailwind CSS utility classes. No CSS-in-JS, styled-components, 
or inline styles permitted unless justified in code review. Tailwind enforces design consistency 
and enables efficient maintenance of design systems.

### III. Mobile-First UI Design
All interfaces MUST be designed and implemented mobile-first. Desktop breakpoints are applied 
progressively via Tailwind's responsive prefixes (md:, lg:, xl:). Testing on mobile dimensions 
is required before desktop expansion.

### IV. Component Documentation
Every component MUST include JSDoc comments describing props, return type, and usage examples. 
This ensures developer clarity and enables automated documentation generation.

### V. Testing Requirements
Components require unit tests for logic and visual regression tests for UI changes. 
Test coverage minimum: 80% for components and utilities.

## Technology Stack

**Mandatory:**
- React 18+ (functional components only)
- Tailwind CSS 3+ (no alternative CSS libraries)
- Vite (build tool and dev server)
- Vitest + React Testing Library (testing)

**Optional:**
- TypeScript (strongly recommended for type safety)
- React Router (if routing needed)
- State management: Context API preferred; Redux acceptable for complex state

## Development Workflow

1. **Branch naming**: feature/*, bugfix/*, chore/*
2. **Commit format**: Conventional commits (feat:, fix:, refactor:, docs:, test:)
3. **PR requirements**: 
   - Functional component structure verified
   - Tailwind classes used exclusively for styling
   - Mobile-first responsive design confirmed
   - All tests passing (min 80% coverage)
4. **Code review checklist**:
   - ✓ No class components
   - ✓ Tailwind only (no CSS modules/inline styles)
   - ✓ Mobile-first approach applied
   - ✓ Component props documented
   - ✓ Tests included and passing

## Governance

This constitution supersedes all conflicting development practices. All PRs must verify 
compliance with these principles before merge. Amendments require:
1. Documentation of rationale
2. Impact analysis on existing code
3. Approval via consensus (team lead + 1 reviewer minimum)
4. Migration plan for breaking changes

Version changes follow semantic versioning:
- MAJOR: Principle removals or redefinitions
- MINOR: New principles/sections added
- PATCH: Clarifications and wording refinements

**Version**: 1.0.0 | **Ratified**: 2026-05-11 | **Last Amended**: 2026-05-11
