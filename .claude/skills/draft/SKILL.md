---
name: draft
description: "Help expand a specific section of a lesson from bullets to prose. Asks pointed questions, waits for answers, then shapes into the author's voice. Use when user invokes /draft with a lesson file path and optional section name. Also use when a user says 'help me write this section', 'expand this part', or 'turn these bullets into prose' in the context of a lesson file."
disable-model-invocation: false
argument-hint: 'lessons/XX-topic.md "Section Name"'
---

Help expand a specific section of the lesson file at $ARGUMENTS into prose.

Format: `/draft lessons/01-building-demos-with-claude-code.md "Section Name"`

If no section name is given, ask which section to work on.

## What you're trying to do

The author has bullets or rough notes that contain real thinking. Your job is to help him turn those into prose that sounds like him — direct, specific, and willing to say "I don't know." You're a collaborator, not a ghostwriter. The difference matters: a ghostwriter produces text, a collaborator helps the author find what he's actually trying to say.

## The process

1. Read the full lesson file for context, then focus on the specified section.

2. Don't write the section. Instead, ask 2-3 pointed questions about the bullet points — questions that force specifics. "What specifically happened when...?" and "Can you describe the moment when...?" are better than "How did it go?" Wait for answers before writing anything.

3. Shape the author's answers into prose. The voice should be:
   - Direct, not academic
   - Specific, not abstract
   - Willing to say "I don't know" or "I got this wrong"
   - No filler ("It's worth noting that...", "Interestingly enough...", "In today's rapidly evolving...")

4. After drafting, read it back and ask: "Does this sound like you?" Flag any sentence that feels generic or could appear in anyone's blog post. Check that every claim traces back to something the author actually experienced.

## Ground rules

- One section at a time. Don't jump ahead.
- If the author can't answer a question about a bullet point, that bullet point isn't ready to be prose yet. Leave it as a bullet with a note about what's missing.
- Prose should be tighter than the bullets, not longer. Expanding doesn't mean inflating.
