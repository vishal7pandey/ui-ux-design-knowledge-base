# Agent UX Patterns Catalog

This catalog captures the established, production-proven surface patterns for human-agent collaboration. It complements the more foundational `agentic-experience-design.md` and `ai-interface-patterns.md` with concrete UX recipes: how to handle streaming, artifact panels, approval, undo, long-running tasks, and multi-agent interfaces.

---

## 1. Why Agent UX Is Different

Five characteristics make agent UX unlike traditional software UX:

| Characteristic | What it means for the interface |
|----------------|---------------------------------|
| **Nondeterminism** | The same input can produce different outputs. Surface confidence, alternatives, and uncertainty instead of pretending output is authoritative. |
| **Latency** | Agent responses take 1–60+ seconds. The wait is part of the UX; fill it with progress and intermediate state. |
| **Decision-making** | Agents choose tools, sources, and phrasing. Make those decisions visible when it matters. |
| **Fallibility** | Agents can be confidently wrong. Design for correction, undo, and graceful degradation. |
| **Agency** | Agents act across systems on the user’s behalf. Communicate boundaries: what it can do, what it has done, and what it intends to do. |

---

## 2. The Chat-Is-Not-Always-UI Rule

Chat is the right interface for:

- Open-ended questions
- Brainstorming and ideation
- Iterative text refinement
- Quick lookups
- Exploratory Q&A

Chat is the **wrong** interface for:

- Tabular data and comparisons
- Maps, diagrams, spatial information
- Forms and structured editing
- Persistent artifacts (documents, code, dashboards)
- Multi-step workflows with parallel state
- Code with file-tree structure

> **Design principle (2025/2026)**: Choose the interface shape from the **task**, not from the chat default.

---

## 3. Core Agent UX Patterns

### 3.1 Token Streaming

**Intent**: Reduce perceived latency by displaying response tokens as they are generated.

**When to use**: Essentially all user-facing agent interfaces. Non-streaming responses feel broken.

**Best practices**:

- Stream at token or word level, debounced to avoid jitter.
- Apply markdown formatting progressively with a streaming-aware renderer.
- Handle mid-stream errors gracefully.
- Allow cancellation with a stop button.

**Example (React/Vercel AI SDK)**:

```tsx
import { useChat } from 'ai/react';

function Chat() {
  const { messages, input, handleInputChange, handleSubmit } = useChat({
    api: '/api/chat',
  });

  return (
    <div>
      {messages.map(m => (
        <div key={m.id} className={m.role}>
          {m.content}
        </div>
      ))}
      <form onSubmit={handleSubmit}>
        <input value={input} onChange={handleInputChange} />
        <button type="submit">Send</button>
      </form>
    </div>
  );
}
```

---

### 3.2 Intermediate State Display

**Intent**: Show what the agent is doing during the response: thinking, tool calls, retrieval, plan execution.

**When to use**: Coding agents, research agents, complex multi-step agents, high-stakes agents.

**Patterns**:

- **Thinking blocks**: collapsed by default, visually distinct (e.g., “Reasoning” or “Thinking”).
- **Tool call cards**: which tool, with what arguments, and the result.
- **Retrieved sources**: cards with titles, snippets, and relevance scores.
- **Plan display**: sequence of intended steps, user-editable.

**Guideline**: Use progressive disclosure — final answer first, reasoning on demand, full trace for power users.

---

### 3.3 Generative UI / Artifact Panels

**Intent**: Display substantial work artifacts (documents, code, tables, dashboards) in a persistent, structured surface alongside the conversation.

**When to use**: Generated content the user wants to iterate on, copy, or edit.

**Leading implementations**:

- **Anthropic Artifacts**: side panel for documents, code, interactive HTML.
- **OpenAI Canvas**: similar pattern with inline editing affordances.
- **Vercel AI SDK generative UI**: agent streams React components directly into the UI.

**Design guidance**:

- Trigger artifacts when content is substantial (long docs, code > 20 lines, structured data, interactive demos).
- Keep the chat in a narrow column on the left; the artifact on the right.
- Provide preview / source / edit / copy / download affordances.
- Allow the user to edit the artifact directly or through chat.

---

### 3.4 Pre-Action Approval

**Intent**: Let users review what the agent intends to do before it does it.

**When to use**: Sending external emails, modifying important data, purchases, deletions, any irreversible or high-blast-radius action.

**Patterns**:

- **Pre-action confirmation**: describe the action in concrete detail, with confirm/modify/cancel.
- **Batched approval**: review N proposed actions together (e.g., multi-file diff in Cursor).
- **Progressive trust**: auto-approve patterns the user has approved before; new patterns trigger approval.
- **Risk-scaled approval**: classify actions by sensitivity and surface the classification.

---

### 3.5 Undo-First Design

**Intent**: Let the agent act fast and provide a clear rollback path, rather than gate every action.

**When to use**: Reversible, high-frequency, low-stakes operations.

**Patterns**:

- **Snapshot-and-restore**: capture state before edit; user can restore.
- **Soft delete with grace period**: item appears removed but recoverable.
- **Action history with selective revert**: undo any past action, not just the latest.

> **Combined rule of thumb**: approval for irreversible, undo for reversible, resume for long-running.

---

### 3.6 Long-Running Task UX

**Intent**: Keep the user informed without forcing them to wait in place.

**When to use**: Tasks taking more than 10–20 seconds.

**Patterns**:

- **Step-level status**: “Planning → Searching → Analyzing → Writing.”
- **Activity feed**: real-time tool calls and retrievals.
- **Progress estimates**: “Step 3 of 5, ~2 minutes left.”
- **Streaming partial results**: show completed files or findings as they arrive.
- **Background mode**: let the user navigate away; notify on completion.

---

## 4. Progressive Disclosure: The Core Transparency Trade-Off

**The tension**: Hide everything and users can’t trust or debug. Show everything and cognitive load explodes.

**Default architecture**:

```
┌─────────────────────────────────────┐
│  Summary / final answer (always)    │
├─────────────────────────────────────┤
│  Reasoning & sources (one click)    │
├─────────────────────────────────────┤
│  Full trace / debug view (power)    │
└─────────────────────────────────────┘
```

**Examples**:

- Coding agent: summary = proposed code; on-demand = explanation; trace = tool calls.
- Research agent: summary = synthesized answer; on-demand = sources with relevance; trace = search queries and reranking.
- Customer service: summary = response to customer; on-demand = policy and history; trace = full reasoning chain.

---

## 5. Human-in-the-Loop & Human-on-the-Loop Patterns

### Human-in-the-Loop (HITL)

Human judgment at critical decision points. Use when a wrong decision is costly, irreversible, or ethically sensitive.

### Human-on-the-Loop (HOTL)

Human monitors an autonomous process and can intervene, pause, or take control. Use when the agent operates mostly autonomously but oversight is required.

### Approval Queues & Escalation Chains

First-class approval as an operational workflow:

- **Reversible** actions → auto-approve.
- **Medium-risk** → asynchronous review queue; agent continues other work and resumes.
- **Irreversible** → synchronous approval before execution.
- **Escalation** triggers: confidence breach, irreversibility flag, SLA-approach, anomaly/injection detection.

---

## 6. Trust & Transparency Patterns

| Pattern | Purpose |
|---------|---------|
| **Confidence indicators** | Show how certain the agent is about a prediction or answer. |
| **Citations** | Link specific claims to sources. |
| **Source attribution** | Show which data was used. |
| **Capability display** | “I can read your email but not your bank.” |
| **Action preview** | “I’m about to send this email to these three people.” |
| **Agent activity trail** | Log of actions the agent has taken. |
| **Permission boundaries** | Visual limits on what the agent is authorized to do. |

---

## 7. Multi-Agent UX Patterns

When several agents work in parallel, the chat UI breaks down. Use one or more of:

- **Agent dashboard**: small list of active agents with status and recent activity (2–5 agents).
- **Graph visualization**: nodes = agents; edges = messages or delegations.
- **Swim lanes**: time-based parallel work streams.
- **Aggregate progress**: overall state when individual visibility would overwhelm.
- **Intervention surfaces**: per-agent pause, cancel, message, override.
- **Audit and replay**: scroll back, replay from checkpoint, inspect message flows.

**When to expose multi-agent internals**:

- Initial deployments: hide multi-agent nature, treat as one assistant.
- As users need trust or debugging: expose the dashboard or graph.
- Developer/ops tools: show full traces and replay.

---

## 8. Cross-Cutting Agent UX Checklist

- [ ] The interface shape matches the task, not the chat default.
- [ ] Users see what the agent is doing during latency (streaming, thinking, tool calls).
- [ ] Final answers are first-class; reasoning is available on demand.
- [ ] Persistent artifacts have their own surface (panel, canvas, generated UI).
- [ ] Irreversible actions require approval; reversible actions allow undo.
- [ ] Long-running tasks have status, partial results, and background/resume support.
- [ ] Multi-agent systems have visibility and intervention surfaces.
- [ ] Confidence, sources, and capabilities are surfaced for trust.
- [ ] Errors are specific (model, tool, refusal, hallucination) with recovery paths.
- [ ] Graceful degradation: partial failures still produce useful output.
- [ ] Consistent UI/UX elements used where possible to reduce cognitive load.
