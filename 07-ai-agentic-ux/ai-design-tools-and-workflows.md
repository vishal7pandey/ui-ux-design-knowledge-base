# AI Design Tools and Workflows

This guide captures the current landscape of AI-powered design tools and how to integrate them into a productive, human-centered workflow. It complements the existing `ai-for-designers.md` with practical tool comparisons and workflow patterns.

---

## 1. The New Design-to-Code Pipeline

AI has changed the handoff between design and development. A modern workflow often looks like:

```
Prompt / Sketch / Wireframe
        ↓
AI-generated concept (Figma, v0, tldraw)
        ↓
Designer refinement and UX validation
        ↓
AI-assisted code generation (v0, Figma Dev Mode, Cursor)
        ↓
Engineer review and production hardening
        ↓
Ship and iterate
```

The designer’s role is shifting from pixel-perfect production to direction, critique, and validation.

---

## 2. Major Tools

### 2.1 Figma AI

**Strengths**:

- Native to the industry-standard design tool.
- Generates options on the canvas using real components, tokens, and variables.
- Auto layer renaming, content generation, background removal, and translation.
- AI Design Agent that runs multi-step tasks on the canvas.
- Figma MCP server feeds design context into agentic coding tools.

**Best for**: Teams already working in Figma who want AI without switching tools.

**Limitations**: Less useful for generating production code directly.

---

### 2.2 v0.dev (Vercel)

**Strengths**:

- Text-to-UI for production-ready React / Next.js / Tailwind / shadcn/ui components.
- Conversational iteration and one-click deploy.
- Strong for developers and component-minded designers.

**Best for**: Fast wireframe-to-frontend workflows, proof of concepts, internal tools.

**Limitations**: Locked into the Vercel / React / shadcn ecosystem; less design-control than Figma.

---

### 2.3 tldraw

**Strengths**:

- Open-source infinite canvas.
- “Make Real” feature turns hand-drawn wireframes into functional, code-based prototypes.
- Free and extensible.

**Best for**: Quick ideation, sketch-to-prototype, hackathons, experimentation.

**Limitations**: More of a tech demo than a full design suite.

---

### 2.4 Galileo AI

**Strengths**:

- Prompt-to-high-fidelity design.
- Generates entire design systems.
- Exports layered Figma files.

**Best for**: Rapid exploration and full-screen design generation.

---

### 2.5 Uizard

**Strengths**:

- Sketch-to-UI: draw on paper, scan, and convert to editable UI.
- Screenshot-to-UI: clone an existing app from a screenshot.
- Generates clickable prototypes.

**Best for**: Low-fidelity ideation, rapid concepting, non-designers.

---

## 3. Where Each Tool Fits

| Stage | Tool | Output |
|-------|------|--------|
| Ideation / sketch | tldraw, Uizard | Concept wireframes |
| High-fidelity design | Figma AI, Galileo AI | Editable design files |
| Design refinement | Figma | Production-ready designs |
| Code generation | v0, Figma Dev Mode, agentic coders | React / HTML / CSS |
| Handoff | Figma, Figma MCP, GitHub | Specs, assets, code |

---

## 4. Practical Workflows

### 4.1 Rapid landing page

1. Prompt Galileo or Figma AI for a hero + features + pricing page.
2. Refine in Figma using the design system.
3. Generate code with v0 or hand off to engineering.

### 4.2 Component ideation

1. Sketch a card, button, or table in tldraw or paper and scan with Uizard.
2. Drop into Figma for refinement.
3. Propose or add to the design system.

### 4.3 Design-to-code

1. Figma AI generates layout and content from a prompt.
2. Figma MCP server sends context to Cursor / VS Code / Claude.
3. Agentic coder produces React components using design tokens.
4. Designer reviews and tests the result.

### 4.4 Bulk edits and consistency

1. Use Figma AI Agent to rename layers, apply tokens, and audit usage.
2. Review changes before accepting.
3. Publish updated components.

---

## 5. Best Practices

1. **AI is a collaborator, not a replacement**. Designers must validate UX, accessibility, and brand fit.
2. **Start with your design system**. Point AI tools at your tokens, components, and variables.
3. **Generate options, not answers**. Use AI to explore, then converge on the best solution.
4. **Iterate conversationally**. Refine prompts, not just outputs.
5. **Keep humans in the loop** for high-stakes, user-facing, or accessible work.
6. **Version your experiments**. AI output is cheap; losing the best iteration is not.

---

## 6. Risks and Limitations

- **Hallucination**: AI may invent components, tokens, or interactions that do not exist.
- **Generic output**: AI-generated designs can look samey without strong design direction.
- **Accessibility gaps**: generated code often fails contrast, focus, or screen-reader checks.
- **Design-system drift**: generated work may not respect existing tokens or patterns.
- **Over-reliance**: teams may skip UX thinking and ship bad patterns faster.

---

## 7. The Designer’s New Role

| Old focus | New focus |
|-----------|-----------|
| Producing every screen | Directing and curating AI output |
| Manual alignment | Prompt engineering and component libraries |
| Pixel-perfect mockups | Interaction, logic, and edge-case validation |
| Static handoff | Living design-to-code pipelines |
| Sole ownership | Collaboration with AI and engineering agents |

---

## 8. Checklist

- [ ] AI tool is chosen for the right stage (ideation, design, or code).
- [ ] Design system tokens and components are loaded into the AI context.
- [ ] Generated output is reviewed for UX, brand, and accessibility.
- [ ] Edge cases and error states are designed, not just the happy path.
- [ ] Engineers can trace generated code back to design decisions.
- [ ] Versioning and handoff are documented.
