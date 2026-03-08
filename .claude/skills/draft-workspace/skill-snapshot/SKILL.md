---
name: draft
description: "Help expand a specific section of a lesson from bullets to prose. Asks pointed questions, waits for answers, then shapes into author's voice. Use when user invokes /draft with a lesson file path and optional section name."
disable-model-invocation: true
argument-hint: 'lessons/XX-topic.md "Section Name"'
---

Help expand a specific section of the lesson file at $ARGUMENTS into prose.

Format: `/draft lessons/01-building-demos-with-claude-code.md "Section Name"`

If no section name is given, ask which section to work on.

## How to Draft

1. Read the full lesson file for context, then focus on the specified section.

2. Do NOT write the section for the author. Instead:
   - Ask 2-3 pointed questions about the section's bullet points ("What specifically happened when...?", "Can you describe the moment when...?")
   - Wait for the author's answers
   - Then help shape those answers into prose that sounds like the author, not like an AI

3. Keep the author's voice:
   - Direct, not academic
   - Specific, not abstract
   - Willing to say "I don't know" or "I got this wrong"
   - No filler phrases ("It's worth noting that...", "Interestingly enough...", "In today's rapidly evolving...")

4. After drafting a section together:
   - Read it back and ask: "Does this sound like you?"
   - Flag any sentence that feels generic or could appear in anyone's blog post
   - Check: does every claim trace back to something the author actually experienced?

## Ground Rules

- One section at a time. Don't jump ahead.
- If the author can't answer a question about a bullet point, that bullet point isn't ready to be prose yet. Leave it as a bullet with a note about what's missing.
- Prose should be tighter than the bullets, not longer. Expanding doesn't mean inflating.
