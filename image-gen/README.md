# Cover Image Generation

## Process

1. **Extract the visual metaphor** from the article — the core metaphor, 2-4 word main text, and a subtitle line
2. **Generate with Gemini** using the prompt template in `prompt-template.md`
3. **Refine** — iterate on text accuracy, illustration style, figure visibility, topic signal
4. **Review against article** — run the checklist in CLAUDE.md or spawn a review agent
5. **Save and upload** — save to `generated/`, upload as Substack cover image

## Tools Evaluated

| Tool | Verdict | Notes |
|------|---------|-------|
| **Google Gemini** | Best for this style | Good text rendering, iterative refinement via conversation |
| **Ideogram** | Decent but text errors | Struggles with accurate long text, better for abstract/dark designs |
| **Canva** | Not tested | Good for template-based covers with manual text placement |

## History

### Lesson 05 — "I Couldn't See the Gap Because I Was Standing on It"
- **Prompt iterations**: 3 on Ideogram (text errors on all), 3 on Gemini (nailed it)
- **Final image**: Cream background, "THE GAP" + "you can't see it from the top" + "AI Lessons as a PM" label + stacked architectural blocks with figure on top
- **Key learning**: Short text (2-4 words) generates accurately. Long sentences get mangled. Let the article title carry the full message. Gemini handles iterative refinement better than Ideogram for warm editorial style.
- **Design feedback applied**: blocks should look architectural (not Jenga), figure needs thumbnail visibility, add topic label for AI context
