# UX Research

## Why Research Matters

Research removes guesswork. You're not designing for yourself — you're designing for real users with real needs, contexts, and limitations.

## Research Methods

### By Phase

| Phase | Methods |
|---|---|
| **Discover** | User interviews, surveys, field studies, competitive analysis |
| **Define** | Personas, journey maps, empathy maps, affinity diagrams |
| **Design** | Card sorting, tree testing, usability testing |
| **Validate** | A/B testing, beta testing, analytics review |

### By Type

| Type | Question Answered | Methods |
|---|---|---|
| **Attitudinal** | What do users say? | Interviews, surveys, focus groups |
| **Behavioral** | What do users do? | Analytics, usability tests, A/B tests |
| **Qualitative** | Why? | Interviews, usability tests, diary studies |
| **Quantitative** | How many? | Surveys, analytics, A/B tests |

## User Interviews

### When to Use
- Understanding user needs, motivations, and pain points
- Exploring a problem space before designing solutions
- Validating assumptions about user behavior

### How to Conduct

#### Preparation
1. **Define research goals** — what do you need to learn?
2. **Write a discussion guide** — open-ended questions, not a script
3. **Recruit participants** — 5-8 users per persona segment
4. **Set up recording** — audio (with permission) for later analysis

#### Interview Structure (45-60 min)
1. **Intro (5 min):** Explain purpose, get consent, build rapport
2. **Background (10 min):** Understand their context and experience
3. **Core questions (25-30 min):** Explore the research topic
4. **Show & tell (10 min):** Show prototypes/screens, get reactions
5. **Wrap-up (5 min):** Any final thoughts, thank them

#### Question Tips
- **Open-ended:** "Tell me about how you..." not "Do you...?"
- **Neutral:** Don't lead the witness. "What was your experience?" not "Wasn't it frustrating?"
- **Follow up:** "Can you tell me more about that?" "Why do you say that?"
- **Past behavior:** "Tell me about the last time you..." (past behavior predicts future better than hypotheticals)
- **Avoid "would you":** People are bad at predicting what they'd do. Focus on what they've done.

#### Bad Questions
- ❌ "Would you use this feature?" → ✅ "How do you currently solve this problem?"
- ❌ "Do you think this is easy to use?" → ✅ "Show me how you'd complete this task."
- ❌ "What do you want?" → ✅ "What's the hardest part about [activity]?"
- ❌ "Don't you think...?" → ✅ "What do you think about...?"

### Analysis
1. **Transcribe** interviews (or use AI transcription)
2. **Code** responses — tag quotes with themes
3. **Affinity mapping** — group related quotes on a board
4. **Identify patterns** — what comes up repeatedly?
5. **Prioritize insights** — which are most impactful?

## Surveys

### When to Use
- Collecting quantitative data from many users
- Validating qualitative findings at scale
- Measuring satisfaction (NPS, CSAT, SUS)

### Best Practices
- **Keep it short:** 5-10 questions max, under 5 minutes
- **Mix question types:** Multiple choice, rating scales, one open-ended
- **Avoid leading questions:** "How satisfied are you?" not "How happy are you?"
- **Use validated scales:** SUS (System Usability Scale), NPS, CSAT
- **Pilot test:** Send to 5 colleagues first, check for confusing questions
- **Incentivize:** Offer a small reward for completion

### System Usability Scale (SUS)
10-question standardized survey. Scores 0-100. Average is 68. Above 80 is excellent.

1. I think that I would like to use this system frequently.
2. I found the system unnecessarily complex.
3. I thought the system was easy to use.
4. I think that I would need the support of a technical person to use this system.
5. I found the various functions in this system were well integrated.
6. I thought there was too much inconsistency in this system.
7. I would imagine that most people would learn to use this system very quickly.
8. I found the system very cumbersome to use.
9. I felt very confident using the system.
10. I needed to learn a lot of things before I could get going with this system.

(Odd questions: strongly agree = 5. Even questions: strongly disagree = 1. Convert to 0-4 scale, sum, multiply by 2.5.)

## Competitive Analysis

### Process
1. **Identify 3-5 competitors** — direct and indirect
2. **Audit their product** — sign up, use it, screenshot everything
3. **Analyze features** — what do they have? What's missing?
4. **Evaluate UX** — what works well? What's frustrating?
5. **Identify opportunities** — gaps you can fill, mistakes to avoid

### Framework
| Feature | Competitor A | Competitor B | Your Product |
|---|---|---|---|
| Feature 1 | ✅ Good | ⚠️ Partial | ❌ Missing |
| Feature 2 | ✅ | ✅ | ✅ |
| Feature 3 | ❌ | ✅ | ❌ |

## Personas

### What Is a Persona?
A persona is a fictional character that represents a user segment, based on research data.

### Persona Template
```
┌───────────────────────────────────┐
│  [Photo]                           │
│  Name: Sarah Chen                  │
│  Age: 32                           │
│  Role: Marketing Manager           │
│  Tech comfort: High                │
├───────────────────────────────────┤
│  Goals:                            │
│  • Track campaign performance      │
│  • Generate reports quickly        │
│  • Collaborate with team           │
│                                    │
│  Frustrations:                     │
│  • Reports take too long           │
│  • Data is scattered               │
│  • Can't customize dashboards      │
│                                    │
│  Quote:                            │
│  "I just want to see my numbers    │
│  without clicking through 5 tabs." │
└───────────────────────────────────┘
```

### Guidelines
- Base personas on **real research**, not assumptions
- Create 2-5 personas (primary, secondary, negative)
- Share widely — they should be visible to the whole team
- Update as you learn more
- Don't over-personalize — focus on behaviors, not demographics

## Journey Maps

### What Is a Journey Map?
A visual representation of a user's experience over time, showing their actions, thoughts, emotions, and pain points.

### Structure
```
Stage:     Awareness →  Consideration →  Purchase →  Onboarding →  Ongoing Use
Action:    Searches    Compares options   Signs up    Sets up       Daily use
           online      Reads reviews      Pays        profile       Reports
Thought:   "I need     "Which is best     "Let's      "How do I     "This saves
           a tool"     for me?"           try it"     import data?" me hours"
Emotion:   😐 Neutral   😟 Confused        😊 Excited   😟 Frustrated  😊 Happy
Pain:      Too many     Hard to compare    Long form   Missing docs  Slow reports
           options                                       
```

### Guidelines
- Map the **current state** (as-is) before the future state
- Include emotional highs and lows
- Identify pain points and opportunities
- Use real research data, not guesses
- Share with the team to build empathy

## Empathy Maps

### Structure
```
┌──────────────┬──────────────┐
│  SAYS        │  THINKS       │
│  "I wish..." │  (internal    │
│  "It's hard" │   thoughts)   │
├──────────────┼──────────────┤
│  DOES        │  FEELS        │
│  (actions)   │  😊 😟 😐     │
└──────────────┴──────────────┘
```

### When to Use
- Quick team exercise to build empathy
- Early in the design process
- When you don't have time for full personas

## Card Sorting

### When to Use
- Designing or redesigning information architecture (IA)
- Organizing navigation menus
- Grouping features or content

### Types
| Type | How It Works |
|---|---|
| **Open** | Users group items and name the groups |
| **Closed** | Users sort items into predefined categories |
| **Hybrid** | Users sort into predefined categories + can create new ones |

### Process
1. Write each content item on a card (physical or digital)
2. Have users sort cards into groups
3. Ask them to name the groups (open sort)
4. Analyze patterns across participants
5. Use results to inform your IA

## Tree Testing

### When to Use
- Validating information architecture
- Testing if users can find items in your navigation

### Process
1. Create a text-only version of your site structure
2. Give users tasks: "Where would you find X?"
3. Users click through the tree to find the item
4. Measure: success rate, time, path taken
5. Identify where users get lost

## Research Without Budget

### Free/Low-Cost Methods
- **Guerrilla testing:** Test with 5 people at a coffee shop
- **Remote interviews:** Zoom/Google Meet with existing users
- **Analytics:** Google Analytics, Hotjar, FullStory
- **Support tickets:** Mine customer support data for pain points
- **Reviews:** Read app store and product reviews
- **Social media:** Listen to what users say on Twitter, Reddit
- **Competitor analysis:** Use competitors' products yourself
- **5-second test:** Show a screen for 5 seconds, ask what they remember

## Research Outputs

### Research Report
- **Executive summary:** Key findings in 1 page
- **Methodology:** How you conducted the research
- **Findings:** Organized by theme, with quotes
- **Recommendations:** What to do next
- **Raw data:** Appendix with full notes/transcripts

### Share Widely
- Present findings to the whole team
- Create a summary deck (10-15 slides)
- Store in a shared, searchable location
- Reference in design decisions

---

## User Panels

A **user panel** is a prescreened group of people who have agreed to be contacted for future research. Panels dramatically speed up recruiting — instead of running a new recruitment campaign for every study, you draw from a pool of pre-vetted, willing participants.

Many teams build panels with enthusiasm, then watch that enthusiasm fade after the first few recruitment cycles: internal ownership gets fuzzy, external participants stop responding, and the panel goes stale. A panel is a **long-term asset**, not a one-time project — it needs ongoing governance, monitoring, maintenance, and evolution to stay useful.

### Govern
Establish clear ownership and process before scaling usage.

- **Assign ownership.** Some orgs give this to a dedicated research-ops role; smaller teams rotate a "panel manager" among researchers.
- **Coordinate access.** Use a shared Slack channel or a simple request form so everyone can see who's reaching out to whom — this prevents over-contacting the same panelists and creates accountability.
- **Document expectations.** Maintain an accessible guide covering: how to use the panel for a study, how to log studies, how to incentivize participants, how to communicate with panelists, and where research data is stored.

Good governance reduces liability (over-contacting, inconsistent messaging) and makes recruiting faster for everyone in the org, not just the panel's original owners.

### Monitor
Track panel health so you catch problems before they become crises.

Useful indicators to track (as dashboard columns):
- **Last activity date** — surfaces stale segments needing re-engagement
- **Number of studies joined** — flags overused or underused panelists
- **Preferred contact method** — improves response rates
- **Representation gaps** — e.g., "we're only hearing from one region"

A quick **quarterly review** of these indicators is usually enough to keep the panel accurate and recruiting efficient.

### Maintain
Even a well-built panel decays without regular upkeep — both internally (process) and externally (participant relationship).

- Send brief **thank-you messages** after studies, or occasional updates showing how feedback shaped real product decisions — this sustains goodwill and response rates.
- Trigger a lightweight **"are you still interested?"** re-confirmation after ~12 months of inactivity.
- Periodically verify/update contact information.
- **Spread invitations across the panel** to avoid overusing a small subset of eager responders (which skews your sample) or underusing others (which lets them go cold).

### Evolve
Panels must grow and shift as the organization's priorities and audience change.

- **Audit annually** — review which studies the panel supported and how quickly recruitment happened, to gauge overall panel performance against your research goals.
- **Create sub-panels** for new regions, customer segments, or product lines once under-representation becomes visible in monitoring data.
- Treat evolution as continuous, not a one-time setup decision.

> **Summary:** Govern, Monitor, Maintain, Evolve. These four disciplines aren't the flashiest part of running research — but they're what determines whether a user panel becomes a durable, org-wide asset instead of a one-time recruiting push that quietly dies.
