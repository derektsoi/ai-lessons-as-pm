---
name: challenge
description: "Adversarial review of a lesson. Stress-tests conclusions for survivorship bias, attribution error, sample size, and cost accounting. Use when user invokes /challenge with a lesson file path. Also use when a user says things like 'argue against this', 'what's wrong with this', 'play devil's advocate', or 'stress-test this lesson' — even without saying /challenge."
disable-model-invocation: false
argument-hint: "lessons/XX-topic.md"
---

Adversarial review of the lesson file at $ARGUMENTS (e.g., `/challenge lessons/01-building-demos-with-claude-code.md`).

Read the lesson file, then locate the `> Core message (1 sentence):` line.

```
Core message: [present/missing]
Status: [READY/BLOCKED]
```

If BLOCKED (core message missing), output: **BLOCKED: Core message required. Run /think-through first, then return here.** Do not proceed to challenges.

If READY, your challenges should test whether this core message holds. Argue against it.

## Why this matters

The author writes lessons to crystallize what he's learned. The risk is that writing feels like learning — you can produce a coherent narrative about an experience and mistake the coherence for truth. Comfortable conclusions survive by not being examined. Your job is to examine them.

## How to challenge

Attack the strongest claims first. If you only poke at easy targets, you're not helping — you're performing rigor without providing it. If something is genuinely solid, say so and move on.

For each challenge, provide the strongest version of the opposing view. Not a straw man you can knock down, but the argument a smart, experienced person would actually make. "Here's what someone who disagrees would say, and here's why they might be right."

Distinguish between "this is wrong" and "this is incomplete." A claim can be true and still miss something important. Both matter, but they need different responses — one needs retraction, the other needs expansion.

## What to look for

**Survivorship bias** — Are you only writing about this because it worked? What about the times this approach failed or you abandoned it? One success is an anecdote, not a method.

**Attribution error** — Are you crediting the tool for something that was really about your effort, context, timing, or domain knowledge? Would the outcome have been the same with a different tool and the same effort?

**Sample size** — You did this once (or twice). Is the lesson generalizable, or is it "it worked for me on this project"? Both are valid — but don't dress up the latter as the former.

**Cost accounting** — What did this actually cost in time, energy, and opportunity? Include setup, debugging, dead ends. Is the "faster/better" claim honest when you account for everything?

**Audience projection** — Are you writing for PMs like you, or for an idealized PM? Would someone at a different company, with less context, less technical comfort, or a different team structure actually find this useful?

**The uncomfortable question** — What's the one thing about this experience you're avoiding writing about? Why?

**Credibility** — Evaluate whether claims are Credible — backed by specific evidence, not asserted. If a claim sounds authoritative but has no source, flag it.

## Output format

For each challenge:
- The claim you're challenging (quote or paraphrase it)
- The strongest counter-argument
- Whether this is a fatal flaw, a weakness to acknowledge, or a valid tradeoff the author should own

End with: **"The lesson survives if..."** — state what the author needs to demonstrate for the core lesson to hold up.

## Phase 2: Deepen disputed claims

After presenting your initial challenges, assess each one:

- **Empirical claims** (e.g., "infrastructure matters more than practice hours") — search for supporting or contradicting research using web search. Present what you find alongside the challenge.
- **Philosophical/leadership claims** (e.g., "managers are accountable for team adoption") — spawn a 3-agent debate: one arguing for, one against, one synthesizing. Present the debate result.

Do not leave disputed claims as assertions. The author should receive the challenge AND the evidence in one pass, not have to request follow-up research manually.
