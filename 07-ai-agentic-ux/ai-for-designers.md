# AI for Designers: State of Practice

## The Honest Baseline: AI Isn't a Design Replacement

As of the current generation of tools, AI does not reliably replace core steps in the design process:

- **AI wireframing tools remain unpredictable** — they often shuffle pre-made, poorly-fitting components rather than genuinely reasoning about layout, and aren't reliable enough for professional, ship-ready work.
- **AI image generators (Midjourney, DALL·E, etc.) carry real risk** for public-facing use — copyright ambiguity, inconsistency, and compatibility issues mean they're best confined to **ideation, prototyping, and internal use**, not production assets.
- Most general-purpose AI tools are fundamentally **text-first** — which makes them strong at summarizing, editing, generating UX copy, and communicating in the right tone, but comparatively weak at genuine visual design judgment.

**Practical takeaway:** if you're not using AI heavily in your design work right now, you are not "behind" — the tools genuinely aren't mature enough yet to replace craft. Use AI now for the text-heavy, low-risk busywork (copy editing, summarization, documentation) and keep sharpening core design skills with traditional tools. This will change over time — but it hasn't changed as fast as the hype suggests.

---

## Code Is Becoming a Design Material

A structural shift is underway: code, historically the end of the design pipeline (designers hand off static mocks, engineers translate them into code), is becoming something designers **manipulate directly**, thanks to AI-assisted coding tools.

### What's Changing
- Code was previously **gatekept** — you needed real engineering skill to build anything functional. AI has largely democratized that: if you can describe what you want, you can often generate a working version of it.
- This is producing a blurred, back-and-forth workflow: design in a tool like Figma → bring it to life and modify it via AI-assisted coding ("vibe-coding") → sync changes back to the design canvas — rather than a strict one-way handoff.
- Many designers are already living this shift day-to-day: using AI to draft research guides, synthesize findings, generate early concepts, prototype, and iterate — well beyond traditional visual design tasks.

### The Real Danger: Perfecting Too Early
AI-assisted prototyping can produce high-fidelity, interactive mockups **far faster** than before — which is genuinely useful for aligning teams and exposing edge cases early. But it creates a new failure mode:

> High-fidelity, polished-looking output creates a false sense of completeness. Because the concept *looks* finished, teams can commit to a direction before the underlying structure/logic has actually been solved.

**Case in point:** a team used an AI-generated high-fidelity prototype to align on an initial workflow — which worked well. But when a more complex secondary workflow (a multi-state approval process) emerged, continuing to iterate at high fidelity caused conversations to get stuck on surface details (copy, spacing) instead of the underlying architecture. The fix was to **deliberately step back to low-fidelity artifacts** — block diagrams, information-architecture maps, abstracted system diagrams — to solve the structural problem before returning to high-fidelity execution.

**Design principle: match fidelity to the actual open question.** If the open question is structural/architectural, stay low-fidelity even if a high-fidelity mock is technically one prompt away. The speed of AI generation is not a reason to skip low-fidelity thinking — if anything, it makes the discipline to *not* jump to polish more important, not less.

### Why This Still Requires Human Thoughtwork
Raw AI generation is not the same as design strategy. An AI can construct a plausible-looking "wing of a house," but it doesn't inherently know if the materials, style, and layout fit the rest of the home, the needs of its occupants, or its environment — it optimizes for a statistically average, plausible-looking output, not a contextually correct one.

A polished, fast AI-generated screen can hide:
- A broken interaction model
- Logic that completely misses the actual user pain point
- Structural assumptions that only surface once real edge cases appear

The tactile, deliberate act of sketching/prototyping by hand is not just tradition — it engages **embodied cognition** (the idea that physically making something forces deeper problem engagement than passively reviewing generated output). Practically: keep sketching and low-fidelity wireframing as a genuine thinking tool, not a step to skip now that AI can generate polish instantly.

---

## UX-Context Design: The New UX Deliverable

As more interface work becomes AI-generated — by designers, PMs, and engineers alike — the actual output of research and design work is shifting from **documents written for humans** to **curated context that steers AI generation**.

### Why This Shift Is Happening
AI models produce output based on context: your request, plus whatever instructions, standards, examples, and background accompany it. Without your organization's specific context, a model defaults to a "middle-of-the-road" average of its training data — an average search screen, an average two-story house, an average onboarding flow. That average is often wrong for your specific users.

> Analogy: a skilled builder designing your house without ever meeting your family will design the *average* house — two stories, generic layout. If you use a wheelchair, have a baby who needs to sleep nearby, or work from home with no kids, that average design is wrong in ways that matter — not because the builder is bad, but because they lacked context.

**Everyone is now designing**, whether they hold a "designer" title or not — PMs asking for quick mockups, engineers letting a coding assistant decide button placement and error copy. Gatekeeping who's "allowed" to design is both impractical and counterproductive. The realistic goal is ensuring **everything AI generates is informed by the organization's actual user knowledge and standards**, regardless of who prompted it.

### AI-Ready Deliverables Look Different From Human-Ready Ones
Traditional UX deliverables (personas with stock photos and first names, journey maps, findings decks) were built to help **humans** empathize and remember. A model doesn't need persuading — it needs the underlying reasoning, distilled and structured, not narrative packaging.

- Feeding raw research transcripts directly to a model can work, but without human curation, the model may fixate on the wrong takeaway or lose signal in noise.
- The goal is deliverables that are **"AI-ready" / machine-readable**: curated by a skilled human, but structured for model consumption rather than human persuasion.

### DESIGN.md: A Concrete, Real Pattern
Google Labs' open-sourced **DESIGN.md** format (grown out of the Stitch AI design tool) is a working example of this shift. It lives alongside a product's code and contains two things:
1. **Machine-readable exact values** — colors, type sizes, spacing, corner radii — written precisely enough for tools to parse and apply correctly.
2. **Human-readable prose** — explaining *what those values are for* and *how to apply them*, including do's and don'ts.

Instead of an AI tool guessing intent (e.g., "is this blue a brand color or a semantic error color?"), it can check its own choices against explicit rules — including automated accessibility-contrast verification. Critically, **there's no handoff** — the file is read fresh every time an AI tool generates something, rather than being a one-time reference document.

### UX.md: A Broader Hypothesis
Extending the DESIGN.md idea beyond visual identity, a hypothetical **UX.md** could reference DESIGN.md and additionally encode:

| Section | Purpose | Example |
|---|---|---|
| **Research synthesis** | Findings stated as direct constraints, not narrative insights | "Users abandon setup when asked for information they don't have on hand" becomes a generation constraint, not just a report footnote |
| **Interaction standards** | How the product behaves | When to use confirm dialogs vs. allow undo; how errors are worded; expert vs. novice optimization |
| **Glossary** | Domain-specific vocabulary | If users say "case" but get confused by "ticket," the AI should default to "case" |
| **User models** | What research established about users | Expertise level, concerns, goals, known friction points |
| **World models** | The real-world context of use | A nurse interrupted mid-task; a driver filing a claim under stress; a workflow requiring an audit trail for compliance |

A finding like "users work in this product for hours, making complex decisions with many variables" should measurably steer generation toward **denser, information-rich screens** (what expert users actually prefer) — while a "used a few minutes a month" finding should steer toward **fewer choices per screen**. Without this context explicitly encoded, the model defaults to whatever's statistically common in its training data — which may be the opposite of what your specific users need.

### Curation, Not Handoff — Two Properties That Matter
1. **Not written for humans.** Its success is measured by whether AI output improves — not whether it convinces a stakeholder in a meeting. This is a genuinely different success metric than traditional UX deliverables.
2. **Not separate from the product.** It lives with the code, updates as the product changes, and is read by every AI tool in the org on every generation — not archived after a single handoff meeting.

This makes UX-context design **continuous** rather than a phase that ends: new research updates it, and so does observing what the AI consistently gets wrong.

### Getting Started (Practical Steps)
1. Take a small sample of your team's most load-bearing research insights.
2. Write them down as direct, plain-language constraints in a markdown file your team's AI tools can actually see.
3. Make your design system machine-readable (tokens, exact values + usage prose) — following the DESIGN.md pattern.
4. Observe what changes in AI-generated output, and iterate the file based on what the AI still gets wrong.

---

## Vibe Architects: How Non-Developers Are Actually Using Agentic AI

A notable 2025-era research finding: non-developers are already building **complex, proactive agentic systems** — multi-agent orchestration, automation pipelines, even team-wide "operating systems" replacing meetings — using tools like Claude Cowork/Code, almost entirely through intuition rather than technical understanding. Researchers call these people **"vibe architects."**

This matters for designers because it's a live case study in what happens when a technology's promised ease-of-use ("just talk to it") collides with real usability gaps.

### What Vibe Architects Actually Do
- They build real, working systems — automation pipelines, multi-agent coordination, entire team workflows — sometimes living purely in markdown files or a chat interface, with no traditional UI at all.
- They **don't prompt-engineer carefully.** Frontier models are good enough at interpreting ambiguous, stream-of-consciousness input (often dictated, not typed) that most participants skip careful prompt construction entirely.
- They **delegate decision-making, not just execution**, often accepting an AI's own improvement suggestions (e.g., asking "what would make this world-class?" and accepting whatever comes back) with minimal review.
- One participant reported approving permission requests reflexively, without reading them, because "it only has the context of this folder" — a rationalization for reduced oversight that may or may not be sound depending on what's actually scoped to that folder.

### How They Learn (and Why It Matters for Product/Onboarding Design)
- **The AI products themselves consistently fail as a learning source** — even for technically sophisticated users. LLM behavior is opaque and inconsistent across models and configurations, and users don't discover limitations until they hit them directly.
- **Nearly all learning happens outside the product** — Twitter, Reddit, YouTube, Slack communities, or word-of-mouth from tech-savvy peers. Multiple participants explicitly said the product's own onboarding gave them no clear guidance on core usage questions (e.g., "I don't really understand what Cowork is for").
- Even after **hundreds or thousands of hours of use**, opacity persists at the deepest end of practice — expertise here compounds into "a feel for where it fails," not into articulable, transferable knowledge. One advanced user described a security-and-privacy governance file (`boundaries.md`) that the AI had created and maintained on its own — he hadn't written it, and reviewed it only after the fact.
- This produces a documented emotional pattern: **quiet embarrassment.** Nearly every studied participant assumed someone else must be using these tools "more cleanly, more professionally" — despite being genuinely advanced users themselves.

### Design Implication: The Onboarding Gap Is the Real Product Gap
The core finding for designers: **capability alone doesn't win adoption.** These tools are already extraordinarily powerful — what's missing is a usable, self-contained entry point that doesn't require months of community-sourced tacit knowledge to operate confidently.

If you're designing agentic tools for non-technical users, treat the following as first-class design problems, not afterthoughts:
- **In-product learning that actually works** — if users have to leave your product and go to Reddit/Twitter to understand basic usage, your onboarding has failed regardless of how capable the underlying model is.
- **Legible system state** — users should be able to answer "what is this system currently doing, and why" without hunting through generated files they never wrote.
- **Meaningful default permission tiers** — reflexive, fatigue-driven approval of every permission request (to the point of reported repetitive strain injury in this study) is a signal that the permission UX pattern itself has failed, not that users are being careless.
- **Explaining tool relationships clearly** — if your product has multiple modes/entry points (e.g., a chat mode and an agent mode), don't assume users — or even the AI itself when asked — can clearly explain when to use which.
- **System decay is a real, recurring cost.** Agentic systems these users built required ongoing maintenance as "context drifts" and "connections expire" — design explicit maintenance/health-check surfaces rather than assuming a system that worked once keeps working indefinitely.

### The Bigger Trend
Non-developer, non-technical adoption of agentic AI is shifting from hypothesis to explicit product strategy — major AI labs are actively repositioning coding-agent products toward non-engineering roles (sales, creative production, finance) at significant scale and growth rate. Designers working in or adjacent to this space should expect **"agentic UX for non-developers"** to be a fast-growing, high-demand design specialty — and one where the core unsolved problem is legibility and trust, not raw capability.
