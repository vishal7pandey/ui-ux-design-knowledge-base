# AI Agent Integration

This folder — plus the platform-specific files it references — turns this knowledge base from something a human reads into something AI coding agents actually consult while writing UI code.

## Why This Exists

Every major AI coding agent (Claude Code, Cursor, Devin, Google Antigravity, and others) converged independently on the same finding: **generic design instructions don't work.** "Use good spacing" or "follow accessibility best practices" gets ignored the moment the agent hits an edge case its training data didn't cover. What works is:
1. A short, precisely-scoped file the agent loads automatically for relevant tasks
2. Mathematically specific, falsifiable rules (exact px/rem/hex values, not vibes)
3. A pointer to deeper reference material for anything the short file doesn't cover

This repo's `01-design-principles/` through `07-ai-agentic-ux/` folders are the deep reference material. This folder's files are the short, agent-loaded routers into that material.

## Files in This Folder

| File | Purpose |
|---|---|
| [platform-setup-guide.md](./platform-setup-guide.md) | Step-by-step setup for Claude Code, Cursor, Devin, Antigravity, and other agents |
| [DESIGN.md.template](./DESIGN.md.template) | Copy-and-customize template for the cross-agent `DESIGN.md` convention (used by Devin, Windsurf, Copilot, Cline, Aider, Codex) |

## Files Elsewhere in This Repo (Created for Direct Agent Consumption)

| File | Platform |
|---|---|
| `.claude/skills/ui-ux-design/SKILL.md` | Claude Code |
| `.agents/skills/ui-ux-design/SKILL.md` | Google Antigravity |
| `.cursor/rules/ui-ux-design.mdc` | Cursor |

These live outside `08-ai-agent-integration/` because each platform requires its config file at a specific, fixed repo path — they can't be relocated into this folder without breaking auto-discovery.

## Quick Start

- **Using Claude Code or Antigravity?** The relevant `SKILL.md` is already in place — just start a session in this repo.
- **Using Cursor?** The `.mdc` rule is already active for `.tsx/.jsx/.vue/.svelte/.css/.scss/.html` files in this repo.
- **Using Devin, Windsurf, Copilot, Cline, Aider, or Codex on a different product repo?** Copy `DESIGN.md.template` there, fill in your real tokens, and follow the platform-specific pointer instructions in [platform-setup-guide.md](./platform-setup-guide.md).
- **Bringing this knowledge base into a different project entirely?** Copy the relevant platform file(s) above into that project — see the copy commands in [platform-setup-guide.md](./platform-setup-guide.md).
