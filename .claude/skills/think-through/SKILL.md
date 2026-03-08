---
name: think-through
description: "Structured critique of a lesson draft. Checks whether observations are grounded, whether the lesson goes deep enough, what's missing, and whether it's ready for readers. Use when user invokes /think-through with a lesson file path. Also use proactively when a user shares a lesson draft and asks for feedback, critique, or 'what do you think' — even if they don't say /think-through explicitly."
disable-model-invocation: true
argument-hint: "lessons/XX-topic.md"
---

Run a structured critique on the lesson file at $ARGUMENTS (e.g., `/think-through lessons/01-building-demos-with-claude-code.md`).

Read the lesson file, then work through the areas below. Output your findings directly — don't rewrite the lesson.

## What you're trying to do

The author is a PM who writes lessons to crystallize what he's learned. The biggest risk isn't bad writing — it's comfortable thinking. Lessons that sound good but don't hold up under scrutiny. Your job is to find where the thinking is lazy, vague, or incomplete before the author publishes something he'll regret.

## Observation vs. narrative

Go through each claim or insight. The most common failure mode is the author narrating what he *thinks* happened rather than what he *observed*. There's a difference between "stakeholders responded well to the demo" (narrative) and "the COO pointed at conversation #7 and said 'this is wrong because the price doesn't include shipping'" (observation).

For every vague claim, ask for the specific moment. Not "what happened?" but "what did the person actually say or do?" If the author can't point to a concrete moment, the claim isn't grounded yet.

## Depth

The first framing the author lands on is usually the obvious one. Your job is to push past it. Ask what's underneath — what's the lesson behind the lesson? Is there an uncomfortable truth the author is dancing around?

Propose 1-2 alternative framings that might be more honest or more useful than the current one. The best alternative framings usually involve something the author got wrong or a tradeoff they're avoiding.

## Gaps

Look for what's missing:
- "Think through" prompts in the scaffold that haven't been addressed
- Sections still in bullets that should be prose (or prose that should be tighter)
- Counterarguments or failure modes that aren't acknowledged
- Questions a reader would have that the lesson doesn't answer

## Audience readiness

If this were cross-posted to Substack: would a PM who has never used Claude Code understand why this matters? Is there enough context, or does it assume insider knowledge? What's the one line that would make someone share this?

## Verdict

Rate readiness — not ready / scaffold done / draft ready / publishable — and end with 3 specific questions for the author to sit with. These should be the questions that, if answered honestly, would most improve the lesson.
