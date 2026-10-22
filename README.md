# Conor Cruise

**Full-stack AI engineer · AI agents, MCP and AI-directed development · Dublin, Ireland**

I build production software by directing AI coding agents (Claude Code): I set the direction and the constraints, the agent implements, and I review what comes back against what I meant. I'm strongest where AI systems fail quietly — finding why, fixing it, and adding a check so it can't come back.

> *"The difference between the models isn't significant; what surrounds the models is."* — the rule I build on. My work is the harness around the model: memory, checks, routing, and a record of every decision.

---

## FlowMerge — my main project (private development)

An AI build platform for interfaces, apps, games (including 3D) and back-end integrations. A user's own Claude Code or Codex connects and builds alongside FlowMerge's models; every design decision is recorded with where it came from, and the result is checked against it. Built solo since 2024; rebuilt as the full platform in 2026.

**Architecture I designed**
- **Every decision has a named source** — stated by the prompt, cited by name from the user's own earlier project, carried from the project's record, or resolved by the user in the open — and builds are checked against them.
- **Three roles** — a planning layer that owns the conversation, memory and judgement, and is the only channel between a front-end and a back-end builder that never share a context.
- **Main over flash** — a strong model writes and watches the plan, a fast model performs it.
- **The user's agent as lead** — their own coding agent directs FlowMerge, which adds memory, readers and checks, each returned as a typed result.

**Built by directing Claude Code**
- An MCP server (21 tools) with OAuth 2.1 + PKCE one-click pairing; keys scoped to one task or one project, with credit ceilings
- Long-running coding agents in sandboxes (Vercel Sandbox, Upstash Box) with checkpoints, budgets and a stall guard
- Durable workflow pipeline with replay-safe writes; six model seats routed by measured speed and price
- Verification by measurement: compiler checks, a runtime referee for 3D scenes and games, a paint read of the rendered page, conformance against agreed decisions
- An append-only, hash-chained ledger; a change map that reads the repository at any commit
- Postgres (Neon) + pgvector, migrated from Turso behind a single seam

**A few things I diagnosed and decided**
- **Cost:** asked why a paid agent run kept re-reading its own context when the platform already had memory to hold it; redesigned the build stage as the unit to compress and recall — cost per step fell 2.7×, with no loss of quality allowed.
- **Leaks:** set the rule that the product shows people their work but never how it works; the audit found 29 leaks with one root cause, now one allow-list, plus a check on the shipped browser bundles.
- **Drift:** had 203 of my own proposals checked word for word against the code — 69 faithful, 48 narrowed, 71 not yet built — and used the list to set the work order.

The code is private while FlowMerge is in development. **A walkthrough or a demo account is available on request.**

---

## Earlier products

| Project | What it shows | Live |
|---|---|---|
| **CryptoIntel** | A self-updating news pipeline: aggregation from 130+ sources, AI sentiment analysis and live market context, on a front end that refreshes itself | [cryptointel.site](https://cryptointel.site) |
| **AetherNode** | A trading-platform front end with real-time market data, charting and indicators | [live demo](https://v0-searchable-analytics-menu.vercel.app) |
| **CryptoPulse** | Live Polymarket prediction-market data turned into AI-analysed trading signals | [thecryptopulse.xyz](https://thecryptopulse.xyz) |

Two of these drew a $2,000 purchase offer.

---

## Stack

TypeScript · React · Next.js · Node · Tailwind · Postgres (Neon) · pgvector · Redis · Vercel (Workflow, Sandbox, Blob) · MCP · OAuth 2.1 · Three.js / React Three Fiber · Playwright · Docker

## Contact

[LinkedIn](https://www.linkedin.com/in/conor-cruise-50b9b02b9/) · conor.cruise848@gmail.com · open to product, agent and forward-deployed engineering roles — remote or in Dublin, full-time or contract
