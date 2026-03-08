# Think-Through Critique: Helping Designers Prototype with Claude Code

**Lesson status:** Scaffold
**File:** `lessons/02-designers-prototyping-with-claude-code.md`

---

## Observation vs. Narrative

This lesson is almost entirely narrative. That's partly by design — the scaffold marks it as an early experiment — but the honest assessment is that there are zero grounded observations in the file right now. Every section is either a placeholder or an abstract claim.

Specific calls:

1. **"Natural next question: could designers use this too?"** — Narrative. What actually prompted this? Did a designer see your lesson 01 demo and say something? Did you find yourself wishing a designer could iterate on an output you'd generated? Did you hand a Claude Code prototype to a designer and watch them react? The "natural next question" framing hides the actual origin. The real moment matters because it determines whether this lesson is about a pull (designers wanting this) or a push (you wanting designers to use it).

2. **"The prompt is the spec" (section heading)** — This is a claim that sounds good but has no observation underneath it. Have you actually seen a designer write a prompt to Claude Code? If not, this is a hypothesis, not an observation. The scaffold's own "Think through" prompt already calls this out, which is a good sign — but the fact that the prompt is there unanswered means this section is currently empty thinking.

3. **"The fear of 'code'"** — Same issue. The scaffold asks "Is this a real barrier I've observed, or am I assuming it based on stereotypes about designers?" That's the right question. But it's unanswered. Right now the section heading *is* the stereotype — it presupposes the barrier exists before checking whether it does.

4. **"PMs want directional answers fast. Designers want craft control."** — This is a tidy dichotomy that feels true but might not be. Some designers want speed too. Some PMs care about craft. This line risks flattering both audiences without saying anything precise. What specific moment made you think designers want something different from what you wanted?

**Bottom line on grounding:** The lesson is honest about being early, which is good. But every section currently reads as "things I believe are true" rather than "things I've seen happen." The scaffold's own "Think through" prompts are doing the right work — none of them have been answered yet.

---

## Depth

The current framing is: *Claude Code could help designers prototype faster.* That's the surface-level version. Here are two alternative framings that might cut deeper:

**Alternative framing 1: "I tried to give designers my tool and learned that adoption is not enthusiasm."**
The more uncomfortable version of this lesson might be about what happens when a PM who's excited about a tool tries to get others to use it. The open question "Am I projecting my own enthusiasm onto designers who didn't ask for this?" is buried in line 13 as a secondary bullet. That might actually be the lead. The lesson underneath the lesson could be about the difference between a tool that works for you and a tool that works for your team — and how PMs mistake the former for the latter.

**Alternative framing 2: "The real bottleneck isn't prototyping speed — it's the handoff conversation."**
If Claude Code lets a PM generate an interactive prototype and hand it to a designer, the interesting question isn't "is the prototype good?" but "what happens to the conversation between PM and designer?" Does it get better because there's something concrete to react to? Or does it get worse because the PM has already committed to a direction before the designer was involved? This framing would make the lesson about collaboration dynamics, not tool adoption — which is more durable and more interesting for a PM audience.

Both of these framings require you to have actually tried something and watched what happened. The lesson can't go deeper until the experiment does.

---

## Gaps

### Unanswered "Think through" prompts

Every single "Think through" prompt in the scaffold is unanswered. There are five of them. They're good prompts — they're doing exactly what scaffolds should do, which is preventing you from writing before you've thought. But they need responses before any section can become prose. The most critical ones to answer first:

1. **"What specific moment or friction made me think 'a designer should be able to do this'?"** — This is the origin story. Without it, the lesson has no anchor.
2. **"Am I writing about what I've done, or what I imagine doing?"** — This is the honesty check. The answer right now appears to be "mostly imagining," and the lesson should own that explicitly rather than structuring itself as if it has findings.

### Missing counterarguments

- The scaffold mentions "Figma is already fast. Why add another tool?" but doesn't engage with it. This is the strongest objection a designer would raise, and it deserves real treatment.
- There's no mention of what happens when the AI-generated prototype is *bad* — when it has wrong spacing, inconsistent components, or interactions that don't match the design system. For a designer, "close but wrong" can be worse than "not started" because now someone expects them to fix it rather than design it properly.
- The open question about "cleaning up AI output that's close but wrong" (line 68) hints at this but doesn't frame the risk: if the PM generates a prototype, the designer's role shifts from *creator* to *editor of someone else's output*. That's a fundamentally different job, and some designers will hate it.

### Structural gap

The lesson lists "What's actually happened" and "What's still hypothetical" as subsections but both are empty. This is the most important structural distinction in the piece. Until those are filled in, there's no way to know what the lesson is actually about versus what it's speculating about.

### Missing voice: the designers

There are no designer quotes, reactions, or perspectives in this scaffold. The lesson is called "Helping Designers Prototype with Claude Code" but is written entirely from the PM's perspective. At minimum, one concrete designer reaction — even a skeptical one — would ground the entire piece.

---

## Audience Readiness

**Would a PM who's never used Claude Code understand why this matters?**
Not yet. The lesson assumes the reader has context from lesson 01 (it links to it) but doesn't stand alone. A reader needs to understand what Claude Code prototyping looks like before they can evaluate whether designers should try it. One concrete example — "I prompted Claude Code with X and got Y, and then I wondered what would happen if a designer had written that prompt instead" — would bridge the gap.

**Is there enough context?**
No. The lesson doesn't describe what a Claude Code prototype actually looks like, how it differs from a Figma prototype, or what the designer's actual experience of using it would be. These aren't cosmetic details — they're the core of the argument.

**What's the one line that would make someone share this?**
Nothing yet. The closest candidate is the open question on line 67: *"Is 'designer uses Claude Code' the right frame, or is it 'PM and designer collaborate through Claude Code'?"* That reframe is genuinely interesting. If the lesson eventually lands on a sharp answer to that question, that could be the hook.

---

## Verdict

**Not ready.**

This is an honest, well-structured scaffold with strong "Think through" prompts that are doing their job. But it's a scaffold with nothing filled in. There are no observations, no grounded experiences, and no answered questions. The lesson correctly identifies that the experiment is too early — the file should stay in scaffold state until there's something real to report.

### Three questions to sit with

1. **Have you actually put Claude Code in front of a designer yet?** If yes, what happened — not what you think it meant, but what the designer literally said and did? If no, that's the next step, and this lesson should wait.

2. **When you imagine this working, who is the designer in your head?** Is it a specific person on your team, or an abstract "designer"? If it's abstract, you're designing a workflow for a person who doesn't exist. If it's specific, what do you know about how *that person* works that makes you think this would help them?

3. **Are you writing this lesson because you learned something, or because you want to learn something?** Both are valid, but they're different documents. If it's the latter, the honest move is to keep this as a watching brief — a list of what you're testing and what you're looking for — rather than shaping it into a lesson that implies findings.
