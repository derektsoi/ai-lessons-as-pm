# Think-Through Critique: 01-building-demos-with-claude-code.md

---

## 1. Observation Check

**Grounded claims (strong):**

- "I used Claude Code to generate HTML+Tailwind mobile mockups" -- specific action, concrete tool usage.
- "Connected Figma MCP to read real design tokens. Built a component library from our design system. Used agent teams (4 generators + 3 reviewers) to produce 8 structural variations." -- precise numbers and method. This is observation.
- "Wrote 13 Golden Conversations" -- specific, countable artifact.
- "5 tech spikes testing real APIs, sequence diagrams mapping data flow, a 2,383-line agent I/O specification" -- concrete numbers grounding the claim.
- "All the Pokemon APIs use different card identification standards. The price API has one, the card catalog has another, the photo recognition returns a third." -- specific technical discovery. This reads like something that actually happened.
- "I wrote 15 test cases before sharing anything with engineers" (merchant pinning) -- specific.

**Claims that read like narrative constructed after the fact:**

- "The PRD is theater. It serves a bureaucratic function, not a thinking function." -- This is a strong claim presented as universal truth. Was every PRD you wrote theater? Were there PRDs that actually worked? If so, what made those different? This line is doing rhetorical work, not observation work.

- "I didn't set out to change how I write specs. I was building a demo... Somewhere in the middle of that, I realized I wasn't writing a demo anymore. I was writing the spec." -- This is a clean origin story. Too clean. Did you really have a single moment of realization, or did this understanding emerge gradually? If it was gradual, what were the intermediate steps?

- "In the old workflow, decisions took 4-10 weeks to surface." -- Is this measured or estimated? What's the actual range from specific projects? "4-10 weeks" feels like a round number picked to sound bad. What was it actually?

- "I'd say 50% of the time we got it wrong and had to adjust last minute. Sometimes it was a disaster." -- "I'd say 50%" is a guess, not data. Can you name the disasters? Even one specific one would make this credible. Without it, this reads like "things were bad before, now they're good" -- the most common and least trustworthy narrative shape.

- "Now, the COO sees a demo grounded in real API calls in the first few sessions. When he asks 'can it do X?' -- the answer is based on an API call I already made, not a guess." -- Has this actually happened? What did the COO actually ask? What was your answer? This is the single most important claim in the lesson (the new workflow produces better stakeholder conversations) and it's the one with the least specific evidence.

**Questions to ground the narrative:**

- What did the COO actually say when he saw the Pokemon demo? Quote him, or at least paraphrase a specific reaction.
- What did stakeholders say when they saw the Trending Merchants mockups? Did the "directional concept, not a design" framing actually work, or did someone treat it as a final design anyway?
- You mention engineering pushback on the "demo owner" concept. What specifically did they push back on? What words did they use?

---

## 2. Lesson Depth Check

**The stated lesson:** "Claude Code compressed my product development cycle from weeks to days. That sounds like a win -- and it is -- but it means my judgment has to be right much earlier, with fewer correction points."

**Is this the first-pass lesson?** No -- the author has already pushed past several first-pass framings (listed in the "Previous framings (superseded)" section). The current framing has real tension in it. That's good.

**But there's something underneath it that the lesson is circling around without landing on:**

**Alternative framing 1: "I replaced a distributed decision-making process with a centralized one, and I'm calling it better because it's faster."**

The old workflow (PM writes spec, designer interprets, engineer discovers problems, it escalates back) is slow and frustrating -- but it's also a distributed system for catching errors. Multiple people apply judgment at multiple stages. The new workflow concentrates judgment in one person (you) at one stage (the demo). The lesson acknowledges this ("judgment is higher-leverage and higher-risk now") but frames it as a future concern rather than a present tension. You already have two projects using this method. Is your judgment actually being validated, or are you too early to know?

**Alternative framing 2: "I found a way to do engineering's job before they do, and I'm framing it as product work."**

The lesson carefully distinguishes "what the product does" (PM) from "how it works" (engineering). But you're writing sequence diagrams, testing APIs, defining data flows, and producing 2,383-line specifications. At what point does "product judgment about what to test" become "technical architecture decisions made without engineering input"? The engineering pushback you mention might be more substantive than the lesson currently acknowledges. The question isn't just "who builds the demo" -- it's "who gets to make architectural implications before engineering is in the room."

**The uncomfortable truth the lesson is dancing around:** You enjoy this. You say so explicitly in the "It's both" section. But the lesson is structured to justify the practice on productivity grounds first, and acknowledge the enjoyment second. What if the enjoyment is the primary driver, and the productivity argument is the rationalization? That doesn't make the practice wrong -- but it changes how you'd evaluate it. You'd ask "is this the best use of my time?" differently if you started from "I like building" rather than "this produces better decisions."

---

## 3. Gap Check

**Unaddressed "Think through" prompts:**

- "What specifically made the old workflow ineffective? Was it the format (document), the timing (too late), the abstraction (too vague), or the people (wrong audience)?" -- The prose section partially answers this but doesn't commit to a specific diagnosis. If it's all four, say that and rank them. The lesson currently implies "abstraction" is the main problem (demos are concrete, PRDs are vague) but the timing argument might be stronger.

- "Does this framing actually address engineering's concern? Or does it still feel like the PM has pre-empted technical decisions?" -- This is the right question and it's still sitting unanswered in the scaffold. The "Demo Owner" section acknowledges the question but doesn't engage with it honestly.

- "Have you tried this and had it fail? If not, these boundaries are theoretical." -- Still theoretical. The lesson is honest about this, but it weakens the "Where This Approach Works" section significantly. Everything in the "Might not work when" list is speculation.

**Sections still in bullets that need prose:**

- "The Problem This Solves" -- still bullets. This is the setup for the entire piece. If this stays as bullets, the reader has no emotional entry point.
- "The 'Demo Owner' Experiment" -- still mostly bullets. This is where the real organizational tension lives. It deserves more than a bullet list.
- "Where This Approach Works (and Doesn't)" -- bullet list is fine for this section structurally, but the items need expansion. "Internal system behavior that can't be tested from the outside" -- can you give an example from your own work?

**Counterarguments not acknowledged:**

- What if the COO preferred the demo because it was shiny, not because it was better? Is there a risk that "real API data" gives a false sense of completeness? You validated that an API returns certain data -- you didn't validate that the product built on that API would work at scale. The demo could be persuasive without being predictive.
- What about the designers? You mention PM and designers working together, but the lesson is almost entirely about you working solo with Claude Code. Where did design actually contribute? If they didn't contribute much, that's worth examining -- you may be cutting them out of the process the same way you're worried about cutting out engineering.
- Survivorship bias: you're writing about two projects that went well. Were there demos you started and abandoned? Approaches you tried with Claude Code that didn't work?

**Reader questions the lesson doesn't answer:**

- How long did the Pokemon demo actually take to build? "Days not weeks" is implied but never stated.
- What happened after the demo? Did engineering implement it? Did the golden conversations actually serve as the spec during development, or did they write their own?
- What does the COO think about this approach? Has he said anything about the quality of decisions coming out of it?

---

## 4. Audience Check

**Would a PM who has never used Claude Code understand why this matters?**

Partially. The core insight (demos force concrete decisions, PRDs allow vagueness) is universal and doesn't require Claude Code knowledge. But the lesson is heavy on Claude Code mechanics (Figma MCP, agent teams, HTML+Tailwind) that will lose non-technical readers. The lesson needs to be clearer about what's transferable (the practice of building concrete artifacts before writing specs) vs. what's tool-specific (using Claude Code to do it).

**Does it assume insider knowledge?**

- "Figma MCP" -- most PMs won't know what this is.
- "Agent teams (4 generators + 3 reviewers)" -- this is Claude Code jargon.
- "Golden Conversations" -- the term isn't standard. It's defined well enough in context, but the first mention should make clear this is the author's own term.
- "TDD for LLM products" -- assumes the reader knows what TDD is.

**What's the one line that would make someone share this?**

"A working demo doesn't let you be vague." This is already in the text (line 57). It's sharp, it's true, and it applies beyond AI tools. This should be the title or the hook, not buried in a paragraph.

Runner-up: "I did more work, not less. I made better decisions, not faster ones." This challenges the "AI saves time" narrative that most readers will expect.

---

## 5. Verdict

**Scaffold done.** The Core Insight section has been expanded into strong prose -- it's the most developed part of the lesson and it's genuinely good. But the surrounding sections (The Problem, Demo Owner, Where This Works) are still in bullet/scaffold form. The lesson has a solid center but unfinished edges. The biggest risk is that the Core Insight section is doing too much work -- it's trying to be the entire lesson, and the other sections feel like appendices rather than integral parts of the argument.

Before expanding the remaining sections, the author should decide: is this one lesson or three? "Decision compression" is one lesson. "The demo owner experiment" is another. "Judgment risk when you remove the iteration safety net" is a third. Trying to serve all three in one piece may be why the scaffold feels uneven -- the Core Insight section is the strongest because it's the most focused.

---

## 3 Questions to Sit With

1. **What did the COO actually say after the Pokemon demo?** You've built the entire lesson around the claim that demos produce better stakeholder conversations than PRDs. But you haven't included a single specific reaction, quote, or decision that came out of those conversations. Without that, the reader is taking your word for it. What's the moment that proved this worked?

2. **Is the engineering pushback about process or about trust?** You frame it as a role-definition problem (who builds the demo). But engineers might be saying something different: "You're making technical commitments we haven't agreed to." If that's the real objection, the "demo owner builds, business owner decides" framing doesn't address it -- because the concern isn't about who decides, it's about what's already been decided by the time they see it.

3. **If you hadn't enjoyed building, would you still think this is the right approach?** You're honest about the "it's both" tension. But the lesson is structured to prove the productivity case first, then acknowledge the enjoyment. Try inverting it: assume the enjoyment is the primary driver. Does the productivity argument still hold up on its own? If it does, great -- lead with that evidence. If it doesn't, the lesson needs to reckon with that more directly.
