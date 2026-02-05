# Update Documentation

Update all project documentation files based on recent changes.

## Instructions

1. **Review Recent Changes**
   - Run `git diff` to see uncommitted changes
   - Run `git log -5 --oneline` to see recent commits
   - Identify what features, fixes, or changes were made

2. **Update docs/CLAUDE.md** (if needed)
   - Update "Current Milestone" if phase changed
   - Update Architecture Overview if structure changed
   - Update Component Hierarchy if new files/folders added
   - Update Tech Stack if new dependencies added
   - Keep this file concise - it's a quick reference

3. **Update docs/changelog.md**
   - Add entries under `[Unreleased]` section
   - Use appropriate subsections: Added, Changed, Fixed, Removed
   - Be specific about what changed and why
   - Update UI Components list if new components added
   - Update Dependencies list if packages added/removed

4. **Update docs/project_status.md**
   - Check off completed items with `[x]`
   - Update "Current Phase" header if phase changed
   - Update "Last Updated" date
   - Add new items to current phase if scope expanded
   - Move completed issues from "Known Issues" to "Recent Fixes"

5. **Update docs/project_overview.md** (for significant changes)
   - Add new sections for major features
   - Update architecture diagrams if structure changed
   - Document technical challenges and solutions
   - Update project statistics
   - This is the comprehensive reference - be thorough

## Guidelines

- Keep CLAUDE.md concise (quick reference)
- Keep changelog entries specific and actionable
- Keep project_status.md as a progress tracker
- Keep project_overview.md comprehensive and technical
- Do NOT commit changes - just update the files
- Maintain consistent formatting across all docs
