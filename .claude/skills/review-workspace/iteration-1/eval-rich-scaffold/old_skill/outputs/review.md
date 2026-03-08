# Multi-Perspective Review: Building Product Demos with Claude Code

---

## Agent 1: The Skeptic

**Perspective:** Skeptical of AI hype and tired of people overselling their AI workflows.

### Is the author being honest about what worked and what didn't?

**Mostly yes, and this is the strongest thing about the piece.** The "What I Got Wrong" section is genuinely rare in AI-productivity writing. Three specific observations:

1. **The "I did more work, not less" admission is credible.** Most AI articles claim magical time savings. This author says the opposite — the output is denser, the upfront investment is higher, and the claimed benefit is decision quality, not speed. That's a harder sell, which makes it more believable.

2. **The "it's both" honesty about motivation is disarming.** Acknowledging that part of the drive is enjoying building, not just productivity, is the kind of thing people usually edit out. It stays.

3. **The judgment-risk section is the most honest part of the whole piece.** "If my judgment is wrong, it's wrong at scale and it looks authoritative because it's grounded in real data" — this is a genuinely uncomfortable insight that most AI advocates wouldn't surface.

**Where honesty falters:**

- The "I found this before any engineer touched the project" line about the Pokemon API identification mismatch reads like a humble-brag. Did you find it because you're a great PM, or because you happened to be the first person to actually call the APIs? Those are very different things. An engineer doing discovery would have found the same thing.
- The "50% of the time we got it wrong" claim about the old workflow is suspiciously round and dramatic. Is this a real number or a vibes estimate? If vibes, say so.
- The comparison to the old workflow ("PM writes a spec based on assumptions...") is a straw man of the old way. Plenty of teams do discovery, prototyping, and API testing without Claude Code. The old workflow described here sounds dysfunctional regardless of AI tools.

### Genuine insight vs. tool justification?

**The "decision compression" framing is genuine insight.** It names something real — the collapse of spec/demo/validation into one activity — and the author traces it to specific experiences rather than abstract benefits.

**But large sections still read as "look at what I built."** The Trending Merchants description (agent teams, 8 structural variations, Figma MCP) reads like a feature list for Claude Code, not a lesson about product work. The Pokemon Shopping Agent section is better because it connects the work to a product insight (the card ID mismatch), but even here the tech details (2,383-line spec, 5 tech spikes) feel like they're there to impress rather than to teach.

### What would make me share this?

The judgment-risk section. If the whole article were as sharp as "the safety net of slow iteration is gone, and we don't have a replacement yet," I'd share it immediately. The author is at their best when they're worried, not when they're proud.

### Top 3 Feedback (ranked)

1. **Cut the resume items.** "2,383-line agent I/O specification," "4 generators + 3 reviewers," "8 structural variations" — these make you sound like you're pitching Claude Code, not reflecting on what you learned. The lesson doesn't need your line count to be credible.

2. **The old workflow straw man weakens the argument.** If the old workflow was genuinely that bad ("PRD is theater"), the improvement might be about fixing a broken process, not about AI. Acknowledge that competent teams already do discovery work — your claim should be that Claude Code makes it accessible to PMs who don't code, not that it replaces dysfunction.

3. **Lead with the uncomfortable stuff.** The piece buries its best material (judgment risk, "it's both," the unsolved safety-net problem) in a section called "What I Got Wrong." That material IS the lesson. The "what I did" sections are just context.

---

## Agent 2: The Outside Reader

**Perspective:** A product manager at a mid-size company who has heard about Claude Code but never used it. Clicked the article because the title was interesting.

### At what point did I get lost or confused?

1. **"Connected Figma MCP to read real design tokens"** — I don't know what MCP is, what a design token is in this context, or what "connected" means practically. This is the first moment where I felt like the article was written for people who already use Claude Code.

2. **"Used agent teams (4 generators + 3 reviewers) to produce 8 structural variations"** — Agent teams? Are these AI agents? People? What's a generator vs. a reviewer in this context? The article assumes I know Claude Code's capabilities.

3. **"TDD for LLM products"** — I get TDD conceptually, but the analogy isn't fully explained. How are golden conversations like TDD? TDD has a specific red-green-refactor cycle. Are golden conversations automated? Can they be re-run?

4. **The jump from "golden conversations" to "sequence diagrams" to "tech spikes"** — I follow golden conversations because they're well-explained. But the article introduces sequence diagrams and tech spikes without explaining how they fit into the workflow. When did they happen? Were they a separate step or did they emerge from the golden conversations?

### What's the one takeaway I'd remember tomorrow?

**"A working demo doesn't let you be vague."** This is the sharpest line in the piece and it's the one I'd repeat to a colleague. The idea that concreteness forces better decisions is intuitive and resonant even without knowing Claude Code.

### Did this make me want to try Claude Code?

**Yes, but not for what the author intended.** I'm interested in the golden conversations concept — scripting user dialogues as a spec — more than the demo-building. I could see writing golden conversations without Claude Code. The article doesn't clearly separate what Claude Code enables from what's just a good PM technique.

Specifically, I'd want to know: could I do the golden conversations approach with a different tool? With no tool? What part of this requires Claude Code specifically?

### Jargon / assumed knowledge

- **MCP** — never defined
- **Figma design tokens** — assumes reader uses Figma
- **Agent teams (generators + reviewers)** — Claude Code concept, unexplained
- **Tech spikes** — engineering term, not universal among PMs
- **Sequence diagrams** — mentioned but not explained for a PM audience
- **"HTML+Tailwind mobile mockups"** — assumes reader knows Tailwind CSS
- **"LLM translation layer"** — assumes reader knows what an LLM does in an architecture

### Top 3 Feedback (ranked)

1. **Separate the method from the tool.** The most valuable idea here — use concrete demos to compress product decisions — doesn't require Claude Code. But the article blends the method and the tool so tightly that I can't tell which lessons apply to me if I don't use Claude Code. A clearer separation would help: "Here's the approach. Here's how Claude Code makes it faster/possible."

2. **Define or cut the jargon.** MCP, agent teams, design tokens, Tailwind — each of these is a speed bump for an outside reader. Either explain them in a sentence or remove them. The golden conversations concept is beautifully explained; apply that same care to the technical references.

3. **The merchant pinning example is actually more relatable than the Pokemon one.** The Pokemon shopping agent is a cool project but it's unusual — most PMs aren't building AI chatbots. The merchant pinning example (marketer pins a merchant, edge cases emerge) is something almost any PM can relate to. Consider leading with that or giving it equal weight.

---

## Agent 3: The PM Peer

**Perspective:** A senior PM who also uses AI tools in product work. Has had my own successes and failures with AI-assisted product development.

### Does this match my experience?

**The core dynamic — yes, absolutely.** I've had the same experience where building a prototype forced me to discover edge cases I'd have glossed over in a spec. The "decision compression" framing puts a name to something I've felt but couldn't articulate. That's valuable.

**Where it diverges from my experience:**

1. **The COO-as-audience dynamic is specific and possibly distorting.** The author's workflow is heavily optimized for impressing/aligning with a single executive decision-maker (COO). In my experience, the harder alignment problem is cross-functional — getting design, engineering, data, and business aligned simultaneously. A demo that wows the COO might actually make that harder if other stakeholders feel bypassed. The article doesn't address this.

2. **The "PM builds before engineering" dynamic.** I've tried this and it can create resentment. Engineers feel their expertise is being pre-empted, especially when a PM makes architectural assumptions (like "we need a middle LLM layer to translate between APIs"). The author acknowledges engineering pushback but doesn't take it seriously enough. "Demo owner builds, business owner decides" is a clean slogan, but in practice the demo bakes in technical assumptions that constrain engineering's solution space.

3. **Scale and team dynamics are missing.** This works as a solo PM workflow. What happens when 3 PMs are all building demos? Do you get competing visions? Conflicting demo artifacts? Who maintains the golden conversations after launch?

### What's the author missing?

1. **The maintenance problem.** Golden conversations are great as a discovery tool. But they become a liability if they're treated as living specs. APIs change, product requirements evolve, edge cases multiply. Who updates the 13 golden conversations when the third API changes its card identification format? If nobody, they become stale artifacts that mislead. If the PM, that's a lot of ongoing work. If engineering, they'll rewrite them in a way that works for them, not for COO presentations.

2. **The validation gap.** The author tested APIs and built demos, but did users validate the golden conversations? The article mentions the COO seeing demos, but COO approval and user validation are different things. A beautiful demo that the COO loves but users find confusing is still a failed product.

3. **Survivorship bias.** Two projects that went well. What about the projects where this approach wouldn't have worked? The "Where This Approach Works" section is theoretical — the author admits they haven't had a failure case yet. That's a significant gap. One success story is an anecdote, not a method.

### Is the lesson actionable?

**Partially.** The golden conversations concept is actionable — I could start writing scripted dialogues for my next project tomorrow. The decision compression idea is a useful mental model.

**But the how-to is thin.** How do you decide what to put in a golden conversation? How many do you need? How do you know when you've covered enough edge cases? The 15 test cases for merchant pinning — how did you decide when to stop at 15? The article tells me what the author did but doesn't give me enough to replicate it.

### What would I push back on in a 1:1?

**"I did more work, not less"** — I'd push on whether this is sustainable. You're describing a workflow that requires deep domain expertise, strong product judgment, comfort with technical tools, and significant upfront time investment. That's a high bar. If the lesson is "PMs should do more upfront work," that's not new. If the lesson is "Claude Code makes a specific kind of upfront work possible for PMs who don't code," that's more interesting but the article doesn't quite land there.

**The engineering relationship.** You mention pushback from engineering exactly twice, both times briefly. This is the elephant in the room. If I were your peer, I'd ask: "Have you talked to your engineers about how they feel when you show up with a 2,383-line spec and sequence diagrams? Do they feel like collaborators or implementors?" The "demo owner builds, business owner decides" framing conspicuously leaves out "engineering validates and pushes back." That's either an oversight or an avoidance.

### Top 3 Feedback (ranked)

1. **Take the engineering tension seriously.** This is the most important unresolved issue in the piece. The "demo owner" framing papers over a real dynamic: when a PM shows up with a detailed demo and spec, engineering's role shifts from co-creator to implementor. The article needs to either honestly grapple with this or acknowledge it as the biggest open risk.

2. **Add the user validation step.** The workflow goes: PM builds demo -> COO approves -> engineers build. Where do users come in? If the answer is "after engineering builds," you've just recreated the old waterfall with a faster front end. If users validate the golden conversations directly, say so and explain how.

3. **Ground the "Where This Works" section in real experience.** Right now it's a theoretical matrix. Either find real examples of where this approach struggled (even small ones) or be explicit that this is speculative. "I think it wouldn't work for incremental features" is honest but weak — test it and report back.

---

## Synthesis

### 1. Where All 3 Agree

These are the strongest signals — pay attention.

- **The judgment-risk insight is the best material in the piece.** All three reviewers flagged that the "What I Got Wrong" section contains the real lesson. The Skeptic said "the author is at their best when they're worried, not when they're proud." The Outside Reader found "a working demo doesn't let you be vague" to be the sharpest line. The PM Peer valued the decision compression framing most when it came with honest caveats. The uncomfortable material is buried; it should lead.

- **The engineering tension is undercooked.** The Skeptic flagged that "I found this before any engineer touched the project" is a humble-brag. The PM Peer said engineering's role as co-creator vs. implementor is the elephant in the room. The Outside Reader didn't flag this directly but noticed the workflow conspicuously skips from "PM builds" to "COO decides" without engineering in the loop. All three see a gap where the author waves at engineering pushback without confronting it.

- **The piece blends tool-showcase with genuine reflection, and the tool-showcase parts are weaker.** The Skeptic wants the "resume items" cut. The Outside Reader got lost in Claude Code jargon (MCP, agent teams, Tailwind). The PM Peer said the how-to is thin — details about the tool don't translate to actionable guidance. The golden conversations concept is well-explained; the Claude Code feature list is not.

### 2. Where They Disagree

These are the interesting tensions — explore them.

- **Which example should lead?** The Outside Reader says the merchant pinning example is more relatable and should be given equal or greater weight. The Skeptic and PM Peer both focused more on the Pokemon example because it's richer. The tension: the Pokemon example is more impressive but less transferable; the merchant pinning example is more universal but less developed. The author needs to decide which audience they're writing for.

- **Is "I did more work, not less" a strength or a weakness?** The Skeptic finds this admission credible and refreshing. The PM Peer questions whether the workflow is sustainable and whether the lesson is actually just "PMs should do more upfront work." Both are right — the honesty is valuable, but it raises a question the piece doesn't answer: is this a replicable approach or a personal flex?

- **How much should the piece be about Claude Code specifically?** The Outside Reader wants a clearer separation between method and tool — the golden conversations concept is tool-agnostic. The Skeptic wants the piece to acknowledge that competent teams already do discovery without AI. The PM Peer wants to know what's specifically enabled by Claude Code vs. what's just good PM craft. None of them agree on the answer, which suggests the author hasn't decided either.

### 3. Top 5 Changes (ranked by impact)

1. **Restructure so the uncomfortable insights lead, not trail.** The judgment-risk problem, the "it's both" motivation honesty, and the missing safety net are currently buried in "What I Got Wrong." Move these to the front of the argument. The narrative should be: "I compressed weeks of decisions into days — and that created a new problem I haven't solved yet." All three reviewers identified this as the real lesson.

2. **Confront the engineering relationship honestly.** Two brief mentions of pushback isn't enough for the biggest open tension in the piece. Either devote a real section to how this workflow changes the PM-engineering dynamic (with specific examples of how engineers responded) or name it explicitly as the unsolved problem it is. Don't paper over it with a clean slogan.

3. **Cut the Claude Code feature-list material.** Remove or drastically reduce references to agent teams, line counts, structural variations, MCP, Tailwind, and other tool-specific details. These serve the author's pride more than the reader's learning. Keep the golden conversations concept (well-explained) and the API testing insight (earned through real work). Everything else is noise.

4. **Separate the method from the tool.** Make explicit what's a PM technique anyone could adopt (golden conversations, testing assumptions through concrete demos, decision compression as a mental model) and what Claude Code specifically enables (a non-coding PM can call APIs, generate mockups, iterate quickly). This serves both the Outside Reader who wants to know what applies to them and the Skeptic who wants to know what's actually new.

5. **Add the user validation step to the workflow.** The current workflow is PM builds -> COO approves -> engineers build. If users are validating golden conversations, say how. If they're not, acknowledge this as a gap. Without this, the PM Peer's critique lands hard: this could be faster waterfall, not better product development.

### 4. One Question the Author Should Answer Before Revising

**If your lead engineer read this piece, would they feel like a collaborator in the story you're telling — or would they feel like the person who was told what to build?**

Your answer to this question will determine whether the engineering tension gets a real section or stays a footnote. And if you're not sure how they'd feel, that's worth finding out before you write the revision.
