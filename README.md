# Zero Human Company — AI Agent Configs

> We run a real company with 11 AI agents and zero full-time human employees. This repo contains the agent configuration files, coordination patterns, and heartbeat system that make it work.

**Status:** 30 days in. $207 revenue. $6,131 spent. Still going.

---

## What is this?

[autoworkhq.com](https://autoworkhq.com) is a company that builds and deploys AI agents for small businesses. It is also, itself, run almost entirely by AI agents.

This repo is the raw config — the `AGENTS.md` files that define each agent's role, decision rules, escalation paths, and communication style. We're open-sourcing it because:

1. The architecture works and others should be able to copy it
2. Transparency is our distribution strategy
3. If competitors copy our configs, they still can't copy 30 days of operational context

---

## The Agent Team

| Agent | Role | What they do |
|-------|------|--------------|
| CEO (Jessica) | Strategic | Sets direction, approves budgets, escalates to board |
| Product Manager (Flora) | Product | Breaks strategy into tasks, coordinates team |
| Engineer (Todd) | Engineering | Frontend, backend, infrastructure |
| Engineer (Nate) | Engineering | Convex backend, data |
| Content Writer | Content | Blog posts, landing copy, email sequences |
| SEO Specialist (Sarah) | SEO/GEO | Technical SEO, keyword strategy, AI search optimization |
| Market Researcher (Jordan) | Research | Competitor analysis, market sizing, distribution research |
| Growth Marketer (Maya) | Growth | Email campaigns, conversion optimization, funnels |
| Designer (Kai) | Design | UI specs, OG images, brand assets |
| Social Media Manager (Sam) | Social | Twitter/X content, community posts |
| QA Engineer | QA | Pre-publish review, content accuracy checks |

---

## How It Works

### The Heartbeat System

Agents don't run continuously. They run in short **heartbeat** windows triggered by Paperclip (our agent coordination platform). Each heartbeat:

1. Wake up, check identity and assignments
2. Pull inbox — prioritize `in_progress` then `todo`
3. Checkout the task (locks it to prevent double-work)
4. Read context (issue description, ancestor chain, comment history)
5. Do the work
6. Update status, post a comment, release the task
7. Exit

This means every agent action is auditable. Every comment is linked to a run ID. Every status change has a timestamp.

### Task Coordination

Tasks flow through a simple hierarchy:

```
Company Goal
  └── Project
        └── Epic / Strategic Issue
              └── Task
                    └── Subtask
```

Agents create subtasks, comment with blockers, reassign when stuck. The CEO escalates to the board (a human) for budget decisions and external communication approvals.

### Communication Rules

- All inter-agent communication happens via issue comments
- @mentions trigger heartbeats (they cost budget — used sparingly)
- External communication (email, social, press) requires board approval
- Agents reference each other by role-tag, not name

---

## The AGENTS.md Files

Each agent directory contains an `AGENTS.md` file — the agent's operating instructions. These define:

- Role and responsibilities
- Decision-making authority
- Escalation triggers
- Communication style
- Tool access

```
agents/
  ceo/
    AGENTS.md                  Role, authority, escalation rules
    HEARTBEAT.md               CEO-specific strategic thinking loop
  product-manager/
    AGENTS.md
  engineer/
    AGENTS.md                  Todd — frontend/infra
    HEARTBEAT.md               Engineering-specific checklist extensions
  nate/
    AGENTS.md                  Nate — Convex backend
  content-writer/
    AGENTS.md
  seo-specialist/
    AGENTS.md
  researcher/
    AGENTS.md
  growth-marketer/
    AGENTS.md
  graphic-designer/
    AGENTS.md
  social-media-manager/
    AGENTS.md
  qa/
    AGENTS.md
LICENSE                        MIT
```

**HEARTBEAT.md** files extend the base `paperclip` skill with role-specific work. For example, the CEO's heartbeat requires strategic thinking every run — generating new product ideas, reviewing team blockers, challenging current priorities. The engineer's heartbeat includes environment setup checks and PR review conventions. Most agents rely entirely on the core skill; only roles with strong per-role discipline need a separate file.

> **Note:** These files have been sanitized. API keys, internal URLs, and company-specific IDs have been removed. The coordination logic and prompt templates are intact.

---

## Month 1 Results

We launched this architecture 30 days ago. Here's what actually happened:

- **Revenue:** $207 (Stripe, confirmed)
- **Spend:** $6,131 (agent compute + tools + infrastructure)
- **ROI:** 3.4%
- **Products shipped:** Starter Kit ($199), Workshop ($149), Guide ($29/$59), Day 30 Bundle ($249)
- **Blog posts published:** 8
- **Twitter threads posted:** 6
- **Issues created and resolved:** 200+

Full Day 30 report: [autoworkhq.com/blog/day-30-report](https://autoworkhq.com/blog/day-30-report)

---

## What We Learned

**What worked:**
- Heartbeat coordination prevents agents from stepping on each other
- Explicit checkout/release prevents duplicate work
- Blocked status + comment requirement surfaces real bottlenecks
- Content agents produce faster and more consistently than we expected

**What didn't:**
- Agents without clear escalation paths get stuck and spin
- Too many board-blocked items created a work queue that stalled momentum
- Engineering velocity was the bottleneck — 9 tasks assigned, slow to execute
- PLG funnel (scorecard, Slack audit) has zero conversions — product exists, distribution doesn't

**What we'd do differently:**
- Define "done" for each agent role before hiring
- Fewer agents, more work per agent
- Build distribution before building product

---

## Replicating This

You can run a similar setup with:

1. **An agent coordination platform** — Paperclip (what we use), or build your own task/comment/checkout system
2. **Claude Code** as the agent runtime (Anthropic's Claude Sonnet 4.6)
3. **AGENTS.md files** like the ones in this repo — one per agent, defining role and behavior
4. **A project tracker** — Paperclip handles this for us; Linear/GitHub Issues would work too

The hardest part isn't the tech. It's writing AGENTS.md files that are specific enough to produce useful work without being so rigid they can't adapt.

---

## License

MIT. Copy, fork, adapt. Attribution appreciated but not required.

---

## Links

- [autoworkhq.com](https://autoworkhq.com) — our main site
- [Day 30 Report](https://autoworkhq.com/blog/day-30-report) — full Month 1 breakdown
- [AI Ops Pilot](https://autoworkhq.com/ai-ops-pilot) — hire us to deploy agents for your business

---

*This README was written by the Content Writer agent. The repo was created by the Engineering agent. The strategy was set by the CEO agent. The board (one human) approved publishing.*
