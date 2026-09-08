# Multi-Agent UX: Collaboration Surfaces

This guide focuses on the human-facing surfaces of multi-agent systems: how to make parallel agent activity legible, trustworthy, and controllable.

---

## 1. When Multi-Agent Becomes a UX Problem

A single agent can usually be understood through a conversational or task-focused surface. Multiple agents working together introduce:

- **Parallel activity**: several things happen at once.
- **Hidden coordination**: agents call, delegate, and update each other.
- **Blurred accountability**: users do not know which agent did what.
- **Scaling noise**: the more agents, the harder it is to show meaningful state.

When users need to trust, monitor, or intervene in multi-agent work, the interface must explicitly visualize the system.

---

## 2. Legibility First: Identity, Intent, Boundaries, Recovery

For any system that acts on the user’s behalf, expose four things:

| Concern | What to show |
|---------|--------------|
| **Identity legibility** | Which agent (or human) performed an action. |
| **Intent visibility** | What the agent believed it was authorized to do. |
| **Bounded delegation** | The limits of the agent’s authority. |
| **Intervention & recovery** | How to pause, override, or roll back. |

---

## 3. Collaboration Surface Patterns

### 3.1 Agent Dashboard

A panel listing active agents with current state, recent activity, and pending tasks.

**Best for**: 2–5 agents, each with a clear identity from the user’s perspective.

**Elements**:

- Agent name, avatar, or icon
- Current status (idle, working, waiting, error)
- Short description of the current task
- Time / progress estimate
- Pause, cancel, message buttons
- Recent output preview

**Avoid**: cluttering the dashboard with more than five distinct identities.

---

### 3.2 Graph Visualization

Agents and interactions rendered as a graph: nodes are agents; edges are messages or delegations.

**Best for**: debugging, developer tools, and complex coordination patterns.

**Design guidance**:

- Use color or shape to distinguish agent roles (planner, executor, verifier, retriever).
- Animate or pulse edges when messages are active.
- Make nodes clickable to inspect agent state.
- Provide zoom and filter controls.

---

### 3.3 Swim Lanes

Horizontal lanes with time flowing left to right; each lane is an agent or sub-task.

**Best for**: temporal coordination and post-hoc review.

**Design guidance**:

- Use consistent lane colors by agent role.
- Mark key events (delegation, result, handoff) with icons.
- Allow zoom from minute-level to hour-level.
- Combine with replay for debugging.

---

### 3.4 Aggregate Progress View

When there are many similar agents, show summary counts instead of per-agent detail.

**Best for**: parallel processing, batch work, large multi-agent workflows.

**Example**:

```
12 agents running
  5 complete
  4 in progress
  3 pending
  0 failed
```

**Design guidance**:

- Surface the most important exception (first failure, slowest agent).
- Let users expand an aggregate card for per-agent detail.
- Use progress bars when step counts are known.

---

### 3.5 Agent Handoff Cards

When one agent passes work to another, show the handoff explicitly.

**Elements**:

- From / to agent names
- What was transferred
- Status: pending, in-progress, complete, failed
- Timestamp
- User override option

**Where to use**: multi-step pipelines, customer service triage, research → writer → reviewer flows.

---

### 3.6 Mission Control / Operator Console

A centralized monitoring surface for oversight, intervention, and governance.

**Best for**: enterprise deployments, high-stakes domains, operations centers.

**Elements**:

- Real-time status of all agents and workflows
- Alerts and anomalies
- Approval queues
- Audit log
- Kill switches, pause-all, rollback
- Cost / token usage metrics
- Compliance or policy status

---

### 3.7 Context Preservation Surface

When agents hand off to each other, users should not lose context.

**Patterns**:

- **Shared context panel**: persistent summary visible to all agents in a session.
- **Handoff notes**: brief explanation of what the previous agent learned.
- **Resume-from-checkpoint**: continue a workflow from any prior step.
- **Session links**: shareable URLs so another user can continue the work.

---

## 4. Intervention Design

Users need clear, safe ways to act on a multi-agent system.

| Intervention | When to allow |
|--------------|---------------|
| **Pause one agent** | When a single agent is stuck or off track. |
| **Cancel one agent** | When one task is no longer needed. |
| **Pause all agents** | When the whole workflow needs review. |
| **Message an agent** | To redirect or add constraints. |
| **Override a decision** | When the user disagrees with an agent’s plan. |
| **Add / remove an agent** | When the workflow needs more or fewer capabilities. |
| **Rollback to checkpoint** | When an error is detected after the fact. |

> **Guideline**: Intervention should be as easy as the task is important. High-stakes workflows should have one-click pause and rollback.

---

## 5. Designing for Accountability

### Attribution labels

Every output or action should show who produced it:

- `Drafted by WritingAgent`
- `Verified by CriticAgent`
- `Approved by you`
- `Sent by EmailAgent on your behalf`

### Decision logs

Maintain a human-readable timeline of:

- What was decided
- Who (or what) decided it
- Which data or policy was used
- When it happened
- How to reverse it

### Policy visibility

If agents are governed by rules or policies, surface the relevant ones:

- “This action complies with data-retention policy X.”
- “PrivacyAgent blocked this export because it contains PII.”

---

## 6. Common Multi-Agent UX Mistakes

1. **Exposing the multi-agent architecture before users need it.** Start with a single coherent assistant; add dashboard/graph as trust and complexity require.
2. **Showing every message between agents.** Users need outcomes, not chat logs.
3. **No pause or rollback.** If agents can take consequential actions, users must be able to stop or undo.
4. **Ambiguous accountability.** Users should always know which agent did what.
5. **Forcing all interactions through chat.** Complex multi-agent work often needs a dashboard, canvas, or console.
6. **Ignoring the operator experience.** For production deployments, someone needs a mission-control view.

---

## 7. Multi-Agent UX Checklist

- [ ] Agent identities are clear and consistent.
- [ ] Users can see current state without opening a chat log.
- [ ] Handoffs are visible and explained.
- [ ] Users can pause, cancel, or override individual agents and the whole system.
- [ ] Rollback / replay is available for post-hoc debugging.
- [ ] Outputs are attributed to the responsible agent.
- [ ] Policy and safety boundaries are surfaced.
- [ ] Context is preserved across agent transitions.
- [ ] The right surface (dashboard, graph, swim lanes, console) is chosen for the task.
- [ ] Aggregate views scale to many agents; detail views are one click away.
