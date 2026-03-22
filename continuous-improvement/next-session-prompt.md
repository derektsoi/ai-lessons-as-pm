# Next Session Prompt — Skill Evals (Remaining 4)

Copy-paste this into a new Claude Code session in the `ai-lessons-as-pm` repo.

---

## Prompt

Read these files for context:
- `continuous-improvement/task.md` — the implementation plan (all 8 changes are done)
- `.claude/skills/evals/evals.json` — 6 eval cases with assertions
- `.claude/skills/evals/iteration-1/` — results from evals 2 and 3 (already passed)

Evals 2 (challenge BLOCKED) and 3 (copyedit cold read) already passed. Run the remaining 4 evals:

**Eval 1: /challenge WITH core message**
- Run `/challenge lessons/05-the-infrastructure-gap.md` (it has a core message)
- Verify: output contains `Core message: present` and `Status: READY`
- Verify: challenges reference the core message about infrastructure and obsession
- Verify: Phase 2 section exists with evidence/debate for at least one claim
- Verify: ends with "The lesson survives if..." statement
- Verify: Credibility evaluation present
- Save output to `.claude/skills/evals/iteration-1/eval-1-challenge-ready/with_skill/outputs/output.md`

**Eval 4: /publish cut list**
- Run `/publish lessons/05-the-infrastructure-gap.md`
- Verify: output contains Core message status
- Verify: output contains `## Cut List` section
- Verify: at least one cut tagged `[Scaffold-only]`
- Verify: output asks for approval before /copyedit
- Verify: checks opening against Simple + Unexpected
- Save output to `.claude/skills/evals/iteration-1/eval-4-publish-cutlist/with_skill/outputs/output.md`

**Eval 5: /think-through SUCCESS criteria**
- Run `/think-through lessons/05-the-infrastructure-gap.md`
- Verify: output contains 3 specific questions for the author
- Verify: evaluates whether lesson is Unexpected enough to hook
- Verify: identifies a Concrete moment
- Verify: references or refines the core message
- Save output to `.claude/skills/evals/iteration-1/eval-5-think-through-success/with_skill/outputs/output.md`

**Eval 6: /review 4-agent panel**
- Run `/review lessons/05-the-infrastructure-gap.md`
- Verify: output contains feedback from 4 distinct agents (Skeptic, Outside Reader, PM Peer, Leadership Expert)
- Verify: Leadership Expert section exists with 3 ranked feedback items
- Verify: synthesis has top 5 changes with at least one tagged (patch/restructure/rethink)
- Verify: core message referenced in agent evaluations
- Save output to `.claude/skills/evals/iteration-1/eval-6-review-4agent/with_skill/outputs/output.md`

For each eval, run the skill as a subagent, save the output, then grade against the assertions. Report results as a table:

| Eval | Skill | Assertions | Pass/Fail |
|------|-------|------------|-----------|

If any eval fails, note which assertion failed and why. Do NOT fix the skill in this session — just report. Fixes happen in a separate iteration.

After all 4 pass, commit the eval results and update `continuous-improvement/task.md` to mark all evals complete.
