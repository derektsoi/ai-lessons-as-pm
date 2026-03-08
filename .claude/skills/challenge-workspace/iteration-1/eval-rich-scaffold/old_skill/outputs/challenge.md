# Adversarial Review: Building Product Demos with Claude Code

---

## Challenge 1: "Decision Compression" Is Doing a Lot of Heavy Lifting

**Claim:** The core insight is "decision compression" — that building demos with Claude Code collapses weeks of iterative decision-making into days, because a working demo forces you to confront specifics a PRD can skip.

**Strongest counter-argument:** What you're describing isn't decision compression. It's decision *front-loading*. You moved the same decisions earlier in the timeline. The total number of decisions didn't shrink — you say yourself you did "more work, not less." Compression implies you're getting the same output in less space. What actually happened is you shifted the work from a distributed process (PM → designer → engineer → correction loops) to a concentrated one (PM alone with Claude Code). That's a different claim with different implications.

The real question: is front-loaded judgment by one person actually better than distributed judgment across a team over 10 weeks? You assert it is because the COO got "real answers" and stakeholders gave "grounded feedback." But those are outputs. The mechanism you're crediting — solo PM judgment applied early — is exactly the thing your "What I Got Wrong" section flags as risky. You can't claim the mechanism is both the insight and the risk without resolving the tension.

**Verdict: Weakness to acknowledge.** The term "decision compression" is catchy but misleading. You compressed the *timeline*, not the *decisions*. The decisions just happened in a different shape — concentrated rather than distributed. That's a meaningful distinction because it changes who you'd recommend this to and when.

---

## Challenge 2: You Have a Sample Size of Two, and Both Worked

**Claim:** This approach produces better outcomes than the old PRD workflow.

**Strongest counter-argument:** You built two demos. Both went well. You have zero examples of this approach failing. Your "Where This Approach Works (and Doesn't)" section is entirely theoretical — you even flag this yourself with the "Think through" prompt at the end. But that honesty doesn't fix the problem.

Survivorship bias is loud here. You're writing this lesson *because* the Pokemon demo impressed the COO and the merchant mockups were useful. If the COO had looked at your 13 Golden Conversations and said "this is overengineered, I just wanted a one-pager," would you be writing about decision compression? Or would you be writing about how PMs can over-invest in demos?

You also chose two projects that seem unusually well-suited to this approach: one had external APIs you could actually call, and the other was a visual feature where HTML mockups would obviously communicate better than a PRD. What about the majority of PM work that doesn't look like this — internal tooling changes, pricing experiments, operational workflow improvements, features that are small adjustments to existing behavior?

**Verdict: Weakness to acknowledge.** The lesson reads like a general method discovered through two confirming examples. It's more honest as: "I tried something on two well-suited projects and it worked. Here's what I learned. I don't yet know the boundaries." You partially do this, but the "Core Insight" section is written with the confidence of a pattern, not an experiment.

---

## Challenge 3: Attribution Error — Claude Code vs. Your Effort

**Claim:** Claude Code enables PMs to build demos that compress decisions. The tool is central to the approach.

**Strongest counter-argument:** Strip Claude Code out of this story. What you actually did was: (1) refused to write a PRD, (2) built concrete artifacts instead, (3) tested real APIs before involving engineers, (4) showed stakeholders something tangible early.

A PM who's good at Figma, knows Postman, and is willing to put in the hours could do the same thing. A PM who convinced a designer to pair with them for two days could do the same thing. You even mention that you and designers "start working on a demo together" — so Claude Code isn't the only tool in play.

The lesson might really be: "PMs should build concrete artifacts early instead of writing PRDs, and they should test their assumptions against reality before handing off." Claude Code makes that cheaper for PMs who can't design or code, but it's the practice, not the tool, that matters.

Someone who disagrees with you would say: "You're giving credit to a tool for what was actually a change in your *process and mindset*. Any PM who decided to stop writing PRDs and start testing APIs manually would get 80% of the benefit you describe."

**Verdict: Valid tradeoff, but under-examined.** Claude Code lowers the barrier, which matters. But the lesson buries the behavioral change (stop writing PRDs, start building) under the tool story (Claude Code lets you do X). If Claude Code disappeared tomorrow, would you go back to PRDs? If not, the real lesson isn't about Claude Code.

---

## Challenge 4: The Cost Accounting Is Still Incomplete

**Claim:** "I did more work, not less. I compressed decisions." The cost section acknowledges this honestly.

**Strongest counter-argument:** You list what you produced — thousands of lines of spec, 13 conversations, 5 tech spikes, sequence diagrams. But you don't quantify the *time*. How many hours did the Pokemon demo take? How many hours would a PRD have taken? You claim the trade is "more PM time upfront, less iteration time later" — but you don't have the "later" data yet. The projects haven't shipped. You're comparing measured upfront cost against *projected* savings.

There's also an opportunity cost you don't address. While you were writing 2,383 lines of agent I/O specification and 13 Golden Conversations, what weren't you doing? Were there other products that needed PM attention? Is the implicit argument "a PM's time is best spent going deep on one project" or is it "this is what I chose to spend time on because I enjoy building"?

Your "It's both" section gestures at this but doesn't resolve it. "I enjoy this" combined with "the output is better" is a convenient conclusion. How would you know if you were over-investing because you enjoy it? What would the signal look like?

**Verdict: Weakness to acknowledge.** The cost section is more honest than most people would write, but it's still missing the denominator. Hours spent, opportunity cost, and — critically — whether the projected time savings in later phases actually materialize. You should flag this as an open question, not a resolved trade.

---

## Challenge 5: The "Demo Owner" Framing Might Be Solving Your Problem, Not a General One

**Claim:** "Anyone with an idea can be demo owner." The demo owner builds, the business owner decides.

**Strongest counter-argument:** You're a PM who enjoys building, has deep domain context, and is willing to write 2,383 lines of spec. You are not a representative PM. The "demo owner" concept assumes someone who (a) has the product judgment to test the right things, (b) has the patience to build at this level of detail, and (c) won't accidentally pre-empt engineering decisions while doing it.

Engineering's pushback might be right. When a PM shows up with 13 Golden Conversations, 5 tech spikes, and sequence diagrams, saying "I'm just the demo owner, you own the how" — the "how" has already been substantially constrained by the "what." You defined the API call order, the data flow, the conversation structure. An engineer looking at that might reasonably say: "You didn't leave me architecture decisions. You left me implementation details."

The distinction between "what the product does" and "how it works" gets blurry fast when the demo includes sequence diagrams and API contracts. You acknowledge this in the "Think through" prompt, but the lesson doesn't resolve it.

**Verdict: Incomplete.** The demo owner concept needs stress-testing with someone who isn't you. The question isn't whether it works when Derek does it — it's whether the *framework* works when a less experienced PM, a designer, or a marketer tries it. Your own success might be an argument against generalizing it.

---

## Challenge 6: The Uncomfortable Question

**What you might be avoiding:** You built something impressive and your COO liked it. That feels good. But there's a version of this story where you've created a workflow that depends entirely on you — your judgment, your willingness to go deep, your comfort with Claude Code. The "demo owner" concept sounds democratic ("anyone can do it"), but your own examples suggest it requires a specific kind of person with a specific skill set.

The uncomfortable edge: you might be building a process that makes you indispensable rather than one that makes the team better. If you left tomorrow, could anyone at Buy&Ship replicate what you did with the Pokemon demo? If the answer is no, then "decision compression" is really "Derek compression" — and that's a different lesson with different implications for what you should do next.

---

## The lesson survives if:

1. You rename or redefine "decision compression" to be honest about what's actually happening — *front-loading of judgment*, not compression of decisions. The total work went up.

2. You hold the two-project sample size openly throughout, not just in the caveats section. The Core Insight section should read as "here's what I observed" not "here's how product development works now."

3. You separate the *practice* (build concrete artifacts, test assumptions early) from the *tool* (Claude Code) and give appropriate credit to each. The practice is the lesson. The tool is the enabler.

4. You follow up after shipping to report whether the projected time savings in later phases actually materialized. Without that data, the cost argument is half-finished.

5. You address engineering's pushback as a real concern, not a framing problem. The question isn't whether "demo owner vs. business owner" is a clean distinction — it's whether your demos leave enough architectural space for engineers to actually own the "how."
