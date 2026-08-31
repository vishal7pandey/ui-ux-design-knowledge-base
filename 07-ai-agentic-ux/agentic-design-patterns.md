# Agentic AI Design Patterns

## Why This Matters for UX/Product Designers

You don't need to implement these patterns as code to design well for them. Understanding how agentic systems are architected — where they can fail, where a human needs to step in, where latency/cost tradeoffs happen — directly informs where you need to design **checkpoints, review UIs, fallback states, and transparency mechanisms.** Every pattern below has a corresponding UX surface: a place where the system needs to communicate state, ask for input, or hand control back to a human.

Four foundational categories underlie most agentic behavior: **Reflection** (self-evaluation), **Tool Use** (calling external functions/APIs), **Planning** (breaking goals into steps), and **Multi-Agent Collaboration** (specialized agents working together, coordinated by a supervisor). The 20 patterns below expand on these foundations.

---

## 1. Prompt Chaining
Break a large task into smaller sequential steps, each validating the previous step's output before passing data forward — like an assembly line with quality checks at each station.

- **Diminishing returns exist.** A "magic number" of 3–5 chained steps is usually enough; beyond that, added context increases hallucination risk and cost without proportional benefit.
- **Context explosion** is the main failure mode — carrying all prior context forward to every step balloons token cost and confuses the model by step 6 or 7.
- **UX surface:** Log every intermediate artifact so failures can be traced to the exact step that went wrong — this is essential for building user trust in "why did this happen."
- **Good for:** document processing, multi-stage data cleaning, content creation pipelines.

## 2. Routing
Analyze an incoming request's intent and direct it to the right specialist agent/tool — like a smart receptionist directing you to the right department.

- If confidence is low, the system should **ask a clarifying question** rather than guess — this is the single most important UX safeguard for this pattern.
- **UX surface:** design the clarification prompt carefully; a bad clarification question is worse than no routing at all.
- **Good for:** customer service, healthcare triage, any system with genuinely distinct specialist paths.
- **Risk:** edge cases that don't fit any defined route — always design a "none of the above, escalate to human" path.

## 3. Parallelization
Split a large job into independent chunks processed simultaneously by multiple agents ("workers"), then merge results — like ten people each summarizing a different book chapter.

- Requires a **normalization step** before merging — outputs from different workers often come back in inconsistent formats and must be reconciled into one shape.
- **UX surface:** provide **provenance** — cite which worker/sub-task produced which part of the final output, so users (and you) can debug which specific piece failed.
- **Good for:** large-scale data processing, web scraping, research automation.

## 4. Reflection
The system generates output, then a **critic** (can be the same or a different model) evaluates it against quality standards, and the output is revised iteratively until it passes.

- Always set a **max retry count** — without one, a fundamentally flawed task can loop indefinitely.
- **UX surface:** if reflection fails after max retries, don't fail silently — surface *what specifically* didn't meet quality bar, and offer human review.
- **Good for:** content generation, anything where "creative but not chaotic" output quality matters (legal writing, product descriptions).
- **Cost warning:** reflection loops multiply API calls — budget and rate-limit carefully for high-volume use cases.

## 5. Tool Use
The agent discovers available tools, checks permissions, selects the right one, and executes it with proper parameters — like a chef checking the pantry before cooking.

- **Misfires compound.** If the wrong tool is chosen but the system doesn't catch it, every downstream step inherits that mistake (like an early arithmetic error propagating through a math problem).
- **UX surface:** always log which tool was selected and why — this is the single highest-value debugging signal for agentic failures.
- **Good for:** research assistants, data analysis, anything requiring live/external information beyond the model's training data.

## 6. Planning
Break a large ambiguous goal into a structured, ordered roadmap of milestones before execution — rather than attacking the problem in an unstructured way.

Four sub-steps: **task decomposition** → **strategic structuring** (ordering dependencies) → **efficient execution** (with progress monitoring) → **flexible adjustment** (replanning as new information emerges).

- More planning time up front generally produces more adaptable execution — this is directly analogous to good UX practice of "measure twice, cut once."
- **UX surface:** expose the plan itself to the user before execution begins on ambiguous, high-stakes, or expensive tasks — let them review/edit the plan, not just the final output.
- **Good for:** project management style workflows, software development tasks, research projects.

## 7. Multi-Agent Collaboration
Multiple specialized agents work on different parts of a complex task, coordinated by a central "manager"/orchestrator agent, often sharing a common memory store.

Sub-patterns:
- **Collaborative** — agents work as peers, sharing progress toward a unified result
- **Supervised** — a central supervisor assigns tasks and verifies outputs
- **Supervisor tool-calling** — the supervisor uses LLM-powered logic to decide which agent/tool to invoke and with what arguments

- **UX surface:** define clear "acceptance criteria" per sub-task (like tickets on a project board) so users can audit which agent did what and whether it met the bar.
- **Good for:** software/product development, financial analysis, content production, research requiring diverse expertise.
- **Practical advice:** think in terms of coarse-grained "microservices" — carve out standalone functionality that could be its own agent, then delegate via a supervisor, rather than building one monolithic mega-agent.

## 8. Memory Management
Classify incoming information into short-term (conversation), episodic (specific events), or long-term (persistent knowledge), storing each type with appropriate metadata (recency, relevance, topic tags).

- No single memory architecture works for all use cases — it's highly context-dependent on what's actually worth remembering.
- **UX surface:** give users visibility into and control over what the system remembers about them — this is both a trust issue and (in regulated contexts) a compliance requirement.
- **Good for:** conversational continuity, personalized experiences (customer service, education platforms that track a learner's specific weak spots).
- **Risk:** privacy/security — always design explicit redaction/deletion flows for sensitive stored memories.

## 9. Learning & Adaptation
Collect feedback (corrections, ratings, outcomes) from users, clean/validate it, then use it to update prompts, policies, examples, or (rarely) fine-tune a model.

- **You can learn the wrong thing.** A single loud, unrepresentative piece of negative feedback can bias the system if not filtered/validated first.
- **UX surface:** show users *that* their feedback changed something (closing the loop) — this materially increases willingness to give feedback in the future.
- **Good for:** any tailored/personalized service that improves with usage.
- **Cost warning:** every feedback-driven update round is itself often an LLM call — this compounds cost at scale.

## 10. Goal Setting & Monitoring
Define specific, measurable goals (often "SMART" goals) with deadlines/budgets, then continuously monitor progress against metrics — like a GPS that recalculates when you're off course.

- **UX surface:** when the system detects it's drifting from its KPIs, don't let it silently keep going — surface the drift and the proposed correction (more resources? adjusted scope?) for human sign-off on any advanced/high-stakes workflow.
- **Good for:** complex, long-running projects — sales pipelines, system optimization, cost management.
- **Risk:** goal conflicts and overly rigid constraints — test with genuinely messy, real-world inputs, not idealized ones.

## 11. Exception Handling & Recovery
Classify errors as **permanent** (won't resolve on retry — need a fallback path) vs. **temporary** (worth retrying, often with exponential backoff), with an emergency-response path for critical failures.

- **Alert fatigue is a real risk** — be judicious about what actually warrants a human alert, or trust erodes ("cried wolf" problem) and real alerts get ignored.
- **UX surface:** for critical failures, the system should be able to (1) save current work, (2) alert the right people, and (3) determine if it's safe to continue — all visibly, not silently.
- **Good for:** any production system — this pattern underlies reliability for nearly everything else on this list.

## 12. Human-in-the-Loop (HITL)
Insert an explicit review/approval checkpoint for medium-to-high-risk decisions, showing full context and giving the human the ability to approve, edit, deny, or take over.

- **UX surface — this is the most important pattern for designers specifically.** The review UI itself (what context is shown, how urgency is prioritized, how "take over" works) *is* the product experience for agentic tools in regulated or high-stakes domains.
- Best practice: show a **diff/context view**, not just a binary approve/reject — humans need to understand what they're approving, not just rubber-stamp it.
- **Good for:** regulatory compliance, medical/financial/legal decisions, anything where an error is costly or hard to reverse.
- **Trade-off:** every human-in-the-loop step adds latency — the system is only as fast as the human's response time. Design for this explicitly (async notifications, batched review queues) rather than assuming instant response.

## 13. Retrieval (RAG)
Index documents by parsing, chunking, and embedding them into a searchable vector store; at query time, retrieve the most relevant chunks (optionally reranked) to ground the model's answer in real source material.

- **Chunking strategy matters** — fixed-size, semantic-boundary, and context-aware chunking each have different tradeoffs; test against your actual content, don't assume one approach.
- **Top-K matters** — more retrieved matches gives the model more to potentially hallucinate from; don't just maximize retrieval count.
- **UX surface:** always surface citations alongside RAG-generated answers (see the inline-citation pattern in `ai-interface-patterns.md`) — this is non-negotiable for user trust in retrieval-grounded answers.
- **Good for:** enterprise search, customer support, research assistants, any documentation-heavy domain.

## 14. Inter-Agent Communication
Agents exchange structured messages with defined protocols — message IDs for tracking, expiration times, and security/identity checks — coordinated via a hierarchy (one boss), flat democracy (everyone has a say), or shared-board model (agents comment on a common thread).

- **This is the most complex, least production-proven pattern on this list.** Real-world deployments are rare — most current use is prototype/demo-level, not scaled production.
- **Fault isolation is the real payoff, if you can pull it off** — a well-instrumented multi-agent conversation lets you pinpoint exactly which agent caused a breakdown, which is harder to do with an equivalent human team.
- **UX surface:** if you build this, invest heavily in observability tooling (conversation state viewers, loop detectors) before investing in the agents' capabilities themselves.
- **Caution:** endless loops between agents are a real failure mode — always design a hard stop/timeout, and a human-alert path for stuck conversations.

## 15. Resource-Aware Optimization
Classify a task's complexity, then route it to the cheapest model/resource that can handle it adequately — simple tasks to fast/cheap models, complex tasks to slower/expensive ones.

- **UX surface:** this pattern is usually invisible to end users, but be transparent in developer-facing or enterprise tooling about *why* certain requests take longer or cost more — opacity here breeds distrust ("did they downgrade my request to save money?").
- **Good for:** cost-sensitive, high-volume, or budget-constrained systems at scale.
- **Risk:** a bad complexity classifier routes hard problems to weak models — invest real effort in the classification step, since it's the lever that determines quality/cost tradeoff for the entire system.

## 16. Reasoning Techniques
Choose the right internal reasoning method for the problem: **Chain of Thought** (linear, step-by-step), **Tree of Thought** (branch, explore, prune multiple solution paths), **self-consistency** (generate multiple solutions, score and pick the best), or **debate** (adversarial proponent/opponent agents argue toward a conclusion).

- This is an **advanced, high-token-cost category** — appropriate for genuinely hard problems (mathematical reasoning, strategic planning, legal/medical analysis), not general-purpose use.
- **Overthinking is real** — just as humans can overanalyze, models can too; more reasoning steps aren't free and don't always improve output quality.
- **UX surface:** for user-facing tools using these techniques, manage expectations around latency and cost — this is not a "make everything think harder" toggle to expose casually.

## 17. Evaluation & Monitoring
Define quality gates and golden test sets **before** deployment; continuously monitor accuracy, performance, cost, and **drift** (gradual degradation of the same model/pipeline over time) in production.

- **Drift detection matters as much as pre-launch testing** — a system that passed every test at launch can quietly degrade in production without anyone noticing, unless monitored continuously.
- **UX surface:** for internal/admin tooling, surface drift and regression alerts clearly — this is infrastructure most designers won't build UI for directly, but should know exists and advocate for.
- **Good for:** enterprise/SaaS, healthcare, finance — any domain where "it worked at launch" isn't a sufficient bar.

## 18. Guardrails & Safety
Check inputs for harmful content, PII, or injection attacks; classify risk level (low/medium/high) and apply proportional controls — sanitize, redact, block, or escalate to a human.

- **High-risk inputs should almost always route to human review**, not just be silently blocked or allowed.
- **UX surface — a major, often-overlooked design decision:** open-ended chat/text boxes are the highest-risk vector for malicious input. For high-volume, customer-facing products, consider **pre-scripted, click-through interaction flows** instead of open text boxes — this dramatically reduces injection risk at the cost of some flexibility.
- **Good for:** any public-facing, brand-sensitive, or regulated system.
- **Trade-off:** stricter guardrails add friction; balance safety against usability, but never at safety's expense for genuinely high-risk categories.

## 19. Prioritization
Score tasks by value, effort, urgency, and risk (e.g., `priority = value × effort × urgency × risk`), build a dependency graph, then dynamically re-rank as new information or environmental changes emerge — like an ER triage system.

- **Re-prioritization must be continuous, not one-time.** Executing the top task can itself create new information that should reshuffle the rest of the queue (a real-world delay might mean skipping a lower-priority step entirely).
- **UX surface:** show users *why* something was reprioritized, not just that the order changed — silent reordering feels arbitrary and erodes trust in the system's judgment.
- **Good for:** task/ticket management, customer service queues, manufacturing/devops pipelines, dynamic environments generally.

## 20. Exploration & Discovery
Broadly explore a knowledge space (papers, data, expert sources), cluster findings into themes, then use selection criteria (novelty, impact, feasibility, knowledge gaps) to decide where to focus deeper investigation.

- This is the pattern underlying most "deep research" agent products (e.g., agentic research assistants that spend many minutes autonomously investigating a topic before returning a report).
- **UX surface:** surface the exploration *process*, not just the final report — which sources were considered and rejected, and why, builds far more trust than a report that appears fully-formed with no visible working.
- **Good for:** academic/R&D research, competitive analysis, drug discovery, any open-ended investigative task.

---

## Pattern Selection Quick Reference

| If your problem is... | Consider this pattern |
|---|---|
| A big task with clear sequential stages | Prompt Chaining |
| Requests need to go to different specialists | Routing |
| A big task splits into independent chunks | Parallelization |
| Output quality/creativity needs iteration | Reflection |
| The agent needs live/external data | Tool Use |
| The goal is ambiguous and needs breaking down | Planning |
| The task needs genuinely diverse expertise | Multi-Agent Collaboration |
| The system needs to "remember" users over time | Memory Management |
| The system should improve from usage | Learning & Adaptation |
| Long-running work needs tracked KPIs | Goal Setting & Monitoring |
| Production reliability matters | Exception Handling & Recovery |
| Stakes are high or actions are hard to reverse | Human-in-the-Loop |
| Answers must be grounded in real documents | Retrieval (RAG) |
| Multiple agents genuinely need to negotiate/coordinate | Inter-Agent Communication |
| Cost/latency at scale is a real constraint | Resource-Aware Optimization |
| The problem is genuinely hard (math, strategy, law) | Reasoning Techniques |
| You need confidence the system stays correct over time | Evaluation & Monitoring |
| Inputs are open-ended and public-facing | Guardrails & Safety |
| Many competing tasks need dynamic ordering | Prioritization |
| The goal is open-ended investigation, not a fixed task | Exploration & Discovery |

## Designer's Checklist for Any Agentic Feature

- [ ] Where does the human need a review/approval checkpoint (HITL), and what does that screen show?
- [ ] What happens when the agent is uncertain — does it ask, or guess?
- [ ] Is there a visible trace of *why* the agent did what it did (transparency)?
- [ ] What's the fallback when a tool call or sub-agent fails?
- [ ] Can the user see and correct what the system has "learned" about them?
- [ ] Is there a hard stop/timeout for any loop-capable pattern (reflection, multi-agent chat)?
- [ ] For open text input, has injection/misuse risk been considered?
- [ ] Does reprioritization or drift get surfaced to the user, or does it happen silently?
