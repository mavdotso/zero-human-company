# Show HN — Draft Variations

Three title options with different angles. Post body follows.

---

## Title Option A — The honest numbers angle
**"Show HN: We open-sourced the configs for our 11-agent AI company ($207 revenue, 30 days in)"**

*Why this works:* Real numbers + transparency disarms skepticism. The low revenue is honest and signals we're not a pitch deck.

---

## Title Option B — The architecture angle
**"Show HN: AGENTS.md files for an 11-agent AI company that runs itself via heartbeat coordination"**

*Why this works:* Technical audience cares about the mechanism. "Heartbeat coordination" is novel jargon that makes people click to understand.

---

## Title Option C — The provocation angle
**"Show HN: We replaced a 10-person startup with AI agents — here are their full config files"**

*Why this works:* Slightly provocative framing invites engagement. "Full config files" delivers a concrete artifact.

*Note: May be seen as overselling. Option A or B preferred for HN culture.*

---

## Post Body

Use one of the titles above. The body is the same for all three:

---

autoworkhq.com is a company that builds AI agent workflows for small businesses. It is also, itself, run almost entirely by AI agents.

We have 11 agents: CEO, PM, two engineers, content writer, SEO specialist, market researcher, growth marketer, designer, social media manager, and QA engineer. Each agent runs on Claude Sonnet 4.6 via Claude Code, coordinated through a platform called Paperclip that handles task assignment, checkout locks, and run audit trails.

The coordination pattern is called a "heartbeat" — agents don't run continuously. Each heartbeat:

1. Pull inbox, prioritize in_progress then todo
2. Checkout the task (prevents double-work)
3. Do the work using tools (file edits, API calls, web search)
4. Post a comment, update status, release the task
5. Exit

Every action is linked to a run ID. Every status change is auditable.

After 30 days: $207 revenue, $6,131 spent. 3.4% ROI. Painful, but we shipped 4 products, 8 blog posts, and ~200 resolved issues.

This repo contains the sanitized AGENTS.md files that define each agent's role, decision authority, escalation triggers, and communication rules. We stripped API keys and internal URLs; the coordination logic is intact.

We're open-sourcing it because:
- The architecture actually works and others should be able to copy it
- Transparency is our distribution strategy (we have no marketing budget)
- Full Day 30 report is at autoworkhq.com/blog/day-30-report

Repo: [LINK — add after Todd creates the GitHub repo]

Happy to answer questions about the heartbeat system, what broke, what we'd do differently, or how to run a similar setup.

---

## HN Formatting Notes

- No markdown in the post body (HN strips it)
- Keep under 300 words — this draft is ~280
- Post on a Tuesday or Wednesday, 9-11am ET for best visibility
- Don't post the same day as a major AI news cycle
- First comment should add 1-2 things not in the post (e.g., a specific failure story or unexpected finding)

## Suggested First Comment (from founder/CEO account)

> The most surprising thing: agents get stuck in the same ways humans do. They'll mark a task "blocked" and wait indefinitely if the blocker description is vague. Writing good blocker comments — specific about who needs to act and what they need to decide — turned out to be as important as writing the AGENTS.md files themselves.
