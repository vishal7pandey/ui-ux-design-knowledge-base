# Agentic Experience (AX) Design

## From UI → UX → AX

Design has moved through distinct eras, each layering on top of the last rather than replacing it:

| Era | Decade | Focus |
|---|---|---|
| **UI Design** | 1980s | Screens, buttons, icons — the age of computers |
| **UX Design** | 2000s | Human-centered design — flows, usability, emotion |
| **AX Design** | 2020s | Human + AI co-agency — designing for autonomous agents acting on a user's behalf |

**AX (Agentic Experience) design** is the practice of designing how humans and AI agents interact — including how agents interact with interfaces, with each other, and with the humans who delegate to them. It doesn't replace UI/UX; it extends it. The fully accurate name is really "UI/UX/AX," but the industry has converged on **AX** as shorthand for all three combined.

> Job titles like "Agentic UX Designer," "AI Interaction Designer," and "Adaptive Systems Designer" are already appearing — this is a genuine emerging discipline, not just a buzzword.

---

## Why AX Is a Distinct Discipline

Traditional software is built on the **command line → GUI** lineage: humans learned to operate computers via explicit, deterministic commands, then GUIs wrapped that complexity in visual metaphors anyone could use.

AI agents flip this: **agents are excellent at operating the "command line"** on our behalf. When we let an agent type the commands, type the API calls, and navigate the raw system, we shift from designing interfaces *for users* to designing interfaces *for agents*, with humans supervising at a higher level of abstraction.

This creates new design questions that don't exist in classical UX:
- How does a system communicate its *reasoning*, not just its output?
- How does a user delegate an outcome without losing situational awareness?
- What happens when the system acts *before* the user asks?
- How much autonomy should an agent have by default, and how is that adjusted?

---

## Core AX Design Principles

Distilled from planning a real agentic app (a journaling agent) end-to-end, these are the six recurring principles that show up in agent-first products:

### 1. Intent Recognition
The agent must extract *what the human actually needs* from unstructured input — text, voice, or a mix — even when the request is ambiguous or bundles multiple sub-intents together.

- Example: "Just got back home, feeling tired. What should I do now?" contains a **journal entry** (came home from work), a **mood log** (feeling tired), and a **question requiring historical context** (what should I do) — all in one utterance.
- Design implication: give the agent (and its prompt/framework) explicit instructions for how to decompose mixed intents, rather than assuming one intent per input.

### 2. Human-in-the-Loop Confirmation
Never let an agent silently commit to a database, send a message, or take an irreversible action without giving the human a review/edit/discard step — especially for anything with real-world consequences.

- The UI should **dynamically adapt** based on what the agent decided the user meant, presenting the appropriate reviewable output type (a draft entry, a mood chip, a suggested answer) rather than a generic "confirm?" dialog.
- This step is where trust is either built or eroded — rushing past it to feel "more autonomous" is a common and costly AX mistake.

### 3. Feedback & Learning
Every edit, correction, or rejection a user makes should feed back into the system's understanding of that user — not be discarded after the interaction ends.

- Example: if a user corrects a mood log from "tired" to "relieved" and mentions they want to read a book, the agent should carry that forward — next time this context recurs, it should already reflect the correction.
- Design implication: feedback loops need a home in your data model from day one; retrofitting personalization later is much harder.

### 4. Context Awareness
The agent should factor in environmental signals — time of day, day of week, location, recent history — to make its suggestions more accurate without the user having to restate context every time.

- Example: on a weekday at 8am, infer "going to work"; on a weekend evening, infer "going out with friends."
- This is what separates an agentic feature from a static automation — static automations require explicit triggers; agentic ones infer likely context.

### 5. Transparency
Users should be able to see, at some level of detail, *why* the agent suggested what it suggested. This builds trust and lets users correct bad reasoning rather than just bad output.

- Surfacing sources, "based on your history…" framing, or an expandable reasoning trace are all valid transparency mechanisms — the right depth depends on stakes and audience (developer-facing tools can show raw reasoning; consumer apps need simplified framing).

### 6. Progress & Achievement Visibility
For agents that operate over time (journaling, fitness, financial coaching), give users a persistent view into what the system has learned/tracked about them — patterns, mood tracking, recent wins.

- This isn't just a nice-to-have dashboard — it's a **trust-building mechanism**. If users can't see what the agent "knows," they can't calibrate how much to trust its suggestions.

---

## The Extended AX Framework (5 Pillars)

A broader lens for evaluating any agentic product, beyond the app-planning principles above:

### 1. Transparency Over Magic
The agent should show its reasoning ("why I did this") rather than presenting actions as unexplained magic. Unexplained automation is a UX nightmare the moment it's wrong even once — the more invisible an action, the more fragile the trust built on it.

### 2. Control Hierarchy
Let users set levels of autonomy explicitly:
- **Manual** — agent suggests, user executes
- **Guided** — agent drafts/prepares, user approves
- **Autonomous** — agent acts, user is notified after the fact

Don't force a single autonomy level on all users or all task types — high-stakes actions (financial transfers, sending external communications) usually warrant a stricter default than low-stakes ones (drafting an internal note).

### 3. Dialogic Feedback
Agents should *converse*, not just *confirm*. "I've done this. Would you like to adjust it?" is a fundamentally better interaction than a flat success/fail state — it invites correction and treats the interaction as ongoing rather than terminal.

### 4. Predictable Personality
An agent's behavior should be consistent across sessions and contexts. Predictability builds more trust than occasional brilliance — a system that's sometimes amazing and sometimes erratic is worse, from a trust standpoint, than one that's reliably "good enough."

### 5. Ethical Agency
Every autonomous action must preserve human values: privacy, informed consent, and the user's actual intent — not a convenient approximation of it. When an agent acts on a user's behalf and something goes wrong, "the algorithm did it" is not an acceptable accountability model.

---

## Designing for Accountability

When an AI agent negotiates a contract, sends a message, or transfers funds and something goes wrong, responsibility can't default to "nobody." Agentic systems need explicit **accountability layers**:

| Layer | Purpose |
|---|---|
| **Decision discipline** | Log what data/options the agent considered before acting |
| **Ethical alignment** | Verify actions stayed within user-defined boundaries |
| **Reversibility** | Let users roll back agent-made changes — make this the default expectation, not an edge case |

Opaque, unaccountable autonomy is not viable for any agentic product operating in a domain with real consequences.

---

## Emotional Design for Delegation

Handing tasks to an autonomous agent triggers a subtle but real emotional tension in users: **the loss of control.** People start asking, consciously or not: *"Do I still matter in this decision?"*

AX design must actively design for **emotional safety**:
- Reassure users they remain the *author* of outcomes, even when the agent took the initiative.
- Frame the relationship as **AI acting with the user**, not **for** the user — symbiosis rather than submission.
- Give users easy ways to reassert control at any point (pause, override, undo) without friction or shame ("are you sure you want to take over?" dialogs should not feel punitive).

---

## Adaptive UI: Designing for Verbs, Not Just Nouns

Traditional software design deals mostly in **nouns** — buttons, forms, dropdowns, fixed layouts that are the same for every user every time.

AI-native software increasingly needs to represent **verbs** — workflows, auto-complete, auto-suggest, "go gather information for me." We don't yet have mature, standardized tooling for visually representing verbs the way we do for nouns — this is an active, unsolved design frontier.

### Practical Implication: Content-Driven, Not Static, UI
In adaptive interfaces, the **content itself becomes the input**, and the AI's interpretation of that content becomes the UI shown back to the user. A well-known example pattern: an email triage tool that reads each email and dynamically generates *different* suggested-response buttons per email — rather than showing the same static set of reply options for every message.

Design considerations for adaptive/verb-based UI:
- **Keep interaction consistency even when content changes.** If hotkeys map to actions (e.g., "y" to confirm), keep the *keys* stable even as the *options* they trigger change per context — consistency in the input method offsets unpredictability in the available choices.
- **Distinguish "processing" input from "typing" input clearly.** In adaptive interfaces with global hotkeys, it must be unambiguous whether the user's next keystroke will trigger a system action or be typed into a field.
- **Surface confidence and reasoning inline**, especially for anything the agent inferred rather than the user explicitly stated.

---

## Converting an Existing App to Agentic (Pattern Library)

Any product can become "agentic" — the shift is from passive logging/input to the app inferring intent and taking initiative. Examples across common product categories:

| App Type | Traditional Pattern | Agentic Pattern |
|---|---|---|
| **Travel planner** | User manually enters dates/destinations | Autofill suggestions, smart activity groupings, contextual nudges across planning → booking → reminders |
| **Fitness tracker** | User logs every workout | Goal-driven prompts instead of logging; adapts recovery suggestions and motivational tone to progress |
| **Budget/spending app** | User reviews a static ledger | Interprets spending patterns and reframes advice by context (end of month vs. start, essential vs. luxury) |
| **Nutrition assistant** | User searches recipes manually | Scans available ingredients, adapts meal suggestions to dietary restrictions and time of day |
| **Learning app** | Fixed curriculum | Adapts difficulty to previous answers, adjusts motivational framing (competitive vs. supportive) |
| **To-do list** | User manually adds/prioritizes tasks | Detects vague-goal intent behind a task, auto-splits subtasks, dynamically reprioritizes |

The common thread: **the agentic version infers what a static version would require the user to specify explicitly.**

---

## AX Design Workflow (Practical Steps)

1. **Identify the problem** the agentic feature solves — be specific about the friction it removes (e.g., "journaling feels time-consuming and unstructured").
2. **Write a usage overview** in plain language: what does the user input, what does the agent do with it, what does the user see, how does the loop close (save/learn)?
3. **Build an AX flowchart** that includes *both* the user's steps and the agent's decision points — not just a standard user flow. Mark where each of the 6 AX principles (intent recognition, HITL confirmation, feedback/learning, context awareness, transparency, progress visibility) applies.
4. **Design the dynamic UI states** the agent can trigger — not just the "happy path" screen, but every output type the agent might generate (journal entry, mood log, suggestion, error/uncertainty state).
5. **Prototype the human-in-the-loop step explicitly.** This is the highest-leverage screen in any agentic flow — never skip designing it in detail.
6. **Test for trust, not just task completion.** Standard usability testing asks "could they complete the task?" AX testing must also ask "did they trust the agent's reasoning? did they feel in control?"

---

## Skills for AX Designers

Employers hiring for "Agentic UX Designer" / "AI Interaction Designer" roles are typically looking for:
- Ability to **map agent decision trees**, not just user flows
- Fluency testing **agent reliability and usability** (not just interface usability)
- Skill in **orchestrating adaptive interfaces** that change based on inferred context
- Comfort working with **AI workflow tools** (n8n, Zapier, Make, or custom agent frameworks) to prototype real agentic behavior, not just mock it in static screens
- Strong grounding in classical UX fundamentals — AX doesn't replace heuristics, accessibility, or research; it adds a new layer on top of them
