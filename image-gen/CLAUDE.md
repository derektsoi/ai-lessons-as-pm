# image-gen/

## When Working on Cover Images

- Extract the visual metaphor from the article's scaffold or Substack draft BEFORE generating prompts
- Main text must be 2-4 words max — AI mangles longer text
- Use Google Gemini (gemini.google.com/app) for generation — best text accuracy for this style
- Always include "AI Lessons as a PM" label in top-left corner for topic context
- Target 16:9 aspect ratio (1456x816 for Substack)

## Style Rules (Non-Negotiable)

- Warm cream/beige paper texture backgrounds ONLY — never dark/navy/charcoal
- Bold black text, not white text on dark
- Hand-drawn illustration style, not photorealistic or abstract geometric
- Illustration must represent the article's core metaphor, not generic decoration
- Minimalist — if you're tempted to add more elements, don't

## File Conventions

- Save generated images as: `generated/lesson-{number}-cover.png`
- Iterations: `generated/lesson-{number}-cover-v{n}.png`

## Prompt Template

@./prompt-template.md

## Review Checklist (Before Finalizing)

1. Does the image represent the article's core message?
2. Does the cover text complement (not compete with) the article title?
3. Does the illustration match the article's metaphor?
4. Would a PM scrolling Substack click on this?
5. Does the figure/text read clearly at thumbnail size?
6. Does anything signal the topic is AI? (label, illustration, or subtitle)
