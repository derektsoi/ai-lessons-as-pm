# Adversarial Review: Helping Designers Prototype with Claude Code

---

## Challenge 1: The entire premise may be a solution looking for a problem

**Claim:** "Could designers use this too?" and "Claude Code could compress the gap between 'PM has an idea' and 'designer has time to explore it.'"

**Counter-argument:** You're starting from your own excitement about a tool and working backward to find someone else who should also be excited. That's product instinct inverted. The strongest version of the opposing view: designers already have rapid prototyping workflows. Figma's prototyping features, Framer, even basic Webflow — these are tools built for designers, by designers, with design-native mental models. A designer who wants to test an interaction can build it in Figma in 20 minutes with auto-layout, components, and smart animate. You're proposing they learn a CLI-based AI coding tool instead. The gap you're describing — "PM has idea, designer doesn't have time" — isn't a tooling gap. It's a prioritization gap. Adding a new tool doesn't give designers more time. It gives PMs a way to bypass the queue, which designers may not welcome.

**Severity:** This is a weakness to acknowledge, and the scaffold partially does — the "What I'm still figuring out" section asks "Am I projecting my own enthusiasm onto designers who didn't ask for this?" That's the right question. But the rest of the scaffold proceeds as though the answer is no, which undercuts the honesty. The scaffold should hold that tension harder. If you haven't had a designer tell you they want this, the entire lesson rests on your projection.

---

## Challenge 2: You don't have any evidence yet, and the scaffold lets you hide that

**Claim:** The lesson is structured as though observations exist — "Early Observations," "The prompt is the spec," "The fear of code" — but every section is empty placeholder text.

**Counter-argument:** This isn't a lesson. It's a hypothesis document dressed as a lesson scaffold. There's nothing wrong with hypotheses, but the scaffold format gives it an authority it hasn't earned. You have section headers like "Early Observations" with zero observations in them. The "Think through" prompts are doing heavy lifting here — they're essentially saying "have you actually done any of this?" and the implicit answer throughout is no. A smart reader would ask: what has actually happened? You've used Claude Code yourself. You think designers could too. That's it. Everything else — "the prompt is the spec," designers fearing code, the differences between PM and designer needs — reads like armchair theorizing. The scaffold's own "What's actually happened" vs. "What's still hypothetical" split is the most honest part of the document, but neither section is filled in.

**Severity:** Not a fatal flaw — the status says "Scaffold" and the lesson section says "Not Ready Yet," so you're being transparent. But it's a weakness to acknowledge that you're building an elaborate structure around nothing yet. The risk is that the structure itself starts to feel like progress.

---

## Challenge 3: "The prompt is the spec" is a seductive analogy that probably breaks down

**Claim:** "For designers, writing a Claude Code prompt is basically writing a design brief — but one that executes immediately."

**Counter-argument:** A design brief and a Claude Code prompt are fundamentally different artifacts. A design brief is deliberately ambiguous in the right places — it describes intent, mood, constraints, and leaves execution to the designer's craft judgment. A Claude Code prompt that's ambiguous produces garbage. It needs specificity about layout, spacing, color, interaction behavior, edge cases. The skills that make someone good at writing design briefs (setting vision, leaving room for creative interpretation) are almost opposite to what makes someone good at prompting an AI code generator (being explicit, anticipating literal interpretation, iterating on specific outputs). The analogy flatters the concept but misleads about the actual experience. A designer trying to use Claude Code would likely find that the "brief" they write either produces something too generic to be useful or requires so many follow-up corrections that they'd have been faster in Figma.

**Severity:** This is incomplete rather than wrong. The analogy might hold for a narrow slice of prototyping — rough directional layouts, flow validation, "does this interaction concept even make sense" testing. But it breaks badly for anything requiring visual craft, which is the part designers care most about. You need to define the boundary explicitly rather than letting the analogy suggest a broader applicability than it has.

---

## Challenge 4: The "fear of code" framing is condescending

**Claim:** "Claude Code outputs HTML/CSS/JS, which can feel intimidating even though the designer never touches it."

**Counter-argument:** Framing designers as afraid of code is a PM cliche that most designers find patronizing. Many designers today know HTML and CSS. Many have used developer tools, inspect element, and basic scripting. The real issue isn't fear — it's relevance. A designer looking at Claude Code's output isn't intimidated by `<div>` tags; they're annoyed that the output doesn't respect their grid system, uses wrong spacing tokens, and produces visually mediocre results. The barrier isn't emotional (fear), it's practical (the output isn't good enough for their standards). By framing it as fear, you're centering the narrative on designer psychology instead of on tool capability — which lets you avoid the harder question of whether Claude Code's output meets the quality bar designers actually work at.

**Severity:** This is a weakness to acknowledge and reframe. If you've actually observed a designer react with anxiety to code output, report that. If you're assuming it, you're projecting a stereotype. Either way, the stronger analysis is about quality expectations, not emotional barriers.

---

## Challenge 5: Your success criteria reveal the real risk

**Claim:** "Signal that this doesn't work: I'm the only one generating and designers are just reviewing my output (that's just a PM making mockups with extra steps)."

**Counter-argument:** This is the most honest line in the scaffold, and it deserves more weight than you're giving it. Because here's the likely outcome based on what you've described: you are a PM who's excited about Claude Code, and you want to bring designers along. The most probable path is exactly the failure mode you named — you generate prototypes, show them to designers, and they give feedback. That's not "designers prototyping with Claude Code." That's you prototyping and calling it collaboration. And it might actually be the right workflow — PM generates rough prototypes, designer reacts and refines — but that's a different lesson than the one your title promises. The uncomfortable question is whether "Helping Designers Prototype with Claude Code" is really "PM Uses Claude Code to Generate Mockups for Design Review," and whether you're avoiding that framing because it sounds less impressive.

**Severity:** This is the potential fatal flaw. If the actual workflow that emerges is PM-generates-designer-reviews, then the lesson title, the premise, and the "prompt is the spec" framing all need to change. The lesson might still be valuable — "how PMs can use AI prototypes to communicate with designers more effectively" is a real topic — but it's a fundamentally different lesson.

---

## Challenge 6: Missing cost accounting for the designer's side

**Claim (implicit):** This workflow would save designers time or give them a useful new capability.

**Counter-argument:** You haven't accounted for what this costs the designer. Learning a new tool has real costs: time to learn the CLI, time to learn prompting patterns, time spent fixing AI output that's "close but wrong" (which you mention in Open Questions but don't weight). For a designer whose Figma workflow already gets them from idea to testable prototype in under an hour, the ROI of learning Claude Code is negative unless the prototypes it produces are meaningfully different from what Figma can do — specifically, working interactive HTML prototypes that test real browser behavior, not just click-through flows. You need to be specific about which prototyping scenarios actually benefit from code output vs. visual tool output. Without that specificity, "designers should try Claude Code" is just "everyone should use the tool I like."

**Severity:** This is a weakness to acknowledge. The scaffold's Open Questions section gestures at this — "When does this create more work for designers instead of less?" — but it needs to be a central concern, not a bullet point.

---

## The lesson survives if...

The author can demonstrate all three of the following:

1. **A real designer actually tried it.** Not a hypothetical designer, not the author generating prototypes on a designer's behalf. A designer sat down, wrote prompts, and produced something. What happened? Was it useful? Would they do it again?

2. **There's a specific prototyping scenario where Claude Code is genuinely better than existing design tools.** Not "also works" — better. The most likely candidate is interactive prototypes that need real browser behavior (API calls, state management, responsive behavior) that Figma can't simulate. If that specific scenario doesn't exist or isn't common enough to matter, the lesson collapses.

3. **The workflow that emerged was actually "designer prototyping" and not "PM prototyping for designer review."** The author's own success criterion nails this. If the designer didn't voluntarily reach for the tool a second time, the lesson is about something else — and the author needs to be honest about what that something else is.
