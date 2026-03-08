# Adversarial Review: Building Product Demos with Claude Code

---

## Challenge 1: "Decision compression" may just be "decision front-loading" — and the old workflow wasn't as broken as you're claiming

**The claim:** "I didn't set out to change how I write specs... I was writing the spec." The core argument is that demos, specs, and validation collapsed into one artifact, compressing a 4-10 week decision cycle.

**The strongest counter-argument:** You're comparing your best new workflow against your worst old workflow. The old process you describe — PM writes spec based on assumptions, designer interprets it, engineer discovers API doesn't work, it escalates — is a dysfunctional version of waterfall, not the only alternative. A team that does weekly design critiques, involves engineering early in discovery, and runs lightweight spikes already compresses decisions without any AI tooling. The question isn't "is my demo workflow better than a broken PRD process?" — it's "is my demo workflow better than a well-run discovery process?" You haven't compared against that.

You also say "I'd say 50% of the time we got it wrong and had to adjust last minute." That's a damning number — but is it accurate, or is it how it felt? Did you actually track this? If you're reconstructing a failure rate to justify the new approach, you're building a narrative, not citing evidence.

**Verdict: Weakness to acknowledge.** The lesson isn't wrong, but the "before" picture may be exaggerated to make the "after" look better. The honest framing is: "My team's old process was particularly bad at surfacing decisions early. This approach fixes that. Teams with better discovery processes may get less dramatic improvement."

---

## Challenge 2: You did this twice. Two projects is not a method.

**The claim:** The lesson presents "decision compression" as a repeatable approach, with a "works when / doesn't work when" framework that implies generalizability.

**The strongest counter-argument:** You built two demos. One was a set of HTML mockups for a quarterly planning discussion. The other was a deep AI product spec. These are very different types of work, and you're pattern-matching across them to extract a general principle. But two data points drawn from the same person, at the same company, in the same quarter, with the same stakeholders, is not a pattern — it's a coincidence waiting to be tested.

The "Where This Approach Works (and Doesn't)" section is honest about this being theoretical. But the rest of the lesson doesn't read that way. "Decision compression" has the cadence of a coined term, a portable framework. You haven't earned that yet. You've earned "here's what happened when I tried something twice."

The scaffold itself flags this: "Have you tried this and had it fail? If not, these boundaries are theoretical." That question is doing more work than the answer. You should lead with it, not bury it at the bottom.

**Verdict: Weakness to acknowledge.** The observation is real. The generalization is premature. You can keep the lesson, but the framing should be "here's what I'm watching for" rather than "here's how it works."

---

## Challenge 3: Attribution error — is this Claude Code or is this you?

**The claim:** "Claude Code handles the mechanical parts — browsing API documentation, calling endpoints, handling authentication. I don't need to know Postman. What I bring is product judgment about what to test and what matters."

**The strongest counter-argument:** The real differentiator in your Pokemon project wasn't Claude Code. It was that you, a PM, voluntarily spent the time to explore APIs, write 13 scripted conversations, build sequence diagrams, and create test cases. That's unusual PM behavior. Most PMs wouldn't do this with or without AI tooling — not because they lack the tools, but because they don't think it's their job, or they don't have the curiosity, or their org doesn't reward it.

Claude Code made the mechanical parts easier. But the hard part — the decision to go deep, the judgment about what to test, the willingness to do "engineering-adjacent" work — that's all you. A different PM with Claude Code would have produced a prettier PRD, not 13 Golden Conversations. A technically curious PM without Claude Code might have done something similar with Postman, curl, and more time.

The lesson risks implying "give a PM Claude Code and they'll produce better specs." The honest version is closer to: "I'm a PM who thinks like this, and Claude Code removed friction from a workflow I was already inclined toward." That's a much narrower and less exciting lesson, but it's more honest.

**Verdict: Weakness to acknowledge.** You partially address this in "It's both" — but that section is about motivation (enjoying building vs. it being the right use of PM time), not about attribution. The tool question is different: how much of this outcome is the tool and how much is the person?

---

## Challenge 4: The judgment risk section is too comfortable

**The claim:** "If my judgment is wrong, it's wrong at scale... This is fine for me right now — I have the context and domain knowledge to make these calls."

**The strongest counter-argument:** "This is fine for me right now" is exactly the sentence someone says before it's not fine. You're acknowledging the risk in the abstract and then exempting yourself from it. But have you actually stress-tested your own judgment on these two projects?

For the Pokemon project: you discovered the card ID mismatch across APIs. That's a genuine catch. But what did you get wrong? What did engineering find that you missed? What assumptions in your 13 Golden Conversations turned out to be incorrect once engineering started building? If the answer is "I don't know yet because they haven't built it" — then you can't claim the judgment was right. You can only claim it felt right. And that's exactly the problem you're describing.

For the merchant pinning project: you wrote 15 test cases before showing engineers. How many of those test cases survived contact with the actual implementation? How many edge cases did engineers find that you missed?

The section reads like you're flagging the risk so you can move past it. But the risk is the most interesting part of the lesson. If you're going to claim your judgment is "fine for now," show the evidence — not just the catches, but the misses.

**Verdict: Weakness to acknowledge, bordering on fatal flaw if left unaddressed.** The lesson's credibility depends on you being honest about your own misses, not just your catches. Right now it reads like a highlight reel with a footnote about risk.

---

## Challenge 5: "The PRD is theater" is a straw man

**The claim:** "The PRD is theater. It serves a bureaucratic function, not a thinking function."

**The strongest counter-argument:** PRDs are theater when they're written as theater. A PRD written by a PM who hasn't done the thinking is bad — but that's a people problem, not a format problem. Plenty of PMs write PRDs that are genuine thinking artifacts. The best PRDs force you to articulate assumptions, define scope, and make tradeoffs explicit — exactly what you say your demos do.

What you're really saying is: "I found a format that forces me to think more concretely than a document does." That's valid. But dismissing PRDs as inherently theatrical mischaracterizes the tool to justify your alternative. A PRD that includes API test results, edge case analysis, and concrete scenarios would accomplish much of what your demos accomplish — it would just look different.

The more honest claim is: "For the way my team works and the way my COO consumes information, a demo is a more effective thinking and communication artifact than a document." That's still a useful insight. It just doesn't require trashing the alternative.

**Verdict: Valid tradeoff the author should own.** You prefer demos to documents. That's fine. But "PRDs are theater" is too sweeping. Some PRDs are theater. Yours were. That's a narrower claim.

---

## Challenge 6: The "demo owner" concept is undercooked and may be causing real organizational harm

**The claim:** "Anyone with an idea can be demo owner... There's pushback from engineering on this. I don't know if it's right yet."

**The strongest counter-argument:** Engineering's pushback might be more substantive than you're treating it. When a PM builds a demo with 13 Golden Conversations, 5 tech spikes, and sequence diagrams — and then says engineering owns "how it works" — that line is blurrier than you're drawing it. Your sequence diagrams make architectural assertions. Your API tests make feasibility claims. Your golden conversations constrain implementation paths. You've already made technical decisions; you've just framed them as product decisions.

The "demo owner builds, business owner decides" formulation sounds clean, but it may be experienced by engineers as "PM builds, PM decides what the product does, engineer implements." That's a demotion disguised as a framework.

The fact that you're the only one building demos is the signal you identified yourself — "Signal that it fails: you're the only one doing it and it becomes 'Derek's thing.'" But you haven't engaged with why that might be happening. Is it because no one else has Claude Code? Because they don't want to? Because the organizational incentives don't support it? Each of those has a different implication for whether this is scalable or personal.

**Verdict: Weakness to acknowledge.** You're honest that this is experimental. But you're not honest enough about the power dynamics it creates. A PM who shows up with a working demo and 2,383 lines of spec has already won the argument before the discussion starts. That might be efficient or it might be steamrolling. You need to figure out which.

---

## Challenge 7: Cost accounting is still incomplete

**The claim:** "I didn't save time. I compressed decisions. The total work output is higher than a PRD."

**The strongest counter-argument:** You say you'll "spend less time in the 4-10 weeks of iteration that usually follows a PRD." Have you? Has this actually played out? The Pokemon project — has it shipped? Did the compressed front-end actually reduce back-end iteration?

If the project is still in progress, this is a prediction, not a finding. And it's a prediction that confirms what you want to believe. The honest version is: "I believe this will reduce iteration time. I'll know in a few months."

Also missing from the cost accounting: what else didn't you do while spending PM time on API testing, sequence diagrams, and scripting 13 conversations? Opportunity cost is cost. If you spent two weeks on deep demo work, what got deprioritized? Was that the right tradeoff?

**Verdict: Weakness to acknowledge.** The cost section is more honest than most people would write. But it's still forward-looking where it should be backward-looking. You can't claim the tradeoff is worth it until the project ships and you can compare actual timelines.

---

## The lesson survives if...

The author can demonstrate three things:

1. **The judgment was actually tested, not just applied.** Show what you got wrong on these two projects, not just what you caught. If engineering hasn't built yet and you can't cite misses, say that — and acknowledge the lesson is incomplete until you can.

2. **The comparison is fair.** Compare against a well-run discovery process, not just your team's broken PRD workflow. If the lesson is "this is better than what we were doing," own that it's a local improvement, not a universal one.

3. **The tool vs. person question is answered honestly.** What percentage of this outcome is Claude Code and what percentage is a PM who was already inclined to go deep? If a median PM at your company used the same tools, would they produce the same result? If not, the lesson is about PM craft, not about AI tooling — and that changes who it's for.

The core observation — that building a demo forces concreteness that a document doesn't — is solid and likely true. It doesn't need Claude Code to be true, and it doesn't need two projects to be true. That's both its strength (it's robust) and its weakness (it's not as novel as the framing suggests). The lesson gets interesting at the edges: the judgment risk, the organizational tension, the cost question. Those are the parts that need more honesty, not more polish.
