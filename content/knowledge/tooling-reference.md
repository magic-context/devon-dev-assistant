# Tooling Reference

## Languages & Frameworks

### Frontend
| Tool | Best For | Notes |
|------|----------|-------|
| **React** | Complex SPAs, large ecosystem | Most popular, huge community |
| **Next.js** | Full-stack React, SSR/SSG | Vercel-backed, great DX |
| **Vue** | Progressive adoption, simplicity | Gentle learning curve |
| **Svelte/SvelteKit** | Performance, less boilerplate | Compiles away the framework |
| **Astro** | Content-heavy sites | Ships zero JS by default |
| **HTMX** | Server-rendered with interactivity | Minimal JS, great for simple apps |

### Backend
| Tool | Best For | Notes |
|------|----------|-------|
| **Node.js (Express/Fastify)** | JavaScript full-stack, APIs | Huge ecosystem, fast development |
| **Python (FastAPI/Django)** | Data-heavy, ML integration, rapid prototyping | FastAPI for APIs, Django for full framework |
| **Go** | Performance-critical services, CLIs | Fast compilation, great concurrency |
| **Rust** | Systems programming, maximum performance | Steep learning curve, incredible reliability |
| **Ruby (Rails)** | Rapid prototyping, conventions | "Convention over configuration" |
| **Java/Kotlin (Spring)** | Enterprise, large teams | Type safety, mature ecosystem |

### Databases
| Tool | Type | Best For |
|------|------|----------|
| **PostgreSQL** | Relational | Default choice. JSON support, extensions, reliability |
| **MySQL** | Relational | Simple, widely deployed, good for read-heavy |
| **SQLite** | Embedded relational | Local apps, prototyping, edge computing |
| **MongoDB** | Document | Flexible schemas, rapid prototyping |
| **Redis** | Key-value/Cache | Caching, sessions, queues, pub/sub |
| **DynamoDB** | Key-value/Document | AWS serverless, massive scale |

## Development Tools

### Version Control
- **Git** — non-negotiable. Learn it well.
- **GitHub / GitLab / Bitbucket** — hosting + CI/CD + code review
- **Conventional Commits** — structured commit messages (`feat:`, `fix:`, `chore:`)

### CI/CD
| Tool | Best For |
|------|----------|
| **GitHub Actions** | GitHub-hosted projects, wide marketplace |
| **GitLab CI** | GitLab users, built-in |
| **CircleCI** | Fast builds, good caching |
| **Jenkins** | Self-hosted, maximum flexibility |

### Testing
| Tool | Language | Type |
|------|----------|------|
| **Jest** | JavaScript/TypeScript | Unit + integration |
| **Vitest** | JavaScript/TypeScript | Vite-native, fast |
| **Pytest** | Python | Unit + integration |
| **Playwright** | Any | E2E browser testing |
| **Cypress** | Any | E2E browser testing |

### Code Quality
| Tool | Purpose |
|------|---------|
| **ESLint** | JavaScript/TypeScript linting |
| **Prettier** | Code formatting (JS/TS/CSS/etc.) |
| **Ruff** | Python linting + formatting (fast) |
| **SonarQube** | Multi-language quality analysis |
| **Husky** | Git hooks (pre-commit, pre-push) |

### Infrastructure
| Tool | Purpose |
|------|---------|
| **Docker** | Containerization |
| **Kubernetes** | Container orchestration (complex, use only when needed) |
| **Terraform** | Infrastructure as Code |
| **Vercel / Netlify** | Frontend + serverless deployment |
| **Railway / Render** | Simple backend deployment |
| **AWS / GCP / Azure** | Full cloud platforms |

## Choosing Tools

### Decision Criteria
1. **Team familiarity** — the best tool you know > the "best" tool you don't
2. **Community and ecosystem** — documentation, packages, hiring
3. **Maturity** — how battle-tested is it? Check GitHub activity, adoption
4. **Operational complexity** — every tool is a dependency. Minimize.
5. **Exit cost** — how locked in are you? Can you migrate if needed?

### The Boring Technology Rule
Use proven, well-understood tools for your core infrastructure. Save your "innovation tokens" for the parts that make your product unique.
