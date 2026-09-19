# Claude Code Skills

Custom Skills for Claude Code (`~/.claude/commands/`) built for real support and operations workflows.

## Install

Copy any `.md` file from this repo into `~/.claude/commands/`:

```bash
cp wp-support-brief.md ~/.claude/commands/
cp mercor-interview-support.md ~/.claude/commands/
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

## Built with

All skills written and iterated using Claude Code.
