# AI Interface Patterns

## Overview

As AI capabilities move beyond the chat box, a new generation of interface patterns is emerging — voice interfaces, agent canvases, adaptive/generative UIs, and multimodal creation tools. This is a genuinely new design frontier: previous software design dealt mostly with **nouns** (buttons, forms, screens); AI-native software increasingly needs interfaces for **verbs** (workflows, autocomplete, delegated tasks) — and the tooling for representing verbs visually is still immature.

---

## Voice AI Interfaces

### Latency Is the Interface
In voice interactions, **response speed *is* the primary usability signal.** The longer a system takes to respond, the less it feels like a natural conversation and the more it feels like talking to a robot — latency alone can break the illusion of "talking to a human," even when the voice quality itself is excellent.

Design implications:
- For developer-facing voice tools, **expose the latency number** (e.g., milliseconds per response) as a visible, persistent metric — this builds an intuition for what "feels natural" vs. "feels robotic" and helps teams optimize the right thing.
- Distinguish **dev-mode** transparency (show all diagnostic info: latency, confidence scores, intermediate reasoning) from **production-mode** simplicity (hide all of that from end users).

### Multimodal Feedback Is Required, Not Optional
Pure voice interfaces without any visual cues create real usability problems:
- Users can't tell if their voice was actually recognized (no confirmation that the mic picked them up).
- Users can't tell if the system is speaking, thinking, or has failed silently (e.g., if the device is accidentally muted, a voice-only interface gives no way to distinguish "broken" from "just quiet").

**Always pair voice output with a visual indicator** — even a simple waveform, pulsing icon, or "listening…" state — whenever a screen is available. Pure-voice-only design should be reserved for genuinely screen-less contexts.

### Interruption Handling
Real human conversation includes interruptions — a well-designed voice agent should detect when the user starts speaking mid-response and yield the floor, rather than talking over them or ignoring the new input entirely. Current-generation systems often fail this test (finishing their own sentence, then answering a stale/previous question). This is a known gap to test for explicitly.

### Learning Mid-Conversation
Simple systems keep referring to information from the start of a session even after being corrected. A well-designed conversational agent should **update its working model of the user within the same conversation** — e.g., if a caller says "actually, this is Steve, not Aaron," the agent should refer to them as Steve for the rest of the call, not just apologize and continue using the old name.

---

## Canvas-Based Agent Workflow Interfaces

Visual, node-based canvases (à la Figma/Miro) have re-emerged as the dominant pattern for modeling and monitoring autonomous, multi-step agent workflows — echoing flowchart traditions from chip design and older engineering disciplines, now resurfaced for the AI era.

### Why Canvases Work for Agent Workflows
Agent processes are inherently **multi-dimensional and branching** — not linear, step-by-step recipes. A canvas lets designers represent:
- Sequential steps *and* branching decision trees simultaneously
- Parallel paths that a linear document (like a numbered list) can't easily express
- The full "decision tree" an agent might traverse, not just the happy path

### Design Guidance for Agent Canvases
- **Use color coding by node type** (input, action, output, decision) — but always pair color with a visible legend; color-only encoding fails for both accessibility and simple onboarding.
- **Support multiple zoom/fidelity levels.** At high zoom-out, small text becomes unreadable — collapse distant nodes into simplified colored blocks rather than leaving unreadable text on screen.
- **Make the "run" action unambiguous.** Ambiguous icons (like an up-arrow for "execute") can be misread; a clear play/run icon converts better than abstract icons.
- **Annotate with inline text blocks**, not just nodes — freeform text callouts explaining "why" a section exists help new users understand a complex flow without needing a separate manual.
- **Showcase multi-dimensional/branching examples in onboarding templates.** A purely linear starter template undersells the canvas's actual power — pick a template with real branching logic to demonstrate the tool's value.

---

## Adaptive, Content-Driven UI

### The Core Shift
In adaptive AI interfaces, the **content becomes the input**, and the AI's interpretation of that content becomes the UI shown back to the user — rather than a single static UI serving all content.

**Example pattern:** An email-triage tool that reads each email's content and dynamically generates a *different* set of suggested-response actions per email (e.g., "confirm a callback time" vs. "approve a document") — rather than presenting a fixed list of generic reply buttons for every message.

### Interaction Consistency Under Changing Content
When the available *options* change per item (per email, per record, per card), keeping the **interaction method** constant is critical for usability:
- If a keyboard shortcut like "Y" always means "accept the top suggestion," users can build muscle memory even though *what* Y confirms changes every time.
- This lets users keep their hands on the keyboard and stay in flow, rather than re-scanning the UI for the right button on every item.

### The Focus Ambiguity Problem
A key interaction-design risk in adaptive UIs with global hotkeys: **is the user's next keystroke a command, or text input?** If a text field is focused and a global hotkey shares a letter with normal typing (e.g., "Y" as both a shortcut and a valid input character), users can accidentally trigger unintended actions. Always make focus state highly visible, and consider modifier keys (not bare letters) for destructive or high-impact actions.

### Right Level of Abstraction
There's a spectrum of how much an adaptive interface should do *for* versus *with* the user:
- **Full autopilot** — the system acts with no per-item review (fastest, least control)
- **Predictive draft** — the system prepares a best-guess response already sitting in the inbox, user tweaks with a higher-level prompt
- **Guided selection** — the system offers a curated small set of context-specific options, user picks (a good middle ground for most cases)
- **Manual** — no AI assistance; full user control

Choose deliberately based on the stakes and reversibility of the action — don't default to maximum automation just because it's technically possible.

---

## AI-Generated UI (GenUI)

### Definition
A **generative UI (GenUI)** is an interface dynamically generated in real time by AI to fit a specific user's needs and context — as opposed to a single static interface designed once and shown to everyone.

### GenUI vs. AI-Assisted Design (Important Distinction)
- **AI-assisted design** (common today): designers use AI tools to speed up their *existing* design process — the output is still a single, fixed interface used by all users.
- **GenUI** (mostly aspirational, not yet mainstream): AI generates *custom* content, layout, and styling in real time, per user, per moment — potentially producing a different interface for every single user.

### Illustrative Example (Conceptual)
A travel-booking app where a user with dyslexia sees a font and color-contrast profile tailored to her documented accessibility needs; results are ranked by her personal priorities (cost, travel time) rather than a generic default order; red-eye flights she never books are auto-collapsed; a warning about a pricing-impacting event is proactively surfaced based on her destination and dates. This level of personalization is technically plausible for a single user manually, but **GenUI's value is delivering it at the scale of millions of users simultaneously** — which is not feasible with hand-crafted static UI.

### Current State (Reality Check)
As of recent research, GenUI in production is mostly still **AI-assisted design**, not true real-time interface generation. True GenUI requires AI generation to be more stable, reliable, and less resource-intensive than current models allow. Treat "the interface generates itself per user" as a forward-looking design exercise for now, not a shipped pattern — but start thinking about the underlying architecture (design tokens, component libraries, and design systems that could theoretically be assembled by an AI) today, since that groundwork pays off regardless of when true GenUI matures.

---

## Trust & Verification Patterns for Agent Output

When an agent goes out and autonomously gathers information (web search, scraping, multi-step research), users need a way to verify the results weren't hallucinated.

### Inline Citation Pattern
Attach sources directly to AI-generated answers, inline — not as a separate, disconnected list of links at the bottom. This pattern (popularized by tools like Perplexity) uses small numbered markers within the generated text that map to specific source fragments, letting users verify *which part* of an answer came from *which* source.

- In dense UI (e.g., spreadsheet cells), this can be collapsed into a popover/hover state to save space, while still being one click away.
- This borrows directly from academic citation conventions (footnotes) — a long-standing pattern for trust in written work, now resurfacing in software.

### Handling Missing Units/Context in Extracted Data
When an agent extracts structured data (e.g., "$470 million" becomes just "470" in a cell), the missing unit/context isn't just cosmetic — it can materially mislead a user scanning a table quickly. Always verify extracted values retain their necessary context (units, currency, scale) or make it one click away (e.g., clicking into the cell reveals the full sourced answer).

---

## Multimodal Content Generation (Video, Voice, Design)

### The Fidelity-for-Latency Trade
Full-fidelity AI generation (a polished, lip-synced deep-fake video; a fully rendered UI mockup) often takes minutes. Making a user wait blind for that duration, only to discover the output doesn't match their intent, is a costly UX failure.

**Pattern: low-fidelity preview first, high-fidelity generation on confirmation.**
- Example: an AI video tool shows a **blurry preview with correct audio** almost immediately, letting the user validate script/tone/pacing before committing to the ~10+ minute full-fidelity render with accurate lip-sync.
- This deliberately trades some fidelity for immediacy, and puts the human back in the loop *before* the expensive generation step — rather than after.

### Free-Form Prompt Boxes Need Scaffolding
Fully open text-based generation ("describe what you want") is powerful but risky: users may not know the vocabulary the system understands (e.g., design terms like "glass morphic" or "skeuomorphic"), leading to wasted generation cycles on misunderstood prompts.

Mitigations:
- **Pre-built example prompts as one-click buttons** — this both demonstrates the tool's range and gives users a starting template to modify rather than starting from a blank page.
- **A richer prompt-builder UI** — surfacing selectable "pills" for common style/technique vocabulary (like draggable Lego-brick terms) reduces reliance on users already knowing the right jargon.
- **Feedback on what the model did/didn't respect** from the prompt — showing (even informally) which parts of a prompt were honored and which were ignored helps users iteratively refine prompts rather than guessing blind.

### Incremental Editing, Not Full Regeneration
When a user requests a small change to AI-generated output (e.g., "make the sidebar blue"), the system should ideally apply an **incremental diff** rather than regenerating the entire output from scratch. Full regeneration risks losing previously-accepted elements, wastes compute, and takes longer than a scoped edit would. This is a known hard problem — solving it well is a competitive differentiator, not a solved commodity.

### Engagement During Long Waits
For generation tasks that take multiple minutes, don't rely on vague, disappearing status messages. Borrow patterns from other domains that have solved long-wait UX before (e.g., flight meta-search engines): show low-resolution partial results early, and let users start interacting (adjusting filters/parameters) *while* the full result continues to compute in the background.

---

## Cross-Cutting AI Interface Design Checklist

- [ ] Does the interface provide visual feedback for voice input, even when a screen is available?
- [ ] Is latency visible or optimized for, given it directly impacts perceived naturalness?
- [ ] Can the agent update its model of context mid-session (not just at session start)?
- [ ] Are agent workflows visualized with branching/multi-dimensional structure, not forced into a linear list?
- [ ] Do adaptive interfaces keep interaction methods (hotkeys, gestures) stable even as available options change?
- [ ] Is it unambiguous whether a keystroke will trigger a command or be typed as text?
- [ ] Are AI-generated claims/data backed by inline, verifiable citations?
- [ ] Do extracted values retain necessary context (units, currency, scale)?
- [ ] For long-running generation, is there a low-fidelity preview before the full-fidelity commit?
- [ ] Does the prompt interface scaffold users toward vocabulary the system actually understands?
- [ ] Can users make incremental edits without triggering full regeneration?
