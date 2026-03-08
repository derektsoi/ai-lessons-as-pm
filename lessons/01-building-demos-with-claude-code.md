# Building Product Demos with Claude Code

> Status: Scaffold — core insight sharpened after challenge round, sections need expanding

## The Problem This Solves

- Old workflow: PM waits for vague idea from management. Writes PRD in a format boss won't read. Discusses with boss — ineffective. Designers and engineers not involved at all.
- The PRD is theater. It serves a bureaucratic function, not a thinking function.
- By the time the idea becomes concrete enough to react to, weeks have passed.

**Think through:** What specifically made the old workflow ineffective? Was it the format (document), the timing (too late), the abstraction (too vague), or the people (wrong audience)?

---

## What I Do Now

- Once I understand what management wants, PM and designers start working on a demo together.
- The demo is used directly to discuss with designers, engineers, stakeholders, and users.
- The role of "demo owner" is for anyone who has an idea — not just PMs. There's pushback from engineering on this. I don't know if it's right yet. I'm experimenting.
- The demo owner builds. The business owner (e.g., COO) decides. These are different roles.

### Two examples

**Trending Merchants (quarterly planning demo):**

- Boss gave feedback on the feature. Instead of writing a PRD, I used Claude Code to generate HTML+Tailwind mobile mockups.
- Connected Figma MCP to read real design tokens. Built a component library from our design system. Used agent teams (4 generators + 3 reviewers) to produce 8 structural variations.
- _Expand on: what happened when stakeholders saw the mockups. Did the framing ("directional concept, not a design") work?_

**Pokemon Shopping Agent (AI product demo):**

- Built a demo for a Pokemon card shopping chatbot. Lead engineer and COO are both the users.
- Wrote 13 Golden Conversations — scripted user dialogues that are simultaneously the demo, the acceptance tests, AND the spec.
- Rendered the golden conversations in HTML to present to COO.
- But the demo was just the visible surface. Underneath: 5 tech spikes testing real APIs, sequence diagrams mapping data flow, a 2,383-line agent I/O specification.

---

## The Core Insight: Decision Compression

I didn't set out to change how I write specs. I was building a demo for the Pokemon shopping agent — scripting conversations that showed how a user would find and buy a Japanese Charizard card through our chatbot. Somewhere in the middle of that, I realized I wasn't writing a demo anymore. I was writing the spec.

The 13 Golden Conversations I scripted aren't a presentation. Each one defines exactly how the product should behave — what the user says, what the agent responds, what data it pulls, from which API, in what order. They're acceptance tests that happen to be readable by a COO. I think of them like TDD for LLM products: you can't spec LLM behavior declaratively ("be helpful but concise" means nothing), but you can show what good looks like through a concrete example.

The spec and the demo co-evolved. Every time I built a conversation, I'd test the real APIs through Claude Code and discover something the spec needed to say. Every time I updated the spec, it changed the demo. I didn't write a requirements doc, hand it off, and wait. I was doing both at once, and each one made the other better.

Claude Code handles the mechanical parts — browsing API documentation, calling endpoints, handling authentication. I don't need to know Postman. What I bring is product judgment about what to test and what matters. I discovered that all the Pokemon APIs use different card identification standards. The price API has one, the card catalog has another, the photo recognition returns a third. This meant the architecture needed a middle LLM layer to translate between them. I found this before any engineer touched the project.

The sequence diagrams are my thinking tool, not an engineering deliverable. Engineers write their own. Whether EN vs JP card identification is a phase-1 problem (identify the card) or a phase-2 problem (choose the price) changed how we call APIs and what information the LLM has at each stage. That decision came from thinking through the diagram and testing the APIs at the same time.

### This isn't specific to AI products

The merchant pinning project made this even clearer. A marketer pins a merchant to the homepage — sounds simple. I started building the demo thinking it was. Then I saw the HTML output and realized: what happens when a marketer pins a merchant that's already ranked #3? What about pinned merchants that conflict with the data-driven ranking? What about multiple marketers pinning different merchants?

I wrote 15 test cases before sharing anything with engineers. Each one set up mock merchant data to show how the logic would handle a specific scenario. I wouldn't have written those test cases from a blank PRD — I didn't even know the edge cases existed until the demo forced me to confront them.

This is what I mean by decision compression. It's not about speed. It's that a working demo doesn't let you be vague. A PRD can say "marketers can pin merchants to the homepage" and everyone nods. A demo has to answer: what actually happens when they do?

### Why this matters: the old workflow was broken

In the old workflow, decisions took 4-10 weeks to surface. A PM writes a spec based on assumptions. A designer interprets it. An engineer starts building and discovers the API doesn't work that way. It escalates back. We only caught misalignment with the COO when we had a finished design — and not every product even got a design critique session with the COO. I'd say 50% of the time we got it wrong and had to adjust last minute. Sometimes it was a disaster.

Now, the COO sees a demo grounded in real API calls in the first few sessions. When he asks "can it do X?" — the answer is based on an API call I already made, not a guess. The stakeholders are reacting to real output, not wireframes of idealized flows. Their feedback is grounded too — they can't say "make it smarter," they have to point to a specific conversation and say "this answer is wrong because X."

I did more work, not less. The output is denser — thousands of lines of spec, 13 scripted conversations, 5 tech spikes, sequence diagrams. But the PRD is no longer the main artifact. The spec and the demo are the thinking. The PRD is a by-product Claude Code can generate from the work I've already done.

I'm proud of the work I put into figuring out what may not work before engineering starts. Of course bugs will be found during development. But I've eliminated an entire category of "oh wait, this API doesn't cover vintage cards" surprises.

---

## The "Demo Owner" Experiment

- Anyone with an idea can be demo owner. I have pushback from engineering.
- My answer (still testing): demo owner builds, business owner decides.
- The golden conversations work for a first draft. What I need at that stage is to hear what the COO and users want. Edge cases are relevant later — COO and users can't think through that level of detail yet.

### Engineering's role (working this out)

The demo defines *what the product does*. Engineering owns *how it works*. The golden conversations are the contract between those two — product says "this is what the user should experience," engineering says "here's what's feasible, here's what needs to change, here's what you missed."

Everything outside the golden conversations — architecture, implementation, error handling, scale — is engineering's domain to challenge and own.

**Think through:**

- Does this framing actually address engineering's concern? Or does it still feel like the PM has pre-empted technical decisions?
- What would make engineering's pushback right? When would this create problems?
- Signal that this works: someone other than you voluntarily builds a demo. Signal that it fails: you're the only one doing it and it becomes "Derek's thing."

---

## What I Got Wrong (or Am Unsure About)

### The "I don't need technical details" claim needs scoping

I said I don't need to understand API authentication or Postman. That's true for mechanical details. But I'm now building specs and sequence diagrams that engineers implement. The line between "technical details I can safely skip" (auth plumbing, request formatting) and "technical understanding I need" (how APIs behave under load, error conditions, pagination at scale) is real and I haven't drawn it carefully enough.

What I validated: this API returns this data in this format when called this way. What I assumed: this will work at scale, under error conditions, with production authentication. The spec should flag its own confidence levels.

### Cost accounting — honest version

I didn't save time. I compressed decisions. The total work output is higher than a PRD — thousands of lines of spec, 13 conversations, 5 tech spikes, sequence diagrams. But the COO conversation was productive because I had real answers. Future discussions are shorter because the hard questions are already answered. The PRD is a by-product, not the main artifact.

The trade: I spent more PM time upfront. I'll spend less time in the 4-10 weeks of iteration that usually follows a PRD. Whether that's a good trade depends on whether the upfront thinking was right. Which leads to...

### Judgment is higher-leverage and higher-risk now

In the old workflow, my product judgment got applied gradually over 4-10 weeks. I'd make a decision, see it interpreted by a designer, react, adjust, see it built by an engineer, react again. The slow iteration was a safety net — my judgment didn't need to be sharp upfront because there were many correction points.

Now I jump almost to the end. The demo is concrete. The spec is detailed. The API contracts are tested. By the time anyone else sees it, I've already made dozens of product decisions baked into the golden conversations. If my judgment is wrong, it's wrong at scale and it looks authoritative because it's grounded in real data.

This is fine for me right now — I have the context and domain knowledge to make these calls. But it raises a question I'm not ready to answer yet: what happens when someone with less product taste uses this approach? The old safety net of slow iteration is gone, and we don't have a replacement yet. _(Future lesson — not solving this here.)_

### It's both

The honest answer to "are you doing this because it produces better decisions or because you like building?" is both. That's fine — but I should be honest about which one drives me on any given day, because "I enjoy this" is not the same as "this is the right use of PM time."

---

## Where This Approach Works (and Doesn't)

_The challenge round flagged that two projects isn't a general method. Be honest about scope._

**Works when:**

- External APIs with discoverable behavior (you can test them)
- Stakeholders who respond to visual/interactive demos
- PM has deep domain context (judgment about what to test is calibrated)
- Greenfield features or significant redesigns (enough surface area to explore)

**Might not work when:**

- Internal system behavior that can't be tested from the outside
- Incremental improvements to existing features (a PRD might actually be faster)
- PM is new to the domain (product judgment about what to test is poorly calibrated — and the output will still look authoritative)
- Non-visual products where a demo doesn't communicate the value

**Think through:** Have you tried this and had it fail? If not, these boundaries are theoretical. Watch for the first failure — that's when the lesson gets real.

---

## The Lesson (Draft — Refine This)

_Previous framings (superseded):_

- ~~"AI lets PMs prototype structural ideas without waiting for a design sprint"~~ — too generic, could be any prototyping tool
- ~~"The value isn't the mockup, it's having something concrete to react to"~~ — true but not the real insight
- ~~"Demo, spec, and validation became one thing"~~ — describes the mechanism, not the lesson

_Current framing:_

- **"Claude Code compressed my product development cycle from weeks to days. That sounds like a win — and it is — but it means my judgment has to be right much earlier, with fewer correction points. I did more work, not less. I made better decisions, not faster ones. And the safety net of slow iteration is gone."**

_Alternative (punchier):_

- "The demo is evidence, not a presentation. But evidence created by one person's judgment, without the correction loop of a 10-week development cycle, is only as good as that judgment."

**Think through:** The lesson has two halves — the power (decision compression, evidence-based demos) and the risk (judgment is higher-leverage, safety net is gone). Can they coexist in one article, or do they need to be separate?

---

## If Cross-Posting to Medium

- Title ideas: _TBD after the lesson crystallizes_
- Hook: The Pokemon card API discovery? "I found out our entire architecture needed an LLM translation layer — before any engineer touched the project. Here's how — and why that's not entirely a good thing."
- Key visual: Golden conversation side-by-side with the sequence diagram that informed it? The before/after of old workflow vs new?
- Audience: PMs who've felt the gap between "I wrote a spec" and "does this actually work?"

---

## Raw Material & References

- Pokemon Shopping Agent POC: `/Users/derektsoi/Downloads/20260123_01_pokemon_chatbot_poc`
  - Golden Conversations: `01_requirements/agent_io_specification.md`
  - Sequence diagrams: `02_design/d1_d2_sequence_diagrams.md`
  - Tech spikes: `08_tech_spikes/`
  - COO presentation: `10_coo_presentation/coo_presentation.html`
- Trending Merchants plan: `/Users/derektsoi/Downloads/00-plan.md`
- Trending Merchants demo: `/Users/derektsoi/Downloads/bundle.html`
