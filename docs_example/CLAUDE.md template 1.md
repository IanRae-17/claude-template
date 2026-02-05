
# CLAUDE.md

  
## Project Goals

  

**Current Milestone:** - 

  

## Architecture Overview

```

```

## Component Hierarchy

```

```

## Design Style Guide

**Tech stack:** 

**Visual style:**
- 

**Component patterns:**
- 

**Core UX principles:**
- 

**Copy tone:**
- 

## Constraints & Policies

  

**Security - MUST follow:**
- 

**Code quality:**
-  

**Dependencies:**
- 

## Repository Etiquette

**Branching:**

- ALWAYS create a feature branch before starting major changes

- NEVER commit directly to `main`

- Branch naming: `feature/description` or `fix/description`

**Git workflow for major changes:**

1. Create a new branch: `git checkout -b feature/your-feature-name`

2. Develop and commit on feature branch

3. Test locally before pushing:

   - `npm run dev` - start dev server at localhost:3000

   - `npm run lint` - check for linting errors

   - `npm run build` - production build to catch type errors

4. Push the branch: `git push -u origin feature/your-feature-name`

5. Create a PR to merge into `main`

6. Use the `/update-docs-and-commit` slash command for commits - this ensures docs are updated alongside code changes.

  
**Commits:**

- Write clear commit messages describing the change

- Keep commits focused on single changes

  
**Pull requests:**

- Create PRs for all changes to `main`

- NEVER force push to `main`

- Include descriptions of what changed and why

**Before pushing:**

1. `npm run dev` - start dev server at localhost:3000

2. `npm run lint` - check for linting errors

3. `npm run build` - production build to catch type errors

## Documentation

- [Project Spec](docs/project_spec.md) - Full Requirements and tech details

- [Architecture](docs/architecture.md) - System design and data flow

- [Changelog](docs/changelog.md) - Version History

- [Project Status](docs/project_status.md) - Current progress

- Update files in the docs folder after major milestones and major additions to the project.

- Use the /update-docs-and-commit slash command when making git commits