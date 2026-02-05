# CLAUDE.md

## Project Goals

<!-- One-paragraph description of what this project does -->

**Current Milestone:** Phase 1 - Project Setup

<!-- Brief description of current focus -->

## Architecture Overview

```
<!-- ASCII diagram showing main application structure -->
<!-- Example:
+------------------+
|     Frontend     |
+------------------+
        |
+------------------+
|       API        |
+------------------+
        |
+------------------+
|    Database      |
+------------------+
-->
```

## Component Hierarchy

```
src/
├── components/
│   └── <!-- main components -->
├── hooks/
│   └── <!-- custom hooks -->
├── services/
│   └── <!-- business logic -->
├── store/
│   └── <!-- state management -->
├── types/
│   └── <!-- TypeScript types -->
└── utils/
    └── <!-- utility functions -->
```

## Design Style Guide

**Tech stack:**
- <!-- Framework (e.g., React 18, Next.js 14) -->
- <!-- Language (e.g., TypeScript) -->
- <!-- Build tool (e.g., Vite, Webpack) -->
- <!-- Package manager (e.g., npm, bun, pnpm) -->
- <!-- Styling (e.g., Tailwind CSS, CSS Modules) -->
- <!-- State management (e.g., Zustand, Redux) -->

**Visual style:**
- <!-- Color scheme -->
- <!-- Typography -->
- <!-- Spacing/layout conventions -->

**Component patterns:**
- <!-- e.g., Functional components with hooks -->
- <!-- e.g., Custom hooks for reusable logic -->
- <!-- e.g., TypeScript strict mode -->

**Core UX principles:**
- <!-- e.g., Fast feedback, accessibility -->

**Copy tone:**
- <!-- e.g., Brief, clear, no jargon -->

## Constraints & Policies

**Security - MUST follow:**
- <!-- e.g., Sanitize user input -->
- <!-- e.g., Validate all external data -->
- <!-- e.g., Never expose secrets in client code -->

**Code quality:**
- <!-- e.g., TypeScript strict mode -->
- <!-- e.g., ESLint + Prettier -->
- <!-- e.g., Meaningful names -->

**Dependencies:**
- <!-- e.g., Prefer minimal, well-maintained packages -->
- <!-- e.g., Audit before adding -->

## Repository Etiquette

**Branching:**
- ALWAYS create a feature branch before starting changes
- NEVER commit directly to `main`
- Branch naming: `feature/description` or `fix/description`

**Git workflow:**
1. Create branch: `git checkout -b feature/your-feature`
2. Develop and test locally
3. Use `/update-docs` to update documentation
4. Use `/commit` to commit changes
5. Push and create PR to merge into `main`

**Before pushing:**
1. Run dev server and test manually
2. Run linter: `bun run lint`
3. Run build: `bun run build`

**Commits:**
- Write clear commit messages
- Keep commits focused on single changes
- Use conventional commit format: `feat:`, `fix:`, `docs:`, etc.

**Pull requests:**
- Create PRs for all changes to `main`
- NEVER force push to `main`
- Include description of what changed and why

## Documentation

- [Changelog](changelog.md) - Version history
- [Project Status](project_status.md) - Current progress
- [Project Overview](project_overview.md) - Technical deep-dive

Use `/update-docs` command after making changes to keep documentation current.
