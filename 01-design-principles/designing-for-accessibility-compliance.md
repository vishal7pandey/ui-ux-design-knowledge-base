# Designing for Accessibility Compliance

Accessibility compliance means meeting recognized standards so that people with disabilities can use the product. The most common standard is WCAG. Compliance is the floor, not the ceiling.

---

## 1. Common Standards

| Standard | Region / Use |
|----------|--------------|
| **WCAG 2.2** | Global web standard. |
| **Section 508** | US federal requirements. |
| **ADA** | US anti-discrimination law. |
| **EN 301 549** | European standard. |
| **AODA** | Canadian accessibility law. |

Most teams aim for WCAG 2.2 Level AA as a baseline.

---

## 2. WCAG 2.2 Levels

### Level A

- Minimum requirements.
- For example: text alternatives, keyboard access, captions.

### Level AA

- Common standard for most products.
- For example: contrast 4.5:1, resizable text, consistent navigation.

### Level AAA

- Highest level.
- Not always practical for all content.
- For example: 7:1 contrast, sign language for media.

---

## 3. POUR Principles

WCAG is organized around four principles:

### Perceivable

Users can perceive the information.

- Text alternatives for images.
- Captions and transcripts.
- Sufficient contrast.
- Resizable text.

### Operable

Users can operate the interface.

- Keyboard access.
- Enough time.
- No seizures.
- Clear navigation.

### Understandable

Users can understand the information and UI.

- Readable text.
- Predictable behavior.
- Help with errors.

### Robust

Content works with current and future assistive technology.

- Valid code.
- Correct ARIA.
- Cross-browser compatibility.

---

## 4. Compliance by Design Phase

### Discovery

- Include disabled users in research.
- Identify accessibility requirements early.
- Review legal and policy requirements.

### Design

- Use sufficient color contrast.
- Design for keyboard and screen readers.
- Make interactive elements large enough.
- Use semantic components.

### Development

- Use semantic HTML.
- Add ARIA only when needed.
- Ensure keyboard and focus support.
- Test with assistive technology.

### QA

- Run automated and manual tests.
- Test with keyboard and screen readers.
- Audit before release.
- Retest after changes.

---

## 5. Key Compliance Targets

| Area | Target |
|------|--------|
| **Text contrast** | 4.5:1 for body, 3:1 for large text. |
| **UI contrast** | 3:1 for interactive elements and icons. |
| **Touch target** | At least 44×44 CSS pixels. |
| **Focus** | Visible and logical. |
| **Text resize** | Works up to 200%. |
| **Keyboard** | All functionality available. |
| **Alt text** | Meaningful alternatives for images. |
| **Forms** | Labels, errors, and instructions. |
| **Motion** | Honor `prefers-reduced-motion`. |

---

## 6. Documentation and Evidence

- Keep a VPAT (Voluntary Product Accessibility Template) or ACR (Accessibility Conformance Report).
- Document known limitations and workarounds.
- Record testing methods and results.
- Track remediation over time.

---

## 7. Common Mistakes

- Treating accessibility as a final checkbox.
- Relying on automated tools alone.
- Not involving disabled users in research.
- Insufficient color contrast.
- Missing keyboard support.
- Overuse or misuse of ARIA.
- Not testing across devices and assistive tech.
- No documentation or evidence of compliance.

---

## 8. Checklist

- [ ] WCAG 2.2 AA is the target.
- [ ] Legal and policy requirements are known.
- [ ] Disabled users are included in research.
- [ ] Contrast, focus, and keyboard are designed in.
- [ ] Semantic HTML and correct ARIA are used.
- [ ] Automated and manual testing is performed.
- [ ] Screen-reader and keyboard tests pass.
- [ ] Touch targets meet minimum sizes.
- [ ] Text resizes without breaking.
- [ ] Reduced motion is supported.
- [ ] Compliance evidence is documented.
- [ ] Accessibility is tested continuously, not once.
