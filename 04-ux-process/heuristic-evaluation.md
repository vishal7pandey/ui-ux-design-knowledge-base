# Heuristic Evaluation

## What Is a Heuristic Evaluation?

A method for finding usability flaws in a design by judging it against known principles for what makes user interfaces easy to use. The ten most fundamental principles are Jakob Nielsen's **Usability Heuristics** — broad rules of thumb that apply across nearly all interface types (mainframes, mobile, voice assistants, smartwatches) and nearly all product categories (games, enterprise software, consumer apps).

These heuristics have remained unchanged for **25+ years** precisely because they're grounded in the basics of human cognition and behavior, not any particular technology. They will likely remain relevant for future interface paradigms too — including voice and agentic UIs, with reinterpretation (e.g., "visibility" becomes "audibility" for voice systems).

> If you're about to launch a product that violates one of these heuristics, don't assume you're the exception — validate with real user testing first.

---

## The 10 Usability Heuristics

### 1. Visibility of System Status
Users should always know what the system is doing and what state it's in — through timely, appropriate feedback. They should never have to guess or remember.

- **Persistent status** (always visible): battery indicator, Wi-Fi signal, connection status.
- **Triggered feedback** (after an action): button press states, progress indicators, confirmation toasts.
- Analogy: an elevator call button that lights up and shows which floor the elevator is on — you know it registered your request and can estimate the wait.
- **Don't over-communicate.** If the user can't act on a status update, it's just noise. Show only what's genuinely useful or reassuring.
- This heuristic underlies trust: continuous, appropriate communication makes a system feel reliable and predictable.

### 2. Match Between System and the Real World
Speak the user's language — words, phrases, and concepts they already know — not internal jargon or system-oriented terms. Follow real-world conventions so information appears in a logical, expected order.

- **Avoid marketing jargon.** "Staff Directory" beats "Meet & Greet" — the direct label creates a stronger information scent because it maps to an existing mental model.
- **Skeuomorphism is one execution of this heuristic** — e.g., page-turning gestures, highlighting text, and bookmarking in e-reader apps mirror physical book interactions.
- Users' mental models come from **both** prior digital experience and real-world/physical experience — design must account for both.
- **Test with real users** — don't rely on what makes sense to you as the designer.

### 3. User Control and Freedom
Users often invoke functions by mistake and need a clearly marked "emergency exit" — support undo and redo everywhere.

- Classic example: browser back/forward buttons. Without them, every click would need total confidence.
- Every process or mode needs an exit path — don't rely solely on browser-level navigation.
- **Undo/cancel is especially critical on mobile/touch** where accidental taps are common.
- **Discoverability matters as much as existence.** A hidden "shake to undo" gesture that nobody knows about might as well not exist.
- Control and freedom reduce user anxiety — people explore more confidently when they know mistakes are reversible.

### 4. Consistency and Standards
Users shouldn't have to wonder whether different words, icons, or actions mean the same thing.

| Type | Definition | Example |
|---|---|---|
| **Internal consistency** | Consistency within your own product/family of products | If orange = "actionable" for buttons, don't reuse it for static headings |
| **External consistency** | Consistency with conventions across the industry/web at large | Shopping cart icon in the top-right on e-commerce sites |

- **Jakob's Law:** "People spend most of their time on sites other than yours." If everyone else follows a convention and you break it, you force users to relearn something — at a real cognitive cost.
- Breaking convention is sometimes worth it (you've found a genuinely better pattern) — but treat it as an exception, not a default, and validate with testing.

### 5. Error Prevention
Good design prevents errors before they happen — better than a great error message after the fact.

- A "reply-all" disaster isn't user error — it's a **design error** that failed to prevent an easy, high-consequence mistake.
- **Prioritize by consequence.** Start with errors that cause severe damage (medical, financial, security contexts), then address minor annoyances.
- Prevention techniques:
  - Constrain input (date pickers, dropdowns instead of free text)
  - Adjust size, color, placement, or texture of risky controls
  - Add confirmation dialogs for destructive/high-stakes actions ("Are you sure you want to transfer all your money?")
  - Provide undo as a safety net when prevention alone isn't enough

### 6. Recognition Rather Than Recall
Minimize the user's memory load by making options, actions, and information visible — recognition (seeing and confirming) is easier than recall (retrieving from memory unaided).

- Example: "Is Lisbon the capital of Portugal?" (recognition) is easier than "What is the capital of Portugal?" (recall) — because recognition provides more contextual cues for memory retrieval.
- **Menus are the classic recognition-based UI** — showing available commands instead of requiring users to remember command names (as in old command-line interfaces).
- Practical translation: show recently used items, provide autocomplete, use icons + labels together, and surface options rather than requiring users to recall exact syntax or paths.

### 7. Flexibility and Efficiency of Use
Let both novice and expert users work efficiently — accommodate multiple ways to perform the same action.

- **Accelerators** are shortcuts for experienced users: keyboard shortcuts (⌘C), gestures (double-tap to like), macros.
- Accelerators shouldn't be forced on new users — don't front-load every shortcut in a first-run experience; let users discover them over time.
- A well-designed system is flexible enough to be efficient for experts *and* approachable for newcomers — these aren't in tension if accelerators are optional, discoverable enhancements rather than the only path.

### 8. Aesthetic and Minimalist Design
Interfaces should contain only relevant, need-to-know information — not necessarily flat or monochromatic, but focused.

- Related to **signal-to-noise ratio**: every extra unit of information (text, visuals, animation) competes with what actually matters and reduces its relative visibility.
- **Prioritize ruthlessly.** Content or features used infrequently, or by a small non-critical user segment, are candidates for removal or relocation.
- Decorative visuals should support user or business goals — not exist purely "to look nice."
- Mantra: **communicate, don't decorate.**

### 9. Help Users Recognize, Diagnose, and Recover From Errors
Error messages should be expressed in plain language, precisely indicate the problem, and constructively suggest a solution.

Three-part recipe:
1. **Clearly inform users an error occurred** — combine messaging with visual treatment (red text, warning icon).
2. **Explain what went wrong in plain language** — e.g., "This page is missing or has moved" beats a raw error code.
3. **Offer a concrete way to fix it** — ideally an actionable shortcut, not just instructions. Example: an empty search-results page that explains "too many filters" *and* offers one-click filter removal, right in the error message.
4. **Undo as a recovery mechanism** — e.g., Gmail's "Undo Send" turns a potential error into a non-event.

> The best error handling is prevention (Heuristic #5) — but when errors do occur, recovery quality determines whether users trust the system afterward.

### 10. Help and Documentation
Even highly intuitive products eventually need help — especially as interfaces grow more complex (more gestures, more features, more edge cases).

Modern help takes many forms beyond static help pages: onboarding flows, walkthroughs, tooltips, popovers, videos, chatbots, live chat.

**Evaluation questions:**
- Is help easy to *search* for?
- Is documentation focused on the user's actual task (not just feature descriptions)?
- Does it provide concrete, scannable steps?

**Good practice examples:**
- Phrasing FAQ suggestions as questions (matches how users search) improves scannability.
- **Contextual help** (a popover exactly where the user needs it, exactly when they need it) beats a generic help center — timely and task-focused.
- Interspersing screenshots with numbered steps (rather than dense paragraphs) improves comprehension.

**Common failures:**
- Overly restrictive search fields (e.g., character limits that truncate real queries).
- Search results that are just page links, forcing users to click through blindly instead of scanning an answer.

---

## How to Conduct a Heuristic Evaluation

### Step 1: Prepare Your Team
- Solo evaluation is fine for practice, but for real usability audits, use **3–5 independent evaluators**.
- No single evaluator — regardless of experience — catches every problem. Multiple evaluators surface a broader, more reliable set of issues.

### Step 2: Decide How to Document
Any medium works: pen and paper, a spreadsheet, a digital whiteboard (Miro/FigJam), or a structured heuristic-evaluation workbook/template.

Minimum fields to capture per issue:
- Heuristic violated (1–10)
- Description of the issue
- Severity/impact
- Recommendation (optional but valuable)

### Step 3: Evaluate Independently
Each evaluator works through the interface **twice**, alone:

1. **First pass — learn the system.** Move through the interface as a real user completing a task. If unfamiliar with the product, don't evaluate yet — just learn how it works.
2. **Second pass — hunt for violations.** Go through the same task again, actively looking for design elements/decisions that violate one of the 10 heuristics. Log each one against the specific heuristic it violates.

**Worked example:** Evaluating a mobile e-commerce site for the task "buy a shirt." On the second pass, you notice product listing pages overlay text (name, price, discount) directly on top of product images, making both hard to read. This violates **Heuristic #8 (Aesthetic and Minimalist Design)** — log it as: *"Text overlaps with product images on listing pages"* with a recommendation like *"Add a solid or semi-opaque background behind overlaid text."*

### Step 4: Consolidate Issues
Once everyone has completed an independent evaluation:
1. Bring all findings together — **affinity diagramming** (physical or digital whiteboard) works well.
2. Group duplicate/related issues found by multiple evaluators (these are often the highest-confidence problems).
3. Align on severity and prioritize which issues to fix first.
4. Assign owners and next steps.

### Tips
- These four steps look simple but take practice to execute well — don't be discouraged if your first evaluations feel slow or uncertain.
- Heuristic evaluation is a **discount usability method** — fast and cheap compared to full usability testing, but it surfaces expert-judgment issues, not real user behavior. Pair it with usability testing (see [usability-testing.md](./usability-testing.md)) for a complete picture.
- Use heuristic evaluation early and often: before major releases, after significant redesigns, or as a periodic health check on mature products.

## Quick Reference Table

| # | Heuristic | One-Line Test |
|---|---|---|
| 1 | Visibility of System Status | Does the user always know what's happening? |
| 2 | Match Between System & Real World | Does it speak the user's language and follow real-world logic? |
| 3 | User Control & Freedom | Can users easily undo, cancel, or exit? |
| 4 | Consistency & Standards | Do the same words/icons/actions always mean the same thing? |
| 5 | Error Prevention | Can this mistake be prevented instead of just handled? |
| 6 | Recognition Rather Than Recall | Are options shown, not memorized? |
| 7 | Flexibility & Efficiency of Use | Can both novices and experts work efficiently? |
| 8 | Aesthetic & Minimalist Design | Is every element earning its place on screen? |
| 9 | Help Recognize/Diagnose/Recover From Errors | Is the error message plain, specific, and actionable? |
| 10 | Help & Documentation | Can users find task-focused help when they need it? |
