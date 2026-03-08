# /draft — "The Problem This Solves"

## Section Under Review

From `lessons/01-building-demos-with-claude-code.md`:

```
## The Problem This Solves

- Old workflow: PM waits for vague idea from management. Writes PRD in a format boss won't read. Discusses with boss — ineffective. Designers and engineers not involved at all.
- The PRD is theater. It serves a bureaucratic function, not a thinking function.
- By the time the idea becomes concrete enough to react to, weeks have passed.
```

The scaffold also includes this prompt:
> **Think through:** What specifically made the old workflow ineffective? Was it the format (document), the timing (too late), the abstraction (too vague), or the people (wrong audience)?

---

## Questions I'd Ask Before Writing

**1. What did a typical PRD cycle actually look like — in calendar time and in handoffs?**

The lesson mentions "4-10 weeks" later (in the "Why this matters" subsection under Core Insight), and describes the chain: PM writes spec based on assumptions, designer interprets it, engineer discovers the API doesn't work that way, it escalates back. But those details live in the middle of the lesson, not here at the top. The opening section needs to establish the pain concretely. Was there a specific project where this played out badly? The lesson mentions "50% of the time we got it wrong and had to adjust last minute. Sometimes it was a disaster." That's vivid — but what's one actual disaster? Without that, "the old workflow was broken" is an assertion, not evidence.

**2. When you say the PRD is theater — theater for whom?**

This is the sharpest bullet in the section, but it needs to land harder. Who was the PRD serving? Was the boss requesting it? Was it a company norm? Was there a moment where you realized nobody was actually using the PRD to make decisions — that the real decisions happened in a meeting or a Slack thread or when the engineer hit the first API wall? The "Think through" prompt asks whether the problem was format, timing, abstraction, or audience. Based on the rest of the lesson, the answer seems to be "all of them, but especially abstraction" — the PRD let everyone stay vague, and vagueness only got resolved when someone tried to build the thing. Is that right?

**3. What was your specific role in the broken workflow — and what did it feel like?**

The lesson later says you were proud of the work you put into the Pokemon agent demo. That implies some contrast with how the old workflow felt. Were you writing PRDs you knew wouldn't land? Were you frustrated at being a document-production middleman between management and engineering? Or was it more subtle — you didn't realize the workflow was broken until you accidentally found a better one?

---

## Suggested Prose

Based on what the rest of the lesson reveals, here's a draft for this section. Every sentence traces to something written elsewhere in the file — but flag anything that doesn't match your actual experience.

---

Here's how product development worked before. Management floated a vague idea. I wrote a PRD — a document formatted for a process, not for the person who needed to make a decision. My boss wouldn't read it in that format, and I knew that going in. Designers and engineers weren't in the room yet. I was writing for a handoff chain that hadn't started.

The PRD served a bureaucratic function, not a thinking function. It let everyone stay abstract. "Marketers can pin merchants to the homepage" — that's a sentence you can write in a PRD, and everyone nods. Nobody has to answer what actually happens when a marketer pins a merchant that's already ranked #3, or when two marketers pin different merchants to the same slot. The hard questions didn't surface until an engineer tried to build it, which was weeks later.

That's the core problem: decisions took 4-10 weeks to surface. I'd write a spec based on assumptions. A designer would interpret it. An engineer would start building and discover the API didn't work that way. It escalated back. We only caught misalignment with the COO when we had a finished design — and about half the time, we got it wrong and had to adjust last minute.

By the time the idea became concrete enough for anyone to react to with real feedback, the calendar had moved on and the cost of changing direction had gone up.

---

## Readback & Flags

- **"a document formatted for a process, not for the person who needed to make a decision"** — this is inferred from the bullets but not something you explicitly said. Does this match? Or was the PRD actually addressed to the boss, just in a format he wouldn't engage with? The distinction matters: one is a process problem, the other is a communication problem.

- **The merchant pinning example** — I pulled this from the Core Insight section to make the "staying abstract" point concrete. It works well here as a preview, but check whether you want to use it twice. If this example appears in the opening, it might lose impact when it comes back in the Core Insight section. You could swap in a different example here, or keep it and cut the repetition later.

- **"about half the time, we got it wrong"** — this is a direct pull from later in the lesson. It's strong and specific. But "sometimes it was a disaster" is even more interesting — do you have one disaster you'd name? A single sentence about a specific project that went sideways would anchor this entire section.

- **The last sentence** ("the calendar had moved on and the cost of changing direction had gone up") is the most generic line in this draft. It's true but it could appear in any article about product development. Consider cutting it or replacing it with something specific to your experience — what did "cost of changing direction" actually look like at Buy&Ship?

## Does this sound like you?

The tone is direct and the structure is tight. But the section is still mostly describing a general PM workflow problem — it doesn't yet have a moment that's distinctly yours. The rest of your lesson is full of those moments (the Pokemon API discovery, the 13 golden conversations, the COO seeing real data). This opening section needs at least one anchoring detail that says "this is my specific experience, not a blog post about why PRDs are bad."
