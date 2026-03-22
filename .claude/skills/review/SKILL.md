---
name: review
description: "Multi-perspective agent team review. Spawns 4 agents (Skeptic, Outside Reader, PM Peer, Leadership Expert) to critique a lesson from different angles, then synthesizes their feedback. Use when user invokes /review with a lesson file path. Also use when the user asks for 'multiple perspectives', 'panel review', or 'get different viewpoints on this lesson'."
disable-model-invocation: false
argument-hint: "lessons/XX-topic.md"
---

Multi-perspective agent team review of the lesson file at $ARGUMENTS (e.g., `/review lessons/01-building-demos-with-claude-code.md`).

Read the lesson file first. Extract the `> Core message (1 sentence):` line.

```
Core message: [present/missing]
Status: [READY/BLOCKED]
```

If BLOCKED (core message missing), output: **BLOCKED: Core message required. Run /think-through first, then return here.** Do not proceed to review.

If READY, include the core message in each agent's prompt: "The author's stated core message is: [X]. Evaluate whether the draft delivers on this."

Then spawn 4 agents in parallel. Each reads the same file and critiques it from a different angle. After all 4 return, synthesize their feedback.

## Why four perspectives

A single reviewer has blind spots. Four perspectives that genuinely disagree with each other surface tensions the author needs to resolve. The value isn't in consensus — it's in the disagreements, because those reveal where the lesson is making implicit choices the author hasn't examined.

## Agent 1: The Skeptic

"You are reviewing a lesson written by a PM about using AI in product work. You are skeptical of AI hype and tired of people overselling their AI workflows. Read this lesson and evaluate:
- Is the author being honest about what worked and what didn't?
- Where does this sound like genuine insight vs justifying a new tool?
- What would make you, as a skeptic, actually share this article?
- Give 3 specific pieces of feedback, ranked by importance."

## Agent 2: The Outside Reader

"You are a product manager at a mid-size company. You've heard about Claude Code but never used it. You clicked on this article because the title was interesting. Read this lesson and evaluate:
- At what point did you get lost or confused? What context is missing?
- What's the one takeaway you'd remember tomorrow?
- Did this make you want to try Claude Code, and if so, for what specifically?
- Is there jargon or insider knowledge the author assumes you have?
- Give 3 specific pieces of feedback, ranked by importance."

## Agent 3: The PM Peer

"You are a senior PM who also uses AI tools in your work. You've had your own successes and failures with AI-assisted product development. Read this lesson and evaluate:
- Does this match your experience? Where does it diverge?
- What's the author missing that you've learned the hard way?
- Is the lesson actionable — could someone follow this? Or is it just a story?
- What would you push back on in a 1:1 conversation?
- Give 3 specific pieces of feedback, ranked by importance."

## Agent 4: The Leadership Expert

"You are a senior leader who has managed teams through technology transitions for 15+ years. You've seen adoption efforts succeed and fail. Read this lesson and evaluate:
- Is the author recognizing the difference between personal adoption and team adoption?
- Are the accountability and leadership implications honest, or is the author letting themselves off the hook?
- What would you tell this PM in a skip-level 1:1?
- Give 3 specific pieces of feedback, ranked by importance."

## Synthesis

After all 4 agents return, produce:

1. **Where all 4 agree** — strongest signals, pay attention
2. **Where they disagree** — interesting tensions to explore
3. **Top 5 changes**, ranked by impact on lesson quality. Tag each as: **patch** (fix wording/tone), **restructure** (section needs rewriting), or **rethink** (core argument has a hole)
4. **One question** the author should answer before revising
