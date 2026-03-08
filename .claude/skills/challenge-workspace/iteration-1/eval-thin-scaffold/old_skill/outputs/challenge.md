# Adversarial Review: Helping Designers Prototype with Claude Code

---

## 1. Survivorship Bias

**Claim being challenged:** "Claude Code could compress the gap between 'PM has an idea' and 'designer has time to explore it.'"

**Strongest counter-argument:** You built lesson 01 around the fact that *you* — a PM — got value from Claude Code for prototyping. Now you're assuming that value transfers to designers. But the reason it worked for you might be precisely because you *aren't* a designer. You had no faster alternative. A designer already has Figma, Framer, prototyping tools they're fluent in. You're generalizing from your own constraint (no design tools fluency) to someone else's situation (full design tools fluency). The gap you experienced doesn't exist for them in the same way.

**Verdict:** Weakness to acknowledge. The lesson needs to explicitly separate "this helped me as a PM" from "this would help designers." They are different claims with different evidence requirements.

---

## 2. Attribution Error

**Claim being challenged:** "For designers, writing a Claude Code prompt is basically writing a design brief — but one that executes immediately."

**Strongest counter-argument:** This reframes prompt engineering as design briefing, which sounds elegant but might be flatly wrong. A design brief communicates intent to another human who shares context, taste, and professional judgment. A Claude Code prompt communicates instructions to a model that has none of those things. The skill of writing a good design brief and the skill of writing a good prompt may overlap less than you think. You're crediting the *tool* with bridging a gap that actually requires a new *skill* — one designers haven't signed up to learn. You're attributing ease to Claude Code when the ease might come from your own comfort with writing structured technical instructions (a PM skill, not a universal one).

**Verdict:** This could be a fatal flaw if the lesson leans on this analogy too hard. The "prompt is the spec" framing is your mental model, not necessarily a designer's. Test it before building on it.

---

## 3. Sample Size of One

**Claim being challenged:** The entire lesson premise — that designers could or should use Claude Code for prototyping.

**Strongest counter-argument:** The scaffold is admirably honest that the experiment is early, but let's be blunt: there is no experiment yet. The "What I've Tried So Far" section has no content — just prompts asking you to fill in what's happened. The "Early Observations" section is entirely hypothetical bullet points with "Expand on" notes. You are writing a lesson about helping designers do something when, as far as this document shows, no designer has actually done it. This isn't a sample size of one. It's a sample size of zero.

**Verdict:** Fatal flaw *if you try to publish this as a lesson now*. As a scaffold for future exploration, it's fine. But every claim in this document is currently speculative. The scaffold's own "Think through" prompts are doing the right thing by pushing you to separate observation from imagination — but those prompts are unanswered.

---

## 4. Missing Cost Accounting

**Claim being challenged:** That Claude Code prototyping could be "faster than a full design sprint" or reduce friction for designers.

**Strongest counter-argument:** You already know from lesson 01 that your own prototyping involved an 800-line plan doc. You even reference this in the Open Questions ("Not my 800-line plan doc"). But you haven't grappled with the cost honestly. For a designer to use Claude Code, they'd need to: (1) install and configure a CLI tool, (2) learn prompt patterns that produce decent visual output, (3) iterate through rounds of "close but wrong" output, (4) potentially clean up or discard HTML/CSS that doesn't meet their standards. Compare this to opening Figma and dragging components they already know. The time-to-first-useful-output for a designer in Claude Code could be *significantly longer* than in their native tools, and you're not accounting for that learning curve because you've already paid it yourself.

**Verdict:** Weakness to acknowledge. The cost comparison needs to be honest. "Faster" compared to what? For whom? At what point on the learning curve?

---

## 5. Audience Projection

**Claim being challenged:** That this lesson would be useful to PMs thinking about designer-AI workflows.

**Strongest counter-argument:** You're writing from the perspective of a PM who wants designers to adopt a tool the PM likes. This is a classic organizational dynamic: person A finds something useful, assumes person B should use it too, and frames the pitch as being for person B's benefit. But the lesson is really about *your* desire to change someone else's workflow. A designer reading this would likely ask: "Why is a PM telling me how to prototype?" A PM reading this might think: "I should pitch this to my designers." Neither reaction is what you want. The audience that would actually benefit is PMs who want to *understand the boundaries* of where AI prototyping helps vs. where it steps on designers' expertise — and that lesson requires you to have talked to designers, which you may not have done yet.

**Verdict:** Weakness to acknowledge. The lesson risks coming across as a PM prescribing tools to designers. The fix is grounding it in what designers actually said when you showed them this — if that's happened.

---

## 6. The Uncomfortable Question

**What you might be avoiding:** The possibility that "helping designers prototype with Claude Code" is actually "replacing part of what designers do and calling it collaboration."

If a PM can generate a functional HTML prototype with Claude Code, and then asks a designer to "react" to it rather than create from scratch, the PM has already made dozens of design decisions — layout, flow, hierarchy, interaction patterns. The designer's role shifts from creator to reviewer. You hint at this in your Open Questions ("Is 'designer uses Claude Code' the right frame, or is it 'PM and designer collaborate through Claude Code'?") and in your failure signal ("I'm the only one generating and designers are just reviewing my output — that's just a PM making mockups with extra steps"). But you haven't sat with the deeper discomfort: maybe the real lesson is that Claude Code *does* let PMs bypass designers for certain types of work, and the question isn't how to bring designers along but whether that bypass is legitimate or corrosive.

**Verdict:** This is the lesson underneath the lesson. You're framing this as "how to include designers in AI prototyping" but the tension is really about power dynamics — who gets to make design decisions, and whether AI tools shift that boundary. If you don't address this, the lesson will feel evasive to anyone who works closely with designers.

---

## The lesson survives if...

1. **You have actually run the experiment.** At least one designer has used Claude Code (or reacted to its output) and you can cite what specifically happened — not what you imagine would happen.

2. **You separate the PM lesson from the designer lesson.** "I learned something about how PMs and designers collaborate when AI tools are involved" is defensible. "Designers should use Claude Code for prototyping" is not, unless a designer told you that.

3. **You confront the power dynamics question.** Does this tool shift who makes design decisions? Is that good, bad, or contextual? Avoiding this makes the lesson feel naive.

4. **You drop the "prompt is the spec" analogy unless a designer validated it.** It's a PM's mental model imposed on a designer's workflow. It might be right, but you need evidence, not elegance.

5. **You stay in scaffold mode until you have real observations.** The scaffold is well-structured and the "Think through" prompts are sharp. Answer them honestly before drafting. This lesson isn't ready to be written yet — and the scaffold already knows that.
