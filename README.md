# Devon — Your AI Dev Assistant That Remembers Your Entire Codebase

Every AI coding tool starts from scratch. Devon knows **your stack** — your architecture decisions, your coding conventions, the tech debt you've been ignoring, and why you chose Postgres over MongoDB six months ago. He gives technical guidance that gets smarter every session because he never forgets your context.

## The Problem

You ask an AI to help with a feature. It suggests a pattern that contradicts your existing architecture. It doesn't know you're using TypeScript with Zod validation, that your auth middleware already handles JWT tokens, or that you tried Redis caching last quarter and rolled it back. You re-explain your entire project. Every. Single. Time.

**Devon fixes this.**

## What Devon Does

🏗️ **Architecture Awareness** — Devon knows your system design, remembers why decisions were made, and keeps recommendations consistent with your existing patterns

💻 **Context-Rich Coding Help** — Code suggestions that match your stack, style, and conventions — not generic snippets from Stack Overflow

📋 **Tech Debt Tracking** — Devon maintains a living list of technical debt, helps prioritize it, and remembers when you address items

🔍 **Code Review Support** — Reviews with project-specific context: "This breaks the pattern we established in the auth module"

🔒 **Security Awareness** — OWASP-informed security guidance integrated into every coding conversation

📊 **Decision Tracking** — Architecture decisions with rationale, alternatives considered, and tradeoffs — searchable forever

## How It Works

Devon is an **AI Specialist** built on [Magic Context](https://magiccontext.ai). Instead of starting every AI conversation from scratch, Devon maintains a persistent workspace — your tech stack, project architecture, coding preferences, and decision history — that carries across every session.

```
┌──────────────────────────────────────────┐
│          Devon's Workspace               │
├──────────────────────────────────────────┤
│                                          │
│  📋 AI Instructions                      │
│  ├── Development personality & approach  │
│  ├── Coding principles                   │
│  └── Memory protocols                    │
│                                          │
│  🧠 Memory                               │
│  ├── Dev profile & tech stack            │
│  ├── Coding preferences & style          │
│  └── Project history & decisions         │
│                                          │
│  📚 Knowledge Base                       │
│  ├── Architecture patterns               │
│  ├── Code quality (SOLID, clean code)    │
│  ├── Tooling reference                   │
│  └── Security basics (OWASP)             │
│                                          │
│  🎯 Active Projects                      │
│  ├── Current codebases                   │
│  └── Tech debt & learning queue          │
│                                          │
│  📝 Templates                            │
│  ├── Project setup                       │
│  ├── Bug reports & feature specs         │
│  └── Code review checklists              │
│                                          │
└──────────────────────────────────────────┘
```

### The Magic Context Difference

Traditional AI is **stateless** — it forgets everything between conversations. Magic Context gives AI specialists **persistent memory** through structured workspaces. This means:

- **Session 1:** Devon learns your stack, conventions, and current projects
- **Session 5:** Devon suggests code that follows your existing patterns and references past decisions
- **Session 20:** Devon catches when a new feature conflicts with your architecture and suggests the right approach
- **Session 50+:** Devon knows your codebase history better than most team members

**Your context is yours.** It's stored as plain markdown files you can read, edit, or export anytime. No black box. No vendor lock-in.

## Quick Start

### Import to AI Specialists Hub

```bash
# Via the Magic Context import feature
import_specialist github.com/magic-context/devon-dev-assistant
```

Or use the import tool in [AI Specialists Hub](https://aispecialistshub.com) with:
```
https://github.com/magic-context/devon-dev-assistant
```

### First Session

Devon will guide you through a dev intake:
1. Your experience level and primary languages
2. Current tech stack and frameworks
3. Active projects and their architecture
4. Coding style and workflow preferences
5. Current pain points and goals

Then he'll set up context for your projects.

### Ongoing Use

- **Architecture discussions** with full project context
- **Coding help** that matches your conventions
- **Code reviews** informed by your patterns and history
- **Tech debt management** with prioritized tracking
- **Security checks** integrated into development conversations
- **Decision documentation** that persists forever

## Repository Structure

```
devon-dev-assistant/
├── configuration/
│   └── module.json
├── content/
│   ├── README.md
│   ├── ai-instructions/
│   │   ├── core-instructions.md
│   │   ├── getting_started.md
│   │   └── memory-protocols.md
│   ├── memory/
│   │   ├── user-profile.md
│   │   └── preferences.md
│   ├── knowledge/
│   │   ├── architecture-patterns.md
│   │   ├── code-quality.md
│   │   ├── tooling-reference.md
│   │   ├── security-basics.md
│   │   └── templates/
│   │       ├── project-setup.md
│   │       ├── bug-report.md
│   │       ├── feature-spec.md
│   │       └── code-review-checklist.md
│   ├── active-projects/
│   │   └── current-goals.md
│   ├── historical/
│   └── feedback/
└── README.md
```

## Who This Is For

- **Solo developers** who need a second brain for architecture and decisions
- **Team leads** who want persistent technical context across projects
- **Career changers** learning to code with guided, contextual support
- **Anyone tired of re-explaining their codebase** to AI every single session

## Suggested MCP Skill Pairings

Devon works with any MCP-compatible AI agent (Claude, GPT, Gemini, etc.):

- **Git / Code Repository** — PR tracking, issues, CI runs, code reviews
- **Coding Agent** — Automated code analysis, refactoring, and tech debt assessment
- **Kanban / Task Boards** — Sprint boards and backlog management
- **Team Messaging** — Standup summaries and blocker alerts
- **Conversation History** — Recall past architectural decisions

## Requirements

- [AI Specialists Hub](https://aispecialistshub.com) account (or any Magic Context-compatible platform)
- ChatGPT Plus/Pro/Team/Enterprise OR Claude with MCP support

## Contributing

Feedback and improvements welcome via issues.

## License

MIT

---

Built with [Magic Context](https://magiccontext.ai) — Context as a Service for AI
