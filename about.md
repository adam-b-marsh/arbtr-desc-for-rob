# Arbtr — System of Record for Architectural Decisions

**"Architecture as Code"** for CTOs, Staff Engineers, and Architecture Teams

---

## Overview

Arbtr is the **System of Record for Decisions**. It is NOT a wiki, a voting tool, or a project management app — it is **Architecture as Code**.

- **Core Value**: Visualize strategic debt, prevent architectural drift, and act as a "Strategic Linter" for technical leadership
- **Primary Users**: Fractional CTOs, Staff Engineers, Principal Engineers, Platform Teams
- **Design Philosophy**: High-rigor, developer-centric, graph-first navigation

---

## Decision Management

### Full Lifecycle Tracking

- **8 decision statuses**: Stub → Proposed → Active → Under Discussion → Approved/Rejected/Deferred → Archived
- Automatic status promotion when engagement begins (first argument, vote, or relationship)
- Soft deletion with archive and recovery
- Human-readable URL slugs for sharing

### Structured Decision Framework

- **Multiple positions/options** per decision (not limited to binary yes/no)
- Rich context field for problem statement and background
- Importance levels: **Anchor** (foundational), **Important**, **Standard**, **Tentative**
- Confidence scoring (0-100%) with traffic light indicators
- Custom tags and domain assignment for organization

### Decision Delegation & Ratification

- Assign delegates to conclude decisions (solves the "vacation problem")
- Optional ratification workflow requiring CTO/approver sign-off
- Veto capability with explanation (reverts to Active status)

---

## Decision Graph

### Visual Network of Decisions

- **Interactive graph visualization** — the primary navigation interface, not just a visualization afterthought
- Nodes scale by importance and dependency count
- Visual indicators: status badges, importance ribbons, confidence %, age tinting
- Zoom, pan, drag-to-reposition with layout persistence

### 6 Relationship Types

| Relationship                    | Description                    |
| ------------------------------- | ------------------------------ |
| **depends_on / required_by**    | One decision relies on another |
| **supersedes / superseded_by**  | One decision replaces another  |
| **conflicts_with**              | Decisions in tension           |
| **enables / enabled_by**        | One makes another possible     |
| **constrains / constrained_by** | One limits another             |
| **derived_from / derived_to**   | One inspired by another        |

### Graph Linting & Validation

- Automatic conflict detection
- 9 linting error types: circular dependencies, time travel paradoxes, deprecated dependencies, hypothetical conflicts
- Severity levels with taskbar indicators

---

## Strategic Branches (Scenarios)

**"Terraform Plan for Architecture"** — explore hypothetical decision chains in a sandbox before committing.

### Core Capabilities

- Create **isolated branches** to model "what-if" scenarios without affecting live decisions
- Add proposed decisions as **ghost nodes** (visually distinct with dashed borders and branch badges)
- Draw relationships between branch decisions and existing live decisions
- Compare multiple strategic directions side-by-side before choosing one

### Key Features

- **Hypothetical conflict detection** — warns when a branch would create conflicts with your live graph _before_ you merge
- **Graph diff view** — git-style visual comparison showing added decisions (green), superseded decisions (amber), and new relationships (blue)
- **Merge flow** — preview all changes, then commit the branch to your live graph
- **Supersession support** — branch decisions can explicitly replace existing decisions with full audit trail
- **Decision provenance** — "git blame" for architecture; track which branch introduced each decision

### Use Cases

- Model a major technology migration before committing
- Compare two competing architectural approaches (branch vs branch "shootout")
- Onboard a new team member by having them propose changes in a branch for review
- Plan Q2 architecture changes while Q1 decisions remain stable

---

## Briefings

**Multi-Decision Intelligence Reports** — synthesize multiple related decisions into cohesive, purpose-built documents.

### 5 Briefing Types

| Type                  | Audience      | Content Focus                                     |
| --------------------- | ------------- | ------------------------------------------------- |
| **Executive Summary** | Leadership    | High-level outcomes, business impact, risks       |
| **Technical Digest**  | Engineering   | Implementation details, dependencies, constraints |
| **Onboarding Guide**  | New hires     | Context, history, "why we do it this way"         |
| **Policy Document**   | Governance    | Formal rules, compliance requirements             |
| **ADR Export**        | Documentation | Architecture Decision Record format for Git       |

### Key Features

- **Staleness warnings** — alerts when source decisions have changed since briefing was generated
- **Regeneration** — one-click refresh when underlying decisions update
- **Shareable URLs** — distribute to stakeholders who don't need full Arbtr access
- **Markdown export** — drop into wikis, Notion, Confluence, or Git repos
- **Edit after generation** — AI provides the draft, you refine the final version

### Use Cases

- Prepare board-level architecture updates without manual summarization
- Generate onboarding docs for new engineers joining a complex system
- Create compliance documentation from security-related decisions
- Export quarterly architecture summaries to stakeholders

---

## Project Memory

**Persistent AI Memory Layer** — capture architectural choices as they happen and surface emerging patterns across your codebase.

### How It Works

```
Developer uses AI assistant →
  Assistant logs choice ("using React Query for server state") →
    Pattern detected across projects →
      Pattern promoted to team standard →
        Future AI sessions enforce standard
```

### Key Capabilities

**Choice Logging**

- Fire-and-forget logging from AI assistants via MCP
- Categories: dependencies, patterns, conventions, structure, tools, architecture
- Evidence linking (file paths, commits, PRs)
- Confidence scoring

**Pattern Detection**

- Automatic pattern emergence across 2+ projects
- Confidence aggregation from multiple observations
- Category-based grouping

**Standards Enforcement**

- **Suggest** — AI mentions the standard but doesn't block
- **Warn** — AI flags deviation but allows override
- **Block** — AI refuses to generate non-compliant code
- Alignment checking via `check_standards` MCP tool

**Repository Analysis**

- Scan connected Git repos for existing undocumented decisions
- Stack detection (frameworks, languages, tools)
- **Swipe review UI** — Tinder-style accept/reject/skip for discovered patterns
- Auto-create draft decisions from discovered patterns
- _"Document years of decisions in minutes"_

### Use Cases

- Ensure all AI-assisted coding follows your established patterns
- Onboard new repos by scanning for existing architectural decisions
- Detect when teams are diverging on conventions before it becomes technical debt
- Build institutional knowledge that persists beyond individual developers

---

## Collaboration & Argumentation

### Structured Debate

- Pro/con arguments with evidence support
- **Rebuttal threads** (recursive argumentation)
- Argument linking: support and reinforce relationships
- Evidence substantiation levels: Opinion, Reasoned, Data-backed
- Consensus detection: Unchallenged, Contested, Blocker, Resolved

### Voting System

- Multi-position voting (not binary)
- Open or restricted voting modes
- Anonymous voting option
- Deadline management with reminders
- Permission-based voting (restrict by group)

### Comments & Discussions

- Threaded comments with replies
- **8 comment types**: Question, Context, Idea, Risk, Data-request, Clarification, Gap-response, Best-practice-response
- Promotion-to-argument workflow (comments can become formal arguments)

### Evidence Library

- File uploads with processing and extraction
- URL attachments with smart provider detection (GitHub, Linear, Jira, Notion, Confluence, Slack, Figma)
- Tag system with custom colors
- Search and filtering

---

## AI Features

### Magic Paste

- **Extract structured decisions from unstructured text** (Slack threads, emails, meeting notes)
- AI identifies positions, arguments, and attributions
- Ghost profiles for unverified authors
- Batch assignment of extracted arguments
- Source content stored for audit trail

### Oracle (RAG Chatbot)

- Natural language Q&A about your decision history
- Vector embeddings for semantic search
- Conversation persistence with follow-up understanding
- AI response citations
- Requires 5+ decisions to activate

### Spark (Conversational Scaffolding)

- Guided dialogue to build new decisions
- AI suggests relationships and domains during creation
- Reduces blank-page syndrome

### Arbiter Insights (Background Analysis)

- Real-time AI analysis running in background
- Detects conflicts between decisions
- Identifies similar/duplicate decisions
- Finds duplicate arguments
- **Promotion suggestions** (comments that should be arguments)
- One-click actions to accept insights
- Ripple effect detection (status changes → dependent decisions)

### Comprehensive Summaries

- Auto-generated when decisions conclude
- Executive summary with background
- Options considered with pros/cons
- Implementation details: timeline, responsibilities, success metrics
- Risks and mitigation strategies
- Lessons learned

---

## Git Integration & PR Enforcement

### Multi-Provider Support

- **GitHub**, **GitLab**, **Bitbucket** integration
- GitHub App integration
- GitLab OAuth (supports self-hosted)
- Provider-aware UI (MR/PR terminology)

### ADR Publishing

- MADR-style Markdown output with frontmatter
- **One-way sync**: Arbtr is the editor, Git is the archive
- Sync status tracking: Pending, Synced, Out of Sync, Error
- Auto-sync on decision conclude (configurable)

### PR Policy Enforcement (Strategic Linter)

- **AI rule inference** from decision content
- Automatically detects enforceable patterns:
  - Blocked dependencies
  - Blocked file patterns
  - Required patterns/files
- **Enforcement levels**: Off, Warn, Block
- GitHub Check Runs / GitLab MR / Bitbucket PR integration
- Compliance dashboard with check history
- Violation reporting with decision links
- Rego policy generation for OPA-compatible systems

---

## MCP Server Integration

### Model Context Protocol

- Direct integration with **Claude Code, Cursor, Windsurf, and other AI assistants**
- Decisions available as context during coding sessions

### MCP Tools

| Tool                  | Description                              |
| --------------------- | ---------------------------------------- |
| `search_decisions`    | Semantic search with filters             |
| `get_decision`        | Full structured decision data            |
| `get_project_context` | Team standards and patterns              |
| `log_choice`          | Fire-and-forget developer choice logging |
| `check_standards`     | Alignment checking before changes        |

### Team API Keys

- Generate MCP API keys per team
- Secure key management

---

## Governance & Compliance

### Complete Audit History

- **29+ audit event types** tracked automatically
- Decision lifecycle events (created, status changed, edited, archived)
- Delegation and ratification events
- Arguments, voting, and relationship changes
- MCP access logging
- Full diffs for large text changes
- Configurable retention by tier (30/90/365 days)

### Architectural Domains

- Group decisions by system area
- Custom color coding
- Collapsible domain containers
- Bulk domain assignment

---

## Team & Permissions

### Multi-Tenant Architecture

- Human-readable team slugs
- Team branding and settings
- Users can belong to multiple teams

### Role-Based Access Control

| Role       | Capabilities                                   |
| ---------- | ---------------------------------------------- |
| **Owner**  | Full control including billing and AI settings |
| **Admin**  | Team management, invites, groups               |
| **Member** | Participation (create, vote, comment)          |

### Groups & Visibility

- Create groups for departments, projects, teams
- Restrict decision visibility by group or individual
- OR logic for access control

---

## Dashboard & Metrics

### Pulse Dashboard

- System health grade (A/B/C/F)
- Critical conflicts display
- Stale watch (30+ day untouched decisions)
- Inbox of actionable items
- Activity feed integration

### Decision Metrics

- Confidence tracking per decision
- Consensus scoring
- Age tracking with visual tinting (green <3mo, amber 3-12mo, red >12mo)
- Dependency and conflict counts

---

## Search & Discovery

### Command Palette

- VS Code-style search (Cmd/Ctrl+K)
- Search by title, status, owner, importance, tags, domain
- Graph filtering as you type
- Keyboard navigation

### Advanced Filtering

- Full-text and semantic search
- Filter chips with one-click dismiss
- Unified filtering between List and Graph views

---

## Subscription Tiers

| Feature            | Free    | Team      | Organization | Enterprise |
| ------------------ | ------- | --------- | ------------ | ---------- |
| Repositories       | 1       | 3         | Unlimited    | Unlimited  |
| Decisions          | 50      | Unlimited | Unlimited    | Unlimited  |
| AI Features        | ✓       | ✓         | ✓            | ✓          |
| Briefings          | ✓       | ✓         | ✓            | ✓          |
| MCP Integration    | ✓       | ✓         | ✓            | ✓          |
| Strategic Branches | —       | ✓         | ✓            | ✓          |
| PR Enforcement     | —       | ✓         | ✓            | ✓          |
| Audit Retention    | 30 days | 90 days   | 365 days     | Custom     |

---

## Key Differentiators

1. **Graph-First Navigation** — The decision network is the primary interface, not a visualization afterthought
2. **Relationships > Voting** — 6 relationship types capture how decisions interact; the graph structure IS the decision mechanism
3. **Strategic Branches** — "Terraform plan for strategy" — model hypothetical futures before committing
4. **Project Memory** — Persistent AI memory layer that learns your team's patterns across sessions
5. **PR Enforcement** — Turn architectural decisions into automated code review checks
6. **No Argument Scores** — We check for completeness, not quality; prevents toxic culture
7. **Magic Paste** — Extract decisions from Slack/email/meetings in seconds
8. **One-Way Git Sync** — Simple mental model: Arbtr is editor, Git is archive
9. **MCP Integration** — Native integration with AI coding assistants (emerging standard)
10. **Repo Analysis Onboarding** — Document years of undocumented decisions in minutes

---

## By the Numbers

- **305+ API functions** across 32 modules
- **267 UI components**
- **119 changelog entries** (continuous delivery since v0.1.0)
- **29+ audit event types** for governance
- **1,119+ tests** maintaining quality
- **6 relationship types** for decision connections
- **8 decision statuses** for lifecycle tracking

---

## Summary

| Feature                | Problem It Solves                                                            |
| ---------------------- | ---------------------------------------------------------------------------- |
| **Decision Graph**     | "We don't know how our decisions connect or conflict"                        |
| **Strategic Branches** | "We can't experiment with architecture without risk"                         |
| **Briefings**          | "Leadership needs summaries but I don't have time to write them"             |
| **Project Memory**     | "Our AI tools don't know our conventions and keep suggesting wrong patterns" |
| **PR Enforcement**     | "Decisions get made but never enforced in code"                              |
| **Magic Paste**        | "Decisions are scattered across Slack, email, and meetings"                  |
| **Audit History**      | "We don't know who decided what or when"                                     |

**Arbtr is not a documentation tool — it's an active governance system that participates in your development workflow.**
