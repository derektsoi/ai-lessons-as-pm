---
name: publish
description: "Convert a lesson scaffold into a publishable Substack article. Strips scaffold elements, produces clean prose. Use when user invokes /publish with a lesson file path."
disable-model-invocation: true
argument-hint: "lessons/XX-topic.md"
---

Convert the lesson file at $ARGUMENTS into a Substack-ready article.

## Steps

1. **Read the lesson file** at `$ARGUMENTS`. Identify the lesson number from the filename (e.g., `01` from `lessons/01-topic.md`).

2. **Produce a Substack-ready draft** saved as `lessons/XX-substack-draft.md` (using the same lesson number).

3. **Conversion rules:**

   **Title**: Pick the sharpest, punchiest line from the lesson — usually from "The Lesson" section or a key insight. It should be a statement, not a description. Not "Lessons from Building a Demo" but something like "A Working Demo Doesn't Let You Be Vague."

   **Subtitle**: Frame the topic broadly — what this is really about, beyond the specific tool or project.

   **Strip all of these:**
   - `> Status:` lines
   - "Think through" prompt blocks (any `> Think through:` content)
   - "Raw Material & References" sections
   - Local file paths or repo references
   - Scaffold markers and section headers that are still in bullet form without prose
   - Any sections that are purely structural/empty

   **Keep:**
   - "What I'm still figuring out" — this works as an honest closing section
   - All prose sections that have been drafted
   - Concrete examples and specific moments

   **Add:**
   - An opening setup paragraph that establishes context (PM in Hong Kong, building with AI tools, the specific problem or situation)
   - `---` section breaks between major sections (Substack renders these as visual dividers)
   - A closing bio line: *"[Author name] is a PM based in Hong Kong. This is [first/next in a series] about what he's learning building with AI."*

   **Voice check:**
   - Direct, not academic
   - Specific, not abstract
   - Willing to say "I don't know" or "it's both"
   - No filler phrases added during conversion

4. **Show the user the draft** and ask them to review before finalizing. Specifically ask:
   - "Does the title capture the sharpest insight?"
   - "Does the opening give enough context?"
   - "Anything that should stay that I cut, or vice versa?"
