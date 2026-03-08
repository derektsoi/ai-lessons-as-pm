# Multi-Perspective Review: Lesson 01 — Building Product Demos with Claude Code

---

## Agent 1: The Skeptic

**Prompt:** "You are reviewing a lesson written by a PM about using AI in product work. You are skeptical of AI hype and tired of people overselling their AI workflows."

### Is the author being honest about what worked and what didn't?

More honest than most. The "What I Got Wrong" section is genuinely strong — particularly the admission that "I didn't save time. I compressed decisions" and the self-aware observation that enjoying the building process might be driving behavior as much as productivity gains. The line "I enjoy this is not the same as this is the right use of PM time" is the kind of honesty I rarely see in AI workflow posts.

However, there's a blind spot. The author frames the old workflow as unambiguously broken — "the PRD is theater" — without acknowledging that PRDs serve coordination functions beyond stakeholder persuasion (alignment across teams, institutional memory, onboarding new team members). Declaring the old way "theater" is rhetorically convenient. It lets the new approach look transformative by comparison. A more honest framing would be: "The PRD was doing some things poorly and some things fine, and I replaced the part that was failing."

### Where does this sound like genuine insight vs justifying a new tool?

**Genuine insight:** The observation that a working demo forces you to confront edge cases you'd gloss over in a PRD. The merchant pinning example (what happens when a pinned merchant is already ranked #3?) is concrete and convincing — that's a real edge case that a document-based workflow would miss until design or engineering.

**Justifying the tool:** The Pokemon shopping agent example leans heavily on impressive-sounding output metrics — "2,383-line agent I/O specification," "13 Golden Conversations," "5 tech spikes." Volume of output is not evidence of quality. Did those 2,383 lines survive contact with engineering? How many of the 13 conversations turned out to be wrong? The author never says. The numbers are deployed to impress, not to teach.

Also: "Connected Figma MCP to read real design tokens. Built a component library from our design system. Used agent teams (4 generators + 3 reviewers) to produce 8 structural variations." This reads like a tech blog post, not a lesson. I don't learn anything from knowing the agent team configuration. I'd learn something from knowing which of the 8 variations the stakeholder chose and why the other 7 missed.

### What would make me actually share this article?

If the author picked ONE of the two examples and went deep enough to show a failure. The merchant pinning story almost gets there — he discovered edge cases. But did any of those edge cases turn out to be wrong priorities? Did engineering push back on the test cases? Did the COO disagree with any of the golden conversations? The lesson currently reads as: "I did this new thing, it was mostly great, here are some caveats." I'd share it if it read as: "I did this new thing, here's the moment it broke, and here's what that taught me about when to use it."

### 3 specific pieces of feedback (ranked by importance)

1. **Show a failure, not just caveats.** The "What I Got Wrong" section lists theoretical risks but no actual moments where the approach failed. The judgment-risk observation is sharp but abstract. Ground it: was there a golden conversation that turned out to be wrong? A tech spike that gave you false confidence? Without a concrete failure, the lesson reads as "this worked and I'm being modest about it."

2. **Cut the output volume metrics.** "2,383-line specification" and "13 Golden Conversations" are vanity metrics unless you show what they produced. Replace the numbers with outcomes: what decision did the COO make differently because of this work? What did engineering discover that the spec missed?

3. **Interrogate "the PRD is theater" more honestly.** This is a strong claim. Was it always theater, or was it theater in your specific org because of how your COO consumes information? If you moved to a company where stakeholders prefer documents, would you go back to PRDs? The lesson would be stronger if it acknowledged this is partly an org-fit observation, not a universal truth.

---

## Agent 2: The Outside Reader

**Prompt:** "You are a product manager at a mid-size company. You've heard about Claude Code but never used it. You clicked on this article because the title was interesting."

### At what point did I get lost or confused?

I was tracking well through "The Problem This Solves" — the frustration with PRDs that nobody reads is universal. I started losing the thread in the "Two examples" section. The Pokemon Shopping Agent example introduces a lot of concepts quickly: Golden Conversations, agent I/O specifications, tech spikes, sequence diagrams, Figma MCP, design tokens, agent teams (4 generators + 3 reviewers). I don't know what most of these are. The lesson assumes I already understand what Claude Code can do and jumps straight to an advanced workflow.

I also don't know what "MCP" means. Or what "agent teams (4 generators + 3 reviewers)" refers to — is that a Claude Code feature? A custom setup? People?

The "Decision Compression" section recovered my attention because it tells a story. But by then I've already been confused by the examples section, so I'm reading with less trust.

### What's the one takeaway I'd remember tomorrow?

"A working demo doesn't let you be vague." That's the line. It's concrete, memorable, and immediately applicable to my own work. I already know that my PRDs have vague spots that don't get caught until engineering. The idea that building a demo forces those to surface earlier is compelling.

### Did this make me want to try Claude Code?

Partially. The merchant pinning example made me curious — using Claude Code to generate HTML mockups that surface edge cases sounds useful and achievable. The Pokemon example made me feel like I'd need months of setup to get to that level (custom component libraries, Figma MCP, agent teams). The article doesn't give me a starting point. If there were a "here's the simplest version of this you can try today" moment, I'd be more motivated.

### Is there jargon or insider knowledge assumed?

Yes, significantly:
- **MCP** — never defined
- **Agent teams (4 generators + 3 reviewers)** — unexplained
- **Figma MCP / design tokens** — assumes familiarity with a specific toolchain
- **Tech spikes** — PM jargon that not all PMs use
- **Golden Conversations** — introduced as a concept without enough explanation of why this format specifically (vs. user stories, acceptance criteria, etc.)
- **TDD for LLM products** — assumes reader knows TDD
- **Sequence diagrams** — mentioned as a thinking tool but the reader doesn't know what role they play

### 3 specific pieces of feedback (ranked by importance)

1. **Explain the "Golden Conversations" concept more carefully.** This is the most original idea in the lesson and it goes by too fast. Why conversations specifically? How is this different from writing user stories or acceptance criteria? Show me one (even abbreviated) so I can see the format. Right now I'm told they're important but I can't picture what one looks like.

2. **Cut or simplify the toolchain details.** The Figma MCP / agent teams / design tokens paragraph reads like a conference talk for people who already use Claude Code. It's not teaching me anything — it's showing off a workflow. Either explain what these things are in plain language or remove them and focus on the insight.

3. **Give me a bridge from my current workflow.** I use PRDs today. The lesson tells me they're theater but doesn't give me a first step toward the alternative. Even something like "next time you're about to write a PRD section about how a feature should behave, try scripting a conversation instead" would help me see how to start.

---

## Agent 3: The PM Peer

**Prompt:** "You are a senior PM who also uses AI tools in your work. You've had your own successes and failures with AI-assisted product development."

### Does this match my experience?

The core observation — that building with AI tools compresses the decision cycle and forces earlier clarity — matches my experience completely. I've seen the same thing: when you can prototype something in hours instead of weeks, you front-load the hard product decisions. The PRD-as-theater point is also real, though I'd frame it less aggressively. PRDs aren't theater in every org — they're theater when the culture doesn't support document-based decision-making.

Where it diverges from my experience: the author seems to be operating as a solo practitioner. The demos are built by the PM alone (or PM + Claude Code). In my experience, the most effective AI-assisted workflows involve the PM and designer co-creating, or the PM and engineer co-exploring APIs. The "demo owner" framing makes it sound like one person owns the entire front-end of product thinking. That's fragile — it creates a single point of failure and can alienate collaborators.

### What's the author missing that I've learned the hard way?

**The demo anchoring problem.** When you show a concrete demo early, you anchor the entire conversation to that specific implementation. Stakeholders react to what they see, not what they imagine. This is powerful when the demo is directionally right. It's dangerous when the demo accidentally commits you to a UX pattern, a data model, or an interaction flow that's suboptimal but now feels "real." I've had projects where an early demo made it harder to pivot because everyone — including me — was anchored to the prototype.

The author mentions this risk obliquely ("if my judgment is wrong, it's wrong at scale and it looks authoritative") but doesn't connect it to the anchoring problem. It's not just that your judgment might be wrong in the abstract — it's that a concrete demo makes it psychologically harder for everyone to course-correct, including you.

**The collaboration cost.** The author describes working with the COO and mentions engineering pushback but doesn't address how designers feel about this workflow. If the PM is generating HTML mockups with real design tokens, what's the designer's role? In my experience, this creates real tension — not because designers are territorial, but because design decisions made in code (layout, spacing, interaction patterns) are hard to undo. The lesson mentions "PM and designers start working on a demo together" but every example is the PM working alone.

### Is the lesson actionable?

Partially. The "Decision Compression" framing is clear and memorable. A PM reading this could understand the concept and look for opportunities to apply it. But the how is underspecified. The lesson doesn't explain:
- How to scope a demo (when do you stop building and start sharing?)
- How to frame a demo to stakeholders (the "directional concept, not a design" framing is mentioned once and never explored)
- How to handle the moment when a stakeholder reacts to the demo in a way you didn't expect

The golden conversations idea is the most actionable element, but it needs more scaffolding. Show me the format. Tell me how to write one. Explain how you decided on 13 conversations and not 5 or 30.

### What would I push back on in a 1:1?

"The role of demo owner is for anyone who has an idea — not just PMs." This sounds democratic but I'd push hard on it. In practice, "anyone can build a demo" means "whoever is fastest with Claude Code sets the product direction." That's not democratization — it's a new kind of power concentration. The person who controls the demo controls the conversation. If that's always the PM, fine — that's their job. But if it's "anyone," you've created a situation where product direction is set by whoever builds the most convincing prototype, regardless of whether they have the product judgment to back it up.

The author even flags this risk in the "judgment" section but doesn't connect it to the "anyone can be a demo owner" claim. Those two ideas are in direct tension.

### 3 specific pieces of feedback (ranked by importance)

1. **Address the anchoring problem directly.** You've identified the judgment risk but missed the psychological mechanism. Early concrete demos anchor everyone — including you. Have you experienced a moment where the demo made it harder to change direction? If so, that's a critical addition. If not, name it as a risk you're watching for.

2. **Reconcile "anyone can be demo owner" with "judgment is higher-leverage."** These two claims contradict each other. If judgment is the key input and the safety net of slow iteration is gone, then making it easy for anyone to build demos is actively dangerous. Either scope "demo owner" to people with strong product judgment, or explain what guardrails exist for demos built by people without it.

3. **Show the collaboration, not just the solo work.** Every example is you building alone with Claude Code. But you claim the workflow starts with "PM and designers start working on a demo together." Where's the designer in these stories? What did they contribute? If the honest answer is "I did it alone," say that — and examine whether that's a feature or a bug of this approach.

---

## Synthesis

### 1. Where all 3 agree — strongest signals

- **The Golden Conversations concept needs more depth.** All three reviewers found this to be the most original and valuable idea in the lesson, but all three said it goes by too fast. The Skeptic wants to know which ones were wrong. The Outside Reader wants to see what one looks like. The PM Peer wants to know how to scope them. This is the centerpiece of the lesson and it's currently underserved.

- **Output volume is not the argument.** "2,383 lines" and "13 conversations" and "5 tech spikes" appear as evidence but don't function as evidence. All three reviewers wanted outcomes, not metrics. What decisions did those artifacts enable? What did they get wrong?

- **The lesson needs a concrete failure.** The "What I Got Wrong" section is admirably self-aware but stays theoretical. Every reviewer wanted a moment where the approach actually broke down — not a risk the author is watching for, but something that already happened. Without it, the lesson reads as advocacy with caveats, not a genuine postmortem.

### 2. Where they disagree — interesting tensions

- **"PRD is theater" — universal truth or org-specific?** The Skeptic says this is too strong a claim and might be org-specific (a COO who prefers demos over documents). The PM Peer partially agrees but frames it more gently. The Outside Reader accepted it uncritically because it matches their frustration. This disagreement suggests the lesson needs to scope this claim — is this about PRDs generally, or about a specific decision-making culture?

- **How much toolchain detail to include.** The Skeptic and Outside Reader both want less Claude Code-specific detail (MCP, agent teams, design tokens). The PM Peer implicitly wants more — specifically about the collaboration workflow and how the tools fit into team dynamics. The tension: the lesson is partly about Claude Code and partly about a way of working. It needs to decide which story it's telling, or be clearer about how they connect.

- **"Anyone can be demo owner" — empowering or dangerous?** The PM Peer sees this as actively dangerous when combined with the judgment-risk observation. The Skeptic didn't engage with it deeply. The Outside Reader didn't flag it. This is a tension within the lesson itself — two of the author's own claims contradict each other, and only one reviewer caught it clearly.

### 3. Top 5 changes, ranked by impact on lesson quality

1. **Show a Golden Conversation.** Even an abbreviated example. This is the most original idea and readers can't evaluate or apply it without seeing the format. Include one, then explain why conversations (not user stories, not acceptance criteria) are the right unit for LLM product specs.

2. **Replace one "What I Got Wrong" item with a real failure.** Pick the moment where the demo-first approach actually led you astray — an edge case you got wrong, a golden conversation that turned out to be based on a wrong assumption, a stakeholder reaction that the demo anchored in the wrong direction. Theoretical risks are less convincing than lived ones.

3. **Reconcile "anyone can be demo owner" with "judgment is higher-leverage."** Either scope who should be a demo owner, or explain what guardrails prevent low-judgment demos from steering product direction. Right now these two claims sit in the same lesson without acknowledging their tension.

4. **Cut or contextualize output metrics.** Replace "2,383-line specification" and similar metrics with what those artifacts produced — decisions made, misalignments caught, surprises avoided. If you keep the numbers, pair each one with an outcome.

5. **Scope the "PRD is theater" claim.** Acknowledge that this observation may be specific to your org's decision-making culture (COO who responds to visual demos, short feedback loops). This makes the lesson more credible, not weaker — it shows you've thought about generalizability rather than just evangelizing.

### 4. One question the author should answer before revising

**"What is the single most important product decision that came out of a Golden Conversation — and would that decision have been made differently (or later, or worse) under the old PRD workflow?"**

This question forces the author to ground the entire lesson in one concrete, traceable outcome. If the answer is vivid and specific, it becomes the spine of the article. If the author struggles to answer it, that's a signal that the lesson is still more about the process (which is exciting) than the outcome (which is what readers need to see).
