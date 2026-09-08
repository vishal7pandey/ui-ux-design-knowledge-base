# UX Writing and Content Design

UX writing is the craft of designing with words. It is the short text that guides users through an interface and helps them complete tasks. Done well, it reduces cognitive load, builds trust, and turns confusion into action.

---

## 1. Three Pillars of UX Writing

### Clarity

Users should understand the text on the first read. If they have to read it twice, the design has failed.

### Conciseness

Remove every word that does not add value. Concise does not always mean short; it means efficient.

### Consistency

Use the same terms, formatting, and tone throughout the product. If you call it “Reservation” on one screen, do not call it “Booking” on another.

---

## 2. Three Sizes of Copy

| Size | Length | Use for |
|------|--------|---------|
| **Microcopy** | Fewer than 3 sentences | Buttons, labels, error messages, tooltips, empty states |
| **Short-form** | A paragraph or two | Alerts, descriptions, onboarding cards, confirmation dialogs |
| **Long-form** | Multiple paragraphs | Help articles, terms, detailed explanations, documentation |

Most interface copy is microcopy. It is the text users actually read at decision points.

---

## 3. Microcopy Patterns

### 3.1 Buttons

**Formula**: verb + the user’s outcome

| Weak | Better |
|------|--------|
| Submit | Send invoice |
| Click here | Download report |
| OK | Save changes |
| Yes | Keep editing |

Button labels should survive being read alone. The user should know what happens before they click.

---

### 3.2 Error messages

**Formula**: what happened + why + what to do next

| Weak | Better |
|------|--------|
| Invalid email | Add the @ to your email address |
| Something went wrong | We couldn’t save your changes — the connection dropped. Your draft is safe; try saving again. |
| Upload failed | That file is 12 MB; the limit is 5 MB. Try compressing it or upload a CSV. |
| Error 500 | Something broke on our end. Your data is safe. Try again in a moment. |

**Avoid**:

- “Invalid” — it sounds accusatory.
- “Failed” alone — it gives no context.
- “Oops” for serious errors — it can feel dismissive.
- Raw error codes unless a support agent will need them.

---

### 3.3 Empty states

**Formula**: what this screen is for + the payoff + one action

| Weak | Better |
|------|--------|
| No messages | No messages yet. Conversations with your team will show up here. Start a conversation → |
| No results | No results for “prodct.” Did you mean “product”? Or browse by category → |
| Empty | Your favorites will appear here. Favorite items for quick access. Browse items → |

---

### 3.4 Form labels and placeholders

- Labels tell the user what belongs in the field. They are always visible.
- Placeholders are hints, not replacements for labels.
- Helper text explains formatting or constraints before the user types.

| Weak | Better |
|------|--------|
| Input data | Enter your email address |
| Email | Work email |
| Password | Password (at least 8 characters, one number) |

---

### 3.5 Notifications

**Rule**: earn the right to interrupt.

- Keep them short and actionable.
- Match the tone to the severity.
- Provide a clear close or undo action.
- Use them for outcomes the user cares about, not for marketing.

---

## 4. Voice and Tone

**Voice** is the brand’s personality. It does not change.

**Tone** adapts to the user’s emotional state and the context.

| Context | Tone |
|---------|------|
| Onboarding | Encouraging, light, educational |
| Daily use | Efficient, invisible |
| Error | Direct, helpful, calm |
| Payment failure | Serious, reassuring |
| Success | Warm, brief |

---

## 5. Accessibility in Writing

- Use plain language. Avoid jargon like “authenticating” or “buffering” if “checking” or “loading” works.
- Use active voice. It makes responsibility clear.
- Avoid directional language. “Click the red button below” is bad for screen-reader users. Use “Select Save to finish.”
- Do not rely on color alone. Pair it with text, icons, or both.
- Keep error messages next to the relevant field.
- Make sure copy still makes sense when read by a screen reader.

---

## 6. Inclusive Language

- Avoid gendered or ableist assumptions.
- Use people-first language where appropriate.
- Be careful with idioms that do not translate well.
- Do not make users feel excluded by default labels or examples.

---

## 7. Content Style Guide

A content style guide is the single source of truth for product copy. It should include:

- Terminology and definitions
- Capitalization rules
- Punctuation and formatting
- Voice and tone guidelines
- Error message and button conventions
- Examples of do’s and don’ts

---

## 8. Measuring Content Quality

Track the same metrics as UX:

- **Task completion rate** — did users finish the task?
- **Error rate** — are they making mistakes?
- **Time on task** — are they slowed down by confusing copy?
- **Support tickets** — do users ask for help where the copy should explain?
- **Click-through rate** — do clearer buttons drive more action?

---

## 9. AI-Generated Copy Governance

- Human review of every AI draft.
- Tone and terminology checked against the style guide.
- Accessibility and inclusivity validated.
- No publishing unreviewed AI output in user-facing UI.

---

## 10. Checklist

- [ ] Every piece of copy has one clear purpose.
- [ ] Buttons use verb + user outcome.
- [ ] Error messages say what, why, and how to fix.
- [ ] Empty states guide the user to the first action.
- [ ] Labels, placeholders, and helper text are not confused.
- [ ] Voice is consistent; tone matches the context.
- [ ] Language is plain, active, and inclusive.
- [ ] A style guide exists and is followed.
- [ ] Content is reviewed for accessibility.
- [ ] AI-generated copy is edited before shipping.
