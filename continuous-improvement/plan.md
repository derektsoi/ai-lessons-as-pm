# Continuous Improvement Plan — Pre-Publish Pipeline

> Status: Planning
> Created: 2025-03-14
> Updated: 2025-03-14 — v3, revised after full flow review

## Purpose

The author writes lessons to learn through reflection. Publishing on Substack is a forcing function for clarity, not the goal. The pipeline should serve the thinking, not optimize for distribution.

## What Exists (and Why We're Not Using It)

Searched GitHub for Claude Code SEO skills. Found ~10 repos (claude-seo, claude-blog, seomachine, seo-geo-claude-skills, etc.). All are full SEO agency suites with 13-26 sub-skills — keyword research, SERP analysis, competitor audits, schema markup, E-E-A-T scoring.

**None solve the actual problem.** Substack handles most technical SEO automatically. Authors only control 3 fields:

1. SEO Title (≤60 chars)
2. SEO Description (~150 chars)
3. URL Slug (set before publish, immutable after)

These are a 3-line appendix, not a skill.

## Current Pipeline — Full Flow Review

```text
SCAFFOLD (lessons/XX-topic.md)
  │
  ├── /think-through ─── "Is the thinking honest and deep enough?"
  │     • Observation vs narrative (grounding)
  │     • Depth — push past the first framing
  │     • Gaps — unanswered scaffold prompts, missing counterarguments
  │     • Audience readiness — would a PM who hasn't used Claude Code get it?
  │     • Verdict + 3 questions
  │     • OUTPUT: console only
  │
  ├── /challenge ──────── "Does this survive scrutiny?"
  │     • Survivorship bias, attribution error, sample size
  │     • Cost accounting — honest about tradeoffs?
  │     • The uncomfortable question — what are you avoiding?
  │     • "The lesson survives if..."
  │     • OUTPUT: console only
  │
  ├── /draft ─────────── "Turn bullets into prose, one section at a time"
  │     • Asks pointed questions, waits for answers
  │     • Shapes prose in author's voice
  │     • Flags generic sentences
  │     • OUTPUT: modifies the lesson file (only skill that does)
  │
  ├── /review ─────────── "Three perspectives that disagree with each other"
  │     • Skeptic: honest or justifying a tool?
  │     • Outside Reader: where do I get lost? One takeaway?
  │     • PM Peer: actionable? What would you push back on?
  │     • Synthesis: agreements, disagreements, top 5 changes
  │     • OUTPUT: console only
  │
  │   ── author revises ──
  │
  ├── /publish ─────────── "Convert scaffold → Substack article"
  │     • Picks sharpest title
  │     • Strips scaffolding, keeps prose
  │     • Adds opening setup + bio
  │     • Voice check (direct, specific, no filler)
  │     • Conversion integrity check (NEW — see below)
  │     • OUTPUT: creates lessons/XX-substack-draft.md
  │     • NOTE: does NOT post to Substack — creates a local file only
  │
  │   ── author confirms content survived ──
  │
  ├── /copyedit ─────────── "Sentence-level polish + SEO fields" (NEW)
  │     • Reads the Substack draft cold, as a standalone piece
  │     • Voice editing calibrated to author
  │     • Substack SEO fields (3 settings, copy-pasteable)
  │     • OUTPUT: console only
  │
  │   ── author applies edits, copy-pastes SEO fields ──
  │
  └── MANUAL: post to Substack
```

### Deliberate overlaps (fine as-is)

These aren't bugs — they're the same concern checked at different stages on different artifacts:

- **Honesty/grounding**: `/think-through` (observation vs narrative) → `/challenge` (survivorship bias) → `/review` Skeptic (insight vs justification). Same concern, three angles, all on the scaffold. Each catches things the others miss.
- **Voice**: `/draft` (shapes prose) → `/publish` (voice check during conversion) → `/copyedit` (sentence-level edit on final artifact). Each operates on a different version of the text.

### Gap identified: `/publish` conversion check is too passive

**Problem:** `/publish` step 4 currently asks: "Anything that should stay that I cut, or vice versa?" This puts the burden on the author to notice what's missing. But the author has read the scaffold dozens of times — they fill in gaps mentally without realizing the text doesn't say what they think it says.

Example from lesson 01: the scaffold's "It's both" section (an honest admission about enjoying building vs. it being the right PM move) was cut entirely during `/publish` conversion. Was that intentional? `/publish` didn't flag it specifically.

**Fix:** Strengthen `/publish` step 4. After conversion, explicitly list what was cut. Flag any section where the scaffold had an uncomfortable admission, honest uncertainty, or a "Think through" prompt that generated real thinking — and ask the author: "I cut X. Was that the right call, or was that the sharpest part?"

### Gap identified: nothing reads the Substack draft as a standalone piece

**Problem:** `/think-through`, `/challenge`, and `/review` all operate on the scaffold. They check the thinking. `/publish` converts format. But nobody reads the Substack draft cold — as a reader would — and asks: does this article work on its own? Transitions that made sense in the scaffold context may feel unmotivated in the article. Sections may assume context the article didn't provide.

**Fix:** This is what `/copyedit` does. Not re-checking the thinking (done upstream), not re-checking the conversion (done in `/publish`). Just: as a piece of prose, does this read well?

## Change 1: Strengthen `/publish` Step 4

Update `/publish` SKILL.md step 4 from:

> 4. Show the user the draft and ask:
>    - "Does the title capture the sharpest insight?"
>    - "Does the opening give enough context?"
>    - "Anything that should stay that I cut, or vice versa?"

To:

> 4. **Conversion review:**
>
>    First, list everything you cut — section by section. For each cut, say whether it was:
>    - **Scaffold-only** (prompts, raw material, file paths) — routine, no need to discuss
>    - **Content cut** (prose, bullets with real thinking, honest admissions) — flag for the author
>
>    For any content cut, ask: "I cut this. Was that the right call, or was this the sharpest part?" Pay special attention to:
>    - Uncomfortable admissions or "what I got wrong" content
>    - "Think through" prompts that generated real thinking in the draft
>    - "What I'm still figuring out" content beyond what made it into the closing
>
>    Then ask:
>    - "Does the title capture the sharpest insight?"
>    - "Does the opening give enough context without the scaffold?"

## Change 2: New Skill — `/copyedit`

### What it does

Reads the Substack draft cold — as a standalone article, not as a conversion of the scaffold — and provides sentence-level feedback plus SEO fields.

**Single agent. Console output only.** This is the lightest skill in the pipeline. By this point, the thinking has been challenged 3-4 times upstream (`/think-through`, `/challenge`, `/review`). The conversion has been checked by `/publish`. All that remains is prose craft and the 3 Substack settings.

### Agent prompt: The Voice Editor

"You are copy-editing a Substack article. Read it cold — as a reader would, with no context about the scaffold or process that produced it. The prose has already been drafted and approved by the author. Your job is sentence-level mechanics, not reframing or restructuring. This is post-authorial editing: you polish, you don't rewrite meaning.

The author's voice is: direct, first-person, comfortable with uncertainty, uses em-dashes, doesn't hedge. He says 'I don't know yet' and means it. He uses specific numbers and real examples, not abstractions.

Evaluate:

- **Standalone readability:** Does every section make sense without the scaffold context? Flag any transition that feels unmotivated, any paragraph that assumes context the article didn't provide, any section that a cold reader would find confusing.
- **Filler and hedging:** Flag any filler, qualifications, or hedging that crept in during drafting ('It's worth noting...', 'Interestingly...', 'In today's rapidly evolving...'). These violate the author's voice.
- **Redundancy:** Flag where the same point is made twice without adding new information.
- **Awkward sentences:** Flag sentences that are structurally awkward or meander — but do not flag length alone. A 40-word sentence that builds momentum is fine. A 25-word sentence that meanders is not.
- **Meaning-preserving rule:** If a suggestion would change the meaning of a sentence, frame it as a question to the author, not a correction.

Give your feedback as a numbered list, ranked by impact. For each item, quote the specific text and explain what you'd change and why.

After the feedback list, generate:

**Substack SEO Settings** (for the author to copy-paste into Substack's settings panel):

- **SEO Title** (≤60 chars, keyword-forward — this is the Substack SEO settings field, may differ from the article title): ...
- **SEO Description** (~150 chars, direct and specific, no filler — matches author voice): ...
- **URL Slug** (short-kebab-case-with-keywords, set before publishing): ...
- **Suggested Tags** (2-3 Substack tags): ..."

### Skill frontmatter

```yaml
---
name: copyedit
description: "Sentence-level copy edit of a Substack draft. Reads the article cold, flags prose issues, and generates SEO settings. Use when user invokes /copyedit with a substack draft path. Also use when the user says 'polish this before posting', 'final check', or 'ready to post' in the context of a substack draft."
disable-model-invocation: true
argument-hint: "lessons/XX-substack-draft.md"
---
```

### Design decisions

**Why single agent, not two:**

- The original plan had a Shareability Tester ("would your COO read this?"). Review found this was the wrong lens — the author writes to learn through reflection, not to influence colleagues. Removed.
- The original plan had a Reflection Integrity Checker. Review found this overlaps with `/think-through` and `/challenge` upstream. The only unique value — catching conversion drift — now belongs in `/publish` step 4.
- What remains is genuinely one job: read the article cold and check the prose.

**Why SEO fields live here, not in `/publish`:**

- `/publish` is about conversion. SEO fields are about Substack settings.
- `/copyedit` is the last step before posting — natural place for the settings you'll paste into Substack's UI.
- Keeps `/publish` focused on one job.

**Console output only, no file modification:**

- Consistent with `/think-through` and `/challenge`.
- The author decides which suggestions to apply.
- SEO fields are copy-pasted into Substack's settings panel, not written to a file.

**`/publish` does NOT post to Substack:**

- `/publish` creates a local `XX-substack-draft.md` file. It does not automate posting.
- Posting to Substack is a manual step. The author reads the draft one more time in Substack's preview, pastes the SEO fields, and publishes.
- If auto-posting is desired later, it would be a separate `/post` skill — keeping the irreversible "publish to the world" action explicit and intentional.

**What this skill does NOT do:**

- Re-check the thinking (done by `/think-through`, `/challenge`, `/review`)
- Re-check the conversion (done by `/publish` step 4)
- Keyword research or competitor analysis
- Rewrite the author's meaning or add ideas

## Implementation Steps

1. [ ] Update `/publish` SKILL.md step 4 with stronger conversion check
2. [ ] Create `/copyedit` SKILL.md at `.claude/skills/copyedit/SKILL.md`
3. [ ] Update CLAUDE.md — add `/copyedit` to skills list and `continuous-improvement/` to repo structure
4. [ ] Test `/copyedit` against `lessons/01-substack-draft.md` as a dry run
5. [ ] Iterate based on output quality
6. [ ] Update MEMORY.md workflow line to include `/copyedit`

## Consistency Checklist (from audit)

- [ ] `/copyedit` SKILL.md frontmatter follows existing pattern (`name`, `description`, `disable-model-invocation: true`, `argument-hint`)
- [ ] CLAUDE.md skills list description matches existing style: `/copyedit` — Sentence-level copy edit and SEO fields for a Substack draft. Reads the article cold, flags prose issues, generates Substack settings.
- [ ] SEO description constraint: direct and specific, no filler — matches author's voice
- [ ] Explicit note: SEO Title is the Substack SEO settings field, not a replacement for the article title
- [ ] `/publish` step 4 updated before `/copyedit` is built (dependency)
