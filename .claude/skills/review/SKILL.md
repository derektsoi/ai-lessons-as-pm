---
name: review
description: "Multi-perspective agent team review. Spawns 3 agents (Skeptic, Outside Reader, PM Peer) to critique a lesson from different angles, then synthesizes their feedback. Use when user invokes /review with a lesson file path. Also use when the user asks for 'multiple perspectives', 'panel review', or 'get different viewpoints on this lesson'."
disable-model-invocation: true
argument-hint: "lessons/XX-topic.md"
---

Multi-perspective agent team review of the lesson file at $ARGUMENTS (e.g., `/review lessons/01-building-demos-with-claude-code.md`).

Read the lesson file first, then spawn 3 agents in parallel. Each reads the same file and critiques it from a different angle. After all 3 return, synthesize their feedback.

## Why three perspectives

A single reviewer has blind spots. Three perspectives that genuinely disagree with each other surface tensions the author needs to resolve. The value isn't in consensus — it's in the disagreements, because those reveal where the lesson is making implicit choices the author hasn't examined.

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

## Synthesis

After all 3 agents return, produce:

1. **Where all 3 agree** — strongest signals, pay attention
2. **Where they disagree** — interesting tensions to explore
3. **Top 5 changes**, ranked by impact on lesson quality
4. **One question** the author should answer before revising
