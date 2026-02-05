# Commit Changes

Create a git commit on the current feature or fix branch.

## Safety Rules - MUST FOLLOW

- **NEVER** commit if on `main` or `master` branch - REFUSE and tell user to create a feature branch
- **NEVER** push to remote - only commit locally
- **NEVER** force push
- **NEVER** use `--no-verify` flag

## Instructions

1. **Check Current Branch**
   ```bash
   git branch --show-current
   ```
   - If on `main` or `master`: STOP and tell the user to create a feature branch first
   - Acceptable branch names: `feature/*`, `fix/*`, `bugfix/*`, `hotfix/*`, `chore/*`, or any non-main branch

2. **Review Changes**
   ```bash
   git status
   git diff
   git diff --staged
   ```
   - Understand what files changed and why
   - Identify if any sensitive files should be excluded (.env, credentials, etc.)

3. **Stage Files**
   - Stage specific files by name (preferred over `git add .`)
   - Do NOT stage sensitive files (.env, credentials, secrets, etc.)
   - Do NOT stage large binary files unless necessary

4. **Create Commit**
   - Write a clear, descriptive commit message
   - Format: `<type>: <description>`
   - Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`
   - Keep the first line under 72 characters
   - Add body with details if needed

   Example:
   ```bash
   git commit -m "feat: add user authentication flow

   - Implement login/logout functionality
   - Add JWT token handling
   - Create auth context provider"
   ```

5. **Verify Commit**
   ```bash
   git log -1
   git status
   ```
   - Confirm commit was created successfully
   - Confirm working directory is clean (or only has intentionally unstaged files)

## What NOT to Do

- Do NOT push after committing - let the user decide when to push
- Do NOT commit to main/master under any circumstances
- Do NOT stage all files blindly with `git add -A` or `git add .`
- Do NOT include secrets, credentials, or .env files
