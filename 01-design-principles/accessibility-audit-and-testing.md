# Accessibility Audit and Testing

Accessibility audits and testing catch barriers before users do. A mix of automated, manual, and assistive-technology testing gives the most reliable picture.

---

## 1. Types of Accessibility Testing

### Automated testing

- Use tools to scan for common issues.
- Fast and scalable.
- Catches ~30% of issues.
- Tools: Axe, WAVE, Lighthouse, Pa11y.

### Manual testing

- Human review of keyboard, focus, color, and interaction.
- Needed for nuanced issues automated tools miss.

### Screen-reader testing

- Test with NVDA, JAWS, VoiceOver, or TalkBack.
- Verify reading order, headings, labels, and ARIA.

### Keyboard testing

- Navigate the entire interface with only the keyboard.
- Check focus order, visible focus, and keyboard traps.

### User testing with disabled users

- The most valuable form of testing.
- Catches real-world issues tools cannot find.
- Include users with diverse disabilities.

---

## 2. What to Test

### Perceivable

- Text alternatives for images.
- Captions and transcripts for media.
- Color contrast.
- Resize text without breaking layout.

### Operable

- Keyboard access.
- Focus order and visibility.
- Enough time to read and use content.
- No seizures or physical reactions from flashing.

### Understandable

- Readable text.
- Predictable navigation.
- Clear error messages.
- Input assistance and labels.

### Robust

- Valid HTML.
- ARIA used correctly.
- Works with assistive technology.
- Compatible across browsers and devices.

---

## 3. Automated Checks

| Issue | Tool example |
|-------|--------------|
| Missing alt text | Axe, WAVE |
| Low contrast | Axe, Lighthouse |
| Missing form labels | Axe, Pa11y |
| Empty headings | WAVE |
| Missing language attribute | Axe, HTML validator |
| Broken ARIA | Axe, ARC Toolkit |

---

## 4. Manual Checks

- Can you reach everything with a keyboard?
- Is the focus order logical?
- Can you see focus at all times?
- Does the tab order match the visual order?
- Are headings used semantically?
- Are links and buttons descriptive?
- Is color alone used for meaning?
- Does text scale up to 200% without loss?

---

## 5. Screen-Reader Checks

- Are landmarks and headings navigable?
- Are buttons and links announced clearly?
- Is form feedback announced?
- Are dynamic updates announced with `aria-live`?
- Are images and icons labeled?
- Is the reading order logical?

---

## 6. Testing Process

1. **Automated scan** for baseline issues.
2. **Manual keyboard and visual review.**
3. **Screen-reader test** of key flows.
4. **User testing** with people with disabilities.
5. **Document findings** and prioritize.
6. **Fix and retest.**

---

## 7. Audit Report Structure

1. **Scope**: what was tested.
2. **Standards**: WCAG 2.2 AA or other.
3. **Method**: automated, manual, assistive tech.
4. **Findings**: list of issues with severity.
5. **Recommendations**: how to fix.
6. **Priorities**: what to fix first.
7. **Next steps**: retest and ongoing plan.

---

## 8. Common Mistakes

- Relying only on automated tools.
- Not testing with real users.
- Skipping keyboard testing.
- Ignoring mobile accessibility.
- Testing only one screen reader.
- Not testing color contrast in dark mode.
- Treating accessibility as a one-time audit.

---

## 9. Checklist

- [ ] Automated scans are run regularly.
- [ ] Keyboard navigation is tested.
- [ ] Focus order and visibility are verified.
- [ ] Screen readers are tested on key flows.
- [ ] Color contrast passes WCAG 2.2 AA.
- [ ] Images and icons have accessible labels.
- [ ] Forms have proper labels and error feedback.
- [ ] Dynamic content is announced.
- [ ] Real users with disabilities are included in testing.
- [ ] Audit findings are tracked and prioritized.
- [ ] Retesting is scheduled after fixes.
