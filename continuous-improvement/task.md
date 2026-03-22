# Implementation Tasks — Lesson 05 Retro

> Source: `continuous-improvement/lesson-05-retro.md`
> Created: 2026-03-22
> Last reviewed: 2026-03-22 (2 rounds of Claude Code expert review)

---

## Execution Model

Each session implements changes, then verifies before marking complete. **No session proceeds to the next phase until its verification passes.** If verification fails, the agent iterates (fix → re-verify) up to 3 times. If still failing, escalate to author by:
- Writing a summary of what failed and why to `continuous-improvement/blocked.md`
- Proposing 2 alternative approaches
- Waiting for author to choose or redirect

```
Phase 1: Session A (sequential — foundation)
    ↓ blocked until A verified (including contradiction check)
Phase 2: Sessions B, C, D (3 parallel agents — independent skill edits)
    ↓ blocked until B+C+D all verified
Phase 3: Session E (sequential — new agent)
    ↓ blocked until E verified
Phase 4: Session F (sequential — cleanup)
    ↓ blocked until F verified
Phase 5: Session G (E2E — system integration test)
```

### How Parallel Sessions Work (Phase 2)

Sessions B, C, D run as **3 separate agents spawned simultaneously**, each editing a different skill file. They do NOT share context. The author (or lead agent) spawns all 3 and waits for all to complete before proceeding to Phase 3.

File ownership (no overlaps):
- **Session B owns:** `.claude/skills/challenge/SKILL.md`
- **Session C owns:** `.claude/skills/review/SKILL.md`
- **Session D owns:** `.claude/skills/publish/SKILL.md`, `.claude/skills/copyedit/SKILL.md` (new)
- **No session in Phase 2 edits:** `CLAUDE.md`, `/think-through/SKILL.md`, `/draft/SKILL.md` (these belong to Session A)

### How Skills Handle Missing Core Message

Skills are prompt instructions, not enforced gates. They **cannot** actually stop execution. Real enforcement is CLAUDE.md workflow + author discipline. The approach:

1. **Skills flag, they don't gate.** Each skill that reads the core message outputs a status:
   ```
   Core message: [present/missing]
   Status: [READY/BLOCKED]
   ```
   If BLOCKED, the skill outputs: `**BLOCKED: Core message required. Run /think-through first, then return here.**` and should not proceed to its main analysis. However, Claude may proceed anyway — that's a prompt compliance issue, not a system failure.

2. **CLAUDE.md enforces via workflow.** The workflow lists "core message present" as a prerequisite for steps 3-8. The author's discipline (guided by Claude suggesting the correct next step) is the real enforcement.

3. **Functional tests verify the flag with flexible patterns.** Pass criteria: skill output matches `BLOCKED|HALTED|unable to proceed` (case-insensitive) when core message is missing AND does not contain the skill's main output headers.

### Key Technical Decision: `.claude/lesson-workflow.md` Loading

Claude Code does NOT auto-load custom markdown files from `.claude/`. To make `.claude/lesson-workflow.md` visible at startup, CLAUDE.md must use the `@` import syntax:

```markdown
## Detailed Workflow
@./.claude/lesson-workflow.md
```

This expands and loads the imported file at startup. Task A.1 must use this syntax, not a regular markdown link.

---

## Phase 1: Foundation

### Session A: CLAUDE.md workflow + SUCCESS in skills + core message in skills + contradiction check

**Changes:** 1, 2, 8

**Task A.1: Add workflow sequence to CLAUDE.md**
- File: `CLAUDE.md`
- Add abbreviated workflow (steps 0-11) with one-line entry/exit criteria after "Lesson File Convention" section
- Add core message convention to "Lesson File Convention" section
- Add "max 2 returns to earlier step" guardrail for feedback loops
- Create `.claude/lesson-workflow.md` with detailed step descriptions (entry, exit, feedback paths)
- **Reference from CLAUDE.md using `@` import:** `@./.claude/lesson-workflow.md`
- **Line budget: CLAUDE.md under 250 lines** (excluding imported content). Detailed workflow in `.claude/lesson-workflow.md` (no limit).

**Task A.2: Weave SUCCESS criteria into skills**
- File: `.claude/skills/think-through/SKILL.md` — add to exit: "Is this Unexpected enough to hook? What's the Concrete moment that makes it stick?"
- File: `.claude/skills/draft/SKILL.md` — add to ground rules: "If a section is pure analysis without a Story or Emotional beat, flag it and ask for a felt moment."
- File: `.claude/skills/publish/SKILL.md` — add to conversion principles: "Check opening against Simple + Unexpected. Check emotional arc against Emotional + Stories."
- File: `.claude/skills/challenge/SKILL.md` — add: "Evaluate whether claims are Credible — backed by specific evidence, not asserted."

**Task A.3: Add core message read instructions to all downstream skills**

Each skill gets structured status reporting:

- File: `.claude/skills/challenge/SKILL.md` — add: "Locate the `> Core message (1 sentence):` line. Output `Core message: [present/missing]` and `Status: [READY/BLOCKED]`. If BLOCKED, output `**BLOCKED: Core message required. Run /think-through first.**` and do not proceed to challenges. If READY, your challenges should test whether this core message holds."
- File: `.claude/skills/draft/SKILL.md` — add: "Locate the `> Core message (1 sentence):` line. If missing, output BLOCKED status. If present, every section should serve this core message. If a section drifts from it, flag it."
- File: `.claude/skills/review/SKILL.md` — add: "Extract the `> Core message (1 sentence):` line. If missing, output BLOCKED status. If present, include it in each agent's prompt: 'The author's stated core message is: [X]. Evaluate whether the draft delivers on this.'"
- File: `.claude/skills/publish/SKILL.md` — add: "Locate the `> Core message (1 sentence):` line. If missing, output BLOCKED status. If present, the Substack article's thesis must be this core message. If the published draft doesn't deliver it, flag the disconnect."

**Task A.4: Add stale core message check to /draft exit**
- File: `.claude/skills/draft/SKILL.md` — add to exit criteria: "After drafting all sections, re-read the core message. If the prose has shifted the thesis, flag: 'Core message may be stale. Current prose suggests the lesson is about [X]. Update the core message line if this is correct.'"

**Task A.5: Run contradiction check (moved from E2E to here)**

After completing Tasks A.1-A.4, immediately spawn a verification agent that reads:
- CLAUDE.md (workflow section)
- `.claude/lesson-workflow.md` (detailed steps)
- All skill files edited in this session
And checks:
- Skill entry/exit criteria match CLAUDE.md step descriptions
- Core message convention is consistently described
- SUCCESS framework criteria are distributed (S+U in /publish, U+C in /think-through, E+S in /draft, Cr in /challenge)
- No contradictions between CLAUDE.md and skill prompts

**Unit Verification (must pass before Phase 2):**

| # | Test | How | Pass criteria |
|---|------|-----|---------------|
| 1 | CLAUDE.md line count | `wc -l CLAUDE.md` | Under 250 lines (excluding @import content) |
| 2 | Detailed workflow file exists | Check `.claude/lesson-workflow.md` exists | File exists with steps 0-11 |
| 3 | CLAUDE.md uses @import | Grep for `@./.claude/lesson-workflow.md` in CLAUDE.md | Found (NOT a markdown link) |
| 4 | Workflow sequence in CLAUDE.md | Grep for "Lesson Workflow" in CLAUDE.md | Section exists with abbreviated steps |
| 5 | Core message convention present | Grep for "Core message (1 sentence)" in CLAUDE.md | Convention documented |
| 6 | Feedback loop guardrail present | Grep for "max 2 returns" in CLAUDE.md or lesson-workflow.md | Found |
| 7 | SUCCESS in /think-through | Grep for "Unexpected" in think-through/SKILL.md | Found |
| 8 | SUCCESS in /draft | Grep for "Emotional" or "Story" in draft/SKILL.md | Found |
| 9 | SUCCESS in /publish | Grep for "Simple" and "Unexpected" in publish/SKILL.md | Found |
| 10 | Credible in /challenge | Grep for "Credible" in challenge/SKILL.md | Found |
| 11 | Core message + BLOCKED in /challenge | Grep for "BLOCKED" in challenge/SKILL.md | Found |
| 12 | Core message + BLOCKED in /draft | Grep for "BLOCKED" in draft/SKILL.md | Found |
| 13 | Core message + BLOCKED in /review | Grep for "BLOCKED" in review/SKILL.md | Found |
| 14 | Core message + BLOCKED in /publish | Grep for "BLOCKED" in publish/SKILL.md | Found |
| 15 | Stale core message check in /draft | Grep for "stale" in draft/SKILL.md | Found in exit criteria |
| 16 | Contradiction check passes | Task A.5 agent output | `Contradictions found: 0` or equivalent |

**Integration Test (Test 3 from retro):**

Pre-check: `grep "^> Core message" lessons/05-the-infrastructure-gap.md` to see current state.

Test 3a — Core message present:
- Add line: `> Core message (1 sentence): I couldn't see the gap because I was standing on months of infrastructure I'd built through obsession — and obsession isn't a method I can teach.`
- Invoke /challenge on lesson 05
- **Pass criteria:** Output matches `Core message:.*(present|found)` (case-insensitive) AND at least one challenge references the core message text

Test 3b — Core message missing:
- Remove the `> Core message` line
- Invoke /challenge on lesson 05
- **Pass criteria:** Output matches `(BLOCKED|HALTED|unable to proceed)` (case-insensitive) AND output does NOT contain challenge analysis headers (`## Challenge`, `### 1.`, `**Challenge 1**`, or equivalent)

If both pass → Session A complete.

---

## Phase 2: Skill Upgrades (3 parallel agents)

Spawn 3 agents simultaneously. Each agent implements one change, runs unit tests, runs functional test, and reports back. All 3 must pass before Phase 3.

### Session B: Upgrade /challenge with debate agents

**Change:** 3

**Task B.1: Add Phase 2 to challenge skill**
- File: `.claude/skills/challenge/SKILL.md`
- Add after "Output format" section:
  - Phase 2: Deepen disputed claims
  - Empirical claims → search for evidence (WebSearch)
  - Philosophical/leadership claims → spawn 3-agent debate (for, against, synthesizer)
  - "Do not leave disputed claims as assertions"

**Unit Verification:**

| # | Test | How | Pass criteria |
|---|------|-----|---------------|
| 1 | Phase 2 section exists | Grep for "Phase 2" in challenge/SKILL.md | Found |
| 2 | Web search instruction exists | Grep for "search" or "evidence" in challenge skill | Found in Phase 2 context |
| 3 | Debate agent instruction exists | Grep for "debate" or "3-agent" in challenge skill | Found in Phase 2 context |

**Functional Test:**
- Run /challenge on lesson 05 scaffold
- **Pass criteria (parseable output):**
  - Output contains a section titled `## Phase 2` or `## Deepening` or equivalent header
  - At least one challenge includes research/evidence (output contains "research" or "study" or "found" or a URL)
  - At least one challenge includes debate perspectives (output contains "For:" and "Against:" or "Agent 1" or equivalent structured debate)
- If pass → Session B complete. If not → iterate (adjust prompt wording, re-test, max 3 tries)

---

### Session C: Add Leadership Expert to /review

**Change:** 4

**Task C.1: Add 4th agent to review skill**
- File: `.claude/skills/review/SKILL.md`
- Update description frontmatter: "3 agents" → "4 agents"
- Add Agent 4: The Leadership Expert section (evaluate accountability, leadership implications, skip-level 1:1 advice)
- Update Synthesis section: "After all 3 agents return" → "After all 4 agents return"
- Core message anchoring already added by Session A — verify still present

**Unit Verification:**

| # | Test | How | Pass criteria |
|---|------|-----|---------------|
| 1 | 4 agents in description | Grep for "4 agents" in review skill frontmatter | Found |
| 2 | Leadership Expert section exists | Grep for "Leadership Expert" in review skill | Found as Agent 4 |
| 3 | Synthesis references 4 agents | Grep for "all 4" in review skill | Found |
| 4 | Core message anchoring exists | Grep for "Core message" in review skill | Found (from Session A) |

**Functional Test:**
- Run /review on lesson 05 draft
- **Pass criteria (parseable output):**
  - Output contains a section with "Leadership Expert" in the heading
  - That section contains 3 ranked feedback items (numbered or bulleted with priority)
  - Synthesis section references perspectives from all 4 agents
- If pass → Session C complete

---

### Session D: Strengthen /publish + create /copyedit

**Change:** 5

**Task D.1: Strengthen /publish cut tracking**
- File: `.claude/skills/publish/SKILL.md`
- Add requirement: must produce a section titled `## Cut List`
- Each cut categorized with tags: `[Scaffold-only]` or `[Content-cut]`
- Flag content cuts for author review
- Add gate instruction: "Present the cut list and wait for author approval before proceeding"

**Task D.2: Create /copyedit skill**
- File: `.claude/skills/copyedit/SKILL.md` (new)
- Frontmatter: name, description, disable-model-invocation: false, argument-hint
- Cold read of Substack draft — no scaffold context, no reference to scaffold file
- Check: voice consistency, jargon without context, emotional arc, hook strength, single clear thesis
- Output: specific line edits with line numbers (not suggestions like "consider tightening")
- Route: if structural/voice issues → output "Route: return to /publish to re-convert affected sections"

**Unit Verification:**

| # | Test | How | Pass criteria |
|---|------|-----|---------------|
| 1 | Cut list requirement in /publish | Grep for "Cut List" in publish skill | Found |
| 2 | Category tags in /publish | Grep for "Scaffold-only" and "Content-cut" in publish skill | Both found |
| 3 | Gate instruction in /publish | Grep for "approval" or "wait" in publish skill | Found |
| 4 | /copyedit skill file exists | Check `.claude/skills/copyedit/SKILL.md` | Exists |
| 5 | /copyedit frontmatter correct | Check name, description, disable-model-invocation: false | All present |
| 6 | /copyedit has no scaffold reference | Grep for "scaffold" in copyedit skill | NOT found |
| 7 | /copyedit has route-back instruction | Grep for "return to" or "Route:" in copyedit skill | Found |

**Functional Test:**
- Run /publish on lesson 05 scaffold
- **Pass criteria (parseable output):**
  - Output contains `## Cut List` or equivalent section header
  - At least one entry tagged `[Scaffold-only]`
  - At least one entry tagged `[Content-cut]` (if applicable)
  - Output contains text asking for approval before proceeding
- Run /copyedit on lesson 05 Substack draft
- **Pass criteria:**
  - Output contains specific line edits (references line numbers or quotes text to change)
  - Output does NOT reference the scaffold file by name
- If all pass → Session D complete

---

## Phase 3: Infrastructure Agent

### Session E: Create infrastructure-expert agent + rules

**Change:** 6

**Task E.1: Create the agent**
- File: `.claude/agents/infrastructure-expert.md` (new)
- Include: name, description, tools (Read, Grep, Glob, Edit, Write, Bash, Agent, WebSearch, WebFetch)
- CRITICAL instruction: verify against official Claude Code docs before proposing
- 7-step process: read context → read infra → read retros → verify against docs → propose → implement → clean memory
- Line budget reference: keep CLAUDE.md under 250 lines
- Agent should NOT spawn sub-agents for edits (trade-off: safety over speed — guardrails may not apply transitively). Do all work directly.

**Task E.2: Create path-scoped rules file**
- File: `.claude/rules/infrastructure.md` (new)
- Frontmatter: `paths: [".claude/**", "continuous-improvement/**"]`
- Rules: skill requirements (description, argument-hint, disable-model-invocation), core message reference convention, contradiction checks, memory cleanup after changes

**Task E.3: Embed guardrails in agent prompt as fallback**
Because path-scoped rules may not load for agent edits, duplicate critical guardrails in the agent prompt itself:
```
Before proposing any skill edit, verify against this checklist:
- [ ] Skill has description and disable-model-invocation fields
- [ ] If adding core message instruction, include BLOCKED status output
- [ ] Changes don't conflict with CLAUDE.md workflow sequence
- [ ] CLAUDE.md stays under 250 lines after changes
```

**Unit Verification:**

| # | Test | How | Pass criteria |
|---|------|-----|---------------|
| 1 | Agent file exists | Check `.claude/agents/infrastructure-expert.md` | Exists with correct frontmatter |
| 2 | Agent has doc verification instruction | Grep for "official" or "documentation" in agent file | Found as CRITICAL instruction |
| 3 | Agent has WebSearch in tools | Check tools field in frontmatter | WebSearch and WebFetch present |
| 4 | Agent has no-sub-agent instruction | Grep for "sub-agent" or "directly" in agent file | Found |
| 5 | Agent has embedded guardrails | Grep for "checklist" in agent file | Found with skill requirements |
| 6 | Rules file exists | Check `.claude/rules/infrastructure.md` | Exists |
| 7 | Rules file has path scope | Grep for "paths:" in rules file | Contains `.claude/**` and `continuous-improvement/**` |
| 8 | Rules file has skill requirements | Grep for "disable-model-invocation" in rules file | Found |

**Functional Test (Test 5 from retro):**
- Invoke the infrastructure-expert agent
- **Pass criteria (parseable output):**
  - Agent output references reading CLAUDE.md (mentions file by name or quotes content)
  - Agent output references reading at least 2 skill files
  - Agent output references reading a retro file
  - Agent output contains evidence of web search (URL, doc reference, or "verified against documentation")
  - Agent proposes changes with exact file paths (e.g., "Edit `.claude/skills/X/SKILL.md`")

If functional test passes → Session E complete.

---

## Phase 4: Cleanup

### Session F: Clean up stale memory

**Change:** 7

**Task F.1: Record before-state**
- Run `wc -l` on MEMORY.md before changes (record the number)

**Task F.2: Remove stale MEMORY.md sections**
- File: `memory/MEMORY.md`
- Remove "Workflow Rules" section (3 entries) — now in CLAUDE.md
- Remove "CLAUDE.md Fixes Needed" section — applied in Session A
- Remove "Skill Improvements Needed" section — applied in Sessions B-D
- Update "Lesson Workflow" line to match new CLAUDE.md sequence (including /copyedit and step 0)
- Add lesson 05 core message to lesson progress section

**Task F.3: Archive (don't delete) resolved feedback files**
- Files: `feedback_follow_lesson_workflow.md`, `feedback_workflow_confusion.md`, `feedback_update_scaffold_before_drafting.md`, `feedback_claude_md_fixes_needed.md`
- Keep files in memory directory (historical context)
- Remove their index entries from MEMORY.md (so Claude doesn't load them)

**Unit Verification (Test 6 from retro):**

| # | Test | How | Pass criteria |
|---|------|-----|---------------|
| 1 | No "Workflow Rules" section | Grep for "Workflow Rules" in MEMORY.md | NOT found |
| 2 | No "CLAUDE.md Fixes Needed" | Grep for "CLAUDE.md Fixes Needed" in MEMORY.md | NOT found |
| 3 | No "Skill Improvements Needed" | Grep for "Skill Improvements Needed" in MEMORY.md | NOT found |
| 4 | Line count reduced | `wc -l memory/MEMORY.md` | Fewer lines than before-state |
| 5 | Archived files still exist | Check all 4 feedback files exist in memory/ | All 4 present |
| 6 | Archived files not indexed | Grep for each filename in MEMORY.md | NOT found as index entries |
| 7 | Lesson workflow updated | Grep for "copyedit" in MEMORY.md | Found in workflow description |
| 8 | Lesson 05 core message in progress | Grep for "obsession" in MEMORY.md lesson 05 section | Found |

**Functional Test:**
- Start a new conversation in the repo
- Ask Claude "what's the lesson workflow?"
- **Pass criteria:** Claude describes the new workflow (with step 0, /copyedit, and 4-agent review) without referencing archived feedback files
- If pass → Session F complete

---

## Phase 5: E2E System Integration

### Session G: Full system verification

**Prerequisite:** All Sessions A-F verified and complete.

**Test 1: Full workflow walkthrough (happy path)**
- Simulate lesson 06 from Step 0 (interview) through Step 8 (copyedit)
- At each step transition, check:
  - [ ] Claude states the correct next step unprompted
  - [ ] Skill outputs core message status (where applicable)
  - [ ] Exit criteria are checked before moving forward
  - [ ] No step is skipped
- **Pass criteria:** All transitions correct for 8 consecutive steps

**Test 2: Feedback loop triggers (optional — validates during real lesson work)**
- [ ] Scenario A: During /challenge, state "the core message is wrong, it should be X" → Claude suggests returning to /think-through
- [ ] Scenario B: During /review synthesis, include a change tagged "rethink" → Claude routes back to /think-through
- [ ] Scenario C: During /copyedit, report structural voice issues → Claude suggests returning to /publish
- **Pass criteria:** All 3 scenarios trigger the correct feedback loop
- **Note:** This test is optional. Feedback loops are best validated during real lesson conversations where these situations arise organically. If time is limited, skip this and rely on real-world validation.

**Test 3: No contradictions (final cross-check)**
- Spawn an agent that reads:
  - CLAUDE.md (workflow section + @imported lesson-workflow.md)
  - All 6 skill files (/think-through, /challenge, /draft, /review, /publish, /copyedit)
- Agent checks:
  - [ ] Skill entry/exit criteria match CLAUDE.md step descriptions
  - [ ] No skills reference steps or conventions not in CLAUDE.md
  - [ ] CLAUDE.md doesn't reference skills that don't exist
  - [ ] Core message convention is consistently described across all files
  - [ ] SUCCESS framework criteria are distributed (S+U in /publish, U+C in /think-through, E+S in /draft, Cr in /challenge)
- Agent outputs a structured result: `## Contradiction Analysis` section with a count
- **Pass criteria:** Contradiction count is 0

**Final gate:** Tests 1 and 3 pass (Test 2 optional) → implementation complete. Update retro with results.

---

## Summary

| Phase | Session | Changes | Parallel? | Blocked by | Unit | Functional | Integration/E2E |
|-------|---------|---------|-----------|------------|------|------------|-----------------|
| 1 | A | 1, 2, 8 | No | — | 16 | — | 2 (Test 3a, 3b) |
| 2 | B | 3 | Yes (3 agents) | A | 3 | 1 | — |
| 2 | C | 4 | Yes (3 agents) | A | 4 | 1 | — |
| 2 | D | 5 | Yes (3 agents) | A | 7 | 2 | — |
| 3 | E | 6 | No | A | 8 | 1 | — |
| 4 | F | 7 | No | A-E | 8 | 1 | — |
| 5 | G | — | No | A-F | — | — | 2 required + 1 optional |

**Total: 46 unit tests, 6 functional tests, 4-5 integration/E2E tests = 56-57 verification points**

### Skill Evals — All 6 Passed (2026-03-22)

Results at `.claude/skills/evals/iteration-1/`. All assertions verified.

| Eval | Skill | Assertions | Result |
|------|-------|------------|--------|
| 1 | /challenge (with core message) | 6/6 | PASS |
| 2 | /challenge (BLOCKED) | 3/3 | PASS |
| 3 | /copyedit (cold read) | 6/6 | PASS |
| 4 | /publish (cut list) | 5/5 | PASS |
| 5 | /think-through (SUCCESS) | 4/4 | PASS |
| 6 | /review (4-agent panel) | 4/4 | PASS |

---

### Changes from v1 → v2 (based on expert reviews)

| Issue | Fix applied |
|-------|------------|
| `.claude/lesson-workflow.md` won't auto-load | Use `@` import syntax in CLAUDE.md |
| "Stop and tell" is not a real gate | Clarified: skills flag with BLOCKED status, CLAUDE.md + author discipline enforce |
| Functional test patterns too brittle | Grep patterns now flexible: `(BLOCKED\|HALTED\|unable to proceed)` |
| Parallel sessions ambiguous | Clarified: 3 separate agents spawned simultaneously, not sequential |
| Contradiction check too late (was in E2E) | Moved to Session A (Task A.5), kept lighter cross-check in Session G |
| Test 2 (feedback loops) expensive for synthetic test | Made optional — better validated during real lesson work |
| Path-scoped rules test removed | Guardrails embedded in agent prompt are the primary enforcement |
| CLAUDE.md line limit 200 → 250 | Increased with offloaded detail via @import |
| "Credible" from SUCCESS unassigned | Assigned to /challenge skill |
