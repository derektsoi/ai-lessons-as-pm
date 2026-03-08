# Think-Through Critique: 01 — Building Product Demos with Claude Code

## Observation vs. Narrative

The core insight section is the strongest part of this lesson, and it's strongest precisely where it stays grounded. Some specific observations:

**Grounded (good):**
- "All the Pokemon APIs use different card identification standards. The price API has one, the card catalog has another, the photo recognition returns a third." — This is a concrete discovery. It traces to a real moment.
- "What happens when a marketer pins a merchant that's already ranked #3?" — Specific edge case you found by building.
- "13 Golden Conversations... 5 tech spikes... 2,383-line agent I/O specification." — Real numbers, real artifacts. These anchor the claim.

**Narrative masquerading as observation:**
- "I'd say 50% of the time we got it wrong and had to adjust last minute. Sometimes it was a disaster." — Is 50% real or a feeling? What was the actual disaster? Name one. "Disaster" is a story you're telling yourself; the specific incident would teach the reader something.
- "When he asks 'can it do X?' — the answer is based on an API call I already made, not a guess." — Did this actually happen? What did the COO actually ask, and what was your answer? If you have a real exchange, use it. If you're constructing what you imagine happened, flag it.
- "Stakeholders are reacting to real output, not wireframes of idealized flows. Their feedback is grounded too — they can't say 'make it smarter,' they have to point to a specific conversation and say 'this answer is wrong because X.'" — Did someone actually do this? Or is this the theory of how the demo should work? The Trending Merchants section has a bracketed note that literally says: *"Expand on: what happened when stakeholders saw the mockups."* You haven't filled that in. The claim about stakeholder reactions is unsupported by the lesson's own evidence.
- "The PRD is theater." — Strong line, but it's a conclusion, not an observation. What specific moment made you realize this? Was there a particular PRD that no one read? A meeting where the PRD was supposed to be the artifact and it fell flat?

**The "old workflow" section is almost entirely narrative.** "PM waits for vague idea from management. Writes PRD in a format boss won't read." This may be accurate, but it reads like a polemic against a straw man. One concrete example of the old workflow failing — a specific feature, a specific misunderstanding, a specific timeline — would make this section credible instead of just persuasive.

## Depth

The current framing — "decision compression" — is solid and non-obvious. It's better than "AI makes PMs faster" or "demos beat docs." You've pushed past the surface, especially with the risk half (judgment is higher-leverage and the safety net is gone).

But there are two places where the thinking stops short:

**Alternative framing 1: "I replaced a collective thinking process with a solo one."**

The old workflow, for all its slowness, involved multiple people interpreting and reacting to the idea at multiple stages. Designer interprets the spec, engineer pushes back on feasibility, COO sees a finished design. Each handoff was a correction opportunity. You've compressed those handoffs, but you've also eliminated them. The demo arrives fully formed, grounded in real data, and that's exactly what makes it harder to challenge. You acknowledge this in "What I Got Wrong" — but the lesson buries it there instead of wrestling with it as a central tension.

The uncomfortable version: by making the artifact more authoritative (grounded in real APIs, concrete scenarios), you may have made it *harder* for others to push back, not easier. Does the COO challenge a demo backed by real API calls the same way he'd challenge a wireframe? Or does the concreteness create an anchoring effect? You don't say.

**Alternative framing 2: "I discovered the demo is the spec — but I haven't proven the spec is better."**

You have strong evidence that the demo surfaces decisions earlier. You don't have evidence that those decisions are *better*. You mention the Pokemon project hasn't been built yet (implied — no mention of engineering starting). You mention the merchant project test cases, but not whether engineering agreed they covered the right scenarios. The lesson claims "better decisions" but the evidence only supports "earlier decisions." Those are different claims.

## Gaps

**Unaddressed scaffold prompts:**
- "Think through: What specifically made the old workflow ineffective? Was it the format (document), the timing (too late), the abstraction (too vague), or the people (wrong audience)?" — This is still sitting as a prompt. The "Why this matters" section answers it partially but doesn't commit to a clear answer. The lesson would be sharper if you picked one primary cause and argued for it.
- "Think through: Does this framing actually address engineering's concern?" — Still a prompt. The "Demo Owner" section has a contract definition but doesn't report whether engineering actually bought in.
- "Think through: Have you tried this and had it fail?" — Still a prompt. And the answer matters a lot. If the answer is "no," say so — that's honest and useful. Theoretical boundaries without a failure story are less convincing.

**Missing details that weaken the argument:**
- The Trending Merchants example is thin. You describe what you built (HTML+Tailwind mockups, component library, agent teams). You don't describe what happened next. Did it change the conversation? How? What did the boss actually say when he saw mockups instead of a PRD?
- You mention "pushback from engineering" three times but never describe it concretely. What did they actually say? "Pushback" is a narrative summary. The specific objection would teach the reader something.
- The "It's both" section is honest and good, but it's one paragraph. This might be the most important tension in the lesson — the difference between "this produces better outcomes" and "I like doing this" — and it gets the least space.

**Counterarguments not addressed:**
- A skeptical PM would ask: "You spent all this time building a demo and testing APIs. How do you know the PRD approach would have taken longer end-to-end? Maybe you front-loaded work that would have been distributed across the team." You claim the old cycle was 4-10 weeks, but you don't say how long the new approach took for either project.
- Another reader would ask: "If the COO is reacting to a polished demo, does he even realize there are decisions still open? Or does the demo's completeness close doors that should stay open?"

## Audience Readiness

**What works for a Substack audience:**
- The "decision compression" frame is the kind of thing PMs would share. It's specific enough to be useful, abstract enough to apply broadly.
- The Pokemon example is vivid — card identification standards, LLM translation layer, golden conversations. A PM who's never used Claude Code can still follow the logic.
- The "What I Got Wrong" section is genuinely unusual for this kind of article. Most "I used AI to do X" posts are triumphant. This one admits risk.

**What doesn't work yet:**
- The lesson assumes the reader knows what Claude Code is and how it works. A line or two of context would help — "a coding assistant that can browse docs, call APIs, and generate code from conversation" or similar.
- The Trending Merchants example needs to either be fleshed out or cut. Right now it's half-told and dilutes the Pokemon example, which is much stronger.
- The "Demo Owner" section reads like internal org politics, not a lesson. A Substack reader doesn't care about your engineering team's pushback unless you can extract a general principle from it. The principle might be: "When you change the artifact, you change the power dynamics" — but the lesson doesn't get there.

**Shareable line candidate:** "A working demo doesn't let you be vague" is already in the text and it's the strongest one-liner. That could be the title.

## Verdict

**Rating: Draft ready** (for the core insight section). The rest is scaffold that needs either expansion or cutting.

The core insight section (paragraphs on decision compression, the Pokemon example, the merchant pinning example, and the "old workflow was broken" section) is close to publishable prose. The surrounding scaffold sections (Demo Owner, What I Got Wrong, Where This Works) are still in outline/bullet form and aren't ready for readers.

**Three questions to sit with:**

1. **You claim the COO's feedback was "grounded" because he was reacting to real output. Did you actually observe him give different-quality feedback on the demo vs. on a PRD? Or is this the story you want to be true?** If you have a specific contrast — the same person, different quality of response depending on artifact — that's the most powerful evidence in the lesson. If you don't, the claim is a hypothesis, not a finding.

2. **You spent more time, produced denser output, and compressed decisions into a shorter window. What if the reason the old workflow took 4-10 weeks wasn't inefficiency — what if it was the time other people needed to form their own understanding?** You may have traded distributed comprehension for concentrated comprehension. That's a real tradeoff, and the lesson doesn't grapple with it.

3. **The "It's both" admission — enjoyment vs. effectiveness — is a one-paragraph aside. What would happen if it were the center of the lesson?** "I built a 2,383-line spec because I could, and I'm now trying to figure out if I should have" is a more honest and more interesting lesson than "decision compression is better than PRDs." Which one are you actually writing?
