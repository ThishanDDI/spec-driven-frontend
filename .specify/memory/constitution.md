<!-- Sync Impact Report
Version Change: 1.0.0 → 1.1.0 (MINOR: Added Vercel React best practices principle)
New Principle: VI. Vercel React Best Practices (memoization, code-splitting, concurrent features, optimization)
Templates Updated: ✅ plan-template.md, ✅ spec-template.md, ✅ tasks-template.md
Reference: Vercel React optimization patterns and performance standards
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

### VI. Vercel React Best Practices
Follow Vercel's React best practices for optimal performance and maintainability:
- Use `React.memo()` for expensive pure components to prevent unnecessary re-renders
- Implement proper memoization: `useMemo()` for computed values, `useCallback()` for stable function references
- Leverage `React.lazy()` + `Suspense` for code-splitting on route and feature boundaries
- Prefer controlled components for forms; minimize uncontrolled component usage
- Use concurrent features: `useTransition()` for non-blocking state updates, `useDeferredValue()` for value debouncing
- Optimize images with modern formats (WebP, AVIF); use `loading="lazy"` for below-the-fold images
- Avoid prop drilling; use Context API for theme/locale/user state; Redux for complex domain state
- Keep components small and focused; extract sub-components when exceeding 200 lines
- Use strict equality (`===`) checks in dependencies arrays; avoid object/array literals in deps
- Profile with React DevTools Profiler before and after optimization; measure real user metrics

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

**Version**: 1.1.0 | **Ratified**: 2026-05-11 | **Last Amended**: 2026-05-11

## 7. Performance & Optimization (Vercel React Best Practices)

This project follows **Vercel React Best Practices** for optimal performance and user experience. 
The guidelines cover memoization, code-splitting, concurrent rendering, and image optimization.

For detailed implementation patterns, refer to the installed `vercel-react-best-practices` skill.

Key areas:
- Use `React.memo()` for pure components
- Implement `useMemo()` and `useCallback()` strategically
- Code-split with `React.lazy()` + `Suspense`
- Optimize images (WebP, AVIF, lazy-loading)
- Profile with React DevTools before and after changes
