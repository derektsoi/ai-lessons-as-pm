---
name: copyedit
description: "Sentence-level cold read of a Substack draft. Checks voice, clarity, emotional arc, and hook strength. Produces specific line edits and SEO fields. Use when user invokes /copyedit with a Substack draft file path."
disable-model-invocation: false
argument-hint: "lessons/XX-substack-draft.md"
---

Read the Substack draft at `$ARGUMENTS` cold. You have no access to the lesson file, no knowledge of what was cut, and no context beyond what this article gives you. You are a copy editor encountering this piece for the first time.

## What you're checking

1. **Voice consistency.** The author's voice is: direct, first-person, comfortable with uncertainty, uses em-dashes, doesn't hedge. Uses specific numbers and real examples, not abstractions. Flag any sentence that drifts into:
   - Academic or consultant tone ("it is worth noting", "one might argue")
   - Hedging language ("perhaps", "it could be said", "in some ways")
   - Abstract generalization where a specific example should be

2. **Jargon without context.** Any term a general Substack reader wouldn't know must be explained on first use. Technical terms, company-specific language, framework names — if it's not defined within two sentences of first appearance, flag it.

3. **Emotional arc.** The piece should have at least one moment where the reader feels something — not just learns something. If the entire article is analysis without a felt moment (a scene, a reaction, an admission), flag it.

4. **Hook strength.** Read only the first two paragraphs. Would you keep reading if this showed up in your inbox between 10 other newsletters? If not, say why and propose a specific rewrite.

5. **Single clear thesis.** After reading the full piece, state the thesis in one sentence. If you can't, or if the piece argues two different things, flag the split.

## Output format

### Line Edits

For each edit, provide:

```
Line [number]: "[original text]"
→ "[revised text]"
Reason: [why this change improves the piece]
```

Be specific. "Consider tightening" is not an edit. "Cut the first clause — the sentence is stronger starting at 'We shipped'" is an edit.

### Structural Issues

If you find any of these, list them here:
- Voice breaks (sections that sound like a different author)
- Missing emotional beat (all analysis, no felt moment)
- Thesis drift (article argues X in the opening but lands on Y)
- Hook failure (opening doesn't earn the reader's attention)

If structural or voice issues are found: **Route: return to /publish to re-convert affected sections.** Do not attempt to fix structural problems with line edits.

### Verdict

One of:
- **Clean** — minor line edits only, ready to publish after applying them
- **Needs line edits** — substantive but sentence-level fixes, apply and re-read
- **Route back** — structural issues that line editing can't fix

### Substack SEO Fields

After all edits, generate these fields for Substack publishing:

- **SEO Title** (max 60 characters): optimized for search, doesn't need to match the article title
- **SEO Description** (~150 characters): the one-line pitch that appears in search results and social previews
- **URL Slug**: lowercase, hyphenated, concise (e.g., `working-demo-forces-clarity`)
- **Suggested Tags**: 3-5 tags relevant to the Substack audience (e.g., Product Management, AI, Leadership)
