---
name: think-through
description: "Structured critique of a lesson draft. Checks observations, lesson depth, gaps, audience readiness. Use when user invokes /think-through with a lesson file path."
disable-model-invocation: true
argument-hint: "lessons/XX-topic.md"
---

Run a structured critique on the lesson file at $ARGUMENTS (e.g., `/think-through lessons/01-building-demos-with-claude-code.md`).

Read the lesson file, then work through these steps. Output your findings directly — don't rewrite the lesson.

## 1. Observation Check

For each claim or insight in the lesson:
- Is this grounded in something that actually happened, or is it a generalization?
- Flag any line where the author is narrating what they think happened rather than what they observed.
- Ask for the specific moment, conversation, or data point behind vague claims.

## 2. Lesson Depth Check

Look at the main lesson/takeaway:
- Is this the obvious first-pass lesson, or has the author dug deeper?
- What's underneath it? Propose 1-2 alternative framings that might be more honest or more useful.
- Is there an uncomfortable truth the lesson is dancing around?

## 3. Gap Check

What's missing?
- Any "Think through" prompts in the scaffold that haven't been addressed yet?
- Sections that are still bullet points when they should be prose (or vice versa)?
- Counterarguments or failure modes that aren't acknowledged?
- The reader's likely questions that the lesson doesn't answer?

## 4. Audience Check

If this were cross-posted to Substack:
- Would a PM who has never used Claude Code understand why this matters?
- Is there enough context for the reader, or does it assume insider knowledge?
- What's the one line that would make someone share this?

## 5. Verdict

Rate the lesson's readiness:
- **Not ready**: Still thinking — needs more reflection before writing
- **Scaffold done**: Outline is solid, ready to expand into prose
- **Draft ready**: Prose exists but needs tightening
- **Publishable**: Could go out as-is

End with 3 specific questions for the author to sit with.
