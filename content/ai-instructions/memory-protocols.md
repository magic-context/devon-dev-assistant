# Memory Protocols

## What to Remember

### Always Update
- Tech stack changes (new libraries, framework upgrades, migrations) → `memory/user-profile.md`
- Architecture decisions (and rationale) → project files in `active-projects/`
- New projects or project changes → `active-projects/`
- Tech debt items discovered → `active-projects/tech-debt.md`
- Lessons learned from bugs or incidents → `historical/`

### Update Per Session
- What was worked on
- Decisions made and alternatives considered
- Issues encountered and how they were resolved
- New patterns or conventions established

### Update When Projects Complete
- Archive to `historical/` with retrospective notes
- Document key decisions for future reference
- Note technologies that worked well vs. didn't
- Record reusable patterns or solutions

## How to Update

### Dev Profile (`memory/user-profile.md`)
Keep current with:
- Languages and frameworks (with proficiency level)
- Current tech stack per project
- Experience level (updates as they grow)
- Notable achievements and shipped projects
- Areas of expertise and interest

### Preferences (`memory/preferences.md`)
Track:
- IDE and editor setup
- Code style preferences (formatting, naming, patterns)
- Git workflow (branching strategy, commit style)
- Testing philosophy (TDD, test-after, coverage targets)
- Review preferences (detailed vs. high-level feedback)
- Documentation style
- Deployment preferences

### Project Context
For each active project, track:
- Tech stack and architecture
- Key decisions and their rationale
- Known issues and tech debt
- Conventions and patterns used
- Team context (solo, pair, team size)

## Memory Maintenance

- **Track decisions with rationale** — "We chose X because Y; considered Z but rejected because..."
- **Archive, don't delete** — past projects go to `historical/`
- **Keep tech debt visible** — out of sight = out of mind
- **Ask before major updates** — "You switched to Vite? Let me update your tooling profile."
- **Reference past decisions** — "We had a similar issue in project X — the solution there was..."
