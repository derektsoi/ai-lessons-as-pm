# Lesson 05 Retrospective — Process Review

> Date: 2026-03-22
> Lesson: "I Couldn't See the Gap Because I Was Standing on It"

---

## What Worked

### 1. Interview-style opening to gather stories first
Starting with "tell me what happened" before scaffolding was powerful. The user's raw ideas (OKR adoption, Claude usage, weekly loop) were explored through pointed questions, not structured into a scaffold prematurely. This surfaced the real lesson: the user arrived thinking adoption worked, the conversation revealed it was compliance. **This step is missing from the workflow — needs to be formalized as Step 0.**

### 2. Early uncomfortable challenges that shifted the framing
The first think-through pushed back hard: "Is this actually adoption, or is it compliance?" The user admitted: "you're right maybe I'm overly optimistic." This was the turning point — the lesson flipped from "how OKRs cracked adoption" to "the gap I couldn't see." The best insights emerged from discomfort, not from structuring.

### 3. Emergent insights not in any original idea
Key concepts discovered through the thinking process:
- **Feynman Test A/B** — the split between explaining the system vs. explaining the transformation
- **"Obsession isn't a method"** — crystallized why the author can't teach what they brute-forced
- **Task dependency structure** (the "jackpot") — O's SEO report worked because of cross-team data dependency, not just recurring pain
- **Compliance vs. adoption** distinction backed by PR evidence
- **The "chat and hope" vs. "define done, verify" mental model gap** — observed watching a PM build a demo

### 4. Core message distillation (1-sentence, 3-sentence, 1-paragraph)
When introduced, this immediately clarified what to keep and what to cut. The 1-sentence version became the north star: "I couldn't see the gap between my team and me because I was standing on months of infrastructure I'd built through obsession — and obsession isn't a method I can teach."

### 5. Multi-agent review panel (4 agents)
The Skeptic, Outside Reader, PM Peer, and Leadership Expert each surfaced different issues. The convergence question ("did you move too fast on accountability?") was the most valuable output — the user's response shaped the final closing.

---

## What Didn't Work

### 1. SUCCESS framework applied too late
The Made to Stick framework was applied after the editorial review, when the structure was nearly locked. It should have been woven into earlier skills — /think-through for the hook, /draft for emotional arc, /review for shareability. The framework found the middle was analytically strong but emotionally weak (rated "adequate" on Emotional and Stories). Earlier integration could have shaped the drafting.

### 2. Challenge skill required too much manual follow-up
The /challenge produced a monolithic critique. The user had to manually request:
- Web search for infrastructure vs. practice hours evidence
- 3-agent debate on Feynman principle applicability
- 3-agent debate on manager accountability
These should be built into the challenge workflow.

### 3. Workflow sequence ambiguity
The system didn't know which skill to call in sequence. The user had to ask "should I go with review first?" and the system had to correct: "draft comes before review in the workflow." This happens because CLAUDE.md doesn't have the workflow sequence or entry/exit criteria.

### 4. /draft skill doesn't match actual production pattern
The /draft skill asks questions one section at a time. In practice, several sections were drafted in rapid sequence with minimal back-and-forth. The skill's interactive model creates friction the author skips.

### 5. Substack conversion — editorial cuts were correct
The editorial review cut the fabrication story, O's full prototype arc, METR study reference, and Cowork nuance. These were **correct cuts** — none serve the core message ("obsession isn't a method"). The cross-check agent graded B+, but the issue was the *ending* retreating to action items, not the content cuts. Save the fabrication story for a future post on multi-agent review failures.

### 6. Repetition of "I don't know" across sections
Four reviewers independently flagged that the "I don't understand it" admission appears 3-4 times across sections. Should be stated once, powerfully, in the Feynman section.

---

## Ideas vs. Final Outcome

| Original Idea | What Happened |
|---------------|---------------|
| "Adoption shifted after OKR planning — don't know why" | Inverted: OKR produced compliance, not adoption. The "why" became the infrastructure gap + Feynman Test B |
| "Using Claude massively for tasks" (1,621 msgs, 55.9/day) | Served as unstated backdrop. Usage data in scaffold raw material but cut from Substack draft |
| "Weekly improvement loop" | Compressed to one line in "The Bet" section. Fabrication story cut (save for own post) |

**Biggest discovery not in any idea:** The Feynman Test A/B distinction — the gap between explaining the system (pass) and explaining the transformation (fail).

---

## Lesson File Status

| File | Status | Purpose |
|------|--------|---------|
| `lessons/05-the-infrastructure-gap.md` | Draft (full scaffold) | Source of truth — contains all thinking, all sections, raw material |
| `lessons/05-substack-draft.md` | Ready for final review | Publishable version — ~1,800 words, tighter arc |

**Open editorial item:** Cross-check agent graded B+ — ending retreats to action items when core message is about not knowing. Consider whether closing should end on uncertainty rather than the to-do list.

---

## Implementation Plan

### Architecture Decisions

**Continuous improvement workflow:** Custom agent (`infrastructure-expert.md`) invoked when author forks conversation to improvement mode. Path-scoped rules at `.claude/rules/infrastructure.md` load only when editing `.claude/**` files. Normal lesson writing is unaffected.

**Core message as living document:** Core message lives as a field in the scaffold file (`> Core message (1 sentence):`). Updated after /think-through, read by all downstream skills. No separate tracking doc — MEMORY.md captures cross-lesson index.

**SUCCESS framework:** Woven into existing skills as evaluation criteria, not a separate checkpoint. /think-through checks Unexpected + Concrete, /draft checks Stories + Emotional, /publish checks the full framework.

**Copyedit order:** Copyedit AFTER publish, not before. Reason: /publish creates new text (opening, closing, transitions) that needs a cold read. Copyedit evaluates what readers actually see, not the pre-conversion draft. A cut-list approval gate sits between /publish and /copyedit.

**Folder structure:** Keep flat. 2 files per lesson scales fine. Revisit if 3rd per-lesson file type becomes standard.

---

### Workflow (Full E2E)

```
0. Interview — "Tell me what happened." Surface stories, probe for specifics.
   Exit: topic agreed + entry question (what can't you explain yet?)
   ↓
1. Scaffold — Create lessons/XX-topic.md with prompts
   ↓
2. /think-through — Structured critique. Multiple rounds OK.
   Exit: scaffold updated, core message stated in file, 3 closing questions answered
   IF core message isn't clear yet → another round of /think-through
   ↓
3. /challenge — Adversarial stress-test. Spawns debate agents for disputed claims.
   Exit: author addressed each challenge, "survives if..." written into scaffold
   IF core message broke → return to /think-through to restate
   ↓
4. /draft — Expand sections to prose.
   Entry: reads core message + "survives if..." from scaffold
   For single sections: /draft interactively. For full article: parallel agents.
   Exit: all sections in prose
   ↓
5. /review — 4-agent panel (Skeptic, Outside Reader, PM Peer, Leadership Expert).
   Entry: each agent receives the core message as anchor
   Exit: top 5 changes (tagged: patch / restructure / rethink), convergence question
   IF "rethink" → return to /think-through
   IF "restructure" → return to /draft for affected sections
   ↓
6. Revise — Work through top 5 as checklist: accept / reject / modify each.
   Entry: answer convergence question from /review first
   Exit: all 5 changes dispositioned, draft checked against core message
   ↓
7. /publish — Convert to lessons/XX-substack-draft.md
   Entry: reads core message, Substack thesis must match
   Exit: must list what was cut (scaffold-only vs content-cut), author approves cut list
   GATE: author approves cuts before proceeding
   ↓
8. /copyedit — Cold read of Substack draft (no scaffold context)
   Entry: reads Substack draft as standalone
   Exit: line edits applied
   IF structural/voice issues → return to /publish to re-convert affected sections
   ↓
9. Post — Manual: paste into Substack. Record URL in scaffold (Status: Published)
   ↓
10. /retro — What worked, what didn't, ideas vs outcome, implementation proposals
    Exit: continuous-improvement/lesson-XX-retro.md
    ↓
11. Improve — Fork conversation, invoke @infrastructure-expert
    Exit: changes implemented, stale memory cleaned
```

### How Skills Use the Core Message

The core message is a living field in the scaffold file:
```
> Core message (1 sentence): [the lesson in one line]
> Core message (full): [2-3 sentences expanding the above]
```

Each downstream skill must read it before executing. **Current state: zero skills do this.** Required additions:

| Skill | Addition |
|-------|----------|
| /challenge | "Locate the core message line. Your challenges should test whether this core message holds. If no core message exists, stop and tell the author to run /think-through first." |
| /draft | "Locate the core message line. Every section should serve this core message. If a section drifts from it, flag it." |
| /review | "Extract the core message and include it in each agent's prompt: 'The author's stated core message is: [X]. Evaluate whether the draft delivers on this.'" |
| /publish | "Locate the core message line. The Substack article's thesis must be this core message. If the published draft doesn't deliver it, flag the disconnect." |
| /copyedit | "You don't have access to the scaffold. But check: does the Substack draft have a single clear thesis that every section serves? If it's unclear, the core message didn't survive conversion." |

---

### Changes (with Expected Outcomes)

#### Change 1: Add workflow sequence to CLAUDE.md

**File:** `CLAUDE.md`
**What:** Add the full E2E workflow (steps 0-11) with entry/exit criteria and feedback loops.
**Expected outcome:**
- Claude suggests the correct next step after completing any step
- No more "should I go with review first?" confusion
- Feedback loops (challenge → think-through, review → draft) are followed when triggered

**Verification:** Run a new lesson through the workflow. At each step, Claude should unprompted state what the next step is. Test: after /challenge, if the core message shifts, does Claude suggest returning to /think-through?

#### Change 2: Weave SUCCESS into existing skills

**Files:** `/think-through/SKILL.md`, `/draft/SKILL.md`, `/publish/SKILL.md`
**What:** Add SUCCESS criteria as evaluation questions within each skill (not a separate checkpoint).
**Expected outcome:**
- /think-through exit includes: "Is this Unexpected enough to hook? What's the Concrete moment?"
- /draft flags sections that are pure analysis without a Story or Emotional beat
- /publish checks opening hook and emotional arc

**Verification:** During next lesson's /think-through, does Claude evaluate the hook and concrete moments without being asked? During /draft, does Claude flag analytically-heavy sections and ask for a felt moment?

#### Change 3: Upgrade /challenge with debate agents

**File:** `.claude/skills/challenge/SKILL.md`
**What:** Add Phase 2: for empirical claims, search for evidence; for philosophical claims, spawn 3-agent debates.
**Expected outcome:**
- Author receives challenges WITH evidence in one pass
- No manual follow-up requests for web searches or debates

**Verification:** Run /challenge on a lesson with a disputable empirical claim. Does Claude automatically search for evidence without the author requesting it?

#### Change 4: Add Leadership Expert to /review + core message anchoring

**File:** `.claude/skills/review/SKILL.md`
**What:** Add 4th agent. Add core message read instruction. Update synthesis to include all 4.
**Expected outcome:**
- Leadership perspective present in every review
- All 4 agents evaluate against the stated core message

**Verification:** Run /review. Does the Leadership Expert appear? Does each agent's feedback reference the core message?

#### Change 5: Strengthen /publish + create /copyedit

**Files:** `.claude/skills/publish/SKILL.md`, `.claude/skills/copyedit/SKILL.md` (new)
**What:** /publish must list cuts with categories. /copyedit does a cold read of Substack draft.
**Expected outcome:**
- /publish produces an explicit cut list categorized as scaffold-only vs content-cut
- Author reviews and approves cuts before /copyedit
- /copyedit reads Substack draft without scaffold, catches voice/jargon/arc issues

**Verification:** Run /publish. Does it produce a categorized cut list? Does it wait for approval before proceeding? Run /copyedit — does it flag jargon that an outside reader wouldn't understand?

#### Change 6: Create infrastructure expert agent

**File:** `.claude/agents/infrastructure-expert.md` (new)
**What:** Reusable agent with Claude Code expertise. Must verify recommendations against official Claude Code documentation before proposing changes.

```markdown
---
name: infrastructure-expert
description: Expert in Claude Code infrastructure — CLAUDE.md, skills, hooks, rules, memory.
  Invoked during continuous improvement at the end of lesson conversations.
tools: Read, Grep, Glob, Edit, Write, Bash, Agent, WebSearch, WebFetch
---

You are an expert in Claude Code architecture and this repo's lesson workflow.

CRITICAL: Before recommending any change to CLAUDE.md, skills, hooks, or rules,
verify your recommendation against official Claude Code documentation.
Use WebSearch or WebFetch to check https://docs.anthropic.com/en/docs/claude-code
for current best practices. Do not rely on cached knowledge — the platform evolves.

When invoked, you:
1. Read the conversation context to understand what worked and what didn't
2. Read current CLAUDE.md, all skill files, rules, and memory index
3. Read retro files in continuous-improvement/
4. Verify proposed changes against official Claude Code docs
5. Propose specific changes — name exact files, exact content
6. Implement after author approval
7. Clean up stale memory entries

Principles:
- RIGHT mechanism: CLAUDE.md for universal rules, skills for invokable tools,
  hooks for automated checks, rules for path-scoped guidance, memory for
  cross-conversation context
- Prefer editing existing files over creating new ones
- Keep CLAUDE.md under 200 lines. Move detail into skills or rules.
- Test changes mentally against recent lesson conversations:
  would this have prevented the problem?
```

**Also create:** `.claude/rules/infrastructure.md` with path scope for `.claude/**` and `continuous-improvement/**`

**Expected outcome:**
- When author invokes @infrastructure-expert, it reads context + retro + current infra
- Agent verifies against official docs before recommending
- Changes are specific (exact files, exact content)
- Stale memory cleaned after implementation

**Verification:** Invoke the agent. Does it read the retro file? Does it check official Claude Code docs before proposing a skill change? Does it name exact files and content?

#### Change 7: Clean up stale memory

**File:** Memory files + MEMORY.md
**What:** After Changes 1-6: remove Workflow Rules section, CLAUDE.md Fixes Needed section, Skill Improvements Needed section from MEMORY.md. Archive (don't delete) individual feedback files.
**Expected outcome:**
- MEMORY.md is shorter and has no stale "fix this" entries
- Claude doesn't load redundant instructions every conversation

**Verification:** Check MEMORY.md line count before and after. Grep for "CLAUDE.md Fixes Needed" — should not appear. Check that archived feedback files still exist but aren't indexed.

#### Change 8: Add core message read instructions to all downstream skills

**Files:** `/challenge/SKILL.md`, `/draft/SKILL.md`, `/review/SKILL.md`, `/publish/SKILL.md`, `/copyedit/SKILL.md`
**What:** Each skill gets an explicit instruction to locate and read the `> Core message (1 sentence):` line before executing. See "How Skills Use the Core Message" table above.
**Expected outcome:**
- Every skill references the core message during execution
- If no core message exists, skill stops and directs author to /think-through first

**Verification:** Remove the core message line from a test scaffold. Run /challenge — does it stop and ask for core message? Add it back. Run /draft — does it reference the core message when evaluating each section?

---

### Execution Order

```
Phase 1 (sequential):
  Session A: Changes 1+2+8 (CLAUDE.md workflow + SUCCESS in skills + core message in skills)
  → Per-change verification + Test 3 (core message flow)

Phase 2 (parallel — 3 sessions can run simultaneously):
  Session B: Change 3 (/challenge upgrade) → per-change verification
  Session C: Change 4 (/review + Leadership Expert) → per-change verification
  Session D: Change 5 (/publish strengthen + /copyedit create) → per-change verification

Phase 3 (sequential):
  Session E: Change 6 (infrastructure-expert agent + rules) → per-change verification + Test 5 (agent fork context)

Phase 4 (sequential — must be last):
  Session F: Change 7 (memory cleanup) → per-change verification + Test 6 (memory clean)

Phase 5 (E2E — after all changes):
  Session G: System-level Tests 1, 2, 4 (full walkthrough, feedback loops, contradictions)
```

**Session dependencies:**
- Sessions B, C, D depend on Session A (skills need to reference the workflow and core message convention)
- Session E depends on A (agent needs to know the workflow it's improving)
- Session F depends on all prior sessions (only clean up what's been resolved)
- Session G depends on all prior sessions (tests the integrated system)

---

### How Path-Scoped Rules Work

In Claude Code, rule files in `.claude/rules/` can have a `paths` field in YAML frontmatter:

```markdown
---
paths:
  - ".claude/**"
  - "continuous-improvement/**"
---
# These rules only load when Claude reads/edits files matching those paths
```

Without `paths`, the rule loads every conversation. With `paths`, it loads only when Claude touches matching files.

**How this works with the fork workflow:** When the author forks and invokes @infrastructure-expert, the agent starts reading and editing `.claude/skills/`, `.claude/agents/`, `CLAUDE.md`, etc. At that point, path-scoped rules kick in — they load because the agent is working on `.claude/**` files. During normal lesson writing (editing `lessons/05-xxx.md`), these rules never load.

---

### System-Level Verification Plan

Individual change verifications are necessary but not sufficient. After all 8 changes are implemented, verify the system works as a whole.

#### Test 1: Full workflow walkthrough (happy path)
Walk through a hypothetical lesson 06 from Step 0 to Step 11. At each transition, verify:
- Does Claude suggest the correct next step?
- Does the skill read the core message from the scaffold?
- Do exit criteria get checked before moving on?

#### Test 2: Feedback loop triggers
- Scenario A: /challenge breaks the core message → does the workflow route back to /think-through?
- Scenario B: /review tags a change as "rethink" → does it route back to /think-through, not just Revise?
- Scenario C: /copyedit finds structural issues → does it route back to /publish?

#### Test 3: Core message flow integrity
- Write a core message in a scaffold
- Run each downstream skill (/challenge, /draft, /review, /publish, /copyedit)
- Verify: does each skill reference the core message in its output?
- Edge case: remove the core message line → does /challenge stop and ask for it?

#### Test 4: No contradictions between CLAUDE.md, skills, and rules
- The workflow sequence in CLAUDE.md says step order
- Each skill has entry/exit criteria
- Do they agree? Does any skill's prompt contradict the CLAUDE.md workflow?

#### Test 5: Infrastructure-expert agent works in fork context
- Invoke @infrastructure-expert after a lesson conversation
- Does it read the conversation context?
- Does it read the retro file?
- Does it verify against official Claude Code docs before proposing?
- Does the path-scoped rule load when it starts editing `.claude/` files?

#### Test 6: Memory is clean post-implementation
- MEMORY.md has no stale "fix this" entries
- No feedback files are indexed that have been resolved by CLAUDE.md changes
- Total memory load is lighter than before

#### Pre-Mortem: What Could Go Wrong

| Risk | What breaks | How to catch |
|------|------------|--------------|
| CLAUDE.md workflow is too long (>200 lines) | Context budget consumed by rules, less room for actual work | Check line count after Change 1 |
| Skills read core message but it's stale (author updated scaffold but not the core message line) | Skills anchor to wrong thesis | /draft should flag if core message doesn't match the prose |
| Path-scoped rules don't trigger because agent reads files via Agent tool (not direct Read) | Infrastructure rules never load during improvement work | Test: invoke @infrastructure-expert, check if rule content appears in its context |
| Feedback loops create infinite cycles (/challenge → /think-through → /challenge → ...) | Author gets stuck in a loop | Add "max 2 returns to earlier step" guardrail in CLAUDE.md |
| /copyedit after /publish means two conversion passes if issues found | Extra work on the rare path | Acceptable — the common path (no structural issues) is clean |

---

### What Was NOT Changed (and Why)

| Considered | Decision | Reason |
|------------|----------|--------|
| "What NOT to do" workflow section | Dropped | Positive sequence with exit criteria is sufficient |
| SUCCESS as mandatory checkpoint | Dropped | Woven into skills instead — heuristic, not a gate |
| Two /draft modes | Dropped | One line in workflow covers parallel drafting |
| core-messages.md tracking doc | Dropped | Core message in scaffold + MEMORY.md index is sufficient |
| Per-lesson folders | Dropped | 2 files per lesson scales fine flat. Revisit at 3rd file type |
| Copyedit before publish | Rejected | Copyedit must read what readers see (Substack draft), not pre-conversion text. /publish creates new text that needs the cold read |
