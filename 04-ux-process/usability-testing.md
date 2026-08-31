# Usability Testing

## What Is Usability Testing?

Usability testing is a method of evaluating a product by testing it with real users. You watch them attempt to complete tasks to identify usability problems and gather feedback.

## Why Test?

- **You are not your user** — what seems obvious to you may confuse users
- **Catch problems early** — fixing a design is cheaper than fixing code
- **Validate decisions** — confirm your design works before shipping
- **Build empathy** — see real people struggle with your product

## The "5 Users" Rule

> Testing with 5 users reveals 85% of usability problems. After 5, you hit diminishing returns.

| Users | Problems Found |
|---|---|
| 1 | 33% |
| 3 | 67% |
| 5 | 85% |
| 10 | 95% |

Test with 5 users per round. Fix issues. Test again with 5 new users.

## Types of Usability Testing

### Moderated (In-Person or Remote)
- Researcher present, guides the session
- Can probe and ask follow-up questions
- Richer insights, body language visible
- Slower, more expensive

### Unmoderated (Remote)
- User completes tasks on their own
- Screen + audio recorded automatically
- Faster, cheaper, more participants
- Can't ask follow-up questions in real-time

### Guerrilla Testing
- Test with random people (coffee shop, library)
- Quick, free, informal
- Good for early-stage validation
- Participants may not match your target audience

### A/B Testing
- Compare two versions with real users in production
- Quantitative — which version performs better?
- Need significant traffic for statistical significance
- Good for optimization, not discovery

## Planning a Usability Test

### 1. Define Research Questions
What do you want to learn? Be specific.
- ✅ "Can users complete checkout in under 2 minutes?"
- ✅ "Where do users get stuck in the onboarding flow?"
- ❌ "Is the design good?"

### 2. Define Tasks
Write tasks that are **realistic** and **action-oriented**.

#### Good Tasks
- "Find a blue sweater under $50 and add it to your cart."
- "You want to change your password. Show me how you'd do that."
- "Find the report for last month's sales."

#### Bad Tasks
- "Click the settings button." (Too leading — tells them what to do)
- "Navigate to the checkout page." (Uses your internal language)
- "Do you think this is easy to use?" (Opinion, not behavior)

#### Task Types
| Type | Example | When to Use |
|---|---|---|
| **Direct** | "Change your profile picture." | Specific feature testing |
| **Scenario** | "You just got a new phone. Set up your account." | Flow testing |
| **Exploratory** | "Look around the homepage. What catches your eye?" | First impressions |

### 3. Create a Test Script
```
1. Introduction (5 min)
   - Thank them for participating
   - Explain the purpose
   - "There are no wrong answers — we're testing the product, not you"
   - Get consent for recording

2. Background questions (5 min)
   - What do you do?
   - How often do you use [type of product]?
   - Have you used [competitor] before?

3. Tasks (20-30 min)
   - Give one task at a time
   - Ask them to think aloud
   - Don't help — observe
   - Note where they struggle

4. Post-test questions (5 min)
   - What was the easiest part?
   - What was the hardest part?
   - What would you change?
   - Rate difficulty: 1 (very easy) to 7 (very difficult)

5. Thank them
```

### 4. Recruit Participants
- Match your target audience (not your colleagues)
- 5 participants per round
- Offer incentive ($20-50 gift card, 30-60 min session)
- Use recruiting tools or your existing users

## Conducting the Test

### Before
- Test your prototype/app (make sure it works)
- Test your recording setup
- Have your script ready
- Prepare note-taking template

### During
- **Be neutral** — don't react to their actions
- **Don't help** — even if they're struggling, let them try
- **Ask "what are you thinking?"** — if they go quiet
- **Ask "what would you expect to happen?"** — before they click
- **Take notes** — quotes, timestamps, pain points
- **Record** — with permission, for later analysis

### After
- Thank them
- Ask final impressions
- Give incentive
- Debrief with your team immediately while it's fresh

## What to Measure

### Quantitative Metrics
| Metric | What It Measures |
|---|---|
| **Task success rate** | % of users who completed the task |
| **Time on task** | How long it took to complete |
| **Error rate** | Number of errors per task |
| **Clicks to complete** | Number of clicks needed |
| **SUS score** | System Usability Scale (0-100) |
| **Satisfaction rating** | Self-reported ease of use (1-7) |

### Qualitative Observations
| What to Watch | What It Means |
|---|---|
| Hesitation / pausing | User is confused or unsure |
| Back button usage | User took a wrong path |
| Scanning up and down | Looking for something |
| Re-reading text | Instructions unclear |
| Wrong clicks | Misleading UI |
| Verbal frustration | "This is confusing" |
| Workarounds | UI doesn't support their mental model |

## Analyzing Results

### 1. Compile Notes
- List all observations per task
- Tag each: 🟢 no issue, 🟡 minor issue, 🔴 major issue

### 2. Identify Patterns
- Did multiple users struggle at the same point?
- Did users use unexpected workarounds?
- Were any tasks universally easy?

### 3. Prioritize Issues
| Severity | Criteria | Action |
|---|---|---|
| **Critical** | Blocks task completion | Fix before launch |
| **High** | Significant difficulty, workaround needed | Fix before launch |
| **Medium** | Minor difficulty, task still completed | Fix in next iteration |
| **Low** | Cosmetic, slight confusion | Fix when time permits |

### 4. Write Recommendations
- Be specific: "Move the CTA above the fold" not "Make it better"
- Include screenshots/quotes as evidence
- Tie back to research questions

## Common Usability Issues

| Issue | Symptom | Fix |
|---|---|---|
| Hidden navigation | Users can't find pages | Make nav visible, use common patterns |
| Unclear CTAs | Users don't know what to do next | Use clear, action-oriented button labels |
| Too much text | Users skim and miss info | Break up text, use visual hierarchy |
| Unexpected behavior | Users surprised by results | Follow conventions, provide feedback |
| No search | Users can't find specific content | Add search functionality |
| Tiny touch targets | Users tap wrong thing | Increase to 44×44px minimum |
| No feedback | Users don't know if action worked | Add loading states, toasts, confirmations |
| Complex forms | Users abandon | Reduce fields, use multi-step, inline validation |

## Remote Testing Tools

| Tool | Type | Best For |
|---|---|---|
| **UserTesting** | Moderated + unmoderated | Professional panel, comprehensive |
| **Maze** | Unmoderated | Figma prototype testing |
| **Lookback** | Moderated + unmoderated | In-person and remote |
| **UsabilityHub** | Unmoderated | Quick tests (5-second, click test) |
| **Hotjar** | Analytics | Session recordings, heatmaps |
| **FullStory** | Analytics | Session recordings, funnels |
| **Google Meet / Zoom** | Moderated | Free remote testing |

## Tips

1. **Test early, test often** — test wireframes, not just finished designs
2. **You're testing the design, not the user** — make them feel comfortable
3. **Silence is golden** — when they're struggling, don't jump in. That's the finding.
4. **Record sessions** — you'll miss things in real-time
5. **Debrief immediately** — discuss with your team right after each session
6. **Share findings widely** — create a summary and present to the team
7. **Track issues over time** — are the same problems recurring?
