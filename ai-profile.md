---
description: Load Ahmad's full AI fluency profile — projects, tools, Skills, MCP work, and vibe coding track record. Invoke before writing any CV, cover letter, or application answer for an AI-related role.
---

You are helping Ahmad Baig apply for AI-related roles. Below is his complete AI fluency profile. Use this as the authoritative source whenever you need to describe his AI projects, tools, or experience. Do not fabricate details beyond what is listed here.

When invoked with no arguments, output a clean structured summary of the profile below.
When invoked with a specific question or role context (e.g. `/ai-profile What have I built with Claude Code?`), answer that question using only the data below.

---

## AI TOOLS & FLUENCY

- **Claude** — 1–2 years daily use across chat, Projects, Skills, MCP, Claude Code, and agents
- **Claude Code** — primary execution tool for all projects; used for architecture decisions, code generation, debugging, and PR submission
- **ChatGPT** — regular supplementary use
- **Grok API (xAI)** — used in production RAG pipeline
- **Vibe coding** — primary method of shipping; writes minimal code by hand; describes intent and iterates with Claude Code

---

## SHIPPED PROJECTS

### 1. Damha — Autonomous AI Customer Support Agent
- **Repo:** github.com/ahmadbaig1/damha-ai
- **Stack:** Next.js, TypeScript, Vercel, Claude Code
- **What it is:** A full AI support product — not a chatbot widget. An autonomous agent that handles the complete support lifecycle: reads tickets, triages by priority and sentiment, resolves common issues against a knowledge base, escalates complex cases to humans with full context attached.
- **Built via:** Claude Code entirely — positioning, page architecture, copy, animated canvas hero (10-layer wave system using sine functions with independent amplitude/frequency/speed), live inline feature mockups, RLHF metrics panel, testimonials, CTA, Footer. Shipped to Vercel.
- **Product reflects:** 7.5 years of first-hand support experience at Automattic distilled into a product vision.
- **Key metrics baked in:** 94% resolution accuracy, 92% CSAT, 87% FCR, 8% escalation rate

### 2. HubSpot AI Lead Capture & CRM Pipeline
- **Repo:** github.com/ahmadbaig1/evotix-ai-agent (private — client project)
- **Stack:** Python, FastAPI, ChromaDB, Grok API, HubSpot Conversations API, HubSpot CRM API
- **What it is:** A full RAG pipeline end to end. Visitor messages a HubSpot chat widget → FastAPI webhook server intercepts → semantic search against ChromaDB retrieves top-5 relevant knowledge chunks → Grok generates a consultative reply → answer posted back to HubSpot conversation → contact created/updated in CRM with lead status, deal record, and full Q&A note. Fully automated.
- **Built via:** Claude Code — architecture decisions, HubSpot webhook signature verification debugging, ChromaDB collection structure design.
- **Infrastructure:** Configured HubSpot Private App, chatflow, and webhook subscriptions from scratch. Wrote full documentation for independent operation.
- **Pipeline:** web scraper → ChromaDB vector index builder → RAG retriever → Grok LLM → HubSpot Conversations API → HubSpot CRM API

### 3. Toom — macOS Screen Recorder (Free Loom Alternative)
- **Repo:** github.com/ahmadbaig1/toom
- **Stack:** Electron 28, MediaRecorder API, Canvas API, Google Drive API v3, OAuth 2.0
- **What it is:** A macOS desktop app that replaces Loom. Records full screen, individual windows, or custom drag-selected areas. Webcam overlay, microphone, and system audio via BlackHole 2ch. 3-2-1 countdown, pause/resume, floating always-on-top control bar. Auto-uploads to Google Drive via OAuth 2.0 on completion; shareable link auto-copied to clipboard with macOS system notification. All recordings saved locally to ~/Movies/Toom/ as .webm files.
- **Built via:** Claude Code — IPC architecture between Electron main process and renderer windows, macOS screen capture permissions flow.
- **Keyboard shortcuts:** Stop, Pause/Resume, Discard, Confirm Area (Enter), Cancel (Esc)

### 4. Royal Retreat — Luxury Real Estate Website
- **Repo:** github.com/ahmadbaig1/royal-retreat
- **Stack:** Next.js 14, TypeScript, CSS, Vercel
- **What it is:** A luxury real estate website for KSMB Group — dark theme, Apple-style scroll-triggered animations, fully responsive. GitHub → Vercel deployment pipeline set up in under an hour; every push to main auto-deploys with a preview URL per branch.
- **Built via:** Claude Code — full design and build from scratch, no template.

---

## CLAUDE CODE SKILLS (AUTHORED)

**Repo:** github.com/ahmadbaig1/claude-code-skills

### /wp-support-brief
- Converts a raw WordPress support ticket into an engineering-ready bug report
- 13-way issue classification: REST_API_AUTH, PLUGIN_CONFLICT, THEME_BUG, DB_CORRUPTION, JETPACK_FAILURE, WOOCOMMERCE, EDITOR_BLOCK, ACCOUNT_ACCESS, BILLING_SUBSCRIPTION, PERFORMANCE, MULTISITE, SECURITY_ATO, OTHER
- Outputs: severity rating, affected component (wp-calypso / jetpack / themes / woocommerce-blocks / atomic-platform / etc.), numbered repro steps, expected vs. actual behaviour, investigation notes, missing information checklist
- Built from 7.5 years of filing real engineering escalations at Automattic

### /mercor-interview-support
- Structured AI support agent for Mercor's AI interview platform
- 8-way issue classification: CAMERA_MIC, BOT_FREEZE, AUTO_SUBMIT, START_BLOCKED, BOT_INTERRUPTION, RETAKE_REQUEST, BROWSER_COMPAT, POLICY_QUESTION
- Conditional branching: behaves differently when INTERVIEW_DATA_AVAILABLE = true vs. false
- Escalation logic: flags cases where retakes are exhausted or engineering review is needed
- Output: structured JSON with reply, internal_note, escalate (true/false)
- Uses {{placeholder}} template injection from orchestration layer

---

## MCP SERVER (DESIGNED & USED INTERNALLY)

### WordPress Support Investigation MCP
- Connected Claude Code to internal Automattic tooling
- **Tools exposed:**
  - `lookup_account(email)` — hits internal REST API, returns subscription tier, plan state, site count, last payment event
  - `run_safe_query(sql)` — read-only MySQL runner scoped to non-PII columns
  - `check_known_bugs(symptom)` — semantic search against local ChromaDB index of GitHub issue history
  - `create_bug_report(context)` — pre-populated GitHub issue with repro steps, account context, affected component
  - `get_ticket_history(account_id)` — pulls last 10 Zendesk tickets for an account
- **Impact:** Collapsed 15–20 minute multi-tab investigations into a single Claude Code session
- Connected via ~/.claude/claude_desktop_config.json (internal tooling — not public)

---

## PRODUCTION CODE CONTRIBUTIONS VIA CLAUDE CODE

- **PR #222110** — WordPress.com codebase (wp-calypso), June 2026, reviewed and cleared for commit
- **PR #222293** — WordPress.com codebase (wp-calypso), June 2026, reviewed and cleared for commit
- Codebase: live production repo serving 100M+ sites
- Method: scoped, written, and submitted entirely via Claude Code

---

## CLAUDE INFRASTRUCTURE SETUP

- **Skills:** 2 authored and public (github.com/ahmadbaig1/claude-code-skills)
- **Commands dir:** ~/.claude/commands/
- **Plugins enabled:** Automattic internal plugins (dotcom-bug-blitz, gutenberg, systems-review, sdd, github-enterprise), career-ops local marketplace, Vercel plugin
- **Local plugin marketplace:** ~/.claude/local-marketplaces/career-ops — custom career ops plugin with commands, batch-scanner sub-agent, scoring rubric, ATS rules, profile schema
- **Hooks:** None currently configured
- **CLAUDE.md:** Project-level context files in all active working directories

---

## AI SPACE AWARENESS

- Follows model releases, tooling shifts, and agent best practices daily
- Used Claude across: chat, Projects, Skills, MCP, Claude Code, agents
- RAG experience: ChromaDB, vector embeddings, semantic retrieval, chunk sizing, collection design
- LLMs used in production: Claude (Anthropic), Grok (xAI)
- Infra: Vercel, GitHub, Electron, FastAPI, Python, OAuth 2.0, Google APIs
- Orchestration tools: Zapier (production), n8n (familiar), MCP servers

---

## SUMMARY STATS FOR APPLICATIONS

- Claude experience: 1–2 years daily
- Products shipped via vibe coding: 4 (Damha, HubSpot RAG, Toom, Royal Retreat)
- Claude Code Skills authored: 2 (public on GitHub)
- Production PRs via Claude Code: 2 (WordPress.com, June 2026)
- MCP servers designed: 1 (WordPress Support Investigation — internal)
- Public GitHub: github.com/ahmadbaig1
