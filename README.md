# Claude Code Skills

Custom Skills for Claude Code (`~/.claude/commands/`) built for real support and operations workflows.

## Install

Copy any `.md` file from this repo into `~/.claude/commands/`:

```bash
cp wp-support-brief.md ~/.claude/commands/
cp mercor-interview-support.md ~/.claude/commands/
cp ai-profile.md ~/.claude/commands/
```

Then invoke in Claude Code with `/skill-name [args]`.

---

## Skills

### `/wp-support-brief`

**Convert a messy WordPress support ticket into an engineering-ready bug report.**

Paste any raw customer ticket and get back a fully structured brief: issue classification across 13 categories, severity rating, affected component mapped to the correct codebase (wp-calypso, Jetpack, Atomic, WooCommerce, etc.), numbered repro steps, expected vs. actual behaviour, investigation notes, and a Missing Information checklist for anything that needs to be gathered before engineering can act.

Built from 7.5 years of filing bug reports at Automattic (WordPress.com). Designed to eliminate the back-and-forth between support and engineering.

```
/wp-support-brief My site is down showing a critical error occurred
```

---

### `/mercor-interview-support`

**Structured AI support agent for Mercor's AI interview platform.**

Handles inbound support tickets from candidates experiencing issues with Mercor's AI interview system. Classifies issues across 8 categories (camera/mic failure, bot freeze, accidental auto-submit, start button blocked, bot interruption, retake request, browser incompatibility, policy question), branches on live platform data availability, resolves autonomously where possible, escalates with a flag when retakes are exhausted or the issue requires engineering review. Outputs structured JSON: `reply`, `internal_note`, `escalate: true/false`.

Uses `{{placeholder}}` fields injected by an orchestration layer before invocation.

```
/mercor-interview-support [inject platform data]
```

---

### `/ai-profile`

**Load Ahmad's full AI fluency profile for use in job applications.**

Surfaces all AI projects, tools, Skills, MCP work, production PRs, and vibe coding track record in a structured format. Invoke before writing any CV, cover letter, or application answer for an AI-related role so Claude has authoritative context without needing to re-derive it from conversation.

Covers: Damha AI, HubSpot RAG pipeline, Toom, Royal Retreat, Claude Code Skills authored, WordPress Support Investigation MCP, production PRs on WordPress.com, Claude infrastructure setup, and summary stats.

```
/ai-profile
/ai-profile What have I built with Claude Code?
/ai-profile Skills and MCP experience
```

---

## Built with

All skills written and iterated using Claude Code.
