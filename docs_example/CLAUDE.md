# CLAUDE.md

## Project Goals

**Current Milestone:** Phase 1 - Project Setup & Foundation

A peer-to-peer web application where 2-5 users can collaborate on annotating video game map screenshots in real-time. Users can upload map images, place icons (house, chest, building, flag, marker), customize them with colors/labels/sizes, and overlay a colorable grid.

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│ Header: [PTP Map]                    [+ Create] [→ Join]    │
├────┬────────────────────────────────────────────────────────┤
│    │                                                        │
│ T  │                                                        │
│ o  │                    MapCanvas                           │
│ o  │              (Image + Grid + Icons)                    │
│ l  │                                                        │
│ b  │                                                        │
│ a  │                                                        │
│ r  │                                                        │
│    │                                                        │
└────┴────────────────────────────────────────────────────────┘

P2P Data Flow:
User Action → Local State → Broadcast via PeerJS → Remote State Update
```

## Component Hierarchy

```
src/
├── components/
│   ├── Canvas/
│   │   └── MapCanvas.tsx        # Main canvas with drag-drop upload
│   ├── Toolbar/
│   │   └── Toolbar.tsx          # Left sidebar with Lucide icons
│   ├── Session/
│   │   ├── CreateRoomModal.tsx  # Modal for creating rooms
│   │   └── JoinRoomModal.tsx    # Modal for joining rooms
│   ├── UI/
│   │   └── Modal.tsx            # Reusable modal component
│   └── Icons/                   # (To be implemented)
│       ├── MapIcon.tsx          # Individual icon
│       └── IconLabel.tsx        # Icon label tooltip
├── hooks/                       # (To be implemented)
│   ├── usePeerConnection.ts     # PeerJS connection logic
│   └── useRoomSync.ts           # State synchronization
├── services/                    # (To be implemented)
│   └── peerService.ts           # PeerJS wrapper
├── store/
│   └── mapStore.ts              # Zustand store
└── types/
    ├── map.ts                   # Map/icon types
    ├── peer.ts                  # Peer types
    └── messages.ts              # P2P message protocol
```

## Design Style Guide

**Tech stack:**

- React 18 + TypeScript
- Vite (build tool)
- Bun (package manager & runtime)
- PeerJS (WebRTC P2P)
- Zustand (state management)
- Tailwind CSS (styling)
- Lucide React (icons)
- @dnd-kit (drag and drop)
- react-colorful (color picker)
- react-dropzone (file upload)

**Visual style:**

- Minimalistic design - blacks, grays, whites only
- Dark theme (neutral-900, neutral-950 backgrounds)
- Slim left toolbar (48px)
- Session controls in header as icon buttons with modals
- No emojis - use Lucide icons throughout

**Component patterns:**

- Functional components with hooks
- Zustand for global state, local state for UI-only concerns
- Custom hooks for reusable logic (usePeerConnection, useRoomSync)
- TypeScript strict mode

**Core UX principles:**

- Real-time collaboration - changes sync instantly
- Simple room codes for easy sharing (e.g., "ABC123")
- Non-destructive - undo/redo support
- Mobile-responsive design

**Copy tone:**

- Brief, clear labels
- No jargon - "Create Room" not "Initialize P2P Session"
- Friendly error messages

## Constraints & Policies

**Security - MUST follow:**

- Validate all incoming P2P messages before applying
- Sanitize user-provided text (icon labels) to prevent XSS
- Limit room size to 5 peers maximum
- Rate limit message broadcasting to prevent flooding
- Never execute code received from peers

**Code quality:**

- TypeScript strict mode enabled
- ESLint + Prettier for consistent formatting
- Meaningful variable/function names
- Keep components focused and single-purpose

**Dependencies:**

- Prefer well-maintained, minimal dependencies
- Audit new packages before adding
- Keep bundle size reasonable

## Repository Etiquette

**Branching:**

- ALWAYS create a feature branch before starting major changes

- NEVER commit directly to `main`

- Branch naming: `feature/description` or `fix/description`

**Git workflow for major changes:**

1. Create a new branch: `git checkout -b feature/your-feature-name`

2. Develop and commit on feature branch

3. Test locally before pushing:

   - `bun dev` - start dev server at localhost:5173

   - `bun run lint` - check for linting errors

   - `bun run build` - production build to catch type errors

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

1. `bun dev` - start dev server at localhost:5173

2. `bun run lint` - check for linting errors

3. `bun run build` - production build to catch type errors

## Documentation

- [Changelog](docs/changelog.md) - Version History

- [Project Status](docs/project_status.md) - Current progress

- Update files in the docs folder after major milestones and major additions to the project.
