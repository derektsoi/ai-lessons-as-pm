---
name: challenge
description: "Adversarial review of a lesson. Stress-tests conclusions for survivorship bias, attribution error, sample size, cost accounting. Use when user invokes /challenge with a lesson file path."
disable-model-invocation: true
argument-hint: "lessons/XX-topic.md"
---

Adversarial review of the lesson file at $ARGUMENTS (e.g., `/challenge lessons/01-building-demos-with-claude-code.md`).

Read the lesson file, then argue against it. Your job is to stress-test every conclusion. Be direct and specific — not mean, but unsparing.

## Rules

- Attack the strongest claims first, not the weakest. If you only poke at easy targets, you're not helping.
- Don't argue for the sake of arguing. If something is genuinely solid, say so and move on.
- Propose the strongest version of the opposing view. "Here's what someone who disagrees would say, and here's why they might be right."
- Distinguish between "this is wrong" and "this is incomplete." Both matter but differently.

## What to Challenge

1. **Survivorship bias**: Are you only writing about this because it worked? What about the times it didn't?

2. **Attribution error**: Are you crediting Claude Code for something that was really about your own effort, context, or timing?

3. **Sample size of one**: You did this once. Is the lesson generalizable, or is it "it worked for me on this project"? Both are valid, but don't dress up the latter as the former.

4. **Missing cost accounting**: What did this cost in time, energy, opportunity cost? Is the "faster than a design sprint" claim honest when you include setup, debugging, and the 800-line plan doc?

5. **Audience projection**: Are you writing for PMs like you, or for an idealized PM? Would a PM at a different company, with a different team structure, find this useful?

6. **The uncomfortable question**: What's the one thing about this experience you're avoiding writing about? Why?

## Output

For each challenge, state:
- The claim you're challenging
- The strongest counter-argument
- Whether this is a fatal flaw, a weakness to acknowledge, or a valid tradeoff

End with: "The lesson survives if..." — state what the author needs to demonstrate for the lesson to hold up.
