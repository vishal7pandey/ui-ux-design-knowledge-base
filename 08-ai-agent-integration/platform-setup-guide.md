# Setting Up This Knowledge Base for AI Coding Agents

This repo now ships ready-to-use files so AI coding agents actually consult it, instead of falling back on generic training-data defaults (purple gradients, Inter font, cookie-cutter layouts). This guide explains what's included and how to wire it into each platform.

## What's Already in This Repo

| File | Platform | Format |
|---|---|---|
| `.claude/skills/ui-ux-design/SKILL.md` | Claude Code | Agent Skills open standard |
| `.agents/skills/ui-ux-design/SKILL.md` | Google Antigravity | Agent Skills open standard (same format, different directory convention) |
| `.cursor/rules/ui-ux-design.mdc` | Cursor | MDC rules with glob scoping |
| `08-ai-agent-integration/DESIGN.md.template` | Devin, Windsurf, Copilot, Cline, Aider, Codex | DESIGN.md cross-agent convention |

All four formats point back into this repo's folder structure (`01-design-principles/` → `07-ai-agentic-ux/`) as the deep reference material — the platform-specific files are lean routers, not duplicated content, following the **progressive disclosure** principle every platform's own docs recommend (keep the always-loaded file short; load deep detail on demand).

---

## Claude Code

Skills live at `.claude/skills/<name>/SKILL.md` (project-scoped) or `~/.claude/skills/<name>/SKILL.md` (personal, all projects).

**Already done in this repo:** `.claude/skills/ui-ux-design/SKILL.md` exists and will be picked up automatically the next time you run `claude` inside this repo or a project that includes it.

**To use in another project:**
```bash
cp -r ui-ux-design/.claude/skills/ui-ux-design /path/to/your-project/.claude/skills/
```
Claude loads it automatically when your prompt semantically matches the skill's `description` field, or you can force it with `/ui-ux-design`.

**Key detail from Anthropic's own docs:** the `description` field is the *only* thing indexed for automatic discovery — write it in third person with concrete trigger keywords. Ours already covers "building," "reviewing," "redesigning," "accessibility," "design system," and "agentic."

---

## Google Antigravity

Skills live at `.agents/skills/<name>/SKILL.md` (workspace-scoped) or `~/.gemini/config/skills/<name>/SKILL.md` (global, all workspaces/products). Same open standard as Claude Code — this is why both SKILL.md files in this repo are near-identical.

**Already done:** `.agents/skills/ui-ux-design/SKILL.md` exists in this repo.

**To use globally across all your Antigravity projects:**
```bash
mkdir -p ~/.gemini/config/skills
cp -r ui-ux-design/.agents/skills/ui-ux-design ~/.gemini/config/skills/
```

**Note:** Antigravity also supports "Rules" (always-on behavioral guidance) and "Workflows" (on-demand `/slash-command` procedures) as separate customization mechanisms — see `Customizations` in the IDE. Skills are the right mechanism for this knowledge base since it should load conditionally (on UI/design tasks), not on every single prompt.

---

## Cursor

Rules live at `.cursor/rules/*.mdc` — each file has YAML frontmatter with `globs` to scope which files it applies to. Cursor deprecated the old single `.cursorrules` file in favor of this directory approach.

**Already done:** `.cursor/rules/ui-ux-design.mdc` exists, scoped to `.tsx`, `.jsx`, `.vue`, `.svelte`, `.css`, `.scss`, `.html`.

**To use in another project:**
```bash
mkdir -p /path/to/your-project/.cursor/rules
cp ui-ux-design/.cursor/rules/ui-ux-design.mdc /path/to/your-project/.cursor/rules/
```

**Critical lesson from production `.cursorrules` failures:** vague guidance like "follow good design practices" is not enforceable — Cursor has no way to check compliance and will drift back to training-data defaults on any edge case. Our `.mdc` file uses **falsifiable, numeric rules** (exact px/rem scales, exact contrast ratios) precisely because that's the only style of rule Cursor reliably holds to. If your project has its own token system, add it to a second `.mdc` file with higher specificity (e.g., `design-tokens.mdc` scoped to the same globs) — project-specific values should always win over these generic fallback defaults.

---

## Devin

Devin doesn't read arbitrary repo files automatically — it uses a **Knowledge Base** (org/repo-scoped instructions configured in the dashboard) that you point at files in your repo.

**Setup:**
1. Copy `08-ai-agent-integration/DESIGN.md.template` to your product repo's root as `DESIGN.md`, and fill in your actual token values in the YAML frontmatter.
2. In the Devin dashboard: **Settings → Knowledge**, add an entry:
   > "When cloning any repo, check if `DESIGN.md` exists at the root. If it exists, read it COMPLETELY before generating any UI component. Extract tokens for colors, typography, spacing, and border-radius. Apply them in all generated code. Check the 'Constraints' section and do not violate any of it."
3. Optionally add a line to your repo's `README.md`:
   > "**For AI agents:** read [`DESIGN.md`](./DESIGN.md) before generating or modifying any UI component."
4. Pin the Knowledge entry to the specific repo(s) that should use it (**Settings → Resources → Knowledge**, set the repo scope).

**Tip for multi-project setups:** create one Knowledge entry per repo/`DESIGN.md`, named descriptively (e.g., "Design System — Project A"), rather than one generic entry — this avoids Devin applying the wrong project's tokens to the wrong codebase.

---

## Other Platforms (Windsurf, GitHub Copilot, Cline, Aider, Codex)

These all support reading a `DESIGN.md` at the repo root, either automatically or via a one-line pointer in their respective instruction files:

| Platform | Instruction file to add the pointer to |
|---|---|
| Windsurf | `.windsurf/rules` or global rules — add "Read DESIGN.md before UI work" |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cline | `.clinerules` |
| Aider | `CONVENTIONS.md` (referenced via `--read`) |
| Codex / Codex CLI | `AGENTS.md` |

Use the same `08-ai-agent-integration/DESIGN.md.template` for all of these — one `DESIGN.md`, multiple thin pointers.

---

## Maintenance

- If you update the core knowledge base (`01-design-principles/` through `07-ai-agentic-ux/`), check whether the decision-tree tables in the two `SKILL.md` files and the rule summaries in `ui-ux-design.mdc` need a matching update — they're intentionally lean summaries, not full copies, so they can drift out of sync if a whole new topic area is added.
- `DESIGN.md.template` is a **template**, not meant to be used as-is — every real project should have its own populated `DESIGN.md` with actual token values, not the placeholder ones shown here.
