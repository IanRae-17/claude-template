# Claude-Optimized Project Template

A template repository structured to work effectively with Claude Code. Includes documentation templates and custom commands for maintaining docs and git workflow.

## Quick Start

1. Clone this template
2. Fill in the documentation templates in `docs/`
3. Start building - use `/update-docs` and `/commit` as you work

## Structure

```
project-root/
├── .claude/
│   ├── settings.local.json      # Points Claude to docs/CLAUDE.md
│   └── commands/
│       ├── update-docs.md       # /update-docs command
│       └── commit.md            # /commit command
├── docs/
│   ├── CLAUDE.md                # Quick reference (Claude reads this first)
│   ├── changelog.md             # Version history
│   ├── project_overview.md      # Technical deep-dive
│   └── project_status.md        # Phase tracking
└── README.md
```

## Documentation Files

| File | Purpose | When to Update |
|------|---------|----------------|
| `docs/CLAUDE.md` | Quick reference for Claude | Architecture/structure changes |
| `docs/changelog.md` | Version history | Every feature/fix |
| `docs/project_status.md` | Progress tracking | Phase completions |
| `docs/project_overview.md` | Technical reference | Major features |

## Custom Commands

### `/update-docs`

Updates all documentation files based on recent code changes. Does not commit.

**Use after:** Completing a feature, fixing a bug, or making structural changes.

### `/commit`

Creates a git commit on the current feature/fix branch.

**Safety features:**
- Refuses to commit on `main` or `master`
- Does not push to remote
- Requires meaningful commit message

**Use for:** Committing changes on feature branches.

## Workflow

1. Create a feature branch: `git checkout -b feature/my-feature`
2. Build your feature
3. Run `/update-docs` to update documentation
4. Run `/commit` to commit your changes
5. Push and create PR when ready

## Customization

### Adjust Documentation Structure

Edit the templates in `docs/` to match your project's needs. The section headers are suggestions - add, remove, or rename as needed.

### Add More Commands

Create new `.md` files in `.claude/commands/` to add custom commands. The filename becomes the command name (e.g., `test.md` becomes `/test`).

### Change Claude's Entry Point

Edit `.claude/settings.local.json` to point Claude to different or additional files:

```json
{
  "instructions": [
    "docs/CLAUDE.md",
    "docs/another-file.md"
  ]
}
```

## License

MIT - Use this template however you like.
