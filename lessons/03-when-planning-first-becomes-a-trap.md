# When Planning-First Becomes a Trap

> Status: Scaffold — core tension identified, needs grounding in specifics

## The Setup

- Lesson 01 established that planning-first works brilliantly for product demos: test APIs, write golden conversations, compress decisions before engineering starts.
- I tried applying the same instinct to building AI agent workflows — multi-agent skills for an HTML builder pipeline.
- It broke. The planning document grew to 3,000 lines. I still couldn't tell if the thing was buildable.

**Think through:** What made me confident in lesson 01's approach? Was it the planning itself, or was it that I could validate every decision in seconds?

---

## What Happened

### The Pokemon agent (lesson 01) — planning worked

- APIs have predictable inputs and outputs. I could call an endpoint, see the response, adjust.
- Each validation cycle: seconds. I could iterate 20 times in an hour.
- Golden conversations were testable — I could say "this API returns this data, so this conversation is grounded in reality."
- Planning felt productive because every planning decision could be checked immediately.

### The AI skill builder — planning broke

- I wanted to decompose a monolithic workflow into 5 skills with multiple agents.
- Each run of the HTML builder takes ~30 minutes. If it fails, I've lost half an hour and I'm not sure why.
- Outputs are non-deterministic — I can't write a "golden conversation" for what an agent should say when reviewing a contract, because the answer is different every time.
- My instinct: plan more thoroughly to reduce the number of 30-minute cycles. But more planning didn't increase confidence — the document just grew.
- I couldn't rely on TDD. Skills produce open-ended responses. There's no assertion to write.

**Think through:** At what point did you realize the plan was growing without converging? Was there a specific moment where you thought "this isn't working"?

---

## The Core Insight

Decision compression (lesson 01) requires two things I didn't notice at the time:
1. **Fast feedback loops** — seconds, not 30 minutes
2. **Deterministic outputs** — the same input produces the same output, so you can validate

When both are missing, the planning instinct doesn't compress decisions — it just produces more documentation. The 3k-line plan was my attempt to substitute specification for validation. It doesn't work.

### The overengineering trap

Research supports this:
- 79% of multi-agent system failures originate from specification and coordination issues, not technical implementation (CMU/Stanford study).
- If each agent step is 85% accurate, a 10-step workflow succeeds ~20% of the time (compound error math).
- "If you can write down the exact sequence of steps in advance, you're building a workflow, not an agent" — and workflows are almost always cheaper and more reliable.

**Think through:** How many of my 5 planned skills are actually agents (need judgment, open-ended) vs workflows (predictable steps I could script)? Would simplifying the architecture have been the right move from the start?

---

## What I'm Still Figuring Out

### Can I test slices instead of full runs?

- With the Pokemon agent, I tested individual API calls before building the full workflow.
- Can I do the same here? Test a single skill in 2 minutes instead of running the whole 30-minute pipeline?
- I haven't tried this yet. That's my next experiment.

### When should I stop planning and just ship?

- The research says most LLM-powered systems ship with no meaningful test coverage. That's the state of the industry.
- Block Engineering's testing pyramid: deterministic unit tests at the base, record-and-replay in the middle, LLM-as-judge evals at the top. The shift is from "is this the right answer?" to "is this a good enough answer?"
- Maybe the right move is: plan the boundaries (what each skill owns), accept uncertainty about the outputs, ship, observe, iterate.

### Am I overengineering because I'm a PM?

- The PM instinct is "plan thoroughly, then hand off." That works when the system is predictable.
- The same instinct is pulling me toward more agents, more skills, more specification — when the winning move might be fewer agents, simpler boundaries, less specification.
- The lesson might not be "plan better" but "plan less and accept that some things can only be learned by running them."

**Think through:** What would a v1 look like if you gave yourself permission to ship something embarrassingly simple? What's the minimum that would teach you something?

---

## The Meta-Lesson

The same PM instinct that compressed my product decisions in lesson 01 is inflating my AI architecture in this project. The hard part isn't planning better — it's knowing when to stop adding complexity.

**Think through:** Is this lesson actually about AI, or is it about a PM tendency to over-specify when facing uncertainty? Would this lesson apply equally to a non-AI project where validation is slow?

---

## Raw Material & References

- HTML builder skill planning docs: 3k+ lines, v9.1 with 5+ independent review passes
- Vertical slice task decomposition: slices 1-6 (new pattern, untested)
- Skill creator with internal A/B testing: used for agent-team skill trigger optimization
- Research: CMU/Stanford multi-agent failure study, Block Engineering testing pyramid, Louis Bouchard on overengineering
